Tags: [[Authorization]], [[Authentication]], [[Security Controls]]

## What is it?

- Zero trust is a holistic approach to network security
- Covers every device, every process, every person or it isnt zero trust
- Everything must be verified
	- Nothing is inherently trusted
	- MFA, encryption, system permissions, firewalls, monitoring etc

## Additional Information

- #### ==PLANES OF OPERATION==
	- Split the network into functional planes
		- Data plane
			- process the frames, packets and network data
			- processing, forwarding, encrypting, NAT
		- Control plane
			- Manages the actions of the data plane
			- Define policies and rules
			- Determines how packets should be forwarded
			- Routing tables, session tables, NAT tables
	- Adaptive identity
		- Consider the source and the requested resources
		- Multiple risk indicators
			- Relationship to the org
			- Physical location
			- Type of connection
			- Local or external IP address
			- etc
		- Make the authentication stronger if needed
	- Threat scope reduction
		- decrease the number of possible entry points

- #### ==SECURITY ZONES==
	- Security is more than a one-to-one relation
	- Where are you coming from and where are you going
		- Trusted, untrusted
		- Internal network, external network
		- VPN 1, VPN 5 or VPN 11
		- Marketing, IT, Accounting, HR
		- etc
	- Using the zone may be enough by itself to deny access
	- some zones are implicitly trusted
		- For example, trusted to internal zone traffic

 - #### Policy-driven access control
	- Combine the adaptive identity with a predefined set of rules
	- ==Policy enforcement points (PEP)==
		- Subjects and systems: end users, apps, non-humans etc
		- Policy enforcer points: ==THE GATEKEEPER==
		- Allow, monitor and terminate connections
	- ==Policy Decision Point (PDP)==
		- Process for making an authentication decision
		- Policy Engine
			- Evaluates each access decision based on policy
		- Policy Administrator
			- Communicates with the Policy Enforcement Point (PEP)
			- Generates access tokens or creds
			- Tells the PEP to allow or disallow access

![[Pasted image 20260114110110.png]]

## Related Notes



## References