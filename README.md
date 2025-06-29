# MongoDB Data Analysis
### Autor: 
Arnau Muñoz Barrera 

MongoDB Data Analysis and Query performance review.

### Prerequisites
- An IDE like IntelliJ IDEA, Visual Studio Code.

# Datasets analyzed
Inspections & Restaurants -> './datasets/'

# Objectives
#### In this project, I aimed to learn the fundamental technologies for developing data-driven applications using MongoDB, including schema design, data validation, aggregation pipelines, and performance optimization techniques

# Features implemented

• Database schema design and relationship analysis
Analyzed the structure of the datasets to determine the relationship between restaurants and inspections, identifying it as a One-to-Millions relationship and justifying the use of embedded documents for performance optimization.

• Schema validation for data integrity
Created validation schemas for both restaurants and inspections collections, checking required fields and data types to ensure data consistency and integrity.

• Restaurant filtering by type of food
Implemented queries to retrieve restaurants based on their cuisine type (e.g., "Chinese") using field-based filtering.

• Violation-based inspection search
Developed queries to list inspections that include violations, ordered by inspection date using regex filtering and sorting mechanisms.

• Rating-based restaurant filtering
Enabled the retrieval of restaurants with ratings higher than a specified threshold (e.g., >4), using MongoDB comparison operators.

• Aggregation: average rating by cuisine type
Grouped restaurants by type of food and calculated the average rating using the $avg aggregation stage.

• Aggregation: inspection result distribution
Counted the number of inspections per result type and calculated their percentage representation using a multi-stage aggregation pipeline.

• Join restaurants with inspections using $lookup
Linked inspection documents with their corresponding restaurant data for enriched result sets, simulating a relational join.

• Index creation for performance optimization
Identified high-frequency query patterns and created indexes to speed up access. Used explain() to compare query plans before and after indexing.

• Sharding strategy design
Proposed a sharding strategy based on high-cardinality fields like inspection date and restaurant postal code to ensure scalable horizontal partitioning.

• Replica set for high availability
Designed a replica set architecture with three secondary nodes and an arbiter to handle failover and maintain data availability.

• Bottleneck analysis and solutions
Identified potential performance bottlenecks such as read-heavy queries, write contention, and replication lag. Proposed solutions including index usage, sharding, and appropriate read/write concern configurations.

• Code modularity and clarity
Ensured that query logic, validation schemas, and performance tests were modularized and clearly documented for maintainability and readability.

• Focus on performance and scalability
The entire system is designed with future scalability in mind, considering large-scale datasets and high-concurrency environments.

### Setup

**Clone the repository**:
    ```sh
    git clone <repository-url>
    cd <repository-directory>
    ```

**Import datasets & execute validation scripts**:
<br/>
```mongoimport --db ats --collection restaurants --file restaurants.json```
<br/>
   ```mongoimport --db ats --collection inspections --file inspections.json```
<br/>
   ```mongo < scripts/validacio_restaurants.js```
<br/>
   ```mongo < scripts/validacio_inspections.js```

**Execute queries**:
<br/>
```mongo < scripts/query.js```
<br/>
```mongo < scripts/aggregation.js```
<br/>
```mongo < scripts/explain_index.js```
