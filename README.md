# NetPractice

## Content
- [What Is TCP/IP?](https://github.com/Mushigarou/NetPractice#what-is-tcpip)
- [Terminology]()
- [What TCP/IP Can be Used For?]()
- [TCP/IP Layers]()

## What Is TCP/IP?
The Transmission Control Protocol/Internet Protocol is a set of protocols (communication standards) that describe how two or more computers can communicate over a network.

## Terminology
- **Datagrams:** A packet of data passed across a network
- **Routing:** is the process of selecting a path for traffic in a network or between or across multiple networks
- **Encapsulation:** Arranging data into packets to be transmitted over computer networks
- **Deencapsulation:** is the reverse computer-networking process
- **Client:** a computer or a process that accesses data, resources, or services of another computer on the network
- **Host:** a computer that can communicate with other Internet hosts over the Internet network. Its Internet address and name identify it.
  - **Local host:** the computer at which the user is working
  - **Foreign host:** any other hostname on the network
- **Network:** A network is a collection of interconnected devices, systems, or components that can communicate and exchange data with each other (WAN, LAN...)
  - **Physical network:** the hardware that makes up the network (cables, servers, routers, switches...). The physical network must support and the implementation of the logical network for proper functioning
  - **Logical network:** is the virtual design, functional aspect of the network based on the organization's needs, in other words, it's the blueprint for implementing the physical network infrastructure (how systems are interconnected, routing protocols, IP addressing, logical network segmentation...)
- **Packet:** a block of data used by the process to receive and send data in one transaction between the host and its network
- **Port:** A logical endpoint that allows network protocols and services to communicate (send and receive data)
- **Protocol:** A set of rules for handling communications at the physical or logical level. A protocol can use another protocol to accomplish its mission
  
### What TCP/IP Can be Used For? (Non-Exhaustive List)
- Log in remotely
- Transfer emails
- Transfer files
- Manage Network

## TCP/IP Model

Layers                  | Short Explanation       | Protocols Examples  |
------------------------|-------------------------|---------------------|
Application layer       | Applications or processes create user data and communicate it on another or the same host (Make use of the Transport layer)                                            | SMTP, SSH, FTP, HTTPS, HTTP, DHCP...|
Transport layer         | Provides a channel for host-to-host communication on the same network or remote network separated by routers                                                              | TCP (connection-oriented), UDP (connectionless), SCTP (connection-oriented)...|
Internet layer          | Provides unreliable datagram transmission between hosts, and the IP (Primary Protocol) establishes the basis for internetworking. its function in routing is to transport datagrams to the next closer host (IP router) to the final destination.                                                                                                | IP(IPv4, IPv6), ICMP, IGMP...|
Link + Physical layer   | Defines the networking methods (protocols) within the scope of the local network link on which hosts communicate without intervening routers                       | Mac Address, Fiber, Wireless, Ethernet Cables... |

- Connection-oriented Protocol (TCP, SCTP...) :
  - requires both devices to be able to communicate with each other
  - TCP successfully makes the connection reliable by :
    - data arrives in-order
    - data has minimal errors (i.e., correctness)
    - No duplicate data
    - lost or discarded packets are resent
    - includes traffic congestion control

- Connectionless Protocol (UDP, HTTP, ICMP, IP...) :
  - A message is sent from one endpoint to another without a prior arrangement
  - Used for broadcast

## For More Information:
- [Wikipedia](https://en.wikipedia.org/wiki/Internet_protocol_suite)
- [IBM](https://www.ibm.com/docs/en/aix/7.2?topic=management-transmission-control-protocolinternet-protocol)
- [Requirements for Internet Hosts -- Communication Layers -- RFC-1123](https://datatracker.ietf.org/doc/html/rfc1122)
- [List of IP protocol numbers](https://en.wikipedia.org/wiki/List_of_IP_protocol_numbers)
