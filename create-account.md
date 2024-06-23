## 1. Name "Six Pillars of AWS" and briefly describe them.
Operational Excellence, Security, Reliability, Performance Efficiency, Cost Optimization, and Sustainability.
  - Operational Excellence:
    - Running and monitoring systems to deliver business value and continually improve processes. Doing things in the best way possible.
    - Key points: Automate routine tasks. Use best practices for managing and operating workloads.
    - Example: Automating tasks to save time and avoid mistakes. Set up automated backups and monitoring alerts for app.
  - Security:
    - Protecting data, systems, and assets to take advantage of cloud technologies.
    - Key points: Implement strong identity and access management. Protect data in transit and at rest.
    - Example: Use AWS Identity and Access Management (IAM) to control who can access your resources.
  - Reliability:
    - Ensuring a workload performs its intended function correctly and consistently. Making sure things work when you need them.
    - Key points: Recover quickly from failures. Scale resources to meet demand. 
    - Example: Use AWS Auto Scaling to automatically add or remove servers based on traffic.
  - Performance Efficiency:
    - Using resources efficiently to meet system requirements and maintain efficiency as demand changes. Using resources wisely to do tasks faster.
    - Key points: Select the right resource types and sizes. Monitor performance and make improvements.
    - Example: Use AWS CloudWatch to track performance metrics and optimize resource use.
  - Cost Optimization:
    - Managing costs to avoid unnecessary expenses. Spending money smartly.
    - Key points: Use cost-effective resources. Scale to meet needs without overspending.
    - Example: Use AWS Cost Explorer to analyze spending patterns and identify savings opportunities.
  - Sustainability:
    - Minimizing the environmental impact of your AWS resources.
    - Key points: Use energy-efficient resources. Optimize workloads to reduce waste.
    - Example: Use serverless computing with AWS Lambda to only use resources when needed, reducing energy consumption.
    
## 2. Why we don’t use root user and create another one instead?
- Why: The root user has unrestricted access to your AWS account and resources, making it highly risky if compromised.
- Key points: Root user is like an all-access master key. Creating separate users with limited permissions reduces risk.
- Example: Create IAM users with specific permissions for different tasks (like managing databases or deploying code). It's like having a master key to a building; if someone steals it, they can access everything. Creating another user with fewer permissions is safer.
## 3. How budget reached notifications work?
- How it works: You set a spending limit, and AWS sends you a message when you get close to or exceed that limit.
- Key points: Set budget limits for your AWS spending. Receive alerts via email or SMS when you're close to or exceed your budget.
- Example: Set a monthly budget of $100 for your AWS resources and get notified if you reach 80% or 100% of that budget. Like your phone telling you when you've used up most of your data for the month.
## 4. Provide an example where tag properly used.
- Example: Tagging resources in AWS to organize and manage them.
- Usage: Tagging all servers for a project with "Project: Alpha" to easily find and manage them later.
- Tag: {"Key": "Project", "Value": "Alpha"}
