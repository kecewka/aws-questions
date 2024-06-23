## 1. What is Amazon DynamoDB?
- **Definition:** Amazon DynamoDB is a fully managed NoSQL database service provided by AWS that offers fast and predictable performance with seamless scalability.

## 2. Common Use Cases for DynamoDB
- **Use Cases:**
  - Web and mobile applications
  - Real-time bidding platforms
  - Gaming leaderboards
  - IoT applications
  - Content and session storage
  - Data caching and event logging

## 3. Key Differences Between DynamoDB and a Traditional RDBMS
- **DynamoDB:**
  - Schema-less
  - NoSQL database
  - Horizontal scaling
  - Partition-based data distribution
  - Primary keys and secondary indexes for querying

- **Traditional RDBMS:**
  - Fixed schema
  - Relational database
  - Vertical scaling
  - Table-based data storage
  - Complex joins and transactions

## 4. Core Components of DynamoDB
- **Core Components:**
  - Tables: Collections of items
  - Items: Individual records (rows)
  - Attributes: Data fields (columns)
  - Primary Keys: Unique identifier for items

## 5. What is a Primary Key in DynamoDB, and What are the Two Types of Primary Keys?
- **Primary Key:** A unique identifier for each item in a table.
- **Types:**
  - **Partition Key:** A single attribute that uniquely identifies an item.
  - **Composite Key (Partition Key + Sort Key):** A combination of two attributes where the partition key is used for partitioning, and the sort key allows for range queries.

## 6. Different Data Types Supported by DynamoDB
- **Data Types:**
  - **Scalar Types:** String, Number, Binary, Boolean, Null
  - **Document Types:** List, Map
  - **Set Types:** String Set, Number Set, Binary Set

## 7. How Does DynamoDB Handle Data Partitioning?
- **Partitioning:** DynamoDB automatically partitions data based on the partition key. Each partition can store up to 10 GB of data and handle a certain amount of read and write throughput.

## 8. Purpose of Secondary Indexes in DynamoDB, and What are the Two Types?
- **Purpose:** Allow additional access patterns and queries without affecting the performance of the primary table.
- **Types:**
  - **Global Secondary Index (GSI):** Can have a different partition key and sort key from the primary table.
  - **Local Secondary Index (LSI):** Has the same partition key as the primary table but a different sort key.

## 9. Two Read Consistency Options Available in DynamoDB
- **Options:**
  - **Eventually Consistent Reads:** Provides the highest read throughput but might not reflect the most recent write.
  - **Strongly Consistent Reads:** Ensures that the read returns the most recent write but at the cost of lower throughput.

## 10. How Does DynamoDB Handle Backup and Restore?
- **Backup and Restore:**
  - **On-Demand Backup:** Create backups at any time without affecting performance.
  - **Point-in-Time Recovery (PITR):** Restore data to any point in the last 35 days.

## 11. Purpose of Auto Scaling in DynamoDB
- **Purpose:** Automatically adjusts read and write throughput capacity based on the traffic patterns to ensure application performance while optimizing costs.

## 12. Two Pricing Options Available for DynamoDB
- **Options:**
  - **On-Demand Capacity Mode:** Pay for read and write requests as you use them.
  - **Provisioned Capacity Mode:** Specify the read and write capacity units you expect to need.

## 13. Factors to Consider When Choosing Between On-Demand and Provisioned Capacity Modes
- **Factors:**
  - **On-Demand:**
    - Variable or unpredictable traffic
    - No upfront capacity planning
    - Pay-per-request pricing model

  - **Provisioned:**
    - Predictable application traffic
    - Ability to manually adjust capacity
    - Potential cost savings with Reserved Capacity

## 14. Best Practices When Working with DynamoDB
- **Best Practices:**
  - Use primary keys and secondary indexes effectively.
  - Optimize partition keys for uniform data distribution.
  - Use projection expressions to return only necessary attributes.
  - Implement error handling and retries with exponential backoff.
  - Monitor performance using Amazon CloudWatch.

## 15. Optimizing Costs and Performance of DynamoDB Workloads
- **Optimizations:**
  - Choose the appropriate capacity mode (on-demand vs. provisioned).
  - Use auto scaling to adjust capacity based on demand.
  - Employ data compression techniques.
  - Use Global Tables for multi-region replication.
  - Optimize query patterns to minimize read and write costs.
  - Leverage caching solutions like Amazon DynamoDB Accelerator (DAX) for read-heavy workloads.
