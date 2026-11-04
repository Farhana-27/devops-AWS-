
# Scalability and High Availability (HA)

## Scalability

- Your system can **handle more load** by adapting to demand.

| Type | What it means | Example |
|---|---|---|
| **Vertical** (scale up/down) | Make **one machine more powerful**: more CPU, RAM or storage | Upgrade `t2.micro` → `t2.large` |
| **Horizontal** (scale out/in) | **Add more machines** to share the load | 1 server → 5 servers |

- Horizontal scaling is often called **elasticity**, because you can scale **out and in** as demand changes.

## High Availability (HA)

- Your system **keeps running even when parts fail**.

## Scalability vs HA

| | Scalability | High Availability |
|---|---|---|
| About | Handling **more load** | **Staying up** when things fail |

- They're related but different. A system can be highly available but not scale well, and the other way round.

## 📞 Call centre example

- **Vertical:** give one person a better phone and a faster computer so they can take more calls.
- **Horizontal:** hire more people so no one is overwhelmed.
- **High availability:** keep people **on standby**, so the call centre keeps running if someone is sick or quits.

# Vertical Scalability

## What is it?

- **Make the same server bigger** (more CPU, RAM, storage) instead of adding more servers.
- Example: `t2.micro` → `t2.large`. It's the same server, with more power.

## When to use it

- Common for **non-distributed systems**, especially **databases**.
  - For example, **RDS** and **ElastiCache**: upgrade the instance size to handle bigger workloads or more complex queries.
- Often the **first step** when you need better performance.

## Limit

- ⚠️ Limited by the **hardware**. Once you reach the **largest instance type**, you can't scale up any further.
- Beyond that, you need **horizontal scaling** (more servers).

## 👔 Analogy: promotion

- A **junior operator** (`t2.micro`) gets promoted to **senior operator** (`t2.large`) with more tools.
- But one person can only do so much. Eventually you need to **hire more people** (horizontal scaling).

# Horizontal Scalability

## What is it?

- **Add more instances** to handle more load, instead of making one bigger.
- The core idea behind **distributed systems**: many smaller machines each do **part of the work**.

## Why it's great

- 🔄 **Elastic:** scale **out** when traffic spikes and scale **in** when it drops.
  - For example, a website gets a sudden traffic spike, so you add instances, then remove them afterwards.
- 🛡️ **Resilient:** if one instance fails, the others keep the system running.
- ☁️ **Easy in the cloud:** EC2 makes adding instances simple.
- 🤖 **Can be automated** with **Auto Scaling Groups**.
- Ideal for **unpredictable or changing workloads**.

## 📞 Call centre analogy

- **Vertical:** one person answering phones can only handle so much.
- **Horizontal:** bring in **more junior operators**, each one an EC2 instance. Each takes a share of the calls, so **the more people you add, the more calls you can handle**.

## Vertical vs Horizontal

| | Vertical | Horizontal |
|---|---|---|
| How | Bigger instance | More instances |
| Limit | Largest instance type | Very high |
| If one fails | ❌ Everything goes down | ✅ The others keep running |
| Common for | Databases | Web apps, modern cloud apps |

# High Availability (HA)

## What is it?

- Running your app in **multiple locations**, so if one part fails, another takes over.
- Goes hand in hand with **horizontal scaling**, because you need multiple instances in different places.

## How it's done in AWS

- Run your app across **at least 2 Availability Zones (AZs)**.
- **Goal:** survive the loss of a data centre. If one AZ goes down, the app keeps running in another **with no downtime**.

## Two types of HA

| Type | How it works | Example |
|---|---|---|
| **Passive** | One main system runs, with a **backup on standby** in another AZ. If the main one fails, AWS switches to the backup automatically | **RDS Multi-AZ**: primary database in AZ-A, standby in AZ-B |
| **Active** | **All instances share the work** across AZs. If one fails, traffic goes to the healthy ones | EC2 instances in several AZs behind a load balancer |

## 📞 Call centre analogy

- The call centre has **two buildings in different places**.
- If one building has a power cut or network problem, the **other building keeps answering calls**.
- The service stays up no matter what happens to one location.

# Scalability and High Availability for EC2

## 1. Vertical scaling (scale up)

- Make the instance **bigger**: more CPU, RAM or storage.
- From tiny to huge:

| Instance | RAM | vCPUs |
|---|---|---|
| `t2.nano` | 0.5 GB | 1 |
| `u-12tb1.metal` | 12.3 TB | 448 |

- ⚠️ There's always a **limit**. Once you hit it, scale horizontally.

## 2. Horizontal scaling (scale out)

- **Add more instances** instead of a bigger one.
- Done with an **Auto Scaling Group (ASG)**, which **adds or removes instances automatically** based on demand.
  - A traffic spike means more instances. When traffic drops, they're removed.

## 3. Load balancer

- **Spreads incoming traffic** across all the instances.
- Makes sure **no single instance is overloaded**.

## 4. High availability (multi-AZ)

- Run instances across **multiple AZs**.
- **ASG with multiple AZs:** spreads instances across the zones.
- **Load balancer with multiple AZs:** sends traffic to instances in every zone.
- If an instance or a **whole AZ** fails, traffic is **automatically redirected** to the healthy ones.

## Putting it all together

```
Start with one instance
   ↓ grow it if needed        (vertical scaling)
Add more instances
   ↓ automatically with ASG   (horizontal scaling)
Spread them across AZs
   ↓ behind a load balancer   (high availability)
= Flexible and resilient app ✅
```

```
                 Users
                   │
            [Load Balancer]
           ┌───────┴───────┐
        AZ-A              AZ-B
     [EC2] [EC2]       [EC2] [EC2]
     └─────── ASG (adds/removes) ───────┘
```

# Load Balancing

## What is it?

- **Spreads traffic across multiple servers or instances**, instead of sending every user to one.
- 🚦 Like a **traffic cop** directing requests to different servers.

## 🍳 Restaurant analogy

- **One chef** with every order at once is overwhelmed.
- **A team of chefs** (EC2 instances) plus **a manager** (the load balancer) handing each order to the next free chef means faster service and no one is overloaded.

## How it works (Elastic Load Balancer, ELB)

- Sits **between users and your EC2 instances**.
- Forwards each request to the instances **downstream** (behind it).
- 🩺 **Health checks:** constantly checks which instances are **healthy**.
- If an instance fails, traffic is **automatically redirected** to the healthy ones, with nothing for you to do.

```
              Users
                │
              [ELB]   ← health checks
         ┌──────┼──────┐
       [EC2]  [EC2]  [EC2 ❌]
         ✅      ✅    (no traffic sent)
```

## Reverse proxy

- Like a load balancer, it sits between users and servers, but it can do **more than spread traffic**.
- In AWS, the **Application Load Balancer (ALB)** has reverse proxy features:
  - Routes traffic based on the **content of the request**, such as the URL path.
  - Sends requests to **different services or microservices**.

## Why it matters

- ✅ **Scalable:** handles growing traffic.
- ✅ **Resilient:** users don't notice when an instance fails.

# Why Use a Load Balancer?

| Feature | What it does |
|---|---|
| ⚖️ **Spreads the load** | Shares incoming traffic across many instances so none is overloaded |
| 🌐 **Single point of access (DNS)** | Users only need the load balancer's **DNS name**, not each instance's address |
| 🛠️ **Handles failures** | Stops sending traffic to unhealthy instances. Users don't notice |
| 🩺 **Regular health checks** | Constantly checks every instance to know which ones are healthy |
| 🔒 **SSL termination (HTTPS)** | The load balancer handles **encrypting and decrypting** HTTPS, so your instances can focus on the app |
| 🍪 **Sticky sessions** | Uses **cookies** to send a user back to the **same instance** each time when needed |
| 🏢 **High availability across AZs** | Spreads traffic across **multiple AZs**, so the app stays up if one zone has problems |
| 🚧 **Separates public and private traffic** | Keeps **user-facing** traffic apart from **internal** traffic for better security |

> 💡 **Takeaway:** A load balancer does much more than spread traffic. It handles failover, improves security and keeps your app highly available.

# Elastic Load Balancer (ELB): A Managed Load Balancer

## What "managed" means

- **AWS does the heavy lifting** for you.
- ✅ **AWS guarantees it works.** It's built and maintained by AWS.
- ✅ **AWS handles upgrades, maintenance and high availability.** No downtime for updates on your side.
- ✅ **Less to configure.** AWS provides the basics; you just set the rules and routing.

## DIY vs managed

| | DIY (Nginx, HAProxy, Traefik) | Managed (ELB) |
|---|---|---|
| Cost | 💰 Cheaper upfront | 💰💰 Costs more |
| Effort | 😓 You handle maintenance, monitoring, scaling and failover | 😌 AWS handles it all |
| Best for | Full control, tight budgets | Saving time, reliability |

## Integrates with other AWS services

| Service | What it adds |
|---|---|
| **EC2 & Auto Scaling Groups** | Automatically sends traffic to new instances as they're added |
| **ACM** (Certificate Manager) | Provides SSL certificates, and ELB handles HTTPS |
| **CloudWatch** | Monitors the load balancer's performance and health |
| **Route 53** | DNS routing |
| **WAF** | Security (web application firewall) |
| **Global Accelerator** | Better performance across regions |

> 💡 **Takeaway:** ELB costs more than DIY, but it's reliable, low-maintenance and deeply integrated with AWS, so it saves time in the long run.

# Load Balancer Health Checks

## What are they?

- How the load balancer knows whether an instance is **healthy** and able to respond.
- ⚠️ Without them, the load balancer could keep sending traffic to an instance that's **down**.

## How they work

- The load balancer sends a request to a **port** and **route** on each instance.
  - Example: `HTTP` request to port **4567**, route **`/health`**

| Response | Result |
|---|---|
| ✅ **200 OK** | **Healthy**, keeps getting traffic |
| ❌ **Anything else** (or no reply) | **Unhealthy**, gets no traffic |

## Automatic failover

- Health checks run **constantly and automatically**, with nothing for you to do.
- An unhealthy instance gets **no traffic** until it **passes the health check again**.
- Users are only sent to instances that can handle their requests, so **their experience isn't interrupted**.

## Example

```
         [Load Balancer]
   GET :4567/health every few seconds
      ┌───────┼────────┐
   [EC2 ✅]  [EC2 ✅]  [EC2 ❌ high CPU, no 200 OK]
   traffic   traffic   no traffic until healthy again
```

# Types of AWS Load Balancers

| Load balancer | Released | OSI layer | Traffic | Best for |
|---|---|---|---|---|
| **Classic (CLB)** | 2009 | 4 & 7 | HTTP, HTTPS, TCP | ⚠️ Old generation, avoid for new projects |
| **Application (ALB)** ⭐ | 2016 | **7** (Application) | HTTP, HTTPS, WebSocket | Web apps, microservices, containers |
| **Network (NLB)** | 2017 | **4** (Transport) | TCP, UDP | Very high performance, **low latency** |
| **Gateway (GWLB)** | 2020 | **3** (Network) | IP | Third-party network appliances such as firewalls |

## Classic Load Balancer (CLB)

- The **original** AWS load balancer. Simple, but missing modern features.

## Application Load Balancer (ALB)

- The **most popular** one.
- **Layer 7**, so it's "smart": it can route based on the **content of the request**:
  - URLs, headers, query parameters, cookies
- Supports **WebSockets**.
- Great for **microservices and containers**.

## Network Load Balancer (NLB)

- **Layer 4**, built for **TCP and UDP**.
- Handles **millions of requests per second** with **very low latency**.
- Examples: real-time gaming, high-frequency trading.

## Gateway Load Balancer (GWLB)

- **Layer 3**, works with the **IP** protocol.
- Deploys and scales **third-party network appliances** in your VPC:
  - Firewalls, intrusion detection systems, traffic analysers.

## Internal vs external

- **External (public):** handles traffic from the **internet**.
- **Internal (private):** routes traffic **inside your VPC**.

## Which one to choose?

| You need... | Use |
|---|---|
| A normal web app, content-based routing, WebSockets | **ALB** |
| Large volumes of TCP/UDP with very low latency | **NLB** |
| Firewalls or other network security appliances | **GWLB** |
| A new project | ❌ Not Classic. AWS recommends the newer ones |

# Security Groups for Load Balancers

Two security groups work together so that **users can only reach the load balancer**, and **only the load balancer can reach the EC2 instances**.

## 1. Load balancer security group (public)

Allows anyone on the internet to reach the load balancer.

| Type | Port | Source | Meaning |
|---|---|---|---|
| HTTP | 80 | `0.0.0.0/0` | Unencrypted web traffic from anywhere |
| HTTPS | 443 | `0.0.0.0/0` | Encrypted (SSL/TLS) traffic from anywhere |

## 2. Application security group (EC2 instances)

Only allows traffic **from the load balancer**.

| Type | Port | Source | Meaning |
|---|---|---|---|
| HTTP | 80 | **Load balancer's security group** (e.g. `sg-lb123`) | Only the load balancer can connect |

- This uses **security group referencing**: the source is a security group, not an IP.

## How it flows

```
 Users (internet)
       │  ports 80 / 443  ✅
       ▼
 [Load Balancer]   ← SG-LB: allows 0.0.0.0/0
       │  port 80  ✅
       ▼
 [EC2 instances]   ← SG-App: allows ONLY SG-LB

 Users ──X──► EC2 directly  ❌ blocked
```

## Why do this?

- 🛡️ EC2 instances are **shielded from direct internet access**.
- The load balancer is a **protective barrier** that forwards only legitimate traffic.
- A **very common** pattern in cloud architecture: secure and scalable.

> 🏢 **Analogy:** the load balancer is the **front door** of a building. Customers come in through it, but they can't walk into every room. The front door decides which rooms (instances) they reach, and each room has its own restricted access.

# Application Load Balancer (ALB)

## Layer 7 (application layer)

- Works with **HTTP and HTTPS** traffic.
- 🧠 **Smart:** it understands what's **inside the request**:
  - URLs, headers, cookies, query strings and more
- So it can make routing decisions based on the request's content.

## Target groups

- An ALB sends traffic to **target groups** (groups of instances or apps).
- Can load balance across:
  - **Multiple apps on different machines**
  - **Multiple apps on the same machine**, which is great for **containers** (e.g. several apps on one EC2 instance or in **ECS**)

```
                  [ALB]
          ┌─────────┼─────────┐
   Target Group A        Target Group B
   (users app)           (orders app)
   [EC2] [EC2]           [EC2] [EC2]
```

## Modern protocols

| Protocol | What it gives you |
|---|---|
| **HTTP/2** | A faster, more efficient HTTP with more connections and better performance |
| **WebSockets** | **Real-time** two-way communication, e.g. chat apps and live dashboards |

# ALB: Advanced Routing Features

## Route to different target groups

- One ALB can send traffic to **multiple target groups**.
- A target group can contain **EC2 instances, Lambda functions or containers**.

## Routing options

| Routing type | Based on | Example |
|---|---|---|
| **Path-based** | The URL **path** | `/users` → Users service, `/posts` → Posts service |
| **Host-based** | The **host name (domain)** | `blog.example.com` → Blog, `news.example.com` → News |
| **Query string** | Values in the URL | `?question_id=123` → a specific target group |
| **Header-based** | Request **headers** | Mobile users → mobile app servers, desktop users → desktop servers |

- 🌐 Host-based routing lets you run **multiple domains on one ALB**.
- 📱 Header-based routing is great for **device-specific** or **personalised** experiences.

## Containers and ECS

- A natural fit for **microservices and containers** (Docker, Amazon ECS).
- **Dynamic port mapping (ECS):** containers can run on **different ports** on the same machine, and the ALB automatically knows where to send traffic as they scale.

## One ALB for many apps

| Classic Load Balancer (CLB) | Application Load Balancer (ALB) |
|---|---|
| ❌ **One load balancer per application** | ✅ **One load balancer for many applications** |
| More cost, more to manage | 💰 Cheaper and simpler |

## Example: 3 microservices, 1 ALB

```
                    [ALB]
       ┌──────────────┼──────────────┐
    /users          /posts        /comments
       ▼              ▼              ▼
 [Users service] [Posts service] [Comments service]
```

# How an ALB Routes HTTP Traffic

## The flow

1. **Users** send HTTP/HTTPS requests to an **external (public) ALB**.
2. The ALB **looks at each request** (path, host or other rules).
3. It sends the request to the right **target group**.
4. The target group's resources (**EC2, ECS or Lambda**) process the request.

## Target groups for each service

- Each target group usually handles **one service**:
  - **Users target group:** login, profile management
  - **Search target group:** product searches
- 🧱 Services are **kept separate**, so one doesn't interfere with another and each can **scale on its own**.

## Health checks

- The ALB checks every instance in each target group.
- ❌ An instance fails its check → the ALB **stops sending it traffic**.
- ✅ Requests go to the **healthy** instances in that group instead.

## Example

```
                 Users
                   │  HTTP/HTTPS
                   ▼
           [External ALB]
        ┌──────────┴───────────┐
   path: /users           path: /search
        ▼                      ▼
 Target Group: Users    Target Group: Search
 [EC2] [EC2]            [EC2] [EC2]
 (profile updates)      (product searches)
```

> 💡 One ALB, many services. Ideal for **microservices**.

# ALB Target Groups

## What are they?

- **Groups of resources** that the ALB sends traffic to, the **destinations** for incoming requests.
- Each target group is usually tied to **one service or app**, so each part of your system can **scale on its own**.

## Types of targets

| Target type | How it works | Good for |
|---|---|---|
| **EC2 instances** | Can be managed by an **Auto Scaling Group** that adds or removes instances with load. The ALB balances requests between them | Traditional apps |
| **ECS tasks** | The ALB routes traffic to **containers** | Microservices, container apps |
| **Lambda functions** | The ALB turns the HTTP request into a **JSON event** for the Lambda function | **Serverless** apps with no servers to manage |
| **IP addresses** | Routes to IPs directly. ⚠️ They **must be private IPs** | Servers on your own network, or resources without an instance ID |

## Multiple target groups

- One ALB can route to **many target groups**, so it can serve several services or apps.
  - For example: one target group for **user requests**, another for **search**.

## Health checks

- Done **per target group**.
- The ALB regularly checks each resource (instance, ECS task, Lambda function and so on).
- ❌ Unhealthy → **no traffic** until it's healthy again.
- ✅ Users are always sent to **healthy** targets.

# ALB: Host Names and Client IP Headers

## Fixed host name

- AWS gives every ALB a **fixed DNS name** that it creates and maintains for you:
  ```
  my-alb-1234567890.eu-west-2.elb.amazonaws.com
  ```
- Clients use this name to reach your services.
- 🌐 **Want your own domain** (e.g. `app.example.com`)? Use **Route 53** to point it at the ALB's DNS name.

## Your servers don't see the client's IP ⚠️

- The client's connection **ends at the ALB**. The ALB then opens a **new connection** to your EC2 instance.
- So your EC2 instance sees the **ALB's private IP**, not the client's real IP.

```
Client (12.34.56.78) ──► [ALB] ──► EC2 sees: ALB's private IP ❌
                                   Header X-Forwarded-For: 12.34.56.78 ✅
```

## X-Forwarded headers

The ALB passes the client's details along in special **HTTP headers**:

| Header | Contains |
|---|---|
| `X-Forwarded-For` | The client's **real IP address** |
| `X-Forwarded-Port` | The **port** the client connected on |
| `X-Forwarded-Proto` | The **protocol** the client used (HTTP or HTTPS) |

## Why it matters

- You need the real client IP for:
  - 🌍 **Geolocation**
  - 🚦 **Rate limiting**
  - 🔍 **Security auditing and logging**
- ⚙️ Make sure your **app is set up to read these headers**, or your logs will only show the ALB's IP.


