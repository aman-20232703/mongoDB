# Introduction

## What is MongoDB?
MongoDB is a NoSQL database that stores data in JSON-like documents called BSON (Binary JSON). It's schema-less, meaning each document can have different fields.

## SQL vs NoSQL
Feature	       This&nbsp;&nbsp;&nbsp;is&nbsp;&nbsp;&nbsp;spaced&nbsp;&nbsp;&nbsp;text.      SQL (Relational DB)	              NoSQL (MongoDB)
Structure	            Tables, Rows	Collections,              Documents
Schema	              Fixed	                                  Dynamic
Joins                	Supports complex joins	                Limited joins
                      Scalability	Vertical	                  Horizontal (easier to scale)

## JSON vs BSON
JSON: Human-readable text format.

BSON: Binary format used internally by MongoDB. Supports more data types like Date, ObjectId.

## MongoDB Atlas & Compass
Atlas: MongoDB's cloud-hosted database service.

Compass: GUI tool to visualize, query, and manage MongoDB data.

 ## MongoDB Basics
### Clusters, Databases, Collections, Documents
Cluster: A group of servers hosting MongoDB databases.

Database: Holds collections.

Collection: Like a table in SQL, holds documents.

Document: A JSON/BSON object that stores data (like a row).

## CRUD Operations
Operation              	Function
insertOne()        	Add a single document
insertMany()      	Add multiple documents
find(),             findOne()	Retrieve documents
updateOne(),        updateMany()	Modify documents
deleteOne(),        eleteMany()	Remove documents

## Data Types and Schema
Flexible Schema
MongoDB doesn’t require all documents to have the same structure.

## Embedded Documents
Documents can contain nested data (sub-documents).
 
{
  "name": "John",
  "address": { "city": "Delhi", "zip": 110001 }
}
## Case Sensitivity & Quotes
Field names are case-sensitive.

MongoDB uses double quotes for field names in queries.

## Querying MongoDB
### omparison Operators
$eq: Equal to

$gt: Greater than

$lte: Less than or equal to

db.users.find({ age: { $gt: 18 } })

### Logical Operators
$and, $or, $not, $nor for complex filtering.

###  Cursor Methods
.limit(n): Limit results

.skip(n): Skip first n results

.sort(): Sort by field

.count(): Count documents

### Advanced MongoDB
#### Projection
Specifies which fields to return:

db.users.find({}, { name: 1, _id: 0 })

### Element Operators
$exists: Checks if a field exists

$type: Checks data type

### Expressions ($expr)
Allows comparison between fields inside the same document.

### Array Operators
$all: Match all values in array

$elemMatch: Match at least one embedded document in an array

## Indexing
### Indexes
Help speed up read operations (queries).

Type	Use
Default _id	Created automatically
Unique	Prevent duplicate values
Text	Search text in strings

### Commands
createIndex({ name: 1 }): Ascending index

dropIndex(): Removes index

explain(): Shows query performance

## Aggregation Framework
Used for advanced data processing like grouping, sorting, filtering.

### Key Stages:
<b>$match:</b> Filter data

<b>$group:</b> Group data

<b>$sort: </b>Sort results

<b>$project:</b> Include/exclude fields

<b>$unwind:</b> Break arrays into separate documents

<b>$addFields:</b> Add calculated fields

<b>$push, $addToSet:</b> Add elements to an array

<b>$limit, $skip:</b> Control result size

<b>$filter, $size:</b> Work with arrays

## Tools & Setup
<b>MongoDB Server:</b> Local installation to run the database.

<b>MongoDB Compass:</b> GUI tool to interact visually.

<b>MongoDB Atlas:</b> Cloud-based database.

<b>Mongo Shell:</b> Command-line interface to run queries.

## MongoDB with Node.js & Mongoose
### Node.js Driver
Uses MongoClient to connect to the database.

Perform CRUD using async functions.

## Mongoose ODM
<b>ODM =</b> Object Data Modeling.

Create Schemas and Models.

Adds features like validation, middleware, and relationships.
 
const mongoose = require('mongoose');
const userSchema = new mongoose.Schema({ name: String, age: Number });
const User = mongoose.model('User', userSchema);
 
