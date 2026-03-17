Tags: [[Palo Alto]], [[Cloud]], [[Posture]], [[Risk-Management]], [[Compliance]]

## What is it?

- The practice of controlling public cloud infrastructure risk.
- CSPM tools automate the detection and remediation of misconfigurations across cloud
	- (e.g., Amazon EC2 instances).
## Additional Information

- Cloud misconfigurations can lead to unwanted outcomes including data breaches or hefty fines for violating regulatory compliance.
- Multicloud Complexity
	- Each cloud provider offers different infrastructure architectures and taxonomy for security teams to learn and manage.
	- CSPM tools can detect, unify and normalize cloud provider services into a single console reducing complexity for security teams.
- Security Blind Spots
	- Organizations often find it challenging to achieve visibility into their cloud environments
	- With a CSPM tool, security teams get visibility into cloud resources, configuration changes, risks, compliance violations and more.
- Compliance Obligations
	- Many businesses adopting cloud infrastructure have regulatory compliance requirements mandating specific security measures
		- PCI DSS, GDPR, SOC 2, and HIPAA
	- CSPM tools can help businesses ensure that their cloud infrastructure meets these compliance requirements.
		- CSPM tools automatically compare cloud configurations against regulatory controls to detect compliance violations and provide remediation guidance.
- Poor Developer Experience
	- Security teams are perceived as slowing down modern DevOps style development.
	- CSPM tools can improve security and developer collaboration by prioritizing misconfigurations with context and augmenting remediation steps.

#### How Does CSPM Work?

![[Pasted image 20260317112808.png]]

- Connect to Your Cloud Environments
	- CSPM doesn't require agents
	-  CSPM solutions connect to your cloud providers APIs for visibility (agentless)
	- CSPM tools offer automated workflows, generating the permissions needed for effective posture management.

- Get visibility
	- CSPM tools come with policies that compare your cloud resources and configurations against security controls.
	- Typically, the policies will map to an industry best practice framework or regulatory compliance.
		- CIS, MITRE ATT&CK
		- PCI DSS, HIPAA
	- Anytime a configuration matches a defined policy, a CSPM solution will identify this as a misconfiguration and alert security teams.
	- Examples of Misconfigured Services
		- Amazon EC2 instance has IMDSv2 disabled
		- Azure Kubernetes Service endpoint is publicly accessible
		- GCP API key not rotating in every 90 days

- Detect Threats
	- With CSPM, security teams can detect compromises in action just by using the telemetry from your cloud providers such as network traffic, events
		- Amazon VPC flow logs
		- AWS CloudTrail event logs
	- Can work a lot like a SIEM tool
	- An effective CSPM must maintain high-fidelity threat intelligence to identify the latest threats and assess their severity level.

- Remediate Issues
	- At minimum, CSPM solutions provide step-by-step remediation instructions which security teams can forward to the teams responsible for the misconfiguration for improved collaboration.
	- CSPM solutions should integrate with external platforms like SIEM, SOAR, ticketing systems and collaboration tools
	- In some cases, security teams can automatically remediate violations from their CSPM console to facilitate rapid response.

![[Pasted image 20260317113703.png]]

- Monitor and Report
	- CSPM tools with built-in reporting capabilities help security teams verify their efforts and communicate with key stakeholders.
	- CSPM solutions offer the ability to produce easily consumable reports.



## Related Notes



## References

https://www.paloaltonetworks.ca/cyberpedia/what-is-cloud-security-posture-management