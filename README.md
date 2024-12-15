MongoDB Overview
MongoDB is a NoSQL, document-oriented database that stores data in flexible, JSON-like documents, which allows for easy storage and retrieval of data. Unlike relational databases, MongoDB does not require a predefined schema, making it ideal for handling semi-structured data. It is designed for high performance, scalability, and ease of development.

Key Concepts:
Document: The basic unit of data in MongoDB, represented as a JSON object (in BSON format).
Collection: A group of MongoDB documents, similar to a table in a relational database.
Database: A container for collections.
CRUD Operations in MongoDB
CRUD stands for Create, Read, Update, and Delete — the four basic operations to manage data in a database. Below is an explanation of each operation with MongoDB-specific commands:

1. Create
The Create operation allows you to add new documents to a collection.

Command: insertOne() / insertMany()
insertOne() adds a single document.
insertMany() adds multiple documents in one operation.
Example:
javascript
Copy code
db.users.insertOne({
  name: "John Doe",
  email: "john@example.com",
  age: 30
})
2. Read
The Read operation retrieves documents from a collection. MongoDB provides various querying mechanisms to fetch data based on conditions.

Command: find() / findOne()

find() retrieves all documents or documents matching a condition.
findOne() retrieves a single document.
Example:

javascript
Copy code
db.users.find({ age: { $gt: 25 } })
db.users.findOne({ name: "John Doe" })
3. Update
The Update operation modifies an existing document in a collection. You can update one or multiple documents based on specific criteria.

Command: updateOne() / updateMany()

updateOne() updates the first document that matches the criteria.
updateMany() updates all documents that match the criteria.
Example:

javascript
Copy code
db.users.updateOne(
  { name: "John Doe" },
  { $set: { age: 31 } }
)
4. Delete
The Delete operation removes documents from a collection.

Command: deleteOne() / deleteMany()

deleteOne() removes the first document that matches the condition.
deleteMany() removes all documents that match the condition.
Example:

javascript
Copy code
db.users.deleteOne({ name: "John Doe" })
MongoDB Operators Used in CRUD Operations:
$gt (Greater Than): Used to find documents with values greater than a given number.
javascript
Copy code
db.users.find({ age: { $gt: 25 } })
$lt (Less Than): Used to find documents with values less than a given number.
javascript
Copy code
db.users.find({ age: { $lt: 25 } })
$set: Used to modify a field's value in an existing document.
javascript
Copy code
db.users.updateOne({ name: "John Doe" }, { $set: { age: 35 } })
$and / $or: Used for complex queries involving multiple conditions.
javascript
Copy code
db.users.find({ $and: [{ age: { $gt: 25 } }, { status: "active" }] })
Advantages of MongoDB CRUD:
Flexible Schema: MongoDB's document-based structure allows for easy handling of diverse data types without requiring a fixed schema.
Scalability: MongoDB supports horizontal scaling through sharding, distributing data across multiple servers.
High Performance: MongoDB is optimized for high throughput and low latency.
In conclusion, MongoDB's CRUD operations provide a simple and effective way to interact with data, supporting various complex queries and allowing for rapid development with high performance.



