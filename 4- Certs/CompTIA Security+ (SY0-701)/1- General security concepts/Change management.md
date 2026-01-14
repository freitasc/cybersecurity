Tags: [[Governance]], [[Risk-Management]], [[Disaster-Recovery]]

## What is it?

- How to make a change
	- Upgrade a software, patch an app, change firewall policies, merge code into main...
- One of the most common risks in the enterprise
- Often overlooked or ignored
- Have clear policies
	- Frequency, duration, processes, rollback procedures
- Sometimes extremely difficult to implement due to corporate culture

## Additional Information

- #### Change approval process
	- A formal process for managing change
	- A typical approval process
		- Complete the request forms
		- Determine the purpose of the change
		- Identify the scope of the change
		- Schedule a date and time of the change
		- Determine affected systems and the impact
		- Analyze the risk associated with the change
		- Get approval from the change control board
		- Get end-user acceptance
	- On the case of a github, it is easily done by implementing a gitflow policy and merge request templates that needs to be approved by other developers
	- ==DOCUMENT EVERY THING==

- #### Backout plan
	- The change will work perfectly 100% of times always right? ==NO IT WILL NOT DUMMY==
	- You should always have a way to revert changes and restore from a previous safer state
	- This isn't as easy as it sounds, some changes are difficult to revert

- #### Maintance window
	- When the change should happen?
		- This may be difficult, as you have to consider multiple variables
		- IT SHOULD BE:
			- During off-peak hours
			- During off-work hours
			- During system downtime
			- During days of the year of less traffic / usage
			- Overnights

- #### Ownership
	- If an individual or entity needs to make a change
		- They own the process
		- They don't (usually) perform the change themselves
	- The owner manages the process
		- Process updates are provided to the owner
		- Ensure the process is followed and accepted
	- Example: Address label printers needs to be upgraded
		- Shipping and receiving department owns the process
		- IT handles the actual change

- #### Stakeholders
	- Who is impacted by the change?
	- This may not be as obvious as you may think

- #### Impact analysis
	- Determine the risk value (high, medium, low)
	- The risks can be a minor or far-reaching
	- What's the risk with not making the change?
	- You can make a sandbox testing environment to test the impact before release
		- Great time to test your backout plan
	
## Related Notes



## References