# Linux



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

## AWS:
ssh-keygen -f <fiename --- to create pub and private keys
ssh -i <private> ec2-user@publickey ---->> to login into aws




## ESC Mode

- `u` → Undo the changes
- `gg`→ It will take to top of the file
- `shift+g`→ Takes to the bottom of the file

