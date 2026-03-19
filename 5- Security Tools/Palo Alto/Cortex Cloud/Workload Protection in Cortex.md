Tags: [[Cloud]], [[Container]], [[Hardening]]

## What is it?

- Protecting containers, clusters, VMs, databases etc
## Additional Information

### Rules & Policies

- Cloud Workload Policies serve as enforcement mechanisms that govern the responses to the identified findings.
- Cloud Workload Rules establish the criteria for evaluation but do not initiate any actions unless incorporated within a policy.

#### Policies

- Cloud Workload Policies serve as enforcement mechanisms that govern the responses to the identified findings.
	- Policies help you prevent and manage security violations in your cloud runtime instances. 
	- They enable you to apply detection logic to specific asset groups at the desired SDLC stage, and define what action needs to be taken if the conditions are met.
	- SDLC Evaluation Stage
		- CI: The stage during which a pipeline builds the artifact.
		- Deploy: The stage when the artifact is pushed to a cloud instance for running.
		- Runtime: The stage when the artifact is running on a cloud instance.
	- Types of policies
		- **Misconfiguration policies:** Enables you to assess various workloads for misconfigurations against relevant security standards and your organization’s security guidelines.
		- **Malware policies:** Enable you to detect and manage malicious files within cloud workloads. These policies analyze files based on predefined parameters such as file name, path, size, and detection method.
		- **Secret policies:** Enable you to identify and protect sensitive information—such as API keys and credentials—within workloads.
		- **Trusted Image policies:** Enable you to ensure the authenticity, integrity, and security of container images and VMs deployed into your Kubernetes environments. This includes actions such as limiting allowed image sources, mitigating possible image tampering, and more.
	
#### Rules

- Cloud Workload Rules establish the criteria for evaluation ==but do not initiate any actions unless incorporated within a policy==.
	- Rules define the detection logic for misconfigurations and their applicable asset types, specifying the criteria and conditions used to identify security risks. 
	- These rules can be selected and enforced through Misconfiguration Policies within the designated policy asset scope.
	- Rules only enable the detection of security violations. They must be included in a policy to trigger a preventive response or generate an alert in the form of an issue.
	- **Scanner:** You can define the mechanism by which the rule inspects the cloud assets.
		- Agentless Disk Scan: Rules that use Agentless Disk Scanner to inspect the container images on which the Agentless scanner runs. You can specify different rules for containers running different OSes. For example, you can create a rule that checks for incorrect or malicious entries in the etc\hosts file on Windows images.
		- [Kubernetes Connector:](https://docs-cortex.paloaltonetworks.com/r/Cortex-XDR/Cortex-XDR-Cloud-Documentation/What-s-new-in-Kubernetes-Connector) Rules that use the Kubernetes Connector scanner to inspect Kubernetes environment variables and resources such as Namespaces, ReplicaSets, Deployments and more.
		- [XDR Agent:](https://docs-cortex.paloaltonetworks.com/r/Cortex-XDR/Cortex-XDR-Cloud-Documentation/Install-Cortex-XDR-agents) Rules that use XDR Agent Scanner to perform custom compliance checks by executing user-defined Python scripts, offering a tailored approach to compliance validation.

### Agentless vs Agent-based (XDR)

| **Agentless**                                                                                                                                                                   | **Agents (Cortex XDR)**                                                                                                                                           |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Simplified visibility into vulnerability and compliance                                                                                                                         | Continuous, real-time runtime protection                                                                                                                          |
| **Distributed Access -** For distributed environments across different teams, gettings access to deploy agents is difficult                                                     | **Defense in Depth -** For sensitive workloads, deploy defenders/agents to gain deep insights into running processes, runtime forensics, behavioral analysis etc. |
| **First step in securing -** start with agentless security as soon as you on board accounts for first look into all hosts without need for running deployment scripts per hosts | **Advanced security with active prevention -** Actively prevent access to sensitive file systems or malware from being deployed with block capabilities           |
| **No running management -** Agentless uses snapshot based scanning, with no running tools inside your environment to manage                                                     | **Continuous monitoring -** For instances where you require continuous and immediate alerts                                                                       

- The original Prisma Defender got absorbed into Cortex XDR
- Now, the agent is not a workload-monitoring only agent, it extends as a full Extended Detection and Response

#### Agentless

- All agentless scans can be triggered by rules and policies
- Agentless can scan full VM images and it is automatically enabled upon onboarding
- Agentless can full disk scan on a machine
- Agentless can scan container images and container registries
- Agentless can integrate through API gateways to provide Web and API Security
	- It sits an Out-of-Band NDR
	- In-depth scans, thorough analysis, and timely alerts to detect and mitigate security risks and potential vulnerabilities effectively.
	- It cannot respond, as it is not running on the affected machine, it can only generate alerts.

####  Agent-based (XDR)

- XDR is a endpoint and server protection by combining multiple capabilities
	- AI-driven analytics
	- endpoint controls
	- next-generation antivirus
	- automated investigation to detect and respond to threats across various environments
- XDR detects anomalies and threats using machine learning and behavioral models across endpoint, network, and identity data.
- XDR, differently than Agentless, can not only detect but actively respond to threats
- Cortex XDR auto-identifies if a host is running a container orchestrator.
- XDR can also act as a In-Line NDR, reading and responding into the network in real time
	- It can generate alerts for abnormal network behavior, such as port scan activity.
	- It can proactively respond, providing real-time protection 
- XDR employs Agentic AI to streamline security operations

### Cortex CLI for CWP

- You can integrate Cloud Workload Protection scans for secrets, vulnerabilities and malware during your continuous integration (CI) process
- The `cortexcli image scan` command allows you to perform CWP scans on container images. 
- By default, `cortexcli` scans images directly from your local Docker daemon's repository. You can also specify an image archive file to scan instead.
- To scan an image that exists in your local Docker daemon, simply provide its name:

`./cortexcli --api-base-url <API URL> --api-key <API key from the "Authenticate" step in the CLI connector screen> --api-key-id <API key ID from the "Authenticate" step in the CLI connector screen> image scan <image name>`

- This way you can scan the images from containers in a agentless approach and on-demand
- You can also subscribe this commands to a routine into your CI, crontab or whatever

## Related Notes



## References