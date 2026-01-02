### findOne()

```javascript
db.customers.findOne({ customerId: 'C001' });
```

<table>
  <thead>
    <tr>
      <th align="center">
        Returns the document matching customerId: 'C001'
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center">

<img
  src="https://github.com/user-attachments/assets/8343cfd7-0b89-4403-9108-32067af674cd"
  width="600"
  alt="findOne"
/>

  </tbody>
</table>

---

### updateOne()

```javascript
db.customers.updateOne(
  { customerId: 'C001' },
  { $set: { email: "Jack.borwn@example.com" } }
);
```

<table>
  <thead>
    <tr>
      <th align="center">
        Updates the email for customerId: 'C001'
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center">

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

```javascript
db.customers.updateMany(
  { customerId: { $in: ["C001", "C002", "C003"] } },
  { $set: { customerCategory: "Bronze" } }
)
```

<table>
  <thead>
    <tr>
      <th align="center">
        Updates customerCategory for matched customerIds
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center">

<img
  src="https://github.com/user-attachments/assets/226836df-153f-4e8f-b1d3-bd83026592fd"
  width="600"
  alt="UpdateMany true"
/>

<img
  src="https://github.com/user-attachments/assets/bf1013a3-dc50-4670-a50b-ce770af77ad8"
  width="600"
  alt="Updated value"
/>

  </tbody>
</table>

---

### `deleteOne()`

```javascript
db.customers.deleteOne({ customerId: 'C001' });
```

<table>
  <thead>
    <tr>
      <th align="center">
        Deletes the document matching customerId: 'C001'
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center">

<img
  src="https://github.com/user-attachments/assets/4565cfb5-bbee-4dff-b718-1f9850949b8e"
  width="600"
  alt="UpdateMany true"
/>

  </tbody>
</table>

---

### `deleteMany()`

```javascript
db.customers.deleteMany({ customerCategory: "Bronze" })
```

<table>
  <thead>
    <tr>
      <th align="center">
        Delete multiple customer documents by customerCategory
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center">

<img
  src="https://github.com/user-attachments/assets/5c10fffc-8b9a-46c8-b5c6-6c8448206bca"
  width="600"
  alt="UpdateMany true"
/>

  </tbody>
</table>

---


