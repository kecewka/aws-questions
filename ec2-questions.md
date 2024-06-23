## 1. What is EC2?
- **Definition:** Amazon Elastic Compute Cloud (EC2) is a web service that provides resizable compute capacity in the cloud. It allows users to run virtual servers (instances) to host applications and perform other computing tasks.

## 2. Types of EC2 Instances
- **General Purpose:** Balanced compute, memory, and networking resources (e.g., T3, M5).
- **Compute Optimized:** High compute performance (e.g., C5).
- **Memory Optimized:** Fast performance for workloads that process large data sets in memory (e.g., R5, X1).
- **Storage Optimized:** High, sequential read and write access to large data sets (e.g., I3, D2).
- **Accelerated Computing:** Hardware accelerators, or GPUs (e.g., P3, G3).

## 3. EC2 Provisioning/Billing Options
- **On-Demand Instances:** Pay for compute capacity by the hour or second.
- **Reserved Instances:** Purchase instances at a significant discount compared to On-Demand pricing.
- **Spot Instances:** Bid for unused capacity at reduced rates.
- **Savings Plans:** Flexible pricing model offering lower prices in exchange for a commitment to a consistent amount of usage.

## 4. Reducing Costs When Purchasing EC2 Instances
- **Use Reserved Instances or Savings Plans** for long-term workloads.
- **Use Spot Instances** for flexible workloads that can tolerate interruptions.
- **Auto Scaling:** Automatically adjusts the number of instances to match demand.
- **Right-sizing:** Select the instance type that best matches your workload needs.

## 5. Regions and Availability Zones (AZs)
- **Regions:** Geographical areas with multiple, isolated locations known as Availability Zones.
- **Availability Zones:** Data centers within a region. Each region has multiple AZs.
- **High Availability:** Deploy instances across multiple AZs to ensure fault tolerance and minimal downtime.

## 6. Keys Created for Each EC2 Instance
- **Key Pair (SSH Key):** Consists of a public key stored by AWS and a private key held by the user to securely connect to the instance.

## 7. EC2 Instances: Stop/Start vs. Reboot
- **Stop/Start:** 
  - Stops billing for instance usage.
  - The instance is moved to a different host on restart.
  - Data on instance store volumes is lost; EBS volumes are preserved.
- **Reboot:**
  - Reboots the instance on the same host.
  - No data loss on EBS volumes or instance store volumes.

## 8. IAM Roles vs. EC2 (VPC) Security Groups
- **IAM Roles:** Provide temporary credentials to access AWS services without embedding credentials in code.
- **Security Groups:** Act as a virtual firewall, controlling inbound and outbound traffic for instances.

## 9. What is AMI? How it Differs from Snapshot or Launch Template?
- **AMI (Amazon Machine Image):** Provides the information required to launch an instance, including the OS, application software, and configurations.
- **Snapshot:** Point-in-time copy of EBS volumes.
- **Launch Template:** Contains configuration information to launch instances (like an AMI but with additional instance settings).

## 10. What is EBS? Types of Volumes Offered by EC2
- **EBS (Elastic Block Store):** Provides block storage for EC2 instances.
- **Volume Types:**
  - General Purpose SSD (gp2, gp3)
  - Provisioned IOPS SSD (io1, io2)
  - Throughput Optimized HDD (st1)
  - Cold HDD (sc1)

## 11. Decreasing the Size of an Existing EBS Volume
- **Not Possible:** You cannot decrease the size of an existing EBS volume. You must create a new, smaller volume and migrate your data.

## 12. Reusing an EBS Volume for Multiple Instances
- **Not Possible:** An EBS volume can be attached to only one instance at a time, except for Multi-Attach volumes (io1/io2) within the same AZ.

## 13. Monitoring EC2 Instances
- **Services/Tools:** 
  - Amazon CloudWatch (metrics, logs, alarms)
  - AWS CloudTrail (logs API calls)
  - EC2 Instance Status Checks

## 14. Horizontal Scalability and Amazon EC2 Auto Scaling
- **Horizontal Scalability:** Adding more instances to handle increasing load.
- **Amazon EC2 Auto Scaling:** Automatically adjusts the number of EC2 instances based on demand to maintain performance and cost-efficiency.

## 15. Load Balancer and Types of Amazon Load Balancers
- **Load Balancer:** Distributes incoming application traffic across multiple targets (instances, containers).
- **Types:**
  - Application Load Balancer (ALB): Operates at the application layer (HTTP/HTTPS).
  - Network Load Balancer (NLB): Operates at the transport layer (TCP/UDP).
  - Classic Load Balancer (CLB): Legacy load balancer, operates at both the application and transport layers.
- **Key Difference:** ALB is ideal for HTTP/HTTPS traffic with advanced routing, NLB is for high-performance TCP/UDP traffic, and CLB supports both but lacks some advanced features.

## 16. Request Routing Algorithm for Application and Network Load Balancers
- **ALB:** Routes requests based on listener rules (path, host-based routing).
- **NLB:** Routes requests based on the TCP/UDP traffic (least connection, round-robin).

## 17. Listener and Listener Rules; Rule Priority and Rule Condition
- **Listener:** Checks for connection requests using the protocol and port you configure.
- **Listener Rules:** Determines how to route requests to targets.
- **Rule Priority:** Determines the order in which rules are evaluated.
- **Rule Condition:** Defines the criteria for routing requests (e.g., URL path, host header).

## 18. What is a Target Group? Using Lambda Behind the Target Group
- **Target Group:** A set of instances or IP addresses that can receive traffic from the load balancer.
- **Lambda Support:** Yes, Lambda functions can be targets for ALBs.

## 19. Installing/Configuring Software on an EC2 Instance
- **Methods:**
  - SSH into the instance and manually install/configure software.
  - Use user data scripts to automate the installation during instance launch.
  - Use AWS Systems Manager for automated management and configuration.

## 20. Getting Metadata such as Current Region/AZ from Within a Running EC2 Instance
- **Method:** Access the instance metadata service at `http://169.254.169.254/latest/meta-data/`

## 21. Key Events in EC2 Instance Lifecycle
- **Events:** Pending, Running, Stopping, Stopped, Shutting Down, Terminated.

## 22. Granting an EC2 Instance Permissions to Access AWS Resources
- **Method:** Attach an IAM role with appropriate permissions to the EC2 instance.
