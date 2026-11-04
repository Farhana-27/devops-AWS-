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


