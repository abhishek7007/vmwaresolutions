---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-23"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Hinweise zu lokalen VMware HCX on IBM Cloud-Instanzen
{: #standalone_considerations}

Lesen Sie die folgenden Hinweise, bevor Sie die HCX on {{site.data.keyword.cloud}}-Instanzen installieren oder löschen, die Sie für die lokale Verwendung, also für die Verwendung in Ihrer lokalen Umgebung, bestellt haben.

Eine vCenter Server-Instanz mit HCX on {{site.data.keyword.cloud_notm}} ist auf drei simultane Verbindungen von lokalen Standorten begrenzt.
{:note}

## Hinweise vor der Installation von lokalen HCX on IBM Cloud-Instanzen
{: #standalone_considerations-install}

Die HCX on {{site.data.keyword.cloud_notm}}-Komponenten müssen sowohl in der {{site.data.keyword.cloud_notm}} als auch in Ihrer lokalen vSphere-Umgebung installiert sein. Es empfiehlt sich, den Service "HCX on {{site.data.keyword.cloud_notm}}" in Ihrer vCenter Server with Hybridity Bundle-Instanz in {{site.data.keyword.cloud_notm}} zu installieren, bevor Sie die lokale HCX on {{site.data.keyword.cloud_notm}}-Instanz installieren. Weitere Informationen finden Sie im Abschnitt [Hinweise zur Installation von HCX on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-hcx_considerations#hcx_considerations-install).

### Anforderungen an IP-Adressen
{: #standalone_considerations-ip}

Für die vollständige HCX-Funktionalität benötigen Sie mindestens fünf private IP-Adressen mit Internetzugriff.

### Bereitstellungsprozess für lokale HCX on IBM Cloud-Instanzen
{: #standalone_considerations-deploy}

Zur erfolgreichen Installation auf der lokalen HCX on {{site.data.keyword.cloud_notm}}-Instanz müssen Sie die folgenden Tasks ausführen.
1. Bestellen Sie in der {{site.data.keyword.vmwaresolutions_short}}-Konsole die lokale HCX on {{site.data.keyword.cloud_notm}}-Instanz. Weitere Informationen finden Sie unter [Lokale HCX-Instanzen bestellen](/docs/services/vmwaresolutions/services?topic=vmware-solutions-standalone_orderingserviceinstances).
2. Führen Sie in der **HCX-Cloudkonsole** die folgenden Schritte aus:
    1. Klicken Sie auf die Registerkarte **Verwaltung**.
    2. Klicken Sie auf der Registerkarte **Systemupdates** auf **DOWNLOAD-LINK ANFORDERN**.
    3. Klicken Sie auf **LINK KOPIEREN** und verwenden Sie anschließend diesen Link, um HCX Enterprise Client in eine lokale Umgebung herunterzuladen, die Zugriff auf Ihre lokale vSphere-Umgebung besitzt.
3. Stellen Sie HCX Enterprise Client in VMware vSphere Web Client als virtuelle Appliance für den HCX-Manager (kurz "HCX-Manager") in Ihrer lokalen Umgebung bereit.

   Sie müssen den lokalen HCX-Manager in einem privaten Netz bereitstellen und ihm den Zugriff auf das öffentliche Netz ermöglichen. Sie können NSX Edge, Vyatta oder ähnliche Gateways verwenden, um dem lokalen HCX-Manager den Internetzugriff zu ermöglichen. Falls für den Zugriff auf das private Netz und auf das öffentliche Netz verschiedene Gateways verwendet werden, empfiehlt es sich, das Standardgateway für den Zugriff auf das öffentliche Netz zu verwenden und mit der lokalen **Administratorkonsole für den HCX-Manager** eine statische Route für den Zugriff auf das private Netz zu erstellen.
   {:note}
4. Verwenden Sie nach der Bereitstellung des HCX-Managers die **Administratorkonsole für den HCX-Manager**, um den lokalen HCX-Manager zu aktivieren. Einen Aktivierungsschlüssel für den lokalen HCX-Manager erhalten Sie, wenn Sie eine lokale HCX on {{site.data.keyword.cloud_notm}}-Instanz in der {{site.data.keyword.vmwaresolutions_short}}-Konsole bestellen. Weitere Informationen finden Sie unter [Lokale HCX-Instanzen bestellen](/docs/services/vmwaresolutions/services?topic=vmware-solutions-standalone_orderingserviceinstances).
5. Falls Sie ein selbst signiertes SSL-Zertifikat verwendet haben, als Sie den Service "HCX on {{site.data.keyword.cloud_notm}}" bestellt haben, müssen Sie das Zertifikat in den lokalen HCX-Manager importieren, indem Sie die folgenden Schritte ausführen:
    1. Klicken Sie in der lokalen **Administratorkonsole für den HCX-Manager** auf die Registerkarte **Verwaltung**.
    2. Klicken Sie im linken Navigationsfenster auf **Anerkanntes CA-Zertifikat** und dann rechts auf **IMPORTIEREN**.
    3. Klicken Sie auf **URL** und geben Sie dann die URL des Zertifikats ein, das Sie anwenden möchten. Dies ist die **HCX-Cloud-IP** (``https://<cloud-side public IP>``), die Sie auf der Seite mit den Details für den Service "HCX on {{site.data.keyword.cloud_notm}}" in der {{site.data.keyword.vmwaresolutions_short}}-Konsole finden.
    4. Klicken Sie auf **ANWENDEN**.

Die Basiskonfiguration für den lokalen HCX-Manager ist hiermit abgeschlossen. Sie können nun den lokalen HCX on {{site.data.keyword.cloud_notm}}-Standort mit dem cloudseitigen HCX-Standort verbinden.

Weitere Informationen finden Sie auf der Seite [VMware Hybrid Cloud Extension](https://cloud.vmware.com/vmware-hcx).

## Hinweise vor dem Löschen von lokalen HCX on IBM Cloud-Instanzen
{: #standalone_considerations-delete}

Lesen Sie die folgenden Hinweise, bevor Sie eine HCX on {{site.data.keyword.cloud_notm}}-Instanz löschen, die Sie für die lokale Verwendung bestellt haben.
1. Rufen Sie in VMware vSphere Web Client die HCX-Benutzerschnittstelle auf und prüfen Sie die folgenden Punkte:
    1. Vergewissern Sie sich, dass keine Operation für die HCX-Migration oder -Disaster-Recovery aktiv ist.
    2. Vergewissern Sie sich, dass alle erweiterten Netze entfernt wurden.
    3. Vergewissern Sie sich, dass alle Verbindungskomponenten mit paarweise verbundenen Cloudstandorten entfernt wurden.

   Sie müssen alle vorherigen Schritte ausführen, bevor Sie mit dem nächsten Schritt fortfahren. Andernfalls wird die Lizenz für die lokale HCX on {{site.data.keyword.cloud_notm}}-Instanz storniert. Wenn die Lizenz storniert wird, können Migrationen nicht ausgeführt werden und es können Fehler in den HCX-Komponenten auftreten.  
   {:important}
2. Löschen Sie in der {{site.data.keyword.vmwaresolutions_short}}-Konsole die lokale HCX on {{site.data.keyword.cloud_notm}}-Instanz, die bestellt wurde, um den Aktivierungsschlüssel für den lokalen HCX-Manager zu erhalten. Stellen Sie sicher, dass die gelöschte Instanz nicht mehr in der Konsole verfügbar ist, bevor Sie mit dem nächsten Schritt fortfahren.

   Weitere Informationen finden Sie unter [Lokale HCX on {{site.data.keyword.cloud_notm}}-Instanzen löschen](/docs/services/vmwaresolutions/services?topic=vmware-solutions-standalone_deletingserviceinstances).
3. Löschen Sie den lokalen HCX-Manager in VMware vSphere Web Client.

## Zugehörige Links
{: #standalone_considerations-related}

* [Lokale HCX on {{site.data.keyword.cloud_notm}}-Instanzen anzeigen](/docs/services/vmwaresolutions/services?topic=vmware-solutions-standalone_viewingserviceinstances)
* [Glossar der HCX-Begriffe](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcx_glossary)
* [Dokumentation zu VMware Hybrid Cloud Extension](https://cloud.vmware.com/vmware-hcx/resources)
* [Kontaktaufnahme mit dem IBM Support](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support)
