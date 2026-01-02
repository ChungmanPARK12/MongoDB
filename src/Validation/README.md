### customers Collection:

```javascript
db.createCollection("customers", {
  validator: {
    $jsonSchema: {
      bsonType: "object",
      required: ["customerId", "firstName", "email"],
      properties: {
        customerId: { bsonType: "string" },
        firstName: { bsonType: "string" },
        lastName: { bsonType: "string" },
        email: { bsonType: "string" },

        customer_addresses: {
          bsonType: "array",
          items: {
            bsonType: "object",
            required: ["addressId", "addressType", "street", "city", "postCode", "state", "country"],
            properties: {
              addressId: { bsonType: "int" },
              addressType: { bsonType: "string" },
              street: { bsonType: "string" },
              city: { bsonType: "string" },
              postCode: { bsonType: "string" },
              state: { bsonType: "string" },
              country: { bsonType: "string" }
            }
          }
        },

        phones: {
          bsonType: "array",
          items: {
            bsonType: "object",
            required: ["phoneId", "phoneNumber", "phoneType"],
            properties: {
              phoneId: { bsonType: "int" },
              phoneNumber: { bsonType: "string" },
              phoneType: { bsonType: "string" }
            }
          }
        },

        interests: {
          bsonType: "array",
          items: {
            bsonType: "object",
            required: ["interestId", "interestName"],
            properties: {
              interestId: { bsonType: "int" },
              interestName: { bsonType: "string" }
            }
          }
        }
      }
    }
  },
  validationLevel: "strict",
  validationAction: "error"
})

```

---

### Validation Failed (Required Field Missing)

```javascript
db.customers.insertOne({
  customerId: "C001",
  firstName: "John"
})
```

<table>
  <thead>
    <tr>
      <th align="center">
         Insert failed because the required field "email" is missing
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center">

<img
  src="https://github.com/user-attachments/assets/bda43865-4733-4771-afb2-fa24762c6b78"
  width="600"
  alt="UpdateMany true"
/>

  </tbody>
</table>

### Validation Passed (Required Fields Only)

```javascript
db.customers.insertOne({
  customerId: "C001",
  firstName: "John",
  email: "john@example.com"
})
```

<table>
  <thead>
    <tr>
      <th align="center">
       Insert succeeded with only the required fields provided
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center">

<img
  src="https://github.com/user-attachments/assets/ee49cbaf-0c28-499a-a530-0fbb345bf9f9"
  width="600"
  alt="Validation true"
/>

  </tbody>
</table>

