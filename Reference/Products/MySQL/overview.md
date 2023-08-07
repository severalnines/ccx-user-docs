# MySQL

## Overview
CCX supports two types of MySQL clustering:
* MySQL Replication (Primary-replica configuration)
* Percona XtraDb Cluster (Multi-primary configuration)

For general purpose applications we recommend using MySQL Replication, and we only recommend to use Percona XtraDb Cluster if you are migrating from an existing application that uses Percona XtraDb Cluster.

If you are new to Percona XtraDb Cluster we stronly recommend to read about the [Percona XtraDb Cluster limitations](https://docs.percona.com/percona-xtradb-cluster/8.0/limitation.html) and [Percona XtraDb Cluster Overview](https://docs.percona.com/percona-xtradb-cluster/8.0/intro.html) to understand if your application can benefit from Percona XtraDb Cluster.

MySQL Replication uses the standard asynchronous replication based on GTIDs.

## Scaling
Storage and nodes can be scaled online.

### Nodes (horizonal)
* The maximum number of database nodes in a datastore is 5.
* Multi-primary configuration must contain an odd number of nodes (1, 3 and 5).
### Nodes (vertical)
A node cannot be scaled vertically currently. To scale to large instance type, then a larger instance must be added and then remove the unwanted smaller instances.
### Storage
* Maximum size depends on the service provider and instance size
* Volume type cannot currently be changed



## Further Reading

* [Limitations](./limitations.md)
* [Configuration](./configuration.md)
* [Importing Data](./importing_data.md)
