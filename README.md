# MongoDB Comprehensive Guide

![MongoDB Logo](https://webimages.mongodb.com/_com_assets/cms/mongodb-logo-rgb-j6w271g1xn.jpg)

## Table of Contents

- [Introduction](#introduction)
- [Installation](#installation)
- [Basic Operations](#basic-operations)
  - [CRUD Operations](#crud-operations)
  - [Indexes](#indexes)
- [Advanced Topics](#advanced-topics)
  - [Aggregation Framework](#aggregation-framework)
  - [Replication](#replication)
  - [Sharding](#sharding)
- [Best Practices](#best-practices)
- [Resources](#resources)
- [Contributing](#contributing)

## Introduction

MongoDB is a NoSQL database that provides high performance, high availability, and easy scalability. It is document-oriented, which means it stores data in JSON-like documents with dynamic schemas.

## Installation

### Prerequisites

- Ensure you have [Homebrew](https://brew.sh/) installed on macOS or [Chocolatey](https://chocolatey.org/) for Windows.
- Alternatively, you can download MongoDB directly from the [MongoDB Download Center](https://www.mongodb.com/try/download/community).

### macOS

```sh
brew tap mongodb/brew
brew install mongodb-community@5.0
brew services start mongodb/brew/mongodb-community
```

### Windows

```sh
brew tap mongodb/brew
brew install mongodb-community@5.0
brew services start mongodb/brew/mongodb-community
```

### Linux
Refer to the official MongoDB [installation guide.](https://docs.mongodb.com/manual/installation/#mongodb-community-edition)


## Basic Operations
### CRUD Operations

### Create
```js
db.collection.insertOne({ name: "John", age: 30, city: "New York" });
db.collection.insertMany([{ name: "Jane", age: 25 }, { name: "Doe", age: 22 }]);
```

### Read
```js
db.collection.find({});
db.collection.find({ age: { $gt: 25 } });
```


### Update
```js
db.collection.updateOne({ name: "John" }, { $set: { age: 31 } });
db.collection.updateMany({ age: { $lt: 30 } }, { $set: { city: "San Francisco" } });
```


### Delete
```js
db.collection.deleteOne({ name: "John" });
db.collection.deleteMany({ age: { $lt: 25 } });
```

### Indexes
```js
db.collection.createIndex({ name: 1 });
db.collection.createIndex({ age: -1 });
```

## Advanced Topics
### Aggregation Framework
The aggregation framework provides an efficient way to perform data analysis operations.

```js
db.collection.aggregate([
  { $match: { status: "A" } },
  { $group: { _id: "$cust_id", total: { $sum: "$amount" } } },
  { $sort: { total: -1 } }
]);
```

## Replication
Replication provides redundancy and increases data availability. MongoDB achieves replication by applying operations on the primary to the secondary servers.

## Sharding
Sharding is a method for distributing data across multiple machines. MongoDB uses sharding to support deployments with very large data sets and high throughput operations.

## Best Practices
- Use appropriate indexes to improve query performance.
- Monitor your databases regularly.
- Backup your data frequently.
- Use replica sets for high availability.
- Consider sharding for large datasets.

## Resources
- [Official MongoDB Documentation](https://docs.mongodb.com/)
- [MongoDB University](https://university.mongodb.com/)
- [MongoDB Blog](https://www.mongodb.com/blog)


## Contributing
Contributions are welcome!
