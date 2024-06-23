### 1. What is Amazon DynamoDB?
1. A relational database service
2. **A NoSQL database service**
3. A file storage service
4. A virtual server service

### 2. Which of the following is NOT a core component of DynamoDB?
1. Table
2. Item
3. **Column**
4. Attribute

### 3. What is the maximum size of a single item in DynamoDB?
1. 100 KB
2. **400 KB**
3. 1 MB
4. 10 MB

### 4. What is a local secondary index (LSI) in DynamoDB?
1. An index with a different partition key and sort key
2. **An index with the same partition key but a different sort key**
3. An index with the same partition key and sort key
4. An index with a different partition key but the same sort key

### 5. Which of the following is NOT a supported data type in DynamoDB?
1. String
2. Number
3. **Date**
4. Boolean

### 6. What is the default read consistency model for DynamoDB?
1. Strongly consistent reads
2. **Eventually consistent reads**
3. Immediate consistent reads
4. None of the above

### 7. What is the primary purpose of DynamoDB Streams?
1. To replicate data across multiple AWS Regions
2. To capture table activity for auditing purposes
3. To automatically scale read and write capacity
4. **To enable real-time processing of table data**

### 8. What is the maximum number of global secondary indexes (GSIs) that can be created per table in DynamoDB?
1. 5
2. 10
3. **20**
4. 50

### 9. How does DynamoDB autoscaling work?
1. By adjusting the number of partitions
2. **By adjusting the provisioned throughput**
3. By adjusting the number of read replicas
4. By adjusting the storage capacity

### 10. In which of the following scenarios would you choose DynamoDB's on-demand capacity mode?
1. Predictable application traffic
2. **Unpredictable application traffic**
3. Gradually ramping up workloads
4. Forecasting capacity requirements

### 11. Which formula is used to calculate the required Read Capacity Units (RCUs) for strongly consistent reads in Amazon DynamoDB provisioned capacity mode?
1. (Number of strongly consistent reads per second * Item size in KB, rounded up) / 2 KB
2. **(Number of strongly consistent reads per second * Item size in KB, rounded up) / 4 KB**
3. (Number of strongly consistent reads per second * Item size in KB, rounded up) / 8 KB
4. (Number of strongly consistent reads per second * Item size in KB, rounded up) / 16 KB

### 12. Which formula is used to calculate the required Write Capacity Units (WCUs) in Amazon DynamoDB provisioned capacity mode?
1. (Number of writes per second * Item size in KB, rounded up) / 0.5 KB
2. **(Number of writes per second * Item size in KB, rounded up) / 1 KB**
3. (Number of writes per second * Item size in KB, rounded up) / 2 KB
4. (Number of writes per second * Item size in KB, rounded up) / 4 KB
