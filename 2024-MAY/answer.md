# AACS2034 MAY 2024 Answers

[Link to the paper](https://eprints.tarc.edu.my/28539/1/AACS2034.pdf)

- [Question 1](#question-1)
- [Question 2](#question-2)
- [Question 3](#question-3)
- [Question 4](#question-4)

### Question 1

a)

i) IPv4 limitations:

- IPv4 address is depleting because the available IPv4 addresses are only 2^32 (4,294,967,296), which is not enough to accommodate the growing population of devices connected to the internet. The rapid growth of the Internet of Things (IoT) also demands more IP addresses.

- The expansion of the internet routing table leads to slower routing. As IPv4 has more complex structure, it requires more memory and processing power to process the IPv4 packets.

- IPv4 has end-to-end connectivity issues when NAT is used. NAT allows multiple local devices to share a single public IP address, which can cause issues with end-to-end connectivity and complicate peer-to-peer communication.

ii) IPv6 advantages:

- The IPv6 address space is 128 bits, which allows for a virtually unlimited number of unique IP addresses. This means that every device can have its own unique IP address, eliminating the need for NAT and allowing for end-to-end connectivity.

- The IPv6 header is simpler and more efficient than the IPv4 header, which reduces the processing time for routers and improves overall network performance.

- The IPv6 protocol does not require NAT due to its large address space, which simplifies network configuration and improves end-to-end connectivity.

b)

i) 4

ii)

| Directly connected Routes | Remote Routes     |
| ------------------------- | ----------------- |
| 2003:DB8:A:1::/64         | 2003:DB8:A:3::/64 |
| 2003:DB8:1:2::/64         | 2003:DB8:A:2::/64 |

iii)

| Step | Layer 2 Source Address | Layer 2 Destination Address | Layer 3 Source Address | Layer 3 Destination Address |
| ---- | ---------------------- | --------------------------- | ---------------------- | --------------------------- |
| 1    | 0060.2F9A.585E         | 0001.97C6.22D2              | 2003:DB8:A:2::2/64     | 2003:DB8:A:3::2/64          |
| 2    | 0001.9650.9E66         | 0001.420C.C9C2              | 2003:DB8:A:2::2/64     | 2003:DB8:A:3::2/64          |

### Question 2

a)

i) 103.130.11.11

- Address class: A
- Default subnet mask: 255.0.0.0
- Network Portion: 103
- Host Portion: 130.11.11

ii) 169.254.251.1

- Address class: B
- Default subnet mask: 255.255.0.0
- Network Portion: 169.254
- Host Portion: 251.1

b)

i)

- Rule 2: `2003:DB8:80:0:0:0:0:ABCD /64`
- Rule 1: `2003:0DB8:0080:0000:0000:0000:0000:ABCD /64`

ii)

- Rule 2: `FE80:0:0:0:0:0:0:1 /64`
- Rule 1: `FE80:0000:0000:0000:0000:0000:0000:0001 /64`

c)

i) Yes, it is because they are located in the same network, which has the network address of `192.168.2.0/24`, and have a same default gateway of `192.168.2.1`.

ii) It is because the default gateway of Server TWO is misconfigured to `192.168.3.20`, it should be corrected to `192.168.3.1`. This mistake causes Server TWO unable to reply the ping request from Server ONE, because the reply packet cannot escape from the local network.

iii)

| Private IPv4 Address         | Public IPv4 Address           |
| ---------------------------- | ----------------------------- |
| Not routable on the internet | Routable on the internet      |
| Not unique globally          | Unique globally               |
| Used for local communication | Used for global communication |

iv)

| Public IPv4 Address | Private IPv4 Address |
| ------------------- | -------------------- |
| `203.188.200.2`     | `192.168.0.0`        |
| `203.188.200.1`     |                      |

### Question 3

a) AND operation is used to determine the network address of an IP address through the subnet mask.

- Binary of 192.168.2.11 = `11000000.10101000.00000010.00001011`
- Binary of subnet mask /24 = `11111111.11111111.11111111.00000000`
- Result of AND operation = `11000000.10101000.00000010.00000000`
- Decimal of result = `192.168.2.0`

b) Two methods to reduce number of wasted IPv4 addresses in a subnet

- VLSM (Variable Length Subnet Masking): This method allows subnets to be of different sizes, which helps to allocate IP addresses more efficiently based on the number of hosts required in each subnet.
- CIDR (Classless Inter-Domain Routing): This method allows for more flexible allocation of IP addresses by using a prefix length instead of fixed class boundaries, which helps to reduce the number of wasted addresses in a subnet.

> CIDR is used when a portion of global address space is allocated to an organization, and the organization can then use VLSM to allocate subnets within that address space.
> Without CIDR, the organization would be limited to fixed class boundaries (A, B, or C) for their subnets, which could lead to wasted addresses.

c)

| Site         | Subnet Address | Prefix Length (/) | First usable Host | Last usable Host | Broadcast Address |
| ------------ | -------------- | ----------------- | ----------------- | ---------------- | ----------------- |
| EAST BRANCH  | 192.168.23.0   | /26               | 192.168.23.1      | 192.168.23.62    | 192.168.23.63     |
| WEST BRANCH  | 192.168.23.64  | /27               | 192.168.23.65     | 192.168.23.94    | 192.168.23.95     |
| SOUTH BRANCH | 192.168.23.96  | /28               | 192.168.23.97     | 192.168.23.110   | 192.168.23.111    |
| WAN 1        | 192.168.23.112 | /30               | 192.168.23.113    | 192.168.23.114   | 192.168.23.115    |
| WAN 2        | 192.168.23.116 | /30               | 192.168.23.117    | 192.168.23.118   | 192.168.23.119    |
| WAN 3        | 192.168.23.120 | /30               | 192.168.23.121    | 192.168.23.122   | 192.168.23.123    |

### Question 4

a)

- TCP provides ordered delivery of packets. Each packet is assigned a sequence number, and the receiver uses these numbers to reassemble the packets in the correct order. This ensures that the data is received in the same order it was sent.
- TCP provides flow control through windowing. The sender can only send a certain amount of data before waiting for an acknowledgment from the receiver. This prevents the sender from overwhelming the receiver with too much data at once.
- TCP provides error detection and correction through checksums. Each packet includes a checksum that is calculated based on the data in the packet. The receiver checks the checksum to ensure that the data has not been corrupted during transmission. If the checksum does not match, the receiver can request that the sender retransmit the packet.

b) FIN, ACK-FIN, ACK

```
    +--------+              +--------+
    | Client |              | Server |
    +--------+              +--------+
        |                        |
        |--------- FIN --------->|  (1) Client sends FIN to Server
        |                        |
        |<-------- ACK ----------|  (2) Server acknowledges client's FIN
        |                        |
        |<-------- FIN ----------|  (3) Server sends FIN to Client
        |                        |
        |--------- ACK --------->|  (4) Client acknowledges server's FIN
        |                        |
```

c)

i) Dynamic Host Configuration Protocol (DHCP)

ii)

```

    +--------+              +--------+
    | Client |              | Server |
    +--------+              +--------+
        |                        |
        |------- DISCOVER ------>|  (1) Client broadcasts DHCP Discover message to find DHCP server on the network
        |                        |
        |<------- OFFER ---------|  (2) Server offers a lease of an IP address to the client with a DHCP Offer message
        |                        |
        |------- REQUEST ------->|  (3) Client accepts the offer and requests the IP address using DHCP Request message
        |                        |
        |<------ ACK/NAK --------|  (4) Server acknowledges request and provides IP configuration using DHCP ACK message.
        |                        |      If the offer is no longer valid, the server sends a DHCP Negative Acknowledgment
        |                        |      (NAK) message.
```
