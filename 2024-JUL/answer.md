# AACS2034 JUL 2024 Answers

[Link to the paper](https://eprints.tarc.edu.my/29314/1/AACS2034.pdf)

- [Question 1](#question-1)
- [Question 2](#question-2)
- [Question 3](#question-3)
- [Question 4](#question-4)

### Question 1

a) IP subnetting is a process of segmenting a larger network into smaller subnetworks. Subnetting is important because it reduces the broadcast domain of a network, which improves network congestion issues. Smaller subnets are also more manageable and easier to enforce security policies.

b)

i) Subnet mask is a number sequence that helps to identify the network and host portions of an IP address.

ii) Network portion is the part of the IP address which identifies the network to which the host IP address belongs.

iii) Host portion is the part of the IP address which identifies the specific host within the network.

iv) Default gateway is the IP address of local the router interface that connects the local network to the outside world.

c) Yes. Similar functionality exists between MAC address and IP address. Both of the addresses are used to uniquely identify a device on a network. However, IP address is used to identify a host on network layer, while MAC address is used to identify a host on data link layer. IP address can be located outside the local network, while MAC address is only meaningful within the local network.

d) Network address is the first address in a subnet, which is used to identify the subnet itself. Host address is the address used to uniquely identify a host within the subnet. Broadcast address is the last address in a subnet, which is used to indicate that the packet should be sent to all hosts within the subnet.

e)

- Step 1: Convert IP Address and subnet mask /16 to binary
  - IP Address: 10101100.10101000.00010100.00000001
  - Subnet Mask: 11111111.11111111.00000000.00000000
- Step 2: Perform bitwise AND operation between IP Address and subnet mask
  - IP AND Subnet Mask: 10101100.10101000.00000000.00000000
- Step 3: Get the network address
  - Network Address: 10101100.10101000.00000000.00000000 = 172.168.0.0
- Step 4: Get the broadcast address
  - Broadcast Address: 10101100.10101000.11111111.11111111 = 172.168.255.255

### Question 2

a)

i) 191.0.168.20

- Address Class: B
- Default Subnet Mask: 255.255.0.0
- Network Portion: 191.0
- Host Portion: 168.20

ii) 172.29.135.10

- Address Class: B
- Default Subnet Mask: 255.255.0.0
- Network Portion: 172.29
- Host Portion: 135.10

iii) 126.255.255.255

- Address Class: A
- Default Subnet Mask: 255.0.0.0
- Network Portion: 126
- Host Portion: 255.255.255

b)

- Compared to dynamic IP address, static IP address is more reliable for devices that require consistent access so they can be easily reached, such as servers and network intermediary devices. On the other hand, dynamic IP address is more cost-effective and flexible for devices that do not require consistent access, such as personal computers.
- IPv4: `192.168.10.1`
- IPv6: `2000:2121:1212:4543::1`

c) DHCP is a protocol used to dynamically assign IP addresses to devices on a network.

- A newly connected device broadcasts a DHCP Discover message to find available DHCP servers on the network.
- The DHCP server responds with a DHCP Offer message, which includes a lease offer of an IP address.
- The device chooses a lease offer and sends a DHCP Request message to the server to accept the offer.
- The server acknowledges the request with a DHCP Acknowledgment message if the lease offer is still valid, otherwise it will send a DHCP Negative Acknowledgment message.

d)

- IPv4 address depletion
- Internet routing table expansion impacting routing performance
- NAT technique causes problems with end-to-end connectivity due to multiple devices sharing a single public IP address

### Question 3

a)

| Subnet Name               | Subnet Address | Prefix Length/ | First Usable   | Last Usable    | Broadcast Address |
| ------------------------- | -------------- | -------------- | -------------- | -------------- | ----------------- |
| Student Affair Department | 192.168.10.0   | /25            | 192.168.10.1   | 192.168.10.126 | 192.168.10.127    |
| Faculty of Computing      | 192.168.10.128 | /26            | 192.168.10.129 | 192.168.10.190 | 192.168.10.191    |
| Operation Department      | 192.168.10.192 | /27            | 192.168.10.193 | 192.168.10.222 | 192.168.10.223    |
| Management Department     | 192.168.10.224 | /28            | 192.168.10.225 | 192.168.10.238 | 192.168.10.239    |
| WAN                       | 192.168.10.240 | /30            | 192.168.10.241 | 192.168.10.242 | 192.168.10.243    |

b)

i)

- Rule 1: `2001:db8:0:0:0:ff00:42:8329 /64`
- Rule 2: `2001:db8::ff00:42:8329 /64`

ii)

- Rule 1: `FE80:0:0:0:202:B3FF:FE1E:8329 /64`
- Rule 2: `FE80::202:B3FF:FE1E:8329 /64`

c)

- Tunneling is a method of encapsulating an IPv6 packet within an IPv4 packet to transmit it over an IPv4 network.
- Translation is a method of using NAT64 to translate IPv6 packets to IPv4 packets and vice versa, allowing communication between IPv4 and IPv6 networks.
- Dual stack is a method of running both IPv4 and IPv6 protocols on the same device, allowing it to communicate with both IPv4 and IPv6 networks simultaneously.

### Question 4

a) DHCP in charge of assigning dynamic IP addresses to host addresses on a network. Those hosts will be able to access to the internet through the router. The hosts can use DNS to resolve domain names to IP addresses to communicate with web servers on the internet. With these 2 protocols, hosts are able to communicate with each other and access the internet.

b) No. Two devices should not have the same MAC address on the same network. MAC address should uniquely identify a device on the network so the frame can be delivered to the correct destination. If two devices have the same MAC address within a network, the network will not be able to determine which device should receive the frame, causing communication issues. However, it is possible for two devices to have the same MAC address on different networks, as MAC addresses are only meaningful within the local network.

c) I don't agree with this statement. This is because public networks doesn't requires authentication, making it vulnerable to malicious attacks such as data interception and unauthorized access, which makes it less safe than private networks. In addition, charging for network access can also contributes to the network traffic management and network maintenance, which can improve the overall network security.

d) Application is important in networking because it provides interfaces to users and applications to communicate with the network. It also enforces standards to ensure interoperability between different applications and devices. For example, application layer protocols such as HTTP, FTP, and SMTP define how web pages, files, and emails are formatted and interpreted, which allows different devices to communicate with each other effectively.

e) UDP does not establish a connection before sending data. The data are encapsulated with less overhead, which makes the datagram smaller and faster to transmit. After the datagram is sent, no acknowledgment is required from the receiver. This makes UDP suitable for applications that require low latency and can tolerate some data loss, such as video streaming and online gaming.
