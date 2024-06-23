## 1. Difference Between Relational, NoSQL, and In-Memory Databases
- **Relational Databases:**
  - **Structure:** Tables with rows and columns.
  - **Schema:** Fixed schema.
  - **Examples:** MySQL, PostgreSQL, Oracle.
  - **Use Case:** Structured data with relationships, transactional consistency.

- **NoSQL Databases:**
  - **Structure:** Varies (documents, key-value pairs, wide-columns, graphs).
  - **Schema:** Flexible schema.
  - **Examples:** DynamoDB, MongoDB, Cassandra.
  - **Use Case:** Unstructured or semi-structured data, scalability.

- **In-Memory Databases:**
  - **Structure:** Data stored in memory for fast access.
  - **Schema:** Can be relational or NoSQL.
  - **Examples:** Redis, Memcached.
  - **Use Case:** Caching, real-time analytics, fast data access.

## 2. Redis or Memcached for Storing Simple Data (String/Integer) in Cache
- **Use:** Both Redis and Memcached can be used, but Redis offers more features and data structures, making it more versatile.

## 3. Getting the Latest Data from DynamoDB
- **Type of Read:** Use a **strongly consistent read** to ensure you get the latest data.

## 4. Making DynamoDB Highly Available
- **How:** Enable **DynamoDB Global Tables** to automatically replicate your tables across multiple AWS regions.

## 5. Backing Up Database Services
- **Methods:**
  - Automated backups (RDS, DynamoDB)
  - Manual snapshots
  - AWS Backup service for centralized management

## 6. What is RDS? What Engines Does It Support?
- **RDS (Relational Database Service):** Managed relational database service.
- **Supported Engines:** Amazon Aurora, MySQL, MariaDB, PostgreSQL, Oracle, Microsoft SQL Server.

## 7. What is RDS Pricing?
- **Components:** Includes instance hours, storage, I/O requests, backup storage, data transfer.
- **Pricing Models:** On-demand, Reserved Instances, Multi-AZ deployments.

## 8. Making RDS Instance Highly Available
- **How:** Enable **Multi-AZ Deployment** to automatically replicate data to a standby instance in a different Availability Zone.

## 9. What is a Read Replica in RDS and How It Works?
- **Definition:** A copy of the primary database that is asynchronously updated.
- **Use Case:** Improves read scalability, offloads read traffic from the primary database.

## 10. RDS Operational Practices
- **Maintenance:** Regular patching and updates.
- **Monitoring:** Use Amazon CloudWatch, Enhanced Monitoring, and RDS Performance Insights.
- **Backup:** Automated backups and manual snapshots.

## 11. RDS Capacity Planning Best Practices
- **Best Practices:**
  - Monitor performance metrics and adjust instance size accordingly.
  - Use auto-scaling for storage.
  - Analyze workload patterns and provision resources to handle peak loads.

## 12. RDS Testing and Profiling Best Practices
- **Best Practices:**
  - Perform load testing and performance benchmarking.
  - Use Amazon RDS Performance Insights for detailed analysis.
  - Test failover mechanisms for Multi-AZ deployments.

## 13. Advantages of RDS Over Manually Managed Databases
- **Advantages:**
  - Automated backups and patching.
  - High availability with Multi-AZ.
  - Scalability and read replicas.
  - Enhanced security features.
  - Simplified management and maintenance.

## 14. Difference Between Multi-AZ Deployment and Read Replicas in RDS
- **Multi-AZ Deployment:**
  - For high availability and automatic failover.
  - Synchronous replication to standby instance.
  - Used for disaster recovery.

- **Read Replicas:**
  - For read scalability.
  - Asynchronous replication.
  - Used to offload read traffic from the primary database.

## 15. Security Features Provided by RDS
- **Features:**
  - Encryption at rest and in transit.
  - Network isolation using VPC.
  - IAM integration for access control.
  - Automated backups and snapshots.
  - Multi-AZ for disaster recovery.

## 16. What is AWS Aurora?
- **Aurora:** A MySQL- and PostgreSQL-compatible relational database engine designed for cloud scalability and high performance.

## 17. Making a Snapshot in RDS at a Specific Time
- **How:** Use the RDS Console or AWS CLI to create manual snapshots at a specific time, or schedule snapshots using AWS Lambda and CloudWatch Events.
