### 1. Difference Between IAM Identity and IAM Principal
- IAM Identity:
  - Definition: Represents any entity that can be authenticated in AWS.
  - Examples: Users, groups, roles, and services.
  - Key Points: Identities are entities you create to provide authentication (e.g., AWS IAM users, IAM roles).
- IAM Principal:
  - Definition: Any entity that can make a request to AWS services.
  - Examples: IAM users, IAM roles, federated users, and AWS services.
  - Key Points: Principals include both identities and resources/services that can make requests to AWS.
### 2. Which Type of Request to AWS is Recorded by CloudTrail?
- Type of Requests: AWS CloudTrail records API calls made to AWS services.
  - Examples: Management Console sign-ins and operations. API calls made by SDKs, command-line tools, and other services. Requests made by AWS services on behalf of the user (service events).
### 3. Difference Between Customer Managed IAM Policy and AWS Managed IAM Policy
- Customer Managed IAM Policy:
  - Definition: Policies that you create and manage yourself.
  - Control: Full control over the policy's permissions and can customize as needed.
  - Use Case: When you need specific permissions tailored to your organization's needs.
- AWS Managed IAM Policy:
  - Definition: Predefined policies created and managed by AWS.
  - Control: Limited control; you cannot change the permissions defined by AWS.
  - Use Case: Common permission sets, easy to implement and maintain.
### 4. How Inline Policy Differs from Managed Policy
- Inline Policy:
  - Definition: Policies directly embedded within a single user, group, or role.
  - Attachment: Can only be attached to one entity.
  - Use Case: Specific permissions for a particular user, group, or role.
- Managed Policy:
  - Definition: Policies that are created independently and can be attached to multiple users, groups, or roles.
  - Attachment: Can be reused and attached to multiple entities.
  - Use Case: Common permissions that apply to multiple users, groups, or roles.
### 5. Limits for Inline IAM Policy
- Size Limit:
  - Maximum of 5,120 characters per inline policy.
- Number of Inline Policies:
  - Maximum of 10 inline policies per user, group, or role.
- Overall Limits:
  - These limits can vary and should be checked in the latest AWS documentation.
### 6. Best Practices When Working with Permissions
- Principle of Least Privilege:
  - Grant only the permissions needed to perform a task.
- Use Groups for Permissions:
  - Assign permissions to groups rather than individual users.
- Regular Audits and Reviews:
  - Regularly review permissions and remove unnecessary ones.
- Use AWS Managed Policies:
  - For common use cases to simplify permission management.
- Enable Multi-Factor Authentication (MFA):
  - Add an extra layer of security to user accounts.
### 7. AWS CLI Credentials and Configuration Settings Precedence Order (First 3)
- Command Line Options:
  - Parameters specified directly in the CLI command.
- Environment Variables:
  - AWS environment variables set in the operating system.
- CLI Credentials File:
  - Credentials and configuration settings stored in the .aws/credentials and .aws/config files.
### 8. Allow/Deny Priority Order When Policies are Configured on Different Levels
- Explicit Deny:
  - Takes the highest priority and overrides any allow permissions.
- Explicit Allow:
  - Permissions explicitly granted in policies attached to the principal (user, group, or role).
- Default Deny:
  - Any action not explicitly allowed is implicitly denied by default.
