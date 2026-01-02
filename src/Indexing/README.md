
### Create Index
```javascript
db.customers.createIndex({ customerID: 1 });
```
 - Creates an ascending index on the `customerID` field to improve query performance.

---

```javascript
db.customers.createIndex({ firstName: 1, lastName: 1 })
```
 - Creates an ascending index on the `firstName` and  `lastName` field to optimise name-based queried.

### View Existing Indexes
```javascript
db.customers.getIndexes();
```
 - Displays all indexes currently defined on the `customers` collection, including the default `_id` index.

<img width="500" height="250" alt="Image" src="https://github.com/user-attachments/assets/99bbf27e-e834-4e24-9bfe-8e60cb16d869" />

---

## Viewing Indexes in MongoDB Compass

The screenshot below shows that the indexes created using createIndex() are successfully visible in MongoDB Compass under the Indexes tab.

You can see:
- `_id_` (default unique index)
- `customerId_1` (manually created)
- `firstName_1_lastName_1` (compound index)

<img width="1000" height="500" alt="Image" src="https://github.com/user-attachments/assets/e1595285-e7a7-400c-a8fa-38965ee6c696" />


