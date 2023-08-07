# Limitations of MySQL
Every product has limitations. Here is a list MySQL limitations:
## Permissions
The privilege system is not as flexible as in MySQL.
The 'ccxadmin' user has the following privileges:
* Global / all databases (*.*):
* * SELECT, INSERT, UPDATE, DELETE, CREATE, DROP, RELOAD, PROCESS, REFERENCES, INDEX, ALTER, SHOW DATABASES, CREATE TEMPORARY TABLES, LOCK TABLES, EXECUTE, REPLICATION SLAVE, REPLICATION CLIENT, CREATE VIEW, REPLICATION_SLAVE_ADMIN, SHOW VIEW, CREATE ROUTINE, ALTER ROUTINE, CREATE USER, EVEN\
T, TRIGGER, GRANT

* This means that the 'ccxadmin' may assign privileges to users on all databases.

### Restrictions:
'ccxadmin' is not allowed to modify the following databases
* mysql.*
* sys.*

For those database, the following privileges have been revoked from 'ccxadmin':
* INSERT, UPDATE, DELETE, CREATE, DROP, REFERENCES, INDEX, ALTER, CREATE TEMPORARY TABLES, LOCK TABLES, EXECUTE, CREATE\
 VIEW, SHOW VIEW, CREATE ROUTINE, ALTER ROUTINE, EVENT, TRIGGER

