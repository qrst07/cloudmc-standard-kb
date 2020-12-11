---
title: "Service de StackPath:  Présentation des charges de travail"
slug: stackpath-overview-workloads
---


Une **charge de travail** en StackPath représente l'ensemble des ressources nécessaires pour fournir une application. Le type d'une charge de travail peut être **machine virtuelle** (*VM*) ou **conteneur**, et la charge de travail elle-même est composée d'instances de l'un de ces types. Les charges de travail sont déployées sur un ou plusieurs **emplacements périphériques** de StackPath (points de présence ou **PoP**). Les machines virtuelles sont créées à l'aide d'une image du système d'exploitation. Les conteneurs sont créés à l'aide d'une image Docker extraite d'un registre tel que DockerHub ou un autre service.

Une charge de travail donnée peut avoir une ou plusieurs instances déployées sur chaque PoP, toutes construites à l'aide de la même image. Afin de gérer les pics de charge, les fonctionnalités de mise à l'échelle automatique sont prises en charge, grâce auxquelles StackPath surveillera l'utilisation du processeur dans les instances d'une charge de travail et déploiera des instances supplémentaires lorsque certains critères sont remplis afin de réduire la charge sur chaque instance. Lorsque StackPath détecte que la charge de toutes les instances a baissé suffisamment pour répondre aux critères de mise à l'échelle automatique, les instances sont automatiquement supprimées de la charge de travail.

Lors du déploiement, chaque instance reçoit un volume racine dont la taille est définie par l'image. Si un stockage supplémentaire est nécessaire, un volume persistant peut être attaché à chaque machine virtuelle ou conteneur dans une charge de travail. Cela est particulièrement utile pour les charges de travail utilisant des instances de conteneur, pour lesquelles le volume racine **ne persiste pas**.

Chaque instance d'une charge de travail obtient une adresse IP privée et publique lors de sa création.  <!-- [Network policies](stackpack-network-policies.md) -->  Les **politiques de réseau** contrôlent l'accès aux instances dans une charge de travail. Pour les déploiements plus complexes, une **adresse IP Anycast** peut être ajoutée au moment de la création de la charge de travail, et restera attribuée à la charge de travail pendant toute sa durée de vie. Les adresses IP Anycast sont une fonctionnalité de StackPath et fournissent un routage optimal pour le trafic, se comportant essentiellement comme un équilibreur de charge global pour votre charge de travail.  <!-- Need to show where Anycast IPs send traffic.  This is not clear to me at this time. -->



### Liens externes

[Create and Manage Virtual Machines, Containers, and Workloads](https://support.stackpath.com/hc/en-us/articles/360022756051-Create-and-Manage-Virtual-Machines-Containers-and-Workloads)

[Edge Computing: Using Global Anycast IP Addresses](https://support.stackpath.com/hc/en-us/articles/360022801751-Edge-Computing-Using-Global-Anycast-IP-Addresses)

[Learn about Environment Variables](https://support.stackpath.com/hc/en-us/articles/360022768891)

[Edge Computing:  Enabling Auto-Scaling on Your Workload](https://support.stackpath.com/hc/en-us/articles/360034604611-Edge-Computing-Enabling-Auto-Scaling-on-Your-Workload)
