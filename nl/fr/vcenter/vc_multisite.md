---

copyright:

  years:  2016, 2019

lastupdated: "2019-05-06"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Configuration multisite pour des instances vCenter Server on IBM Cloud
{: #vc_multisite}

{{site.data.keyword.vmwaresolutions_full}} permet de déployer des instances dans différents emplacements et de les rendre actives et opérationnelles très rapidement.

La configuration multisite pour des instances vCenter Server est uniquement prise en charge dans les instances de la version 2.0 et des versions ultérieures.
{:note}

## Composants d'un déploiement multisite
{: #vc_multisite-deployment-components}

Un déploiement multisite est constitué des composants suivants.

* **Instance principale** : l'instance principale VMware vCenter Server présente la configuration suivante :
  *  Domaine racine Microsoft Active Directory (AD) et système de noms de domaine (DNS, Domain Name System)
  *  Sous-domaine vCenter Server
  *  Domaine de connexion unique
  *  Nom de site de connexion unique
* **Instance ou instances secondaires** : une ou plusieurs instances vCenter Server liées à l'instance principale, qui présentent la configuration suivante :
   *  Nom de site de connexion unique
   *  Sous-domaine DNS lié au domaine racine sur l'instance principale
   *  Réplication DNS et AD configurée entre les machines virtuelles AD de l'instance principale et des instances secondaires
   *  Pour les instances principales qui sont déployées dans la version 2.8 ou une version ultérieure : vCenter Server Appliance (vCSA) avec contrôleur PSC (Platform Services Controller) intégré, déployé et configuré
   *  VMware vCenter sur les instances secondaires configuré en mode lien étendu (Enhanced Linked) sur le serveur vCenter de l'instance principale

## Déploiement multisite vCenter Server
{: #vc_multisite-deployment}

Le modèle de configuration multisite utilise un concentrateur et une topologie en étoile (hub and spoke) avec un site principal et un maximum de sept sites secondaires. Une seule couche de sites est prise en charge, c'est-à-dire que vous ne pouvez pas configurer de sites supplémentaires qui sont liés à d'autres sites secondaires. Une configuration multisite accepte jusqu'à 128 serveurs ESXi répartis dans toutes les instances.

Si votre configuration nécessite un déploiement multisite de plus de 128 serveurs ESXi, contactez le support IBM pour obtenir de l'aide. Pour plus d'informations, voir [Contacter le support IBM](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support).
{:note}

Le graphique suivant décrit l'architecture globale d'un déploiement multisite de vCenter Server. 

![Déploiement multisite de vCenter Server](../images/multisite-hub-spoke.svg "Déploiement multisite de vCenter Server")

Le modèle contient les couches suivantes :

* **Instance principale** : dans une configuration multisite, pour déployer la première instance, vous définissez cette dernière en tant qu'instance principale au cours du processus de commande de l'instance.
* **Instance secondaire** : dans une configuration multisite, vous définissez les instances liées à l'instance principale en tant qu'instances secondaires au cours du processus de commande.

Vous ne pouvez affecter qu'une seule instance secondaire à la fois à une instance principale. Vous ne pouvez pas affecter plusieurs instances secondaires à une instance principale simultanément. Pour ce faire, vous devez exécuter de nouveau le processus de commande et sélectionner l'instance précédemment définie comme instance principale pour l'instance secondaire. Vous devez répéter le processus pour toutes les instances secondaires à créer.

Vous pouvez avoir jusqu'à 8 instances (1 principale et 7 secondaires) au maximum déployées dans une configuration multisite.

La suppression d'instances vCenter Server qui font partie d'une configuration multisite requiert une planification spéciale. Pour plus d'informations, voir [Suppression d'instances vCenter Server dans une configuration multisite](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_deletinginstance_multi).
{:note}

## Liens connexes
{: #vc_multisite-related}

* [Attribuer un rôle principal à NSX Manager](https://docs.vmware.com/en/VMware-NSX-Data-Center-for-vSphere/6.2/com.vmware.nsx-cross-vcenter-install.doc/GUID-44E8AE16-BA3F-4DD9-B582-FC1E137E6CFC.html){:new_window}
* [Configurer les NSX Manager secondaires](https://pubs.vmware.com/NSX-62/topic/com.vmware.nsx-cross-vcenter-install.doc/GUID-9E48BC57-15E3-49C7-8BC5-F94ED8918BBE.html){:new_window}
* [Approbations Microsoft Active Directory prises en charge avec VMware vCenter SSO](https://kb.vmware.com/s/article/2064250){:new_window}
