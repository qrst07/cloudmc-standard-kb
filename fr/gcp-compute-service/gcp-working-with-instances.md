---
title: "GCP: Gestion des instances"
slug: gcp-gestion-des-instances
---


Pour créer, modifier ou supprimer une instance, un compte avec le rôle *Utilisateur* doit être membre de l'environnement qui contient l'instance, et également avoir le rôle d'environnement *Éditeur* ou *Propriétaire* attribué. Un compte avec le rôle *Administrateur* ou supérieur peut créer, modifier ou supprimer des instances dans un environnement.

Pour accéder aux instances, accédez à votre environnement GCP et cliquez sur l'onglet **Calcul**.  Au moins au VPC doit exister pour qu'une instance puisse être créée.

### Ajouter une instance

1. Cliquez sur *Ajouter une instance*.
1. Sur la page *Ajouter une instance*, entrez les paramètres requis pour l'instance souhaitée. Les coûts horaires et mensuels estimés apparaîtront sur le côté droit.
1. Vous pouvez choisir d'autoriser le trafic HTTP (port 80) ou HTTPS (port 443), ou les deux. Cela créera une règle de pare-feu autorisant le trafic sélectionné vers cette VM.
1. Vous pouvez choisir d'attacher une adresse IP publique à l'instance avec le menu contextuel **Attacher une IP externe**.
    - **Aucun :** Votre instance n'aura pas d'adresse IP publique.
    - **Nouvelle adresse IP éphémère :** Votre instance se verra attribuer une nouvelle adresse IP publique à chaque démarrage.
    - **Nouvelle IP statique :** Une adresse IP publique sera réservée spécifiquement pour cette instance, et sera la même à chaque démarrage.
1. Vous pouvez choisir de spécifier un script de démarrage à exécuter à chaque démarrage de l'instance. Entrez le script de démarrage souhaité dans la zone de texte intitulée **Automatisation - Script de démarrage**. Pour les instances exécutant des systèmes d'exploitation basés sur Unix, il peut s'agir d'un script shell, et pour les instances Windows, il peut s'agir d'une clé de métadonnées, où la valeur correspond aux commandes batch ou aux commandes PowerShell souhaitées.
1. Cliquez sur *Valider*. La nouvelle instance apparaîtra dans la liste et sera à l'état **En provisionnement**. Lorsque l'instance a été provisionnée, elle passera à l'état **Active**.

### Obtenir les détails de l'instance

1. Dans l'onglet **Calcul**, cliquez sur l'instance. Cela vous mènera à la page *Détails de l'instance*.
    - Dans l'onglet **Calcul**, cliquer sur le nom ou l'adresse IP d'une instance copiera ces données dans votre presse-papiers et ne vous mènera *pas* à la page *Détails de l'instance*.
1. Sur la page *Détails de l'instance*, cliquer sur n'importe quelle chaîne la copiera dans votre presse-papiers.
1. Cliquez sur *Disques* pour accéder à la page *Disques d'instance*, où vous pouvez ajouter, redimensionner, détacher ou supprimer des disques sur cette instance. Voir [GCP: Travailler avec des disques](gcp-working-with-disks.md) pour plus d'informations.

### Arrêter une instance active

1. Dans l'onglet **Calcul**, cliquez sur le menu **Action** à droite de l'instance et sélectionnez *Arrêter instance*.
1. Une boîte de dialogue apparaîtra, demandant la confirmation de continuer. Cliquez sur *Valider*.
1. L'instance entrera dans l'état **En cours d'arrêt**. Une fois que l'instance a cessé de fonctionner, elle passe à l'état **Terminé**.

**Remarque :** Si l'instance ne s'arrête pas dans les 90 secondes, l'instance sera arrêtée de force.

### Démarrer une instance arrêtée

1. Dans l'onglet **Calcul**, cliquez sur le menu **Action** à droite de l'instance, et sélectionnez *Démarrer instance*.
1. L'instance entrera dans l'état **En provisionnement**. Une fois que l'instance démarre, elle entre dans l'état **Active**.

### Supprimer une instance

Une instance dans n'importe quel état peut être supprimée.

**Avis :** La suppression d'une instance supprimera le disque de démarrage, ainsi que tous les disques qui étaient attachés à l'instance avec la règle de suppression *Supprimer le disque* sélectionnée.

1. Dans l'onglet **Calcul**, cliquez sur le menu **Action** à droite de l'instance, et sélectionnez *Supprimer*.
1. Une boîte de dialogue apparaîtra, demandant la confirmation de continuer. Cliquez sur *Valider*.
1. Si l'instance est en cours d'exécution, elle passera à l'état **En cours d'arrêt**, après quoi elle sera supprimée. Si l'instance est déjà arrêtée, elle sera supprimée immédiatement.

### Se connecter via SSH (pour les instances Linux)

Utilisez cette commande pour configurer l'accès SSH à l'instance. Vous recevrez une demande pour fournir votre clé publique SSH ou de sélectionner une clé existante.

1. Dans l'onglet **Calcul**, cliquez sur le menu **Action** à droite de l'instance et sélectionnez **Obtenir la commande SSH**.
1. La boîte de dialogue **Obtenir la commande SSH** apparaît.
   - Si vous avez déjà configuré une ou plusieurs clés publiques SSH, celles-ci apparaîtront dans le menu contextuel intitulé **Clé SSH**.
   - Si vous n'avez pas configuré de clé SSH, ou si vous souhaitez en configurer une nouvelle, sélectionnez l'option *Nouvelle clé SSH* dans le menu contextuel **Clé SSH**, puis saisissez la clé publique souhaitée dans le zone de texte intitulée **Clé publique**.
1. Cliquez sur *Valider*.
1. La boîte de dialogue disparaîtra. Une règle de pare-feu sera créée pour autoriser le trafic SSH (port 22) vers cette instance. Une notification apparaîtra, fournissant la commande SSH qui peut être utilisée pour se connecter à l'instance.

**Avis :** Votre client SSH doit déjà être configuré avec la clé privée de la clé publique que vous avez sélectionnée.

### Se connecter via Remote Desktop (pour les instances Microsoft Windows)

Utilisez cette commande pour configurer l'accès Remote Desktop (RDP) à l'instance.

1. Dans l'onglet **Calcul**, cliquez sur le menu **Action** à droite de l'instance et sélectionnez *Configurer le mot de passe*. Cette opération ne peut être effectuée que sur une instance à l'état **Active**.
1. La boîte de dialogue *Configurer le mot de passe* apparaît. Entrez votre nom d'utilisateur et cliquez sur *Valider*.
    **Avis :** La définition du mot de passe d'un compte qui existe déjà peut entraîner la perte des données chiffrées du compte.
1. Momentanément, une notification apparaîtra, affichant l'adresse IP de l'instance et les informations d'identification pour se connecter.
1. Configurez votre client Remote Desktop avec ces paramètres. Vous pouvez maintenant vous connecter à l'instance.
