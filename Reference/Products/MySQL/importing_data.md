# Importing data

This procedure describes how to import data to a MySQL datastore located in CCX.
- The MySQL Datastore on CCX is denoted as the 'replica'
- The source of the data is denoted as the 'source'

Note! If you dont want to setup replication, then you can chose to only apply the sections:
* Create a database dump file
* Apply the dumpfile on the replica

### Preparations
Ensure that the source is configured to act as a replication source.
* Binary logging is enabled.
* Server_id is set to non 0.

Create a replication user with sufficient privileges on the source.
```
CREATE USER 'repluser'@'%' IDENTIFIED BY '<SECRET>';
GRANT REPLICATION SLAVE ON *.* TO  'repluser'@'%';
```
### Prepare the replica to replicate from the source
The replica must be instrucuted to replicate from the source.
Make sure to change <SOURCE_IP>, <SOURCE_PORT>, and <SECRET>.
```
CHANGE REPLICATION SOURCE TO SOURCE_HOST=<SOURCE_IP>, SOURCE_PORT=<SOURCE_PORT>, SOURCE_USER='repluser', SOURCE_PASSWORD='<SECRET>', SOURCE_SSL=1;
```
### Create a replication filter on the replica
The replica filter prevents corruption of the datastore.
If the datastore's system tables are corrupted using replication then the SLA is void and the datastore must be recreated.

```
CHANGE REPLICATION FILTER REPLICATE_IGNORE_DB=(mysql,sys, performance_schema);
```

### Create a database dump file
The database dump contains the data that you wish to import into the replica. Only partial dumps are possible. The dump must not contains any mysql or other system datbases.
On the source, issue the following command:
```
mysqldump --set-gtid-purged=OFF -uUSER -pSECRET   --master-data --single-transaction --databases --triggers --routines --events DATABASES > dump.sql
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
START REPLICA;
```
followed by
```
SHOW REPLICA STATUS;
```
And verify that:
```
             Replica_IO_State: Waiting for source to send event
	     ..
  	     Replica_IO_Running: Yes
             Replica_SQL_Running: Yes
```	     
### When the migration is ready
```
STOP REPLICA;
CHANGE REPLICATION FILTER REPLICATE_IGNORE_DB=();
```


### Troubleshooting
If the replication fails to start then verify:
* All the steps above has been followed.
* Ensure that the replication source is added as a Trusted Source in the Firewall section of the CCX UI.
* Ensure that you have the correct IP/FQDN of the replication source.
* Ensure that users are created correctly and using the correct password.
* Ensure that the dump is fresh.



