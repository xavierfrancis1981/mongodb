# What is MongoDB
### MongoDB is a popular NoSQL document-oriented database management system, known for its flexibility, high performance, high availability, and multi-storage engines. Unlike traditional relational databases (RDBMS), MongoDB does not store data in tables and rows but instead uses a document-based structure with BSON (Binary JSON) format

# What are collections and documents?
### A collection is a grouping of MongoDB documents. Documents within a collection can have different fields. A collection is the equivalent of a table in a relational database system.

# MongoDB Architecture
![alt-text](./mongo-arch.png "Architecture")
### MongoDB's architecture consists of several core components that work together to provide efficient data storage, retrieval and processing.
## What are Replica Sets?
### A replica set is a group of mongod instances that maintain the same data set. A replica set contains several data bearing nodes and optionally one arbiter node. Of the data bearing nodes, one and only one member is deemed the primary node, while the other nodes are deemed secondary nodes.
![alt-text](./mongo1.png "Replica Set")
### Replica sets offer high availability, fault tolerance, and improved read capacity through data redundancy. However, they also introduce complexity in setup and maintenance, potential performance bottlenecks with replication lag, and increased storage and resource requirements

## What is Sharding?
### Sharding is a method for distributing data across multiple machines.
### MongoDB uses sharding to support deployments with very large data sets and high throughput operations. Database systems with large data sets or high throughput applications can challenge the capacity of a single server.
### For example, high query rates can exhaust the CPU capacity of the server. Working set sizes larger than the system's RAM stress the I/O capacity of disk drives.
![alt-text](./mongo2.png "Sharding")
### The Advantages of using Sharding include improved performance and scalability, especially for large datasets and high-volume workloads. However, sharding also introduces complexities in application development, query management, and data consistency, potentially increasing maintenance costs
# MongoDB Use Cases
### 1. Customer service applications: MongoDB is used in customer service applications to manage and analyze unstructured data from various sources. Its scalability and flexible schema design enable the creation of responsive and efficient customer service platforms. For example, eBay uses MongoDB to store and manage customer interactions, enhancing their service quality.
### 2. Content management systems: MongoDB is widely used in content management systems (CMS) because it handles various data types and formats. Its JSON-like BSON format allows for easy storage and retrieval of multimedia content, making it a preferred choice for CMS platforms. For example, The New York Times uses MongoDB to manage its vast articles and multimedia content archive.