---

copyright:

  years:  2016, 2019

lastupdated: "2019-03-12"

---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Commande et suppression d'instances Version d'essai à noeud unique pour VMware vCenter Server on IBM Cloud
{: #vc_trial_hybrid_orderinginstance}

La version d'essai à noeud unique pour VMware vCenter Server on {{site.data.keyword.cloud}} est un cloud privé hébergé à service exclusif qui fournit la pile VMware vSphere en tant que service. Alors que l'environnement géré par le client est généralement déployé avec trois noeuds au minimum, cette version d'essai à noeud unique permet d'expérimenter à moindres frais les avantages d'une implémentation de cloud hybride.

Cette version d'essai démontre parfaitement la faisabilité d'une solution impliquant la vitesse de l'automatisation avancée d'IBM pour le déploiement initial et la facilité de déplacement de plusieurs charges de travail simples hors production vers le cloud. Grâce à VMware Hybrid Cloud Extension (HCX), vous pouvez étendre en toute sécurité votre réseau de centre de données sur site à l'{{site.data.keyword.CloudDataCent_notm}}, tout en réduisant de façon significative la complexité réseau de la configuration de l'interconnexion. HCX extrait les ressources réseau sous-jacentes pour les placer sur l'Internet public afin que vous puissiez déplacer en toute transparence des charges de travail de façon bidirectionnelle sans avoir à redéfinir les adresses IP des machines virtuelles. Grâce à HCX, il n'est pas nécessaire que VMware NSX soit installé sur site. En outre, il est compatible en amont avec les versions précédentes de vSphere.  

Cette version d'essai à noeud unique est destinée à une démonstration de faisabilité uniquement. N'exécutez pas de charges de travail de production dans cet environnement. Les fonctions de gestions, telles que l'ajout et le retrait d'hôtes et de clusters, la commande de services complémentaires supplémentaires et l'application de mises à jour ne sont pas prises en charge.
{:important}

Cette version d'essai peut être utilisée pendant 90 jours au maximum. Une fois qu'elle a expiré, vous pouvez supprimer cet environnement, puis mettre à disposition un environnement hautement disponible répondant à vos besoins en matière de capacité.

Pour plus d'informations sur la conception d'architecture, voir [Conception d'architecture HCX on IBM Cloud pour la version d'essai à noeud unique vCenter Server on IBM Cloud](/docs/services/vmwaresolutions/archiref/trial/vc_trial_hcx_arch.html).

## Spécifications techniques relatives aux instances Version d'essai à noeud unique pour vCenter Server
{: #vc_trial_hybrid_orderinginstance-specs}

Les composants suivants sont inclus dans votre instance Version d'essai à noeud unique pour vCenter Server :

La disponibilité et la tarification des configurations matérielles normalisées peuvent varier en fonction de l'{{site.data.keyword.CloudDataCent_notm}} sélectionné pour le déploiement.
{:note}

### Serveur bare metal
{: #vc_trial_hybrid_orderinginstance-bare-metal}

Un processeur Dual Intel Xeon Gold 5120 (28 coeurs, 2,20 GHz) avec 384 Go de mémoire RAM.

### Spécifications relatives à la mise en réseau pour les instances Version d'essai à noeud unique pour vCenter Server
{: #vc_trial_hybrid_orderinginstance-networking-specs}

Les composants réseau suivants sont commandés :
*  Liaisons montantes réseau public et privé double de 10 Gbps
*  Trois VLAN (réseaux locaux virtuels) : un VLAN public et deux VLAN privés
*  Un VXLAN (réseau local virtuel extensible) avec routeur logique distribué (DLR) pour éventuelle communication d'est en ouest entre des charges de travail locales connectées à des réseaux de la couche 2 (L2). Le VXLAN est déployé en tant qu'exemple de topologie de routage, que vous pouvez modifier, à partir duquel vous pouvez construire et que vous pouvez supprimer. Vous pouvez également ajouter des zones de sécurité en connectant d'autres VXLAN aux nouvelles interfaces logiques sur le DLR.
*  Deux passerelles de services périphériques VMware NSX :
  * Une passerelle de gestion sécurisée VMware NSX Edge Services Gateway (ESG) pour le trafic de gestion HTTPS sortant, déployée par IBM dans le cadre de la topologie de réseau de gestion. Les machines virtuelles de gestion IBM utilisent cette passerelle ESG pour communiquer avec des composants de gestion IBM externes spécifiques liés à l'automatisation.

    Vous n'avez pas accès à cette passerelle ESG et vous ne pouvez pas l'utiliser. Si vous la modifiez, vous ne pourrez peut-être plus gérer l'instance Version d'essai à noeud unique pour vCenter Server depuis la console {{site.data.keyword.vmwaresolutions_short}}. De plus, sachez que si vous utilisez un pare-feu ou désactivez les communications ESG vers des composants de gestion IBM externes, {{site.data.keyword.vmwaresolutions_short}} sera inutilisable.
    {:important}
  * Une passerelle VMware NSX Edge Services Gateway sécurisée gérée par le client pour le trafic de charge de travail HTTPS sortant et entrant, déployée par IBM en tant que modèle que vous pouvez modifier pour fournir un accès au réseau privé virtuel ou un accès public.

### Instance de serveur virtuel
{: #vc_trial_hybrid_orderinginstance-vsi}

Les instances de serveur virtuel suivantes sont commandées :
* Une instance de serveur virtuel pour IBM CloudBuilder, annulée une fois le déploiement de l'instance terminé.
* Une instance de serveur virtuel Microsoft Windows Server pour Microsoft Active Directory (AD) est déployée et peut être interrogée. L'instance de serveur virtuel fonctionne en tant que serveur de noms de domaine pour l'instance où sont enregistrés les hôtes et les machines virtuelles.

### Licences fournies par IBM et frais
{: #vc_trial_hybrid_orderinginstance-license-and-fee}

Les licences suivantes sont incluses avec votre commande d'instance Version d'essai à noeud unique pour vCenter Server :
* VMware vSphere Enterprise Plus 6.5
* VMware vCenter Server 6.5
* VMware NSX Service Providers Advanced Edition 6.4

Les instances Version d'essai à noeud unique pour vCenter Server ne prennent pas en charge le mode BYOL (Bring Your Own License).
{:note}

## Spécifications techniques relatives à VMware HCX on IBM Cloud
{: #vc_trial_hybrid_orderinginstance-hcx-tech-specs}

L'instance Version d'essai à noeud unique pour vCenter Server comprend HCX on {{site.data.keyword.cloud_notm}}. Les composants suivants sont commandés et inclus dans le service HCX on {{site.data.keyword.cloud_notm}} :

Les instances HCX locales incluent uniquement l'octroi de licence et l'activation.
{:note}

### Paire active/passive de passerelles VMware NSX Edge Services Gateway pour HCX Management
{: #vc_trial_hybrid_orderinginstance-esg}

* UC : 6 vCPU
* Mémoire RAM : 8 Go
* Disque : VMDK 3 Go

### HCX Management Appliance - Machine virtuelle
{: #vc_trial_hybrid_orderinginstance-hcs-mgmt-appliance}

* UC : 4 vCPU
* Mémoire RAM : 12 Go
* Disque : VMDK 60 Go

Des dispositifs HCX supplémentaires sont déployés durant la configuration s'il y a lieu pour la connectivité L2, l'optimisation WAN et les connexions de passerelle.

### Spécifications relatives à la mise en réseau du service HCX on IBM Cloud
{: #vc_trial_hybrid_orderinginstance-hcx-networking-specs}

* Un sous-réseau portable public avec 16 adresses IP
* Deux sous-réseaux portables privés avec 64 adresses IP
* Huit adresses IP issues du sous-réseau vMotion portable privé

## Exigences et planification pour la commande d'instances Version d'essai à noeud unique pour vCenter Server
{: #vc_trial_hybrid_orderinginstance-req}

Assurez-vous que les conditions requises suivantes sont réunies et exécutez les tâches suivantes :
* Conditions requises pour les instances HCX sur site :
 * VMware vSphere et vCenter 5.5 ou de niveau ultérieur sont requis.
 * L'environnement vSphere doit comporter des commutateurs distribués pour les machines virtuelles qui seront migrées vers {{site.data.keyword.cloud_notm}}.
 * Le dispositif HCX Manager Virtual Appliance doit pouvoir être déployé sur un réseau privé dans l'environnement sur site et doit être autorisé à accéder à l'Internet public.
 * Pour pouvoir utiliser {{site.data.keyword.vmwaresolutions_short}} en vue de commander des instances, vous devez disposer d'un compte d'infrastructure {{site.data.keyword.cloud_notm}} (SoftLayer). Le coût des composants commandés dans vos instances est facturé sur ce compte {{site.data.keyword.cloud_notm}}.
 *  Configurez les données d'identification de l'infrastructure {{site.data.keyword.cloud_notm}} sur la page **Paramètres**. Dans la console {{site.data.keyword.vmwaresolutions_short}}, cliquez sur **Paramètres** dans le panneau de navigation de gauche.
 * Passez en revue les exigences relatives au nom d'instance :
    * Seuls les caractères alphanumériques et le tiret (-) sont autorisés.
    * Le nom d'instance doit commencer et se terminer par un caractère alphanumérique.
    * Le nom d'instance ne doit pas dépasser 10 caractères.
    * Le nom d'instance doit être unique au sein de votre compte.

## Procédure de commande d'instances Version d'essai à noeud unique pour vCenter Server
{: #vc_trial_hybrid_orderinginstance-procedure}

1. Sur la page **Version d'essai à noeud unique pour VMware vCenter Server on {{site.data.keyword.cloud_notm}}**, cliquez sur **Continuer**.
2. Sur la page **Version d'essai à noeud unique pour VMware vCenter Server**, exécutez les étapes permettant de demander un compte d'infrastructure {{site.data.keyword.cloud_notm}} ou indiquez votre **nom d'utilisateur** et votre **clé d'API** existants, puis cliquez sur **Extraire**.

 Cette section est masquée si la clé d'API existe déjà.
 {:note}
3. Entrez le nom de l'instance.
4. Sélectionnez l'{{site.data.keyword.CloudDataCent_notm}} qui doit héberger l'instance.  

 Par défaut DAL09 {{site.data.keyword.CloudDataCent_notm}} est présélectionné. Sélectionnez un autre emplacement {{site.data.keyword.CloudDataCent_notm}}, si besoin.
 {:note}
5. Sur la page **Récapitulatif de la commande**, vérifiez la configuration de l'instance avant de passer la commande.
   1. Passez en revue les paramètres de l'instance.
   2. Passez en revue le coût estimé de l'instance. Cliquez sur **Détails concernant la tarification** pour générer un récapitulatif au format PDF. Pour sauvegarder ou imprimer votre récapitulatif de commande, cliquez sur l'icône d'**impression** ou de **téléchargement** dans l'angle supérieur droit de la fenêtre du PDF.
   3. Cliquez sur le ou les liens des conditions applicables à votre commande et prenez soin d'accepter ces conditions avant de commander l'instance.
   4. Cliquez sur **Mettre à disposition**.

### Résultats
{: #vc_trial_hybrid_orderinginstance-results}

Le déploiement de l'instance commence automatiquement et la clé d'activation du service HCX on {{site.data.keyword.cloud_notm}} sur site est commandée.

#### Processus de déploiement du service HCX on IBM Cloud
{: #vc_trial_hybrid_orderinginstance-hcs-deploy-process}

Le déploiement du service HCX on {{site.data.keyword.cloud_notm}} est automatisé. Les étapes suivantes sont exécutées par le processus d'automatisation {{site.data.keyword.vmwaresolutions_short}} :
1. Trois sous-réseaux sont commandés pour le service HCX à partir de l'infrastructure {{site.data.keyword.cloud_notm}} :
   * Deux sous-réseaux portables privés pour la gestion HCX.
   * Un sous-réseau portable public pour l'activation et la maintenance avec VMware. Ce sous-réseau est également utilisé pour les interconnexions HCX.

   Les adresses IP dans les sous-réseaux qui sont commandées pour HCX sont conçues pour être gérées par les fonctions d'automatisation de VMware on {{site.data.keyword.cloud_notm}}. Ces adresses IP ne peuvent pas être affectées à des ressources VMware, telles que des machines virtuelles et des serveurs de périphérie NSX Edge, que vous créez. Si vous avez besoin d'adresses IP supplémentaires pour vos artefacts VMware, vous devez commander vos propres sous-réseaux depuis {{site.data.keyword.cloud_notm}}.
   {:important}
3. Trois pools de ressources et dossiers de machines virtuelles pour HCX, nécessaires pour les interconnexions HCX, les composants HCX locaux et les composants HCX distants, sont créés.
4. Une paire de passerelles VMware NSX ESG (Edge Services Gateway) pour le trafic de gestion HCX est déployée et configurée :
   * Des interfaces de liaison montante publique et privée sont configurées à l'aide des sous-réseaux commandés.
   * Les passerelles ESG sont configurées sous forme de paire de dispositifs Edge très volumineux à haute disponibilité.
   * Les règles de pare-feu et les règles de conversion d'adresses réseau (NAT) sont configurées pour autoriser le trafic HTTPS entrant et sortant vers et depuis HCX Manager.
   * Les règles et les pools de ressources d'équilibrage de charge sont configurés. Ces règles sont des pools de ressources utilisés pour réacheminer le trafic entrant lié à HCX vers les dispositifs virtuels appropriés de HCX Manager, vCenter Server et Platform Services Controller (PSC).
   * Un certificat SSL permettant de chiffrer le trafic HTTPS entrant associé à HCX en provenance des passerelles ESG est appliqué.

   Le serveur de périphérie de gestion HCX est dédié au trafic de gestion HCX entre les composants HCX sur site et les composants HCX côté cloud. Ne modifiez pas le serveur de périphérie de gestion HCX et ne l'utilisez pas pour des extensions de réseau HCX. Créez plutôt des serveurs de périphérie distincts pour les extensions de réseau. Par ailleurs, l'utilisation d'un pare-feu ou la désactivation des communications de serveur de périphérie de gestion HCX sur les composants de gestion IBM privés ou l'Internet public peut avoir une incidence défavorable sur la fonctionnalité HCX.
   {:important}

5. HCX Manager on {{site.data.keyword.cloud_notm}} est déployé, activé et configuré :
   * HCX Manager est enregistré auprès de vCenter Server.
   * HCX Manager, vCenter Server (avec Platform Services Controller intégré) et NSX Manager sont configurés.
   * Le parc HCX est configuré.
   * Les conteneurs de déploiement HCX locaux et distants sont configurés.
6. Le nom d'hôte et l'adresse IP de HCX Manager sont enregistrés auprès du serveur DNS de VMware vCenter Server on {{site.data.keyword.cloud_notm}}.

#### Affichage des détails d'instance
{: #vc_trial_hybrid_orderinginstance-view-inst-details}

Vous pouvez vérifier le statut du déploiement en affichant les détails de l'instance. Cliquez sur **Ressources** dans le panneau de navigation de gauche, puis recherchez le tableau **Instances vCenter Server** ou **Instances HCX locales** pour afficher des informations relatives aux instances que vous avez commandées.

Une fois l'instance correctement déployée, les composants décrits dans les sections *Spécifications techniques* de cette rubrique sont installés sur votre plateforme virtuelle VMware et la clé d'activation du service HCX on {{site.data.keyword.cloud_notm}} sur site est indiquée dans le tableau **Instances HCX locales**.

L'instance prend le statut **Prêt à l'emploi** et vous recevez une notification par courrier électronique.

### Etape suivante
{: #vc_trial_hybrid_orderinginstance-next}

Installez HCX Enterprise Manager sur site et configurez la connexion à votre instance HCX on {{site.data.keyword.cloud_notm}}.

1. Localisez la clé d'activation sur site sur la page **Ressources**.
  1. Dans la console {{site.data.keyword.vmwaresolutions_short}}, cliquez sur **Ressources** dans le panneau de navigation de gauche.
  2. Dans le tableau **Instances vCenter Server**, examinez la colonne **Type** pour localiser l'instance de version d'essai à noeud unique vCenter Server et notez le nom de cette instance.
  3. Faites défiler l'écran vers le tableau **Instances HCX locales**, examinez la colonne **Nom** pour localiser l'instance portant le même nom que l'instance de version d'essai à noeud unique que vous avez commandée avec le suffixe *-OnPrem*.
  4. Notez la clé dans la zone **Clé d'activation**.
2. Procurez-vous le dispositif HCX Enterprise Manager Open Virtual Appliance (OVA) local à partir de la console HCX on {{site.data.keyword.cloud_notm}} HCX Manager.
  1. Connectez-vous à la console HCX Cloud.
    1. Dans le tableau **Instances vCenter Server**, cliquez sur l'instance Version d'essai à noeud unique pour en afficher les détails.
    2. Sous **Informations d'accès**, localisez et notez les données d'identification vCenter.
    3. Cliquez sur **Services** dans le panneau de navigation.
    4. Sur la page **Services**, cliquez sur **HCX on IBM Cloud**.
    5. Sur la page des détails relatifs à **HCX on IBM Cloud**, localisez et notez l'**adresse IP HCX Cloud**.
    6. Assurez-vous que vous êtes connecté au VPN pour accéder à votre réseau privé {{site.data.keyword.cloud_notm}}.
    7. Cliquez sur **Afficher la console HCX Cloud**.
  2. Dans **Console HCX Cloud**, procédez comme suit :
      1. Cliquez sur l'onglet **Administration**.
      2. Sur l'onglet **Mises à jour système**, cliquez sur **Demander le lien de téléchargement**.
      3. Cliquez sur **Copier le lien**, puis utilisez ce lien pour télécharger le client HCX Enterprise sur un environnement local avec accès à votre environnement vSphere local.
3. Dans le client VMware vSphere Web Client, déployez le client HCX Enterprise en tant que dispositif virtuel HCX Manager dans votre environnement local. Pour plus d'informations, voir [Installing the HCX Enterprise Manager OVA](https://docs.vmware.com/en/VMware-NSX-Hybrid-Connect/3.5.1/user-guide/GUID-C61E107C-1F5F-4615-9BA9-351900CDB69E.html).

    Vous devez déployer le gestionnaire HCX Manager local dans un réseau privé et l'autoriser à accéder au réseau public. Vous pouvez utiliser une passerelle NSX Edge, Vyatta ou autre pour accorder l'accès Internet au gestionnaire HCX Manager local. Si les passerelles utilisées pour l'accès au réseau privé et l'accès au réseau public sont différentes, il est recommandé d'utiliser la passerelle par défaut pour autoriser l'accès au réseau public et permettre, depuis la **console d'administration de HCX Manager**, de créer une route statique pour l'accès au réseau privé.  
    {:note}
4. Utilisez la clé d'activation sur site notée à l'étape 1 pour activer votre machine virtuelle HCX Enterprise Manager sur site.
  1. Connectez-vous à votre machine virtuelle HCX Enterprise Manager sur site à l'aide des données d'identification spécifiées lors du déploiement de l'OVA.
  2. Entrez la clé d'activation lorsque vous y êtes invité.

  Pour plus d'informations, voir [HCX Activation and Initial Configuration](https://docs.vmware.com/en/VMware-NSX-Hybrid-Connect/3.5.1/user-guide/GUID-6A4740C1-2225-444C-8ADC-CBE54F181536.html).
  {:note}
5. Un certificat SSL autosigné a été généré par le service HCX on {{site.data.keyword.cloud_notm}}. Vous devez importer le certificat dans le gestionnaire HCX Manager sur site en procédant comme suit :
    1. Sur la **console d'administration de HCX Manager** sur site, cliquez sur l'onglet **Administration**.
    2. Dans le panneau de navigation de gauche, cliquez sur **Certificat d'autorité de certification digne de confiance**, puis sur **Importer** sur la droite.
    3. Cliquez sur **URL** et entrez l'adresse URL du certificat à appliquer, c'est-à-dire l'**adresse IP HCX Cloud** (``https://<cloud-side public IP>``), dont les détails se trouvent sur la page des détails du service HCX on {{site.data.keyword.cloud_notm}} dans la console {{site.data.keyword.vmwaresolutions_short}}.
    4. Cliquez sur **Appliquer**.
6. Continuez la configuration initiale et créez l'interconnexion. Pour plus d'informations, voir [Installing and Configuring VMware HCX Enterprise](https://docs.vmware.com/en/VMware-NSX-Hybrid-Connect/3.5.1/user-guide/GUID-A26BFB16-FA94-426F-8E18-15BAD4BF840E.html).
7. Etendez les réseaux de l'environnement VMware HCX sur site à {{site.data.keyword.cloud_notm}}. Pour plus d'informations, voir [Extending Networks with VMware HCX](https://docs.vmware.com/en/VMware-NSX-Hybrid-Connect/3.5.1/user-guide/GUID-DD9C3316-D01C-4088-B3EA-84ADB9FED573.html?hWord=N4IghgNiBcIKIA8AuBTAdgEwJZoOYAI0UkB3AewCcBrAZxAF8g).
8. Migrez les machines virtuelles entre l'environnement sur site et {{site.data.keyword.cloud_notm}}. Pour plus d'informations, voir [Migrating Virtual Machines with VMware HCX](https://docs.vmware.com/en/VMware-NSX-Hybrid-Connect/3.5.1/user-guide/GUID-D0CD0CC6-3802-42C9-9718-6DA5FEC246C6.html?hWord=N4IghgNiBcILIEsDmAnMAXBA7JACAagiugK6S5xgDGAFtgKYDOuA7gujQXC2CvbgAkAwgA0QAXyA).

Vous devez gérer les composants d'infrastructure {{site.data.keyword.vmwaresolutions_short}} créés dans votre compte {{site.data.keyword.cloud_notm}} uniquement depuis la console {{site.data.keyword.vmwaresolutions_short}}, et non depuis le portail	{{site.data.keyword.slportal}} ou tout autre élément extérieur à la console.
Si vous modifiez ces composants en dehors de la console {{site.data.keyword.vmwaresolutions_short}}, les modifications ne sont pas synchronisées avec la console et votre environnement peut devenir instable.
{:important}

## Procédure de suppression d'instances Version d'essai à noeud unique pour vCenter Server
{: #vc_trial_hybrid_orderinginstance-deleting-procedure}

Lorsque vous supprimez une instance Version d'essai à noeud unique pour vCenter Server, les composants suivants sont libérés, dans cet ordre :

1. Tous les services déployés
3. Licences de produit VMware
4. Serveurs ESXi
5. Sous-réseaux
6. Réseaux locaux virtuels

En raison des dépendances de ressource, les composants de votre instance ne sont pas libérés immédiatement lorsque vous supprimez cette dernière. Par exemple, les sous-réseaux et les réseaux locaux virtuels ne peuvent pas être supprimés tant que l'infrastructure {{site.data.keyword.cloud_notm}} n'a pas récupéré tous les serveurs ESXi, opération qui s'effectue en fin de cycle de facturation de l'infrastructure {{site.data.keyword.cloud_notm}}. A la fin du cycle de facturation de l'infrastructure {{site.data.keyword.cloud_notm}}, qui est généralement de 30 jours, les sous-réseaux et les réseaux locaux virtuels sont supprimés et la suppression de l'instance est effective.

L'instance supprimée vous est facturée jusqu'à échéance du cycle de facturation de l'infrastructure {{site.data.keyword.cloud_notm}}.
{:note}

Procédez comme suit pour supprimer une instance Version d'essai à noeud unique pour vCenter Server :

1. Dans la console {{site.data.keyword.vmwaresolutions_short}}, cliquez sur **Ressources** dans le panneau de navigation de gauche.
2. Dans le tableau **Instances vCenter Server**, recherchez l'instance à supprimer.
3. Dans la colonne **Actions**, cliquez sur l'icône Supprimer.
   L'instance prend le statut **Suppression en cours**. Une fois l'instance supprimée, ses composants sont libérés et elle prend le statut **Supprimé**.
4. Si vous voulez supprimer l'enregistrement d'instance depuis la console {{site.data.keyword.vmwaresolutions_short}}, procédez comme suit :
   1. Dans la colonne **Actions**, cliquez à nouveau sur l'icône Supprimer.
   2. Dans la fenêtre **Supprimer une instance**, cliquez sur **OK**.

## Liens connexes
{: #vc_trial_hybrid_orderinginstance-related}

* [Conception d'architecture HCX on IBM Cloud pour la version d'essai à noeud unique vCenter Server on IBM Cloud](https://console.bluemix.net/docs/services/vmwaresolutions/archiref/trial/vc_trial_hcx_arch.html)
* [Documentation VMware Hybrid Cloud Extension](https://hcx.vmware.com/#/vm-documentation)
* [Obtaining the HCX OVA](https://docs.vmware.com/en/VMware-NSX-Hybrid-Connect/3.5.1/user-guide/GUID-B0471D10-6EB0-4587-9205-11BF0C78EC1C.html)
