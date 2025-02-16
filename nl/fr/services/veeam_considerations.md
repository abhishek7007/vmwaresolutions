---

copyright:

  years:  2016, 2019

lastupdated: "2019-03-07"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Présentation de Veeam on IBM Cloud
{: #veeam_considerations}

Le service Veeam on {{site.data.keyword.cloud}} s'intègre directement et en toute transparence à vos hyperviseurs VMware afin d'aider votre entreprise à obtenir la haute disponibilité requise. Il fournit des objectifs de points de récupération et de temps de reprise pour vos applications et vos données. Ces objectifs peuvent être fournis en moins de 15 minutes après la fin de la configuration. Ce service vous permet de contrôler directement à la fois la sauvegarde et la restauration de toutes les machines virtuelles de votre infrastructure depuis la console Veeam.

Ce service est disponible uniquement sur les instances déployées en version 1.8 ou dans des éditions ultérieures. La version de Veeam en cours qui est installée est la version 9.5u4.
{:note}

## Spécifications techniques relatives à Veeam on IBM Cloud
{: #veeam_considerations-specs}

Les composants suivants sont commandés et inclus dans le service Veeam on {{site.data.keyword.cloud_notm}} :

### Instances de serveur virtuel
{: #veeam_considerations-specs-vsi}

* Une instance de serveur virtuel avec service complémentaire Veeam Backup and Replication 9.5
* Windows Server 2016 Standard Edition (64 bits)
* 4 coeurs de 2 GHz
* 8 Go de mémoire RAM
* Liaison montante de réseau privé 1 Gbps
* Disque 100 Go (SAN)

### Stockage pour les sauvegardes
{: #veeam_considerations-specs-storage}

* Stockage Endurance iSCSI (2000, 4000, 8000 ou 12000 Go)
* Performances de stockage (0,25, 2 ou 4 IOPS/Go)

### Utilisation en réseau
{: #veeam_considerations-specs-networking}

Une adresse IP privée principale

### Licences et frais
{: #veeam_considerations-specs-licenses}

Veeam Backup and Replication 9.5 Enterprise Plus (licence pour 10, 25, 50, 100 ou 200 machines virtuelles)

### Gestion
{: #veeam_considerations-specs-mgmt}

Des sauvegardes de gestion sont configurées par défaut avec un maximum de cinq machines virtuelles et 2000 Go de stockage

## Remarques relatives à l'installation de Veeam on IBM Cloud
{: #veeam_considerations-install}

Le référentiel du stockage et celui du serveur Veeam se trouvent dans le pod et le centre de données d'origine. Par conséquent, les performances des opérations de sauvegarde des clusters distants peuvent se dégrader.

## Remarques relatives au retrait de Veeam on IBM Cloud
{: #veeam_considerations-remove}

Le retrait du service Veeam on {{site.data.keyword.cloud_notm}} arrête toutes les sauvegardes et supprime toutes les sauvegardes précédentes. Les sauvegardes des machines virtuelles de gestion sont arrêtées et la suppression des sauvegardes précédentes est irréversible. Si les machines virtuelles de gestion sont endommagées, leur restauration est impossible.

## Liens connexes
{: #veeam_considerations-related}

* [Commande de Veeam on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-veeam_ordering)
* [Gestion de Veeam on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-managingveeam)
* [Demande de services gérés pour Veeam on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-managing_veeam_services)
* [Contacter le support IBM](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support)
* [Foire aux questions](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-faq)
* [Site Web Veeam](https://www.veeam.com/){:new_window}
* [Centre d'information Veeam](https://www.veeam.com/documentation-guides-datasheets.html){:new_window}
