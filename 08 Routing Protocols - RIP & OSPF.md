08#Routing Protocols - RIP & OSPF

###RIPv1/RIPv2

+ RIP v1

	- Interior Gateway Protocol
	
		+ Distance Vector, 30 seconds
		
		+ Hop Count, max 15
		
	- Load Balancing
	
	- Limitations
	
		+ No subnet mask info. in updates
		
		+ Sends updates as broadcasts on 255.255.255.255
		
		+ No authentication
		
		+ Not support VLSM(Variable Length Subnet Masking) or Classless Interdomain Routing
		
	- Configure
	
			Router(config)# router rip
			Router(config-router)# network network-number
			
![Comparing RIPv1 and RIPv2]()

+ RIP v2

	- What's new
	
		+ Support use of classless routing
		
		+ Send subnet masks
		
		+ Support prefix routing
		
		+ Provide authentication
		
		+ Multicasts over the Class D address 224.0.0.9
		
	- Configure
	
			Router(config)# router rip
			Router(config-router)# version 2
			Router(config-router)# network network-number
			
	- Verify & Debug
	
			Router# show ip protocols
			Router# shwo ip route
			Router# debug ip rip
			Router# turn off all debugging
			
###OSPF(single area)

+ Preview

	- Open Shortest Path First is a **link-state** routing protocol
	
	- Become the preferred IGP protocol when compared with RIP
	
	- Use Metrics like bandwidth
	
+ Routing Infomation

	- Topological database
	
	- Apply the Dijkstra Shortest Path First(SPF) algorithm to build a SPF tree
	
	- Calculate best paths
	
+ Feature

	- Use a hierarchial design
	
+ Terminology(Slides: pp21-29)

	- Link: A physical connection between two network devices
	
	- Link-State: The status of a link between two routers, including  information about a router's interface and its relationship to neighbouring routers
	
	- Cost: The value assigned to a link

	> Rather than hops, link-state protocols assign a cost to a link, which is based on the bandwidth of the link.
	
	- Area: A collection of networks/routers having the same area ID, each router within an area has the same link-state information
	
	- Neighborship Database: A list of all the neighbors to which a router has established a bi-directional communication
	
	- Topology Database: A list of information about all other routers in the internetwork
	
	- Routing Table: Unique
	
	- DR(Designated Router) / BDR(Backup Designated Router)
	
+ OSPF Areas

	- Defined with 32 bits number
	
	- Area 0 / Area 0.0.0.0
	
	- Use a 2 level hierarchical model
	
	- All areas are required to connect to Area 0
	
+ OSPF Operations

	- Neighbour adjacencies
	
	- **Five Steps(Slides: pp31-36)**
	
		+ Set up the adjacency relationships
		
		+ Elect DR(Designated Router) and BDR(Backup Designated Router) (if needed)

		+ Discover the routes

		+ Choose appropriate routes

		+ Maintain the route information
		
	- Seven States: Init, 2Way, Ex Start, Exchange, Loading, Full
	
+ OSPF Packets

	- Hello
	
		+ Addressed to 224.0.0.5
		
		+ Sent every 10 seconds, broadcast multi-access and point-to-point
		+ NBMA networks(Nonbroadcast Multiple Access), default time is 30 seconds
	
	- Database Description(DBD)
	
	- Link-State Request(LSR)
	
	- Link-State Update(LSU)
	
	- Link-State Acknowledgement(LSAck)