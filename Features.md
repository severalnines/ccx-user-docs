# CCX

Comprehensive data management and storage solution that offers a range of features including flexible node configurations, scalable storage options, secure networking, and robust monitoring tools. It supports various deployment types to cater to different scalability and redundancy needs, alongside comprehensive management functions for users, databases, nodes, and firewalls. The CCX project provides a versatile platform for efficient data handling, security, and operational management, making it suitable for a wide array of applications and workloads.

## Deployment Solutions

Our deployment solutions offer customizable configurations for various node types, designed to support both dynamic and ephemeral storage requirements across multiple cloud environments. This includes comprehensive support for a wide range of cloud regions and instances, ensuring flexibility and scalability.

## Database Support

Our platform is compatible with a diverse array of database types, including:

- MariaDB
- MySQL
- PostgreSQL
- Redis
- Microsoft SQL Server

## Cloud Service Providers

We support integration with several leading Cloud Service Providers (CSPs), including:

- Amazon Web Services (AWS)
- OpenStack
- SafeSpring

## Node Configurations

We provide support for various node configurations to meet your database needs:

- Replica nodes for MariaDB, MySQL, PostgreSQL, Redis, and Microsoft SQL Server (Single server and Always-On)
- Galera clusters for MariaDB and MySQL

## Monitoring and Management

Our platform features advanced monitoring capabilities, offering detailed performance analysis through extensive charts. It enables efficient management of nodes, including:

- Datastore scaling
- Volume scaling
- Promote replica to primary
- Node repair mechanisms

## User and Database Administration

We offer sophisticated tools for managing database users and their permissions, ensuring secure access control.

## Network Security

Our firewall configuration options are designed to enhance network security, providing robust protection for your data.

## Event Logging

The event viewer tracks and displays a comprehensive history of operations performed on the datastore, enhancing transparency and accountability.

## Backup and Recovery

Our backup solutions include:

- Incremental and full backup options for comprehensive data protection
- Point-in-time recovery capabilities
- Automated cloud backup uploads with customizable retention periods
- Restoration from separate volumes to optimize datastore space utilization

## Customizable Settings

We offer customizable settings for various operational database parameters, allowing for tailored database management.

## Account Management

Our platform facilitates user account creation and management, streamlining the login and registration process.

## Billing and Payments

Our billing and payment processing tools are designed to simplify financial transactions, including the management of payments and invoices.

# Feature Matrix
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

