# Life-cycle management and upgrade
CCX will keep your system updated with the latest security patches for both the operating system and the database software.

You will be informed when there is a pending update and you have two options:
- Apply the update now
- Schedule a time for the update

The update will be performed using a roll-forward upgrade algorithm:
1. The oldest replica (or primary if no replica exist) will be selected first
2. A new node will be added with the same specification as the oldest node and join the datastore
3. The oldest node will be removed
4. 1-3 continues until all replicas (or primaries in case of a multi-primary setup)  are updated.
5. If it is a primary-replica configuration then the primary will be updated last. A new node will be added, the new node will be promoted to become the new primary, and the old primary will be removed.

## Upgrade now
This option will start the upgrade now.

## Scheduled upgrade
The upgrade will start at a time (in UTC) and on a weekday which suits the application.
Please note, that for primary-replica configurations, the update will cause the current primary to be changed.

