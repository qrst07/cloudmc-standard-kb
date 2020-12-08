---
title: "StackPath Service:  Workloads"
slug: stackpath-workloads
---


A StackPath **workload** represents the collection of resources needed to deliver an application.  A workload consists of either a single virtual machine or a container that can be deployed to one or more of StackPath's Edge Locations.  

To create, modify, or delete a StackPath workload, an account with the *User* role must be a member of the environment which contains the instance, and also have the *Editor* or *Owner* environment role assigned.  An account with the *Administrator* role or higher may create, modify, or delete workloads in any environment.

To access workloads, navigate to your StackPath environment and click on the **Workloads** tab.

### Add a workload

1. From the **Workloads** tab, click on the *Add workload* button.
1. Enter a name for the workload.
1. Select the type of workload:
   - Virtual machine
   - Container
1. If the type of workload is **Virtual machine**, select an operating system image from the popup list labeled **OS image**.
1. If the type of workload is **Container**, enter the location from which the image should be pulled.  If credentials are required for the remote location, check the box labeled *Add image pull credentials*.  Fields for the credentials will become visible.
1. Additionally, if the type of workload is **Container**, environment variables may be defined and made accessible to the container.  These values are defined at runtime or during deployment, and are presented within the container as standard environment variables.
   - Environment variable key and value:  Key value pairs are made available to all instances.  
   - Secret environment key and value: Same as environment variables but can be used to store credentials securely.
1. Select VPC for deploying the workload.
   - At this time, workloads are created only in the default VPC.
1. If an Anycast IP address is desired, mark the checkbox labeled **
1. Public port and protocol (optional)
1. First boot SSH key (VM only): paste in the public SSH key, required field
1. Commands: Container only
1. Specification of offering
1. Persistent storage
1. Deployment name: a name to describe the deployment.
1. Deployment PoP: One or more StackPath Edge Location for workload.
1. Auto-scaling
   - CPU utilization
   - Min instances per PoP
   - Max instances per PoP
1. Click *Submit*. The **Workload** tab will

containers
resources
targets

### External links

[Create and Manage Virtual Machines, Containers, and Workloads](https://support.stackpath.com/hc/en-us/articles/360022756051-Create-and-Manage-Virtual-Machines-Containers-and-Workloads)
[Edge Computing: Using Global Anycast IP Addresses](https://support.stackpath.com/hc/en-us/articles/360022801751-Edge-Computing-Using-Global-Anycast-IP-Addresses)
[Learn about Environment Variables](https://support.stackpath.com/hc/en-us/articles/360022768891)
