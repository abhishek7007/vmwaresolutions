---

copyright:

  years:  2016, 2019

lastupdated: "2019-05-06"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Présentation de la version d'essai à noeud unique pour la migration et la modernisation des applications
{: #cloud_modern_bundle_overview}

La version d'essai à noeud unique pour la migration et la modernisation des applications permet de tester l'utilisation d'{{site.data.keyword.cloud_notm}} pour migrer les charges de travail VMware vers {{site.data.keyword.cloud}}, puis de moderniser ces simples charges de travail à l'aide de conteneurs.

La version à noeud unique est une version d'essai d'{{site.data.keyword.cloud_notm}} Private Hosted sur VMware vCenter Server on {{site.data.keyword.cloud_notm}} qui fournit la plateforme de gestion Kubernetes pour les conteneurs et la plateforme VMware à service exclusif qui peut être gérée à l'aide des mêmes outils que dans les environnements locaux. Vous pouvez ainsi bénéficier de la vitesse et de l'échelle du cloud tout en conservant le même niveau de contrôle et de visibilité que dans un environnement local.

La version d'essai permet de migrer jusqu'à 20 charges de travail simples de développement ou de test à l'aide de vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle et de conteneuriser ces charges de travail avec la plateforme de développement d'applications {{site.data.keyword.cloud_notm}} Private Hosted basée sur Kubernetes. L'automatisation installe et configure VMware HCX dans {{site.data.keyword.cloud_notm}}, fournit une clé d'activation HCX sur site, puis installe et configure une petite topologie de développement/test d'{{site.data.keyword.cloud_notm}} Private Hosted en quelques heures seulement.

La version d'essai à noeud unique pour la migration et la modernisation des applications est destinée à une démonstration de faisabilité uniquement. N'exécutez pas de charges de travail de production dans cet environnement. Les fonctions de gestion, telles que l'ajout et le retrait d'hôtes et de clusters, la commande de services complémentaires et l'application de mises à jour ne sont pas prises en charge.
{:important}

Pour tirer le meilleur parti de l'instance Version d'essai à noeud unique pour la migration et la modernisation des applications, vous pouvez utiliser [IBM On Demand Consulting for Hybrid Cloud](https://public.dhe.ibm.com/software/data/sw-library/services/ODC.pdf){:new_window} dans [IBM Analytics Cloud Expert Services](https://www.ibm.com/analytics/us/en/services/cloud-expert-services.html){:new_window}, pour vous aider à migrer vos charges de travail VMware vers {{site.data.keyword.cloud_notm}}. En outre, [{{site.data.keyword.cloud_notm}} Garage Services](https://www.ibm.com/cloud/garage/){:new_window} peut vous aider à accélérer la modernisation des applications grâce aux dernières recommandations pour le cloud natif.

Cette version d'essai peut être utilisée pendant un maximum de 90 jours. Une fois qu'elle a expiré, vous pouvez supprimer cet environnement, puis mettre à disposition un nouvel environnement répondant à vos besoins en matière de capacité.
{:note}

## Spécifications techniques relatives aux instances Version d'essai à noeud unique pour la migration et la modernisation des applications
{: #cloud_modern_bundle_overview-tech-specs}

Les composants suivants sont inclus dans votre instance Version d'essai à noeud unique pour la migration et la modernisation des applications.

La disponibilité et la tarification des configurations matérielles normalisées peuvent varier en fonction de l'{{site.data.keyword.CloudDataCent_notm}} sélectionné pour le déploiement.
{:note}

### Serveur bare metal
{: #cloud_modern_bundle_overview-bare-metal}

Processeur Dual Intel Xeon Gold 5120/28 coeurs au total, 2,2 GHz avec 384 GB de mémoire RAM, pour jusqu'à 20 MV

#### Surallocations d'UC
{: #cloud_modern_bundle_overview-cpu}

* Surallocation d'UC 16:1 pour la gestion vCenter Server, HCX et 20 MV de charge de travail client
* Surallocation d'UC 11:1 pour {{site.data.keyword.cloud_notm}} Private

#### Surallocations de mémoire RAM
{: #cloud_modern_bundle_overview-ram}

* Surallocation de mémoire RAM 1.22:1 pour un déploiement client de 20 MV de charge de travail avec 8 Go chacune
* 1:1 (pas de surallocation) pour un déploiement client de neuf MV de charge de travail avec 8 Go chacune

### Stockage NFS
{: #cloud_modern_bundle_overview-nfs-storage}

* 2 To pour la gestion
* 1 To pour la charge de travail client (pour 20 MV client)
* 4 To pour {{site.data.keyword.cloud_notm}} Private Hosted

### Spécifications de mise en réseau relatives aux instances Version d'essai à noeud unique pour la migration et la modernisation des applications
{: #cloud_modern_bundle_overview-networking-specs}

Les composants réseau suivants sont commandés :
*  Liaisons montantes réseau public et privé double de 10 Gbps
*  Trois VLAN (réseaux locaux virtuels) : un VLAN public et deux VLAN privés
*  Un VXLAN (réseau local virtuel extensible) avec routeur logique distribué (DLR) pour éventuelle communication d'est en ouest entre des charges de travail locales connectées à des réseaux de la couche 2 (L2). Le VXLAN est déployé en tant qu'exemple de topologie de routage, que vous pouvez modifier, à partir duquel vous pouvez construire et que vous pouvez supprimer. Vous pouvez également ajouter des zones de sécurité en connectant des VXLAN supplémentaires aux nouvelles interfaces logiques sur le DLR.
*  Deux passerelles de services périphériques VMware NSX :
  * Une passerelle de gestion sécurisée VMware NSX Edge Services Gateway (ESG) pour le trafic de gestion HTTPS sortant, déployée par IBM dans le cadre de la topologie de réseau de gestion. Les machines virtuelles de gestion IBM utilisent cette passerelle ESG pour communiquer avec des composants de gestion IBM externes spécifiques liés à l'automatisation.

    Vous n'avez pas accès à cette passerelle ESG et vous ne pouvez pas l'utiliser. Si vous la modifiez, vous ne pourrez peut-être plus gérer l'instance Version d'essai à noeud unique pour la migration et la modernisation des applications depuis la console {{site.data.keyword.vmwaresolutions_short}}. De plus, sachez que si vous utilisez un pare-feu ou désactivez les communications ESG vers des composants de gestion IBM externes, {{site.data.keyword.vmwaresolutions_short}} sera inutilisable.
    {:important}
  * Une passerelle VMware NSX Edge Services Gateway sécurisée gérée par le client pour le trafic de charge de travail HTTPS sortant et entrant, déployée par IBM en tant que modèle que vous pouvez modifier pour fournir un accès au réseau privé virtuel ou un accès public.

### Instance de serveur virtuel
{: #cloud_modern_bundle_overview-vsi}

Les instances de serveur virtuel suivantes sont commandées :

* Une instance de serveur virtuel pour IBM CloudBuilder, annulée une fois le déploiement de l'instance terminé.
* Une instance de serveur virtuel Microsoft Windows Server pour Microsoft Active Directory (AD) est déployée et peut être interrogée. L'instance de serveur virtuel fonctionne en tant que serveur de noms de domaine pour l'instance où sont enregistrés les hôtes et les machines virtuelles.

### Licences fournies par IBM et frais
{: #cloud_modern_bundle_overview-license-and-fee}

Les licences suivantes sont incluses avec votre commande d'instance Version d'essai à noeud unique pour la migration et la modernisation des applications :

* VMware vSphere Enterprise Plus 6.7u1
* VMware vCenter Server 6.5
* VMware NSX Service Providers Advanced Edition 6.4
* {{site.data.keyword.cloud_notm}} Private Hosted 3.1.2
* {{site.data.keyword.cloud_notm}} Automation Manager 3.1.2

Les instances Version d'essai à noeud unique pour la migration et la modernisation des applications ne prennent pas en charge le mode BYOL (Bring Your Own License).
{:note}

## Spécifications techniques relatives à VMware HCX on IBM Cloud
{: #cloud_modern_bundle_overview-hcx-tech-specs}

L'instance Version d'essai à noeud unique pour la migration et la modernisation des applications comprend HCX on {{site.data.keyword.cloud_notm}}. Les composants suivants sont commandés et inclus dans le service HCX on {{site.data.keyword.cloud_notm}} :

Les instances HCX locales incluent uniquement l'octroi de licence et l'activation.
{:note}

### Paire active/passive de passerelles VMware NSX Edge Services Gateway pour HCX Management
{: #cloud_modern_bundle_overview-esg}

* UC : 6 vCPU
* Mémoire RAM : 8 Go
* Disque : VMDK 3 Go

### HCX Management Appliance - Machine virtuelle
{: #cloud_modern_bundle_overview-hcx-mgmt-appliance}

* UC : 4 vCPU
* Mémoire RAM : 12 Go
* Disque : VMDK 60 Go

Des dispositifs HCX supplémentaires sont déployés durant la configuration s'il y a lieu pour la connectivité L2, l'optimisation WAN et les connexions de passerelle.

### Spécifications de réseau pour HCX on IBM Cloud
{: #cloud_modern_bundle_overview-hcx-networking-specs}

* Un sous-réseau portable public avec 16 adresses IP
* Deux sous-réseaux portables privés avec 64 adresses IP
* Huit adresses IP issues du sous-réseau vMotion portable privé

## Spécifications techniques relatives à IBM Cloud Private Hosted
{: #cloud_modern_bundle_overview-icp-tech-specs}

{{site.data.keyword.cloud_notm}} Private Hosted 3.1.2 est installé à l'aide de la topologie Développement/Test sur toutes les instances Version d'essai à noeud unique pour la migration et la modernisation des applications. Pour plus d'informations sur {{site.data.keyword.cloud_notm}} Private Hosted, voir [Présentation de {{site.data.keyword.cloud_notm}} Private Hosted](/docs/services/vmwaresolutions/services?topic=vmware-solutions-icp_overview).

## Spécifications techniques pour IBM Cloud Automation Manager
{: #cloud_modern_bundle_overview-cam-tech-specs}

{{site.data.keyword.cloud_notm}} Automation Manager 3.1.2 est installé à l'aide de la topologie Développement/Test sur toutes les instances Version d'essai à noeud unique pour la migration et la modernisation des applications. Pour plus d'informations sur {{site.data.keyword.cloud_notm}} Automation Manager, voir [Documentation d'{{site.data.keyword.cloud_notm}} Automation Manager](https://www.ibm.com/support/knowledgecenter/en/SS2L37_3.1.2.0/kc_welcome.html){: new_window}.

## Liens connexes
{: #cloud_modern_bundle_overview-related}

* [Guide vCenter Server et {{site.data.keyword.cloud_notm}} Private](/docs/services/vmwaresolutions/archiref/vcsicp?topic=vmware-solutions-vcsicp-intro)
* [Ouvrir un ticket au sujet d'{{site.data.keyword.cloud_notm}} Private](https://www.ibm.com/mysupport/s/?language=en_US){:new_window}
* [Ressources VMware HCX](https://hcx.vmware.com/#/docs){:new_window}
* [VMware HCX User Guide](https://docs.vmware.com/en/VMware-HCX/services/user-guide/GUID-BFD7E194-CFE5-4259-B74B-991B26A51758.html){:new_window}
