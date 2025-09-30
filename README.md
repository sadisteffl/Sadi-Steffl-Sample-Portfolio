# Overview: Sadi's Guidebook to Shifting Left

 This "Sadi's Guidebook to Shifting Left" is a tangible introduction to my security philosophy: to empower engineers by making secure choices the easiest choices.

My approach uses automation to embed security directly into development workflows, reducing manual overhead and accelerating launch times. The code within this repo is primarily Terraform and Kubernetes YAML, managed via Git, reflecting the tools required for the role from the website, in which I have extensive experience. Critically, please keep in mind that all of the following directories were built with the foundational requirements of ISO and SOC 2 standards in mind.

This guidebook is my blueprint for how security can be a strategic partner to engineering, ensuring a strong compliance posture from day one without sacrificing speed.

---

## 1. Documentation

This repo is designed to give engineers a clear, actionable foundation for building secure, compliant, and resilient systems - across both application code and infrastructure.

### Application

This directory provides a practical overview of secure development standards for a company's application code, offering guidance for engineers to build security into every stage of the development lifecycle. It covers key areas such as secrets management using approved tools, secure dependency management using CI-integrated SCA tools, robust authentication and authorization practices, and safe logging standards. These are just a few examples of what should be posted on the intranet site. The goal is to make secure coding seamless and effective from day one. Security is a shared responsibility, and this resource - along with supporting tools, training, and examples - is here to help engineers write secure, compliant, and resilient code by default.

### Infrastructure

This directory outlines a mapping of AWS security best practices - specifically focused on AWS. It organizes controls by AWS service, includes severity ratings, and aligns each practice with compliance requirements to help teams build secure and compliant infrastructure from the ground up. While this version highlights a couple of standard practices, the full version will include detailed expectations for every AWS resource, giving developers a clear, actionable guide to meet both internal standards and external audit frameworks.

Engineers can use this guide to:

-   Understand **how to securely build**
-   Reference **control mappings** to compliance frameworks
-   Reduce back-and-forth during reviews by following **predefined standards**

While this version includes foundational examples, a complete version will be provided upon hire with detailed security expectations for **every AWS resource** in the environment. This not only accelerates secure deployment but gives developers a trusted source to reference during infrastructure provisioning and compliance reviews.

---

## 2. CI/CD Checklist

This proposal outlines a security-first CI/CD pipeline for GitHub, designed to embed robust security controls throughout the development lifecycle. By integrating automated scanning for application code (SAST/DAST), container images, and Infrastructure as Code (IaC), we can proactively identify and remediate vulnerabilities early. The strategy also defines key standards for access control, secret management, and pipeline integrity to build a secure, compliant, and efficient development process from day one.

---

## 3. Application Coding Checklist

This document provides a comprehensive application security checklist, outlining essential security tasks across the entire software development lifecycle, from initial design to post-deployment operations. It details proactive measures like threat modeling and secure coding, integrates automated scanning (SAST, DAST, SCA, IaC), and covers operational controls like logging, hardening, and incident response.

---

## 4. Hardening - IaC Modules

This Terraform module for an IAM password policy is a practical example of how to bake security directly into your cloud infrastructure, hardening authentication controls. The process is designed for maximum efficiency: when provisioning a new AWS account, its Terraform configuration simply calls this reusable, version-controlled module to automatically enforce a strong, standard password policy. This "security-by-default" approach offers significant benefits by ensuring consistency across all accounts, which eliminates configuration drift and simplifies auditing. It reduces a complex security task to a single line of code and allows for centralized management, meaning the policy can be updated once and rolled out in a controlled manner, guaranteeing a strong security posture from day one without manual intervention.

---

## 5. Control Policies - SCP

This repository provides a practical Terraform configuration for proactive AWS governance. This example code creates one comprehensive SCP that enforces two critical, preventative security controls simultaneously. First, it prevents IAM privilege escalation by requiring a specific permissions boundary on all newly created roles. Second, it ensures data-in-transit is encrypted by mandating that all new or modified RDS databases use a parameter group that enforces SSL/TLS connections, providing a scalable template for implementing high-impact security across an AWS Organization.

---

## 6. Kubernetes Samples

This repository provides a comprehensive guide to building a secure Kubernetes ecosystem by embedding security throughout the entire application lifecycle. It emphasizes a proactive, "shift-left" approach by integrating vulnerability and secret scanning directly into the CI/CD pipeline to block threats before they reach production. Key technical controls demonstrated include enforcing least privilege with RBAC, hardening pod configurations to prevent execution as root, and implementing default-deny network policies to control traffic flow. Furthermore, this guide covers enhancing the security of managed services like AWS EKS with customer-controlled KMS encryption and advocates for leveraging specialized vendors to achieve zero-CVE container images and continuous runtime integrity, ensuring a resilient and compliant environment from code to cloud all while complying with audits.

---

## 7. Automation Using SSM Directory

This repository provides a serverless, automated security response to detect and remediate publicly exposed AWS S3 buckets in near real-time, acting as a critical detective and corrective control. Deployed via Terraform, the solution uses an event-driven architecture where an EventBridge rule monitors CloudTrail for API calls that make a bucket public. Upon detection, it triggers an AWS Lambda function that invokes an SSM Automation document to automatically apply a strict Public Access Block and set the bucket's ACL to private. This entire workflow enforces security policies with no manual overhead, ensuring data remains protected from misconfigurations and directly supporting key compliance frameworks.

---

## 8. Incident Response Directory

This directory provides a comprehensive corporate Incident Response Plan designed to ensure a swift, effective, and coordinated response to security breaches, thereby minimizing operational and reputational damage. The plan establishes a clear framework by defining a formal Incident Response Team (IRT) with specific roles, classifying incidents by severity level to prioritize actions, outlining a structured communication strategy for internal and external stakeholders, and mandating regular testing and maintenance to keep the plan current. To support the execution of this plan, I have also built an automated Terraform Playbook for AWS Incident Response, which can be triggered to instantly neutralize a compromised IAM user by deactivating their access keys, detaching all policies, applying an explicit "DenyAll" policy, and deleting their console login profile, demonstrating how automated workflows can be integrated for rapid containment.

---

## 9. Reporting

This directory provides a framework for security reporting that combines comprehensive assessment structures with a proactive, tiered strategy for continuous communication. It includes templates and examples for formal security assessments designed to build comprehensive reports and provide a complete view of the security posture, covering everything from a high-level executive summary and detailed technical findings to a strategic roadmap with key metrics (KPIs). The framework also outlines a multi-audience strategy to tailor communication for specific needs: providing leadership with high-level dashboards on overall health, equipping technical teams with granular, real-time alerts for immediate remediation, and generating historical, automated evidence for auditors.

---

# Notes

### Cost

Given the opportunity, I would welcome a discussion with the CTO to provide potential pricing for a full implementation or go over other methods and architectural choices.

### Gaps 

I have also identified several areas that are intentionally not fully built out in this sample but would be critical components of a production-ready environment. These are topics I am prepared to discuss in greater detail:

#### Threat Modeling

Threat modeling is crucial because it helps companies find security problems before building anything. Including threat modeling from the start is important because it's dramatically cheaper and more effective to design security in from the beginning than to try and add it on later. It helps build a fundamentally secure application, rather than just patching holes after they've already been built.

#### Data Security & Governance
Data is the lifeblood of an AI company, so its security and governance are a top-level priority, adding a strategic layer beyond foundational controls like Macie and encryption. A robust data governance program is critical for building and maintaining trust. This starts with clear data classification policies to ensure we understand our data's sensitivity and apply the right protections. It also includes disciplined data lifecycle management to responsibly handle information from creation to secure deletion, which is crucial for minimizing risk when managing vast training datasets. Finally, collaborating with the privacy team on Data Protection Impact Assessments (DPIAs) is non-negotiable. This allows us to proactively identify and mitigate privacy risks before a product launch, ensuring regulatory compliance and demonstrating a deep commitment to customer trust

#### Runtime Security

Runtime security is crucial because it protects companies's application while it's actually running in a live environment. No matter how well the design and scan of the code are before deployment, it's impossible to predict every possible threat. A brand-new vulnerability might be discovered, or an attacker could find a clever way to exploit a minor misconfiguration that only appears in the live system.

Including runtime security from the start is important because it acts as a final and most critical layer of defense. It actively monitors for suspicious behavior - like a container trying to access a file it shouldn't or an application making unexpected network connections - and can block these threats in real-time. Without it, companies would have a major blind spot and be vulnerable to attacks that static checks and firewalls simply cannot see.

---

# Conclusion

This guidebook is more than a collection of configurations and code; it's a practical reflection of my core philosophy. I believe that the concepts we learn and the people we meet within our community have a profound effect on our ability to address the world around us. The most successful people - and the most successful companies - are those who accumulate diverse skills, learn from their mistakes, and are always willing to innovate.

My approach to security is guided by a simple, personal principle: every day is a chance to make things better than they were the day before. I see mistakes and vulnerabilities not as failures, but as opportunities for growth. This is why I am so passionate about the "shift-left" model; it's a software-led initiative that bakes learning and improvement directly into the development process. For me, a successful day is one where I've learned something new while helping my team build more secure, resilient systems.

This mindset directly aligns with my mission to drive progress through software. To build world-changing AI, the underlying security function must be a catalyst, not an obstacle. It must be as agile, automated, and forward-thinking as the technology it protects. My goal is to help build that function - one that empowers engineers, automates compliance, and turns every challenge into a chance to improve.



