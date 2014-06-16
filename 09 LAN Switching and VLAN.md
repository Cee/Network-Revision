#LAN Switching and VLAN

###Switch

+ Main Task

	- Building and maintaining switching tables
	
	- Switching frames out the interface to the destination
	
+ Switching

	- Symmetric: Provide switched connections between ports with the same bandwidth
	
	- Asymmetric: Require memory buffering
	
		+ Port-based memory buffering
		
		+ Shared memory buffering
		
+ Switching Methods

	- Store-and-Forward: receives the entire frame, calculating the CRC at the end, before sending it to the destination
	
	- Cut-through
		
		+ Fast forward switching: only checks the destination MAC  before immediately forwarding the frame
		
		+ Fragment Free: reads the first 64 bytes to reduce errors before forwarding the frame
		
+ Layer Switching

	- Layer 2: Data-Link
	
		+ Low cost
		
		+ Low latency
		
		+ High-speed
		
		+ Hardware-based bridging
		
		+ MAC address
		
	- Layer 3: Network
		
		+ Qos
		
		+ Security
		
		+ Flow accounting
		
		+ Low latency
		
		+ Low per-port cost
		
		+ High-speed scalability
		
		+ Hardware-based packet forwarding
		
	- Layer 4: Transport
	
		+ Based on Layer 3
		
		+ TCP/UDP Fields
		
		+ Qos
		
		+ Traffic control
		
	- Multilayer
	
		+ Low latency
		
		+ High-speed scalability
	
###The Spanning-Tree Protocol

+ Loops

	- Layer 2
	
		+ No TTL field
		
		+ Filp flop the bridging table entry
		
+ Overview of STP

	- Main function: allow redundant paths
	
	- Prevent loops: calculate a stable spanning-tree network
	
	- Spanning-tree frames(BPDU, Bridge Protocol Data Unit)
	
+ Decision Sequence

	- Lowest root BID(Bridge Identification)
	
		+ BID: 8bytes
		
			- Bridge priority(2 bytes): 0-65535 possible values
			
			- MAC address assigned to the switch(6 bytes)
				
	- Lowest path cost to root bridge
	
	- Lowest sender BID
	
	- Lowest port ID

+ STP cost values: lower costs are better
		
	- Bridges use the concept of cost to evaluate how close they are to other bridges
		
+ Electing the Root Switch
		
	- The switches elect a single root switch by looking for the switch with the lowest BID
			
	- If all the switches are using the default bridge priority of 32,768, the lowest MAC address serves as the tie-breaker
			
+ Five STP States
		
	- Blocking: frames forwarded, BPDUs heard
			
	- Listening: no frames forwarded, listening for data frames

	- Learning: no frames forwarded, learning addresses

	- Forwarding: frames forwarded, learning addresses

	- Disabled: no frames forwarded, no BPDUs heard

+ Initial STP Convergence

	- Root switch decision
	
		+ Announce itself as the root
		
		+ Checking all BPDUs received on the port
		
		+ Checking the value
	
	- Electing the root ports
	
		+ Every non-root bridge must select one root port
	
	- Electing the designated ports
	
		+ Every active port on the root bridge becomes a designated port
		
###VLAN

####Introduction of VLAN

+ Intro
	
	- Group users logically by function, department or application in use

	- Configuration is done through proprietary software
	
	- Work at Layer 2 & 3
	
	- Control network broadcasts
	
+ VLANs(IEEE 802.1q)

	- logical grouping of network devices, regardless of their physical segment location
	
	- creates a single broadcast domain
	
+ Group Users

	- port number

	- MAC address

	- protocol being used

	- application being used
	
####VLAN Architecture

+ Router's Role

	- A router provides connection between different VLANs
	
+ Frames Used in a VLAN(Slides: pp39-43)

	- Frame filtering
	
	- Frame tagging(Ethernet)
	
		+ IEEE 802.1Q
		
			- Encapsulation: No
			
			- Label: Yes
		
		+ ISL(Inter-Switch Link)
					
			- Encapsulation: Yes
			
			- Label: No

####VLAN Implementation

+ Static VLANs

	- Defined: Static VLANs are when ports on a switch are administratively assigned to a VLAN
	
	- Benefits
	
		+ secure, easy to configure and monitor
		
		+ works well in networks where moves are controlled

![Static VLANs]()

+ Dynamic VLANs

	- When a station is initially connected to an unassigned port, the switch checks an entry in the table and dynamically configures the port with the right VLAN
	
	- Benefits
	
		+ less administration (more upfront) when users are added or move

		+ centralized notification of unauthorized user

![Dynamic VLANs]()

+ Port-Centric VLANs

	- Benefits
	
		+ All nodes in the same VLAN are attached to the same router interface
		
		+ Users are assigned by router port

		+ VLANs are easy to admin

		+ Provides increased security

		+ Packets do not “leak” into other domains
		
![Port-Centric VLANs]()		

+ Access and Trunk Links

+ Configuration

	- Step1: A VLAN name may be configured
	
			Switch# vlan database
			Switch(vlan)# vlan vlan_number
			Switch(vlan)# exit

	- Step2: Assign the VLAN to one or more interfaces
	
			Switch(config)# interface fastethernet 0/9
			Switch(config-if)# switchport access vlan vlan_number
			
	- Verify
	
			Switch# show vlan [vlanid]
			
	- Delete
	
			Switch(vlan)# no vlan vlanid [name vlan-name]
			
####Routing Between VLANs 
	
+ Multiple Links

![Multiple Links]()

+ Trunk-Connected Routers

![Trunk-Connected Routers]()

+ Subinterfaces

![Subinterfaces]()

+ Configure

	- Step 1: Identify the interface
	
			Router(config)#interface fastethernet port-number. subinterface-number
	
	- Step 2: Define the VLAN encapsulation
	
			Router(config-if)#encapsulation 802.1q vlan-number
	
	- Step 3: Assign an IP address to the interface
	
			Router(config-if)#ip address ip-address subnet-mask
	