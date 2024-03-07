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


|| MySQL | MariaDb | PostgreSQL | Redis | MS SQLServer<br> (single server) |  MS SQLServer<br> (Always-on, std license)|
|Feature|:---------:
|Scale nodes| Yes |



| Datastore/Feature   |    Scale nodes   |  Scale volume size | Upgrade | Backup/Restore | User mgmt | 
|----------|:-------------:|:------:|:------:|:------:|:------:|
| MySQL | Yes, max 5 | Yes | Yes | Yes |
| MariaDb | yes, max 5   | Yes | Yes | Yes |
| PostgreSQL | yes, max 5 | Yes | Yes | Yes |
| Redis | yes, max 5 | Yes | Yes | Yes | Yes |
| MS SQLServer (single server) | No  | Yes | Yes | Yes | Yes |
| MS SQLServer (Always-on, std license) | No  | Yes | Yes | Yes |


S3: Backups are stored in an S3 compatible storage.
