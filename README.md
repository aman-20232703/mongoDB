# Introduction

## What is MongoDB?
MongoDB is a NoSQL database that stores data in JSON-like documents called BSON (Binary JSON). It's schema-less, meaning each document can have different fields.

## SQL vs NoSQL
<b>Feature</b>	 &nbsp;&nbsp;&nbsp;&nbsp;     <b>SQL (Relational DB)</b>	        &nbsp;&nbsp;&nbsp;&nbsp;        <b>NoSQL (MongoDB)</b>

Structure	        &nbsp;&nbsp;&nbsp;&nbsp;     Tables, Rows	Collections,           &nbsp;&nbsp;&nbsp;&nbsp;        Documents

Schema	          &nbsp;&nbsp;&nbsp;&nbsp;      Fixed	                             &nbsp;&nbsp;&nbsp;&nbsp;         Dynamic

Joins             &nbsp;&nbsp;&nbsp;&nbsp;      Supports complex joins	          &nbsp;&nbsp;&nbsp;&nbsp;          Limited joins

Scalability       &nbsp;&nbsp;&nbsp;&nbsp;      Scalability	Vertical	              &nbsp;&nbsp;&nbsp;&nbsp;         Horizontal (easier to scale)

## JSON vs BSON
JSON: Human-readable text format.

BSON: Binary format used internally by MongoDB. Supports more data types like Date, ObjectId.

## MongoDB Atlas & Compass
Atlas: MongoDB's cloud-hosted database service.

Compass: GUI tool to visualize, query, and manage MongoDB data.

 ## MongoDB Basics
### Clusters, Databases, Collections, Documents
<b>Cluster:</b> A group of servers hosting MongoDB databases.

<b>Database:</b> Holds collections.

<b>Collection:</b> Like a table in SQL, holds documents.

<b>Document:</b> A JSON/BSON object that stores data (like a row).

## CRUD Operations
<b>Operation </b>             <b>	Function</b>

<b>insertOne() </b>       	Add a single document

<b>insertMany() </b>     	Add multiple documents

<b>find(),</b>           findOne()	Retrieve documents

<b>updateOne(),</b>        updateMany()	Modify documents

<b>deleteOne(),</b>        eleteMany()	Remove documents

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
<b>.limit(n): </b> Limit results

<b>.skip(n):</b> Skip first n results

<b>.sort():</b> Sort by field

<b>.count():</b> Count documents

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
<b>$all:</b> Match all values in array

<b>$elemMatch:</b> Match at least one embedded document in an array

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
 
