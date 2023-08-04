# Importing data

This procedure describes how to import data to a PostgreSQL datastore located in CCX.
- The PostgreSQL Datastore on CCX is denoted as the 'replica'
- The source of the data is denoted as the 'source'

### Create a database dump file

Dump the database schema from the  <DATABASE> you wish to replicate:

```
pg_dump --no-owner -d<DATABASE> > /tmp/DATABASE.sql
```

### Apply the dumpfile on the replica
```
postgres=# CREATE DATABASE <DATABASE>;
```

Copy the DSN from Nodes, Connection Information in the CCX UI.
Change 'ccxdb' to  <DATABASE>:
```
psql postgres://ccxadmin:.../<DATABASE> <  /tmp/DATABASE.sql
```






