# AWS – Intro to Compute 💻

- **Compute** = the computer power that runs your apps.
- **On-prem** = you own physical servers. **Cloud** = AWS handles the hardware, and you just use it.
- **1. EC2** 🖥️: virtual machines (VMs). Full control over the OS and software.
- **2. Containers** 📦: your app + everything it needs, packed into one neat bundle.
  - **ECS**: Amazon's own way to run containers.
  - **EKS**: runs containers using **Kubernetes**.
- **3. Lambda (serverless)** ⚡: no servers to manage. Code runs when triggered, scales itself, and you pay only for the time it runs.
- **4. HA & Scalability** 📈: **High Availability** (always up) + **Scalability** (grows with demand). Works across EC2, containers and Lambda.

# AWS – What is EC2? 🖥️

- **EC2** = **Elastic Compute Cloud**: you **rent virtual machines** from AWS.
- It's **IaaS** (**Infrastructure as a Service**): AWS gives you the computer, and you set it up.
- Very popular: **flexible**, **scale up or down**, and **pay only for what you use** 💷.
- **What EC2 lets you do:**
  - **Rent VMs** 💻: pick the OS and set them up how you like.
  - **EBS (Elastic Block Store)** 💾: a **hard drive** for your EC2.
  - **ELB (Elastic Load Balancer)** ⚖️: **shares traffic evenly** across your EC2s so none gets overloaded.
  - **ASG (Auto Scaling Group)** 📈: **adds EC2s** when traffic goes **up** (scale out) and **removes them** when it goes **down** (scale in).
- EC2 is a **key foundation** of cloud computing.

# AWS – EC2 Configuration Options ⚙️

- **OS** 🖥️: Linux, Windows, macOS and more. Pick what your app needs.
- **CPU / cores** 🧠: how much processing power you need (more for heavy work like machine learning).
- **Memory (RAM)** 📊: more RAM = handles more data and bigger apps smoothly.
- **Storage** 💾:
  - **EBS**: a hard drive attached to one EC2.
  - **EFS**: shared storage that many EC2s can use.
  - **Instance store**: very fast, but **temporary**. The data is **lost** when the instance stops ⚠️
- **Networking** 🌐: choose network speed, plus an optional **public IP** so the internet can reach it.
- **Security Groups (SGs)** 🛡️: a **firewall** that controls who and what traffic can get in.
- **User Data (bootstrap script)** 📜: a script that **runs automatically the first time** the EC2 starts (install software, run updates).
- **Size it right**: too small = slow 🐢, too big = wasting money 💸

# AWS – EC2 User Data 📜

- **User Data** = a **script that runs automatically** when an EC2 starts for the **first time**.
- This is called **bootstrapping** (setting up the machine at launch) 🚀
- **What it can do:**
  - **Update** the system with the latest patches 🔄
  - **Install software** (e.g. Nginx, Apache) 📦
  - **Download files** (packages, config files, app code) ⬇️
- It only **runs once**, at first launch. It won't run again unless you stop the instance, change the user data and start it again.
- It runs as **root** 👑, with **full control** of the machine, so be careful what you put in it ⚠️
- **DevOps win:** set up **many EC2s automatically** with no manual logging in 🤖

# AWS – Launching & Connecting to an EC2 Instance 🚀

## 1. Launch the instance 🖥️
- Log in to AWS → **EC2** → **Instances** → **Launch instance**.
- **Name:** give it a name (e.g. `my-ec2`).
- **Image (AMI):** **Amazon Linux**, 64-bit. Keep the defaults.
- **Instance type:** `t2.micro` (**free tier** ✅).

## 2. Create a key pair 🔑
- Click **Create key pair** → give it a name → type **RSA** → format **.pem** → **Create**.
- It downloads to your **Downloads** folder. Move it to the folder you'll work from:
  - `mv ~/Downloads/my-key.pem .`
- This key is how you **log in** to the EC2 later.

## 3. Network settings 🌐
- **Create security group** ✅
- **Auto-assign public IP** → **Enable** (so you can reach it from the internet).
- **Allow SSH traffic** → from **My IP** only (safer than "Anywhere") 🛡️
- Leave everything else as default → **Launch instance**.
- Wait until it goes from **Pending** ⏳ → **Running** ✅

## 4. Connect with SSH 🔌
- Copy the instance's **Public IP**.
- In Terminal (in the folder with your key):
  - `ssh -i my-key.pem ec2-user@<PUBLIC-IP>`
  - Type `yes` when asked.
- `ec2-user` = the **default user** for Amazon Linux.

## 5. Fix the permissions error ⚠️
- First try = **permissions error** (the key is too "open").
- Check with: `ls -la`
- Fix it: `chmod 400 my-key.pem` (makes the key **read-only, just for you**).
- Run the `ssh` command again → **you're in!** 🎉
- Test it: `ls`, `touch test.txt`

## 6. Clean up 🧹 (so you don't get charged 💸)
- `exit` to leave the EC2.
- AWS → select instance → **Instance state** → **Terminate**.
- **Key Pairs** → **Actions** → **Delete** → type `delete`.
- Delete the local key file: `rm my-key.pem`


# EC2 Instance Types

An instance type is the "shape" of your virtual server: how much CPU, memory, storage and networking it gets. Pick the shape that fits your workload.

## The 6 families

| Family | What it gives you more of | Good for |
|---|---|---|
| **General purpose** | A balanced mix | Web servers, small databases, everyday workloads |
| **Compute optimised** | CPU | Heavy calculations, batch processing |
| **Memory optimised** | RAM | In-memory databases, big data processing |
| **Storage optimised** | Fast, high-throughput disk | Large datasets, databases that read and write a lot |
| **Accelerated computing** | GPUs and FPGAs | Machine learning, video processing, simulations |
| **HPC optimised** | Very powerful CPU plus fast networking | Large scientific or engineering workloads |

## Reading an instance name: `m5.2xlarge`

```
  m        5        .2xlarge
  │        │          │
class   generation   size
```

- **Class (letter):** the family.
  - `m` = general purpose
  - `c` = compute optimised
  - `r` = memory optimised (think "RAM")
  - `t` = general purpose, "burstable" (cheap, handles short CPU spikes)
- **Generation (number):** a higher number means a newer version, usually faster or more efficient. `m5` is newer than `m4`.
- **Size:** `small`, `large`, `xlarge`, `2xlarge` ... up to `32xlarge`. Bigger means more CPU and RAM, and a higher cost.

## Key takeaway

Choosing an instance type is a trade-off between performance and cost:

- **Too small:** your app runs out of resources and slows down.
- **Too big:** you pay for capacity you don't use.

Tip: start with a general purpose instance, check how much CPU and memory you actually use, then resize or switch to a specialised family if one resource is clearly the bottleneck.

# Creating an EC2 Instance with a Web Server

## Steps

1. **Open EC2:** In the AWS Console, go to **EC2 → Instances → Launch instance**.
2. **Name:** `protocol-first-instance`, with 1 instance.
3. **AMI (operating system):** Amazon Linux, 64-bit x86 (the free tier default).
4. **Instance type:** `t2.micro` (free tier eligible).
5. **Key pair:** Create a new one called `protocol-key-pair`, type RSA, format `.pem`. Save the file because you need it to SSH in later. Use `.ppk` instead if you connect with PuTTY on Windows.
6. **Network settings:**
   - Default VPC
   - Auto-assign public IP: on
   - New security group that allows **SSH (port 22)** and **HTTP (port 80)**. HTTPS is not allowed.
7. **Storage:** 8 GB gp3 (the default). By default it is deleted when the instance is terminated.
8. **User data:** Under **Advanced details**, paste the script below. It runs once, the first time the instance starts.
9. **Launch** the instance.

## User data script

```bash
#!/bin/bash
yum update -y                 # update the system (-y = auto-confirm)
yum install -y httpd          # install the Apache web server
systemctl start httpd         # start the web server now
systemctl enable httpd        # start it automatically after every reboot
echo "<h1>Hello from $(hostname)</h1>" > /var/www/html/index.html   # create the web page
```

## Testing it

- In **Instances**, click the instance to see its instance ID, public IP, private IP and security group rules.
- Open `http://<public-ip>` in a browser. Use **http, not https**, because port 443 isn't open.
- The page shows "Hello from" followed by the **private** hostname. That is the server's internal name. You reach the server through its public IP.

## Stop, start and terminate

- **Stop:** Instance state → Stop instance. The website goes down, and you stop paying for the server while it's off.
- **Start:** Instance state → Start instance. ⚠️ **You get a new public IP**, so the old address no longer works. Use the new one.
- **Terminate:** Deletes the instance permanently. It's kept in this video for later demos.

# EC2 Purchasing Options

- **On-Demand:** Pay by the second, with no commitment. Flexible but not the cheapest.
  - *Use for:* short-term or unpredictable work, such as testing a new app or a temporary project.

- **Reserved Instances (1 or 3 years):** A discount in exchange for committing to a term. The longer the term, the cheaper it is.
  - **Standard:** the biggest discount, for steady, predictable workloads.
  - **Convertible:** lets you change instance type over time, for a smaller discount.
  - *Use for:* production apps that will run for a long time.

- **Savings Plans (1 or 3 years):** A discount for committing to a set amount of usage. More flexible than Reserved because it works across instance types and regions.
  - *Use for:* long-term savings without being tied to one instance type.

- **Spot Instances:** Unused AWS capacity at a big discount. ⚠️ AWS can take the instance back at any time.
  - *Use for:* work that can be interrupted, such as batch processing or data analysis.

- **Dedicated Hosts:** You rent a whole physical server, with full control and visibility of the hardware.
  - *Use for:* compliance, or software licences tied to a specific server.

- **Dedicated Instances:** Your instances run on hardware that no other AWS customer shares, but you don't control the physical server.
  - *Use for:* security or compliance needs that require isolated hardware.

- **Capacity Reservations:** Guarantees capacity in a specific Availability Zone (AZ) for as long as you need it.
  - *Use for:* critical workloads that must run in a certain AZ, especially at busy times.

## Quick rule of thumb

| Situation | Best option |
|---|---|
| Testing or experimenting | On-Demand |
| Steady, long-term workload | Reserved Instances or Savings Plans |
| Cheap work that can be interrupted | Spot |
| Compliance or licensing | Dedicated Host or Dedicated Instance |
| Must have capacity in one AZ | Capacity Reservation |

# EC2 Purchasing Options in the Console

The EC2 console's left menu has a page for each purchasing option:

- **Spot Requests:** Request spare capacity cheaply.
  - To create a **Spot Fleet request**, you choose the AMI, the capacity you need, the network settings, the instance type requirements and an allocation strategy.
  - AWS then shows you an **estimated price** before you commit.
- **Savings Plans:** Browse and compare the plans available.
- **Reserved Instances:** Buy one by choosing the instance type, term and payment option.
- **Dedicated Hosts:** Allocate a whole physical server for yourself.
- **Capacity Reservations:** Reserve capacity in a specific AZ.

## Finding instance types

- Go to **EC2 → Instance Types** to see every type, such as `t2`, `t3`, `m3` and `m7`.
- Use the **search bar** to filter, for example type `m3` for one type or `m` for the whole general-purpose family.
- **Instance type finder:** describe your workload (for example machine learning and high performance), and AWS suggests suitable instance types with their details.
- Once you've picked a type, use it when you **launch an instance**.

