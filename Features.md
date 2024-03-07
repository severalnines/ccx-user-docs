# Introduction to CCX
CCX is a managed database service. It offers support for the following databases:
- MySQL
- MariaDb
- Postgres
- Redis
- MS SQLServer (Not offered by Severalnines public CCX service offering)

A database in CCX is called a datastore.

## Cloud support
The following clouds are supported:
- Openstack
- Amazon AWS
- SafeSpring

# Features
Each datastore has different features and are suitable for different use cases.
Below is a feature matrix showing what operational feature is supported on each datastore:


|           | MySQL | MariaDb | PostgreSQL | Redis | MS SQLServer<br> (single server) |  MS SQLServer<br> (Always-on, std license)|
|-----------|:-----:|:-------:|:----------:|:-----:|:---------:|:---------:|
|Scale nodes| Yes | Yes | Yes | Yes | No | No |
|Scale volume| Yes | Yes | Yes | Yes | Yes | Yes |
|Upgrade | Yes | Yes | Yes | Yes | Yes | Yes |
|Promote replica| Yes | Yes | Yes | Yes | Yes | Yes |
|Configuration management| Yes | Yes | Yes | Yes | No | No |
| |  |  | |  | |  |  |
|Backup to S3 | Yes | Yes | Yes | Yes | Yes | Yes |
|Restore | Yes | Yes | Yes | Yes | Yes | Yes |
|PITR | Yes | Yes | Yes | No | No | No |
| |  |  | |  | |  |  |
| User management&dagger; | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| Create databases | Yes | Yes | Yes | Yes | No | No | No |
| Query monitoring | Yes | Yes | Yes | Yes | No | Yes | Yes |
| Database growth <br>(Capacity planning)| Yes | Yes | Yes | Yes | No | Yes | Yes |

&dagger; : User management features and scope depends on the underlying datastore. There are datastore specific limitations.

