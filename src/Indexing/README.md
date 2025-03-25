Example:
### Create Index
```javascript
db.customers.createIndex({ customerID: 1 });
```
 - Creates an ascending index on the `customerID` field to improve query performance.

---

### View Existing Indexes
```javascript
db.customers.getIndexes();
```
 - Displays all indexes currently defined on the `customers` collection, including the default `_id` index.

---

## Viewing Indexes in MongoDB Compass

The screenshot below shows that the indexes created using `createIndex()` are successfully visible in **MongoDB Compass** under the **Indexes** tab.

✅ You can see:
- `_id_` (default unique index)
- `customerID_1` (manually created)
- `firstName_1_lastName_1` (compound index)

This confirms that indexes can be visually verified using the MongoDB Compass GUI.

![Image](https://github.com/user-attachments/assets/6e4fbc40-7d67-4ac6-801c-de7bf420c1b1)


