*This project has been created as part of the 42 curriculum by stmaire.*
<div align="center">
<br>
  <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTQPzuYKu7n0cWUYa5Kbg0_LrlEQAIURWeo9A&s" alt="42 Logo" width="400" />

  <br>
</div>

# NetPractice

![Static Badge](https://img.shields.io/badge/Rigor-pink)
![Static Badge](https://img.shields.io/badge/Network_&_system_administration-pink)

## 🔵 Description

### ✳️ Goal
The goal of this project is to discover the basics of networking.

### ✳️ Overview
This project is based on a practical exercise designed to introduce the basics of computer networking : how to configure IP addresses, how to connect devices through a router, what is the role of a gateway within a network.
It involves solving networking  problems to make a network function properly.



## 🔵 Instructions

### ✳️ Prerequisites
- Download the file attached to the project's page on the intranet:

```net_practice.1.9.tgz```

### ✳️ Installation
- Extract the files into the folder of your choice (example with the standard archive name):

```tar -xvzf net_practice.1.9.tgz -C <Your_Directory>```


### ✳️ Execution

**1. Run the training interface**

Navigate to your directory and run the run.sh script to launch the local web server and automatically open the interface in your browser:

```./run.sh```

Note: Due to technical design and security constraints on various web browsers, it is required to use a local web server to deliver NetPractice’s web pages. If the “run.sh” script does not function properly, you can access the project manually:

```python3 -m http.server 49242```

You may change the port number. Then, in your web browser navigate to the URL :

http://localhost:49242

 (or any other
port you may have chosen).

**2. Export configurations**

For each of the 10 available levels, it is possible to download the correct network configuration (.json file).

Once a level is successfully completed, click the [Get my config] button to download the configuration file.

**3. Submission requirements**

The 10 exported configuration .json files (one per level)
must be placed at the root of the Git repository.

## 🔵 Resources

### ✳️ Key notions

*Click on the notion to see the definition.*

**1. Networking Infrastructure**

<details>
<summary><strong>LAN/MAN/WAN</strong></summary>


There are three types of networks which always include terminal elements, interconnexion elements and cables :

- LAN (Local Area Network): A network covering a small geographic area like a home or office. Devices are directly connected and can communicate quickly.
- MAN (Metropolitan Area Network): A network spanning a larger area like a city or campus. It connects multiple LANs together.
- WAN (Wide Area Network): A network covering a very large geographic area, like the internet connecting cities and countries.
</details>


<details>
<summary><strong>Switch</strong></summary>

A switch is a networking device that connects devices within the same network. It receives data from one device and forwards it to the correct port based on the device's physical address (MAC address). Switches operate at layer 2 (Data Link Layer) and are used to create efficient local networks.
</details>

<details>

<summary><strong>Router</strong></summary>

A router is a device that connects different networks together. It reads IP addresses to determine where data should go and forwards packets between networks. Routers operate at layer 3 (Network Layer) and are essential for connecting your local network to the internet or other networks.
</details><br>

**2. IP Protocol & Addressing**

<details>
<summary><strong>TCP/IP Addressing</strong></summary>

TCP/IP (Transmission Control Protocol/Internet Protocol) is not a single protocol, but a comprehensive protocol suite that works collaboratively to split, address, route, and reassemble data packets from a source (Point A) to a destination (Point B).

When you send data from one computer to another, the TCP/IP protocol suite follows four simple steps to make sure it arrives safely:

* Breaking into Packets (TCP): First, the protocol takes your large data (like a web page or an image) and cuts it into many smaller pieces called packets. This makes the data easier and faster to move across the network.

* Adding Addresses (IP): Next, the protocol attaches an "envelope" to each packet. This envelope contains the source IP address (where it comes from) and the destination IP address (where it goes).

* Routing the Data (The Router): The packets are then sent into the network. Devices called routers look at the destination IP address on the envelope. If the destination is outside the local network, the computer sends the packets to its Default Gateway (its local router). The routers then pass the packets from one to another until they reach the correct network.

* Reassembling the Data (TCP): Finally, when all the packets arrive at the destination computer, the protocol checks them for errors. It puts the pieces back together in the correct order so the receiver can read the original data.
</details>


<details>
<summary><strong>IP Addresses (IPv4)</strong></summary>

An IPv4 address (**Internet Protocol Version 4**) is a unique identifier for each device on a network. It consists of four numbers separated by dots (example: 192.168.1.5). Each number ranges from 0 to 255. This address allows data to be sent to the correct device, similar to a street address for a house.

Because the world has run out of unique IPv4 addresses due to the massive number of connected devices, a newer version called IPv6 (**Internet Protocol Version 6**) was created; it uses a longer format with numbers and letters (example: 2001:0db8:85a3:0000:0000:8a2e:0370:7334) to provide an almost infinite number of unique addresses.
</details>

<details>
<summary><strong>Subnet Masks</strong></summary>

A subnet mask determines which part of an IP address represents the network and which part represents individual devices. It looks like an IP address (example: 255.255.255.0). The subnet mask divides a large network into smaller, more manageable sections called subnets.
</details>

<details>
<summary><strong>Network Address & Broadcast Address</strong></summary>

The **network address** is the **first address** in a subnet and identifies the entire network (example: 192.168.1.0).

The **broadcast address** is the **last address** in a subnet and is used to send messages to all devices in that network (example: 192.168.1.255). Individual devices use addresses between these two.
</details>

<details>
<summary><strong>CIDR Notation</strong></summary>

CIDR (Classless Inter-Domain Routing) notation is a shorthand way to write IP addresses with their subnet mask. It uses a slash followed by a number (example: 192.168.1.0/24). The number represents how many bits are used for the network portion, making it simpler than writing out the full subnet mask.

| CIDR | Total addresses | Usable hosts | Netmask |
|------|-----------------|--------------|---------|
| /16  | 65,536          | 65,534       | 255.255.0.0 |
| /17  | 32,768          | 32,766       | 255.255.128.0 |
| /18  | 16,384          | 16,382       | 255.255.192.0 |
| /19  | 8,192           | 8,190        | 255.255.224.0 |
| /20  | 4,096           | 4,094        | 255.255.240.0 |
| /21  | 2,048           | 2,046        | 255.255.248.0 |
| /22  | 1,024           | 1,022        | 255.255.252.0 |
| /23  | 512             | 510          | 255.255.254.0 |
| /24  | 256             | 254          | 255.255.255.0 |
| /25  | 128             | 126          | 255.255.255.128 |
| /26  | 64              | 62           | 255.255.255.192 |
| /27  | 32              | 30           | 255.255.255.224 |
| /28  | 16              | 14           | 255.255.255.240 |
| /29  | 8               | 6            | 255.255.255.248 |
| /30  | 4               | 2            | 255.255.255.252 |
</details><br>

**3. Routing Logic**

<details>
<summary><strong>Gateway / Default Gateway</strong></summary>

A gateway is a device that connects your local network to other networks or the internet. The default gateway is the router that receives all data packets destined for networks outside your own. Every device needs to know its default gateway to communicate beyond its local network.

Example: `Default` route or `0.0.0.0/0` via `192.168.1.1`means “send all unknown traffic through this gateway.” |
</details>

<details>
<summary><strong>Next Hop</strong></summary>

The next hop is the next device that a data packet should be sent to on its journey toward its destination. Routers use routing tables to determine the next hop for each packet. This ensures data takes the most efficient path through the network.
</details>

<details>
<summary><strong>Routing Table</strong></summary>

A routing table is a list of routes stored in a router or device. Each route specifies which network address can be reached and through which gateway or interface the packet should be sent. Routers consult this table to decide how to forward each packet.
</details>

<details>
<summary><strong>0.0.0.0/0 (Default Route)</strong></summary>

This special address represents "any network" or "anywhere." When a router has a route to 0.0.0.0/0, it means "if you don't know where this packet should go, send it here." This is typically set to your internet service provider's gateway to reach the wider internet.
</details><br>

**4. Conceptual Framework:**

<details>
<summary><strong>OSI Model (Open Systems Interconnection)</strong></summary>


The OSI model is a theoretical framework that describes how data travels through a network in 7 layers. Each layer has a specific purpose and communicates only with the layers directly above and below it. This model helps us understand networking concepts and troubleshoot problems.

1. **Physical Layer**: Deals with the actual hardware and cables. It transmits raw bits of data through physical mediums like cables and wireless signals.

2. **Data Link Layer**: Handles communication between devices on the same network using MAC addresses. Switches operate at this layer to forward data between local devices.

3. **Network Layer**: Manages routing and IP addressing. Routers operate here, using IP addresses to send data across different networks.

4. **Transport Layer**: Ensures reliable data delivery between applications using protocols like TCP and UDP. It manages how data is broken into segments and reassembled.

5. **Session Layer**: Establishes, maintains, and terminates connections between applications. It handles conversation management between devices.

6. **Presentation Layer**: Translates data into a format that applications can understand. It handles encryption, compression, and data formatting.

7. **Application Layer**: Where users interact with the network through applications like web browsers, email clients, and file transfer programs.

**TCP/IP Model (Practical Model)**

The TCP/IP model is a simpler, 4-layer framework used in real-world networking. It combines some OSI layers and focuses on how the internet actually works.

1. **Link Layer**: Combines OSI layers 1-2. Handles physical transmission and local device communication using MAC addresses.

2. **Internet Layer**: Corresponds to OSI layer 3. Manages routing and IP addressing to send data across networks.

3. **Transport Layer**: Corresponds to OSI layer 4. Provides reliable delivery through TCP or fast delivery through UDP.

4. **Application Layer**: Combines OSI layers 5-7. Includes all user applications and protocols like HTTP, FTP, DNS, and SMTP.

**Why Both Models?**

The OSI model is used for teaching and understanding networking concepts systematically. The TCP/IP model is what the actual internet uses. Understanding both helps you grasp how networks function at different levels and how data travels from one device to another across the globe.
</details>

<div align="center">
<br>
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/79/OSI_Application_Layer.svg/960px-OSI_Application_Layer.svg.png?_=20260118223941"  width="400" />

  <br>
</div>


### ✳️ References

OpenClassrooms tutorial:
https://openclassrooms.com/fr/courses/6944606-concevez-votre-reseau-tcp-ip

Zeste de Savoir tutorial "les réseaux de zéro":
https://zestedesavoir.com/tutoriels/2789/les-reseaux-de-zero/le-concept-et-les-bases/

### ✳️ AI Usage

Artificial Intelligence was exclusively used as a writing assistant for the documentation part of this project. Specifically, it helped translate and refine the English phrasing within this README.md file.

All technical configurations, routing logic, and level resolutions were achieved manually without AI assistance.
