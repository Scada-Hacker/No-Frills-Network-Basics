! This is the work in progress salty version !

No Frills, does what it says on the tin, Network Basics.

Lets get some things out the way

## Who am I ?

Just an IT manager with a lot of experience and a lot of niche experience in OT/ICS security.

There are 2 things I'm very aware of : 

1. Those that want the quick and easy win, without spending any time learning. Everything is expected to be handed on a plate. I once put this down to complete and utter lazyness. And in a sense it is, but thats due to technology becoming so simple and pushbutton freindly its turning the world in to drones.

2. Even worse are those that exploit this. Charging ridiculous amounts of money, knowing the same individuals will lap it up, only to be dissapointed when what they purchase is lacking any real content, or containing content that can be easily found with a search engine.

I cant do much about number 1. If you fall into this catergory, I doubt this is for you. I can, for those willing to learn and do research without constantly asking "next question please" do something about the second.

As I said - no frills.

Index :

1. I Want to be a hacker like MR Robot. Teach ME !
2. Fundementals
3. Networking
IP Address
Subnets
Cidr
Addressing
3.2.2. Private / Public IP 
3.3. Protocols
3.3.1. DNS
3.3.4. DHCP
3.3.3. ARP
3.3.4. SMB
3.3.5. SMTP
3.3.6. HTTP

4. Firewalls
5. Network Analysis
6. Wireless Protocols
7. An introduction to ICS and why you should NEVER attempt to hack it 
7.1 Shodan
7.2 Perdue Model
7.3 PLC's
7.4 SCADA
7.5 MODBUS
7.6 HMI - Human Machine Interface
8. CAN Bus
9. Radio Frequencies
10 HMI - USB on steroids

------------------------------------------------

#### 1. I Want to be a hacker like MR Robot. Teach ME !

Shut up. Take a moment, repeat out loud and listen to how ridiculous it sounds asking such questions. BTW Mr Robot, whilst rather good in its own right was nothing to do with hacking and everything to do with mental illness.

Now you have 2 options :

Go away
Jump to the next section and start learning the fundementals
    
#### 2. Fundementals

The next sections cover the bits you should learn before progressing any further. This will give you a strong foundation and understanding before sticking on a guyfawkes mask and pretending your some kind of anoynmous super hacker. It's not over complicated, and you will thank yourself for putting in a little work instead of wasting your time playing fortnite, watching xxxx porn websites and trying to hack into someones private instagram pictures (Im looking at YOU !)

3.1 Networks

Network fundamentals encompass the foundational principles and components essential for the functioning of computer networks. At the core is an understanding of the OSI (Open Systems Interconnection) model, which delineates the seven layers of communication protocols. Proficiency in networking requires a grasp of networking devices such as routers, switches, hubs, and modems, as well as an ability to configure and manage them. A solid comprehension of IP addressing, subnetting, and the different types of IP protocols is crucial for effective communication within a network. Protocols like TCP/IP play a pivotal role in data transmission, highlighting the significance of reliable and efficient communication. Security is another critical aspect, with an emphasis on concepts like firewalls, encryption, and secure authentication mechanisms. Additionally, troubleshooting skills are paramount for identifying and resolving issues that may arise in a network.

3.1.1. IP Addressing Basics:

In networking, devices are identified by unique IP addresses. IP addresses consist of two main components: the network portion and the host portion. Subnetting focuses on dividing the IP address space into smaller, more manageable segments.

----------

Subnets

Understanding Subnets in Networking
A subnet, short for "subnetwork," is a division of an IP network that enables efficient organization and management of IP addresses. Subnetting plays a crucial role in optimizing network performance, security, and resource allocation.

3.1.2 Why Subnet?

Efficient Resource Allocation: Subnetting allows network administrators to allocate IP addresses more efficiently by creating smaller, logical subdivisions. This helps prevent IP address exhaustion and makes it easier to manage and troubleshoot network issues.
Improved Performance: By breaking a large network into smaller subnets, broadcast traffic is contained within each subnet. This minimizes network congestion and enhances overall performance.

3.1.3 Subnet Mask:

A subnet is defined by a subnet mask, which is a 32-bit number that divides the IP address into network and host portions. The subnet mask uses a combination of binary 1s (representing the network portion) and 0s (representing the host portion).
Example: In the IP address 192.168.1.1 with a subnet mask of 255.255.255.0, the first 24 bits are dedicated to the network, and the last 8 bits are for hosts.

3.1.4 Subnetting Notation:

Subnets are often represented using CIDR (Classless Inter-Domain Routing) notation. For instance, 192.168.1.0/24 indicates a subnet with a 24-bit network portion.
The CIDR notation helps express the size of the subnet and facilitates efficient addressing.

3.1.5 Subnetting Benefits:

Security: Subnets enhance security by isolating sections of a network. Access control lists (ACLs) can be applied to regulate traffic between subnets, minimizing unauthorized access and potential security threats.
Scalability: Subnets provide scalability by allowing networks to grow in a structured manner. New subnets can be added as needed without impacting the entire network.

3.1.6 Subnet Design Considerations:

Number of Hosts: The number of hosts required in each subnet influences the subnet mask and design.
Geographical Location: Consider the physical layout of the network and the need for subnets in different locations.

Binary Translation in Subnetting: Unveiling the Binary Language of Networks
3.1.7 Binary Representation of IP Addresses:

At its core, all networking operations, including subnetting, rely on binary representation. Each octet (8 bits) of an IP address is converted into binary form. For example, the IP address 192.168.1.1 translates to 11000000.10101000.00000001.00000001 in binary.

3.1.8 Subnet Mask in Binary:

The subnet mask is a binary pattern that separates the network and host portions of an IP address. In binary, it consists of a series of consecutive 1s followed by 0s. For instance, the subnet mask 255.255.255.0 translates to 11111111.11111111.11111111.00000000 in binary.

3.1.9 Applying the Subnet Mask:

The subnet mask is logically ANDed with the IP address in binary. This operation preserves the network portion while zeroing out the host bits. In our example:

    IP Address:   11000000.10101000.00000001.00000001
    Subnet Mask:   11111111.11111111.11111111.00000000
    Result:        11000000.10101000.00000001.00000000

    The result is the network address of the subnet.

3.2.1 CIDR Notation in Binary:

CIDR notation, often expressed as /n, indicates the number of bits in the network portion of the subnet mask. For example, /24 means the first 24 bits are the network, and the remaining bits are for hosts. In binary, this translates to:

    Network:       11000000.10101000.00000001.00000000
    CIDR (/24):    11111111.11111111.11111111.00000000

    The CIDR notation aligns with the subnet mask in binary representation.

3.2.2 Binary Subnetting Examples:

Consider a subnet with CIDR notation /26:

    CIDR (/26):    11111111.11111111.11111111.11000000

    Applying this subnet mask to an IP address yields a subnet with 64 possible hosts.

3.2.3 Binary Logic for Subnetting Decisions:

When designing subnets, binary logic guides decisions on the number of subnets and hosts per subnet. It ensures efficient utilization of IP address space and accommodates the desired network structure.

3.2.4 Practical Application:

As network administrators plan and implement subnets, understanding the binary translation is essential. It aids in addressing complexities, troubleshooting, and efficiently managing IP resources.

3.2.5 Addressing

3.2.5.1  Public IP addresses 

Crucial for global internet connectivity, are organized within specific ranges. 
These ranges ensure efficient allocation and management of addresses.  

1.0.0.0 to 9.255.255.255, 
11.0.0.0 to 100.63.255.255, 
100.128.0.0 to 126.255.255.255, 


128.0.0.0 to 169.253.255.255, 
169.255.0.0 to 172.15.255.255, 
172.32.0.0 to 191.255.255.255, 
192.0.1.0/24, 
192.0.3.0 to 192.88.98.255, 
192.88.100.0 to 192.167.255.255, 
192.169.0.0 to 198.17.255.255, 
198.20.0.0 to 198.51.99.255, 
198.51.101.0 to 203.0.112.255, 
203.0.114.0 to 223.255.255.255. 

These ranges help in preventing conflicts, ensuring that each device on the internet is uniquely identified by its public IP address. Whether it's for a website, server, or any globally accessible device, adhering to these established ranges ensures the smooth flow of information across the interconnected web.

3.2.5.2 Private IP addresses fall within the ranges of 

10.0.0.0 to 10.255.255.255 (Class A),
172.16.0.0 to 172.31.255.255 (Class B), and 
192.168.0.0 to 192.168.255.255 (Class C). 

These private address ranges are reserved for internal networks and are not routable over the internet.


3.3 Protocols

3.3.1 DNS

Understanding How DNS Works: A Comprehensive Tutorial

The Domain Name System (DNS) is a crucial component of the internet infrastructure, responsible for translating human-readable domain names into machine-readable IP addresses. This tutorial aims to provide a detailed explanation of how DNS works, from the initial domain name resolution to the final retrieval of web content.

The Domain Name System (DNS) stands as a crucial network protocol that plays a fundamental role in the functioning of the internet. Without it, navigating to our favorite websites would be an arduous task, requiring us to memorize countless IP addresses. Just imagine having to recall the IPv4 (32-bit) addresses of platforms like Facebook, Amazon, and Hackers-Arise, compounded by the complexity of IPv6 (128-bit) addresses.
DNS serves the purpose of translating human-readable domain names into the numerical IP addresses necessary for internet routing. It essentially acts as a translator, converting domain names, which are easy for people to remember, into IP addresses comprehensible to computers and the internet routing system. Therefore, when you input a domain name like www.hackers-arise.com into your browser, DNS swiftly translates it into the corresponding computer-friendly IP address (23.236.62.147), enabling the internet to effectively route your request.

Domain names are required to undergo registration with ICANN (Internet Corporation for Assigned Names and Numbers), typically facilitated by intermediaries like VeriSign or GoDaddy. These registrations encompass various Top-Level Domains (TLDs) such as .com, .edu, and .org, which are commonly observed at the conclusion of Fully Qualified Domain Names (FQDNs).

DNS operates in a hierarchical fashion, with TLDs capable of accommodating multiple subdomains. A subdomain denotes a domain integrated within a larger domain structure. In this instance, redhat and cnn are often colloquially termed as the domain, yet they are technically Second-Level Domains (SLDs) beneath .com.

Beneath these SLDs, commonly referred to as domains, exist numerous subdomains. For instance, within and beneath google.com, google.developent.com may be established. This hierarchical structure allows for the subdivision of domains, with the leftmost portion representing the most specific designation, while the rightmost portion denotes the most general categorization.


3.3.2 DNS Basics

DNS operates as a distributed hierarchical system comprised of multiple components, including DNS servers, resolvers, and authoritative name servers.

DNS Servers: These servers store DNS records and respond to queries from clients. They are classified into several types, including recursive resolvers, root servers, top-level domain (TLD) servers, and authoritative name servers.

Resolvers: Resolvers are DNS clients that initiate DNS queries on behalf of users. They communicate with DNS servers to resolve domain names into IP addresses.

Authoritative Name Servers: These servers store DNS records for specific domains and provide authoritative responses to DNS queries for those domains.

3.3.3 DNS Resolution Process

The DNS resolution process involves several steps, starting from the user's request to access a domain name:

Step 1: User Request: A user enters a domain name (e.g., www.example.com) into their web browser.

Step 2: Resolver Query: The resolver, typically provided by the user's ISP or network administrator, receives the request and queries its configured DNS servers.

Step 3: Recursive Query: If the resolver does not have the requested DNS record cached, it sends a recursive query to a root DNS server.

Step 4: Root DNS Server: The root DNS server responds with the IP address of the TLD server responsible for the requested domain's top-level domain (e.g., .com).

Step 5: TLD DNS Server: The resolver sends a query to the TLD server, which responds with the IP address of the authoritative name server for the requested domain.

Step 6: Authoritative Name Server: Finally, the resolver queries the authoritative name server, which provides the IP address associated with the requested domain name.

3.3.4 DNS Caching and TTL

To improve DNS query efficiency and reduce network traffic, DNS servers and resolvers implement caching mechanisms. When a DNS query is resolved, the result is cached for a specified Time to Live (TTL) period. Subsequent queries for the same domain within the TTL period can be answered directly from the cache, bypassing the recursive resolution process.

3.3.5 DNS Record Types

DNS supports various types of resource records (RRs) that store different types of information about domain names. Some common DNS record types include:

    A Record: Maps a domain name to an IPv4 address.
    AAAA Record: Maps a domain name to an IPv6 address.
    CNAME Record: Creates an alias for a domain name (canonical name).
    MX Record: Specifies the mail exchange servers for a domain.
    NS Record: Indicates the authoritative name servers for a domain.

3.3.6 DNSSEC (DNS Security Extensions)

DNSSEC is a suite of security extensions designed to add cryptographic integrity and authentication to DNS data. It aims to prevent DNS spoofing and man-in-the-middle attacks by validating DNS responses using digital signatures.

DNS plays a critical role in facilitating internet communication by translating human-readable domain names into machine-readable IP addresses. Understanding how DNS works is essential for network administrators, web developers, and anyone interested in internet infrastructure. By following the steps outlined in this tutorial, you can gain a comprehensive understanding of the DNS resolution process and its underlying mechanisms.

3.4 DHCP

DHCP is a network management protocol employed to automate the assignment of IP addresses and other network configuration parameters to devices connected within a network. Its primary goal is to simplify the process of network administration by dynamically allocating network addresses to devices, thereby eliminating the need for manual configuration.

At its core, DHCP operates on a client-server model, where DHCP servers are responsible for assigning IP addresses and related network parameters, while DHCP clients request and receive these configurations. The process unfolds in a series of steps, encapsulated within a DHCP transaction.

DHCP Transaction:

DHCP Discover: 

When a device connects to a network, it sends out a DHCP Discover broadcast message to discover available DHCP servers. This broadcast is typically directed to the limited broadcast address (255.255.255.255), ensuring that all DHCP servers within the local network segment receive the message.

DHCP Offer: 

Upon receiving the DHCP Discover message, DHCP servers respond with a DHCP Offer message. This message contains an available IP address and other network configuration parameters, such as subnet mask, default gateway, DNS server addresses, lease duration, etc. Each DHCP server may send an offer, but the client usually accepts the first offer it receives.

DHCP Request: 

Having received one or more offers, the DHCP client selects an offer and sends a DHCP Request message to the chosen DHCP server, confirming its intention to acquire the offered configuration.

DHCP Acknowledgment: 

Upon receiving the DHCP Request message, the DHCP server acknowledges the client's request by sending a DHCP Acknowledgment message. This message confirms the allocation of the IP address and other network parameters to the client.

IP Lease: 

The DHCP server leases the IP address to the client for a specified duration, known as the lease period. During this lease period, the client is authorized to utilize the allocated IP address and network configurations. Upon lease expiration, the client must renew its lease or request a new one.

Key Components of DHCP:

DHCP Server: 

A DHCP server is a network device responsible for allocating IP addresses and configuring network parameters to DHCP clients within its scope of authority. DHCP servers maintain a pool of available IP addresses and lease durations, ensuring efficient utilization of network resources.

DHCP Client: 

DHCP clients are devices seeking network configuration parameters from DHCP servers. These devices may include computers, smartphones, printers, and other network-enabled devices. DHCP clients automate the process of obtaining IP addresses and related configurations, simplifying network setup and administration.

DHCP Relay Agent: 

In large networks spanning multiple subnets, DHCP relay agents facilitate DHCP communication between DHCP clients and servers. These agents receive DHCP broadcast messages from clients and forward them to designated DHCP servers, ensuring seamless DHCP operation across network segments.

Benefits of DHCP:

Simplified Network Management: 

DHCP eliminates the manual configuration of network parameters, streamlining the process of network administration. By automating IP address assignment and configuration, DHCP minimizes human intervention and reduces the likelihood of configuration errors.

Efficient Resource Utilization: 

DHCP optimizes the utilization of IP addresses by dynamically allocating them to devices as needed. By leasing IP addresses for a finite duration, DHCP ensures that unused addresses are returned to the available pool, preventing address exhaustion and promoting resource efficiency.

Scalability: DHCP accommodates the dynamic growth of networks by dynamically allocating IP addresses to newly connected devices. As networks expand or contract, DHCP seamlessly adjusts its allocation of IP addresses and network configurations, facilitating network scalability and adaptability.

Centralized Management: DHCP centralizes the management of network configurations within a dedicated DHCP server. Administrators can configure DHCP servers to enforce network policies, assign specific IP address ranges to designated devices, and monitor network activity centrally, enhancing network security and control.
