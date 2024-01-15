# User management
CCX does not support user mangement for Redis. Only one user is created, called the 'ccxadmin'.
The 'ccxadmin' user is created as follows, where SECRET is the password:
```
user ccxadmin >SECRET ~* +@all -@dangerous +info +slowlog +dbsize on
```

