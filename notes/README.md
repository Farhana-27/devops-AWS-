# AWS – History (Intro Video)

## What is AWS?
- **AWS** = **Amazon Web Services**.
- It lets other companies **rent Amazon's computers, storage and tools over the internet**. This is called **cloud computing**.
- Instead of buying and running their own servers, businesses pay Amazon to use theirs.

## How it started
- Amazon was mainly an **online shop**.
- To run that shop, Amazon built a huge, powerful system of computers behind the scenes. That system is called **infrastructure**.
- Amazon realised this system was one of its **biggest strengths**.
- 💡 **Big idea:** *"Why not rent this system out to other companies?"*

## Timeline

```
2002 ── AWS started inside Amazon (only Amazon used it)
  │
2003 ── Idea: offer it to other companies as a paid service
  │
2004 ── AWS launched to the public with its first service: SQS
  │
2006 ── Big relaunch with S3, EC2 and SQS (the year AWS took off)
  │
2007 ── Launched in Europe, so businesses worldwide could use it
```

## The 3 key early services (plain English)

| Service | Full name | What it does (simple version) |
|---------|-----------|-------------------------------|
| **SQS** | Simple Queue Service | A **waiting line for messages**. One part of an app drops a message in, and another part picks it up when it's ready, so nothing gets lost or overloaded. |
| **S3** | Simple Storage Service | **Online storage for files**, like Google Drive but for businesses and apps. |
| **EC2** | Elastic Compute Cloud | **A computer you rent online**. "Elastic" means you can make it bigger or smaller whenever you need. |

## Key takeaway
> AWS started as a tool built **only for Amazon** and became the **backbone of cloud computing** today.

## Memory trick
**2002** Inside → **2003** Idea → **2004** SQS → **2006** S3 + EC2 → **2007** Europe

# AWS – In Numbers (How Big Is AWS?)

## The main point
- AWS isn't just big, it's **massive**.
- It's the **biggest company in cloud computing**. In other words, it's the No.1 place businesses go to rent computers, storage and tools online.

## Key numbers (2019)

| What | Number | What it means (simple version) |
|------|--------|--------------------------------|
| 💰 **Revenue** | **$35 billion** | The money AWS made from selling its cloud services in one year. |
| 📊 **Market share** | **47%** | Almost **half** of all cloud business went to AWS. |
| 🥈 **Microsoft (2nd place)** | **22%** | The next biggest competitor had **less than half** of AWS's share. |
| 🏆 **Years at the top** | **9 years in a row** | AWS has been the **leader** in cloud for nine consecutive years (when the video was made). |
| 👥 **Active users** | **1 million+** | Over a million customers use AWS. |

> **Jargon buster**
> - **Revenue** = the total money a company brings in from sales.
> - **Market share** = the slice of the whole market that one company owns.

## Cloud market share in 2019 (simple diagram)

```
AWS        ███████████████████████████████  47%
Microsoft  ██████████████                   22%
Others     ████████████████████             31%
```
*(I worked out "Others" as 100% − 47% − 22% = 31%. The video doesn't give this number.)*

## Who uses AWS?
- **Not just big companies.** Everyone from small **startups** to huge **enterprises** (very large businesses) uses it.
- They use AWS to **grow (scale)** and **build new things (innovate)** faster.

## Key takeaway
> AWS is the **No.1 cloud provider**: it had the most money, the biggest share of the market and over a million users, and it's still growing.

## Memory trick
**$35B** money → **47%** of the market → **2x** Microsoft → **9** years on top → **1M+** users

# AWS – Use Cases (What Can You Do With AWS?)

## The main point
- AWS isn't just about history and numbers. It's about **what you can actually do with it**.
- AWS is **versatile**, meaning it can be used for lots of different things.

## What AWS lets you do
- Build **sophisticated, scalable applications**.
  - **Sophisticated** = advanced, with lots of features.
  - **Scalable** = it can grow (or shrink) as more (or fewer) people use it.
- It works whether you're **starting small or going big**. AWS gives you **flexibility** (you can change things easily) and **performance** (it runs fast and reliably).

## Industries that use AWS
AWS isn't stuck in one type of business. It's used in:
- 💻 **IT** (technology companies)
- 🏥 **Healthcare**
- 🎬 **Entertainment**
- 🎮 **Gaming**

## How companies use AWS (simple diagram)

```
                        AWS
                         │
     ┌───────────────────┼───────────────────┐
     │                   │                   │
 ENTERPRISE IT     WEB & MOBILE APPS       GAMING
     │                   │                   │
 • Backup storage  • Websites             • Hosting games
 • Big data        • Social media apps    • Multiplayer
   analytics       • Mobile apps            online play
```

> **Jargon buster**
> - **Enterprise** = a very large business.
> - **Backup storage** = keeping spare copies of data in case the original is lost.
> - **Big data analytics** = making sense of huge amounts of data to spot patterns and make decisions.
> - **Hosting** = running something (like a website or game) on a server so people can use it over the internet.

## Big brands that use AWS

| Brand | What they do | How AWS helps |
|-------|--------------|---------------|
| 🎬 **Netflix** | Streams shows and movies | Handles **huge amounts of data** to deliver video to viewers. |
| 📁 **Dropbox** | Online file storage | Provides **cloud storage** for millions of users. |
| 🎮 **Activision** | Video games | Runs **multiplayer games** smoothly for players worldwide. |
| 🍔 **McDonald's** | Fast food | Helps **scale (grow) their global operations**. |

## Key takeaway
> AWS is **flexible**, **powerful** and **trusted** by some of the biggest companies in many different industries.

## Memory trick
**N**etflix, **D**ropbox, **A**ctivision, **M**cDonald's → "**N**ever **D**oubt **A**WS **M**ate"# AWS – Global Infrastructure (Chapter Intro)

## The main point
- This chapter explains **the physical setup that makes AWS work**: where Amazon's computers actually are around the world.
- It's a bit more technical, but it's an **important chapter**.

> **Jargon buster**
> - **Infrastructure** = the physical equipment (buildings, computers, cables) behind a service.
> - **Data centre** = a big building full of computers (servers) that run websites and apps.

---

## 1. Regions 🌍
- A **Region** is a **physical location in the world** where AWS has data centres.
- Think of it as a **large group of AWS buildings in one area**.
- AWS has Regions in **North America, Europe, Asia, Australia** and more.
- **Why?** So your apps can be **close to your customers**, wherever they are.

### How do you choose a Region? (3 things to think about)

| Factor | What it means (simple version) |
|--------|--------------------------------|
| ⚡ **Latency** | **Speed/delay.** Pick the Region **closest to your users** so things load fast. |
| 📜 **Compliance** | **Following the rules.** Some countries or industries (or governments) have strict laws about **where data must be stored**. |
| 💷 **Pricing** | **Cost.** Prices can be **different in each Region**, so this can affect your choice. |

---

## 2. Availability Zones (AZs) 🏢
- Inside **each Region**, there are **several Availability Zones** (called **AZs**).
- An **AZ** = **one data centre or a group of data centres** within a Region.
- **Why have more than one?** If you spread your app across several AZs and **one AZ breaks down**, your app **stays online** using the others.

> **Jargon buster**
> - **High availability** = your app is almost always up and running.
> - **Fault tolerance** = your app keeps working even when something breaks.

---

## 3. Edge Locations (Points of Presence) 📍
- **Edge locations** are **smaller sites spread around the world**, even closer to users.
- They are part of AWS's **CDN (Content Delivery Network)**, which is covered later in the course.
- They **store copies of content** (like videos or web pages) **near users**, so it loads **faster**.
- Example: when you stream a video, it may come from a **nearby edge location** instead of a faraway data centre, which is why it's quick and smooth.

> **Jargon buster**
> - **Caching** = keeping a saved copy of something nearby so it can be delivered faster next time.
> - **CDN** = a network of locations that delivers content to users quickly.

---

## How it all fits together (simple diagram)

```
                    🌍 THE WORLD
                         │
       ┌─────────────────┼─────────────────┐
       │                 │                 │
   REGION            REGION            REGION
  (e.g. Europe)    (e.g. N. America)  (e.g. Asia)
       │
  ┌────┼────┐
  │    │    │
 AZ   AZ   AZ      ← Each AZ = one or more data centres
 🏢   🏢   🏢        If one breaks, the others keep your app running

 📍  📍  📍  📍  📍  ← EDGE LOCATIONS (lots of small sites near users)
                       They keep copies of content so it loads faster
```

**Biggest → smallest:** World → Regions → Availability Zones → Data centres

---

## 4. The AWS Console 🖥️
- The **AWS Console** is the **website where you manage everything in AWS**.
- From here you can do things like:
  - Launch **EC2 instances** (rent a computer online)
  - Set up **S3 buckets** (online storage folders for files)
- There will be **hands-on practice** later in the course.

---

## Key takeaway
> AWS has data centres all over the world, organised into **Regions** → **Availability Zones**, plus **Edge Locations** for fast delivery. You pick a Region based on **speed, rules and price**, and manage it all from the **AWS Console**.

## Memory tricks
- **Choosing a Region = L.C.P** → **L**atency, **C**ompliance, **P**ricing → "**L**ondon **C**osts **P**ounds"
- **Region = city**, **AZ = buildings in that city**, **Edge location = local corner shop** (small, close to you, quick to grab things from)

# AWS – Availability Zones (AZs)

## What is an Availability Zone? 🏢
- An **Availability Zone (AZ)** = a **separate data centre** (or group of data centres) **inside a Region**.
- AZs are one of the main reasons AWS is **super reliable**.
- A Region is **not one big data centre**. It's made up of **several AZs**, usually **between 3 and 6**.

> **Jargon buster**
> - **Data centre** = a big building full of computers (servers).
> - **Discrete** = separate, standing on its own.
> - **Outage** = when something stops working (e.g. a power cut).

---

## How AZs are named 🏷️
AZs take the **Region code** and add a **letter** on the end.

**Example: the London Region (`eu-west-2`)**

| AZ name | What it is |
|---------|------------|
| `eu-west-2a` | London AZ "a" |
| `eu-west-2b` | London AZ "b" |
| `eu-west-2c` | London AZ "c" |

```
 eu-west-2  +  a   =  eu-west-2a
 └─Region─┘   └AZ letter┘
```

---

## Separate... but connected 🔌

### 1. Separate (isolated) 🛡️
- Each AZ has its **own**:
  - ⚡ **Power**
  - 🌐 **Networking**
  - 🔗 **Connectivity** (its own internet links)
- They are **physically apart** from each other.
- So if a **natural disaster** or **power cut** hits **one AZ**, the **others keep running**.

### 2. Connected 🚀
- Even though they're apart, AZs are linked by **very fast connections**:
  - **High bandwidth** = lots of data can travel at once (a wide motorway 🛣️).
  - **Low latency** = very little delay (cars move fast, no traffic jams).
- So the AZs can **talk to each other super quickly**.

---

## Simple diagram

```
┌──────────────── REGION: London (eu-west-2) ────────────────┐
│                                                             │
│   ┌────────────┐     ┌────────────┐     ┌────────────┐      │
│   │ eu-west-2a │◄───►│ eu-west-2b │◄───►│ eu-west-2c │      │
│   │    🏢      │     │    🏢      │     │    🏢      │      │
│   │ own ⚡ 🌐  │     │ own ⚡ 🌐  │     │ own ⚡ 🌐  │      │
│   └────────────┘     └────────────┘     └────────────┘      │
│          ▲  fast, low-delay connections between them  ▲     │
└─────────────────────────────────────────────────────────────┘
```

### What happens if one AZ goes down?
```
  eu-west-2a     eu-west-2b     eu-west-2c
     🏢              🏢             🏢
     ✅              ❌             ✅
  (still up)     (power cut!)   (still up)

  → Your app keeps running on 2a and 2c 🎉
```

---

## Why this matters for YOUR apps 💡
- If you **spread your app across several AZs**, then:
  - One AZ has a problem → **your app stays online** using the others.
- This gives you an **extra layer of protection and reliability**.

> **Jargon buster**
> - **High availability** = your app is almost always up and running.
> - **Fault tolerant** = your app keeps working even when something breaks.
> - **Resilient** = able to recover quickly from problems.
> - **Deploying** = putting your app live on servers.

---

## Key takeaway
> Each **Region** has **3–6 AZs**. Each AZ is a **separate data centre** with its **own power and network**, but they're all **linked with fast connections**. Spread your app across **multiple AZs** so it **stays up even if one fails**.

## Memory tricks
- **Each AZ has its own P.N.C** → **P**ower, **N**etworking, **C**onnectivity
  → "**P**lease **N**ever **C**rash" 💥
- **Region = a city 🏙️, AZs = separate buildings in that city 🏢🏢🏢.** If one building has a power cut, the others still have the lights on 💡
- **Don't put all your eggs in one basket 🥚🧺**: spread your app across **multiple AZs**!

# AWS – Points of Presence (Edge Locations)

## What are Edge Locations? 📍
- **Points of Presence** = **Edge Locations** (two names for the same thing).
- They are **small AWS sites spread all over the world**.
- Their job is to **deliver content (videos, web pages, images) to users as fast as possible**, wherever those users are.

> **Jargon buster**
> - **Content** = anything users see or download, e.g. videos, pictures, web pages.
> - **End user** = the actual person using your website or app.
> - **Regional cache** = a slightly bigger storage site that sits between the main Region and the edge locations, holding extra copies of content.

---

## The numbers 🔢 (at the time of the video)

| What | Number |
|------|--------|
| 📍 **Points of Presence** (edge locations + regional caches) | **400+** |
| 🏙️ **Cities** | **90+** |
| 🌍 **Countries** | **40+** |

---

## Why do they matter? ⚡ It's all about LATENCY
- **Latency** = **delay**: how long it takes for data to reach the user.
- **Closer edge location = less travel = faster loading.**
- Instead of data travelling **halfway across the world**, it comes from an edge location **near the user**.
- Result: a **faster, smoother experience** for users. 🎉

### Simple diagram: without vs with an edge location

```
❌ WITHOUT an edge location
 👤 User in London ─────────── long journey 🐢 ───────────► 🏢 Main data centre (USA)
                                (slow, more delay)

✅ WITH an edge location
 👤 User in London ──► 📍 Edge location (London) ⚡
                        (copy of the content is already here, so it's fast!)
```

---

## The warehouse analogy 📦
Think of it like a big online shop:

```
        🏭 HEADQUARTERS (main AWS Region, far away)
                         │
        ┌────────────────┼────────────────┐
        ▼                ▼                ▼
   📦 Local          📦 Local          📦 Local
   warehouse        warehouse         warehouse
   (Edge, UK)       (Edge, France)    (Edge, Japan)
        │                │                │
        ▼                ▼                ▼
      👤 👤             👤 👤             👤 👤
   Customers get their delivery from the NEAREST warehouse 🚚💨
```

- **Headquarters** = the main AWS Region (can be far away).
- **Local warehouses** = edge locations that keep **copies** of your data close to customers.
- Customers get things **quicker** because it doesn't have to come from HQ every time.

### Where is this extra useful? 🚀
Any app where **speed really matters**:
- 🎬 **Video streaming** (e.g. Netflix)
- 🎮 **Gaming**
- ⚡ Any **real-time** app

---

## How to explore AWS's global map yourself 🗺️
1. Search Google for **"AWS global infrastructure"**.
2. Open the official AWS page (aws.amazon.com).
3. You'll see a **map** showing:
   - **Regions** 🌍
   - **Availability Zones (AZs)** 🏢
   - **Edge locations** 📍
4. **Hover over a Region** (e.g. **Europe → London**) to see:
   - When it **launched**
   - How many **AZs** it has
5. Areas covered include North America, Europe, Middle East, Africa, Asia Pacific and Australia.

---

## How it ALL fits together (recap of the chapter so far)

```
🌍 REGION           = a city 🏙️             (e.g. London, eu-west-2)
   └─ 🏢 AZs         = buildings in that city (eu-west-2a, 2b, 2c)
📍 EDGE LOCATIONS   = local corner shops 🏪   (lots of them, close to users, super quick)
```

---

## Key takeaway
> **Edge locations** are **400+ small AWS sites worldwide** that keep **copies of content near users**. This **cuts latency (delay)** so websites, videos and games load **faster**.

## Memory tricks
- **The numbers = "4-9-4"** → **4**00+ locations, **9**0+ cities, **4**0+ countries 📞 (like a phone number!)
- **EDGE = "Every Delivery Gets Earlier"** 🚚💨
- **Edge location = local warehouse 📦**: stuff is kept close to you, so it arrives faster than from HQ.

# AWS – Console Intro: Global vs Region-Scoped Services

## The AWS Console 🖥️
- The **AWS Console** = the **website where you manage everything in AWS**.
- Think of it as your **command centre** 🎛️: everything is in **one place**.
- From here you can **spin up** (create/start) and **manage** your AWS services.

---

## Two types of AWS services

### 1. 🌍 GLOBAL services
- **Not tied to any one Region.** They work **everywhere in the world**.
- You **don't pick a Region** when using them.

| Service | Full name | What it does (simple version) |
|---------|-----------|-------------------------------|
| 🔐 **IAM** | Identity and Access Management | Controls **who** can get into your AWS account and **what they're allowed to do**. (Like giving out keys 🔑 to a building.) |
| 🧭 **Route 53** | (DNS service) | Turns a **website name** (like `google.com`) into the **address of the server**, and **sends users to your app**. (Like a sat-nav 🗺️.) |
| 🚀 **CloudFront** | (CDN) | Delivers your content **fast** using **edge locations** near users. (The "local warehouses" 📦 from the last video!) |
| 🛡️ **WAF** | Web Application Firewall | A **security guard** for your website that **blocks bad/harmful traffic**. |

> **Jargon buster**
> - **DNS (Domain Name System)** = the internet's phone book 📖. It turns names like `amazon.com` into number addresses computers understand.
> - **CDN (Content Delivery Network)** = a network of locations that delivers content to users quickly.
> - **Firewall** = a security barrier that decides what traffic is allowed in or out.

---

### 2. 📍 REGION-SCOPED services (most services!)
- **Most AWS services are Region-scoped.**
- When you create one, you **must choose a specific Region**, and it **lives there**.

| Service | What it does (simple version) |
|---------|-------------------------------|
| 💻 **EC2** (Elastic Compute Cloud) | **Rent a computer online.** |
| ⚡ **Lambda** | **Run small bits of code without managing a server.** AWS handles the computer for you. |
| 👁️ **Rekognition** | **AI that looks at images and videos**, e.g. spotting faces or objects. |
| ➕ ...and many more | |

---

## Simple diagram

```
                       🖥️ AWS CONSOLE (your command centre)
                                     │
             ┌───────────────────────┴───────────────────────┐
             │                                               │
     🌍 GLOBAL SERVICES                             📍 REGION-SCOPED SERVICES
   (work everywhere, no Region                    (you MUST pick a Region,
     needs to be picked)                            they live there)
             │                                               │
   • IAM        🔐                                 • EC2          💻
   • Route 53   🧭                                 • Lambda       ⚡
   • CloudFront 🚀                                 • Rekognition  👁️
   • WAF        🛡️                                 • ...most others
```

### Everyday comparison 🏠
- **Global service** = your **passport** 🛂: it works in **any country**.
- **Region-scoped service** = your **local gym membership** 🏋️: it only works at **the branch you signed up to**.

---

## How to check which services are in which Region 🔎
- Not every service is available in every Region.
- AWS has a **Region table** (official name: **"AWS Regional Services List"**).
- **To find it:** search Google for **"AWS regional services list"** and open the aws.amazon.com page.
- Pick a Region and see **which services it offers**.

---

## Key takeaway
> **Global services** (IAM, Route 53, CloudFront, WAF) **work everywhere**, so you don't choose a Region. **Most other services** (like EC2, Lambda, Rekognition) are **Region-scoped**, so you **must pick a Region**. You manage all of them from the **AWS Console**.

## Memory tricks
- **Global services = I.R.C.W** → **I**AM, **R**oute 53, **C**loudFront, **W**AF
  → "**I** **R**eally **C**an't **W**ait" ⏳ (to learn AWS! 😄)
- **Region-scoped examples = E.L.R** → **E**C2, **L**ambda, **R**ekognition
  → "**E**very **L**ocal **R**egion" 📍
- **Global = passport 🛂 | Regional = local gym membership 🏋️**

# AWS – IAM (Identity and Access Management) – Chapter Intro

## What is IAM? 🔐
- **IAM** = **I**dentity and **A**ccess **M**anagement.
- It's one of the **most important services in AWS**. You'll use it **all the time**.
- **Simple meaning:** IAM controls:
  - **WHO** can get into your AWS account 👤
  - **WHAT** they're allowed to do ✅❌
  - **HOW** they get in 🔑
- IAM is a **global** service (it works in every Region, remember **I.R.C.W**!).

---

## The 5 building blocks of IAM

### 1. 👤 Users
- A **User** = **one person** (or one app/service) that needs access to AWS.
- Example: *Sarah the developer* gets her **own** user login.

### 2. 👥 Groups
- A **Group** = a **collection of users** who need the **same permissions**.
- **Why?** Instead of setting up permissions **one person at a time**, you set them **once on the group**, and everyone in it gets them.
- Example: put all developers in a **"Developers"** group.

> **Jargon buster**
> - **Permissions** = what someone is allowed to do.
> - **Resources** = the things you create in AWS (e.g. EC2 computers, S3 storage).

### 3. 📜 Policies
- A **Policy** = a **set of rules** saying what a user or group **CAN** and **CANNOT** do.
- Policies are written in **JSON** (a simple text format). **Don't worry, you won't need to write them from scratch!**
- They control things like:
  - Can this user **create an S3 bucket**? 🪣
  - Can this user **launch an EC2 instance**? 💻
  - Can this user **see certain data**? 📂
- Policies can be **very granular**.

> **Jargon buster**
> - **JSON** = a way of writing information as text that computers can read easily.
> - **Granular** = very detailed and specific (e.g. "can READ this one folder but NOT delete it").

**What a policy looks like (just for a feel, no need to memorise):**
```json
{
  "Effect": "Allow",
  "Action": "s3:CreateBucket",
  "Resource": "*"
}
```
➡️ In plain English: **"Allow** this person to **create S3 buckets**."

### 4. 📱 MFA (Multi-Factor Authentication)
- **MFA** = needing **two things** to log in instead of one:
  1. Your **password** 🔑
  2. A **code from an app on your phone** 📱
- It's like having a **second lock on your door** 🚪🔒🔒. Even if someone **steals your password**, they **still can't get in** without your phone.
- **Very important security feature!**

### 5. 🎭 Roles
- A **Role** = **temporary access** to AWS.
- Great for giving **outside people or services** access **without giving them a permanent login**.
- Think of it like a **visitor badge** 🪪: it lets you in **for a while**, then it **expires**.

> **Jargon buster**
> - **Credentials** = login details (e.g. username + password, or access keys).
> - **Temporary** = only lasts for a short time.

---

## Simple diagram: how it fits together

```
                     📜 POLICY  (the rules)
               "Can create S3 buckets ✅"
               "Can't delete EC2 ❌"
                          │
                     attached to
                          ▼
                 👥 GROUP: "Developers"
                ┌─────────┼─────────┐
                ▼         ▼         ▼
             👤 Sarah   👤 Tom    👤 Priya
         (all 3 get the SAME permissions automatically)

   🔒🔒 MFA  → each user logs in with password + phone code
   🎭 ROLE  → a visitor badge for temporary access (e.g. an outside contractor or an app)
```

---

## Everyday comparison: an office building 🏢

| IAM part | Office building version |
|----------|------------------------|
| 👤 **User** | An **employee** |
| 👥 **Group** | A **department** (e.g. Marketing), where everyone gets the same access |
| 📜 **Policy** | The **rules on the key card**: which doors it opens and which it doesn't |
| 📱 **MFA** | Needing your **key card + a PIN** to get in |
| 🎭 **Role** | A **visitor badge** for the day |

---

## Key takeaway
> **IAM** controls **who** can access your AWS account, **what** they can do and **how** they get in. You create **Users**, put them in **Groups**, give them rules with **Policies**, protect logins with **MFA**, and give temporary access with **Roles**.

## Memory tricks
- **IAM's 5 building blocks = U.G.P.M.R** → **U**sers, **G**roups, **P**olicies, **M**FA, **R**oles
  → "**U**se **G**ood **P**asswords, **M**ate, **R**eally!" 🔐
- **IAM = "I Am" 🙋**: IAM checks *who you are* and *what you're allowed to do*.
- **MFA = two locks on the door 🔒🔒**
- **Role = visitor badge 🪪** (temporary, then it expires)

# AWS – IAM: Root Account, Users & Groups

## 1. Root account 👑
- Made **automatically** when you create an AWS account.
- It can do **everything**.
- ❌ **Don't use it every day. Don't share it.**
- It's the **master key 🗝️ to your house**, so lock it away.

## 2. Users 👤
- A **user** = **one person** (or one app).
- Each user gets **their own login**.
- They only get the access they **need**.
- Like giving someone a **key to just one room** 🔑, not the whole house.

## 3. Groups 👥
- A **group** = a **team** (e.g. Developers, Operations, Audit).
- Give permissions to the **group**, and everyone in it gets them.
- Saves you setting up each person **one by one**.

### The 3 group rules 📏
1. Groups hold **users only**, **not other groups**. (No Russian dolls 🪆)
2. A user **doesn't have to** be in a group.
3. A user **can be in more than one** group.

## Diagram

```
👑 ROOT ACCOUNT (master key, keep locked away 🔒)

┌─ 👥 Developers ─┐   ┌─ 👥 Audit ─┐   ┌─ 👥 Operations ─┐
│ Michael         │   │            │   │                 │
│ Jennifer        │   │      Z ◄───┼───┼──► Z            │  ← Z is in 2 groups ✅
│ Joey            │   │            │   │                 │
└─────────────────┘   └────────────┘   └─────────────────┘

👤 Kasu ← in NO group, but can still use AWS ✅
```

## Key takeaway
> Lock away the **root account**. Give each person their **own user**. Put users in **groups** to make permissions easy.

## Memory trick
**R.U.G** → **R**oot, **U**sers, **G**roups
→ "Keep the **root** key under the **RUG** 🧶🗝️" (hidden and safe!)

# AWS – IAM Permissions & Least Privilege

## 1. Policies 📜
- Users and groups are given **policies**.
- A **policy** = a **rule book**: *"This person CAN do this ✅, but NOT that ❌."*
- Written in **JSON** (a simple text format).

## 2. Actions ⚙️
- Permissions are made of **actions**.
- Each action is either **Allowed ✅** or **Denied ❌**.
- Examples of actions:
  - **Describe EC2**: look at your rented computers 💻
  - **Describe Elastic Load Balancing**: look at your load balancers ⚖️
  - **List metrics in CloudWatch**: see your monitoring stats 📊

> **Jargon buster**
> - **Describe / List** = just **look**, without changing anything 👀
> - **Load balancer** = splits website traffic across several servers so none gets overloaded.
> - **CloudWatch** = AWS's monitoring tool (shows how your stuff is running).

## 3. Least Privilege Principle 🔒 (the GOLDEN rule ⭐)
- Only give people the access they **actually need**. **Nothing more.**
- Example: someone only needs to **read** a database → **don't** let them **delete** or **change** it.
- 🚗 Like letting a friend **open your car to grab something from the back seat**, but **not letting them drive it**.
- **Why?** It keeps things **safe** 🛡️ and saves **headaches** as your company grows.

## Diagram

```
 👤 User / 👥 Group
        │
        ▼
 📜 POLICY (rule book)
   ✅ Describe EC2
   ✅ Describe Load Balancers
   ✅ List CloudWatch metrics
   ❌ Delete anything
        │
        ▼
 🔒 Only what's needed = LEAST PRIVILEGE
```

## Key takeaway
> **Policies** decide what users **can** and **can't** do. Always follow **least privilege**: give the **minimum** access needed.

## Memory trick
**"Give the LEAST, not the FEAST"** 🍽️
→ Only hand out a small snack of access, never the whole buffet!

# AWS – IAM Policy Inheritance

## What is inheritance? 👨‍👩‍👧
- **Inheritance** = users **automatically get** the permissions of the **group(s)** they're in.
- Like **family hand-me-downs** 👕: you get what the group has.

## 1. One group 👥
- **Developers group:** Alice, Bob, Charles
- If the group can access **EC2 instances and S3 buckets**, then **all 3** get that access.

## 2. More than one group ➕
- A user in **2 groups** gets the permissions of **BOTH**.
- **Charles** = Developers + DevOps → dev access **plus** DevOps access.
- **David** = Operations + DevOps → gets **both** too.
- Examples of DevOps extras:
  - **CloudFormation**: build infrastructure 🏗️
  - **CloudWatch**: monitor apps 📊

## 3. Inline policies 🎯
- An **inline policy** = a rule attached **directly to ONE user**.
- **Not shared** with the group. **Only that person** gets it.
- **Fred** = Operations group **+ his own inline policy** → he has **extra access** that no one else has.
- Like a **personal gift** 🎁 just for you.

## Diagram

```
┌── 👥 Developers ──┐   ┌──── 👥 DevOps ────┐   ┌── 👥 Operations ──┐
│ Alice             │   │                   │   │                   │
│ Bob               │   │                   │   │                   │
│ Charles ◄─────────┼───┼─► Charles         │   │                   │
│                   │   │   David ◄─────────┼───┼─► David           │
│                   │   │                   │   │   Fred + 🎯 inline │
└───────────────────┘   └───────────────────┘   └───────────────────┘

Charles = Dev ✅ + DevOps ✅
David   = DevOps ✅ + Ops ✅
Fred    = Ops ✅ + his own personal extra 🎯
```

## Key takeaway
> Users get **all permissions** from **every group** they're in. Use **inline policies** only when **one person** needs something **special**.

## Memory trick
**"G comes before I"** 🔤 (just like in the alphabet)
→ Set up **G**roups first, use **I**nline policies only when needed.

# AWS – IAM Policy Structure

## The big idea 💡
A policy says: **WHO** can do **WHAT** to **WHICH thing**, and **WHEN**.

You **don't** need to write these from scratch. AWS has **ready-made policies**. But it helps to understand them!

---

## Example policy (JSON)

```json
{
  "Version": "2012-10-17",
  "Id": "MyS3Policy",
  "Statement": [
    {
      "Sid": "AllowUploadDownload",
      "Effect": "Allow",
      "Principal": { "AWS": "arn:aws:iam::123456789012:user/Alice" },
      "Action": ["s3:GetObject", "s3:PutObject"],
      "Resource": "arn:aws:s3:::my-bucket/*",
      "Condition": { "IpAddress": { "aws:SourceIp": "203.0.113.0/24" } }
    }
  ]
}
```

> **Jargon buster**
> - **ARN** = Amazon Resource Name, an **address** for something in AWS (like a postcode 📮).
> - **IP address** = a computer's **address** on the internet.

---

## Part 1: The top 🔝

| Part | What it means | Needed? |
|------|---------------|---------|
| **Version** | Policy language date. **Always `2012-10-17`**. Just copy it. | ✅ Always |
| **Id** | A **name** for the policy. | ⚪ Optional |
| **Statement** | The **main part**: the actual rules. Can have **one or more**. | ✅ Always |

## Part 2: Inside a Statement 📋

| Part | Simple meaning | In the example |
|------|----------------|----------------|
| **Sid** | A **label** for the statement 🏷️ | `AllowUploadDownload` |
| **Effect** | **Allow ✅** or **Deny ❌**. That's it. | `Allow` |
| **Principal** | **WHO** it applies to 👤 (user, role or account) | Alice |
| **Action** | **WHAT** they can do ⚙️ | `GetObject` = **download** ⬇️, `PutObject` = **upload** ⬆️ |
| **Resource** | **WHICH thing** it's for 🪣 | the S3 bucket `my-bucket` |
| **Condition** | **WHEN** it works ⏰ (optional) | Only from a certain IP address |

---

## Diagram

```
📜 POLICY
 ├─ Version   → always "2012-10-17"
 ├─ Id        → name (optional)
 └─ Statement
     ├─ Sid        🏷️ label
     ├─ Effect     ✅ / ❌
     ├─ Principal  👤 WHO
     ├─ Action     ⚙️ WHAT
     ├─ Resource   🪣 WHICH thing
     └─ Condition  ⏰ WHEN (optional)
```

**Read it as a sentence:**
> ✅ **Allow** 👤 **Alice** to ⚙️ **upload & download** in 🪣 **my-bucket**, ⏰ **only from this IP address**.

---

## Key takeaway
> A policy has a **Version**, an optional **Id**, and **Statements**. Each statement says **Allow/Deny**, **who**, **what**, **which resource** and (optionally) **when**.

## Memory tricks
- **Top of a policy = V.I.S** → **V**ersion, **I**d, **S**tatement
  → "**V**ery **I**mportant **S**tuff" ⭐
- **Inside a statement = S.E.P.A.R.C** → **S**id, **E**ffect, **P**rincipal, **A**ction, **R**esource, **C**ondition
  → "**S**ome **E**lephants **P**aint **A**rt **R**eally **C**arefully" 🐘🎨

  # AWS – Password Policy 🔑

- A **password policy** makes everyone use **strong passwords**. This works for any login, not just AWS.
- **Length:** at least **8–12 characters**. Longer = harder to crack.
- **Mix it up:** **UPPERCASE**, **lowercase**, **numbers** and **symbols** (e.g. `@`, `!`).
- **Changes:** users can **change their own** password, and passwords **expire** after a set time.
- **No reusing** old passwords (no `password123` over and over ❌).
- **At work (production / big companies):** you'll mostly use **SSO (Single Sign-On)**, one secure login for everything, instead of passwords.
- **Personal account:** use a **strong password + MFA** 📱.

**Memory trick: L.M.E.N.S** → **L**ength, **M**ix, **E**xpire, **N**o reuse, **S**SO
→ "Look through a strong **LENS** 🔍... with an **M** in it!"


# AWS – MFA (Multi-Factor Authentication) 📱

- **MFA** = logging in with **2 things** instead of 1:
  - **Something you KNOW** → your password 🔑
  - **Something you HAVE** → a one-time code from an app on your phone 📱
- **Why?** If a hacker steals your password, they **still can't get in** without your phone.
- **Without MFA**, a hacker could **delete your stuff**, **change settings**, or **run Bitcoin mining** on your account → **huge bill 💸**.
- **Set it up on your root account first** 👑 (it has full access to everything), then on all IAM users.
- Quick to set up, **huge security boost** 🛡️.

**Memory trick: "Know + Have = Safe" 🔑 + 📱 = 🛡️**

# AWS – MFA Device Options 🔐

- **1. Virtual MFA device** 📱: an **app on your phone** (e.g. Google Authenticator, Microsoft Authenticator).
  - Gives you a **one-time code**. **Free**, and one phone can hold **many accounts**. Best for most people ✅
- **2. U2F Security Key** 🔌: a **USB stick** you plug in (e.g. **YubiKey**).
  - **No code to type**, just plug in and tap. One key works for **many accounts**.
- **3. Hardware Key Fob** ⌚: a small **physical gadget** that shows a **new code every 30 seconds**.
  - Old school. Good where **phones aren't allowed**.
- **4. Hardware Key Fob for AWS GovCloud** 🏛️: a special fob for **AWS GovCloud (US)**, the Region for **US government** work with **high security** needs.
- **Main point:** any option is fine. Just **USE MFA!**

**Memory trick: V.U.H.G** → **V**irtual, **U**2F, **H**ardware fob, **G**ovCloud fob
→ "**V**ery **U**seful **H**ardware **G**adgets" 🛠️

# AWS – 3 Ways to Access AWS 🚪

- **1. AWS Management Console** 🖥️: the **website**.
  - Log in with **password + MFA**. Good for doing things **by clicking** (nicknamed **"ClickOps"**).
- **2. AWS CLI (Command Line Interface)** ⌨️: type **commands in your terminal**.
  - e.g. `aws ec2 run-instances`. **Faster**, and good for **automating** tasks.
- **3. AWS SDK (Software Development Kit)** 👩‍💻: lets **your code / apps** talk to AWS **automatically**.
- **CLI + SDK use Access Keys**, not passwords:
  - **Access Key ID** = like a **username** 👤
  - **Secret Access Key** = like a **password** 🔑
- ⚠️ **NEVER share access keys or put them in your code / GitHub.** Hackers could take over your account (Bitcoin mining = huge bill 💸).
- **Rule:** Console → **password + MFA**. Only use access keys **when you need to**.

**Memory trick: C.C.S** → **C**onsole, **C**LI, **S**DK
→ "**C**lick, **C**ommand, **S**cript" 🖱️⌨️📜

# AWS – Access Keys (What They Look Like) 🔑

- Access keys come in a **pair**, and they work together for the **CLI / SDK**:
  - **Access Key ID** = **username** 👤 → e.g. `AKIAIOSF••••••••••••` (usually starts with **AKIA**)
  - **Secret Access Key** = **password** 🔑 → e.g. `wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY`
  - *(These are AWS's official fake examples, so they won't work.)*
- ⚠️ **NEVER share them.** Anyone with your keys can do **whatever your permissions allow**, including **deleting things**.
- **Think your keys are leaked?** Straight away, either:
  - make them **Inactive** ⛔, or
  - **Rotate** them 🔄 (create **new** keys, then **disable the old** ones).
- **Best practice:** rotate keys **regularly**, even if nothing's wrong.
- Lots of people get hacked by **accidentally pushing keys to GitHub**, so be careful!

**Memory trick: "Hide it, Don't Ride it, Rotate it"** 🙈🚫🔄
→ Keep it secret, never share it, change it regularly.

# AWS – CLI (Command Line Interface) ⌨️

- The **AWS CLI** lets you control AWS by **typing commands in your terminal**, so you don't need to log in to the website.
- It talks directly to AWS's **public APIs** (the "doors" into each service 🚪).
- You can do **almost anything** the console can: manage **S3 buckets** 🪣, launch **EC2 instances** 💻, etc.
- **Big win:** you can write **scripts** to **automate** jobs instead of clicking around (**ClickOps**) 🤖
- **Example commands:**
  - `aws s3 cp myfile.txt s3://my-bucket/` → **upload (copy)** a file to a bucket ⬆️
  - `aws s3 ls` → **list** your buckets 📋
- It's **open source** (free, and anyone can see the code on GitHub: `github.com/aws/aws-cli`).

> **Jargon buster:** **API** = a way for programs to talk to a service.

**Memory trick: "cp = CoPy, ls = LiSt"** 📄➡️🪣 | 📋

# AWS – SDK (Software Development Kit) 👩‍💻

- The **SDK** lets **your code** talk to AWS, using the **programming language you already use**.
- It's a set of **ready-made libraries** 📚 for each language: **Python, JavaScript / Node.js, PHP, Go, C++** and more.
- You can use AWS **inside your app**, e.g. **upload files to S3** 🪣 or **start EC2 instances** 💻, with just a few lines of code.
- Also works for **mobile** (Android 🤖, iOS 🍎) and **IoT devices** (e.g. Arduino, embedded C).
- **Python's SDK is called Boto3** 🐍:
  ```python
  import boto3
  s3 = boto3.client("s3")
  s3.upload_file("myfile.txt", "my-bucket", "myfile.txt")
  ```
- **Fun fact:** the **AWS CLI is built on the AWS Python SDK**, so if you've used the CLI, you've already used the SDK! 😄

> **Jargon buster:** **Library** = pre-written code you can reuse so you don't start from scratch.

**Memory trick: CLI = you type 🧑‍💻, SDK = your code types 🤖**
→ **Boto3** = "**Bo**ss **To**ol for Python" 🐍

# AWS – Installing & Setting Up the CLI (Mac) 🍎⌨️

- **1. Install:** Google **"install AWS CLI"** → AWS page → **macOS** → **GUI installer** → download, then click Continue/Agree → enter your Mac password → Close.
- **2. Check it worked:** open **Terminal** (`Cmd + Space` → "Terminal") and type:
  - `aws --version` → it shows a version (e.g. `aws-cli/2.17...`) ✅
- **3. Create an access key** (for your **IAM user**, ❌ **NOT the root account**):
  - Console → **IAM** → **Users** → click your user → **Security credentials** → **Create access key** → choose **CLI** → tick "I understand" → **Create**.
- **4. Connect the CLI to your account:**
  - `aws configure`, then enter:
    - **Access Key ID** 👤 (paste)
    - **Secret Access Key** 🔑 (paste)
    - **Region** → `eu-west-2` (London) 🇬🇧
    - **Output format** → `json`
- **5. Test you're logged in:**
  - `aws sts get-caller-identity` → shows **who you're logged in as** ✅
  - `aws iam list-users` → lists your **IAM users** 👥
- **Main point:** anything you can do in the **console**, you can do in the **CLI**. A user made in the console **shows up in the CLI** too.

**Memory trick: I.C.K.C.T** → **I**nstall, **C**heck, **K**ey, **C**onfigure, **T**est
→ "**I** **C**an **K**ick **C**ode **T**oday" ⚽

# AWS – IAM Roles for Services 🎭

- Sometimes an **AWS service needs to use another AWS service** for you.
  - e.g. **EC2** 💻 needs to **read from S3** 🪣
  - e.g. **Lambda** ⚡ needs to **write logs to CloudWatch** 📊
- ❌ **Don't** put your access keys or passwords inside the service (that's called **hard-coding**).
- ✅ **Use an IAM Role** instead. It gives the service **temporary access**, with **no long-term keys** needed.
- **Common examples:**
  - **EC2 instance role** → lets EC2 use **S3, DynamoDB**, etc.
  - **Lambda function role** → lets Lambda use other AWS services
  - **CloudFormation role** → lets CloudFormation **build resources** across many services 🏗️
- You **control exactly what each service is allowed to do**.

> **Jargon buster:** **Hard-coding** = typing secret details straight into code or settings (unsafe ⚠️).

**Memory trick: "Role = a temporary key for a service" 🎭🔑**
→ **E.L.C** → **E**C2, **L**ambda, **C**loudFormation = "**E**very **L**ittle **C**omputer needs a role" 💻

# AWS – IAM Security Tools 🛡️

- **1. IAM Credentials Report** 📋 (**whole account** level)
  - A **list of ALL users** and the state of their logins.
  - Shows: who has **access keys** 🔑, who uses **MFA** 📱, and when people **last changed their password**.
  - Gives you the **big picture** 🌍.
- **2. IAM Access Advisor** 🔍 (**one user** level)
  - Shows **what services a user is allowed to use** and **when they last used them**.
  - Not used in months? → **remove that permission** ✂️
  - Good for **fine-tuning** one person's access.
- Both tools help you follow **least privilege** (only give what's needed 🔒).

**Memory trick: Report = big picture 🌍, Advisor = close-up 🔍**
→ "**R**eport is **R**oom-wide, **A**dvisor is **A**bout one person" 👥 vs 👤

