# Linux

# Waterfall Methodology and SDLC

## Waterfall Methodology

The Waterfall model is a traditional software development methodology. It follows a **sequential** approach, where each phase must be completed before moving on to the next. The Waterfall method is typically used in environments where requirements are well-defined and unlikely to change.

### Phases in the Waterfall Model:

1. **Requirements:** 
   - Gather and document all the requirements for the software.
   - Ensure that all stakeholders have agreed on the requirements.

2. **Design:** 
   - Create detailed design specifications based on the requirements.
   - This phase involves system and software architecture design.

3. **Development:** 
   - Write the actual code based on the design specifications.
   - This phase involves coding, programming, and implementing the solution.

4. **Testing:** 
   - After development, testing is conducted to find defects or bugs in the system.
   - The software is tested to ensure it meets the requirements.

5. **Deployment:** 
   - Once the software is tested and is working as expected, it is deployed for use.
   - This involves setting up the software in the live environment.

6. **Maintenance:** 
   - After deployment, the software enters the maintenance phase.
   - This phase involves fixing issues, making updates, and enhancing the software.

---

## Software Development Life Cycle (SDLC)

SDLC stands for **Software Development Life Cycle**. It is a step-by-step process for planning, creating, testing, and deploying a software product. The SDLC ensures that software is developed in a structured and efficient manner.

### Phases in the SDLC:

1. **Planning:**
   - Define the scope, objectives, and resources required for the software project.
   - Identify potential risks and plan mitigation strategies.

2. **Requirements:**
   - Gather detailed requirements from stakeholders.
   - Document functional and non-functional requirements.

3. **Design:**
   - Create both high-level and detailed design documents.
   - Define architecture, components, and user interfaces.

4. **Development:**
   - Start coding based on the design specifications.
   - Implement features and functionality defined in the design phase.

5. **Testing:**
   - Perform various types of testing (e.g., unit testing, integration testing, acceptance testing).
   - Identify and fix bugs or issues.

6. **Deployment:**
   - Deploy the software into the production environment.
   - Ensure the software is available for users.

7. **Maintenance:**
   - Monitor the software for issues.
   - Provide updates, fixes, and enhancements as required.

---
DevOps is the process of building, deploying and testing the code written by developer on the same day instead of doing after complete development.. we can acheive this using continous integration, continous deployment, continous delivery and continous testing. 
We can do faster releases with less defect using DevOps... basically automation mindset to get the best results


## Conclusion

Both Waterfall and SDLC are essential methodologies in the software development world. The Waterfall method is more rigid and sequential, while the SDLC provides a more flexible, iterative process. Choosing the right approach depends on the nature and complexity of the project.

## What is Linux?
- Linux is an open-source operating system like Windows and macOS, but it is free.

## Why Linux is Important?
- Most of the cloud providers like Azure, GCP, AWS run Linux VMs.
- Automation tools like Ansible, Kubernetes, Docker mostly work on Linux.
- CI/CD servers like Jenkins mostly run on Linux.
- Bash scripting is easy in Linux.

## What is Networking?
- Networking means connecting one or more devices like containers, servers, computers so they can share information.
- There are 2 types:
  - **Private Networking:** Used for internal purposes.
  - **Public Networking:** Used for internet-facing applications.

## Core Network Concepts:
- **IP Address:** Unique address of a machine on a network.
- **Port:** Doorway to communicate with a machine.
- **Protocol:** Rules for communication like HTTPS, HTTP, UDP, TCP.
- **Subnet:** A small network within a big network.
- **Gateway:** Device that connects two different networks.

## Viewing Network Interface:
- `ip config` or `ip link show`

## Configuring Network Interface:

### Static IP Address:
- You need to add the network configuration:
  - `sudo nano /etc/network/interfaces`
- To restart and save:
  - `sudo systemctl restart networking`

### Dynamic IP Configuration:
- It can be done using DHCP.
- Configuration example under `/etc/network/interfaces`:
  auto eth0 iface eth0 inet dhcp
- To restart and save:
- `sudo systemctl restart networking`

## Network Configuration Files:
- `/etc/network/interfaces` location.
- This file is mostly used on Debian-based systems to configure the network interface.

## What is CIDR Block?
- CIDR means Classless Inter-Domain Routing blocks.

## IPv4 Address:
- It contains 32-bit numeric values written in 4 decimals.
- Example: `192.168.1.1`

### IPv4 Address Classes:
- **Class A:**  
`1.0.0.0` to `127.255.255.255` (Default subnet mask: `255.0.0.0` /8)
- **Class B:**  
`128.0.0.0` to `191.255.255.255` (Default subnet mask: `255.255.0.0` /16)
- **Class C:**  
`192.0.0.0` to `223.255.255.255` (Default subnet mask: `255.255.255.0` /24)

## Calculating CIDR Blocks:

- Common prefix lengths:
- `/8`: 8 bits for network and 24 bits for host.
- `/16`: 16 bits for network and 16 bits for host.
- `/24`: 24 bits for network and 8 bits for host.

- Example:
- IP: `192.168.1.0`
- 32 bits total, each number (octet) has 8 bits (192, 168, 1, 0).
- `/24` means:
  - First 24 bits = Network part (fixed) → `192.168.1`
  - Last 8 bits = Host part → `0` can be changed.

## How Many Hosts You Get for a Given CIDR Block:
- Formula:  
`Number of hosts = 2^(number of host bits) - 2`
- We subtract 2 because:
- 1 for broadcast address (all bits 1).
- 1 for network address (all bits 0).

windows
-----------
not open source
costly
not secure must install anti virus
slow
too many graphics
frequent restarts
tough to update/upgrade

Linux --> 9MB
Secure
high speed --> mostly text
no need of restarts
install or update packages is easy
free, community support
low resources

### Examples:
- `/24`:  
- 32-24 = 8 host bits  
- Total IP addresses = 2^8 = 256  
- Usable IPs = 256 - 2 = 254 hosts
- `/16`:  
- 32-16 = 16 host bits  
- Total IP addresses = 2^16 = 65536  
- Usable IPs = 65536 - 2 = 65534 hosts
- `/8`:  
- 32-8 = 24 host bits  
- Total IP addresses = 2^24 = 16,777,216  
- Usable IPs = 16,777,216 - 2 = 16,777,214 hosts

````
# What is a Computer?

A computer is a machine that can perform calculations, process data, and store information.

---

# What is a Server?

A **server** is a system that hosts applications and provides services to other computers (clients) over a network.

---

# Client-Server Architecture

**Client-Server Architecture** is a design pattern used in network computing. It contains two main components to interact:

1. **Client**  
2. **Server**
**Client**  : A client is any device or application that sends a request to the server.
**Server** : A server is a system or program that waits for requests from clients and responds to them.

Client (Browser/App)  ---> sends request --->  Server (Backend)
Client (Browser/App)  <--- receives data <---  Server (Backend)

---

# Common Issues After Hitting a URL in the Browser

If there is any issue after accessing something in a browser, it could be due to:

1. **Network Application Issues**  
2. **Application Issues**

---

# How to Connect to a Server

### Required Components:
- **Protocols**: `http` / `https`
- **Ports**: `80` / `443`
- **IP Address**: DNS or IP Address
- **Username**: Required for login
- **Password**: Required for authentication

---

# SSH (Secure Shell)

- **SSH**: Secure Shell, used to securely connect to remote servers.
- **Default Port**: `22`
- Linux servers typically work over SSH.

---

# Types of Network Traffic

1. **Inbound Traffic** – Incoming traffic to a server.
2. **Outbound Traffic** – Outgoing traffic from a server.

---

# Types of Keys

1. **Private Key** – Used to authenticate and decrypt data.
2. **Public Key** – Shared with others to encrypt data.

AMI -----> Amazon machine image
AMI name ----> devops-practice
password -----> DevOps321
user name -----> ec2-user

It is not keybased is password. 
It is a template used to lanch the Ec2 instances in AWS.
It includes OS,software and settings need to start an intances

Internal communication should be done using private key
External comminucation should be done using public key
````
