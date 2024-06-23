## 1. AWS Services Related to Storage Types

- **Block Storage:**
  - **Service:** Amazon Elastic Block Store (EBS)
- **File Storage:**
  - **Service:** Amazon Elastic File System (EFS), Amazon FSx (for Windows File Server and Lustre)
- **Object Storage:**
  - **Service:** Amazon Simple Storage Service (S3)

## 2. Difference Between EBS and EC2 Instance Store

- **Amazon EBS (Elastic Block Store):**
  - **Persistence:** Data is persistent, meaning it remains after stopping or terminating the instance.
  - **Snapshot:** Can create snapshots for backups and replication.
  - **Attachment:** Can be detached and reattached to another instance.
  - **Use Case:** For applications requiring long-term data storage, like databases.

- **EC2 Instance Store:**
  - **Persistence:** Data is ephemeral, meaning it is lost when the instance is stopped or terminated.
  - **Snapshot:** Cannot create snapshots directly.
  - **Attachment:** Cannot be detached or reattached to another instance.
  - **Use Case:** For temporary data that changes frequently, like caches or buffers.

## 3. Service for Shared Folder Across Multiple Instances

- **Service:** Amazon Elastic File System (EFS)

## 4. How to Replicate an EBS Volume

- **Steps:**
  1. Create a snapshot of the EBS volume.
  2. Create a new volume from the snapshot, possibly in another region if needed.

## 5. Exposing Static Pages to the Internet

- **Service:** Amazon S3 (with static website hosting enabled) or Amazon CloudFront (for content delivery network and caching)

## 6. What are Buckets in S3?

- **Definition:** Containers for storing objects (files and their metadata) in Amazon S3.

## 7. What Does S3 Replication Do? What Is It For?

- **Purpose:** Automatically replicates objects from one S3 bucket to another.
- **Use Case:** For data redundancy, compliance, disaster recovery, or closer data access to users.

## 8. Versions in S3 and Deleting Objects When Versioning is Enabled

- **Versions:** S3 can keep multiple versions of the same object, allowing you to track and restore previous versions.
- **Deleting with Versioning Enabled:** Deletes the latest version of the object, and a delete marker is added. Previous versions are retained and can be restored.

## 9. Optimizing Cost of S3 Resources

- **Methods:**
  - Use S3 storage classes (e.g., S3 Standard-IA, S3 One Zone-IA, S3 Glacier) for less frequently accessed data.
  - Enable S3 Lifecycle policies to automatically transition objects to cheaper storage classes or delete them.
  - Analyze storage usage with S3 Storage Lens and use tools like S3 Intelligent-Tiering for automatic cost optimization.

## 10. Nested File Hierarchies in S3

- **Representation:** S3 uses a flat namespace. Nested directories are simulated by using prefixes and delimiters (usually a forward slash `/`).

## 11. What S3 Stores Inside Its Objects

- **Contents:** Data (the actual content of the file) and metadata (information about the file like name, size, last modified date).

## 12. Why S3 is Better Than a Physically Maintained File Server

- **Advantages:**
  - Scalability: Automatically scales to meet your storage needs.
  - Durability: Designed for 99.999999999% (11 9s) durability.
  - Availability: High availability and fault tolerance.
  - Maintenance: No need to manage physical hardware.
  - Security: Strong security and access control features.
  - Cost-Effective: Pay only for what you use, with various storage classes for different use cases.

## 13. Ways to Allow Access to S3 Bucket

- **Methods:**
  - Bucket policies: JSON policies attached directly to the bucket.
  - IAM policies: Permissions granted via AWS Identity and Access Management.
  - Access Control Lists (ACLs): Granting access permissions to individual objects or buckets.
  - Pre-signed URLs: Temporary access URLs to specific objects.
  - AWS Organizations service control policies (SCPs): To centrally manage permissions across multiple AWS accounts.

## 14. Attaching EBS Volume to Multiple Instances Simultaneously

- **Standard EBS Volumes:** Cannot be attached to multiple instances simultaneously.
- **Amazon EBS Multi-Attach (for io1/io2 volumes):** Can be attached to multiple instances within the same Availability Zone, but must be managed at the application level to ensure consistency.

## 15. Use Scenario for Each Amazon FSx File System Type

- **Amazon FSx for Windows File Server:**
  - **Use Case:** Windows-based applications requiring SMB protocol, Active Directory integration, and Windows file system features.
  - **Example:** Enterprise applications like Microsoft SharePoint, SQL Server, and home directories.

- **Amazon FSx for Lustre:**
  - **Use Case:** High-performance computing applications needing fast, scalable storage for big data and machine learning workloads.
  - **Example:** Media processing, financial modeling, and machine learning training.
