---
title: "GCP: Gestion des disques et copies instantanées"
slug: gcp-gestion-des-disques-et-copies-instantanees
---


Un **disque** est un stockage présenté à une instance en tant que périphérique bloc, qui peut ensuite être monté et utilisé. Toutes les instances ont un **disque de démarrage**, qui peut être redimensionné mais qui ne peut pas être détaché de son instance. Des disques persistants supplémentaires peuvent être créés, redimensionnés, attachés ou détachés et supprimés.

Pour créer, modifier ou supprimer un disque, un compte avec le rôle *Utilisateur* doit être membre de l'environnement qui contient l'instance, et également avoir le rôle d'environnement *Éditeur* ou *Propriétaire* attribué. Un compte avec le rôle *Administrateur* ou supérieur peut créer, modifier ou supprimer des disques dans un environnement.

Pour accéder aux disques, accédez à votre environnement Google Cloud Platform et cliquez sur l'onglet **Calcul**, puis cliquez sur *Disques*.

### Créer un disque

1. Sur la page *Disques*, cliquez sur *Ajouter un disque*. Vous serez redirigé vers la page *Ajouter un disque*.
1. Entrez un nom pour votre disque.
1. Sélectionnez la région et la zone dans lesquelles vous souhaitez que le disque soit disponible. La région et la zone ne peuvent pas être modifiées une fois le disque créé. Un disque ne peut être attaché qu'à une instance de la même région et zone.
1. Entrez les paramètres de type de disque, de taille de disque et de taille de bloc.
1. Cliquez sur *Valider*. Le disque sera créé et apparaîtra sur la page *Disques* à l'état **prêt**.

### Attacher un disque à une instance

Un disque ne peut pas être attaché à une instance lorsque le disque est déjà à l'état **attaché**.

1. À partir de la page *Disques*, cliquez sur le menu **Action** à droite du disque que vous souhaitez attacher, puis cliquez sur *Attacher*.
1. La boîte de dialogue *Attacher* apparaît. Sélectionnez l'instance souhaitée dans la liste contextuelle **Instance**.
1. Choisissez si ce disque doit être présenté à l'instance en tant que périphérique inscriptible ou en tant que périphérique en lecture seule.
1. Choisissez si ce disque doit être conservé si l'instance à laquelle il est attaché est supprimée ou si ce disque doit être supprimé avec l'instance attachée.
1. Cliquez sur *Valider*. Le disque sera attaché à l'instance et le disque apparaîtra dans l'état **attaché**. Le disque est maintenant prêt à être monté ou partitionné.

### Détacher un disque d'une instance

**Avis :** Le détachement d'un disque d'une instance en cours d'exécution peut entraîner une corruption du disque et une perte de données. Démontez toujours correctement le volume du système d'exploitation de l'instance avant de détacher un disque.

1. Sur la page *Disques*, cliquez sur le menu **Action** à droite du disque que vous souhaitez détacher, puis cliquez sur *Détacher*.
1. Une boîte de dialogue apparaîtra, demandant la confirmation de continuer. Cliquez sur *Valider*.
1. Le disque sera détaché et reviendra à l'état **prêt**.

Alternativement, un disque peut être détaché d'une instance via la page *détails de l'instance*.

### Redimensionner un disque

Un disque peut être redimensionné pour augmenter la quantité d'espace de stockage alloué. L'espace disque ne peut qu'être augmenté. La réduction de la taille d'un disque n'est pas prise en charge.

1. Sur la page *Disques*, cliquez sur le menu **Action** à droite du disque que vous souhaitez redimensionner, puis cliquez sur *Redimensionner*.
1. Une boîte de dialogue apparaîtra. Dans la zone de texte intitulée **Taille du disque**, entrez le nombre de gigaoctets souhaité pour le disque.
1. Cliquez sur *Valider*. Le disque sera redimensionné et une notification apparaîtra lorsque l'opération sera terminée.
1. Le système de fichiers peut désormais être étendu à partir du système d'exploitation de l'instance.

Sinon, un disque peut être redimensionné s'il est attaché via la page *détails de l'instance*.

### Supprimer un disque

Un disque doit être détaché avant de pouvoir être supprimé. La suppression d'un disque est définitive. Cette action ne peut pas être annulée.

1. Dans la page *Disques*, cliquez sur le menu **Action** à droite du disque que vous souhaitez supprimer, puis cliquez sur *Supprimer*.
1. Une boîte de dialogue apparaîtra, demandant la confirmation de continuer. Cliquez sur *Valider*.
1. Ce disque sera supprimé et sera supprimé de la liste des disques.

### Prendre une copie instantanée d'un disque

Une copie instantanée d'un disque est une copie d'un disque à un moment donné.

1. Sur la page *Disques*, cliquez sur le menu **Action** à droite du disque que vous souhaitez prendre en photo, puis cliquez sur *Prendre une copie instantanée*.
1. Une boîte de dialogue apparaîtra, vous demandant le nom à donner à la copie instantanée. Cliquez sur *Valider*.
1. La copie instantanée sera prise et apparaîtra sur la page *Copies instantanées* dans l'état **En cours de création**.
1. Lorsque l'instantané est créé, il passe à l'état **Téléversement**. Lorsqu'il est terminé, il apparaîtra dans l'état **Prêt**.
