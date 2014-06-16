#Network Security

###Introduction

+ Safety Problems

+ Passive & Active Attacks

	- PDU
	
+ Intension

###Cryptology

+ DES(Slides: p14)

+ RSA(Slides: pp16-19)

+ Signature(Slides: pp22-25)

###Firewall

+ Trusted Network & Untrusted Network

+ Two main functions: Deny and Permit

+ ACL

	> ACL is a list of instructions that tells a router what type of packets to permit or deny.

	- Source address

	- Destination address

	- Upper Layer protocols
	
+ Configure(Basic ACL)

	- Write the ACL statements sequentially in global configuration mode

		> Router(config)#access-list access-list-number {permit/deny} {test-conditions}
	
	- Group the ACL to one or more interfaces in interface configuration mode
	
		> Router(config-if)#{protocol} access-group access-list-number {in/out}
		
		+ `access-list-number` types(Slides: p37)
		
		+ `permit` / `deny`
		
		+ `test-conditions`: ip mask and wildcard mask
		
			- `any` command: permit/deny any
			
			- `host`: particular host
			
+ Configure(Extended ACL)

	- Write the ACL statements sequentially in global configuration mode
	
		> Router(config)# access-list access-list-number {permit|deny} {protocol|protocol-keyword}{source source-wildcard} {destination destination-wildcard} [protocol-specific options] [log]

	- Group the ACL to one or more interfaces in interface configuration mode
	
		> Router(config-if)#{protocol} access-group access-list-number {in/out}
		
		+ `access-list-number`: 100-199
		
		+ `protocol | protocol-number`: `ip` and `tcp`
		
		+ Port Numbers
		
			- FTP: 21
			
			- Telnet: 23
			
			- SMTP: 25
			
			- DNS: 53
			
			- TFTP: 69
			
+ Configure(Naming and verifying)

	> show access-lists
	
	> show access-lists {name | number}
	
	> show ip interface
	
	> show running-config