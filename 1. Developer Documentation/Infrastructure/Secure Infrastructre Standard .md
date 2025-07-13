# AWS Security Controls Map for ISO 27001, SOC 2 and  AWS Best Practices Frameworks
<b> This list is limited just to AWS IAM and not IAM audit controls across the company. 

## Introduction
This document provides a detailed mapping of AWS security best practices to the control requirements of the ISO/IEC 27001:2022 standard and the AICPA's SOC 2 Trust Services Criteria. The controls are organized by AWS service and include a severity rating to provide a clear, actionable guide for architects, engineers, and compliance professionals. This would be posted on an internal site with a list of every AWS resource possible so developers have a guide for what is expected of every resource. Of course, this is a sample but I would provide the extensive list once hired. 

Frameworks Referenced:
ISO/IEC 27001:2022: The international standard for information security management systems (ISMS). We will reference the Annex A controls.
SOC 2 (System and Organization Controls 2): A framework for managing customer data based on five "Trust Services Criteria" (TSC). We will focus primarily on the Security (Common Criteria), Confidentiality, and Availability TSCs.


## Amazon S3 (Simple Storage Service)

Controls for S3 focus on protecting data at rest and in transit, and preventing unauthorized access.

| Control ID | Severity | AWS Resource/Feature | Control Description | ISO 27001 Annex A | SOC 2 Common Criteria (CC) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| S3-01 | Critical | Block Public Access | Enable "Block all public access" at the account and bucket level to prevent accidental public exposure of data. | A.8.2, A.8.9, A.8.24 | CC6.1, CC6.7 |
| S3-02 | High | Bucket Policies & ACLs | Implement restrictive bucket policies and Access Control Lists (ACLs) that enforce least-privilege access to objects. | A.5.15, A.8.3 | CC6.1, CC6.5 |
| S3-03 | High | Server-Side Encryption | Enforce server-side encryption for all objects stored in S3. Use AWS Key Management Service (SSE-KMS) for manageable, audited encryption keys. | A.8.24 | CC6.7, Confidentiality |
| S3-04 | High | Encryption in Transit | Enforce encryption of data in transit by requiring HTTPS (TLS) connections to S3 endpoints using a bucket policy condition (aws:SecureTransport). | A.8.24 | CC6.7, Confidentiality |
| S3-05 | High | Versioning & MFA Delete | Enable versioning on S3 buckets to protect against accidental deletion or overwrites. Enable MFA Delete for an additional layer of protection against object deletion. | A.8.13, A.8.14 | CC3.2, Availability |
| S3-06 | Medium | S3 Access Logs | Enable server access logging for all S3 buckets. Store logs in a separate, secure S3 bucket for audit and security analysis. | A.8.15, A.8.16 | CC7.1, CC7.2 |
| S3-07 | Medium | S3 Object Lock | Use S3 Object Lock for WORM (Write-Once-Read-Many) storage requirements, ensuring objects cannot be deleted or overwritten for a fixed amount of time. | A.8.9, A.8.13 | CC6.7, Confidentiality |
| S3-08 | Medium | Amazon Macie | Use Amazon Macie to discover and protect sensitive data (like PII and financial information) stored in S3 using machine learning and pattern matching. | A.8.9, A.8.20 | CC6.7, Confidentiality |

## Amazon EC2 (Elastic Compute Cloud) & VPC (Virtual Private Cloud)
These controls cover network security, host-level security, and data protection for virtual servers and networks.

| Control ID | Severity | AWS Resource/Feature | Control Description | ISO 27001 Annex A | SOC 2 Common Criteria (CC) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| EC2-01 | Critical | Security Groups | Use security groups as a stateful firewall to control inbound and outbound traffic to EC2 instances. Follow the principle of least privilege. | A.8.23 | CC6.1, CC6.6 |
| EC2-02 | Medium | Network ACLs (NACLs) | Use NACLs as a stateless firewall at the subnet level for an additional layer of defense. | A.8.23 | CC6.1, CC6.6 |
| EC2-03 | Medium | VPC Endpoints | Use VPC endpoints to privately connect your VPC to supported AWS services without requiring an internet gateway, NAT device, or VPN connection. | A.8.23 | CC6.1, CC6.6 |
| EC2-04 | High | EBS Encryption | Encrypt all EBS volumes attached to EC2 instances using AWS KMS to protect data at rest. Enable "Encrypt by Default" for the region. | A.8.24 | CC6.7, Confidentiality |
| EC2-05 | High | AMI Management | Use hardened, patched, and approved Amazon Machine Images (AMIs). Implement a process for regularly updating and patching your custom AMIs. | A.8.7, A.8.8 | CC7.1 |
| EC2-06 | Critical | Patch Management | Implement a robust patch management process for the operating systems and applications on your EC2 instances using AWS Systems Manager Patch Manager. | A.8.8 | CC7.1 |
| EC2-07 | High | SSH Key Management | Prohibit the use of password-based logins for EC2 instances. Use securely managed SSH key pairs. Do not use the same key pair for all instances or regions. | A.5.17, A.8.5 | CC6.1, CC6.3 |
| EC2-08 | High | VPC Flow Logs | Enable VPC Flow Logs to capture information about the IP traffic going to and from network interfaces in your VPC. Analyze these logs for anomalous traffic. | A.8.15, A.8.16 | CC7.1, CC7.2 |
| EC2-09 | High | AWS Systems Manager | Utilize AWS Systems Manager Session Manager for secure, auditable remote access to EC2 instances, eliminating the need for open inbound SSH or RDP ports. | A.8.5, A.8.16 | CC6.1, CC6.6 |


## Amazon RDS (Relational Database Service)
Controls for RDS focus on securing the database engine, the data it contains, and the network connections to it.

| Control ID | Severity | AWS Resource/Feature | Control Description | ISO 27001 Annex A | SOC 2 Common Criteria (CC) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| RDS-01 | High | Encryption at Rest | Enable encryption at rest for all RDS instances and snapshots using AWS KMS. | A.8.24 | CC6.7, Confidentiality |
| RDS-02 | High | Encryption in Transit | Enforce SSL/TLS for all connections to your RDS instances to protect data in transit. | A.8.24 | CC6.7, Confidentiality |
| RDS-03 | Critical | Public Accessibility | Configure RDS instances to not be publicly accessible. Access should be restricted to within the VPC. | A.8.2, A.8.23 | CC6.1, CC6.6 |
| RDS-04 | Critical | Security Group Access | Restrict network access to RDS instances using security groups. Only allow connections from specific application servers or bastion hosts. | A.8.23 | CC6.1, CC6.6 |
| RDS-05 | High | Automated Backups & Retention | Enable automated backups for RDS instances and configure an appropriate backup retention period to support point-in-time recovery. | A.8.13 | CC3.2, Availability |
| RDS-06 | High | Database Logging | Enable and configure database engine logging (e.g., audit, error, general, slow query logs) and forward them to CloudWatch Logs for monitoring and analysis. | A.8.15, A.8.16 | CC7.1, CC7.2 |
| RDS-07 | Medium | IAM Database Authentication | Where supported, use IAM database authentication to manage database access using IAM users and roles instead of native database credentials. | A.5.15, A.8.2 | CC6.1, CC6.2 |
