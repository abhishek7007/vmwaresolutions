---

copyright:

  years:  2016, 2017

lastupdated: "2017-10-13"

subcollection: vmware-solutions


---

# Notes sur l'édition pour la version 1.9
{: #relnotes_v19}

Cette édition inclut de nouvelles fonctionnalités, des mises à jour de composant, des améliorations d'utilisation et des corrections d'erreur. Pour obtenir la liste des erreurs rectifiées dans les différentes éditions, des problèmes connus concernant le produit et des astuces relatives à l'utilisation d'{{site.data.keyword.vmwaresolutions_full}}, voir [{{site.data.keyword.vmwaresolutions_short}} dW Answers](https://developer.ibm.com/answers/topics/cloudvmw/){:new_window}.

## VMware vSphere on IBM Cloud
{: #relnotes_v19-vss}

Cette édition introduit l'offre VMware vSphere on {{site.data.keyword.cloud_notm}}. Celle-ci vous permet de construire votre propre environnement virtuel VMware hébergé par IBM en personnalisant et en commandant des ressources de calcul, de stockage et de réseau compatibles VMware sur la base des composants VMware sélectionnés. Etant donné que vSphere on {{site.data.keyword.cloud_notm}} n'automatise pas l'installation, la configuration et l'ouverture des composants VMware optionnels, vous disposez d'un maximum de souplesse pour concevoir et élaborer l'architecture d'un environnement totalement adapté à vos besoins métier. Commencez par créer un nouveau cluster vSphere de serveurs ESXi ou par mettre à l'échelle un cluster vSphere existant dans un {{site.data.keyword.CloudDataCent_notm}}.

Pour plus d'informations, voir les rubriques suivantes :
* [Commande de nouveaux clusters vSphere](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_orderinginstances)
* [Mise à l'échelle de clusters vSphere existants](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_scalingexistingclusters)

## NetApp ONTAP Select on IBM Cloud
{: #relnotes_v19-netapp}

Cette édition introduit l'offre NetApp ONTAP Select on {{site.data.keyword.cloud_notm}}, un dispositif virtuel de stockage défini par les logiciels, qui implémente NetApp ONTAP Select en tant que service sur les serveurs {{site.data.keyword.baremetal_short}} dédiés d'IBM Cloud. NetApp ONTAP Select on {{site.data.keyword.cloud_notm}} est proposé en configuration hautes performances (entièrement SSD) et en configuration haute capacité (entièrement SATA).
Cette offre héberge votre stockage sur une infrastructure dédiée et fournit des fonctionnalités NetApp, telles que la déduplication, la compression et le chiffrement des données au repos. Mettez à disposition des ressources de stockage avec souplesse et flexibilité tout en protégeant les données à l'aide de fonctions avancées de gestion des données. Par exemple, utilisez les copies NetApp Snapshot® rapides et efficaces, les copies FlexClone® et la réplication SnapMirror®.

Pour plus d'informations, voir les rubriques suivantes :
* [Présentation de NetApp ONTAP Select](/docs/services/vmwaresolutions/netapp?topic=vmware-solutions-np_netappoverview)
* [Commande d'instances NetApp ONTAP Select](/docs/services/vmwaresolutions/netapp?topic=vmware-solutions-np_orderinginstances)

## Service F5 on IBM Cloud
{: #relnotes_v19-f5}

Le service F5 BIG-IP Virtual Edition (VE) on {{site.data.keyword.cloud_notm}} est désormais disponible pour les instances VMware Cloud Foundation et VMware vCenter Server. Ce service fournit des services intelligents d'équilibrage de charge L4-L7 et de gestion du trafic à l'échelle locale et globale, une protection maximale via pare-feu des applications Web et réseau et un accès sécurisé aux applications fédérées.
Commandez des instances avec le service F5 BIG-IP Virtual Edition (VE) on {{site.data.keyword.cloud_notm}} déjà inclus ou ajoutez ultérieurement ce service à vos instances existantes à partir de l'onglet **Services** de la page des détails de propriété d'instance sur la console {{site.data.keyword.vmwaresolutions_short}}. En fonction de vos besoins, sélectionnez l'une des trois options de licence pour BIG-IP VE.

Pour plus d'informations, voir les rubriques suivantes :
* [Remarques relatives au service F5 on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-f5_considerations)
* [Gestion de F5 on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-managing_f5)

## Services gérés depuis IBM Integrated Managed Infrastructure
{: #relnotes_v19-imi}

Des services gérés depuis IBM Integrated Managed Infrastructure (IMI) sont désormais disponibles pour les instances VMware Cloud Foundation. IMI simplifie la gestion de l'infrastructure virtuelle VMware à l'aide de services modulaires et peut faire office de fournisseur digne de confiance unique afin de réduire la complexité des opérations de surveillance et de gestion des infrastructures informatiques virtuelles. Déléguez à IMI certaines des opérations quotidiennes, telles que la surveillance, de manière à vous concentrer sur des initiatives de plus grande importance.

Vous pouvez demander un rendez-vous et une estimation à tout moment à partir de la page **Initiation**.
Pour plus d'informations, voir [Demande de services gérés issus d'IMI](/docs/services/vmwaresolutions/services?topic=vmware-solutions-managing_imi#requesting-managed-services-from-imi).

## Restrictions liées aux noms des instances vCenter Server et NetApp ONTAP Select
{: #relnotes_v19-inst-name}

Les noms d'instance indiqués dans {{site.data.keyword.vmwaresolutions_short}} au moment de la commande de vos instances ne peuvent pas contenir de caractères spéciaux (par exemple, un tiret). Seuls les caractères alphanumériques sont autorisés. Cette restriction ne s'applique pas aux instances Cloud Foundation.

Pour plus d'informations, voir les rubriques suivantes :
* [Commande d'instances vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance)
* [Commande d'instances NetApp ONTAP Select](/docs/services/vmwaresolutions/netapp?topic=vmware-solutions-np_orderinginstances)

## Mises à jour des instances VMware Cloud Foundation
{: #relnotes_v19-vcf}

### Personnalisez l'UC et la mémoire de votre instance
{: #relnotes_v19-custom-cpu}

Une option de serveur personnalisé par l'utilisateur est disponible avec les options petite et Standard préconfigurées et testées. De manière à adapter au plus près le rapport UC/RAM de vos charges de travail au matériel compatible VMware, vous pouvez désormais sélectionner indépendamment le nombre total de coeurs d'un serveur à double UC et la quantité de mémoire RAM. Le stockage local n'est pas personnalisable.

## Mises à jour des instances VMware vCenter Server
{: #relnotes_v19-vcs}

### Prise en charge des clusters inter centres de données
{: #relnotes_v19-cross-dc}

Afin d'améliorer l'évolutivité de votre environnement VMware hébergé, vous pouvez désormais créer un nouveau cluster dans un autre pod d'infrastructure {{site.data.keyword.cloud_notm}} (SoftLayer), ou un autre {{site.data.keyword.CloudDataCent_notm}}, que celui du cluster initial déployé dans l'instance.

Pour plus d'informations, voir [Ajout, affichage et suppression de clusters pour des instances vCenter Server](/docs/services/vmwaresolutions?topic=vmware-solutions-vc_addingviewingclusters#vc_addingviewingclusters).

### Changement de composants
{: #relnotes_v19-change-comp}

Cette édition neutralise l'impact des opérations au sein de la console {{site.data.keyword.vmwaresolutions_short}} lorsque l'administrateur de connexion unique modifie certaines ressources vCenter Server à l'aide d'un outil VMware natif. Par exemple, vous pouvez désormais modifier les noms des centres de données virtuels VMware, des clusters, des commutateurs, des groupes de ports et des magasins de données à partir du client Web VMware vSphere pour personnaliser des déploiements en fonction de convention de dénomination de société ou personnelles, sans répercussion en aval sur les opérations depuis la console {{site.data.keyword.vmwaresolutions_short}}.

Pour plus d'informations, voir [Répercussions sur les instances vCenter Server des changements apportés à des composants](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vcenter_chg_impact).

### Tailles de mémoire RAM supplémentaires
{: #relnotes_v19-ram-sizes}

Lorsque vous commandez des instances vCenter Server ou que vous ajoutez des clusters pour des instances vCenter Server, vous avez désormais le choix entre un plus grand nombre de tailles de mémoire RAM pour vous aider à adapter le rapport UC/RAM de la charge de travail au matériel. Les options suivantes sont disponibles avec l'option de configuration **Personnalisée par l'utilisateur** lorsque vous commandez un serveur à partir de la console {{site.data.keyword.vmwaresolutions_short}} : 64 Go, 128 Go, 256 Go, 384 Go, 512 Go, 768 Go et 1,5 To.

Pour plus d'informations, voir [Commande d'instances vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance).

### Mise à jour de la version du système NFS

Le système NFS (Network File System) version 4.1 n'est plus disponible en tant que paramètre de stockage depuis l'interface utilisateur. Toutes les instances vCenter Server sont déployées avec NFS V3. Bien qu'étant une ancienne version de protocole, NFS V3 propose des fonctionnalités avancées sur les environnements VMware avec la prise en charge du contrôleur SDRS (Storage Distributed Resource Scheduler) VMware et de SIOC (Storage I/O Control).

Pour plus d'informations, voir [Commande d'instances vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance).

### Nom de domaine de serveur de noms de domaine de site unique
{: #relnotes_v19-single-site-dns}

Vous pouvez désormais fournir le nom de domaine du serveur de noms de domaine (DNS, Domain Name Server) pour une instance vCenter Server lors de la commande. Une instance de serveur virtuel Microsoft Windows Server, qui fonctionne en tant que serveur de noms de domaine pour l'instance où sont enregistrés les hôtes et les machines virtuelles, est déployée et peut être interrogée. Microsoft Active Directory (AD) est également configuré au-dessus de l'instance de serveur virtuel Microsoft Windows et le nom de domaine du serveur de noms de domaine est le nom de l’approbation de la racine AD. Cette instance de serveur virtuel Microsoft Windows n'est disponible qu'en version 1.9 et versions ultérieures.

Pour plus d'informations, voir les rubriques suivantes :
* [Présentation de vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_vcenterserveroverview)
* [Affichage des instances vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_viewinginstances)

## Exigences pour l'installation automatique des mises à jour de Windows Server
{: #relnotes_v19-win-server}

Microsoft Active Directory (AD)/Domain Name Server (DNS) est automatiquement configuré pour ne télécharger que les mises à jour. Ce module n'installe pas automatiquement ces mises à jour et n'effectue pas un redémarrage automatique. Vous devez installer les mises à jour manuellement et redémarrer le système à une heure planifiée afin d'éviter toute interruption de la configuration de serveur Active Directory en cours et d'autres tâches de sauvegarde. Pour appliquer les mises à jour Windows, installez-les manuellement.

## Documentation nouvelle et mise à jour
{: #relnotes_v19-new-docs}

* Une documentation supplémentaire est fournie pour configurer les pare-feu qui permettent toutes les communications de protocole depuis IBM CloudDriver et les machines virtuelles du gestionnaire SDDC. Pour plus d'informations, voir [Composants et remarques pour Fortinet on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-fsa_considerations).
