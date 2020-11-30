---
title: "StackPath Service:  Workloads"
slug: stackpath-workloads
---


A StackPath workload is...

containers
resources
targets

And is deployed on the StackPath edge servers.


Workloads are created only in the default VPC.

To create, modify, or delete a StackPath workload, an account with the *User* role must be a member of the environment which contains the instance, and also have the *Editor* or *Owner* environment role assigned.  An account with the *Administrator* role or higher may create, modify, or delete workloads in any environment.

To access disks, navigate to your StackPath environment and click on the **Workloads** tab.

### Add a workload

https://support.stackpath.com/hc/en-us/articles/360022756051-Create-and-Manage-Virtual-Machines-Containers-and-Workloads

From the **Workloads** tab, click on the *Add workload* button.
Provide a name.
Select the workload type:
   - VM
   - Container
Select an operating system
   - VM
   - Container
Add image pull credentials
Container only:  https://support.stackpath.com/hc/en-us/articles/360022768891
   - Environment variable key and value
   - Secret environment key and value
Select VPC
AnyCast IP address: https://support.stackpath.com/hc/en-us/articles/360022801751-Edge-Computing-Using-Global-Anycast-IP-Addresses
Public port and protocol (optional)
First boot SSH key (VM only): paste in the public SSH key
Commands: Container only
Specification
Persistent storage
Deployment name: a name to describe the deployment.
Auto-scaling
   - CPU utilization
   - Min instances per PoP
   - Max instances per PoP



#### Subsection


### See also

### External links
