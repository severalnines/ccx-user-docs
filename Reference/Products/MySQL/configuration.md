# Configuration
##  max_connections
* 75 connections / GB of RAM.
* Example: 4GB of RAM yields 300 connections.
* This setting cannot be changed as it affects system stability.

## InnoDb settings
* These setting cannot be changed as it affects system stability.
### innodb_buffer_pool_size
* 50% of RAM if total RAM is > 4GB
* 25% of RAM if total RAM is <= 4GB
### innodb_log_file_size 
* 1024 MB if innodb_buffer_pool_size >= 8192MB
* 512 MB if innodb_buffer_pool_size < 8192MB  
### innodb_buffer_pool_instances
* 8 

## Storage
### Recommended storage size
* We recommend a maximum of 100GB storage per GB of RAM.
* Example: 4GB of RAM yields 400GB of storage.
* The recommendation is not enforced by the CCX platform.


