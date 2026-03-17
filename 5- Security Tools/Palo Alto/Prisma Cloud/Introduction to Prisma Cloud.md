
Prisma Cloud is Palo Alto Networks' flagship **Cloud Native Application Protection Platform (CNAPP)**. It is designed to provide "Code-to-Cloud" security by integrating security into the developer's workflow and maintaining protection through production.

### 1. The Core Vision: Code-to-Cloud

- **Platform Consolidation:** Prisma Cloud eliminates "point product fatigue" by combining multiple security disciplines (CSPM, CWPP, CIEM, etc.) into a single integrated console.

- **The "Darwin" Release:** A major architectural shift that unified the platform, allowing for **Cloud-to-Code traceability**. If a risk is found in production, the platform can trace it back to the specific line of Infrastructure as Code (IaC) that created it.

- **Full Lifecycle Security:** 
	- **Build:** Scanning code, images, and templates in CI/CD.
    - **Deploy:** Preventing insecure deployments via admission controllers.
    - **Run:** Monitoring and protecting active workloads in real-time.

---

### 2. Key Functional Pillars

Prisma Cloud is divided into several modules that work together to provide a holistic security posture:

- **CSPM (Cloud Security Posture Management):** Continuous monitoring of cloud configurations (AWS, Azure, GCP, OCI).
    - Automated remediation of misconfigurations (e.g., publicly accessible S3 buckets).
    - Compliance reporting for frameworks like SOC2, HIPAA, and GDPR.

- **CWPP (Cloud Workload Protection Platform):** Secures Hosts (VMs), Containers (Kubernetes), and Serverless (Lambda).
    - Uses **Defenders** (agents) for runtime protection and **Agentless Scanning** for visibility.

- **CIEM (Cloud Infrastructure Entitlement Management):** Analyzes permissions to enforce **Least Privilege**.
    - Identifies "Net Effective Permissions" to see what a user _can_ do versus what they _actually_ do.

- **DSPM (Data Security Posture Management):** Automatically discovers and classifies sensitive data (PII, financial data) in cloud storage.
    - Assesses risks like data exposure or unauthorized access paths.

- **WAAS (Web App & API Security):** Protects against OWASP Top 10 threats, bot attacks, and API abuse from within the workload.

---

### 3. Architecture & Deployment Models

Prisma Cloud offers flexibility in how it gathers data and protects environments:

- **Agentless Scanning (SideScanning):**
    - Uses cloud snapshots to scan disks for vulnerabilities and malware.
    - **Pros:** Zero performance impact, 100% coverage of the environment instantly.

- **Agent-Based (Defenders):**
    - Small binaries installed on the workload (DaemonSets in K8s, Sidecars in Fargate).
    - **Pros:** Necessary for **Runtime Protection**, process blocking, and deep network inspection (microsegmentation).

- **Cloud Discovery:** Connects via Cloud APIs to ingest metadata about resources, identities, and traffic logs.

---

### 4. Operational Workflow (Day-to-Day)

- **Vulnerability Management:** Prioritizing CVEs based on **Environmental Context**. (e.g., A "Critical" vulnerability on a container that is not internet-facing is a lower priority than a "Medium" vulnerability on an internet-facing container).

- **Policy Enforcement:** Setting "Guardrails" for developers. If an IaC template contains a security flaw, the PR (Pull Request) is automatically blocked or flagged.

- **Runtime Defense:** Monitoring the "Radar" view to identify anomalous behavior, such as a container suddenly executing a shell or communicating with an unknown IP.

- **Incident Response:** Investigating alerts using integrated forensics that capture process trees and network flows at the time of an event.


---

### 5. Why it Matters in the Market

- **Multi-Cloud Parity:** Provides the same security experience regardless of whether the infrastructure is on AWS, Azure, or Google Cloud.

- **Shift-Left Integration:** Seamlessly integrates with tools like Jenkins, GitHub Actions, GitLab, and Terraform.

- **Regulatory Readiness:** Built-in templates for global compliance standards, making audits significantly faster for security teams.

---

### 6. Offered Versions

- **Prisma Cloud Enterprise Edition (PCEE)** - This is the SaaS version of Prisma Cloud, where Palo Alto Networks hosts the console and manages the underlying infrastructure and patches and updates to the console. 
	- **It is the only flavor where all of the modules above (CSPM, CWP, CAS) are offered to our customers.**

- **Prisma Cloud Compute Edition (PCCE)** - This is the self-hosted version of Prisma Cloud, where the customer must deploy the self-hosted console onto their infrastructure and manage all patches and upgrades themselves. 
	- **This version only includes the CWP module of Prisma Cloud.**