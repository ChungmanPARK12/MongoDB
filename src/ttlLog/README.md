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
## Creating TTL Index on `ttlLogs` Collection

To automatically delete log entries after a specific time (e.g., 3 minutes), a **TTL (Time-To-Live)** index is created on the `loggingDateTime` field.

### TTL Index Command
```javascript
db.ttlLogs.createIndex(
  { loggingDateTime: 1 },
  { expireAfterSeconds: 180 }
);
```

 - This sets the documents to expire **180 seconds** (3 minutes) after the `loggingDateTime` value.

---

### Inserting a Sample Log Entry
```javascript
db.ttlLogs.insertOne({
  loggingDateTime: new Date(),
  transactionType: "insert",
  logMessage: "inserted document into customers collection"
});
```

 - This log will be automatically deleted 3 minutes after insertion.



