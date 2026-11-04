
# EBS Volumes (Elastic Block Store)

## What is it?

- A **network drive** you attach to your EC2 instances.
- Not a physical drive like the one in your laptop, but it **works in a similar way**: virtual storage in the cloud that connects to your instance.
- 🔌 **Analogy:** like a USB stick for your instance. Plug it in and save data. Unplug it and the data stays safe. Plug it into the same instance or another one later.

## Key features

- **Data persists.** It stays on the volume even if you **stop or terminate** the instance (unless you choose to delete it).
- **Tied to one Availability Zone (AZ).**
  - You can't move a volume to another AZ directly.
  - Instead, take a **snapshot** and create a new volume from it in the other AZ.
- **Can be reattached** to the same instance or a different one **in the same AZ**.

## Why use EBS?

- **Long-term storage** for databases, logs and files.
- Your data stays safe even if the instance it's attached to goes away.

## Free tier

- **30 GB of EBS storage per month** (General Purpose SSD or Magnetic), which is enough for experimenting at no cost.

# AMI (Amazon Machine Image)

## What is it?

- A **blueprint (template)** for launching EC2 instances.
- Contains everything an instance needs to start: the **operating system, software, configuration, monitoring tools** and more.

## Why it's useful

- ⏱️ **Saves time.** Everything is already installed, so you don't set it up by hand each time.
- 🚀 **Faster boot.** The instance is ready to go as soon as it launches.
- 🔁 **Consistency.** Launch many identical instances with the same setup.
- ✅ **Fewer human errors**, especially in big environments.
- 📈 **Great for scaling.** Quickly spin up copies of the same server.

## Regions

- An AMI is built for **one region**, but you can **copy it to other regions**.

## Types of AMI

| Type | Who provides it | Example |
|---|---|---|
| **Public** | AWS, free for everyone | Amazon Linux, Windows, Ubuntu |
| **Your own (custom)** | You, made from an instance you've customised | Your web server with everything pre-installed |
| **Marketplace** | Third-party vendors (free or paid) | Software that comes pre-configured |

## How you make your own

```
Customise an instance → Create an AMI from it → Launch identical instances (any region)
```
# Amazon EFS (Elastic File System)

## What is it?

- A **managed network file system (NFS)** for **shared** file storage.
- Can be **mounted on many EC2 instances at the same time**.
- 🗂️ Think of it as a **shared network drive** that all your instances can use.

## Key features

- **Multi-AZ:** data is copied across several Availability Zones, so it's **highly available** and durable.
- **Scales automatically:** it grows and shrinks as you add or remove data, so there's no resizing to do.
- **Mounts like any Linux file system** using NFS. Set it up once, then mount it on each instance.

## When to use it

- Several instances running the **same app** that need the **same files**.
  - For example, a content management system (CMS) such as WordPress, or distributed workloads.

## Drawback

- 💰 **Expensive:** about **3× the cost** of a standard General Purpose SSD (gp2) EBS volume.
- Only use it when your app **really needs shared storage**.

## EBS vs EFS

| | EBS | EFS |
|---|---|---|
| Type | Network drive (block storage) | Shared network file system |
| Attached to | Usually **one** instance | **Many** instances at once |
| Availability Zones | Tied to **one AZ** | Works across **many AZs** |
| Size | You choose it | Grows automatically |
| Cost | Cheaper | About 3× more expensive |

