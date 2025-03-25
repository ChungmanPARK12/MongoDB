# MongoDB - ShoppingWorld

## 📝 Project Overview

**ShoppingWorld** is an online shopping company headquartered in **South Australia**, using a **MySQL relational database**. As the business expands globally, the current system is facing **performance issues**, especially with enquiries related to **customers, suppliers, and shopping details**.

To address this, the company is exploring a **NoSQL solution**, particularly **MongoDB**, inspired by the success of its **sister company in the US**.

## 💡 Key Objectives

- Improve performance for frequent customer and sales staff enquiries.
- Enable scalable solutions to meet the growing demand and data volume.
- Support distributed offices in various countries for localized support.
- Handle semi-structured or unstructured data, where transactions may vary in data fields.
- Maintain ACID compliance, along with availability and partition tolerance.
- Develop a MongoDB-based prototype as a pilot project before full implementation.

## 1.Data Structure Design

MongoDB schema designed for **flexibility**, **scalability**, and **performance**, using embedded documents to support global business growth.

- **View Code:** [Click here](https://github.com/ChungmanPARK12/MongoDB/tree/6dc101f2e7feebe00446ec271e23d13afd83de16/src/DesignData)

## 2.Inserting Data

Use the **Mongosh shell** to create collections and insert sample data.

- **View Code:** [Click here](https://github.com/ChungmanPARK12/MongoDB/tree/7d3eb8fc607d82efde9a3b1576c97d8a71c6bcb5/src/InsertData)

### CRUD Operations on `customers` Collection

This section demonstrates Create, Read, Update, and Delete operations using MongoDB shell commands.

- **View Code:** [Click here](https://github.com/ChungmanPARK12/MongoDB/tree/7d3eb8fc607d82efde9a3b1576c97d8a71c6bcb5/src/CRUD)

### Schema Validation on `customers` Collection

Although MongoDB is a flexible NoSQL database that allows schema-less design, **schema validation** is important for the following reasons:

- **Data Consistency**: Ensures documents follow a defined structure and contain required fields.
- **Error Prevention**: Reduces bugs caused by missing or incorrect data types.
- **Data Integrity**: Prevents invalid data from being inserted or updated.
- **Reliable Queries**: Helps developers write more predictable queries and aggregations.
- **Security**: Blocks untrusted users from injecting malformed or harmful data.

MongoDB uses **JSON Schema validation** to define rules for each collection (like required fields, data types, value ranges, etc.).

 - **View Code:** [Click here](https://github.com/ChungmanPARK12/MongoDB/tree/7d3eb8fc607d82efde9a3b1576c97d8a71c6bcb5/src/CRUD)


 
