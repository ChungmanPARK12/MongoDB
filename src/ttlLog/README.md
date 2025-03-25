Example:
```javascript
db.createCollection("ttlLogs", {
  validator: {
    $jsonSchema: {
      bsonType: "object",
      required: ["loggingDateTime", "transactionType", "logMessage"],
      properties: {
        _id: {},
        loggingDateTime: {
          bsonType: "date",
          description: "Require the loggingDateTime"
        },
        transactionType: {
          bsonType: "string",
          description: "Require the transactionType"
        },
        logMessage: {
          bsonType: "string",
          description: "Require the log message for the sales status"
        }
      }
    }
  }
});
```
