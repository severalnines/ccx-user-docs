# Frequently Asked Questions
### Does CCX provide a High-availability feature
Yes

### Can I change the database configuration?
This is a managed service.

### Does CCX support multiple AZs.
CCX supports multiple AZs if the Cloud Provider does.

### Can write only instances and read only replicas be created?
Yes, but the write-only instances is read-write. It allows both reads and writes.

### Does support use a Proxy or Load Balancer (fora example, if there are 2 or more Read Replica instances, then Read can be load balanced across multiple instances).

DNS is used to facilitate this. However, the user can create his own loadbalancer (such as HAProxy or ProxySQL) and connect to the database service. A load balancer should be placed as close as possible to the user's application. We recommend that the end-user manages the loadbalancer.

### Are backups automatic?
Yes, backups are created automatically. The user can set the frequency.

## Is there an auto-upgrade SQL version feature, for minor and major updates?
Only minor upgrades. Major upgrades are not supported in an online operation.
See product documentation about upgrades (Life-cycle management)

## Can it be backed up externally, for example dumping data?
Yes. See product documentation.

### Can external data be restored, if yes, how?
See product documentation.
