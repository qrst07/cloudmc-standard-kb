---
title: "Microsoft Azure: Gestion des instances"
slug: azure-gestion-des-instances
---


Pour créer, modifier ou supprimer une instance, un compte avec le rôle *Utilisateur* doit être membre de l'environnement qui contient l'instance, et également avoir le rôle d'environnement *Éditeur* ou *Propriétaire* attribué. Un compte avec le rôle *Administrateur* ou supérieur peut créer, modifier ou supprimer des instances dans un environnement.

Pour accéder aux instances, accédez à votre environnement Microsoft Azure et cliquez sur l'onglet **Instances**.

<!-- Creating an environment - Advanced - Select region -->

### Ajouter une instance

Avant d'ajouter une instance, vous devez avoir au moins un réseau créé dans votre environnement Microsoft Azure.

1. Cliquez sur *Ajouter une instance*.
1. Sur la page *Ajouter une instance*, entrez les paramètres requis pour l'instance souhaitée. Les coûts horaires et mensuels estimés apparaîtront sur le côté droit.
1. Sélectionnez la région dans laquelle créer l'instance. La région ne peut pas être modifiée une fois l'instance est créée.
1. Vous pouvez choisir de joindre une adresse IP publique lors de la création de l'instance. Il doit y avoir une adresse IP publique déjà allouée et non connectée sur le réseau où l'instance doit être créée.
1. Sélectionnez le sous-réseau à attacher à cette instance.
1. Cliquez sur *Valider*. L'onglet **Instances** apparaîtra. Une fois la nouvelle instance est créée, elle apparaîtra dans la liste et sera à l'état **En démarrage**. Une fois l'instance provisionnée, elle passera à l'état **Active**.

### Obtenir les détails de l'instance

1. Dans l'onglet **Instances**, cliquez sur l'instance. Cela vous mènera à la page *Détails* de l'instance.
    - Dans l'onglet **Instances**, cliquer sur le nom ou l'adresse IP d'une instance copiera ces données dans votre presse-papiers et *ne vous mènera pas* à la page *Détails* de l'instance.
1. Sur la page *Détails* de l'instance, cliquer sur une chaîne de caractères la copiera dans votre presse-papiers.
1. Cliquez sur *Disques* pour accéder à la page *Disques* de l'instance, où vous pouvez ajouter, redimensionner, détacher ou supprimer des disques sur cette instance. Consultez [Azure: Gestion des disques](azure-working-with-disks.md) pour plus d'informations.

### Arrêter une instance en cours d'exécution

1. Dans l'onglet **Instances**, cliquez sur le menu **Action** à droite de l'instance et sélectionnez *Arrêter l'instance*.
1. Une boîte de dialogue apparaîtra, demandant la confirmation de continuer. Cliquez sur *Valider*.
1. L'instance entrera dans l'état **En cours d'arrêt**. Une fois que l'instance a cessé de s'exécuter, elle passe à l'état **Arrêtée**.

### Démarrer une instance arrêtée

1. Dans l'onglet **Instances**, cliquez sur le menu **Action** à droite de l'instance, et sélectionnez *Démarrer l'instance*.
1. L'instance entrera dans l'état **En traitement**. Une fois que l'instance démarre, elle entre dans l'état **Active**.

### Supprimer une instance

Une instance dans n'importe quel état peut être supprimée. Par défaut, le disque de démarrage est supprimé avec l'instance (voir ci-dessous), mais tous les disques de données qui sont attachés à l'instance seront détachés avant la suppression de l'instance, et les disques resteront à l'état **Détaché**.

1. Dans l'onglet **Instances**, cliquez sur le menu **Action** à droite de l'instance, et sélectionnez *Supprimer*.
1. Une boîte de dialogue apparaîtra, demandant la confirmation de continuer. Cliquez sur *Valider*.
    - La boîte de dialogue offrira également la possibilité de supprimer le disque de démarrage, qui est sélectionné par défaut. Désélectionner cette case détachera le disque de démarrage avant de supprimer l'instance, et le disque restera à l'état **Détaché**.
1. L'instance entrera dans l'état **En cours de suppression**. Une fois la suppression terminée, l'instance sera supprimée de l'onglet **Instances**.
