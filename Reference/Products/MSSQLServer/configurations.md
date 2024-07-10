# Configuration
## Important default values
###  max_connections
* SQL Server has no direct "max connection per GB of RAM" rule. The actual number of user connections allowed depends on the version of SQL Server that you are using, and also the limits of your application(s), and hardware.
* SQL Server allows a maximum of 32,767 user connections.
* User connections is a dynamic (self-configuring) option, SQL Server adjusts the maximum number of user connections automatically as needed, up to the maximum value allowable.
* In most cases, you do not have to change the value for this option. The default is 0, which means that the maximum (32,767) user connections are allowed.
* To determine the maximum number of user connections that your system allows, you can execute **sp_configure** or query the **sys.configuration** catalog view.
* For more info: https://learn.microsoft.com/en-us/sql/database-engine/configure-windows/configure-the-user-connections-server-configuration-option?view=sql-server-ver16&viewFallbackFrom=sql-server-ver16.
