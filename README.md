# Mongo-DB

## What is Mongo DB
Mongo DB is a database solution to store data. It's a `NoSQL` database. Mongo DB allows the user to store data in a json format. Unlike the other `SQL` databases, it offers the flexibility to store and query data in a most efficient way. Mongo DB is schemaless.

A Mongo DB server can contain multiple databases. Each data base contains `Collections` which is similar to the tables in SQL. Each collection contains `Documents` which is nothing but the data we are storing in the Collection.

Mongo DB saves data in a BSON format (Binary JSON). We will provide data in JSON format and MongoDB Driver will convert that into BSON.

Each document in a collection will have a unique _id. By default, it will be created by MongoDB. If you want to explicitly provide an _id, then add a key called `_id` in your document object. You can't insert 2 documents with same _id.

## Installing Mongo db Community Server
https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-os-x/

## Run MongoDB Shell
`mongosh`

## Create a database
`use <database_name>` This command will create and switch to the database.
Eg: `use shop`

Collections can be created on demand.
Eg: `db.products`

## Commands

| Command | Description | Operation | Example |
| ------- | ----------- | -------- | ------- |
| `.insertOne(data)` | Inserts one document into the collection | Create | `db.products.insertOne({name: "Book", price: 50})`|
| `.insertMany(data)` | Inserts multiple documents in onetime | Create | `db.products.insertMany([{name: "Pen", price: 10}, {name: "T-Shirt", price: 500}])`|
|`.find(filter, options)`| Displays documents in the collection | Read | `db.products.find()` |
|`.findOne(filter, options)`| Displays only one document in the collection | Read | `db.products.findOne({name: "Pen"})` |
|`.updateOne(filter, data, options)`| Updates only one document in the collection | Update | `db.products.updateOne({name: "Pen"}, {$set: {price: 20}})` |
|`.updateMany(filter, data, options)`| Updates multiple documents in the collection | Update | `db.products.updateMany({name: "Pen"}, {$set: {color: "blue"}})` |
|`.replaceOne(filter, data, options)`| replaces only one document in the collection | Update | `db.products.replaceOne()` |
|`.deleteOne(filter, options)`| Delete only one document in the collection | Delete | `db.products.deleteOne({name: "Pen"})` |
|`.deleteMany(filter, options)`| Delete multiple documents in the collection | Delete | `db.products.deleteMany({name: "Pen"})` |

## Cursor
The `find` method returns a cursor instead of complete data. You can either user `toArray()` method of `forEach(callback)` methods to access data. 

## Filters
Filters are used to limit the quantity of data based on a criteria.

## Projector
Projector is nothing but, it is used to limit the data keys we are fetching from a document. 
Eg: `db.patients.find({}, {name: 1, _id: 0})`. This fetches all the names in the patients collection.

## Operators
Eg: `$set` `$gt` `$lt`