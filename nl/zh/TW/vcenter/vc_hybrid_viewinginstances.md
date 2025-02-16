---

copyright:

  years:  2016, 2019

lastupdated: "2019-03-04"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# 檢視 vCenter Server with Hybridity Bundle 實例
{: #vc_hybrid_viewinginstances}

檢視針對不同使用者帳戶佈建之 VMware vCenter Server with Hybridity Bundle 實例的摘要及詳細資訊。

## 檢視 vCenter Server with Hybridity Bundle 實例摘要的程序
{: #vc_hybrid_viewinginstances-procedure-view-inst-summary}

若要檢視針對使用者帳戶佈建之所有 vCenter Server with Hybridity Bundle 實例的摘要，請完成下列步驟：
1. 在 {{site.data.keyword.vmwaresolutions_full}} 主控台中，從左導覽窗格按一下**資源**。
2. 從主控台橫幅，按一下您的使用者帳戶圖示，然後按一下**帳戶**欄位，以選取您要檢查其實例的使用者帳戶。
3. 在 **vCenter Server 實例**表格中，檢視佈建在所選取使用者帳戶中的實例清單。

表 1. vCenter Server with Hybridity Bundle 實例項目

|項目        |說明       |  
|:------------- |:------------- |
|名稱 |實例的名稱|
|類型      | vCenter Server 實例的類型 |
|版本|實例部署所使用或升級至的發行版本|  
|位置|管理實例所在的 {{site.data.keyword.CloudDataCent_notm}} |  
|建立時間|建立實例的日期和時間|  
|狀態|實例的狀態|  

實例可以具有一定範圍的狀態。

表 2. vCenter Server with Hybridity Bundle 實例狀態說明

|狀態|說明       |
|:------------- |:------------- |
|正在建立|正在建立實例。|
|正在建置|正在配置實例。|
|備妥使用|實例已備妥可供使用。|
|正在修改|正在修改實例。|
|失敗|建立、配置或修改程序失敗。|
|正在刪除|正在刪除實例。|
|刪除錯誤|刪除實例時發生錯誤。|
|已刪除|已刪除實例。|

## 檢視 vCenter Server with Hybridity Bundle 實例內容詳細資料的程序
{: #vc_hybrid_viewinginstances-procedure-view-inst-property}

若要檢視 vCenter Server with Hybridity Bundle 實例的內容詳細資料，請執行下列動作：
1. 在 **vCenter Server 實例**表格中，按一下實例名稱。
2. 在**內容**下，檢視實例的詳細資料。

表 3. vCenter Server with Hybridity Bundle 實例內容

|內容        |說明       |
|:------------- |:------------- |
|名稱 |實例的名稱。|
|ID |實例的 ID。|
|位置|管理實例所在的 {{site.data.keyword.CloudDataCent_notm}}。|
|現行版本|{{site.data.keyword.vmwaresolutions_short}} 的現行版本。|
|vCenter 版本|VMware vCenter Server with Hybridity Bundle 版本。<br><br>**附註：**在 {{site.data.keyword.vmwaresolutions_short}} 主控台及 VMware vSphere Web Client 上顯示的 vCenter Server 版本之間略有不同。兩者皆正確。|
|NSX for vSphere |VMware NSX for vSphere 產品版本。|
|NSX 授權版本|VMware NSX 授權的版本。|
|DNS、根網域|根網域名稱是 DNS（網域名稱系統）網域名稱及 Microsoft Active Directory (AD) 樹系根名稱。|
|DNS、SSO 網域|SSO 網域是 vSphere Single Sign-On 網域。針對值為 <samp class="ph codeph">vsphere.local</samp> 的所有已部署 vCenter Server with Hybridity Bundle 實例，SSO 網域名稱是固定的。|
|DNS、子網域|子網域是本端 vCenter Server with Hybridity Bundle 實例主機名稱所在之根網域名稱的 DNS 子網域名稱。子網域名稱的格式為 <samp class="ph codeph"><var class="keyword varname">vcenter_server_instance_name</var>.<var class="keyword varname">root.domain_name</var></samp>。|
| Hybridity Bundle |指出是否已安裝 vCenter Server with Hybridity Bundle。|
|狀態|實例的狀態。<br><br>顯示的資訊會提供關於部署進度或對實例所採取動作的更新。如果發生問題，可能會顯示訊息，以協助您調查及解決問題。|

## 檢視 vCenter Server with Hybridity Bundle 實例存取資訊的程序
{: #vc_hybrid_viewinginstances-procedure-view-access-info}

在**存取資訊**下，檢視實例相關元件的存取資訊。顯示的密碼是系統產生的起始密碼。如果您在 {{site.data.keyword.vmwaresolutions_short}} 主控台以外變更它們，則不會在實例摘要頁面上更新它們。

表 4. 實例相關元件的 vCenter Server with Hybridity Bundle 存取資訊

|元件        |說明       |
|:------------- |:------------- |
|AD/DNS IP |兩部 AD 伺服器的 IP 位址。|
|AD/DNS FQDN |AD/DNS 伺服器的完整網域名稱。<br><br>**附註：**您可以使用相同的管理者密碼，透過遠端桌面連線來連接至所有 AD/DNS 伺服器。|
|AD/DNS ADMIN（遠端桌面）|針對主要實例，它會顯示用來透過遠端桌面連線存取 AD 伺服器的使用者名稱及密碼。<br><br>針對次要實例，按一下**在主要實例上檢視**鏈結，以便導向至主要實例上使用者名稱及密碼資訊。<br><br>**附註：**將次要實例新增至主要 DNS 網域並進行抄寫之後，主要實例上的本端管理者密碼可能會改寫次要實例上的本端管理者密碼。按一下**在主要實例上檢視**鏈結，即可存取正確的管理者密碼。  
|NSX Manager IP  |NSX Manager 的 IP 位址。|
|NSX Manager FQDN  |NSX Manager 的完整網域名稱 (FQDN)。|
|NSX Manager HTTP  |用來存取 NSX Manager Web 主控台的使用者名稱和密碼。|
|vCenter IP  |vCenter Server 的 IP 位址。|
|vCenter FQDN  |vCenter Server 的完整網域名稱 (FQDN)。|
|vCenter ADMIN  |您可以用來使用 vSphere Web Client 登入 vCenter Server 的 VMware vCenter Single Sign-On 使用者名稱及密碼。|
|vCenter SSH  |您可以用來透過 SSH 連線存取 vCenter Server VM 的使用者名稱及密碼。|

## 檢視 vCenter Server with Hybridity Bundle 實例部署歷程的程序
{: #vc_hybrid_viewinginstances-procedure-view-deploy-history}

按一下左導覽窗格中的**部署歷程**，以檢視該實例的部署歷程。

表 5. vCenter Server with Hybridity Bundle 實例部署歷程

|項目        |說明       |  
|:------------- |:------------- |
|日期 |變更實例狀態的日期和時間|
|摘要 |變更的詳細資料|

## 發生錯誤時要執行的作業
{: #vc_hybrid_viewinginstances-if-errors-occur}

如果在部署實例或刪除實例期間發生錯誤，則會自動通知「{{site.data.keyword.cloud_notm}} 支援中心」團隊。若要查詢問題單的狀態，您可以[與 IBM 支援中心聯絡](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support)。

## 下一步
{: #vc_hybrid_viewinginstances-next}

從 {{site.data.keyword.vmwaresolutions_short}} 主控台或 VMware vSphere Web Client 管理實例。

您必須先登入 {{site.data.keyword.CloudDataCent_notm}} 的 VPN 入口網站，才能在實例摘要頁面上按一下 **vCenter 主控台**，以移至 vSphere Web Client 並開始管理 ESXi 伺服器。將游標移至 **vCenter 主控台**按鈕上方，並遵循指示以確保您符合所有需求，並在存取 vSphere Web Client 之前完成必要的步驟。
{:important}

如需可協助您完成登入指示的資訊，請檢閱下列主題：
*  如需存取 vSphere Web Client 之前的需求及必要步驟，請參閱[連接至 vSphere Web Client 時發生逾時](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_timeout_vc_console)。
*  如需使用 VPN 登入 {{site.data.keyword.cloud_notm}} 基礎架構「專用網路」的存取點清單，請參閱 [VPN 存取](http://www.softlayer.com/vpn-access){:new_window}。
*  如果您在使用 vSphere Web Client 部署 OVF（開放式虛擬化格式）檔案時發生問題，請參閱[使用 vSphere Web Client 部署 OVF 檔案](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_deploy_ovf)。

## 相關鏈結
{: #vc_hybrid_viewinginstances-related}

* [訂購 vCenter Server with Hybridity Bundle 實例](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_orderinginstance)
* [新增、檢視及刪除 vCenter Server with Hybridity Bundle 實例的叢集](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_addingviewingclusters)
* [擴充及縮減 vCenter Server with Hybridity Bundle 實例的容量](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_addingremovingservers)
* [刪除 vCenter Server with Hybridity Bundle 實例](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_deletinginstance)
