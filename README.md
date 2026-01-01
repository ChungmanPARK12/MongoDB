# MongoDB - ShoppingWorld
![Image](https://github.com/user-attachments/assets/f9f680b3-1913-4024-a805-5a8f09141c37)

## Overview

**ShoppingWorld** is an online shopping company headquartered in **South Australia**, using a **MySQL relational database**. As the business expands globally, the current system is facing **performance issues**, especially with enquiries related to **customers, suppliers, and shopping details**.

To address this, the company is exploring a **NoSQL solution**, particularly **MongoDB**, inspired by the success of its **sister company in the US**.

## Purpose

This learning project focuses on understanding how **MongoDB** can be used to explore common limitations of relational databases.  

- Explore how document-based data models support **flexibility and scalability**
- Practice core MongoDB features such as **CRUD operations, aggregation, and indexing**
- Build a small **prototype** to evaluate MongoDB as an alternative data store

## Tools Used

- **Mongo Shell (mongosh)** – For running database commands and queries.
- **MongoDB Compass** – For visualizing collections, documents, indexes, and schema validation.


### 1.Data Structure Design

MongoDB schema designed for **flexibility**, **scalability**, and **performance**, using embedded documents to support global business growth.

- [View result](src/DesignData)

### 2.Inserting Data

Use the **Mongosh shell** to create collections and insert sample data.

- [View result](src/InsertData)

### CRUD Operations on `customers` Collection

This section demonstrates **Create**, **Read**, **Update**, and **Delete** operations using MongoDB shell commands.

- [View result](https://github.com/ChungmanPARK12/MongoDB/tree/7d3eb8fc607d82efde9a3b1576c97d8a71c6bcb5/src/CRUD)

### Schema Validation on `customers` Collection

The `customers` collection uses JSON Schema validation to enforce minimal data consistency.

 - [View result](https://github.com/ChungmanPARK12/MongoDB/tree/f686f750e5a9eabd286b12c3beea851690ab4c9c/src/Validation)

### 3.Relation to Query Design, Indexing, and Sharding

- **Query Design**: Uses `$lookup` to join documents from multiple collections.
- **Indexing**: Indexes are added on `customerID` in both `customers` and `shopping_Carts` to improve query performance.
- **Sharding/Partitioning**: Sharding distributes large datasets, with `$lookup` performing best when collections share the same shard key (e.g., `customerID`).

### Aggregation with `$lookup`

Joins `customers` and `shopping_Carts` collections to show cart details for customer with `customerID: 2`.
  - **View Code:** [Click here](https://github.com/ChungmanPARK12/MongoDB/tree/e1f96a4ac7e926a50aa8e7746cb000a8b1d9e20c/src/Aggregation)

### Indexing on `customers`

  - **View Code:** [Click here](https://github.com/ChungmanPARK12/MongoDB/tree/e1f96a4ac7e926a50aa8e7746cb000a8b1d9e20c/src/Indexing)

### Creating `ttlLogs` Collection with Schema Validation

This section demonstrates how a `ttlLogs` collection is defined with schema validation and prepared for use with a TTL index.

  - **View Code:** [Click here](https://github.com/ChungmanPARK12/MongoDB/tree/b0d517ee442a678dd03653d441872363aa177f82/src/ttlLog)

### 4.User Access Control

 Grants the user administrative privilegs across all database:
  - `userAdminAnyDatabase`: Create/manage users
  - `readWriteAnyDatabase`: Read/write access to all DBs
  - `dbAdminAnyDatabase`: Admin functions like index creation

  - **View Code:** [Click here](https://github.com/ChungmanPARK12/MongoDB/tree/6d92d0014b92eacb5381169a0fc7bd43fcda9521/src/CreateUser)

## Summary

This project explores MongoDB through a ShoppingWorld case study, focusing on schema design, querying, indexing, and access control as part of a learning-driven NoSQL prototype.








 







 
