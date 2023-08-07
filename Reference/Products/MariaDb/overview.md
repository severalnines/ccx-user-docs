# MariaDb 10.x

## Overview
CCX supports two types of MariaDb clustering:
* MariaDb Replication (Primary-replica configuration)x
* MariaDb Cluster (Multi-primary configuration)

For general purpose applications we recommend using MariaDb Replication, and we only recommend to use MariaDb Cluster if you are migrating from an existing application that uses MariaDb Cluster.

If you are new to MariaDb Cluster we stronly recommend to read about the [ MariaDb Cluster 10.x limitations](https://mariadb.com/kb/en/mariadb-galera-cluster-known-limitations/) and [MariaDb Cluster Overview](https://mariadb.com/kb/en/what-is-mariadb-galera-cluster/) to understand if your application can benefit from MariaDb Cluster.

MariaDb Replication uses the standard asynchronous replication based on GTIDs.

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

* [Limitations of MariaDb](./limitations.md)
* [Configuration](./configuration.md)
* [Importing Data](./importing_data.md)
