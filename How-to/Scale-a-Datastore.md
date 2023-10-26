# Scaling a datastore
This section describes how to scale a datastore:
* Scale volumes
* Scale nodes
## Scale nodes
Go to the Nodes tab, and select "Scale nodes".
The dialog allows you to select scale up or down the number of nodes.
In the dialog, you are allowed to select the Instance Size, and where applicable and Availabilty Zone for the new node.

Instance size may be larger than the currenlty used instances. This means it is possible to scale the capacity by adding larger instances. Once new nodes have been added, older nodes with less capacity may be removed and a new node maybe promoted as the new primary (in the primary-replica configurations).

### Primary - replica configurations
The new node will be added as a replica.
A new instance may promoted to the new replica. This is a good way to scale up and to have a primary with e.g more CPU cores and RAM available.

### Multi-primary configurations
In multi-primary configurations it is only possible to scale up and down to an odd number of nodes to maintain quorums and consensus protocal required by the database.

The new nodes are added as primaries.

## Scale volumes
Go to the Nodes tab, and select "Scale storage".
It is possible to extend the storage size, but it cannot be shrunk to a smaller size.
The storage of all nodes will be scaled to the new size.