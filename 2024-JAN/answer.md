# AACS2034 MAY 2024 Answers

[Link to the paper](https://eprints.tarc.edu.my/27893/1/AACS2034.pdf)

- [Question 1](#question-1)
- [Question 2](#question-2)
- [Question 3](#question-3)
- [Question 4](#question-4)

### Question 1

a.

(i) `show ip route`

(ii) Routing table on a router

(iii) 3 routes

(iv) 

- 172.16.18.0/24
- 192.168.10.0/26
- 209.165.200.0/30

> The IP addresses marked with C, which means directly connected networks (and the network address is shown)

(v) 

- 172.16.18.1
- 192.168.10.1
- 209.165.200.2

> The IP addresses marked with L, which means the IP address of the interface of the router that is connected to the network

(vi) GigabitEthernet0/1 is an interface on router R1 that connects the router to network 172.16.18.0. The interface is also used by the said network as the default gateway to transmit packets outside its local network.

(vii) The packet will be dropped. There is no network which contains the IPv4 address 210.200.100.8 within the routing table. In addition, the router's default gateway is not set.

b.  

- Connectionless --> does not need to establish a connection between 2 hosts
- Best Effort --> will not guarantee packet delivered safely and correctly
- Media Independent --> can be used on any media available to pass data.

c. 

| IPv4 | IPv6 |
| ---- | ---- |
| 20 bytes of header size | 40 bytes of header size |
| Has more fields | Has less fields |

### Question 2

a.

(i) 10.6.70.1

- Class A
- Default Subnet Mask: 255.0.0.0 

(ii) 192.168.38.9

- Class C 
- Default Subnet Mask: 255.255.255.0

(iii) 172.16.15.19

- Class B
- Default Subnet Mask: 255.255.0.0

b. 

- Class D is reserved for multicasting purposes. They are not available to assign to any host. They are used to identify a group of hosts that can receive the same packet simultaneously.
- Example: 234.10.10.0

c.

- Dual Stack: Hosts run on both IPv4 and IPv6 protocols simultaneously
- Tunnelling: Encapsulate IPv6 packet within an IPv4 packet to allow it to transmit on an IPv4 network. (No vice versa)
- Translation: Using Network Address Translation 64 (NAT64) to translate IPv4 packets into IPv6 packets and vice versa, so IPv6 devices can communicate with IPv4 devices.

d. 

(i) `2001:0db8:CAFE:FDFF:000A:0100:0000:0001`

- Rule 1: `2001:db8:CAFE:FDFF:A:100:0:1`
- Rule 2: `2001:db8:CAFE:FDFF:A:100::1`

(ii) `FE80:0000:0000:0000:020A:F3FF:FEBB:A594`

- Rule 1: `FE80:0:0:0:20A:F3FF:FEBB:A594`
- Rule 2: `FE80::20A:F3FF:FEBB:A594`

(iii) `FDFF:0000:A100:9800:0000:AAAA:BBBB:CCCC`

- Rule 1: `FDFF:0:A100:9800:0:AAAA:BBBB:CCCC`
- Rule 2: `FDFF::A100:9800:0:AAAA:BBBB:CCCC`

### Question 3

a.

192.168.8.9/27 - base here how many bit borrowed

(i) 

- Default Prefix (Class C): /24
- Custom Prefix: /27
- $27 - 24 = 3$


(ii)

- IP Address in Binary: `11000000.10101000.00001000.00001001`
- Subnet Mask (/27) in Binary: `11111111.11111111.11111111.11100000`

```
    11000000.10101000.00001000.00001001
AND 11111111.11111111.11111111.11100000
----------------------------------------
    11000000.10101000.00001000.00000000
```

- Convert back to Decimal: `192.168.8.0`

(iii)

$`
\begin{aligned}
\text{Host Bit} &= 32 - 27
 &= 5
\end{aligned}
`$

$`
\begin{aligned}
2^{5} - 2 &= 32 - 2
 &= 30
\end{aligned}
`$

(iv) NO because the broadcast address is the last address in a subnet. The last IP address for the network is 192.168.8.31.

b. 
| Branch Name / WAN Link | Prefix length(/X) | Subnet Address | First Usable Host Address | Last Usable Host Address | Broadcast |
|-|-|-|-|-|-|
| Accounting | /26 | 192.168.10.0 | 192.168.10.1 | 192.168.10.62 | 192.168.10.63 |
| IT | /27 | 192.168.10.64 | 192.168.10.65 | 192.168.10.94 | 192.168.10.95 |
| Purchasing | /27 | 192.168.10.96 | 192.168.10.97 | 192.168.10.126 | 192.168.10.127 |
| Warehouse | /28 | 192.168.10.128 | 192.168.10.129 | 192.168.10.142 | 192.168.10.143 |
| SALES | /28 | 192.168.10.144 | 192.168.10.145 | 192.168.10.158 | 192.168.10.159 |

### Question 4

a. 

- Socket Pair is the pair of source IP address with port number and destination IP address with port number.
- Sockets enable one host to track individual communication for different processes.
- Example: (192.168.10.11:80, 192.168.10.2:80)

b.

| Well Known Port | Registered Port |
| --------------- | --------------- |
| Range from 0-1023 | Range from 1024 to 49151 |
| Reserved for popular services such as web and mail services | Individual application that users chosen to installed |

c. 

- Simple Mail Transfer Protocol (SMTP)
- Post Office Protocol (POP)
- Internet Message Access Protocol (IMAP)

d. 
GET - is HTTP message type to REQUEST web page or HTML or data from a HTTP Server by HTTP client
POST - is a HTTP message type to SEND data to an HTTP Server
PUT - is a HTTP message type to UPLOAD RESOURCES(usually images or files) into HTTP Server

### Extra Question 

a. Examine the main function and state the well-known port numbers of the protocols as follows: 

(i) Hypertext Transfer Protocol (HTTP) - Used to communicate and access web services through the Universal Resource Locator (URL). Port: 80

> HTTPS has a port number of 443, which is HTTP with SSL encryption.

(ii) File Transfer Protocol (FTP) - Use in transferring, reading, and uploading of files to a file server, Port: 20 (Data), 21 (Control)

(iii) Simple Mail Transfer Protocol (SMTP) - Standard to send email from a mail client to a server. Port: 25
(iv) Post Office Protocol (POP) - Retrieving emails from the mail server by downloading them to the mail client. The downloaded email will be deleted on the server. Port: 110
