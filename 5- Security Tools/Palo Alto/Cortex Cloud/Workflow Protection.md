Tags: [[Cloud]], [[Container]], [[Hardening]]

## What is it?

- Protecting containers, clusters, VMs, databases etc
## Additional Information

- Using the Cortex GUI: It is mainly for SDLC and before-deploy stage
	- Policies
		- Policies help you prevent and manage security violations in your ==cloud== runtime instances. 
		- They enable you to apply detection logic to specific asset groups at the desired SDLC stage, and define what action needs to be taken if the conditions are met.
		- SDLC Evaluation Stage
			- CI: The stage during which a pipeline builds the artifact.
			- Deploy: The stage when the artifact is pushed to a ==cloud== instance for running.
			- Runtime: The stage when the artifact is running on a ==cloud== instance.
		- Types of policies
			- **Misconfiguration policies:** Enables you to assess various ==workload==s for misconfigurations against relevant security standards and your organization’s security guidelines.
			- **Malware policies:** Enable you to detect and manage malicious files within ==cloud== ==workload==s. These policies analyze files based on predefined parameters such as file name, path, size, and detection method.
			- **Secret policies:** Enable you to identify and protect sensitive information—such as API keys and credentials—within ==workload==s.
			- **Trusted Image policies:** Enable you to ensure the authenticity, integrity, and security of container images and VMs deployed into your Kubernetes environments. This includes actions such as limiting allowed image sources, mitigating possible image tampering, and more.
	- Rules
		- Rules define and enforce security best practices tailored to your organization's objectives.
		- 


## Related Notes



## References