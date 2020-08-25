---
title: "GCP: Groupes d'instances"
slug: gcp-groupes-d-instances
---


**Les groupes d'instances** sont utilisés pour fournir des services de backend tels que l'équilibrage de charge. Les groupes d'instances existent dans une seule zone d'une région et peuvent contenir des instances uniquement dans cette zone.

Pour créer, modifier ou supprimer un groupe d'instances, un compte avec le rôle *Utilisateur* doit être membre de l'environnement qui contient l'instance, et également avoir le rôle d'environnement *Editeur* ou *Propriétaire* attribué. Un compte doté du rôle *Administrateur* ou supérieur peut créer, modifier ou supprimer des groupes d'instances dans un environnement.

Pour gérer les groupes d'instances, accédez à l'environnement GCP souhaité, cliquez sur l'onglet **Calcul**, puis sur *Groupes d'instances*.

### Ajouter un groupe d'instances

1. Depuis la page *Groupes d'instances*, cliquez sur *Ajouter un groupe d'instances*. La page *Ajouter un groupe d'instances* apparaîtra.
1. Fournissez un nom pour le groupe d'instances et une description facultative.
1. Sélectionnez la région et la zone où se trouvent les instances à regrouper.
1. Si le sous-réseau sélectionnée contient des instances, une liste contextuelle intitulée **Instances** apparaîtra sous le sous-réseau. Vous pouvez choisir zéro ou plusieurs instances de cette liste pour devenir membres de ce groupe d'instances. Notez que changer une zone effacera la liste des instances déjà sélectionnées.
1. Cliquez sur *Valider* pour créer le groupe.
1. Vous serez renvoyé à la page *Groupes d'instances*, le groupe d'instances sera créé et les instances seront ajoutées au groupe.

**Avis :** Une fois qu'un groupe d'instances est créé, sa région et sa zone ne peuvent pas être modifiées.

### Gérer un groupe d'instances

1. Sur la page *Groupes d'instances*, cliquez sur le menu **Action** et sélectionnez *Modifier les membres du groupe*. La boîte de dialogue *Modifier les membres du groupe* s'affiche.
1. La liste contextuelle intitulée **Instances** contiendra une liste des instances qui sont membres de ce groupe.
    - Pour supprimer une instance du groupe, cliquez sur la marque X à droite du nom d'une instance.
    - Pour ajouter une instance au groupe, cliquez sur la liste pop-up, puis cliquez sur le nom de l'instance que vous souhaitez ajouter.
1. Cliquez sur *Valider* lorsque vous avez terminé les modifications.

### Supprimer un groupe d'instances

Un groupe d'instances utilisé par un service de backend ne peut pas être supprimé. La suppression d'un groupe d'instances ne supprime pas ses instances membres.

1. Sur la page *Groupes d'instances*, cliquez sur le menu **Action** et sélectionnez *Supprimer*.
1. Vous serez invité à confirmer l'opération. Cliquez sur *Valider* pour confirmer.
