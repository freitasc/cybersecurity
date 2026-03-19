Tags: [[Cloud]], [[Container]], [[Hardening]]

## What is it?

- Protecting containers, clusters, VMs, databases etc
## Additional Information

### CORTEX GUI

- Using the Cortex GUI: It is mainly for SDLC and before-deploy stage
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

### CORTEX CLI




## Related Notes



## References