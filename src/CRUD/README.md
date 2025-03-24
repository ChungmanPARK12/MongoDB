
### `findOne()`
Returns the first document that matches the query.

```javascript
db.customers.findOne({ customerID: 1 });
```

*Find the customer with `customerID` 1.*

---

### `updateOne()`
Updates the **first matching** document.

```javascript
db.customers.updateOne(
  { customerID: 1 },
  { $set: { email: "newemail@example.com" } }
);
```

*Update the email of customer with `customerID` 1.*

---

### `updateMany()`
Updates **all documents** that match the filter.

```javascript
db.customers.updateMany(
  { annualSpend: { $lt: 200 } },
  { $set: { customerCategory: "Bronze" } }
);
```

*Add a new field `customerCategory` as "Bronze" to customers who spend less than 200.*

---

### `deleteOne()`
Deletes the **first matching** document.

```javascript
db.customers.deleteOne({ customerID: 3 });
```

*Delete the customer with `customerID` 3.*

---

### `deleteMany()`
Deletes **all documents** that match the filter.

```javascript
db.customers.deleteMany({ annualSpend: { $lt: 150 } });
```

*Delete all customers whose `annualSpend` is less than 150.*

---


