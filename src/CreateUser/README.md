### Administrative User(Global Privileges)

An administrative user with global privileges, allowing user management and full read/write access across all databases.

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
---

The following command creates a user named `JimBrown` with **read-only access** to the `shoppingCartDB` database.

```javascript
db.createUser({
  user: "JimBrown",
  pwd: "Password1",
  roles: [
    { role: "read", db: "shoppingCartDB" }
  ]
});
```
---
