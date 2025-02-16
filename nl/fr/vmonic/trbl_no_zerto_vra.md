---

copyright:

  years:  2016, 2019

lastupdated: "2019-02-14"

subcollection: vmware-solutions


---

# Les dispositifs de réplication Zerto Virtual Replication Appliance ne s'affichent pas pour les serveurs ESXi qui viennent d'être créés
{: #trbl_no_zerto_vra}

## Problème
{: #trbl_no_zerto_vra-problem}

Les dispositifs Virtual Replication Appliances (VRA) ne s'affichent pas sur la console de réplication virtuelle Zerto après l'ajout de serveurs ESXi à une instance VMware vCenter Server sur laquelle la reprise après incident Zerto est installée.

## Résolution
{: #trbl_no_zerto_vra-resolution}

Pour les instances vCenter Server, la reprise après incident Zerto n'est installée que sur le serveur ESXi à partir du cluster par défaut, **cluster1**. Tous les autres clusters du même environnement vCenter Server ne bénéficient pas automatiquement de la reprise après incident Zerto lorsqu'ils sont créés ou lorsque le serveur ESXi est ajouté à ces clusters supplémentaires.

Sur les clusters ajoutés, vous devez installer la reprise après incident Zerto séparément.

Ouvrez un ticket de demande de service {{site.data.keyword.cloud}} et contactez le support IBM afin d'obtenir les adresses IP disponibles pour installer les dispositifs VRA à partir de la console Zerto, au lieu de la console {{site.data.keyword.vmwaresolutions_short}}.

Pour accéder à la console Zerto, cliquez sur la carte Zerto depuis l'onglet **Services** de l'instance et cliquez sur **Afficher des détails**, puis sur **Afficher la console Zerto**.

Pour savoir comment contacter le support IBM, voir [Contacter le support IBM](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-trbl_support#trbl_support).
