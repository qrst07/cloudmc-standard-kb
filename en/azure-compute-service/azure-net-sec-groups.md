---
title: "Microsoft Azure:  Network security groups"
slug: azure-network-security-groups
---


A **network security group** is a set of rules that control access to a network.  A network security group can be bound to a subnet or to a NIC.  

Summary

Required permissions

Navigate to

### Security rules

You may not create two security rules with the same priority and direction (rewrite)

If you specify an outbound security rule to any address over port 80, for example, it's not necessary to specify an inbound security rule for the response to the outbound traffic. You only need to specify an inbound security rule if communication is initiated externally. (rewrite)

Existing connections may not be interrupted when you remove a security rule that enabled the flow. Traffic flows are interrupted when connections are stopped and no traffic is flowing in either direction, for at least a few minutes. (re-write, plus, isn't that a little fucked up?  If a rule is removed, the access should be killed immediately, no?)

Limits on number of security rules in a group.

#### Order of evaluation

For inbound traffic, subnet is evaluated first, then NIC.  For outbound traffic, it's the opposite, interface first and then subnet.


### See also

https://docs.microsoft.com/en-us/azure/virtual-network/network-security-groups-overview
https://docs.microsoft.com/en-us/azure/virtual-network/network-security-group-how-it-works
