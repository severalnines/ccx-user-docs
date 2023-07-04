<!-- Parent: CCX-Docs --> 
<!-- Parent: End-Users --> 
<!-- Title: Datastore-Statuses --> 
When you deploy a Datastore, you will see a `Status` reported in the CCX Dashboard. This article outlines the statuses and what they mean.

| **Status** | **Description** | **Action Required?** |
| ---------- | --------------- | -------------------- |
| Deploying | Your `Datastore` is being configured and deployed into the `Cloud` you specified | No |
| Available | Your `Datastore` is up and running with no reported issues | No |
| Unreachable | Your `Datastore` might be running but CCX is not able to communicate directly with one or more `Node(s)`. | Verify you can access the `Datastore` and contact Support |
| Maintenance | Your `Datastore` is applying critical security updates during the specific maintenance window. | No |
| Deleting | You have requested the deletion of your `Datastore` and it is currently being processed. | No, unless this deletion was not requested by you or the `Datastore` has been in this state for more than 2 hours |
| Deleted | Your `Datastore` has been deleted. | No |
| Failed | Your `Datastore` has failed, this can be a hardware or software fault | Contact Support |