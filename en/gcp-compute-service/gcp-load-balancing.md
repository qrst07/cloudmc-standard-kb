---
title: "GCP: Load balancing"
slug: gcp-load-balancing
---


CloudMC supports Google Cloud Platform's load balancing features, whereby traffic can be directed to a reliable backend service with multiple servers for delivering an application.

GCP load balancing is accessed by navigating to the desired GCP environment, clicking on the **Networking** tab, and clicking on the **Load balancing** item.

### Concepts in GCP load balancing

- **Instance group**: Defines the pool of instances that provide an application or a microservice.
- **Health check**: Defines criteria for the determining the availability of an instance.
- **Backend service**: Binds together an instance group, a health check for the instances in that group, and the protocol to use for communicating with those instances.
- **URL map**: Specifies which backend service to send traffic to, based on the request URL.
- **Target proxy**: Listens for traffic on the specified protocol, and forwards that traffic to the correct backend service, based on the specified URL map.
- **Forwarding rule**: Binds together an IP address which serves as the endpoint of the load balancer, a protocol and port, and a target proxy.
- **Google Front End**: Interface point between GCP and the public Internet.

This model allows for significant flexibility in deployments as well as for re-use of components:
   - If you need to support both HTTP and HTTPS for your clients, two target proxies (one for HTTP and the other for HTTPS) can forward requests to the same backend service.
   - SSL connections can be decrypted at the target proxy to offload that work from the backend.
   - For highly sensitive data that requires end-to-end encryption, target proxies can connect to the backend via HTTPS.

The following diagram provides a simplified visualization of the relationships between these different components:

![GCP load balancing](../../assets/gcp-load-balancing-en-1.png)

### Configuring GCP load balancing

Prior to configuring a new load balancer, you must already have the following:
   - At least one instance in the desired region, serving your application or microservice.
   - An instance group in the same region, containing the instance(s).
   - A health check appropriate for the target instance(s).

#### Basic configuration

1. Create a backend service:
   - Click on **Backend services**, and click the *Add backend service* button.
   - Enter a name, and a description if desired.
   - Select the protocol to use for communicating with the instance group.  If using HTTPS, see the section below on enabling SSL.
   - Select the desired health check for the instance group.
   - Select the desired instance group.
   - Click *Submit*.
1. Create a target proxy:
   - Click on **Target proxies**, and click on the *Add target proxy* button.
   - Enter a name, and a description if desired.
   - Select the protocol the target proxy will use for listening for incoming requests from clients.
      - To support HTTPS connections from clients, select HTTPS.  A list of the SSL certificates available to CloudMC will appear beneath the **Protocol** pop-up menu, and you will need to select the appropriate one for this load balancer.  See [GCP: SSL certificates](gcp-ssl-certs.md).  
   - Select a URL map.  If no URL maps have been created, a default URL map will be created at the same time as the target proxy.
   - Click *Submit*.
1. Create a forwarding rule.
   - Click on **Forwarding rules**, and click on the *Add forwarding rule* button.
   - Enter a name, and a description if desired.
   - Select how you wish a public IP address to be allocated for the load balancer:
      - To allocate an IP address solely for this load balancer and have it released when this forwarding rule is deleted, leave *Reserve a new static IP address* unchecked, and select **Ephemeral** selected in the pop-up menu.  The IP address allocated to the load balancer will **not** appear in the **External IPs** list for this environment.
      - To use a public IP address that has already been allocated in this environment, select
      - To reserve a new public IP address that will be not be released when the forwarding rule is deleted, select *Reserve a new static IP address*.  The pop-up menu will disappear, and a new IP address will be allocated when the forwarding rule is created.  The IP address will also appear in the **External IPs** list for this environment.
   - Select the protocol to use and which port to listen on for incoming requests.
      - When selecting HTTPS, a target proxy configured for SSL must exist in the environment.
   - From the **Target proxy** pop-up menu, elect the target proxy that was configured in the previous step.
   - Click *Submit*.
1. The *Forwarding rules* page will appear.  Verify that the new load balancer appears in the list.  It will also appear under the **Load balancers** item.

The new load balancer is now active and ready for testing with public traffic.  The public IP address for your load balancer is listed on both the *Forwarding rules* and the *Load balancers* page.

#### Enabling SSL in the backend

1. Install a valid SSL certificate on each instance in the instance group.
1. Server must be configured to use HTTPS.
1. Select HTTPS for the protocol in the desired backend service.


Install SSL certs? - If using SSL between the target proxy and the backend service, a valid SSL certificate must be installed on each instance in the group.

#### Delete a GCP load balancer

Deletes the forwarding rule, target proxy, URL map
