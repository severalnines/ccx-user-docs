 Backup
# Backups
Mariabackup is used to create backups.
## Backup locks
Mariabackup  blocks DDL operations during the backup using the --lock-ddl flag.
Any attempt to CREATE, ALTER, DROP, TRUNCATE a table during backup creation will be locked with the status 'Waiting for backup lock'  (see SHOW FULL PROCESSLIST).
In this case, wait for the backup to finish and, perform the operation later.
CCX backups a Primary server.

Also see the secion 'Schedule'.
## Schedule
The backup schedule can be tuned and backups can be paused

