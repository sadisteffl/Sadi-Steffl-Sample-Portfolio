# Security Glossary

This glossary defines common acronyms and terms used throughout the Developer Documentation standards.

## Acronyms

### Security Frameworks & Standards
- **ABAC** - Attribute-Based Access Control
- **AES** - Advanced Encryption Standard
- **API** - Application Programming Interface
- **CCPA** - California Consumer Privacy Act
- **CI/CD** - Continuous Integration/Continuous Deployment
- **CIS** - Center for Internet Security
- **DDoS** - Distributed Denial of Service
- **DLP** - Data Loss Prevention
- **DNS** - Domain Name System
- **DSTI** - Data Security & Privacy Standard
- **DAST** - Dynamic Application Security Testing
- **FIDO** - Fast Identity Online
- **GDPR** - General Data Protection Regulation
- **gRPC** - Google Remote Procedure Call
- **HSM** - Hardware Security Module
- **IaC** - Infrastructure as Code
- **IAM** - Identity and Access Management
- **IDS/IPS** - Intrusion Detection System/Intrusion Prevention System
- **ISO** - International Organization for Standardization
- **ITDR** - Incident Response
- **JWT** - JSON Web Token
- **KMS** - Key Management Service
- **MFA** - Multi-Factor Authentication
- **NACL** - Network Access Control List
- **NIST** - National Institute of Standards and Technology
- **OAuth** - Open Authorization
- **OIDC** - OpenID Connect
- **OWASP** - Open Web Application Security Project
- **PAM** - Privileged Access Management
- **PII** - Personally Identifiable Information
- **RBAC** - Role-Based Access Control
- **REST** - Representational State Transfer
- **SaaS** - Software as a Service
- **SAML** - Security Assertion Markup Language
- **SCA** - Software Composition Analysis
- **SCP** - Service Control Policy
- **SDLC** - Software Development Lifecycle
- **SIEM** - Security Information and Event Management
- **SOC** - System and Organization Controls
- **SQL** - Structured Query Language
- **SSH** - Secure Shell
- **SSO** - Single Sign-On
- **TDE** - Transparent Data Encryption
- **TLS** - Transport Layer Security
- **TPM** - Trusted Platform Module
- **VPN** - Virtual Private Network
- **WAF** - Web Application Firewall

### Cloud & Infrastructure
- **AWS** - Amazon Web Services
- **AMI** - Amazon Machine Image
- **CDN** - Content Delivery Network
- **CMK** - Customer Master Key
- **EBS** - Elastic Block Store
- **EC2** - Elastic Compute Cloud
- **ECS** - Elastic Container Service
- **EKS** - Elastic Kubernetes Service
- **ELB** - Elastic Load Balancer
- **KMS** - Key Management Service
- **RDS** - Relational Database Service
- **S3** - Simple Storage Service
- **VPC** - Virtual Private Cloud
- **WAF** - Web Application Firewall

### Database & Storage
- **ACID** - Atomicity, Consistency, Isolation, Durability
- **ETCD** - Distributed key-value store (pronounced "et-see-dee")
- **NoSQL** - Not Only SQL
- **OLTP** - Online Transaction Processing
- **RDBMS** - Relational Database Management System

### DevOps & Development
- **Bash** - Bourne Again Shell
- **CLI** - Command Line Interface
- **CI/CD** - Continuous Integration/Continuous Deployment
- **Git** - Distributed version control system
- **IDE** - Integrated Development Environment
- **JSON** - JavaScript Object Notation
- **YAML** - YAML Ain't Markup Language

## Security Terms

### Access Control
- **Authentication** - The process of verifying identity
- **Authorization** - The process of granting or denying permissions
- **Least Privilege** - Security principle of granting minimum necessary access
- **Need-to-Know** - Principle of restricting access based on job requirements
- **Segregation of Duties** - Security practice of separating critical functions

### Cryptography
- **Encryption at Rest** - Protecting data when stored
- **Encryption in Transit** - Protecting data during transmission
- **Hashing** - One-way function for data integrity
- **Key Rotation** - Process of changing encryption keys
- **Symmetric Encryption** - Same key for encryption and decryption
- **Asymmetric Encryption** - Different keys for encryption and decryption

### Threats & Vulnerabilities
- **Attack Vector** - Path or means by which an attacker gains access
- **Breach** - Unauthorized access to data or systems
- **Exploit** - Code or technique that takes advantage of a vulnerability
- **Threat** - Potential cause of an unwanted incident
- **Vulnerability** - Weakness that can be exploited by a threat
- **Zero-Day** - Unknown vulnerability that hasn't been patched

### Network Security
- **DMZ** - Demilitarized Zone (network segment between internal and external networks)
- **Firewall** - Network security device that monitors and filters traffic
- **Intrusion Detection** - System that monitors for malicious activities
- **Microsegmentation** - Network security technique of creating small security zones
- **Network Segmentation** - Division of computer network into smaller segments

### Compliance & Governance
- **Audit Trail** - Record of activities for compliance and security
- **Compliance** - Adherence to laws, regulations, guidelines, and specifications
- **Due Diligence** - Process of researching and gathering information before making a decision
- **Governance** - Framework of rules and practices by which a board ensures accountability
- **Risk Assessment** - Process of identifying, analyzing, and evaluating risks

### Development Security
- **Secure by Design** - Approach where security is built into products from the beginning
- **Security by Default** - Products are secure in their default configuration
- **Secure Coding** - Practice of writing code that follows security guidelines
- **Static Analysis** - Analysis of code without executing it
- **Dynamic Analysis** - Analysis of code while it's running

### Incident Management
- **Breach Notification** - Process of notifying affected parties of a data breach
- **Containment** - Process of limiting the scope of an incident
- **Eradication** - Process of removing the cause of an incident
- **Incident Response** - Organized approach to addressing and managing security incidents
- **Recovery** - Process of returning to normal operations after an incident

### Authentication & Identity
- **Biometrics** - Biological measurements used for identification
- **Credentials** - Information used to verify identity (username/password, certificates, etc.)
- **Identity** - Information that uniquely describes an entity
- **Passwordless** - Authentication methods that don't use passwords
- **Single Sign-On** - Authentication process allowing access to multiple systems with one login

### Data Protection
- **Data Classification** - Process of categorizing data based on sensitivity
- **Data Masking** - Process of hiding original data with modified content
- **Data Retention** - Policies governing how long data is kept
- **PII** - Information that can be used to identify an individual
- **Right to be Forgotten** - Right to have personal data deleted upon request

## Cloud-Specific Terms

### AWS
- **Availability Zone** - Distinct location within an AWS Region
- **Instance** - Virtual server in the AWS Cloud
- **Region** - Geographic area where AWS data centers are located
- **Security Group** - Virtual firewall for instances to control inbound and outbound traffic
- **Snapshot** - Point-in-time backup of volumes

### Containers & Orchestration
- **Container** - Standard unit of software that packages up code and dependencies
- **Container Image** - Read-only template used to create containers
- **Docker** - Platform for developing, shipping, and running applications in containers
- **Kubernetes** - Container orchestration platform for automating deployment and management
- **Pod** - Smallest deployable unit in Kubernetes

## Compliance Framework Terms

### ISO 27001
- **Annex A** - Set of controls for information security management
- **ISMS** - Information Security Management System
- **Statement of Applicability** - Document outlining which controls are applicable and why

### SOC 2
- **Common Criteria** - Security criteria common to all SOC 2 reports
- **Trust Services Criteria** - Set of criteria used to evaluate systems
- **Type I Report** - Report on controls at a specific point in time
- **Type II Report** - Report on controls over a period of time

---

**Note:** This glossary is a living document and will be updated as new terms and technologies are introduced to our security standards.

**Last Updated:** [Current Date]
**Next Review Date:** [Quarterly Schedule]
**Maintained By:** Security Team