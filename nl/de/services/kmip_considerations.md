---

copyright:

  years:  2016, 2019

lastupdated: "2019-02-15"

---

{:tip: .tip}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}

# KMIP for VMware on IBM Cloud - Übersicht - nicht mehr verwendet
{: #kmip_considerations}

Die aktuelle Version von KMIP for VMware on IBM Cloud wird nicht weiter unterstützt. Weitere Informationen finden Sie unter [Kontaktaufnahme mit dem IBM Support](../vmonic/trbl_support.html).
{:deprecated}

Der Service "KMIP for VMware on {{site.data.keyword.cloud}}" stellt täglich rund um die Uhr einen hoch verfügbaren Service für das Management von Verschlüsselungsschlüsseln bereit, die von VMware in der {{site.data.keyword.cloud_notm}} verwendet werden. Dieser Service bietet Laufzeitfunktionalität, mit der Kunden die Verschlüsselungsschlüssel erstellen, abrufen, aktivieren, widerrufen und zerstören können. Außerdem stellt er Managementfunktionen zum Verwalten der Zuordnungen zwischen den Clientberechtigungsnachweisen und den Verschlüsselungsschlüsseln bereit.

## Technische Spezifikationen für KMIP for VMware on IBM Cloud
{: #kmip_considerations-specs}

Die folgenden Spezifikationen werden mit dem Service "KMIP for VMware on {{site.data.keyword.cloud_notm}}" einbezogen:

* Ein VMware-kompatibles Key Management Interoperability Protocol (KMIP)
* Ein verwalteter Service
* Verfügbar in mehreren geografischen Regionen weltweit
* Hochverfügbarer KMIP-Serviceendpunkt in jeder Region

## Hinweise zur Installation von KMIP for VMware on IBM Cloud
{: #kmip_considerations-install}

KMIP for VMware on {{site.data.keyword.cloud_notm}} verwendet den Service "IBM Key Protect for {{site.data.keyword.cloud_notm}}", um Verschlüsselungsschlüssel zu erstellen, zu verschlüsseln und zu entschlüsseln. Daher müssen Sie vor der Installation von KMIP for VMware on {{site.data.keyword.cloud_notm}} Folgendes sicherstellen:
* Sie haben einen verwendbaren Key Protect-Service bestellt.
* Es wurde eine {{site.data.keyword.cloud_notm}}-Service-ID unter Beachtung der Schritte in [Service-ID erstellen](../../../iam/serviceid.html) erstellt. Diese Service-ID wird verwendet, um auf die von Ihnen erstellte Instanz des Key Protect-Service zuzugreifen.
* Sie haben die folgenden Zugriffsebenen für die Service-ID erteilt:
   * Auf Plattformzugriffsebene: Anzeigeberechtigung für Ihre Instanz von IBM Key Protect.
   * Auf Servicezugriffsebene: Schreibberechtigung für Ihre Instanz von IBM Key Protect
* Sie verfügen über einen API-Schlüssel für die erstellte Service-ID. Der Schlüssel ist zum Bestellen des Service erforderlich.
* Sie haben mindestens einen Stammschlüssel für Kunden (Customer Root Key, CRK) in der Key Protect-Benutzerschnittstelle erstellt. Dazu haben Sie die entsprechenden Schritte wie in [Stammschlüssel erstellen](../../keymgmt/keyprotect_create_root.html) beschrieben ausgeführt oder Sie haben die REST-API in [IBM Key Protect](https://cloud.ibm.com/apidocs/key-protect) verwendet.

   **Wichtig:** Der Service kann nicht ohne Stammschlüssel für Kunden (Customer Root Key, CRK) bestellt werden. Es wird dringend empfohlen, das Verfahren für die Erstellung eines Stammschlüssels für Kunden unter Verwendung vorhandener Schlüsselinformationen zu verwenden und die erstellten Schlüsselinformationen zu sichern. Dadurch stellen Sie sicher, dass Sie Ihre Schlüssel im Falle eines Ausfalls des Rechenzentrums, in dem IBM Key Protect Ihre Stammschlüssel für Kunden speichert, wiederherstellen können.

## Hinweise zur Verwendung von KMIP for VMware on IBM Cloud
{: #kmip_considerations-use}

* Zur Verwendung eines bestellten Service "KMIP for VMware on {{site.data.keyword.cloud_notm}}" als Schlüsselmanagementserver (Key Management Server, KMS), der bei VMware vCenter Server registriert ist, müssen Sie sicherstellen, dass die Netzkonnektivität von vCenter Server zum Endpunkt des bestellten Service "KMIP for VMware on {{site.data.keyword.cloud_notm}}" betriebsfähig ist.
* Zur Verwendung des Service mit der VMware vSAN-Verschlüsselung müssen Sie sicherstellen, dass die Netzkonnektivität zwischen den Hosts im Ziel-vSAN und dem Endpunkt des bestellten Service "KMIP for VMware on {{site.data.keyword.cloud_notm}}" betriebsfähig ist.
* Bei Verwendung der KMIP for VMware with vSAN-Verschlüsselung werden bei der vSAN-Statusprüfung möglicherweise in regelmäßigem Abstand Warnungen ausgegeben, die besagen, dass von keinem Ihrer vSphere-Hosts eine Verbindung zum KMS-Cluster hergestellt werden kann. Diese Warnungen treten auf, da es für die Verbindung der vSAN-Statusprüfung zu schnell zu einer Zeitlimitüberschreitung kommt. Sie können diese Warnungen ignorieren.

## Hinweise zum Entfernen von KMIP for VMware on IBM Cloud
{: #kmip_considerations-remove}

Das öffentliche VMware-Zertifikat, das Sie beim Bestellen oder Verwenden des Service angegeben haben, wird als Clientzertifikat für die Kommunikation mit der Serviceinstanz verwendet. Wenn der Service entfernt wird, werden damit auch alle Verschlüsselungsschlüssel entfernt, die von dieser Serviceinstanz für das zugehörige öffentliche VMware-Zertifikat erstellt wurden.

Bevor Sie den Service entfernen, müssen Sie sicherstellen, dass keine virtuellen Maschinen oder vSANs mit den vom KMIP-Service erstellten Schlüsseln verschlüsselt werden.

## Zugehörige Links
{: #kmip_considerations-related}

* [KMIP for VMware on {{site.data.keyword.cloud_notm}} bestellen](kmip_ordering.html)
* [{{site.data.keyword.cloudaccesstrailshort}}-Ereignisse](../vmonic/at-events.html)
* [IBM Key Protect for {{site.data.keyword.cloud_notm}}](../../keymgmt/index.html)
* [vSphere Security](https://docs.vmware.com/en/VMware-vSphere/6.5/com.vmware.vsphere.security.doc/GUID-52188148-C579-4F6A-8335-CFBCE0DD2167.html)
* [Häufig gestellte Fragen](../vmonic/faq.html)
* [Kontaktaufnahme mit dem IBM Support](../vmonic/trbl_support.html)
