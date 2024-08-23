# Create a datastore from backup
# Create datastore from backup
In CCX, it is possible to create a new datastore from a backup
Supported databases: MySQL, MariaDb, Postgres.

Select the backup you wish to restore in the Backup tab and select "Create datastore" from the action menu next to the backup.
This process may take some time depending on the size of the backup.
The new datastore will have the name datastore as the parent but will be suffixed with _Copy.

## Limitations
PITR is not supported yet.