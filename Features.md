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

| Datastore/Feature   |    Scale nodes   |  Scale volume size |
|----------|:-------------:|------:|
| MySQL | Yes, max 5 | Yes
| MariaDb | yes, max 5   | Yes 
| PostgreSQL | yes, max 5 | Yes |
| Redis | yes, max 5 | Yes |
| MS SQLServer (single server) | No  | Yes1 |
| MS SQLServer (Always-on, std license) | No  | Yes |

