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

- [View result](src/CRUD)

### Schema Validation on `customers` Collection

The `customers` collection uses JSON Schema validation to enforce minimal data consistency.

 - [View result](src/Validation)

### 3.Relation to Query Design, Indexing, and Sharding

- **Query Design**: Uses `$lookup` to join documents from multiple collections.
- **Indexing**: Indexes are added on `customerID` in both `customers` and `shopping_Carts` to improve query performance.
- **Sharding/Partitioning**: Sharding distributes large datasets, with `$lookup` performing best when collections share the same shard key (e.g., `customerID`).

### Aggregation with `$lookup`

Demonstrates the use of `$lookup` to join selected collections and retrieve information associated with customers.

  - [View result](src/Aggregation)

### Indexing on `customers`

  - [View result](src/Indexing)

### Creating `ttlLogs` Collection with Schema Validation

TTL indexes are used to manage time-bound data by automatically removing documents after a defined lifespan, making them suitable for logs, sessions, caches, and other temporary data.

  - [View result](src/ttlLog)

### 4.User Access Control

 Grants the user administrative privilegs across all database:
  - `userAdminAnyDatabase`: Create/manage users
  - `readWriteAnyDatabase`: Read/write access to all DBs
  - `dbAdminAnyDatabase`: Admin functions like index creation

  - [View result](https://github.com/ChungmanPARK12/MongoDB/tree/6d92d0014b92eacb5381169a0fc7bd43fcda9521/src/CreateUser)

## Summary

This project explores MongoDB through a ShoppingWorld case study, focusing on schema design, querying, indexing, and access control as part of a learning-driven NoSQL prototype.








 







 
