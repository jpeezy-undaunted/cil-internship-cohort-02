# The following are detailed different kinds of database and their use cases summarized.

## Relational Database
**Prons**
- Organize data into tables with columns, each with a specified name and datatype.
- Rows are identified with a unique attribute, or grouping of attributes, called a primary key (typically a single column, called a field).
- Relationships between tables are defined through foreign keys which reference primary keys.
- Strict schema (data model) enforcement.
- Data accessed via Structured Query Language (SQL).
- ACID compliance (Atomicity, Consistency, Isolation, and Durability).
- Extra features like Triggers & Stored Procedures.
**Cons**
- SQL databases cannot handle unstructured or semi-structured data, their tables don’t necessarily map to objects, they require complicated ETL (Extract, Transform, Load) and maintenance, have row locking, and pricing for some products (Oracle, SAP) can be expensive.
**Use Case**
- ACID compliance, Datawarehouse, OLAP, OLTP, structured data analysis.
- Examples includes Oracle, MySQL, SQL, DB2 etc.

### Key-Value Store
**Pros**
- Simple, basic, & Schema-less (not as canonical as an RDMS).
- Provides basic functionality for retrieving arbitrary data via a specific key.
- Values can be anything: single values, arrays, objects, files, etc.
- Database does not evaluate the data it is storing.
- Data structure can be referred to as a dictionary or hash table.
**Cons**
- Key value stores provide fast, low-complexity access to data, are flexible, and can scale quickly and cheaply.
- They have extremely limited functionality, cannot handle complex structures or query or search by anything other than key, do not scale well as data models grow, and they require more programming overhead for complex implementations.
**Use Case**
- Embedded systems, URL shorteners, configuration data, application variables and flags for web applications, state information, and data represented by a dictionary or hash.
- Examnples are MongoDB, Redis, DynamoDB and Cosmos DB.

#### Document Stores
**Pros**
- Document formats are JSON, BSON, or XML documents.
- Schema-less, no data structure enforcement (documents can be different).
- Data accessed and modified via NoSQL (or proprietary language).
- Well-suited for unstructured and semi-structured data.
- Seen as easier for development.
- Flexibility and scalability, Schema-less, fast writes, ideal for semi-structured and unstructured data, and developers do not need to know data structure ahead of time / it can change overtime without downtime.
**Cons**
- Not ACID compliant (DynamoDB IS ACID compliant but this is an exception), limited to querying within a document, relationships/cross references are not enforced, slow searching, cannot join documents/collections in a single query, lack of database enforcement requires developer discipline and vigilance for application-level enforcement, and they typically result in data duplication.
**Use cases**
- Unstructured or semi-structured data, content management, rapid prototyping, and collecting of high traffic data.

##### Graph Database
**Pros**
- Based on mathematical graph theory.
- Represent data as a network of related nodes, edges, and properties.
- Database stores data items within nodes and relationships in edges that connect nodes.
- Nodes are connected by relationships and grouped according to labels
- Facilitate data visualizations and graph analytics
- Each node contains free-form data.
- They have advanced features for relationship querying, traversing, and tracking, are optimized for querying related data, and they avoid row locking.
**Cons**
- Difficult to understand and use, high overhead for simple use cases, lack of standardization, poor performance of aggregate queries, and devs typically need to learn a custom query language.
**Use case**
- Great for analysis of heterogeneous data points, fraud prevention, advanced enterprise operations, social networking, payment systems, and GeoSpatial routing/visualization.
- Examples are Neo4j, OrientDB, and TitanDB which are ideal for when relationships or connections are top priority.

###### Search Engines
**Pros**
- Built for non-relational, document-based data.
- Arranged and optimized for storage and rapid retrieval of data.
- Indexes data across a variety of sources including file systems, intranets, document -Management systems, e-mail, and databases
- Focused on optimized searching, highly scalable and Schema-less, and they have advanced search options like full text search, suggestions, and complex search operations.
**Cons**
- They are expensive, have low durability and poor security, have no transaction support, are not efficient for writing and retrieving data outside of searching, and are difficult to manage.
**Use case**
- Search engines are great when search results are top priority, logging, product catalogues, and blogs.
- Examples are Elasticsearch, Splunk and Apache Solr.

###### Time Series Database
**Pros**
- Focused on datasets that change over time.
- Heavily write oriented.
- Designed to handle constant streams of data.
- Typically append-only (no modification after ingestion).
- Rollup/aggregation/down sampling features to lower archive data footprint.
- Time series databases are designed for dealing with linear data over time, can handle high ingestion rates, have built-in features specifically for dealing with time-based data, a schema optimized for time-series arrays, and batch delete features.
**Cons**
- Time series databases only deal with time-series data, do not support full SQL, their read speed suffers compared to writes, they have no transaction capability and are append-only (not optimized for updates).
**Use case**
- Managing infrastructure, IoT sensor collection, and log monitoring and alerting.
- Examples includes InfluxDB, Kdb+, and Prometheus.