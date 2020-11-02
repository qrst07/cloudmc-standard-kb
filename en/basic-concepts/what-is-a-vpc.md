---
title: "What is a VPC?"
slug: what-is-a-vpc
---


A **virtual private cloud** (VPC) is a logically isolated section in an environment, where you can build a multi-tier application architecture.  VPCs help replicate the functionality of physical networks and are a fundamental part of most cloud-computing environments, acting as the container for multiple isolated networks that communicate with each other.

### Overview of VPCs

VPCs rely on several different virtualized networking components, and they enable a number of cloud-standard features.

#### Core concepts

- **Network:** For the purposes of this discussion, a network resides inside a VPC, and its IP space is a subnet of the parent VPC.  Resources such as instances are deployed inside a network.  A network is analogous to a physical LAN.
- **Virtual router:** Each VPC has a virtual router (VR) which facilitates communication between the networks in a VPC.  A virtual router is automatically created and started when you create a VPC.
- **Network ACLs:** Network access control lists (ACLs) are ordered rules that determine whether traffic is allowed in or out of any network associated with the network ACL.  Network ACLs are applied to the networks inside of a VPC.
- **Public IPs:** A public IP for the VPC is automatically assigned to the NIC on the virtual router that connects to the public Internet.  Additional public IPs may be allocated to individual networks, see below [WHICH SECTION].
- **Source NAT:** All traffic leaving a VPC and bound for the public Internet will use the public IP of the VPC.
- **Static NAT and port forwarding:** When additional public IPs are allocated, a VPC can provide port forwarding and network address translation for traffic from the public Internet to reach instances inside the VPC's networks.  

#### Additional features

- **DNS and DHCP services:**  Inside of the VPC, DNS and DHCP services are provided by the virtual router.
- **Public gateway:** The virtual router acts as the gateway to the outside world.
- **Private gateway:** All traffic to and from a private network is routed to the VPC through the private gateway. <-- Rewrite this and then point to section on private gateways.
- **Site-to-site VPN connection:** An IPSec VPN connection between a VPC and a remote datacenter, home network, or co-location facility.
- **Remote access VPN:** An IKEv2-over-IPSec VPN connection between a VPC and a software client running on a workstation.

### Network connectivity

![VPC network model](/assets/what-is-a-vpc-2.png)

The VPC network model provides flexible options for establishing network connectivity.  The virtual router, with its defined set of network ACLs, allows traffic to flow within a VPC, between a VPC and the public Internet, between a VPC and remote networks or individual users via VPNs over the public Internet, and between a VPC and remote networks via a private gateway.

Because of the flexibility afforded by VPCs, it is important to have a clear understanding of the desired flow of traffic, and defining network ACLs that will ensure this flow.  By default, all networks

A VPC can be connected to:

- The public Internet via the virtual router
- A corporate datacenter by using a site-to-site VPN connection
- Both the Internet and your corporate datacenter, using both the public gateway and a VPN gateway

In a VPC, the following network architectures are the basic options:

- VPC with a public gateway only
- VPC with public and private gateways
- VPC with public and private gateways and site-to-site VPN access
- VPC with a private gateway only and site-to-site VPN access

Networks in a VPC are segmented from each other by means of VLANs. <-- Do I put this here?
For each network in a VPC, a corresponding NIC and IP exists in the virtual router.
The NIC of each network acts as its gateway. <-- Do I put this here? Also phrase it better.
Virtual router directs traffic between the public gateway, VPN gateways, and NAT instances.
VR provides DNS and DHCP services through its IP.
VPC has the default network ACLs, default_allow for egress and default_deny for ingress.

### Private gateways
Only an Operator can add a private gateway
What does Source NAT enabled do?
Private gateways are another mechanism for accessing a VPC externally.
A private gateway gets an interface on the VR
It's a point-to-point connection to a private network
All traffic is routed through the VR
Does not use the public network, it's direct.
Users can add static routes so that the desired traffic is routed to the private gateway.
No need for VPN
Fast and reliable
Enables VPC to VPC peering across different regions


### VPC network considerations

Consider the following when you create a VPC:

- The maximum number of networks you can create within a VPC is 4.
- Each network must have an unique CIDR in the VPC. The web interface enforces this requirement.
- A network belongs to only one VPC.
- When a VPC is created, by default, a Source NAT IP is allocated to it. The Source NAT IP is released only when the VPC is removed.
- A public IP can be used for only one purpose at a time. If the IP is a Source NAT, it cannot be used for Static NAT or port forwarding.
- Instances can only have one private IP address, hence be connected to only one network at a time.
- The public load-balancing service can be supported by only one network inside the VPC, in other words a VPC can have only one network with a public load-balancing service.
- If an IP address is assigned to a network:
   - That IP can’t be used by more than one network at a time in the VPC. For example, if you have networks A and B, and a public IP, you can create a port-forwarding rule by using the IP either for A or B, but not for both.
   - That IP can’t be used for Static NAT, load balancing, or port forwarding rules for another guest network inside the VPC.


### See also

[Working with VPCs](../cloudstack-compute-service/working-with-vpcs.md)
[Securing your network](../cloudstack-compute-service/securing-your-network.md)
Site-to-site VPNs
Remote access VPNs

### External links

[Wikipedia: Virtual Private Clouds](https://en.wikipedia.org/wiki/Virtual_private_cloud)
