CCX is provided as a managed service for your database engine in the cloud(s) you select. This document aims to outline the responsibilities of CCX and what rests with you, as the user.

CCX does:
- Deploy, secure and configure database engines onto virtual machines (VMs) in your chosen cloud
- Allow you to:
  - Configure firewall rules for access
  - Create new databases and users
  - Configure replication for the chosen topology
  - Ensure connectivity between nodes
  - View metrics for each VM and the datastore
  - View query statistics for your service
  - Configure and set a backup schedule for your service
  - Configure a maintenance window that allows CCX to perform maintenance and provide security patches
  - Scale your service horizontally (up and down)
  - Scale your storage vertically (up)
  - Manage and monitor the database to ensure connectivity

The primary responsibility of CCX is to ensure that your datastore is running at all times, reacting to scenarios to ensure this is true. CCX does not access your data or control how you use the databases within your datastore.

In order to achieve this, CCX does not:
  - Provide SSH or other ways to access the underlying infrastructure
  - Allow superuser access to the managed services
  - Allow the modification of settings that are not suitable for production use
  - Allow the installation of untrusted extensions or code


If you do have specific requirements, such as:
1. Temporary modification of configuration
2. Feature requests for extensions or different versions of the databases

Please reach out to Support and we will work with you to find a solution.