---
title: "Microsoft Azure: Gestion des disques"
slug: azure-gestion-des-disques
---


Un **disque** est un stockage présenté à une instance en tant que périphérique en mode bloc, qui peut ensuite être monté et utilisé. Toutes les instances ont un disque de démarrage, qui peut être redimensionné mais qui ne peut pas être détaché de son instance. Des disques supplémentaires peuvent être créés, redimensionnés, attachés ou détachés, et supprimés.

Pour créer, modifier ou supprimer un disque, un compte avec le rôle *Utilisateur* doit être membre de l'environnement qui contient l'instance, et également avoir le rôle d'environnement *Éditeur* ou *Propriétaire* attribué. Un compte avec le rôle *Administrateur* ou supérieur peut créer, modifier ou supprimer des disques dans un environnement.

Pour accéder aux disques, accédez à votre environnement Microsoft Azure et cliquez sur l'onglet **Disques**.

### Créer un disque

1. Dans l'onglet *Disques*, cliquez sur *Ajouter un disque*. Vous serez redirigé vers la page *Ajouter un disque*.
1. Entrez un nom pour votre disque.
1. Sélectionnez la région dans laquelle vous souhaitez que le disque soit disponible. La région ne peut pas être modifiée une fois le disque est créé. Un disque ne peut être attaché qu'à une instance de la même région.
1. Entrez les paramètres pour le type de disque et la taille du disque.
1. Cliquez sur *Valider*. L'onglet **Disques** apparaîtra. Le disque sera créé et apparaîtra dans l'état **Détaché**.

### Attacher un disque à une instance

Un disque ne peut être attaché à une instance que lorsque le disque est à l'état **Détaché**. En plus, au moins une instance doit exister dans la région où se trouve le disque.

1. Dans l'onglet **Disques**, cliquez sur le menu **Action** à droite du disque que vous souhaitez attacher, puis cliquez sur *Attacher*.
1. La boîte de dialogue *Attacher* apparaît. Sélectionnez l'instance souhaitée dans la liste contextuelle **Instance**.
    - Par défaut, un disque est attaché à une instance avec le Logical Unit Number (LUN) le plus bas disponible sur l'instance. Si un LUN personnalisé est requis pour ce disque, cochez la case **LUN personnalisé** et spécifiez le LUN que vous souhaitez attribuer à ce disque. Le LUN choisi doit être unique de tous les autres disques attachés à l'instance.
1. Cliquez sur *Valider*. Le disque sera attaché à l'instance et le disque apparaîtra dans l'état **Attaché**. Le disque est maintenant prêt à être monté ou partitionné.

### Détacher un disque d'une instance

**Avis :** Le détachement d'un disque d'une instance en cours d'exécution peut entraîner une corruption du disque et une perte de données. Démontez toujours correctement le volume du système d'exploitation de l'instance avant de détacher un disque.

1. Dans l'onglet **Disques**, cliquez sur le menu **Action** à droite du disque que vous souhaitez détacher, puis cliquez sur *Détacher*.
1. La boîte de dialogue *Détacher* apparaîtra, demandant la confirmation de continuer. Cliquez sur *Valider*.
1. Le disque sera détaché et reviendra à l'état **Détaché**.

Alternativement, un disque peut être détaché d'une instance via la page *Détails* de l'instance.

### Redimensionner un disque ou modifier le type de disque

Un disque peut être redimensionné pour augmenter la quantité d'espace de stockage alloué. L'espace disque ne peut qu'être augmenté. La réduction de la taille d'un disque n'est pas prise en charge. En plus, le type de performance du disque peut être modifié.

**Avis :** Si le disque est attaché à une instance en cours d'exécution, la modification du disque redémarrera l'instance.

1. Dans la page *Disques*, cliquez sur le menu **Action** à droite du disque que vous souhaitez modifier, puis cliquez sur *Modifier*.
1. La page *Modifier* apparaîtra.
1. Pour modifier le type de performance du disque, sélectionnez l'option souhaitée dans la liste contextuelle **Type**.
1. Pour redimensionner le disque, déplacez le curseur **Taille du disque** sur le nombre de gigaoctets souhaité pour le disque.
1. Cliquez sur *Valider*. Le disque sera modifié en conséquence et une notification apparaîtra lorsque l'opération sera terminée.
1. Le système de fichiers peut désormais être étendu à partir du système d'exploitation de l'instance.

Également, un disque peut être redimensionné s'il est attaché via la page *Disques* de l'instance.

### Supprimer un disque

Un disque doit être détaché avant de pouvoir être supprimé. La suppression d'un disque est définitive. Cette action ne peut pas être annulée.

1. Dans l'onglet **Disques**, cliquez sur le menu **Action** à droite du disque que vous souhaitez supprimer, puis cliquez sur *Supprimer*.
1. Une boîte de dialogue apparaîtra, demandant la confirmation de continuer. Cliquez sur *Valider*.
1. Ce disque sera supprimé et sera retiré de la liste des disques.
