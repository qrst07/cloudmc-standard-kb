---
title: "Microsoft Azure: Working with instances"
slug: azure-working-with-instances
---


To create, modify, or delete an instance, an account with the *User* role must be a member of the environment which contains the instance, and also have the *Editor* or *Owner* environment role assigned.  An account with the *Administrator* role or higher may create, modify, or delete instances in an environment.

To access instances, navigate to your Microsoft Azure environment and click on the **Instances** tab.

### Add an instance

Prior to adding an instance, you must have at least one network created in your Microsoft Azure environment.

1. Click on *Add instance*.
1. On the *Add instance* page, enter the required parameters for the desired instance.  The estimated hourly and monthly costs will appear on the right hand side.
1. Select the region in which to create the instance.  The region cannot be changed once the instance is created.
1. You may choose to attach a public IP when the instance is created.  There must be a public IP address already allocated and unattached in the network where the instance is to be created.
1. Select the subnet to attach to this instance.
1. Click *Submit*.  The **Instances** tab will appear.  When the new instance has been created, it will appear in the list, and will be in the **provisioning** state.  Once the instance has been provisioned, it will transition to the **running** state.

Creating an environment - Advanced - Select region


## Delete
Does deleting remove the root disk?

Once a network is created, it cannot be deleted.
