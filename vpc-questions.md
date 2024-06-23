## 1. What Kinds of IP Addresses Does AWS VPC Offer?
- **Public IP:** Assigned to instances that need to communicate with the internet.
- **Private IP:** Assigned to instances for communication within the VPC.
- **Elastic IP:** Static, public IP address that can be associated with any instance.
- **IPv6 Addresses:** Public and private IPv6 addresses can be assigned to instances.

## 2. What Happens to Different IP Address Types When an EC2 Instance is Rebooted, Stopped, Started?
- **Reboot:**
  - Public IP: Retained
  - Private IP: Retained
  - Elastic IP: Retained (if associated)
- **Stop/Start:**
  - Public IP: Released and a new one assigned upon start
  - Private IP: Retained
  - Elastic IP: Retained (if associated)

## 3. Can You Assign Multiple IP Addresses to an Instance?
- **Yes:** You can assign multiple private IP addresses to a single instance, and associate multiple Elastic IPs (one for each private IP) in a VPC.

## 4. How Many Elastic IPs Is It Possible to Create Per Account/Region?
- **Limit:** By default, you can have 5 Elastic IP addresses per AWS account per region. This limit can be increased by requesting a limit increase through AWS Support.

## 5. Difference Between Public and Private Subnet?
- **Public Subnet:**
  - Has a route to the internet gateway.
  - Instances can communicate directly with the internet.
- **Private Subnet:**
  - No direct route to the internet gateway.
  - Instances cannot directly access the internet, typically use a NAT for outbound traffic.

## 6. How Do VPC Subnets Map onto AZs?
- **Mapping:** Each subnet must reside entirely within one Availability Zone (AZ). Subnets are used to segment the VPC into different AZs.

## 7. Difference Between Default and Custom VPC?
- **Default VPC:**
  - Automatically created for each AWS account.
  - Comes with a public subnet in each AZ.
- **Custom VPC:**
  - Manually created by the user.
  - Offers more control over network configuration and segmentation.

## 8. Difference Between NAT Gateways and NAT Instances?
- **NAT Gateway:**
  - Managed service, highly available within an AZ.
  - Scales automatically, simpler to manage.
  - Higher cost than NAT instances.
- **NAT Instance:**
  - Self-managed, must be manually configured for high availability.
  - Requires instance type selection and configuration.
  - Lower cost, more control over configuration.

## 9. Availability of All IPs in a CIDR Block Assigned to a VPC?
- **No:** AWS reserves the first four IP addresses and the last IP address in each subnet's CIDR block.

## 10. When to Use NACL vs. Security Group?
- **NACL (Network ACL):**
  - Use for subnet-level control.
  - Stateless: Return traffic must be explicitly allowed.
- **Security Group (SG):**
  - Use for instance-level control.
  - Stateful: Return traffic is automatically allowed if the request was allowed.

## 11. Stateful vs. Stateless in ACLs and Security Groups?
- **NACL:** Stateless
- **Security Group:** Stateful

## 12. How Does VPC Determine Whether to Deny/Allow a Request When Both ACLs and Security Groups Are Specified?
- **Evaluation:**
  - Both NACLs and Security Groups must allow the traffic. If either denies the request, the traffic is blocked.

## 13. What Does "Local" Target Mean in Terms of an AWS Routing Table?
- **Local Target:** Refers to routing within the VPC, enabling communication between subnets.

## 14. How to Connect Your VPC to the Internet?
- **Method:**
  - Attach an Internet Gateway (IGW) to the VPC.
  - Add a route to the route table that directs traffic to the IGW for internet-bound traffic.

## 15. What is Bastion in Terms of Networking?
- **Definition:** A Bastion host is a special-purpose instance used to access instances in private subnets. It acts as a jump server.

## 16. How Can You Monitor the Network Traffic in VPC?
- **Tools:**
  - VPC Flow Logs: Capture information about IP traffic going to and from network interfaces in the VPC.
  - AWS CloudWatch and CloudTrail for logging and monitoring.

## 17. Can You Peer VPC with a VPC Belonging to Another AWS Account?
- **Yes:** VPC Peering can connect VPCs across different AWS accounts.

## 18. Do You Pay for VPC When Using EC2 Instances?
- **Cost:**
  - VPC itself is free, but there are costs associated with certain features (e.g., NAT gateways, VPC endpoints, VPN connections, and traffic mirroring).
