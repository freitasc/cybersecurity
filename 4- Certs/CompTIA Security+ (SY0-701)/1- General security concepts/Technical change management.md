Tags: [[Change management]], [[Governance]], [[Risk-Management]]

## What is it?

- This are the people that put the change management process into action
- There is no such thing as a simple upgrade
	- Everything can (and probably will) have many moving parts
	- Separate events may be required
- Change management is often concerned with "what" needs to change and ==the Technical team is concerned with "how" to change it==
## Additional Information

- #### Example: ==Allow list vs Deny list==
	- Any app can be dangerous
	- Security policy can control app execution
	- Allow list
		- Nothing runs unless it's on the approved list
		- Very restrictive
	- Deny list
		- Everything runs unless it's on the blocked list
		- Very liberal
	- Inserting or removing something from either lists is a process that can cause serious disruption

- #### Restricted activities
	- The scope of a change is important
	- A change approval isn't permission to make any change
		- The change control approval is very specific in scope
	- The scope may need to be expanded during the change window
		- It's impossible to prepare for all outcomes

- #### Downtime
	- Services will be eventually unavailable
	- If possible, prevent any downtime
	- Minimize any downtime events
		- Should be part of the backout plane
	- Send emails and notify everyone

- #### Restarts
	- It's common to require a restart
	- Implement a new config
	- Reboot the OS, restart the power cycle, restart a service on linux etc

- #### Legacy apps
	- Very hard, sometimes impossible to upgrade/change
	- Some apps were here before you arrived
	- Often no longer supported by the developers
	- Fear of the unknown
		- Face your fears and document the monstrosity

- #### Dependencies
	- To complete A, you must complete B
	- Makes the scope of the change larger and sometimes the work time or downtime longer

- #### Version control
	- Track changes to a file or software
	- Infinite opportunities to manage versions
	- ==USE GIT DUMBASS==

- ## ==DOCUMENT EVERYTHING!!!!!==
## Related Notes



## References