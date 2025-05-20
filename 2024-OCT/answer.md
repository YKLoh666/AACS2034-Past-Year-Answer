# AACS2034 OCT 2024 Answers

[Link to the paper](https://eprints.tarc.edu.my/30253/1/QP-AACS2034.pdf)

- [Question 1](#question-1)
- [Question 2](#question-2)
- [Question 3](#question-3)
- [Question 4](#question-4)

## Answers

### Question 1

a)

i)

- Addressing of end devices
- Encapsulation
- Routing
- Decapsulation

ii)

- Each end devices need to be uniquely identified with an address so the packets can be sent to the correct destination.
- IP header information such as source and destination IP address are added to the segment or datagram to allow the packet to be identified its source and destination.
- Routing is the process of forwarding packets from one network to another, choosing the best path for the packet to reach its destination.
- Decapsulation removes the IP header information to retrieve the segment or datagram at the destination end device.

b) Yes. It is because IP is a connectionless protocol, hence it does not guarantee the delivery of packets. The packets may be lost, duplicated, delayed, or delivered out of order due to network congestion or failures. It also does not provide error correction or recovery mechanisms, the data transmitted may be corrupted or incomplete, requiring higher-level protocols to handle these issues.

c)

i) 5 subnets

ii)

- Directly Connected Routes

| Network Address | Subnet Mask     |
| --------------- | --------------- |
| 192.168.100.128 | 255.255.255.192 |
| 192.168.100.192 | 255.255.255.224 |
| 192.168.100.240 | 255.255.255.252 |

- Remote Routes

| Network Address | Subnet Mask     |
| --------------- | --------------- |
| 192.168.100.0   | 255.255.255.128 |
| 192.168.100.224 | 255.255.255.240 |

iii)

| Hop | Layer 2 Source Address | Layer 2 Destination Address | Layer 3 Source Address | Layer 3 Destination Address |
| --- | ---------------------- | --------------------------- | ---------------------- | --------------------------- |
| 1   | 0001:1234:FF01         | 0001:2234:FEF1              | 192.168.100.200        | 192.168.100.226             |
| 2   | 0001:2234:FEF3         | 0001:2224:FEF3              | 192.168.100.200        | 192.168.100.226             |
| 3   | 0001:2224:FEF2         | 0001:2234:FF10              | 192.168.100.200        | 192.168.100.226             |

### Question 2

a)

|                   | Class B                       | Class C                         |
| ----------------- | ----------------------------- | ------------------------------- |
| Number of network | Less networks                 | More networks                   |
| Number of host    | More hosts per network        | Less hosts per network          |
| Subnet Mask       | 255.255.0.0                   | 255.255.255.0                   |
| Network Range     | 128.0.0.0/16 - 191.255.0.0/16 | 192.0.0.0/24 - 223.255.255.0/24 |

b)

i) 13.13.1.1

- Address Class: A
- Default Subnet Mask: `255.0.0.0`
- Network Portion: `13`
- Host Portion: `13.1.1`

ii) 179.4.51.1

- Address Class: B
- Default Subnet Mask: `255.255.0.0`
- Network Portion: `179.4`
- Host Portion: `51.1`

c) Yes. DHCP is a protocol used to dynamically assign IP addresses to devices on a network. When it does not respond, the device unable to obtain an IP address to communicate on the network. APIPA is a feature of OS to automatically assign an IP address from the link-local address range (169.254.0.0/16) when a DHCP server is not available. It allows devices to communicate on the local network through the assigned address. However, as APIPA addresses are private, it is not routable and cannot be used to communicate with devices outside the local network.

d)

i)

- Rule 1: `2003:DB8:1080:12FF:1:0:0:EEFF /64`
- Rule 2: `2003:DB8:1080:12FF:1::EEFF /64`

ii)

- Rule 1: `FE80:0:0:0:201:1234:4321:1 /64`
- Rule 2: `FE80::201:1234:4321:1 /64`

### Question 3

a) VLSM is a method of allocating IP addresses to subnets based on the number of hosts required in each subnet. As opposed to the traditional fixed-length subnetting, VLSM can reduce the number of wasted IP addresses by allowing subnets to have different subnet masks, allowing more networks to be created within the same address space.

b)

| Branch/WAN | Subnet Address | Prefix Length (/) | First Usable Host | Last Usable Host | Broadcast Address |
| ---------- | -------------- | ----------------- | ----------------- | ---------------- | ----------------- |
| Sao Paolo  | 172.16.0.0     | /18               | 172.16.0.1        | 172.16.63.254    | 172.16.63.255     |
| Jeju       | 172.16.64.0    | /19               | 172.16.64.1       | 172.16.95.254    | 172.16.95.255     |
| Okinawa    | 172.16.96.0    | /20               | 172.16.96.1       | 172.16.111.254   | 172.16.111.255    |
| Mindanao   | 172.16.112.0   | /22               | 172.16.112.1      | 172.16.115.254   | 172.16.115.255    |
| WAN 1      | 172.16.116.0   | /30               | 172.16.116.1      | 172.16.116.2     | 172.16.116.3      |
| WAN 2      | 172.16.116.4   | /30               | 172.16.116.5      | 172.16.116.6     | 172.16.116.7      |
| WAN 3      | 172.16.116.8   | /30               | 172.16.116.9      | 172.16.116.10    | 172.16.116.11     |
| WAN 4      | 172.16.116.12  | /30               | 172.16.116.13     | 172.16.116.14    | 172.16.116.15     |

### Question 4

a)

i) Transmission Control Protocol (TCP) and User Datagram Protocol (UDP)

ii)

- The protocol is connection-oriented. It establishes a connection between the sender and receiver before transmitting data, ensuring reliable delivery.
- The protocol guarantees the delivery of packets. It uses checksums to verify the integrity of the data, and using acknowledgments to confirm the reception of packets.
- The protocol provides flow control and windowing mechanisms. The end devices able to negotiate the amount of data to be sent across the network to prevent congestion.
- The protocol provides ordered delivery of packets. The protocol assigns a sequence number to each packet, allowing the receiver to reassemble the packets in the correct order.

b)

i) Simple Mail Transfer Protocol (SMTP)

ii)

- The Mail User Agent (MUA) composes and sends email to the local mail server.
- If the mail server not active, the mail will be spooled to be sent at later time.
- Mail Transfer Agent (MTA) inspects the email to verify the if the recipient in this mail server.
- If not exists, the mail is transfer to the correct mail server which the recipient located at.

iii)

| IMAP                                                                                     | POP                                                                                |
| ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| IMAP stores the email on the server, unless being manually deleted                       | POP does not store the email on the server permanently                             |
| IMAP recepients access the email by download the copy of the email to their local device | POP downloads the actual email to the local device and deletes it from the server. |

c) No. It is because DNS allows users to access websites using human-readable domain names instead of numerical IP addresses by performing translation. The users can remember the domain names much easier than the numerical IP addresses, which increases the usability of the internet.

d) DHCP is an application layer protocol that automatically assigns IP addresses to devices on a network. It allows client devices to obtain IP addresses from the DHCP server automatically, making IP address management easier and more efficient.
