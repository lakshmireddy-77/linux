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


# What is DNS?

**DNS** stands for **Domain Name System**.

When you type a website like `google.com` or `lakshmireddy.site` in your browser, DNS translates the domain name into an IP address. This is how your computer knows where to connect.

**Example:**
```
google.com          → .com is the TLD (Top-Level Domain)
lakshmireddy.site   → .site is the TLD
```

---

## 🔁 Step-by-Step: What Happens When You Type a Domain in the Browser

```
You type → lakshmireddy.site
        ↓
1. Browser Cache
        ↓
2. Operating System (OS)
        ↓
3. OS Cache
        ↓
4. DNS Resolver (usually by your ISP)
        ↓
5. Root Servers
        ↓
6. TLD Servers (.site)
        ↓
7. Name Server (holds actual records)
        ↓
8. Returns IP Address
```

### 🧩 Components Explained:

#### ✅ OS:
If the browser doesn’t know the IP, your **Operating System** (Windows, macOS, Linux) checks its own cache to see if it remembers the IP address.

#### ✅ DNS Resolver:
If not found, your system asks a **DNS Resolver** (usually from your ISP). This resolver does all the querying work for you.

#### ✅ Root Servers:
The resolver now asks the **Root DNS Servers**: “Where can I find info about `.site` domains?” There are **13 root server systems** globally.

#### ✅ TLD Servers (Top-Level Domain):
These servers are in charge of specific domain extensions like `.com`, `.org`, `.in`, `.site`, etc. The resolver contacts the `.site` TLD server.

#### ✅ Authoritative Name Server:
The TLD server directs the resolver to the **name server** that holds DNS records for `lakshmireddy.site`. These records include the **IP address**.

#### ✅ Get the IP Address:
The name server replies:  
> “The IP address for `lakshmireddy.site` is `123.89.0.0`”  
The browser uses this IP to connect to the site.

---

## 🔑 Key Parts of DNS:

- **Domain Name**: e.g., `google.com`
- **Name Server**: Special servers that store DNS records.
- **DNS Record**: Instructions stored on name servers to direct traffic.

---

## 🧾 Common DNS Record Types:

### 📌 A Record (Address Record)
- Maps a domain name to an **IPv4 address**.
- Used to tell browsers where to find a website.

**Example:**
```
lakshmireddy.in → 123.89.0.0
```

---

### 📌 CNAME Record (Canonical Name)
- Points a domain/subdomain to **another domain**, not an IP.
- Often used for subdomains.

**Example:**
```
www.lakshmireddy.in → lakshmireddy.in → 123.89.0.0
```

> ⚠️ CNAME must point to a domain (not an IP) and **cannot be used on root domains** — only subdomains.

---

### 📌 MX Record (Mail Exchange)
- Used to route **emails** to mail servers for the domain.

---

### 📌 TXT Record (Text Record)
- Holds **text information** for verification (e.g., Google, Microsoft).
- Also used for **email security policies** like SPF, DKIM, and DMARC.

---

# MQ Database Notes

---

## Proxy: Forward Proxy and Reverse Proxy

A **proxy** server is an intermediate server that sits between the client and the server, forwarding requests and responses.

> Think of it as a middleman handling communication between two people.

### Forward Proxy (Client-side proxy)

A **forward proxy** sits in front of the client and forwards the client’s requests to the internet (servers).

```
Client ---> Forward Proxy ---> Internal Servers
```

- Hides the client-side IP
- Monitors outgoing traffic

### Reverse Proxy (Server-side proxy)

A **reverse proxy** sits in front of the server and handles the requests that come from the client to the backend servers.

```
Client ---> Reverse Proxy ---> Internal Servers
```

- Hides the server IP

---

## Synchronous vs Asynchronous

### Synchronous

- Each task runs one after another.
- A new task won’t start until the previous one finishes.
- Blocks the flow.
- Simple and easy to understand.
- **Not suitable for long and waiting tasks.**

Example:

```
Wait for 1 minute ---> No response ---> Raises an error
```

### Asynchronous

- Tasks can start, pause, allow others to run, and come back when ready.
- Non-blocking system.
- Improves performance.
- Can handle multiple operations (e.g., sending a message, opening new chat).

---

## Message Queue (MQ)

Used to handle asynchronous communication.

### Types of Communication

#### 1. Point-to-Point Communication

- **Sender → Receiver**  
- **Producer → Consumer**  
- Example: WhatsApp (1-on-1 messaging)

Structure:

```
Producer ---> Queue ---> Consumer
```

- Messages are stored in a queue (e.g., RabbitMQ, ActiveMQ).
- Only one consumer gets each message.
- Once delivered, the message is deleted from the queue.

#### 2. Topic-to-Subscriber (Publish/Subscribe)

- One sender publishes a message.
- Multiple subscribers receive it.
- Messages are published to a **topic** (e.g., Kafka).
- All active subscribers get a **copy** of the message.

Example:

```
Publisher → [Topic] → Subscriber 1  
                     → Subscriber 2  
                     → Subscriber 3
```



## ESC Mode

- `u` → Undo the changes
- `gg`→ It will take to top of the file
- `shift+g`→ Takes to the bottom of the file

