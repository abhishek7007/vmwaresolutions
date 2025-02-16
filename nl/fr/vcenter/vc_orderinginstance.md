---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-25"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Commande d'instances vCenter Server
{: #vc_orderinginstance}

Afin de déployer une plateforme virtuelle VMware personnalisable et flexible totalement adaptée à vos besoins en charge de travail, commandez une instance vCenter Server VMware. Lors de la commande initiale, vous pouvez également ajouter des services, tels que [Zerto on {{site.data.keyword.cloud}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-addingzertodr) pour la reprise après incident.

## Conditions requises
{: #vc_orderinginstance-req}

Assurez-vous que :
* Vous avez configuré les données d'identification de l'infrastructure {{site.data.keyword.cloud_notm}} sur la page **Paramètres**. Pour plus d'informations, voir [Gestion des paramètres et comptes utilisateur](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-useraccount).
* Vous avez passé en revue les informations décrites dans la rubrique [Exigences et planification pour les instances vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_planning).
* Vous avez passé en revue le format des noms d'instance et de domaine. Le nom de domaine et le libellé de sous-domaine sont utilisés pour générer le nom d'utilisateur et les noms de serveur de l'instance.

Tableau 1. Format de la valeur des noms d'instance et de domaine

| Nom        | Format de la valeur      |
  |:------------|:------------ |
  | Nom de domaine | `<root_domain>` |  
  | Nom d'utilisateur de connexion vCenter Server | `<user_id>@<root_domain>` (utilisateur Microsoft Active Directory) ou `administrator@vsphere.local` |
  | vCenter Server (avec PSC intégré) FQDN | `vcenter-<subdomain_label>.<subdomain_label>.<root_domain>`. La longueur maximale est de 50 caractères. |
  | Nom du site de connexion unique | `<subdomain_label>` |
  | Nom de serveur ESXi qualifié complet | `<host_prefix><n>.<subdomain_label>.<root_domain>`, où `<n>` est la séquence du serveur ESXi. La longueur maximale admise est de 50 caractères. |

Ne modifiez aucune des valeurs définies lors de la commande ou du déploiement de l'instance. Cela rendrait votre instance inutilisable. Par exemple, si le réseau public s'arrête, si les serveurs et les instances de serveur virtuel passent derrière un mi-parcours Vyatta ou si l'instance de serveur virtuel IBM CloudBuilder s'arrête ou est supprimée.
{:important}

## Paramètres système
{: #vc_orderinginstance-sys-settings}

Vous devez spécifier les paramètres système répertoriés ci-après lorsque vous commandez une instance vCenter Server.

### Nom d'instance
{: #vc_orderinginstance-inst-name}

Le nom de l'instance qui doit respecter les règles suivantes :
* Seuls les caractères alphanumériques et le tiret (-) sont autorisés.
* Le nom d'instance doit commencer par un caractère alphabétique et se terminer par un caractère alphanumérique.
* Le nom d'instance ne doit pas dépasser 10 caractères.
* Le nom d'instance doit être unique au sein de votre compte.

### Licences VMware vSphere
{: #vc_orderinginstance-vsphere-license}

Indiquez si vous souhaitez commander vSphere Enterprise Plus 6.7u1 ou vSphere Enterprise Plus 6.5u2.

vSphere Enterprise Plus 6.7u1 est disponible uniquement pour les serveurs {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} Broadwell et Skylake.
{:note}

### Principale ou secondaire
{: #vc_orderinginstance-primary-secondary}

Indiquez si vous souhaitez commander une nouvelle instance principale ou une instance secondaire pour une instance principale existante.

## Paramètres d'octroi de licence
{: #vc_orderinginstance-licensing-settings}

Spécifiez les options d'octroi de licence pour les composants VMware suivants dans l'instance :
* vCenter Server 6.5
* vSphere Enterprise Plus 6.5 ou 6.7
* NSX Service Providers 6.4 (édition Base, Advanced ou Enterprise)

Si vous êtes un partenaire commercial, la licence vCenter Server (édition Standard), la licence vSphere (édition Enterprise Plus) et la licence NSX sont incluses et achetées en votre nom. Vous devez néanmoins spécifier l'édition pour la licence NSX.

Si vous n'êtes pas un partenaire commercial, vous pouvez utiliser les licences VMware fournies par IBM pour ces composants en sélectionnant **Inclure avec achat** ou vous pouvez fournir votre propre licence (mode BYOL) en sélectionnant **Je fournirai** et en entrant vos propres clés de licence.

### Notes de licence
{: #vc_orderinginstance-licensing-notes}

* Une licence avec un minimum de huit UC est requise, ce qui vaut pour quatre serveurs avec deux UC par serveur. Le choix de licence pour chaque composant VMware s'applique à l'instance de base et à tous les serveurs ESXi ajoutés ultérieurement à l'instance. Veillez à ce que votre licence soit à même de prendre en charge une future extension de capacité de votre infrastructure.
* Les éditions de licence minimum sont indiquées sur l'interface utilisateur. Si différentes éditions de composant sont prises en charge, vous pouvez sélectionner celle qui vous convient. Il est de votre responsabilité de vous assurer que la clé de licence fournie est correcte pour chaque composant VMware sélectionné.
* Pour vSphere, des frais de licence sont imputés au moment de la commande, mais ces frais sont ensuite crédités à votre compte.
* Vous pouvez modifier toute licence que vous avez fournie à l'aide du client Web VMware vSphere une fois le déploiement de l'instance terminé.
* La prise en charge des composants VMware pour lesquels vous avez fourni des licences est assurée par VMware et non par le support IBM.

## Paramètres de serveur bare metal
{: #vc_orderinginstance-bare-metal-settings}

Les paramètres bare metal dépendent du centre de données que vous sélectionnez et de la configuration de serveur bare metal.

### Emplacement de centre de données
{: #vc_orderinginstance-dc-location}

Sélectionnez l'{{site.data.keyword.CloudDataCent_notm}} où l'instance doit être hébergée.

### Skylake
{: #vc_orderinginstance-skylake}

Lorsque vous sélectionnez **Skylake**, vous pouvez choisir la combinaison de modèle d'UC et de mémoire RAM de serveur bare metal adaptée à vos besoins.

Tableau 2. Options pour les serveurs Skylake {{site.data.keyword.baremetal_short}}

| Options de modèle d'UC        | Options de RAM       |
|:------------- |:------------- |
| Processeur Dual Intel Xeon Silver 4110/16 coeurs au total, 2,1 GHz | 64 Go, 96 Go, 128 Go, 192 Go, 384 Go, 768 Go, 1,5 To |
| Processeur Dual Intel Xeon Gold 5120/28 coeurs au total, 2,2 GHz | 64 Go, 96 Go, 128 Go, 192 Go, 384 Go, 768 Go, 1,5 To |
| Processeur Dual Intel Xeon Gold 6140/36 coeurs au total, 2,3 GHz | 64 Go, 96 Go, 128 Go, 192 Go, 384 Go, 768 Go, 1,5 To |

### Certifiés SAP
{: #vc_orderinginstance-sap}

Lorsque vous sélectionnez **Certifiés SAP**, vous ne pouvez pas modifier les paramètres d'UC ou de mémoire RAM.

En fonction de vos besoins, sélectionnez une configuration de serveur bare metal :
  * Processeur Dual Intel Xeon Gold 6140/36 coeurs au total, 2,3 GHz/192 Go de mémoire RAM
  * Processeur Dual Intel Xeon Gold 6140/36 coeurs au total, 2,3 GHz/384 Go de mémoire RAM
  * Processeur Dual Intel Xeon Gold 6140/36 coeurs au total, 2,3 GHz/768 Go de mémoire RAM
  * Processeur Dual Intel Xeon E5-2690 v4/28 coeurs au total, 2,6 GHz/512 Go de mémoire RAM
  * Processeur Quad Intel Xeon E7-8890 v4/96 coeurs au total, 2,2 GHz/1024 Go de mémoire RAM
  * Processeur Quad Intel Xeon E7-8890 v4/96 coeurs au total, 2,2 GHz/2048 Go de mémoire RAM
  * Processeur Quad Intel Xeon E7-8890 v4/96 coeurs au total, 2,2 GHz/4096 Go de mémoire RAM

### Broadwell
{: #vc_orderinginstance-broadwell}

Lorsque vous sélectionnez **Broadwell**, vous pouvez choisir la combinaison de modèle d'UC et de mémoire RAM de serveur bare metal adaptée à vos besoins.

Tableau 3. Options pour les serveurs Broadwell {{site.data.keyword.baremetal_short}}

| Options de modèle d'UC        | Options de RAM       |
|:------------- |:------------- |
| Quad Intel Xeon E7-4820 v4/40 coeurs au total, 2,0 GHz | 128 Go, 256 Go, 512 Go, 1 To, 2 To, 3 To |
| Quad Intel Xeon E7-4850 v4/64 coeurs au total, 2,1 GHz | 128 Go, 256 Go, 512 Go, 1 To, 2 To, 3 To |

### Nombre de serveurs bare metal
{: #vc_orderinginstance-bare-metal-number}

* Tous les serveurs que vous commandez ont la même configuration.
* Si vous prévoyez d'utiliser le stockage vSAN, vous pouvez commander entre 4 et 20 serveurs.
* Si vous prévoyez d'utiliser le stockage NFS, vous pouvez commander entre 2 et 20 serveurs. Cependant, pour les charges de travail de production, un minimum de 3 serveurs est recommandé. Pour plus d'informations, voir [Une instance vCenter Server à deux noeuds est-elle à haute disponibilité ?](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-faq#is-a-two-node-vcenter-server-instance-highly-available-).

## Paramètres de stockage
{: #vc_orderinginstance-storage-settings}

Les paramètres de stockage varient en fonction de la configuration de serveur bare metal et du type de stockage que vous sélectionnez.

Pour les instances en version 2.8 et versions ultérieure, vous pouvez ajouter des partages de stockage NFS à un cluster NFS ou vSAN existant. Pour plus d'informations, voir la section *Ajout de stockage NFS à des instances vCenter Server* dans [Extension et réduction de capacité pour des instances vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_addingremovingservers#adding-nfs-storage-to-vcenter-server-instances).
{:note}

### Stockage vSAN
{: #vc_orderinginstance-vsan-storage}

vSAN n'est disponible que pour les configurations bare metal **Skylake** et **Broadwell**. Spécifiez les options vSAN suivantes :
* **Type et taille de disque pour disques de capacité vSAN** : sélectionnez une option correspond aux disques de capacité dont vous avez besoin.
* **Nombre de disques de capacité vSAN** : indiquez le nombre de disques de capacité que vous souhaitez ajouter.
* Si vous souhaitez augmenter la capacité au-delà de la limite de 10 disques, cochez la case **Hautes performances avec Intel Optane**. Cette option fournit deux baies de disques de capacité supplémentaires pour un total de 12 disques de capacité. Elle s'avère utile pour les charges de travail qui nécessitent un temps d'attente plus court et une capacité de traitement d'IOPS plus élevée.

  L'option **Hautes performances avec Intel Optane** n'est disponible que pour les modèles d'unités centrales Skylake.
  {:note}

* Passez en revue les valeurs de **type de disque pour les disques de cache vSAN** et de **nombre de disques de cache vSAN**. Ces valeurs dépendent de la sélection de la case **Hautes performances avec Intel Optane**.
* **Licence vSAN** : utilisez la licence VMware fournie par IBM pour le composant vSAN en sélectionnant **Inclure avec achat** ou fournissez votre propre licence (mode BYOL) en sélectionnant **Je fournirai** et en entrant votre propre clé de licence

### Stockage NFS
{: #vc_orderinginstance-nfs-storage}

Lorsque vous sélectionnez **Stockage NFS**, vous pouvez ajouter un stockage partagé de niveau fichier pour votre instance dans lequel tous les partages utilisent les mêmes paramètres ou vous pouvez spécifier des paramètres de configuration différents pour chaque partage de fichiers. Spécifiez les options NFS suivantes :

Le nombre de partages de fichiers doit être compris entre 1 et 32.
{:note}

* **Configurer les partages individuellement** : permet de spécifier des paramètres de configuration différents pour chaque partage de fichiers.
* **Nombre de partages** : lorsque vous utilisez le même paramètre de configuration pour chaque partage de fichiers, spécifiez le nombre de partages de fichiers pour le stockage partagé NFS que vous souhaitez ajouter.
* **Performances** : sélectionnez la valeur IOPS (opérations d'entrée/sortie par seconde) par Go adaptée à vos besoins en matière de charge de travail.
* **Taille (Go)** : permet de sélectionner la capacité qui répond à vos besoins en matière de stockage partagé.
* **Ajout de stockage partagé** : permet d'ajouter des partages de fichiers individuels qui utilisent des paramètres de configuration différents.

Tableau 4. Options de niveau de performance NFS

| Option        | Détails       |
  |:------------- |:------------- |
  | 0,25 IOPS/Go | Cette option est conçue pour les charges de travail qui ne sont pas souvent utilisées. Exemples d'applications : données de coffre, hébergement de bases de données de grande taille avec des données existantes ou images de disque virtuel de système de mémoire virtuelle en tant que sauvegarde. |
  | 2 IOPS/Go | Cette option est adaptée à la plupart des charges de travail d'usage général. Entre autres exemples d'application, citons l'hébergement de petites bases de données, la sauvegarde d'applications Web ou les images de disque de machine virtuelle pour un hyperviseur. |
  | 4 IOPS/Go | Cette option est adaptée aux charges de travail de grande intensité qui ont un pourcentage élevé de données actives simultanément. Les bases de données transactionnelles en sont un exemple. |
  | 10 IOPS/Go | Cette option est adaptée aux types de charge de travail les plus exigeants, tels que les analyses. Les bases de données à transactions élevées et autres bases de données sensibles aux performances en sont des exemples. Ce niveau de performance est limité à une capacité maximale de 4 To par partage de fichiers. |

### Disques locaux
{: #vc_orderinginstance-local-disks}

L'option Disques locaux est disponible uniquement pour la configuration de processeur Quad Intel Xeon E7-8890 v4 Bare Metal **certifié SAP**. Indiquez les options suivantes :
* **Nombre de disques **: sélectionnez le nombre de disques que vous voulez ajouter.
* **Type de disque **: sélectionnez une option pour le type de disque dont vous avez besoin.

## Paramètres d'interface réseau
{: #vc_orderinginstance-network-interface-settings}

Vous devez spécifier les paramètres d'interface réseau répertoriés ci-après lorsque vous commandez une instance vCenter Server.

### Préfixe de nom d'hôte
{: #vc_orderinginstance-host-name-prefix}

Le préfixe du nom d'hôte qui doit respecter les règles suivantes :
*  Seuls les caractères alphanumériques et le tiret (-) sont autorisés.
*  Le préfixe de nom d'hôte doit commencer et se terminer par un caractère alphanumérique.
*  Le préfixe de nom d'hôte ne doit pas dépasser 10 caractères.

### Libellé de sous-domaine
{: #vc_orderinginstance-subdomain-label}

Le libellé du sous-domaine qui doit respecter les règles suivantes :
*  Seuls les caractères alphanumériques et le tiret (-) sont autorisés.
*  Le libellé de sous-domaine doit commencer par un caractère alphabétique et se terminer par un caractère alphanumérique.
*  Le libellé de sous-domaine ne doit pas dépasser 10 caractères.
*  Le libellé de sous-domaine doit être unique au sein de votre compte.

### Nom de domaine
{: #vc_orderinginstance-domain-name}

Le nom du domaine racine qui doit respecter les règles suivantes :
* Le nom de domaine doit être composé d'au moins deux chaînes séparées par un point (.)
* La première chaîne doit commencer par un caractère alphabétique et se terminer par un caractère alphanumérique.
* Toutes les chaînes, à l'exception de la dernière, ne peuvent contenir que des caractères alphanumériques et des tirets (-).
* La dernière chaîne ne peut contenir que des caractères alphabétiques.
* La dernière chaîne doit comporter entre 2 et 24 caractères.

La longueur maximale du nom de domaine complet des hôtes et des machines virtuelles est de 50 caractères. Les noms de domaine doivent respecter cette longueur maximale.
{:note}

### Réseau public ou privé
{: #vc_orderinginstance-public-private-network}

Les paramètres d'activation de carte d'interface réseau varient selon que vous sélectionnez **Réseau public et réseau privé** ou **Réseau privé uniquement**.

Si vous sélectionnez l'option **Réseau privé uniquement** :
* Les passerelles ESG VMware NSX ne sont pas mises à disposition (ni la passerelle ESG des services de gestion ni la passerelle ESG gérée par le client).
* Les services complémentaires suivants, qui nécessitent des cartes d'interface réseau publiques, ne sont pas disponibles :
  * F5 on {{site.data.keyword.cloud_notm}}
  * Fortigate Security Appliance on {{site.data.keyword.cloud_notm}}
  * Fortigate Virtual Appliance on {{site.data.keyword.cloud_notm}}

### Réseaux locaux virtuels
{: #vc_orderinginstance-vlans}

Les paramètres de réseau varient selon que vous sélectionnez **Commander de nouveaux VLAN** ou **Sélectionner des VLAN existants**.

Un VLAN public et deux VLAN privés sont nécessaires pour votre commande d'instance. Les deux VLAN privés sont liés respectivement à chaque serveur bare metal.

#### Commander de nouveaux VLAN
{: #vc_orderinginstance-new-vlans}

Sélectionnez cette option pour commander un nouveau VLAN public et deux nouveaux VLAN privés.

#### Sélectionner des VLAN existants
{: #vc_orderinginstance-existing-vlans}

En fonction de l'{{site.data.keyword.CloudDataCent_notm}} que vous avez sélectionné, des VLAN publics et privés existants peuvent être disponibles.

Lorsque vous sélectionnez cette option pour réutiliser des VLAN publics et privés existants, spécifiez les VLAN et les sous-réseaux :
* **VLAN public**, pour l'accès au réseau public.
* **VLAN privé**, pour la connectivité entre les centres de données et les services dans {{site.data.keyword.cloud_notm}}.
* **VLAN privé secondaire**, pour les dispositifs VMware, tels que vSAN.
* **Sous-réseau principal**, affecté aux hôtes physiques pour l'accès au réseau public.
* **Sous-réseau privé principal**, affecté aux hôtes physiques pour le trafic de gestion.

Vérifiez que la configuration de pare-feu sur les VLAN sélectionnés ne bloque pas le trafic des données de gestion. Vérifiez également que tous les VLAN sélectionnés se trouvent dans le même pod. Les serveurs ESXi ne peuvent pas être mis à disposition sur des VLAN multi-pods.
{:important}

### Configuration DNS
{: #vc_orderinginstance-dns-config}

Sélectionnez la configuration de système de noms de domaine (DNS, Domain Name System) de votre instance :

* **Une instance de serveur virtuel Windows publique pour Active Directory/DNS** : une unique instance de serveur virtuel Windows Microsoft pour Microsoft Active Directory (AD), qui fonctionne en tant que serveur de noms de domaine pour l'instance où sont enregistrés les hôtes et les machines virtuelles, est déployée et peut être interrogée. Cette option a été déployée par défaut pour les instances de version 1.9 et ultérieures.
* **Deux machines virtuelles Windows Server dédiées à haute disponibilité sur le cluster de gestion** : deux machines virtuelles Microsoft Windows sont déployées, pour plus de sécurité et de robustesse.

Vous devez fournir deux licences Microsoft Windows Server 2016 si vous configurez votre instance de manière à utiliser les deux machines virtuelles Microsoft Windows. Utilisez la licence d'édition Microsoft Windows Server 2016 Standard et/ou la licence d'édition Microsoft Windows Server 2016 Datacenter.
{:important}

Chaque licence ne peut être affectée qu'à un seul serveur physique et couvre jusqu'à deux processeurs physiques. Une licence d'édition Standard peut exécuter deux machines virtuelles Microsoft Windows virtualisées par serveur à 2 processeurs. Par conséquent, deux licences sont nécessaires puisque deux machines virtuelles Microsoft Windows sont déployées sur deux hôtes différents.

Vous disposez de 30 jours pour activer les machines virtuelles.

Pour en savoir plus sur la commande des licences Windows Server 2016, voir [Prise en main de Windows Server 2016](https://docs.microsoft.com/en-us/windows-server/get-started/server-basics){:new_window}.

## Paramètres de services
{: #vc_orderinginstance-addon-services}

Lorsque vous commandez une instance vCenter Server, vous pouvez également commander des services complémentaires. Pour plus d'informations sur les services, voir [Services disponibles pour les instances vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_addingremovingservices#available-services-for-vcenter-server-instances).

## Récapitulatif de la commande
{: #vc_orderinginstance-order-summary}

Selon la configuration que vous avez sélectionnée pour l'instance et les services complémentaires, le coût estimé est généré et affiché instantanément dans la section **Récapitulatif de la commande** sur le panneau de droite. Cliquez sur **Détails concernant la tarification** en bas à droite du panneau pour générer un document PDF contenant les détails relatifs à l'estimation.

## Procédure de commande d'instances vCenter Server
{: #vc_orderinginstance-procedure}

1. Dans le catalogue {{site.data.keyword.cloud_notm}}, cliquez sur **VMware** dans le panneau de navigation de gauche, puis cliquez sur **vCenter Server** dans la section **Centres de données virtuels**.
2. Sur la page **VMware vCenter Server on IBM Cloud**, cliquez sur la carte **vCenter Server**, puis sur **Créer**.
3. Sur la page **vCenter Server**, entrez le nom de l'instance.
5. Sélectionnez la version vSphere.
4. Sélectionnez le type d'instance :
   * Cliquez sur **Instance principale** pour déployer une seule instance dans l'environnement ou pour déployer la première instance dans une topologie multisite.
   * Cliquez sur **Instance secondaire** pour connecter l'instance à une instance (principale) existante dans l'environnement à des fins de haute disponibilité et procédez comme suit :
     1. Sélectionnez l'instance principale à laquelle vous voulez que l'instance secondaire soit connectée.
     2. Pour les instances principales V2.8 ou ultérieures, entrez le mot de passe administrateur vCenter Server pour l'instance principale.
     3. Pour les instances principales V2.5, 2.6 ou 2.7, entrez le mot de passe administrateur PSC pour l'instance principale.
     4. Pour les instances principales V2.4 ou antérieures, assurez-vous que la valeur préremplie pour le mot de passe administrateur PSC pour l'instance principale est correcte.
6. Spécifiez les paramètres de licence pour les composants d'instance.
   *  Pour utiliser des licences fournies par IBM, sélectionnez **Inclure avec achat** et sélectionnez l'édition de licence, le cas échéant.
   *  Pour utiliser votre propre licence, sélectionnez **Je fournirai** et entrez la clé de licence.
7. Spécifiez les paramètres de serveur bare metal.
    1. Sélectionnez l'{{site.data.keyword.CloudDataCent_notm}} qui doit héberger l'instance.
    2. Sélectionnez la configuration de serveur bare metal.
       * Lorsque vous sélectionnez **Skylake** ou **Broadwell**, spécifiez le modèle d'UC et la taille de mémoire RAM.
       * Lorsque vous sélectionnez **Certifiés SAP**, choisissez l'une des configurations prédéfinies.
    3. Spécifiez le nombre de serveurs {{site.data.keyword.baremetal_short}}. Si vous prévoyez d'utiliser le stockage vSAN, un minimum de quatre serveurs {{site.data.keyword.baremetal_short}} est requis.  
8. Procédez à la configuration du stockage.
  * Si vous sélectionnez **Stockage vSAN**, spécifiez les types de disque pour les disques de cache et de capacité, le nombre de disques et l'édition de licence vSAN. Si vous souhaitez obtenir davantage de stockage, cochez la zone **Hautes performances avec Intel Optane**.
  * Si vous sélectionnez **Stockage NFS** et que vous souhaitez ajouter et configurer les mêmes paramètres pour tous les partages de fichiers, renseignez les zones **Nombre de partages**, **Performances** et **Taille (Go)**.
  * Si vous sélectionnez **Stockage NFS** et que vous souhaitez ajouter et configurer des partages de fichiers individuellement, sélectionnez **Configurer les partages individuellement**. Ensuite, cliquez sur l'icône **+** en regard du libellé **Ajout de stockage partagé** et sélectionnez une valeur pour les zones **Performances** et **Taille (Go)** pour chaque partage de fichiers. Vous devez sélectionner au moins un partage de fichiers.
  * Si vous sélectionnez **Disques locaux**, indiquez le nombre et le type de disque.
9. Spécifiez les paramètres d'interface réseau.
   1. Entrez le préfixe du nom d'hôte de l'instance mise à disposition, le libellé de sous-domaine et le nom du domaine racine. Pour une instance secondaire, le nom de domaine est automatiquement renseigné.
   2. Sélectionnez le paramètre réseau **Réseau public et réseau privé** ou **réseau privé uniquement**.
   3. Sélectionnez les paramètres VLAN :
      * Si vous voulez commander de nouveaux VLAN publics et privés, cliquez sur **Commander de nouveaux VLAN**.
      * Si vous voulez réutiliser les VLAN publics et privés existants lorsqu'ils sont disponibles, cliquez sur **Sélectionner des VLAN existants** et spécifiez les VLAN et les sous-réseaux.
   4. Spécifiez la configuration DNS.

10. Sélectionnez les services complémentaires à déployer dans l'instance en cliquant sur la carte de service correspondante. Si un service nécessite de la configuration, spécifiez les paramètres qui lui sont propres et cliquez sur **Ajouter un service** sur la carte.
Pour savoir comment indiquer les paramètres d'un service, voir la rubrique de commande de service correspondante.

11. Sur la page **Récapitulatif de la commande**, vérifiez la configuration de l'instance avant de passer la commande.
   1. Passez en revue les paramètres de l'instance.
   2. Passez en revue le coût estimé de l'instance. Cliquez sur **Détails concernant la tarification** pour générer un récapitulatif au format PDF. Pour sauvegarder ou imprimer votre récapitulatif de commande, cliquez sur l'icône d'**impression** ou de **téléchargement** dans l'angle supérieur droit de la fenêtre du PDF.
   3. Cliquez sur le ou les liens des conditions applicables à votre commande et prenez soin d'accepter ces conditions avant de commander l'instance.
   4. Cliquez sur **Mettre à disposition**.

## Que se passe-t-il après la commande d'instances vCenter Server ?
{: #vc_orderinginstance-results}

Le déploiement de l'instance commence automatiquement. Vous recevez une confirmation que la commande est en cours de traitement et vous pouvez vérifier l'état du déploiement en affichant les détails de l'instance.

Une fois l'instance correctement déployée, les composants décrits dans [Spécifications techniques relatives aux instances vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_vcenterserveroverview#specs) sont installés sur votre plateforme virtuelle VMware. Les serveurs ESXi que vous avez commandés sont, par défaut, regroupés en **cluster1**. Si vous avez commandé des services complémentaires, le déploiement des services commence une fois votre commande honorée.

Lorsque l'instance est prête pour utilisation, elle prend le statut **Prêt à l'emploi** et vous recevez une notification par courrier électronique.

Lorsque vous commandez une instance secondaire, le client Web VMware vSphere de l'instance principale (liée à l'instance secondaire) devra peut-être être redémarré une fois la commande d'instance secondaire honorée.

## Etape suivante
{: #vc_orderinginstance-next}

Affichez et gérez l'instance vCenter Server que vous avez commandée.

Vous devez gérer les composants {{site.data.keyword.vmwaresolutions_short}} créés dans votre compte {{site.data.keyword.cloud_notm}} uniquement depuis la console {{site.data.keyword.vmwaresolutions_short}}, et non depuis le portail	{{site.data.keyword.slportal}} ou tout autre élément extérieur à la console.
Si vous modifiez ces composants en dehors de la console {{site.data.keyword.vmwaresolutions_short}}, les modifications ne sont pas synchronisées avec la console.
{:important}

**ATTENTION :** gérer des composants {{site.data.keyword.vmwaresolutions_short}} (installés dans votre compte {{site.data.keyword.cloud_notm}} lorsque vous avez commandé l'instance) en dehors de la console {{site.data.keyword.vmwaresolutions_short}} risque de rendre votre environnement instable. Ces activités de gestion incluent :
*  L'ajout, la modification, le retour ou la suppression de composants
*  L'extension ou la réduction de la capacité de l'instance via l'ajout ou la suppression de serveurs ESXi
*  La mise hors tension de composants
*  Le redémarrage de services

   Seules les activités de gestion des partages de fichiers du stockage partagé depuis le portail {{site.data.keyword.slportal}} font exception. Il s'agit des activités suivantes : commande, suppression (pouvant avoir un impact sur des magasins de données éventuellement montés), accord d'autorisation et montage de partages de fichiers de stockage partagé.

## Liens connexes
{: #vc_orderinginstance-related}

* [Inscription à un compte {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-signing_softlayer_account)
* [Affichage des instances vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_viewinginstances)
* [Configuration multisite pour des instances vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_multisite)
* [Ajout, affichage et suppression de clusters pour des instances vCenter Server](/docs/services/vmwaresolutions?topic=vmware-solutions-vc_addingviewingclusters#vc_addingviewingclusters)
* [Extension et réduction de capacité pour des instances vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_addingremovingservers)
* [Commande, affichage et retrait de services pour des instances vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_addingremovingservices)
* [Suppression d'instances vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_deletinginstance)
