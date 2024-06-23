## 1. What is the Biggest Benefit of AWS Lambda?
- **Benefit:** Serverless computing, which means you don't need to manage or provision servers. AWS Lambda automatically scales your application by running code in response to triggers, charging you only for the compute time you consume.

## 2. Ways of Triggering a Lambda
- **Triggers:**
  - HTTP requests via Amazon API Gateway
  - Changes in data in an Amazon S3 bucket
  - Updates to a DynamoDB table
  - Messages from an Amazon SNS topic or Amazon SQS queue
  - Scheduled events via Amazon CloudWatch Events or EventBridge
  - Stream-based events from Amazon Kinesis or DynamoDB Streams
  - AWS Step Functions state changes
  - AWS CloudFormation and CloudTrail events
  - Custom applications or other AWS services

## 3. What is the Contract of Lambda Function?
- **Contract:** The function must follow a specific input/output pattern:
  - **Input:** Event data passed as a JSON object.
  - **Output:** The function must return a JSON object that contains the result of the computation.

## 4. What is Lambda Pricing?
- **Pricing:**
  - **Compute Time:** Charged based on the number of requests and the duration of the code execution.
  - **Requests:** The first 1 million requests per month are free. After that, $0.20 per 1 million requests.
  - **Duration:** Measured in milliseconds from the time your code begins executing until it returns or otherwise terminates, rounded up to the nearest 1ms. Pricing is $0.00001667 for every GB-second used.

## 5. Reasonable Code Libraries/Frameworks to Use in Lambda
- **Frameworks/Libraries:**
  - Lightweight frameworks and libraries to minimize cold start times.
  - AWS SDKs for integrating with AWS services.
  - Frameworks like Serverless Framework, AWS SAM, or Zappa for managing and deploying Lambda functions.
  - Commonly used libraries in supported programming languages (e.g., NumPy for Python, AWS SDK for JavaScript).

## 6. How Lambda Instances Are Reused? How to Prepare the Lambda Code for That?
- **Reusability:** AWS Lambda may reuse execution environments to improve performance, particularly for warm starts.
- **Preparation:**
  - Avoid using global state that might persist across invocations.
  - Initialize connections and reusable resources (e.g., database connections) outside the main handler function to take advantage of warm starts.
  - Clean up temporary data within the handler function.

## 7. Programming Languages Supported by Lambda
- **Languages:**
  - Node.js
  - Python
  - Ruby
  - Java
  - Go
  - .NET Core (C#)
  - PowerShell
  - Custom Runtime via AWS Lambda Layers

## 8. Difference Between Synchronous and Asynchronous Lambda Invocations
- **Synchronous Invocation:** The caller waits for the function to process the event and return a response. Errors are returned directly to the caller.
- **Asynchronous Invocation:** The caller places the event on an internal queue and immediately proceeds. Lambda processes the event and handles retries and errors.

## 9. What is Lambda Concurrency?
- **Concurrency:** The number of instances of your function that can be executed simultaneously. AWS Lambda scales up the number of instances to handle increased load.

## 10. Kinds of Lambda Concurrency Allocations
- **Allocations:**
  - **Unreserved Concurrency:** The default concurrency limit applied to all functions within an account.
  - **Reserved Concurrency:** A limit that you set to guarantee a specific number of concurrent instances for a particular function.
  - **Provisioned Concurrency:** Ensures that a specific number of function instances are initialized and ready to respond to invocations.

## 11. AWS Resources Lambda Can Access and How
- **Access:** Lambda can access other AWS resources via:
  - **IAM Roles:** Assigning an IAM role to the Lambda function with necessary permissions.
  - **Environment Variables:** Storing sensitive data and configuration.
  - **VPC Configuration:** Allowing Lambda to access resources within a VPC by configuring it with VPC settings.

## 12. Advantages of API Gateway Endpoints Over Traditional Web Applications
- **Advantages:**
  - Fully managed service with automatic scaling.
  - Integrated with AWS Lambda for serverless backends.
  - Provides features like request validation, throttling, caching, and security (e.g., AWS WAF).
  - Supports various protocols and endpoint types (REST, WebSocket).
  - Simplifies deployment and management of APIs.

## 13. Typical API Gateway Use Cases and Use Case for Combining API GW with Lambda
- **Use Cases:**
  - Creating RESTful APIs for web and mobile applications.
  - Handling real-time data and WebSocket APIs for two-way communication.
  - Integrating with backend services for microservices architectures.

- **Combining with Lambda:** Ideal for creating scalable, cost-efficient serverless applications where API Gateway handles the request routing and Lambda executes the backend logic.

## 14. Use Case for Combining API GW with Lambda
- **Use Case:** Building a serverless web application where API Gateway serves as the HTTP interface and Lambda processes the business logic. This combination offers scalability, reduced operational overhead, and cost savings.

## 15. What is API Gateway Pricing?
- **Pricing:**
  - **REST API:**
    - **Requests:** Charged per million requests (e.g., $3.50 per million requests for the first 333 million).
    - **Data Transfer:** Charges for data transferred out of API Gateway.
    - **Additional Features:** Charges for features like caching, custom domain names, and data transfer.

  - **WebSocket API:**
    - **Messages:** Charged per million messages.
    - **Connection Minutes:** Charged per million connection minutes.

  - **HTTP API:**
    - Generally lower cost compared to REST API, with pricing based on the number of requests and data transfer.

  - **Free Tier:** Offers a certain number of free requests and data transfer per month.
