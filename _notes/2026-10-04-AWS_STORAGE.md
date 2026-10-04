---

title: "EC2 Instance storages"
description: "Describe and understand different available storages in EC2"
duration: "59 minutes"
tools: "AWS interface"
---


## EBS (Elastic Block Store)

**EBS is a network volume** that lets instances keep their data after shutdown.

- Bound to a specific **AZ** (snapshot it to move across AZs)
- Can be detached from one instance and attached to another

## Snapshot Types

| Type | Purpose |
|------|---------|
| **Archive** | Cheaper, but restore takes 24-72 hours |
| **Recycle Bin** | Recover snapshots deleted by accident |
| **Fast Snapshot Restore** | Faster restores from a snapshot |

## AMI (Amazon Machine Image)

Lets you customize your EC2 instances by pre-baking:

- Your software
- Configuration
- Operating system

## EC2 Instance Store

Storage **physically attached** to the instance.

- ⚡ Higher I/O speed
- ⚠️ **Not persistent**: data is lost if the machine fails

## EBS Volume Types

| Type | Media | Use case |
|------|-------|----------|
| **gp2 / gp3** | SSD | General purpose |
| **io1 / io2** | SSD | Higher performance, critical business apps |
| **st1** | HDD | Low cost, frequently accessed: big data, log processing |
| **sc1** | HDD | Lowest cost, infrequently accessed |

## EBS multi-attach
- Attach the same EBS to different EC2 in the same AZ.
- Each instance has full read and write permissions
- Up to 16 instances
 #### Use case
 Applications that must manage concurrent write operations

## Amazon EFS - Elastic file System
