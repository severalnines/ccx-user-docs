# MariaDb 10.x

## Overview
CCX supports two types of MariaDb clustering:
* MariaDb Replication
* MariaDb Cluster

For general purpose applications we recommend using MariaDb Replication, and we only recommend to use MariaDb Cluster 10.x if you are migrating from an existing application that uses MariaDb Cluster 10.x.

If you are new to MariaDb Cluster we stronly recommend to read about the [ MariaDb Cluster 10.x limitations](https://mariadb.com/kb/en/mariadb-galera-cluster-known-limitations/) and [MariaDb Cluster Overview](https://mariadb.com/kb/en/what-is-mariadb-galera-cluster/) to understand if your application can benefit from MariaDb Cluster.

MariaDb Replication uses the standard asynchronous replication based on GTIDs.

## Further Reading

* [Limitations of MariaDb](./limitations.md)
* [Configuration](./configuration.md)
* [Importing Data](./importing_data.md)
