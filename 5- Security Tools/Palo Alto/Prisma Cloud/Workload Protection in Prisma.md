Tags: [[Cloud]], [[Container]], [[Hardening]]

## What is it?

- Protecting containers, clusters, VMs, databases etc

## Additional Information

- It comes in 2 formats
- Agentless and Agent-based (defender)

| **Agentless**                                                                                                                                                                   | **Agents (Defenders)**                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Simplified visibility into vulnerability and compliance                                                                                                                         | Continuous, real-time runtime protection                                                                                                                          |
| **Distributed Access -** For distributed environments across different teams, gettings access to deploy agents is difficult                                                     | **Defense in Depth -** For sensitive workloads, deploy defenders/agents to gain deep insights into running processes, runtime forensics, behavioral analysis etc. |
| **First step in securing -** start with agentless security as soon as you on board accounts for first look into all hosts without need for running deployment scripts per hosts | **Advanced security with active prevention -** Actively prevent access to sensitive file systems or malware from being deployed with block capabilities           |
| **No running management -** Agentless uses snapshot based scanning, with no running tools inside your environment to manage                                                     | **Continuous monitoring -** For instances where you require continuous and immediate alerts                                                                       |

#### Agentless

- When scanning is initiated, it creates a snapshot of the cloud instance, then a M5.2xlarge scanner instance is created.
- After scanning is finished, both the snapshot and the M5.2xlarge are deleted
- If a scan fails, PC re-tries to scan the same unlimited amount of times
- If the agentless scanning is deployed into a cloud instance that has an agent installed, it will automatically detect the Defender agent and skip any EC2's with Defender running.
- It generates visibility of both the container images and the full VM instances
- It usually runs every 24hs
- You can request on demand scans
- You can request a scan on only specific workloads
- It scans the VM fully and report any workloads detected, even shadow workloads not enlisted into the assets inventory
- It also runs the VM and its workloads against rules and policies based on compliance and custom made
- It can do Web-Application and API security by monitoring the traffic for remote applications with no latency cost
	- The reason for this is that it is "Out-of-Band", the traffic doesn't pass through Prisma
	- Prisma instead only "sees" the traffic and send alerts to the console.
	- This way, Prisma CANNOT control the traffic, it is passive reconnaissance

#### Agent-based (Defender)

- It does everything agentless does, except it doesn't scan 3rd party packages by design (increasing the risk of supply chain attack)
- It is best practice to automate the defender deployment.
	- Everything (serverless, server, host..)
	- Openshift
	- GKE Autopilot
	- K8’s
	- Terraform and Kubernetes:
	- Defender baked in AMI
	- Fargate
- After each upgrade on the console, the defender clients must be upgraded as well.
	- It is recommended to automate the defender deployment process.
	- If the customer has an automation process for the container deployment, the customer should integrate the defender deployment process into the existing pipeline process.
	- Defender deployment can be automated with API calls.
- The agents can scan container images in public and private repositories on public and private registries
- When you conﬁgure Prisma Cloud to scan a registry, you can select the scope of defenders.
- In agent-based mode, Prisma can do Web-Application and API security by monitoring the traffic in a In-Line mode
	- This means that the traffic will pass through the Defender
	- It can impact the the latency, but also gives Defender power to respond to threats in real time
	- In-Line mode, defenders can operate as a transparent HTTP proxy and inspect and control the traffic to the applications

## Related Notes



## References