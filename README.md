<h1>WAN Configuration & Layer 1 and 3 Troubleshooting</h1>

<h2>Objective</h2>
Create a WAN with three subnets, configure IP addresses on each interface connected with its neighboring router and route, and troubleshooting using the OSI Model with layers, Layer 1 (Physical Layer) and Layer 3 (Network Layer) to communicate from one end of the router to the other end of the router.

<h2>Important Commands Used for Configuration and Troubleshooting</h2>
-	Traceroute <br>
-	Ping <br>
-	IP Route <br>
-	IP Address <br>
-	No Shutdown <br>

<h2>Program</h2>
<p align="center">
<img src="https://i.imgur.com/I9rDcb6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
From this network diagram, we want R1 to communicate with R4.

<p align="center">
<img src="https://i.imgur.com/SlKZVpo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
R1 can’t reach R4 so what can we do? We can use the traceroute command to see where the communication sent out from R1 stops before reaching R4 and view R1’s current configuration.
<p align="center">
<img src="https://i.imgur.com/hvkoQhq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<p align="center">
<img src="https://i.imgur.com/O0jLhhb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Based on the result from traceroute and the current configuration, an IP address and route has not been set up for it to communicate with R4, so let’s set up the IP address on the interface connected with R2 based on the diagram and route so it can start communicating. Assuming that the rest of the interfaces and route on each router have not been configured, we will set them up as well. Note that the routes must be configured on each router on both directions since there are three subnets.

<p align="center">
<img src="https://i.imgur.com/9EjMzNg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p align="center">
<img src="https://i.imgur.com/SqGrOYu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Now that R1’s interface connected with R2 is now set up and able to communicate with it and assuming that all the other interfaces and route on each router has been configured as well, let’s have R1 communicate with R4.

<p align="center">
<img src="https://i.imgur.com/Zp3CaHc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
It seems that R1 can’t communicate with R4, what could be the problem? Let’s use traceroute to discover where the packet stopped throughout its travel to R4.

<p align="center">
<img src="https://i.imgur.com/N9mHAcr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
It seemed that the packet stopped at R3, so let’s see the configuration on R3.

<p align="center">
<img src="https://i.imgur.com/xCVFD5A.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
The configuration on R3 has been properly configured. Let’s check on R4.

<p align="center">
<img src="https://i.imgur.com/dyq1Nea.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
The interface on R4 connecting to R3 is shutdown, so let’s reverse that and have R1 ping with R4 to check again.

<p align="center">
Layer 2 Network Diagram: <br/>
<img src="https://i.imgur.com/c8JkTRP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
R1 successfully pinged R4.
