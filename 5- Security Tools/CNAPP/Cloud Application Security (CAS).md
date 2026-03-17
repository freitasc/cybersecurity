Tags: [[Palo Alto]], [[Cloud]], [[CI CD]], [[IaC Scanning]], [[SCA]], [[SAST and DAST]]

## What is it?

- AKA Code Security
- Code security for applications focuses on identifying known vulnerabilities in source code, dependencies and open source packages.
## Additional Information

- IaC Security
	- Infrastructure as code is a modern technology and process in which infrastructure is provisioned and managed using machine-readable code files. 
	- Frameworks such as Terraform and CloudFormation allow teams to write declarative or imperative code files, check those files into their version control system and CI/CD pipeline, and then spin up the cloud resources across environments.
	- With IaC, one misconfiguration in a code file can lead to thousands of misconfigurations and alerts across cloud environments.
	- Code security solves this by surfacing security feedback earlier in the development lifecycle instead of taking a reactive approach.
- Web Application Security
	- The fundamentals still matter
		- input validation, authentication, session handling, and output encoding
	- But newer complexities demand attention.
		- Third-party scripts and client-heavy frameworks expand the attack surface beyond your origin server.
		- Legacy business logic — especially in multitenant applications — can bypass newer protections.
		- Misconfigured CSP, lax CORS settings, or improper session token storage can create gaps even in technically sound builds.
- API Security
	- APIs have replaced monoliths as the primary interface between systems, services, and users.
	- APIs rarely break from technical failure — they break from abuse.
		- Improper authorization logic — especially at the object level — remains a widespread flaw.
		- Overly verbose responses can leak structure, keys, or internal metadata.
		- Poor input handling allows deserialization attacks, injection, and abuse of nested query logic.
- Software Supply Chain Security
	- Software supply chains comprise application and infrastructure components as well as the underlying pipelines, including version control systems (VCS), continuous integration and continuous deployment (CI/CD) pipelines, and registries.
	- If a VCS isn’t securely configured, attackers may be able to merge malicious code or get access to exposed secrets that could lead to a larger attack.
	- If CI/CD pipelines are compromised, attackers can gain access to exposed credentials and tamper with code, which can result in downstream incidents.
	- Supply chain security best practices focus on hardening pipelines and configuring access controls and branch protections to restrict access as much as possible.
![[Pasted image 20260317125623.png]]

- SAST
	- Static application security testing (SAST) examines source code for potential security vulnerabilities without executing the program.
	- It's performed early in the development lifecycle, enabling developers to identify and remediate security flaws during coding. 
	- SAST tools analyze code against a set of predefined rules to detect issues like input validation errors, insecure dependencies, and other common vulnerabilities.
- DAST
	- Dynamic application security testing (DAST) assesses applications during runtime, simulating external attacks to identify vulnerabilities. 
	- Unlike SAST, DAST evaluates the application from an outsider's perspective, checking for issues like SQL injection, cross-site scripting, and other flaws exploitable without access to source code. 
	- DAST provides insights into real-world attack scenarios and the application's behavior in production.
- SCA
	- Software composition analysis (SCA) tools audit codebases for open-source components and their dependencies to identify known security vulnerabilities, licensing issues, and outdated libraries. 
	- SCA automates the process of tracking third-party software used in development, crucial for maintaining the security integrity of applications and adhering to compliance standards.
## Related Notes



## References

https://www.paloaltonetworks.ca/cyberpedia/what-is-code-security