Tags: [[Palo Alto]], [[Cloud]], [[Authorization]], [[Authentication]], [[Compliance]]

## What is it?

- AKA IAM for cloud
- Cloud infrastructure entitlement management (CIEM) is the process of managing identities and privileges in cloud environments.
- With CIEM solutions, security teams can manage cloud identities, entitlements, and enforce the principle of least-privileged access to cloud infrastructure and resources.

## Additional Information

- The following image is an example of a badly configured IAM on a cloud premise
- The number of identities in a cloud account multiplied by the number of entitlements each identity has makes for a massive attack surface.
![[output-onlinepngtools.png]]

## Why Is CIEM Important to Your Cloud Security Strategy?

- Traditional identity and access management (IAM) tools deliver access controls to static self-hosted or on-premises infrastructure. 
- As companies move to the cloud, the cloud infrastructure, services and applications they leverage become more ephemeral and dynamic than their on-premises environments.
- Cloud service providers provide unique, native, cloud-based controls to help businesses enforce granular IAM policy.
	- 81% of organizations report working with two or more public cloud providers. 
	- Because different cloud environments don’t natively integrate, companies employing a multicloud strategy find managing entitlements overwhelming. 

## What Are the Components of CIEM?

- Entitlement visibility
- Rightsizing permissions
- Advanced analytics
- Compliance.

CIEM garantee this by automatically scanning access control policies, rules and configurations to determine:
- Which entitlements exist.
- What each human or machine user can do based on those entitlements.
- Which human and machine users can access each cloud resource based on those entitlements.
After identifying an entitlement, CIEM tools assess it to determine whether the access privileges it grants are the least necessary for achieving a workload’s intended purpose. 
- Entitlement assessments performed by CIEM tools rely on advanced analytics powered by machine learning, along with user and entity behavior analytics (UEBA).
- CIEM tools can align entitlements with compliance requirements by automatically assessing whether entitlements conform with compliance needs.



 - The following image is the same previous example, but now properly configured
 - Using the least privilege model exponentially reduces the attack surface.
![[Pasted image 20260317135847.png]]

## How Is CIEM Used?

Example:
- A user requests SSH access to a production machine
- The user can request temporary SSH key pair access to perform the work.
- The security team grants the user’s request and prompts them to use an SSO provider to acquire the keys. 
- Once the user performs the required work, the resource access is revoked, and the user can’t access the machine with those keys again. 
- The security team knows the effective permissions of each user at all times, and they can compare permissions with the minimal requirements for each type of task.

## Related Notes



## References

https://www.paloaltonetworks.ca/cyberpedia/what-is-ciem