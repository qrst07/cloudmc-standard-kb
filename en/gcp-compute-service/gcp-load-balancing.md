---
title: "GCP: Load balancing"
slug: gcp-load-balancing
---


CloudMC supports GCP load balancing features, whereby traffic can be directed to a reliable backend service with multiple servers.

GCP load balancing is accessed by navigating to...

### Concepts in GCP load balancing

- **Instance group**: Defines the pool of instances that provide an application or a microservice.
- **Health check**: Defines criteria for the determining the availability of an instance.
- **Backend service**: Binds together an instance group, a health check for the instances in that group, and the protocol to use for communicating with those instances.
- **URL map**: Specifies which backend service to send traffic to, based on the request URL.
- **Target proxy**: Listens for traffic on the specified protocol, and forwards that traffic to the correct backend service, based on the specified URL map.
- **Forwarding rule**: Binds together an IP address which serves as the endpoint of the load balancer, a protocol and port, and a target proxy.
- **Google Front End**: Interface from GCP to the public Internet.

![GCP load balancing](../../assets/gcp-load-balancing-en-1.png)

SSL certs?

### Configuring GCP load balancing

1.

Install SSL certs?
