---
title: "StackPath:  Overview of workloads"
slug: stackpath-overview-workloads
---


A StackPath **workload** represents the collection of resources needed to deliver an application.  A workload consists of either a virtual machine (or instance) or a container that can be deployed to one or more of StackPath's **edge locations** (points of presence, or **PoPs**).  A given workload can have one or more VMs or containers deployed at each PoP, all using the same image.  Single VMs are built using an operating system image. Containers are built using a Docker image pulled from a registry such as DockerHub or other service.

At deployment, each VM or container is given a root volume whose size is defined by the image.  If additional storage is needed, a persistent volume may be attached to each instance or container in a workload.  This is particularly useful for containers, whose root volume does **not** persist.

Every instance or container in a workload gets a private and public IP address upon creation.  [Network policies](stackpack-network-policies.md) control access to the instances or containers in a workload.  For more complex deployments, an **Anycast IP address** can be added at the time of creation of the workload, and will remain assigned to the workload for the duration of its lifetime.  Anycast IP addresses are a feature of StackPath and provide optimal routing for traffic, essentially behaving as a global load balancer for your workload.  <!-- Need to show where Anycast IPs send traffic.  This is not clear to me at this time. -->

### External links

[Create and Manage Virtual Machines, Containers, and Workloads](https://support.stackpath.com/hc/en-us/articles/360022756051-Create-and-Manage-Virtual-Machines-Containers-and-Workloads)

[Edge Computing: Using Global Anycast IP Addresses](https://support.stackpath.com/hc/en-us/articles/360022801751-Edge-Computing-Using-Global-Anycast-IP-Addresses)

[Learn about Environment Variables](https://support.stackpath.com/hc/en-us/articles/360022768891)

[Edge Computing:  Enabling Auto-Scaling on Your Workload](https://support.stackpath.com/hc/en-us/articles/360034604611-Edge-Computing-Enabling-Auto-Scaling-on-Your-Workload)
