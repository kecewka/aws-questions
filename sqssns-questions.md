## 1. What is a Message Queue?
- **Definition:** A message queue is a communication method for transferring messages between systems or components in a decoupled way. Messages are stored in a queue until they are processed by the receiving system.

## 2. When to Use SQS and When to Use SNS?
- **SQS (Simple Queue Service):**
  - Use when you need to decouple and scale microservices, distributed systems, or serverless applications.
  - Ideal for scenarios where messages need to be stored temporarily and processed asynchronously by one or more consumers.

- **SNS (Simple Notification Service):**
  - Use when you need to send notifications to multiple subscribers or endpoints.
  - Ideal for scenarios where you need to publish messages to many recipients, such as email, SMS, or other applications.

## 3. Scaling an Auto Scaling Group Using Metrics Such as SQS Queue Depth or Number of SNS Messages
- **Yes:** You can use CloudWatch metrics like SQS queue depth to trigger Auto Scaling actions. Create a CloudWatch alarm based on the desired metric and configure it to scale your Auto Scaling Group.

## 4. What is SQS Pricing?
- **Components:**
  - **Standard Queues:**
    - **Requests:** Charges are based on the number of requests (Send, Receive, Delete).
    - **Data Transfer:** Charges may apply for data transferred out of SQS.

  - **FIFO Queues:**
    - **Requests:** Higher per-request charge compared to standard queues.
    - **Additional Charges:** For message deduplication and sequencing.

  - **Free Tier:** 1 million requests per month are free.

## 5. Collecting Notifications from All AWS Regions Using SNS and Forwarding to External System
- **Design Solution:**
  - **Step 1:** Create an SNS topic in each AWS region where notifications are generated.
  - **Step 2:** Configure the SNS topics to publish messages to an SQS queue in a centralized region.
  - **Step 3:** Use an SQS queue in the centralized region to collect messages from all SNS topics.
  - **Step 4:** Set up an AWS Lambda function or an EC2 instance to poll the SQS queue and forward messages to the external system.

## 6. What is FIFO Queue?
- **Definition:** FIFO (First-In-First-Out) queue is a type of SQS queue that ensures messages are processed in the exact order they are sent and are delivered only once.
- **Use Case:** Ideal for use cases where the order of operations and exactly-once processing are critical, such as financial transactions or inventory management.
