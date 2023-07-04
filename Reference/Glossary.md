<!-- Parent: CCX-Docs --> 
<!-- Parent: End-Users --> 
<!-- Title: Glossary --> 
| **Term** | **Definition** | **AKA** | **Area** |
| -------- | ------------- | --------- | -------- |
| Datastore | A deployment of a `Database` on `CCX`. A `Datastore` has a unique ID, it is essential to include this when contacting Support with issues or queries. | Service | Deployment |
| Node | A Virtual Machine (VM) in a `Cloud` that makes up a `Datastore`. A `Node` consists of:<br>- CPU - the number of cores <br>  <br>- RAM - the amount (GB) of memory<br>  <br>- Storage - the amount (GB/TB) of persistent storage | Virtual Machine (VM)<br>Node<br>Server<br>Instance | Compute |
| Storage | The amount of persistent data for your `Datastore`.<br>Storage comes in multiple different formats and not all are supported by all `Clouds`. There are cost and performance considerations when choosing the storage. |  | Storage |
| Volumes | The types of `Storage` available. Typically, this is measured in `IOPS` and the higher `IOPS` has increased performance with an increased cost per GB |  |  |
| Database | The engine deployed and configured for your `Datastore`. To see these options, check Supported Databases | Database Management System (DBMS) | General |
| Virtual Private Cloud (VPC) | A private network configured that is unique to your account and ensures that any traffic between your `Datastore` does not go over the Public Internet | Private Network | Networking |
| Cloud | An infrastructure provider where `Datastores` can be deployed |  | Deployment |
| Region | A geographic region with one or more `Datacentres` owned or operated by a `Cloud`. A `Datastore` is deployed into a single `Region` |  | Deployment |
| Availability Zone (AZ) | A `Region` can have one or more `Availability Zones`. More than one `Availability Zones` allows one `Datacentre` to go down without bringing down all of the `Nodes` in your `Datastore`.<br>CCX will automatically attempt to deploy each `Node` in a `Datastore` into a different `AZ` (if the `Region` supports it) |  | Deployment |
| Replication | A method of exchanging data between two `Nodes` that ensures they stay in sync and allows one Node to fail without bringing your `Datastore` down |  | Operations |
| Primary / Replica | The recommended deployment for a Production `Datastore` with 2 or more `Nodes`, one acting as the `Primary` and the other(s) acting as the `Replica` | Highly Available<br>High Availability | Operations |
| Multi-Primary | Multiple `Nodes` deployed with the same role, all of them acting as the `Primary`. This topology is not supported by all `Databases` | Clustered | Operations |
| Status | The last known status of your `Datastore`. For details of the possible statuses, see [here](./Datastore-Statuses.md) | State | Operations |
| Maintenance | The application of critical security updates to your `Datastore`. These are applied in your `Maintenance Window` which can be configured per `Datastore`. |  | Operations |
| Monitoring | This is the metrics of the hardware and software for your `Datastore`. These can be accessed in the CCX Dashboard and can be shown per `Node`. For details of the metrics available, see [here](./Observability/Metrics/README.md). |  | Observability |