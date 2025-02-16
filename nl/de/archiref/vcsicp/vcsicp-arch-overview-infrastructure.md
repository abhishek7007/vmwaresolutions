---

copyright:

  years:  2016, 2019

lastupdated: "2019-05-08"

subcollection: vmware-solutions


---


# IBM Cloud-Netzbetrieb und -Infrastruktur
{: #vcsicp-arch-overview-infrastructure}

## Virtual Routing and Forwarding
{: #vcsicp-arch-overview-infrastructure-vrf}

Sie können {{site.data.keyword.cloud}}-Konten als VRF-Konten (Virtual Routing and Forwarding) konfigurieren. Dadurch wird das automatische globale Routing zwischen Teilnetz-IP-Blöcken aktiviert. Alle Konten mit direkten Verbindungen (Direct-Link) müssen in VRF-Konten konvertiert oder als solche erstellt werden.

## Direct Link
{: #vcsicp-arch-overview-infrastructure-direct-link}

{{site.data.keyword.cloud_notm}} Direct Link Connect bietet privaten Zugriff auf Ihre {{site.data.keyword.cloud_notm}}-Infrastruktur und auf alle anderen Clouds, die mit Ihrem Netzserviceanbieter über Ihr lokales IBM Cloud-Rechenzentrum verbunden sind. Diese Option ist optimal für die Konnektivität zu mehreren Clouds in einer einzelnen Umgebung geeignet. Kunden werden mittels einer gemeinsam genutzten Bandbreitentopologie mit dem {{site.data.keyword.icpfull_notm}}-Netz verbunden. Wie bei allen Direct Link-Produkten können Sie globales Routing hinzufügen, das privaten Netzverkehr zu allen {{site.data.keyword.cloud_notm}}-Standorten ermöglicht.

## Virtuelle private Netze
{: #vcsicp-arch-overview-infrastructure-vp-networks}

### strongSwan-VPN
{: #vcsicp-arch-overview-infrastructure-strongswan}

Der strongSwan-IPSec-VPN-Service stellt einen sicheren End-to-End-Kommunikationskanal über das Internet bereit, der auf der standardisierten IPSec-Protokollsuite (IPSec - Internet Protocol Security) basiert.

### Hybridität (HCX)
{: #vcsicp-arch-overview-infrastructure-hcx}

vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle erweitert die Netze von lokalen Rechenzentren nahtlos in die {{site.data.keyword.cloud_notm}}. Dies ermöglicht die Migration von virtuellen Maschinen in die und aus der {{site.data.keyword.cloud_notm}}, ohne dass hierzu eine Konvertierung oder Änderung erforderlich ist.

## Physische Struktur
{: #vcsicp-arch-overview-infrastructure-phys-struct}

Die physische Infrastruktur, die zur Bereitstellung einer {{site.data.keyword.icpfull_notm}}-Produktionsinstanz für einen VMware vCenter Server (VCS) on {{site.data.keyword.cloud_notm}}-Cluster erforderlich ist, setzt folgende Mindestspezifikationen voraus.

Tabelle 1. vCenter Server-Spezifikation für {{site.data.keyword.icpfull_notm}}

| NFS-Bereitstellung | vSAN-Bereitstellung |
:--|:----:|:----:
Anzahl Server | 3 | 4
CPU | 28 Kerne 2,2 GHz | 28 Kerne 2,2 GHz
RAM | 384 GB | 384 GB
Speicher | 2000 GB 2IOPS/GB Management, 2000 GB 4 IOPS/GB Workload, 4000 GB 4 IOPS/GB {{site.data.keyword.icpfull_notm}} | Mindest-SSD 960 GB x 2

Zusätzlich zu der Hardware, die für {{site.data.keyword.icpfull_notm}} vorausgesetzt wird, müssen Sie persistente Datenträger in der {{site.data.keyword.icpfull_notm}}-Umgebung erstellen, um die CAM-Datenbank- und -Protokolldaten (CAM = Cloud Automation Manager) zu speichern. CAM unterstützt zwar alle persistenten Datenträgertypen, die von {{site.data.keyword.cloud_notm}} unterstützt werden, für CAM empfohlen werden aber die Speicherkonfigurationen NFS und GlusterFS.

## Virtuelle Struktur
{: #vcsicp-arch-overview-infrastructure-virtual-struct}

![Physische Struktur der vCenter Server- und {{site.data.keyword.icpfull_notm}}-Bereitstellung](../../images/vcsicp-phy-ics-icp-deployment.svg "Physische Struktur der vCenter Server- und {{site.data.keyword.icpfull_notm}}-Bereitstellung")

In der vCenter Server-Instanz wird die {{site.data.keyword.icpfull_notm}}-Instanz mit einem dedizierten NSX Edge Services Gateway (ESG) und dem Distributed Logical Router (DLR) bereitgestellt. Die {{site.data.keyword.icpfull_notm}}-Installation wird in das VXLAN-Teilnetz geladen, das in den vorgenannten Komponenten definiert ist.

Das ESG ist mit einer Quellen-NAT-Regel (SNAT) konfiguriert, um abgehenden Datenverkehr zu ermöglichen, wodurch die Internetverbindung zum Download der {{site.data.keyword.icpfull_notm}} -Voraussetzungen und zur Konnektivität mit GitHub und Docker befähigt wird. Alternativ können Sie einen Web-Proxy für die Internetkonnektivität verwenden. Das ESG ist auch für den Zugriff auf DNS- und NTP-Services konfiguriert.

Das ESG ist zudem mit einer Ziel-NAT-Regel (DNAT) für die virtuellen {{site.data.keyword.icpfull_notm}}-Master-/Proxy-IP-Adressen vom {{site.data.keyword.cloud_notm}} 10.x-Netz bis zur VXLAN-Umgebung konfiguriert.

## Zugehörige Links
{: #vcsicp-arch-overview-infrastructure-related}

* [Übersicht über vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle](/docs/services/vmwaresolutions/archiref/vcs?topic=vmware-solutions-vcs-hybridity-intro)
