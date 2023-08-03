# Importing data

This procedure describes how to import data to a MariaDb datastore located in CCX.
- The MariaDb Datastore on CCX is denoted as the 'replica'
- The source of the data is denoted as the 'source'

Note! If you do not want to setup replication, then you can chose to only apply the sections:
* Create a database dump file
* Apply the dumpfile on the replica

### Limitations of MariaDb
MariaDb does not offer as fine grained control over privileges as MySQL.
Nor does it have the same level of replication features.
The following properties must be respected in order to comply with the SLA:
* There must be no user management happening on the source, while the data is imported and the replication link is active. This is avoid corruption of the mysql database and possibly other system databases.
* It is recommended to set binlog-ignore-db on the source to 'mysql, performance_schema, and sys' during the data import/sync process.


### Preparations
Ensure that the source is configured to act as a replication source.
* Binary logging is enabled.
* Server_id is set to non 0.
Also, prepare the replica with the databases you wish to replicate from the source to the master:
* Using the CCX UI, go to Databases, and issue a Create Database for each database that will be replicated.
Ensure the CCX Firewall is updated:
* Add the replication source as a Trusted Source in the Firewall section of the CCX UI.

### Create a replication user
Create a replication user with sufficient privileges on the source:
```
CREATE USER 'repluser'@'%' IDENTIFIED BY '<SECRET>';
GRANT REPLICATION SLAVE ON *.* TO 'repluser'@'%';
```
### Prepare the replica to replicate from the source
The replica must be instrucuted to replicate from the source.
Make sure to change <SOURCE_IP>, <SOURCE_PORT>, and <SECRET>.
```
CHANGE MASTER TO MASTER_HOST=<SOURCE_IP>, MASTER_PORT=<SOURCE_PORT>, MASTER_USER='repluser', MASTER_PASSWORD='<SECRET>', MASTER_SSL=1;
```

### Create a database dump file
The database dump contains the data that you wish to import into the replica. Only partial dumps are possible. The dump must not contains any mysql or other system datbases.
On the source, issue the following command. Change ADMIN, SECRET and DATABASES:
```
mysqldump -uADMIN -pSECRET   --master-data --single-transaction --triggers --routines --events --databases DATABASES > dump.sql
```
Important! If your database dump contains SPROCs, triggers or events, then you must replace DEFINER:
```
sed 's/\sDEFINER=`[^`]*`@`[^`]*`//g' -i dump.sql
```

### Apply the dumpfile on the replica
cat dump.sql | mysql -uccxadmin -p -h<REPLICA_PRIMARY>

### Start the replica
On the replica do:
```
START SLAVE
```
followed by
```
SHOW SLAVE STATUS;
```
And verify that:
```
             Slave_IO_State: Waiting for source to send event
	     ..
  	     Slave_IO_Running: Yes
             Slave_SQL_Running: Yes
```	     
### When the migration is ready
```
STOP SLAVE;
RESET SLAVE ALL;
```


### Troubleshooting
If the replication fails to start then verify:
* All the steps above has been followed.
* Ensure that the replication source is added as a Trusted Source in the Firewall section of the CCX UI.
* Ensure that you have the correct IP/FQDN of the replication source.
* Ensure that users are created correctly and using the correct password.
* Ensure that the dump is fresh.



