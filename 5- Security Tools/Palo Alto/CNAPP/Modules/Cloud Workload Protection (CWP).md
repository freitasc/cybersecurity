Tags: [[Cloud]], [[Container]]

## What is it?

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
	- 
## Related Notes



## References