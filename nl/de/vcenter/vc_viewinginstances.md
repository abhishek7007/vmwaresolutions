---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-01"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# vCenter Server-Instanzen anzeigen
{: #vc_viewinginstances}

Sie können die Zusammenfassung und die detaillierten Informationen der VMware vCenter Server-Instanzen anzeigen, die für verschiedene Benutzerkonten bereitgestellt wurden.

## Vorgehensweise zum Anzeigen einer Zusammenfassung der vCenter Server-Instanzen
{: #vc_viewinginstances-procedure-view-inst-summary}

Wenn Sie eine Zusammenfassung aller vCenter Server-Instanzen, die für ein Benutzerkonto bereitgestellt wurden, anzeigen möchten, führen Sie die folgenden Schritte aus:

1. Klicken Sie in der {{site.data.keyword.vmwaresolutions_full}}-Konsole im linken Navigationsfenster auf **Ressourcen**.
2. Klicken Sie im Konsolenbanner auf das Symbol Ihres Benutzerkontos und klicken Sie anschließend auf das Feld **Konto**, um das Benutzerkonto auszuwählen, für das Sie Instanzen prüfen wollen.  
3. Prüfen Sie in der Tabelle **vCenter Server-Instanzen** die Liste der Instanzen, die in dem ausgewählten Benutzerkonto bereitgestellt sind.

Tabelle 1. Elemente von vCenter Server-Instanzen

| Element        | Beschreibung       |  
|:------------- |:------------- |
| Name | Der Name der Instanz. |
| Typ | Der Typ der vCenter Server-Instanz. |
| Version | Die Releaseversion, in der die Instanz bereitgestellt wurde oder auf die ein Upgrade durchgeführt wurde. |  
| Standort | Das {{site.data.keyword.CloudDataCent_notm}}, in dem die Instanz gehostet wird. |  
| Erstellungszeit | Der Zeitpunkt (Datum und Uhrzeit), zu dem die Instanz erstellt wurde. |
| Status | Der Status der Instanz. |   

Für die Instanz gibt es eine Reihe von Statuswerten.

Tabelle 2. Statusbeschreibungen der vCenter Server-Instanzen

| Status        | Beschreibung       |
|:------------- |:------------- |
| Wird erstellt | Die Instanz wird gerade erstellt. |
| Wird aufgebaut | Die Instanz wird gerade konfiguriert. |
| Bereit | Die Instanz ist zur Verwendung bereit. |
| Wird geändert | Die Instanz wird gerade geändert. |
| Fehlgeschlagen | Der Erstellungs-, Konfigurations- oder Änderungsprozess ist fehlgeschlagen. |
| Wird gelöscht | Die Instanz wird gerade gelöscht. |
| Fehler beim Löschvorgang | Beim Löschen der Instanz ist ein Fehler aufgetreten. |
| Gelöscht | Die Instanz wurde gelöscht. |

## Vorgehensweise zum Anzeigen von Eigenschaftsdetails einer vCenter Server-Instanz
{: #vc_viewinginstances-procedure-view-inst-property}

Gehen Sie wie folgt vor, um die Eigenschaftsdetails einer Instanz anzuzeigen:

1. Klicken Sie in der Tabelle **vCenter Server-Instanzen** auf einen Instanznamen.
2. Zeigen Sie unter **Eigenschaften** die Details für die Instanz an.

Tabelle 3. Eigenschaften von vCenter Server-Instanzen

| Eigenschaft        | Beschreibung       |
|:------------- |:------------- |
| Name | Der Name der Instanz. |
| ID | Die ID der Instanz. |
| Standort | Das {{site.data.keyword.CloudDataCent_notm}}, in dem die Instanz gehostet wird. |
| Aktuelle Version | Die aktuelle Version von {{site.data.keyword.vmwaresolutions_short}}. |
| vCenter-Version | Die Version von VMware vCenter Server.<br><br>**Hinweis:** Die Versionen von vCenter Server, die in der {{site.data.keyword.vmwaresolutions_short}}-Konsole und in VMware vSphere Web Client angezeigt werden, weichen etwas voneinander ab. Beide Angaben sind richtig. |
| NSX for vSphere | Die Produktversion von VMware NSX for vSphere. |
| _VMware-Komponente_ - Lizenz | Wenn Sie beim Bestellen der Instanz auf der Seite **Lizenzierung** ausgewählt haben, dass Sie für die VMware-Komponenten Ihre eigene Lizenz verwenden wollen, werden hier der Name der VMware-Komponente und der Lizenzschlüssel angezeigt, den Sie für die Komponente eingegeben haben.<br><br>Beispiele für VMware-Komponentenlizenzen sind die **NSX-Lizenz**, die **vCenter Server-Lizenz** und die **vSAN-Lizenz**. |
| NSX-Lizenzedition | Die Version und Edition der VMware NSX-Lizenz. |
| DNS, Rootdomäne | Der Rootdomänenname ist der Domänenname von DNS (Domain Name System) und der Gesamtstrukturrootname von Microsoft Active Directory (AD). |
| DNS, SSO-Domäne | Die SSO-Domäne ist die Single-Sign-on-Domäne von vSphere. Der SSO-Domänenname wird für alle bereitgestellten vCenter Server-Instanzen auf <samp class="ph codeph">vsphere.local</samp> festgelegt. |
| DNS, Unterdomäne | Die Unterdomäne ist im DNS-Unterdomänennamen des Namens der Rootdomäne angegeben, in der sich die Hostnamen der lokalen vCenter Server-Instanz befinden. Der Unterdomänenname hat das Format <samp class="ph codeph"><var class="keyword varname">name_der_vcenter_server-instanz</var>.<var class="keyword varname">root.domänenname</var></samp>. |
| Hybridity Bundle | Gibt an, ob vCenter Server with Hybridity Bundle installiert ist. |
| Status  | Der Status der Instanz.<br><br>Die angezeigten Informationen aktualisieren den Verarbeitungsfortschritt bei der Bereitstellung bzw. der für die Instanz ausgeführten Aktion. Falls Probleme auftreten, wird möglicherweise eine Nachricht angezeigt, die Sie bei der Untersuchung und Lösung des Problems unterstützt. |

## Vorgehensweise zum Anzeigen der Zugriffsinformationen für vCenter Server-Instanzen
{: #vc_viewinginstances-procedure-view-access-info}

Zeigen Sie unter **Zugriffsinformationen** die Zugriffsinformationen für die instanzbezogenen Komponenten an. Bei den angezeigten Kennwörtern handelt es sich um Anfangskennwörter, die vom System generiert werden. Wenn Sie sie außerhalb der {{site.data.keyword.vmwaresolutions_short}}-Konsole ändern, werden sie auf der Seite mit der Instanzzusammenfassung nicht aktualisiert.

Tabelle 4. vCenter Server-Zugriffsinformationen für instanzbezogene Komponenten

| Komponente        | Beschreibung       |
|:------------- |:------------- |
| AD/DNS-IPs | Die IP-Adressen der beiden AD-Server. |
| Vollständig qualifizierte Domänennamen für AD/DNS | Die vollständig qualifizierten Domänennamen des AD/DNS-Servers.<br><br>**Hinweis:** Zur Herstellung einer Verbindung zu allen AD/DNS-Servern über eine Remote-Desktop-Verbindung kann dasselbe Administratorkennwort verwendet werden. |
| AD/DNS ADMIN (Remote Desktop)  | Für primäre Instanzen werden der Benutzername und das Kennwort für den Zugriff auf den AD-Server über eine Remote-Desktop-Verbindung angezeigt.<br><br>Klicken Sie für sekundäre Instanzen auf den Link **Für primäre Instanz anzeigen**, um zu den Informationen zu Benutzername und Kennwort in der primären Instanz weitergeleitet zu werden.<br><br>**Hinweis:** Wenn die sekundäre Instanz zur primären DNS-Domäne hinzugefügt wurde und die Replikation stattfindet, überschreibt das lokale Administratorkennwort für die primäre Instanz möglicherweise das lokale Administratorkennwort für die sekundäre Instanz. Wenn Sie auf den Link **Für primäre Instanz anzeigen** klicken, erhalten Sie Zugriff auf das richtige Administratorkennwort.  
| NSX-Manager-IP  | Die IP-Adresse des NSX-Managers.  |
| Vollständig qualifizierter Domänenname für NSX-Manager  | Der vollständig qualifizierte Domänenname des NSX-Managers.  |
| NSX-Manager-HTTP  | Der Benutzername und das Kennwort für den Zugriff auf die Webkonsole des NSX-Managers. |
| vCenter-IP  | Die IP-Adresse von vCenter Server.  |
| Vollständig qualifizierter Domänenname für vCenter  | Der vollständig qualifizierte Domänenname von vCenter Server.  |
| vCenter-ADMIN  | Der SSO-Benutzername und das Kennwort für VMware vCenter, mit dem Sie sich unter Verwendung von vSphere Web Client bei vCenter Server anmelden können.  |
| vCenter-SSH  | Der Benutzername und das Kennwort, die Sie für den Zugriff auf die VM für vCenter Server über eine SSH-Verbindung verwenden können.  |

## Vorgehensweise zum Anzeigen des Bereitstellungsverlaufs für vCenter Server-Instanzen
{: #vc_viewinginstances-procedure-view-deploy-history}

Klicken Sie im linken Navigationsfenster auf **Bereitstellungsverlauf**, um den Bereitstellungsverlauf für die Instanz anzuzeigen.

Tabelle 5. Bereitstellungsverlauf der vCenter Server-Instanz

| Element        | Beschreibung       |  
|:------------- |:------------- |
| Datum | Der Zeitpunkt (Datum und Uhrzeit), zu dem sich der Instanzstatus geändert hat. |
| Zusammenfassung | Die Details der Änderung. |

## Nächste Schritte bei aufgetretenen Fehlern
{: #vc_viewinginstances-if-errors-occur}

Wenn bei der Bereitstellung oder beim Löschen von Instanzen Fehler auftreten, wird automatisch das {{site.data.keyword.cloud_notm}}-Support-Team benachrichtigt. Um den Status Ihres Tickets abzufragen, können Sie den [IBM Support kontaktieren](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support).

## Nächste Schritte
{: #vc_viewinginstances-next}

Nun können Sie Ihre Instanzen in der {{site.data.keyword.vmwaresolutions_short}}-Konsole oder in VMware vSphere Web Client verwalten.

Bevor Sie auf der Seite mit der Instanzzusammenfassung auf **vCenter-Konsole** klicken, um vSphere Web Client aufzurufen und Ihre ESXi-Server zu verwalten, müssen Sie sich beim VPN-Portal des {{site.data.keyword.CloudDataCent_notm}} anmelden. Bewegen Sie den Mauszeiger über die Schaltfläche **vCenter-Konsole** und befolgen Sie die Anweisungen, um sicherzustellen, dass Sie alle Voraussetzungen erfüllen und Sie alle erforderlichen Schritte ausgeführt haben, bevor Sie auf vSphere Web Client zugreifen.
{:important}

In den folgenden Abschnitten finden Sie Informationen, die Sie bei der Ausführung der Anmeldeanweisungen unterstützen:
*  Informationen zu den Voraussetzungen und erforderlichen Schritten vor dem Zugriff auf vSphere Web Client finden Sie unter [Zeitlimitüberschreitung beim Herstellen einer Verbindung zu vSphere Web Client](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_timeout_vc_console).
*  Eine Liste der Zugriffspunkte für die Anmeldung beim privaten Netz der {{site.data.keyword.cloud_notm}}-Infrastruktur mittels VPN finden Sie unter [VPN-Zugriff](http://www.softlayer.com/vpn-access){:new_window}.
*  Falls Sie beim Bereitstellen einer Datei im Format "OVF" (Open Virtualization Format) mit vSphere Web Client Probleme feststellen, finden Sie unter [OVF-Datei mit vSphere Web Client bereitstellen](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_deploy_ovf) weitere Informationen.

## Zugehörige Links
{: #vc_viewinginstances-related}

* [vCenter Server-Instanzen bestellen](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance)
* [Cluster für vCenter Server-Instanzen hinzufügen, anzeigen und löschen](/docs/services/vmwaresolutions?topic=vmware-solutions-vc_addingviewingclusters#vc_addingviewingclusters)
* [Kapazität für vCenter Server-Instanzen erweitern und verringern](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_addingremovingservers)
* [vCenter Server-Instanzen löschen](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_deletinginstance)
