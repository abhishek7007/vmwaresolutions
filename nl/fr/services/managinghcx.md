---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-01"

subcollection: vmware-solutions


---

# Gestion de VMware HCX on IBM Cloud
{: #managinghcx}

## Accès aux consoles de gestion de HCX on IBM Cloud
{: #managinghcx-accessing-consoles}

Pour gérer le service HCX on {{site.data.keyword.cloud}}, vous devez accéder à la console HCX Cloud ou à la console d'administration de HCX Manager :
1. Utilisez le réseau privé virtuel de l'infrastructure {{site.data.keyword.cloud_notm}} ou un serveur intermédiaire pour autoriser l'accès à l'adresse IP du dispositif virtuel HCX Manager. Vous trouverez l'adresse IP sur la page des détails du service HCX on {{site.data.keyword.cloud_notm}} sur la console {{site.data.keyword.vmwaresolutions_short}}.
2. Pour accéder à la console HCX Cloud, cliquez sur **Afficher la console HCX Cloud** sur la page des détails du service HCX on {{site.data.keyword.cloud_notm}}, puis connectez-vous à l'aide des données d'identification vCenter Server.
3. Pour accéder à la console d'administration de HCX Manager, cliquez sur **Afficher la console d'administration de HCX Manager** sur la page des détails du service HCX on {{site.data.keyword.cloud_notm}}, puis connectez-vous à l'aide des données d'identification de HCX Manager indiquées sur cette même page des détails du service.

Pour plus d'informations, voir [Commande, affichage et retrait de services pour des instances vCenter Server with Hybridity Bundle](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_addingremovingservices).

## Application de mises à jour à HCX on IBM Cloud
{: #managinghcx-updates}

HCX on {{site.data.keyword.cloud_notm}} est déployé avec la dernière génération testée de la technologie VMware Hybrid Cloud Extension. VMware expédie régulièrement des mises à jour pour ces générations, avec des correctifs importants et de nouvelles fonctions. Ces générations sont automatiquement envoyées par commande push vers des installations HCX on {{site.data.keyword.cloud}}, y compris vers des installations HCX locales.

Pour appliquer des correctifs de maintenance envoyés par commande push vers votre environnement, vous devez utiliser la console HCX Manager Admin dans votre centre de données local et votre instance vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle.

Si vous ne voyez pas une mise à jour de génération que vous avez attendez, si vous rencontrez des difficultés avec HCX ou si vous souhaitez que la dernière génération de HCX soit immédiatement envoyée par commande push vers votre système, ouvrez un ticket de demande de service en suivant les étapes décrites dans [Contacter le support IBM](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support).

## Liens connexes
{: #managinghcx-related}

* [Présentation de HCX on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions?topic=vmware-solutions-hcx_considerations#hcx_considerations)
* [Glossaire des termes HCX](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcx_glossary)
* [Présentation de VMware Hybrid Cloud Extension](https://cloud.vmware.com/vmware-hcx)
* [Documentation VMware Hybrid Cloud Extension](https://cloud.vmware.com/vmware-hcx/resources)
