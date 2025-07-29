# MongoDB
MongoDB is a popular NoSQL document-oriented database management system, known for its flexibility, high performance, high availability, and multi-storage engines. Unlike traditional relational databases (RDBMS), MongoDB does not store data in tables and rows but instead uses a document-based structure with BSON (Binary JSON) format

# collections and documents in MongoDB
A collection is a grouping of MongoDB documents. Documents within a collection can have different fields. A collection is the equivalent of a table in a relational database system.

# MongoDB Architecture
![alt-text](./mongo-arch.png "Architecture")
MongoDB's architecture consists of several core components that work together to provide efficient data storage, retrieval and processing.
## Replica Sets
A replica set is a group of mongod instances that maintain the same data set. A replica set contains several data bearing nodes and optionally one arbiter node. Of the data bearing nodes, one and only one member is deemed the primary node, while the other nodes are deemed secondary nodes.
![alt-text](./mongo1.png "Replica Set")
Replica sets offer high availability, fault tolerance, and improved read capacity through data redundancy. However, they also introduce complexity in setup and maintenance, potential performance bottlenecks with replication lag, and increased storage and resource requirements

## Sharding
Sharding is a method for distributing data across multiple machines.
MongoDB uses sharding to support deployments with very large data sets and high throughput operations. Database systems with large data sets or high throughput applications can challenge the capacity of a single server.
For example, high query rates can exhaust the CPU capacity of the server. Working set sizes larger than the system's RAM stress the I/O capacity of disk drives.
![alt-text](./mongo2.png "Sharding")
The Advantages of using Sharding include improved performance and scalability, especially for large datasets and high-volume workloads. However, sharding also introduces complexities in application development, query management, and data consistency, potentially increasing maintenance costs
# MongoDB Use Cases
1. Customer service applications: MongoDB is used in customer service applications to manage and analyze unstructured data from various sources. Its scalability and flexible schema design enable the creation of responsive and efficient customer service platforms. For example, eBay uses MongoDB to store and manage customer interactions, enhancing their service quality.
2. Content management systems: MongoDB is widely used in content management systems (CMS) because it handles various data types and formats. Its JSON-like BSON format allows for easy storage and retrieval of multimedia content, making it a preferred choice for CMS platforms. For example, The New York Times uses MongoDB to manage its vast articles and multimedia content archive.
# Notes
# MongoDB syntaxes
#### Switches the current database context to spartadb
``` 
use spartadb
``` 
#### explicitly create a new collection named "academy" in the current database.

``` 
db.createCollection("academy")
```
#### inserts a single document into the academy collection in the current database.
```
db.academy.insertOne({name:"New document"})
```
#### inserts multiple documents into the academy collection in one operation.
```
db.academy.insertMany([{"course":"Data Engineering", "length":10}, {"course":"Data Analysis", "length":8}])
```
```
db.academy.insertMany([{"first_name":"Xavier"}, {"sur_name":"Francis"}, {"stream":"data_engineering"}, {"course_id":504}, {"Trainer":"Luke"}])
```
# Data Modelling in MongoDB
There are two kind of main ways  we can do data modeling in MongoDB in particular, embedding and Referencing
## Embedding
Embedding is a fairly simple concept in MongoDB.It involves placing sub-documents inside a larger document — essentially, documents within documents. This technique is known as embedding related documents.Embedding is especially suitable for one-to-one and one-to-many relationships. While this might not always be the perfect approach for every use case, it's often the preferred method when normalization isn’t necessary.For example, let’s consider a training course. You can embed related information, such as modules or lessons, directly inside the course document. We’ll look at that example in a moment.
![alt-text](./embedding.png "Embedding")
### An example of embedding
```
db.academy.insertOne({
  name:"David",
  course:"Data Engineering",
  trainer:{name:"Luke", expertise:"Data"}
})
```

## Referencing
Referencing is another way to establish relationships between documents in MongoDB.This approach is more suitable for normalized data because it uses some kind of ID to connect documents.Unlike embedding, where you store a document inside another document (resulting in just one document), referencing involves keeping documents separate and linking them by reference. For example, you might reference a user document in a contact document or an access document.Referencing helps avoid data duplication and reduces redundancy, which is useful for maintaining consistency. However, it comes with a trade-off: lower read performance, since the database may need to perform multiple queries to fetch related data.That said, if you're dealing with many-to-many relationships, referencing is usually the only practical solution.
![alt-text](./referencing.png "Referencing") 
#### explicitly create a new collection called "students" in the current database.
```
db.createCollection("students")
```
#### command that inserts a single document into the students collection.
```
db.students.insertOne(
  {
    name:"Mr S. Global",
    year: NumberInt(2020),
    score: 88.2,
    course: "Data",
    address: {
      city: "Birmingham",
    }
  }
)
```
#### list all collections in the currently selected database.
```
show collections
```
#### return an array of all collection names in the current database.
```
db.getCollectionNames()
```
#### query that retrieves all documents from the students collection.
```
db.students.find({})
```
```
db.academy.find({})
```

 
