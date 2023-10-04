# Computer Networking

Computer Networking is the practice of connecting computers together to enable communication and data exchange between them. 

In general, Computer Network is a collection of two or more computers. It helps users to communicate more easily.

Concept of layering: OSI and TCP/IP Protocol Stacks;
 Basics of packet, circuit and virtual
circuit-switching;

Data link layer: framing, error detection, Medium Access Control, Ethernet bridging;

Routing protocols: shortest path, flooding, distance vector and link state routing;

Fragmentation and IP addressing, IPv4, CIDR notation, Basics of IP support protocols (ARP,
DHCP, ICMP), Network Address Translation (NAT);

 Transport layer: flow control and
congestion control, UDP, TCP, sockets;

Application layer protocols: DNS, SMTP, HTTP, FTP,
Email.

## OSI Model
- Application Layer
- Presentation Layer
- Session Layer
- Transport Layer
- Network Layer
- Data-Link Layer
- Physical Layer

## Application Layer
### Protocols in Application layer
- TELNET
    - It allows Telnet clients to access the resources of the Telnet server. It is used for managing files on the internet. It is used for the initial setup of devices like switches.
    - Port Number - 23
- [FTP](https://www.geeksforgeeks.org/file-transfer-protocol-ftp-in-application-layer/)
- TFTP [Trivial FTP]
    - It’s a technology for transferring files between network devices and is a simplified version of FTP.
    - Port Number - 69
- NFS [Network File System]
    - It allows remote hosts to mount file systems over a network and interact with those file systems as though they are mounted locally.
    - Port Number 2049
- [SMTP](https://www.geeksforgeeks.org/simple-mail-transfer-protocol-smtp/)
- POP
- IMAP
- SNMP [Simple Network Management Protocol]

    There are 3 components of SNMP: 
    - SNMP Manager – It is a centralized system used to monitor network. It is also known as Network Management Station (NMS) 
    - SNMP agent – It is a software management software module installed on a managed device. Managed devices can be network devices like PC, routers, switches, servers, etc. 
    - Management Information Base – MIB consists of information on resources that are to be managed. This information is organized hierarchically. It consists of objects instances which are essentially variables. 
- DNS
- DHCP
- HTTP/HTTPS
- MIME

## DNS
Domain Name System (DNS) is a hostname for IP address translation service. DNS is a distributed database implemented in a hierarchy of name servers. It is an application layer protocol for message exchange between clients and servers. It is required for the functioning of the Internet.

It is basically some sort of infrastructure that helps clients to connect to servers and retrieve IP address of the required IP address by the client for whichever domain the client wants to connect.

### Organization of Domain
It is very difficult to find out the IP address associated with a website because there are millions of websites and with all those websites we should be able to generate the IP address immediately, there should not be a lot of delays for that to happen organization of the database is very important.

![](https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2017/02/DNS.png)

Example:
![](https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2017/02/DNS_2.png)

BEST PICTURE FOR DNS RESOLUTION

![](https://media.geeksforgeeks.org/wp-content/uploads/20230731154431/How-DNS-Works-gif-(1).gif)

We have 13 root servers located strategically around the world.
op Level Domain) server looking at .com, .org, .net, then it forwards to respective Authoritative server.

Authoritative servers are knon to have all the information of all the IP addresses and the domains.


Authoritative DNS Server Vs Recursive DNS Resolver
Parameters|Authoritative DNS Server|Recursive DNS Resolver
|-|-|-
Function|Holds the official DNS records for a domain|Resolves DNS queries on behalf of clients
Role|Provides answers to specific DNS queries|Actively looks up information for clients
Query Handling|Responds with authoritative DNS data|Queries other DNS servers for DNS data
Client Interaction|Doesn’t directly interact with end-users|Serves end-users or client applications
Data Source|Stores the DNS records for specific domains|Looks up data from other DNS servers
Caching|Generally, doesn’t perform caching|Caches DNS responses for faster lookups
Hierarchical Resolution|Does not participate in the recursive resolution|Actively performs recursive name resolution
IP Address|Has a fixed, known IP address|IP address may vary depending on ISP
Zone Authority|Manages a specific DNS zone (domain)|Does not manage any specific DNS zone

DNS uses UDP instead of TCP
- faster
- DNS requests very small so they fit in UDP segments
- not reliable but can be taken care of using time outs in application layer. 

Property|Iterative Resolution |Recursive Resolution
|-|-|-
Server Response |Returns the best match or a referral |Returns the requested mapping or an error message
Query Propagation |Each server that does not know the mapping sends the IP address of the next server |Only the local server sends the query to the next server
Server Load |Higher load on servers since each server in the chain must be queried |Lower load on servers since only the local server is queried
Response Time |Longer response time since multiple servers may need to be queried |Shorter response time since only one or a few servers are queried
Cache Usage |Lower cache hit rate since referrals are returned instead of mappings |Higher cache hit rate since mappings are returned directly
Security |Lower security since each server in the chain may potentially modify the response |Higher security since only the local server is trusted to return a valid response

Types of Attacks:  
- Denial of service (DoS): An attack where the attacker renders a computer useless (inaccessible) to the user by making a resource unavailable or by flooding the system with traffic.
- Distributed denial of service (DDoS): The attacker controls an overwhelming amount of computers (hundreds or thousands) in order to spread malware and flood the victim’s computer with unnecessary and overloading traffic. Eventually, unable to harness the power necessary to handle the intensive processing, the systems will overload and crash.
- DNS spoofing (also known as DNS cache poisoning): An attacker will drive the traffic away from real DNS servers and redirect them to a “pirate” server, unbeknownst to the users. This may cause the corruption/theft of a user’s personal data.
- Fast flux: An attacker will typically spoof his IP address while performing an attack. Fast flux is a technique to constantly change location-based data in order to hide where exactly the attack is coming from. This will mask the attacker’s real location, giving him the time needed to exploit the attack. Flux can be single or double or of any other variant. A single flux changes the address of the webserver while double flux changes both the address of the web server and the names of DNS serves.
- Reflected attacks: Attackers will send thousands of queries while spoofing their own IP address and using the victim’s source address. When these queries are answered, they will all be redirected to the victim himself.
- Reflective amplification DoS: When the size of the answer is considerably larger than the query itself, a flux is triggered, causing an amplification effect. This generally uses the same method as a reflected attack, but this attack will overwhelm the user’s system’s infrastructure further.

Measures against DNS attacks:  
- Use digital signatures and certificates to authenticate sessions in order to protect private data.
- Update regularly and use the latest software versions, such as BIND. BIND is open-source software that resolves DNS queries for users. It is widely used by a good majority of the DNS servers on the Internet.
- Install appropriate patches and fix faulty bugs regularly.
- Replicate data in a few other servers, so that if data is corrupted/lost in one server, it can be recovered from the others. This could also prevent single-point failure.
- Block redundant queries in order to prevent spoofing.
- Limit the number of possible queries.


HTTP|HTTPS
|-|-
HTTP stands for HyperText Transfer Protocol. In HTTP, the URL begins with “http://”. |HTTPS stands for HyperText Transfer Protocol Secure. In HTTPS, the URL starts with “https://”.
HTTP uses port number 80 for communication.|HTTPS uses port number 443 for communication.
Hyper-text exchanged using HTTP goes as plain text i.e. anyone between the browser and server can read it relatively easily if one intercepts this exchange of data and due to which it is Insecure.|HTTPS is considered to be secure but at the cost of processing time because Web Server and Web Browser need to exchange encryption keys using Certificates before actual data can be transferred.
HTTP Works at the Application Layer.|HTTPS works at Transport Layer.
HTTP does not use encryption, which results in low security in comparison to HTTPS.|HTTPS uses Encryption which results in better security than HTTP.
HTTP speed is faster than HTTPS.|HTTPS speed is slower than HTTP.
HTTP does not use data hashtags to secure data.|HTTPS will have the data before sending it and returning it to its original state on the receiver side.
HTTP is used to transfer text, video, and images via web pages.|HTTPS is used to transfer data securely via a network.

Persistent HTTP|Non-Persistent HTTP
|-|-
The server leaves the connection open after sending a response.|Requires 2 RTTs per object.
Subsequent HTTP messages between the same client/server are sent over an open connection.|OS overhead for each TCP connection
The client sends requests as soon as it encounters a referenced object.|Browsers often open parallel TCP connections to fetch referenced objects.
As little as one RTT for all the referenced objects.|Here, at most one object can be sent over one TCP Connection.

![](https://media.geeksforgeeks.org/wp-content/uploads/20230321165105/Non-Persistent-&-Parallel-Connections.png)

![](https://media.geeksforgeeks.org/wp-content/uploads/20230321164838/Persistent-&-Pipelined-Non-Pipelined-Connection.jpg)

# Transport Layer Protocol

TCP 3-Way Handshake Process
- Step 1 (SYN): In the first step, the client wants to establish a connection with a server, so it sends a segment with SYN(Synchronize Sequence Number) which informs the server that the client is likely to start communication and with what sequence number it starts segments with
- Step 2 (SYN + ACK): Server responds to the client request with SYN-ACK signal bits set. Acknowledgement(ACK) signifies the response of the segment it received and SYN signifies with what sequence number it is likely to start the segments with
- Step 3 (ACK): In the final part client acknowledges the response of the server and they both establish a reliable connection with which they will start the actual data transfer

![](https://media.geeksforgeeks.org/wp-content/uploads/handshake-1.png)


![](https://media.geeksforgeeks.org/wp-content/uploads/net.png)

TCP uses 4 timers 
- Retransmission Timer (RTT)
    A segment is retransmitted if RTO timer runs out before recieving Acknoledgement
    - Measured (RTTm)
    - Smoothed (RTTs)
- Deviated
- Persistent
    - When there are too many unacknowledged packets on the network, congestion happens.
    - This is where PT temporarily holds back new transmission until previously sent packages are acknowledged
- Keep Alive Timer
    - used to detect inactive connections
- Time wait timer

TCP can release connections 2 types of ways
- Graceful release
    - similar mechanism as SYN and ACK, but with FIN
- Abrupt release
    - RST segment is sent to close connection when a non-existent header is recieved

When all the sequence numbers are used up, we can reuse the already closed ones. This is called wrap around concept.

Wrap Around Time
$$= (Total sequence number) / (Bandwidth)$$
$$= (2^{32}) / (Bandwidth)$$

Wrap around around time should always be > Life time


How to reduce Wrap around time
- Reduce the sequence numbers or 
- Increase the bandwidth (possible) 

## Responsibilities of a Transport Layer
- The Process to Process Delivery
    ![](https://media.geeksforgeeks.org/wp-content/uploads/20230502004748/image-289.png)
- End-to-End Connection between Hosts
![](https://media.geeksforgeeks.org/wp-content/uploads/20230502004913/EotE.png)
- Multiplexing and Demultiplexing
- Congestion Control
- Data integrity and Error correction
- Flow control

### Protocols of TCP
- [TCP](https://www.geeksforgeeks.org/what-is-transmission-control-protocol-tcp/)
- [UDP](https://www.geeksforgeeks.org/user-datagram-protocol-udp/)
- [SCTP](https://www.geeksforgeeks.org/sctp-full-form/)
- [DCCP](https://www.geeksforgeeks.org/what-is-dccp-datagram-congestion-control-protocol/)
- [ATP](https://www.geeksforgeeks.org/what-is-atp-appletalk-transaction-protocol/)
- [FCP](https://www.geeksforgeeks.org/fcp-fibre-channel-protocol/)
- [RDP](https://www.geeksforgeeks.org/principle-of-reliable-data-transfer-protocol/)
- [RUDP](https://www.geeksforgeeks.org/reliable-user-datagram-protocol-rudp/)
- [SST](https://www.geeksforgeeks.org/what-is-sst-structured-steam-transport/)
- [SPX](https://www.geeksforgeeks.org/what-is-spx-sequenced-packet-exchange/)

# Go through ⬆️ those