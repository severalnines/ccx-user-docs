# CCX User Documentation

## User Authentication

In CCX, all database users are created using the `caching_sha2_password` authentication plugin by default. 
This plugin requires an SSL connection to ensure secure communication between the MySQL server and clients.

## SSL Modes

CCX supports currently two SSL modes:

1. `REQUIRED`: This mode requires an SSL connection. If a client attempts to connect without SSL, the server rejects the connection.

2. `VERIFY_CA`: This mode requires an SSL connection and the server must verify the client's certificate against the CA certificates that it has.

## CA Certificate

The Certificate Authority (CA) certificate can be downloaded using an API call or through the user interface on page `https://{your_ccx_domain}/projects/default/data-stores/{datastore_id}/settings`.
This certificate is used for the `VERIFY_CA` SSL mode.


## Example Commands

Here are example commands for connecting to the MySQL server using the two supported SSL modes:

1. `REQUIRED` mode:

```bash
mysql --ssl-mode=REQUIRED -u username -p -h hostname
```

2. `VERIFY_CA` mode:
```bash
mysql --ssl-mode=VERIFY_CA --ssl-ca=ca.pem -u username -p -h hostname
```
