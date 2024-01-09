# User management
CCX supports creating database users from the web interface.
The database user is created as follows:
```
CREATE LOGIN username WITH PASSWORD = 'SECRET',  DEFAULT_DATABASE=[master], CHECK_EXPIRATION=OFF,  CHECK_POLICY=OFF
ALTER SERVER ROLE [sysadmin] ADD MEMBER [username]
```
