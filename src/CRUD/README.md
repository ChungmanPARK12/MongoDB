
<table>
  <thead>
    <tr>
      <th align="center">
        Returns the document that matches the query
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center">

'db.customers.findOne({ customerId: 'C001' });'

<img
  src="https://github.com/user-attachments/assets/8343cfd7-0b89-4403-9108-32067af674cd"
  width="450"
  alt="findOne"
/>

  </tbody>
</table>

---

<table>
  <thead>
    <tr>
      <th align="center">
        Updates the matching document.
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center">

`db.customers.updateOne(
  { customerId: 'C001' },
  { $set: { email: "Jack.borwn@example.com" } }
);`

<img
  src="https://github.com/user-attachments/assets/f9680f99-9e8a-466f-816e-a0b8f25cb90c"
  width="600"
  alt="Update true"
/>

<img
  src="https://github.com/user-attachments/assets/7068b277-2d5b-4393-bb56-e4beec366648"
  width="600"
  alt="Updated value"
/>

  </tbody>
</table>

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


