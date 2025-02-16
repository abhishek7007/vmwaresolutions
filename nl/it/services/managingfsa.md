---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-04"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Gestione di FortiGate Security Appliance on IBM Cloud
{: #managingfsa}

Dopo aver installato correttamente il servizio FortiGate Security Appliance on {{site.data.keyword.cloud}}, puoi gestire e configurare le regole del firewall per FSA dalla console FortiGate.

Devi assicurarti che le regole del firewall FSA siano definite per consentire le comunicazioni HTTPS in uscita (porta TCP 443) che vengono avviate dai componenti di gestione come Zerto Virtual Manager per comunicare con il database di gestione esterno sull'infrastruttura {{site.data.keyword.cloud_notm}} tramite Internet. Le comunicazioni HTTPS in uscita (porta TCP 443) hanno origine dall'indirizzo IP pubblico del gateway dei servizi edge (ESG) VMware NSX dei servizi di gestione nella tua istanza.
{:important}

## Accesso alla console FortiGate serie 300
{: #managingfsa-access-console}

Per gestire il servizio FortiGate Security Appliance on {{site.data.keyword.cloud_notm}}, devi accedere alla console FortiGate® serie 300 in uno dei seguenti modi:
* Accedi al client web FortiOS utilizzando le credenziali che puoi trovare nella pagina dei dettagli del servizio FortiGate Security Appliance on {{site.data.keyword.cloud_notm}}.
* Accedi alla console tramite una connessione SSH utilizzando le credenziali che puoi trovare nella pagina dei dettagli del servizio FortiGate Security Appliance on {{site.data.keyword.cloud_notm}}.

Per ulteriori informazioni, vedi [Ordine, visualizzazione e rimozione dei servizi per le istanze vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_addingremovingservices).

## Link correlati
{: #managingfsa-related}

* [Panoramica di FortiGate Security Appliance on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-fsa_considerations)
* [Come contattare il supporto IBM](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support)
* [Domande frequenti](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-faq)
* [Sito web fortinet.com](https://www.fortinet.com/)
* [Libreria di documenti Fortinet](https://docs.fortinet.com/product/fortigate/6.2)
