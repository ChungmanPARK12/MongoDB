Example:
```javascript
db.createCollection("customers", {
  validator: {
    $jsonSchema: {
      bsonType: "object",
      required: ["customerID", "firstName", "email"],
      properties: {
        customerID: { bsonType: "int" },
        firstName: { bsonType: "string" },
        email: { bsonType: "string" }
      }
    }
  }
});
```