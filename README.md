# Overview: Sadi's Guidebook to Shifting Left

This "Sadi's Guidebook to Shifting Left" is a tangible introduction to my security philosophy: **prevent security issues before they exist** by making secure choices the easiest choices.

My approach uses automation to embed security directly into development workflows, reducing manual overhead and accelerating launch times. The code within this repo is primarily Terraform and Kubernetes YAML, managed via Git, reflecting the tools required for the role from the website, in which I have extensive experience. Critically, please keep in mind that all of the following directories were built with the foundational requirements of ISO and SOC 2 standards in mind.

## The Shift-Left Security Lifecycle

This guidebook is organized according to a **shift-left security philosophy** that prioritizes prevention over detection. The four phases progress from most proactive (left) to most reactive (right), creating a comprehensive security program where each phase builds upon the previous ones.

### 🛡️ Phase 1: Foundation & Prevention
*Building security culture and standards before code is written*

### 🏗️ Phase 2: Design & Development
*Integrating security into architecture and development processes*

### ⚙️ Phase 3: Infrastructure & Deployment
*Securing platforms and runtime environments*

### 🚨 Phase 4: Operations & Response
*Managing incidents and continuous improvement*

---

## 1. Foundation & Prevention

This phase represents the **most proactive** stage in our security lifecycle, where we focus on preventing security issues before they can even be created by building a strong security culture and comprehensive standards.

### 1. Security Training & Culture

This directory establishes a comprehensive security training and culture framework designed to embed security into the organizational DNA. By developing security expertise across all teams and fostering a security-first mindset, this program transforms security from a compliance requirement into a competitive advantage. The program includes a Security Champions Program, developer security onboarding curriculum, gamification and recognition systems, continuous security awareness content, and role-specific security training.

### 2. Developer Documentation

This directory provides engineers with a clear, actionable foundation for building secure, compliant, and resilient systems across both application code and infrastructure.

**Application Security:**
Comprehensive secure development standards that guide engineers to build security into every stage of the development lifecycle. It covers secrets management, secure dependency management, authentication and authorization practices, and safe logging standards. The goal is to make secure coding seamless and effective from day one.

**Infrastructure Security:**
AWS security best practices organized by service, with severity ratings and compliance mappings to help teams build secure and compliant infrastructure from the ground up. Engineers can reference control mappings to compliance frameworks and reduce review cycles by following predefined standards.

**Additional Resources:**
- Comprehensive security glossary with 100+ terms
- Quick reference cards for daily security tasks
- Container security guidelines and standards

---

## 2. Design & Development

This phase focuses on integrating security into the architecture and development processes where we can catch and fix issues early, when they're cheapest and fastest to resolve through automated security controls.

### 1. Application Coding Checklist

A comprehensive application security checklist that outlines essential security tasks across the entire software development lifecycle, from initial design to post-deployment operations. It details proactive measures like threat modeling and secure coding, integrates automated scanning (SAST, DAST, SCA, IaC), and covers operational controls like logging, hardening, and incident response.

### 2. CI/CD Pipeline Security

A security-first CI/CD pipeline proposal for GitHub that embeds robust security controls throughout the development lifecycle. By integrating automated scanning for application code (SAST/DAST), container images, and Infrastructure as Code (IaC), we can proactively identify and remediate vulnerabilities early. The strategy defines key standards for access control, secret management, and pipeline integrity.

---

## 3. Infrastructure & Deployment

This phase secures the foundational infrastructure and deployment environments where our applications run, implementing security controls at the platform level that automatically enforce security policies.

### 1. Infrastructure Hardening

Terraform modules for IAM password policies and other hardening standards that demonstrate how to bake security directly into cloud infrastructure. This "security-by-default" approach ensures consistency across all accounts, eliminates configuration drift, and simplifies auditing by reducing complex security tasks to reusable modules.

### 2. Control Policies - SCP

Practical Terraform configurations for proactive AWS governance using Service Control Policies. These examples demonstrate implementing high-impact security controls across an AWS Organization, such as preventing IAM privilege escalation and enforcing encryption for data-in-transzmit.

### 3. Kubernetes Security

Comprehensive guide to building a secure Kubernetes ecosystem by embedding security throughout the entire application lifecycle. It emphasizes a proactive approach by integrating vulnerability and secret scanning into CI/CD pipelines, enforcing least privilege with RBAC, hardening pod configurations, and implementing network policies.

### 4. SSM Automation

Serverless, automated security responses that detect and remediate misconfigurations in near real-time. Examples include automated S3 bucket public access remediation using EventBridge, Lambda functions, and SSM Automation documents to enforce security policies without manual overhead.

---

## 4. Operations & Response

This final phase focuses on managing security incidents, monitoring threats, and continuously improving our security posture through comprehensive programs for residual risk management and stakeholder trust.

### 1. Third-Party Risk Management

Comprehensive processes for identifying, assessing, and mitigating risks associated with third-party vendors, suppliers, and technology partners. Essential for maintaining security posture and regulatory compliance in an increasingly interconnected ecosystem.

### 2. Advanced Threat Intelligence

Threat intelligence capability that transforms raw security data into actionable insights, enabling proactive defense against emerging threats through external intelligence integration, security research, and industry collaboration.

### 3. Customer Security Program

Comprehensive approach to customer security that builds trust through transparency, collaboration, and shared security responsibility. Transforms security from a compliance requirement into a competitive advantage that drives customer confidence.

### 4. Incident Response

Comprehensive Incident Response Plan designed to ensure swift, effective, and coordinated response to security breaches. Includes formal Incident Response Team structure, severity classification, communication strategies, and automated Terraform playbooks for rapid containment.

### 5. Security Reporting

Framework for security reporting that combines comprehensive assessment structures with proactive communication strategies. Provides templates for security assessments, multi-audience communication strategies, and automated evidence generation for auditors.

### 6. Security Metrics & KPI

Comprehensive metrics and KPI system to measure, monitor, and improve security program effectiveness. Enables data-driven security decisions, value demonstration, and informed investment prioritization through effectiveness metrics and ROI analysis.

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



