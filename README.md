# 🔹 Introduction

## What is MongoDB?
MongoDB is a NoSQL database that stores data in JSON-like documents called BSON (Binary JSON). It's schema-less, meaning each document can have different fields.

🔄 SQL vs NoSQL
Feature	SQL (Relational DB)	NoSQL (MongoDB)
Structure	Tables, Rows	Collections, Documents
Schema	Fixed	Dynamic
Joins	Supports complex joins	Limited joins
Scalability	Vertical	Horizontal (easier to scale)

🧾 JSON vs BSON
JSON: Human-readable text format.

BSON: Binary format used internally by MongoDB. Supports more data types like Date, ObjectId.

☁️ MongoDB Atlas & Compass
Atlas: MongoDB's cloud-hosted database service.

Compass: GUI tool to visualize, query, and manage MongoDB data.

🔹 MongoDB Basics
🏢 Clusters, Databases, Collections, Documents
Cluster: A group of servers hosting MongoDB databases.

Database: Holds collections.

Collection: Like a table in SQL, holds documents.

Document: A JSON/BSON object that stores data (like a row).

✍️ CRUD Operations
Operation	Function
insertOne()	Add a single document
insertMany()	Add multiple documents
find(), findOne()	Retrieve documents
updateOne(), updateMany()	Modify documents
deleteOne(), deleteMany()	Remove documents

🔹 Data Types and Schema
🧬 Flexible Schema
MongoDB doesn’t require all documents to have the same structure.

📂 Embedded Documents
Documents can contain nested data (sub-documents).

json
Copy
Edit
{
  "name": "John",
  "address": { "city": "Delhi", "zip": 110001 }
}
🔤 Case Sensitivity & Quotes
Field names are case-sensitive.

MongoDB uses double quotes for field names in queries.

🔹 Querying MongoDB
📊 Comparison Operators
$eq: Equal to

$gt: Greater than

$lte: Less than or equal to

js
Copy
Edit
db.users.find({ age: { $gt: 18 } })
🔗 Logical Operators
$and, $or, $not, $nor for complex filtering.

🧮 Cursor Methods
.limit(n): Limit results

.skip(n): Skip first n results

.sort(): Sort by field

.count(): Count documents

🔹 Advanced MongoDB
🎯 Projection
Specifies which fields to return:

js
Copy
Edit
db.users.find({}, { name: 1, _id: 0 })
🔍 Element Operators
$exists: Checks if a field exists

$type: Checks data type

🧠 Expressions ($expr)
Allows comparison between fields inside the same document.

🔢 Array Operators
$all: Match all values in array

$elemMatch: Match at least one embedded document in an array

🧩 Indexing
🧷 Indexes
Help speed up read operations (queries).

Type	Use
Default _id	Created automatically
Unique	Prevent duplicate values
Text	Search text in strings

🔧 Commands
createIndex({ name: 1 }): Ascending index

dropIndex(): Removes index

explain(): Shows query performance

📊 Aggregation Framework
Used for advanced data processing like grouping, sorting, filtering.

🔧 Key Stages:
$match: Filter data

$group: Group data

$sort: Sort results

$project: Include/exclude fields

$unwind: Break arrays into separate documents

$addFields: Add calculated fields

$push, $addToSet: Add elements to an array

$limit, $skip: Control result size

$filter, $size: Work with arrays

⚙️ Tools & Setup
MongoDB Server: Local installation to run the database.

MongoDB Compass: GUI tool to interact visually.

MongoDB Atlas: Cloud-based database.

Mongo Shell: Command-line interface to run queries.

🚀 MongoDB with Node.js & Mongoose
🟩 Node.js Driver
Uses MongoClient to connect to the database.

Perform CRUD using async functions.

🧱 Mongoose ODM
ODM = Object Data Modeling.

Create Schemas and Models.

Adds features like validation, middleware, and relationships.

js
Copy
Edit
const mongoose = require('mongoose');
const userSchema = new mongoose.Schema({ name: String, age: Number });
const User = mongoose.model('User', userSchema);
✅ Summary
You now understand the core features and commands in MongoDB, including data modeling, querying, indexing, aggregation, and integrating with Node.js using Mongoose.
