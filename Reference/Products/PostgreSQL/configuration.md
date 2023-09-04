# Configuration
## Important default values

| Parameter        | Default value           | Comment  |
| ------------- |-------------| -----|
| wal_keep_size | 512 |
| max_wal_senders | min 16, max 4 x Db Node count||
| wal_level | hotstandby ||
| hot_standby |  ON | Replica nodes |
| max_connections | 100 | |
| shared_buffers | instance_memory x 0.25 | |
| effective_cache_size | instance_memory x *0.75 | |
| work_mem | instance_memory / max_connections | |
| maintenance_work_mem | instance_memory/16 | |

| Instance size (GiB RAM)       | Max connections |
| ------------- |-------------|
| < 4 | 100 |
| 8 | 200 |
| 16 | 400 |
| 32 | 800 |
| 64+ | 100 |

