# Project X: Design and implement IP networks

An enterprise has two building one at Casablanca and the second one at Rabat. The Casablanca building has n flours
( n = (X mod 2)+2 ) with 12 rooms each as depicted in the following figure. Each room will contain a double RJ45 outlet.

![image](https://user-images.githubusercontent.com/45466806/75111022-83a36380-5635-11ea-8e38-d098839a5d41.png)

For horizontal cabling, what is the length of UTP cat 6 cable (1 Gb/s) required for wiring a flour?
How much access points we need to cover the Casablanca building? (use 802.11n, suppose you have 70m as radius).
For vertical cabling, the engineer has chosen to use a multimode fiber (10 Gb/s). Suppose that the height’s flour is about 3m, what’s fiber length do we need for vertical cabling?

For switching, use a hierarchical model with two or three levels (Core/distribution and Access levels). 
Consider each flour as an independent VLAN:

```shell
-	VLAN name: Vlan-Flour1, VLAN numer:10, VLAN Network Address: 10.1.X.0/26
-	VLAN name: Vlan-Flour2, VLAN numer:20, VLAN Network Address: 10.2.X.0/26
-	VLAN name: Vlan-Flourn, VLAN numer:n0, VLAN Network Address: 10.n.X.0/26
```

In the first flour, two routers are deployed, one (Internal) for inter-VLAN routing and the second (Casablanca) connecting the enterprise to internet. The network address between the two routers is 9.X.1.0/29. Between these two routers a DMZ zone is deployed containing DNS and Web Servers. The DNS server address is 9.X.1.2/29 and the Web server address is 9.X.1.3/29.
The ip address of the serial interface of the Casablanca router is 9.X.2.6/30.

In Rabat, the network contains twenty PCs belonging to the network 10.10.X.0/27. 
The IP address of the serial interface of the Rabat router is 9.X.2.10/30.

```shell
1-	LAN
  -	Configure the core Switch as a VTP server and the others as VTP clients?
  -	Enforce the Core Switch to be the STP root bridge?
  -	Configure VLAN and Inter-Vlan Routing
  -	Between Internal and Casablanca routers, configure DNS and WEB servers.
  -	Configure a DHCP Server on the internal router to serve all Casablanca’s VLANs?
2-	WAN
  -	Configure static routes between Rabat, Casablanca and Internet routers?
  -	Consider Internet as composed from 3 Routers (Core, East, West), Configure a routing protocol?
  -	Configure PPP with CHAP between Rabat and Casablanca and Internet routers?
  -	Configure PAT on the Rabat and Casablanca routers?
3-	Security: Deploy the following security policies?
  -	Limit telnet access on Switchs and routers to the administrator Laptop (10.1.X.100/26)?
  -	Deny the VLAN-flour2 to access Internet?
  -	On the Casablanca router open only DNS and Web services to machines coming from Internet?
  -	Configure a VPN tunnel between Rabat and Casablanca sites?
```

Use packet tracer to implement this network architecture: 2 packet tracer files with and without VPN must be provided. A doc file must be provided summarizing your project (not more than 8 pages). Focus on Design and Financial aspects.
