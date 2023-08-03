# Importing data

This procedure describes how to import data to a PostgreSQL datastore located in CCX.
- The PostgreSQL Datastore on CCX is denoted as the 'replica'
- The source of the data is denoted as the 'source'

Logical replication is used to facilitate the replication of data.

### Preparations
Ensure that the source is configured to act as a replication source.
* wal_level = logical
* listen_addresses = '*'

Restart the postgres server.

### Create a replication user
Create a replication user with sufficient privileges on the <DATABASE> you wish to replicate, using psql:
```
\c <DATABASE>
<DATABASE>=# CREATE USER repuser WITH REPLICATION  LOGIN PASSWORD 'secret';
<DATABASE>=# GRANT SELECT ON ALL TABLES IN SCHEMA public TO repuser;
```

Update pg_hba.conf to allow the replica to connect:
```
host    <DATABASE>      repuser        REPLICA_IP/32       md5
```

Reload PostgreSQL:
```
systemctl reload postgresql
```


### Create a database dump file

Dump the database schema from the  <DATABASE> you wish to replicate:

```
pg_dump --schema-only --no-publications -d<DATABASE> > /tmp/DATABASE-schema-only.sql
```

### Apply the dumpfile on the replica
Issue the following command on the source
```
psql postgres://ccxadmin:<password>@REPLICA:5432/

postgres=# CREATE DATABASE <DATABASE>;
postgres=#\c  <DATABASE>
<DATABASE>=# \i /tmp/DATABASE-schema-only.sql
```

### Publish the database on the source
Use psql and do:
```
\c <DATABASE>
<DATABASE>=#  CREATE PUBLICATION pub FOR ALL TABLES;
```

### Create the subscription on the Secondary


Connect to the replica using psql:
```
psql postgres://ccxadmin:<password>@REPLICA:5432/
```
and issue the SQL:
```
CREATE SUBSCRIPTION sub CONNECTION 'host=SOURCE port=5432 dbname=<DATABASE> user=repuser password=secret' PUBLICATION pub;
```

### Troubleshooting
If the replication fails to start then verify:
* Check pg_hba.conf on the Primary
* When adding tables on the Primary, make sure you refresh the subscription on the replica.
* Ensure the replication user is allowed to SELECT from the tables part of the publish/subscription. 




