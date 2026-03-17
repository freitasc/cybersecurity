Tags: [[Cloud]], [[Container]], [[IaC Scanning]],

## What is it?

- Visibility for containers, VMs, pods etc.
- A security solution engineered to address the unique requirements of protecting workloads in cloud environments.
- [Workloads](https://www.paloaltonetworks.ca/cyberpedia/what-is-workload) can be hosted on a range of infrastructures, from traditional virtual machines to modern containers and serverless functions.
- Through various security controls, CWPPs preserve the integrity, confidentiality and availability of workloads.

## Additional Information

 - In cloud computing, workloads refer to the amount of processing that a cloud service has been contracted to handle.
	 - Applications
	 - Databases
	 - Batch jobs
	 - User requests
	 - Others
 - Each of these workloads presents a potential attack vector for threat actors.
 - CWPP provides comprehensive protection via a range of cloud workload security capabilities
	 - Vulnerability management
	 - Host intrusion detection/prevention
	 - Compliance management
	 - Image analysis
	 - Runtime protection
	 - Behavioral monitoring of workload
 - Agent-based vs Agentless
	 - **Agent-based solutions** require the installation of security agents on each workload.
		 - The agent lives inside the OS and watches everything in real-time (system calls, network traffic, file changes).
		 - Can actively **block** attacks in real-time (Prevention).
		 - **Examples:**
			 - **Prisma Cloud (Defender):** Uses a "Defender" binary on the host.
			 - **Sysdig:** Deep focus on eBPF-based agents for container forensics.
			 - **CrowdStrike Falcon Cloud Security:** Leverages their famous lightweight agent.
			 - **Trend Micro Cloud One:** A veteran in the agent-based space.
	 - **Agentless solutions** don’t require the installation of security agents
		 - It scans the disk for vulnerabilities, malware, and misconfigurations without touching the running CPU.
		 - Zero performance impact on your apps and very easy to deploy across thousands of accounts.
		 - **Examples:**
			- **Wiz:** Famous for pioneering the "SideScanning" approach.
			- **Orca Security:** Focuses on "SideScanning" to find risks without agents.
			- **Prisma Cloud (Agentless Mode):** Many platforms now offer both options to give you the best of both worlds.

#### Key Features of a CWPP

- Vulnerability Management
	- Incorporating vulnerability databases like CVE (Common Vulnerabilities and Exposures), the CWPP applies threat intelligence to assess the risk posed by vulnerabilities.
	- The platform also supports vulnerability remediation, either by providing patching tools or integrating with existing patch management solutions.
	- The CWPP aids in prioritizing mitigation based on the severity of vulnerabilities, contextual risk factors with the workload, and the sensitivity of the data and services affected.
- Configuration Management
	- The CWPP allows for configuration management, monitoring and enforcement of security best practices.
	- The platform also offers remediation advice or automates the enforcement of secure configurations.
- Compliance Management
	- Compliance management ensures that cloud workloads align with regulatory standards
	- The platform also generates compliance reports detailing the compliance status of cloud workloads, as well as dashboards to visualize security posture and compliance status.
- Image Analysis
	- Image analysis involves scrutinizing container images for potential security issues 
		- Outdated, vulnerable packages
		- Embedded malware
		- Others
	- The CWPP also allows you to implement policies that define which registries, repositories and images you can trust.
- Consistency Across Cloud Environments
	- CWPPs ensure that security policies and controls are consistently applied across all cloud environments.
		- GCP
		- Azure
		- AWS
		- Others
- CI/CD Pipeline Integration
	- The CWPP integrates with existing security tools and processes
		- SIEM
		- SOAR
		- DevOps tools (sonarqube etc)
	- Provides security feedback early in the software development lifecycle and help facilitate shift-left security practices
- Runtime Protection
	- Runtime protection involves monitoring and protecting workloads as they run in the cloud computing environment, defending against attacks and unauthorized activities in real time.
	- The CWPP commands runtime protection with robust threat detection capabilities, 
		- behavioral analysis
		- machine learning (ML)
		- signature-based detection.
- Microsegmentation
	- Many CWPP's offer microsegmentation capabilities that allow developers and security teams to isolate workloads and limit lateral movement within the environment.
- Web Application and API Security (WAAS)
	- Some CWPPs incorporate elements of web application and API security (WaaS), especially as they pertain to containerized and cloud-native applications.
	- For instance, regarding API security, a CWPP may include functionalities to ensure secure communication between microservices in a microservices architecture, which is often implemented in cloud-native applications.
- Web Application Firewall (WAF)
	- Some advanced CWPPs offer security features typically part of a web application firewall (WAF). 
	- WAFs protect against OWASP Top 10 security risks, such as injection, broken authentication and cross-site scripting (XSS) vulnerabilities.
	- t’s important to note that while CWPPs can have overlapping functionalities with WAFs and API Security solutions, they should complement and not replace these solutions.
	
## Related Notes

#### 1. The Core Architecture: Defenders vs. Agentless

Palo Alto’s "Better Together" strategy is their big selling point. You must know when to use which:

- **The Defender (Agent-based):** A small binary deployed onto your workloads.
    - **Orchestrator Defender:** Deployed as a **DaemonSet** in Kubernetes. It automatically ensures every node in the cluster is protected.
    - **App-Embedded Defender:** Used for environments where you don't own the host (e.g., **AWS Fargate**). It runs as a sidecar or is injected into the container.
    - **Function Defender:** A layer or "wrapper" for Serverless (Lambda).
    - **Why use it?** Real-time **blocking** (prevention), eBPF-powered network monitoring, and forensic data collection.
- **Agentless Scanning:** Uses cloud APIs to take a snapshot of the workload’s disk (EBS/Managed Disk) and scans it in a separate sandbox.
    - **Why use it?** Perfect for "dark" corners of the environment where you can't install agents, or for initial onboarding to get a baseline without breaking production.
        

---

#### 2. The Day-to-Day Operations

If you were managing CWP for a large client, your "day in the life" would look like this:
- **Vulnerability Triage:** You don't just look at "Criticals." You use the **Intelligence Stream** (Palo Alto's proprietary feed) to see which CVEs have a "Fix Available" or are actually "In-use" (packages currently loaded in memory).
- **Policy Tuning:** You’ll spend time moving from **"Alert"** to **"Prevent"**. For example, setting a policy that says: _"If a developer tries to deploy an image with a Critical CVE older than 30 days, block the CI/CD pipeline."_
- **Runtime "Radar" Monitoring:** Using the **Radar** (a visual map of the environment) to spot "untrusted" network flows. If a web server starts talking to a known Tor exit node, the CWP tool should kill the process automatically.
- **Incident Forensics:** When a pod is compromised, the CWP tool saves a **forensic snapshot** (process tree, network calls, file changes). You would analyze this to see how the attacker moved laterally.

#### 3. Real-World "Killer Features"

| **Feature**             | **What it actually does in production**                                                                                                                        |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **WAAS**                | (Web App & API Security) - It’s a WAF that sits _inside_ the workload, protecting the app from SQLi or XSS without needing a separate appliance.               |
| **Trust Groups**        | Automatically learns how containers talk to each other and creates "Least Privilege" network rules so you don't have to write thousands of firewalls manually. |
| **Compliance Explorer** | Maps your current container state directly to **CIS Benchmarks**, NIST, or PCI-DSS for auditors at the click of a button.                                      |
| **Shift-Left**          | Using `twistcli` (their CLI tool) to scan images _on the developer's laptop_ before they even push to GitHub.                                                  |

---

#### 4. Good Key Questions to Prepare Yourself

1. **"How would you secure a workload where you don't have root access to the host?"**
    - _Answer:_ Use the **App-Embedded Defender** or **Agentless Scanning** depending on whether you need runtime prevention or just visibility.
        
2. **"A customer is worried that an agent will crash their production server. How do you respond?"**
    - _Answer:_ Mention **Agentless Scanning** for zero-impact visibility, and highlight that the **Defender** has configurable resource limits (CPU/RAM caps) to ensure it never starves the application.
        
3. **"What's the difference between a 'Build' policy and a 'Run' policy?"**
    - _Answer:_ **Build** policies catch "static" risks (hardcoded secrets, old OS packages) in the registry. **Run** policies catch "dynamic" risks (a process suddenly spawning a shell, or a container writing to `/etc/shadow`).

## References

https://www.paloaltonetworks.ca/cyberpedia/what-is-cwpp-cloud-workload-protection-platform