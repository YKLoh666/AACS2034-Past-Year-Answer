## Table of Contents

- [IPv4 Addressing](#ipv4-addressing)
  - [Unicast, Broadcast, Multicast](#unicast-broadcast-multicast)
  - [Private vs Public IP Address](#private-vs-public-ip-address)
  - [Network Segmentation](#network-segmentation)
- [IPv6 Addressing](#ipv6-addressing)
  - [Migrating to IPv6](#migrating-to-ipv6)
  - [IPv6 Address Types](#ipv6-address-types)
- [Network Layer](#network-layer)
  - [Processes of the Network Layer](#processes-of-the-network-layer)
  - [Characteristics of Internet Protocol (IP)](#characteristics-of-internet-protocol-ip)
  - [IPv4 Packet Structure](#ipv4-packet-structure)
  - [Limitation of IPv4 Address](#limitation-of-ipv4-address)
  - [Advangtage IPv6 resolve the limitations](#advangtage-ipv6-resolve-the-limitations)
  - [IPv6 Packet Structure](#ipv6-packet-structure)
- [Transport Layer](#transport-layer)
  - [Responsibilities of the Transport Layer](#responsibilities-of-the-transport-layer)
  - [Transmission Control Protocol (TCP)](#transmission-control-protocol-tcp)
  - [TCP Header](#tcp-header)
  - [User Datagram Protocol (UDP)](#user-datagram-protocol-udp)
  - [UDP Header](#udp-header)
  - [Socket](#socket)
  - [Port Numbers](#port-numbers)
  - [TCP Connection Establishment](#tcp-connection-establishment)
  - [UDP Connection](#udp-connection)
- [Application Layer](#application-layer)
  - [Presentation Layer](#presentation-layer)
  - [Session Layer](#session-layer)
  - [Application Layer](#application-layer-1)

## IPv4 Addressing

- Subnet Mask: A 32-bit number that separates the network portion and the host portion of an IP address.
- 3 IP configurations:
  - IP Address: Unique address
  - Subnet Mask
  - Default Gateway: Local router interface IP address

### Unicast, Broadcast, Multicast

- Static IP Address: Commonly used for servers and network devices.
- Dynamic IP Address: Commonly used for end-user devices.
- Unicast: One source to one destination.
- Broadcast: One source to all devices in the network.
- Multicast: One source to a group of devices.

### Private vs Public IP Address

- Public IP Address: Globally routable between Internet Service Provider (ISP) routers.
- Private IP Address: Not routable on the Internet. Used for local networks.
  - Not unique globally.
- Network Address Translation (NAT): Translates private IP addresses to public IP addresses.
  - Allows multiple devices to share a single public IP address.
  - Used in home networks and small businesses.
- Special IPv4 Addresses:
  - Loopback Address: 127.0.0.0/8, tests local TCP/IP stack.
  - Link-Local Address: 169.254.0.0/16, self-assigned IP address when DHCP fails. (APIPA address)
- IANA (Internet Assigned Numbers Authority): Manages IP address space and assigns IP address blocks to ISPs.

### Network Segmentation

- Reason:
  - Improve performance by reducing broadcast traffic.
  - Enhance security by isolating sensitive data.
  - Easier to manage and enforce policies.

## IPv6 Addressing

- Why IPv6?
  - IPv4 address space depletion.
  - NAT issue (end-to-end connectivity).
  - Internet of Things (IoT) demands.

### Migrating to IPv6

- Dual-stack: Run both IPv4 and IPv6.
- Tunneling: Encapsulate IPv6 packets in IPv4 packets.
- Translation: Convert IPv4 packets to IPv6 packets and vice versa. (Network Address Translation 64)

### IPv6 Address Types

- Unicast: One-to-one communication.
- Multicast: One-to-many communication.
- Anycast: One-to-nearest communication.
- Types of IPv6 addresses:
  - Global Unicast Address (GUA): Globally unique, internet routable.
    - Global Routing Prefix: Network Portion
    - Subnet ID: Subnet Portion
    - Interface ID: Host Portion
  - Link-Local Address (LLA): Communication within the same link, not routable. (FE80::/10)
  - Unique Local Address (ULA): Private address, similar to IPv4 private addresses.
    - Can be used in limited number of networks.
    - Not globally routable or translated to global addresses.

## Network Layer

### Processes of the Network Layer

- Addressing of end devices.
- Encapsulation of data into packets.
- Routing of packets between devices.
- Decapsulation of packets at the destination.

### Characteristics of Internet Protocol (IP)

- Connectionless: No established connection before sending data.
- Best Effort Delivery: No guarantee of delivery, order, or error correction.
- Media Independent: Can run on any type of network media.
  - To overcome different max size of MTU (Maximum Transmission Unit), IP uses fragmentation (Only IPv4)

### IPv4 Packet Structure

- Version: Specify is version 4.
- Differentiated Services (DS): Priority of the packet on the network
- Time-to-Live (TTL): Lifetime of the packet by hop
- Protocol: Next level protocol
- Source and Destination IPv4 Addresses.

### Limitation of IPv4 Address

- IP Address depletion
- Internet routing table expansion
- Lack of end-to-end connectivity (NAT)

### Advangtage IPv6 resolve the limitations

- Increased address space
- Improved packet handling
- Eliminate needs of NAT
- Hierarchical network architecture (increase routing efficiency)
- Autoconfiguration of addresses

### IPv6 Packet Structure

- Version: 0110 = 6
- Traffic Class: DS in IPv4
- Flow Label: Used for QoS
- Payload Length: Length of the data
- Next Header: Protocol type
- Hop Limit: TTL in IPv4
- Source and Destination IPv6 Addresses.
- Extension Headers: Additional information for the packet.

## Transport Layer

### Responsibilities of the Transport Layer

- Track individual conversations
- Segmenting data
- Add header information
- Multiplexing

### Transmission Control Protocol (TCP)

- Number and track data segments
- Acknowledge received segments
- Retransmit unacknowledged segments
- Reassemble segments in the correct order
- Send at controlled rate

### TCP Header

- Source Port: Port number of the sender
- Destination Port: Port number of the receiver
- Sequence Number: Number of the first byte in the segment
- Acknowledgment Number: Number of the next byte expected
- Headers Length: Length of the TCP header
- Control Bits: Flags for connection management
- Window: Number of bytes the sender is willing to accept
- Checksum: Error detection
- Urgent Pointer: Indicates urgent data

### User Datagram Protocol (UDP)

- Connectionless
- Best Effort Delivery
- Less overhead than TCP
- No acknowledgment

### UDP Header

- Source Port: Port number of the sender
- Destination Port: Port number of the receiver
- Length: Length of the UDP header and data
- Checksum: Error detection

### Socket

- Combination of IP address and port number
- Used to identify a specific process on a device
- Socket Pair: Source IP address, source port, destination IP address, destination port

### Port Numbers

- Well-Known Ports: 0-1023 (HTTP, FTP, SSH, etc.)
- Registered Ports: 1024-49151 (Used by software applications)
- Dynamic/Private Ports: 49152-65535 (Used for dynamic allocation by applications)

| Port Number | Protocol    |
| ----------- | ----------- |
| 20          | FTP Data    |
| 21          | FTP Control |
| 22          | SSH         |
| 23          | Telnet      |
| 25          | SMTP        |
| 53          | DNS         |
| 67          | DHCP Server |
| 68          | DHCP Client |
| 80          | HTTP        |
| 110         | POP3        |
| 143         | IMAP        |
| 443         | HTTPS       |

### TCP Connection Establishment

- Three-way handshake:
  - SYN: Client sends a SYN packet to the server.
  - ACK-SYN: Server responds with an ACK and SYN packet.
  - ACK: Client sends an ACK packet to the server.
- Termination:
  - FIN: One side sends a FIN packet to terminate the connection.
  - ACK: The other side acknowledges the FIN packet.
  - FIN: The other side sends a FIN packet to terminate the connection.
  - ACK: The first side acknowledges the FIN packet.

### UDP Connection

- Client selects a port number from the dynamic range to connect to the server.

## Application Layer

### Presentation Layer

- Formats data to compatible format
- Compresses and decompresses data
- Encrypts and decrypts data

### Session Layer

- Create and maintain dialogue between applications
- Keep the session open, restart session if interrupted

### Application Layer

#### HTTP

- Hypertext Transfer Protocol
- Port 80, 443 (HTTPS)
- Communicate with Uniform Resource Locator (URL)
- Message Types:
  - GET: Request data from server
  - POST: Send data to server
  - PUT: Update data on server / Upload resource

#### Email Protocols

- SMTP: Simple Mail Transfer Protocol
  - Port 25
  - Send email from client to server
- POP3: Post Office Protocol
  - Port 110
  - Retrieve email from server to client
  - Download email to client
  - Delete email from server
- IMAP: Internet Message Access Protocol
  - Port 143
  - Retrieve email from server to client
  - Synchronize email between client and server
  - Keep email on server

#### Domain Name Service (DNS)

- Port 53
- Resolves domain names to IP addresses
- Hierarchical structure
- Top-Level Domains (TLDs): .com, .org, .net, etc.

#### DHCP

- Dynamic Host Configuration Protocol
- Port 67 (server), 68 (client)
- Assigns IP addresses to devices on the network
- DHCP Discover: Client sends a broadcast message to find a DHCP server.
- DHCP Offer: Server responds with an available IP address.
- DHCP Request: Client requests the offered IP address.
- DHCP Acknowledgment: Server acknowledges the request and assigns the IP address.
- Lease Time: Duration for which the IP address is valid.

#### FTP

- File Transfer Protocol
- Port 20 (data), 21 (control)
- Connect to port 21 to establish a control connection
- Data connection established on port 20
- Can pull or push files

#### Telnet

- Port 23
- Remote access to devices
- Unencrypted communication
- Replaced by SSH for secure communication

#### SSH

- Port 22
- Secure Shell
- Encrypted remote access to devices
- Requires authentication through username and password
