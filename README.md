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
- **Deencapsulation:** is the reverse computer-networking process.

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
Internet layer          | Provides unreliable datagram transmission between hosts, and the IP (Primary Protocol) establishes the basis for internetworking. its function in routing is to transport datagrams to the next closer host (IP router) to the final destination.                                                                    | IP(IPv4, IPv6), ICMP, IGMP...|
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
