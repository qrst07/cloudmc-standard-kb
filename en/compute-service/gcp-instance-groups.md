---
title: "GCP: Instance groups"
slug: gcp-instance-groups
---

To create, modify, or delete an instance group, an account with the *User* role must be a member of the environment which contains the instance, and also have the *Editor* or *Owner* environment role assigned.  An account with the *Administrator* role or higher may create, modify, or delete instance groups in an environment.

To manage instance groups, navigate to the desired GCP environment, click on the *Compute* tab, and then click on *Instance groups*.

### Adding an instance group

1. Click on *Add instance group*.  The *Add instance group* page will appear.
1. Provide a name for the instance group, and an optional description.
1. Select the region and zone where the instances are located.
1. If the selected zone has instances, a pop-up list of instances will appear beneath the zone.  Select the instances to become members of this instance group.  Note that changing a zone will clear the list of instances that have already been selected.
1. Click *Submit* to create the group.

**Note:** Once an instance group is created, its region and zone cannot be changed.
