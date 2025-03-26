Example:
```javascript
use admin

db.createUser({
  user: "userAdmin",
  pwd: "Password1",
  roles: [
    "userAdminAnyDatabase",
    "readWriteAnyDatabase",
    "dbAdminAnyDatabase"
  ]
});

```