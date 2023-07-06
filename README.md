# NetPractice

<div id="top"></div>

## Content
- [What Is TCP/IP?](https://github.com/Mushigarou/NetPractice#what-is-tcpip)
- [Terminology](https://github.com/Mushigarou/NetPractice/tree/main#terminology)
- [What TCP/IP Can be Used For?](https://github.com/Mushigarou/NetPractice/tree/main#what-tcpip-can-be-used-for-non-exhaustive-list)
- [TCP/IP Model](https://github.com/Mushigarou/NetPractice/tree/main#tcpip-model)
- [IPv4 Subnetting](https://github.com/Mushigarou/NetPractice/tree/main#ipv4-subnetting)
  - [What is subnetting](https://github.com/Mushigarou/NetPractice/tree/main#what-is-subnetting) 
  - [How To Write A CheatSheet?](https://github.com/Mushigarou/NetPractice/tree/main#how-to-write-a-cheatsheet)
  - [How To Find The 7 Attributes of a Given IP Address?](https://github.com/Mushigarou/NetPractice/tree/main#how-to-find-the-7-attributes-of-a-given-ip-address)
  - [Tips For Solving The 7 Attributes Faster](https://github.com/Mushigarou/NetPractice/tree/main#tips-for-solving-the-7-attributes-faster)
  - [Subnetting In /17 - /24 Range](https://github.com/Mushigarou/NetPractice/tree/main#subnetting-in-17---24-range)
  - [Subnetting In /1 - /16 Range](https://github.com/Mushigarou/NetPractice/tree/main#subnetting-in-1---16-range)
- [Network Devices]()

## What Is TCP/IP?
:star: The Transmission Control Protocol/Internet Protocol is a set of protocols (communication standards) that describe how two or more computers can communicate over a network.

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
  - **Physical network:** the hardware that makes up the network (cables, servers, routers, switches...). The physical network must support the implementation of the logical network for proper functioning
  - **Logical network:** is the virtual design, functional aspect of the network based on the organization's needs, in other words, it's the blueprint for implementing the physical network infrastructure (how systems are interconnected, routing protocols, IP addressing, logical network segmentation...)
- **Packet:** a block of data used by the process to receive and send data in one transaction between the host and its network
- **Port:** A logical endpoint that allows network protocols and services to communicate (send and receive data)
- **Protocol:** A set of rules for handling communications at the physical or logical level. A protocol can use another protocol to accomplish its mission
  
### What TCP/IP Can be Used For? (Non-Exhaustive List)
- Log in remotely
- Transfer emails
- Transfer files
- Manage Network

<div align="right">
  <b><a href="#top">↥ back to top</a></b>
</div>

## TCP/IP Model

Layers                  | Short Explanation       | Protocols           |
------------------------|-------------------------|---------------------|
Application layer       | Applications or processes create user data and communicate it on another or the same host (Make use of the Transport layer)                                            | SMTP, SSH, FTP, HTTPS, HTTP, DHCP...|
Transport layer         | Provides a channel for host-to-host communication on the same network or remote network separated by routers                                                                   | TCP (connection-oriented), UDP (connectionless), SCTP (connection-oriented)...|
Internet layer          | Provides unreliable datagram transmission between hosts, and the IP (Primary Protocol) establishes the basis for internetworking. its function in routing is to transport datagrams to the next closer host (IP router) to the final destination.                                                                         | IP(IPv4, IPv6), ICMP, IGMP...|
Link + Physical layer   | Defines the networking methods (protocols) within the scope of the local network link on which hosts communicate without intervening routers                                 | Mac Address, Fiber, Wireless, Ethernet Cables... |

- ⭐ **Connection-oriented Protocol (TCP, SCTP...):**
  - requires both devices to be able to communicate with each other
  - TCP successfully makes the connection reliable by :
    - data arrives in-order
    - data has minimal errors (i.e., correctness)
    - No duplicate data
    - lost or discarded packets are resent
    - includes traffic congestion control

- ⭐ **Connectionless Protocol (UDP, HTTP, ICMP, IP...):**
  - A message is sent from one endpoint to another without a prior arrangement
  - Used for broadcast

<div align="right">
  <b><a href="#top">↥ back to top</a></b>
</div>

## IPv4 Subnetting 

### What Is Subnetting?

⭐ **Subnetting means dividing a network into sub-networks.** :star:

<img width="708" alt="Subnetting a network of 255 addresses" src="https://github.com/Mushigarou/NetPractice/blob/main/Images/Subnetting.png">


➡️ **Subnetting Attributes:**
- **Network ID:** The first IP address in the sub-network
- **Broadcast IP:** The last IP address in the sub-network
- **First host:** The first IP address after the sub-network ID
- **Last host:** The first IP address before the broadcast IP
- **Next Network:** The first IP address after the broadcast IP
- **# IP addresses:** Number of all available IP addresses in a sub-network
- **CIDR/Subnet:** Converting between CIDR/Subnet Mask

<div align="right">
  <b><a href="#top">↥ back to top</a></b>
</div>

### How To Write A CheatSheet?
1️⃣: Start with 1, double until you reach 128 (right to left)

2️⃣: Subtract the top row from 256

3️⃣: From /32, list CIDR notation  (right to left)


| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   | **Groupe Size** |
------|-----|-----|-----|-----|-----|-----|-----|------------------
| 128 | 192 | 224 | 240 | 248 | 252 | 254 | 255 | **Subnet**      |
| /25 | /26 | /27 | /28 | /29 | /30 | /31 | /32 | **CIDR**        |

### How To Find The 7 Attributes of a Given IP Address?
1️⃣ : Use the given CIDR/Mask and find
  - CIDR/subnet map to each other
  - Groupe size ==> IP Address
  - Start at .0 in the relevant octet
  - Increase by group size until you **PASS** target IP

2️⃣ : get Net ID ➡️ Next Network ➡️ BC IP ➡️ First Host ➡️ Last Host ➡️ IP addresses (Group Size)

![Solving subnetting for a target IP](https://github.com/Mushigarou/NetPractice/blob/main/Images/Subnetting_Attribute.png)

### Tips For Solving The 7 Attributes Faster

🎯: Group size can be multiplied to get quickly to the subnet of the targeted IP address

🎯: Every group size lands on 128 at some point

🎯: **Each group size aligns with the subnet value** in the **corresponding column** with each subsequent column **to the left**.

🎯: Start higher, and subtract

<div align="right">
  <b><a href="#top">↥ back to top</a></b>
</div>

### Subnetting In /17 - /24 Range
- **To get the CIDR notation of the 3rd octet**

  *💡: Start over from the **right side** and keep **decrementing***
  
  *💡: **Total of IP Addresses = 2 ^ (32 - CIDR)***

| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   | **Groupe Size** |
------|-----|-----|-----|-----|-----|-----|-----|------------------
| 128 | 192 | 224 | 240 | 248 | 252 | 254 | 255 | **Subnet**      |
| /25 | /26 | /27 | /28 | /29 | /30 | /31 | /32 | **CIDR**        |
| /17 | /18 | /19 | /20 | /21 | /22 | /23 | /24 | **3rd Octet**  |

#### Example:

|  **Subnetting Attributes** |➡️ **of 10.4.235.99 /21:**            | ➡️ ** of 10.4.211.66 /18:** |
-----------------------------|--------------------------------------|----------------------------  |
**Network ID:** |   10.4.232.0 [3rd Octet => .224 => .232]  | 10.4.192.0 [3rd Octet : .128 => .192 => .0]  |
**Broadcast IP:**| 10.4.239.255                                      | 10.4.255.255                                   |
**First host:** |  10.4.232.1                                        |  10.4.192.1                                      |
**Last host:** |  10.4.239.254                                       |  10.4.255.254                                    |
**Next Network:** | 10.4.240.0                                       |  10.5.0.0                                     |
**# Total IP addresses:** | 2048     [32 - 21 = 11 & 2 ^ 11]  |   16,384         [32-18 = 14 & 2 ^ 14 = ]      |
**CIDR/Subnet:** |   255.255.248.0                                   |  255.255.192.0  |

<div align="right">
  <b><a href="#top">↥ back to top</a></b>
</div>

### Subnetting In /1 - /16 Range

- **To get the CIDR notation of the 3rd octet**

  *💡: Start over from the **right side** and keep **decrementing***
  
  *💡: **Total of IP Addresses = 2 ^ (32 - CIDR)***

| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   | **Groupe Size** |
------|-----|-----|-----|-----|-----|-----|-----|------------------
| 128 | 192 | 224 | 240 | 248 | 252 | 254 | 255 | **Subnet**      |
| /25 | /26 | /27 | /28 | /29 | /30 | /31 | /32 | **4th Octet**   |
| /17 | /18 | /19 | /20 | /21 | /22 | /23 | /24 | **3rd Octet**   |
| /9 | /10  | /11 | /12 | /13 | /14 | /15 | /16 | **2nd Octet**   |
| /1 | /2   | /3  | /4  | /5  | /6  | /7  | /8  | **1st Octet**   |

💡: *0.0.0.0 /0 is commonly used in the routing table as the default route or default gateway*

#### Example:

|  **Subnetting Attributes** |➡️ **of 10.50.111.222 /12:**   | ➡️ ** of 10.50.111.222 /7:** | ➡️ ** of 213.50.111.222 /2:**    |
-----------------------------|-------------------------------|----------------------------  |---------------------------------|
**Network ID:**              | 10.48.0.0 [.48 => .64 ]       | 10.0.0.0 [.8 => .10 => .12]  | 192.0.0.0 [.128 => .192 => .0]  |
**Broadcast IP:**            | 10.63.255.255                 | 11.255.255.255               | 255.255.255.255                 |
**First host:**              | 10.48.0.1                     | 10.0.0.1                     | 192.0.0.1                       | 
**Last host:**               | 10.64.255.254                 | 11.255.255.254               | 255.255.255.254                 |
**Next Network:**            | 10.64.0.0                     | 12.0.0.0                     | **n/a**                                                                                                                [No leading octet, we're at end of IPv4 addresses]  |
**# Total IP addresses:**    | 1,048,576    [2 ^ (32-12)]    | 33,554,432  [2^(32-7)]       | 1,073,741,824                   |
**CIDR/Subnet:**             | 255.240.0.0                   |  254.0.0.0                   | 192.0.0.0                       | 

*💡: **In reality most of the last /2 addresses are unassignable as host addresses***
![Entire IPv4 addresses](https://github.com/Mushigarou/NetPractice/blob/main/Images/Entire_IPv4.png)

## Network Devices
### How Data Flows Through The Internet
#### Hosts :
⭐ *Any system that sends or receives traffic.*
  - phone
  - computer
  - laptop
  - servers
  - cloud servers
  - Internet of Things (IoT) (speaker, refrigerator...)

⭐ **Client:** initiates request. **Servers** respond. (Relative to specific communication)

#### IP Addresses :

⭐ *IP Address is the identity of each host*
  - IPv4 is 32bit
  - Hierarchically assigned

![IP addresses](https://github.com/Mushigarou/NetPractice/blob/main/Images/ip_addresses.png)

💡 : all of those hosts above exist in a network

#### Network :
⭐ Network is what **transports traffic between hosts**
  - Logical grouping of hosts which require similar connectivity
  - Subnetworks, subnet
  - 💡 Networks connect to other networks (The Internet is simply an inter-connected network)

<div align="right">
  <b><a href="#top">↥ back to top</a></b>
</div>

## For More Information:
- [Wikipedia](https://en.wikipedia.org/wiki/Internet_protocol_suite)
- [IBM](https://www.ibm.com/docs/en/aix/7.2?topic=management-transmission-control-protocolinternet-protocol)
- [Requirements for Internet Hosts -- Communication Layers -- RFC-1123](https://datatracker.ietf.org/doc/html/rfc1122)
- [List of IP protocol numbers](https://en.wikipedia.org/wiki/List_of_IP_protocol_numbers)
- 📺 [**Video series by Practical Networking on Youtube**](https://subnetipv4.com/)
