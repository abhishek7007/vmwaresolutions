---

copyright:

  years:  2016, 2019

lastupdated: "2019-02-15"

---

{:tip: .tip}
{:note: .note}
{:important: .important}

# 訂購 Cloud Foundation 實例
{: #sd_orderinginstance}

若要使用標準運算、儲存空間及網路配置來部署統一軟體定義的資料中心 (SDDC) 平台，請訂購 VMware Cloud Foundation 實例。在起始訂購期間，您也可以新增服務，例如 [Zerto on {{site.data.keyword.cloud}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-addingzertodr)，來進行災難回復。

## 需求
{: #sd_orderinginstance-req}

請確定您已完成下列作業：
*  您已在**設定**頁面上配置 {{site.data.keyword.cloud_notm}} 基礎架構認證。如需相關資訊，請參閱[管理使用者帳戶及設定](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-useraccount)。
*  您已檢閱 [Cloud Foundation 實例的需求及規劃](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_planning)中的需求及考量。

請不要修改在訂購或部署實例期間設定的任何值。這樣做會讓您的實例無法使用。例如，如果公用網路關閉、伺服器和虛擬伺服器實例 (VSI) 在佈建進行中移到 Vyatta 之後，或者 IBM CloudBuilder VSI 停止或遭到刪除。此外，在部署實例之後，請不要變更實例名稱、根網域名稱、子網域標籤或主機名稱字首。{:important}

## 系統設定
{: #sd_orderinginstance-sys-settings}

訂購 Cloud Foundation 實例時，您必須指定下列系統設定。

### 實例名稱
{: #sd_orderinginstance-inst-name}

實例名稱必須滿足下列需求：
* 只容許英數及橫線 (-) 字元。
* 實例名稱的開頭必須是英文字母，而且結尾必須是英數字元。
* 實例名稱的長度上限為 10 個字元。
* 實例名稱在您的帳戶中必須是唯一的。

### 主要或次要
{: #sd_orderinginstance-primary-secondary}

選取要訂購新的主要實例，還是要為現有的主要實例訂購次要實例。

## 授權設定
{: #sd_orderinginstance-licensing-settings}

在實例中，指定下列 VMware 元件的授權選項：  
* vCenter Server 授權 - Standard
* vSphere 授權 - Enterprise Plus
* NSX 授權 - Enterprise
* vSAN 授權：選取 Advanced 或 Enterprise 版本

對於「事業夥伴」使用者，包括 vCenter Server 授權（Standard 版本）、vSphere 授權（Enterprise Plus 版本）、NSX 授權及 vSAN 授權，並可代表您購買。不過，您必須指定 vSAN 授權的版本。

對於非「事業夥伴」使用者，您可以選取**購買隨附**以將 IBM 提供的 VMware 授權用於這些元件，也可以選取**我將提供**並輸入自己的授權碼以「自帶授權 (BYOL)」。

## Bare Metal Server 設定
{: #sd_orderinginstance-bare-metal}

### 資料中心位置
{: #sd_orderinginstance-dc-location}

選取要在其中管理實例的 {{site.data.keyword.CloudDataCent_notm}}。

### Skylake
{: #sd_orderinginstance-skylake}

當您選取 **Skylake** 時，可以根據需求來為 Bare Metal Server 選擇 CPU 與 RAM 組合。

表 1. Skylake {{site.data.keyword.baremetal_short}} 的選項

| CPU 型號選項             |RAM 選項          |
|:------------- |:------------- |
|雙重 Intel Xeon Silver 4110 處理器 / 總計 16 核心，2.1 GHz| 128 GB、192 GB、384 GB、768 GB、1.5 TB |
|雙重 Intel Xeon Gold 5120 處理器 / 總計 28 核心，2.2 GHz| 128 GB、192 GB、384 GB、768 GB、1.5 TB |
|雙重 Intel Xeon Gold 6140 處理器 / 總計 36 核心，2.3 GHz | 128 GB、192 GB、384 GB、768 GB、1.5 TB |

### Broadwell
{: #sd_orderinginstance-broadwell}

當您選取 **Broadwell** 時，可以根據需求來為 Bare Metal Server 選擇 CPU 與 RAM 組合。

表 2. Broadwell {{site.data.keyword.baremetal_short}} 的選項

| CPU 型號選項             |RAM 選項          |
|:------------- |:------------- |
|雙重 Intel Xeon E5-2620 v4 / 總計 16 核心，2.1 GHz |128 GB、256 GB、512 GB、768 GB、1.5 TB |
|雙重 Intel Xeon E5-2650 v4 / 總計 24 核心，2.2 GHz |128 GB、256 GB、512 GB、768 GB、1.5 TB |
|雙重 Intel Xeon E5-2690 v4 / 總計 28 核心，2.6 GHz |128 GB、256 GB、512 GB、768 GB、1.5 TB |
|四重 Intel Xeon E7-4820 v4 / 總計 40 核心，2.0 GHz |128 GB、256 GB、512 GB、1 TB、2 TB、3 TB |
|四重 Intel Xeon E7-4850 v4 / 總計 64 核心，2.1 GHz |128 GB、256 GB、512 GB、1 TB、2 TB、3 TB |

### Bare Metal Server 數目
{: #sd_orderinginstance-bare-metal-number}

Cloud Foundation 實例在起始部署時包含四部 Bare Metal Server。下訂單時，無法變更 Bare Metal Server 數目。

## 儲存空間設定
{: #sd_orderinginstance-storage}

對於 Cloud Foundation 實例，您只能訂購 VMware vSAN 儲存空間。

選取 **Skylake** 或 **Broadwell** Bare Metal Server 配置時，您可以自訂實例的 vSAN 儲存空間。請指定下列 vSAN 設定：
* **vSAN 容量磁碟的磁碟類型及大小**：選取所需容量磁碟的選項。
* **vSAN 容量磁碟數目**：指定您要新增的容量磁碟數目。
* 如果您要新增超過所限制的 8 個容量磁碟，請勾選**高效能 Intel Optane** 方框。這個選項提供 2 個額外容量磁碟機槽來放置共 10 個容量磁碟，並且適用於需要較少延遲且較高 IOPS 傳輸量的工作負載。

  **高效能 Intel Optane** 選項僅適用於 Skylake CPU 型號「雙重 Intel Xeon Gold 5120」及「雙重 Intel Xeon Gold 6140」。
  {:note}

* 檢閱 **vSAN 快取磁碟的磁碟類型**及 **vSAN 快取磁碟數目**值。這些值取決於您是否已勾選**高效能 Intel Optane** 方框。

## 網路介面設定
{: #sd_orderinginstance-network-interface}

訂購 Cloud Foundation 實例時，您必須指定下列網路介面設定。

### 主機名稱字首
{: #sd_orderinginstance-hostname-prefix}

主機名稱字首必須滿足下列需求：
*  只容許英數及橫線 (-) 字元。
*  主機名稱字首的開頭及結尾必須是英數字元。
*  主機名稱字首的長度上限為 10 個字元。

### 子網域標籤
{: #sd_orderinginstance-subdomain-label}

子網域標籤必須滿足下列需求：
*  只容許英數及橫線 (-) 字元。
*  子網域標籤的開頭必須是英文字母，而且結尾必須是英數字元。
*  子網域標籤的長度上限為 10 個字元。
*  子網域標籤在您的帳戶內必須是唯一的。

### 網域名稱
{: #sd_orderinginstance-domain-name}

根網域名稱必須滿足下列需求：
* 網域名稱必須包含兩個以上以句點 (.) 區隔的字串
* 第一個字串的開頭必須是英文字母，而且結尾必須是英數字元。
* 除了最後一個字串以外，所有字串都只能包含英數字元和橫線 (-) 字元。
* 最後一個字串只能包含英文字母。
* 最後一個字串的長度範圍必須在 2 到 24 個字元之間。

主機和 VM（虛擬機器）的 FQDN（完整網域名稱）長度上限為 50 個字元。網域名稱必須在這個長度上限以內。
{:note}

### 網路設定的值格式
{: #sd_orderinginstance-network-settings-value-format}

網域名稱及子網域標籤用來產生實例的使用者名稱及伺服器名稱，如下表所示。

表 3. 使用者名稱、網域名稱及伺服器名稱的值格式

|名稱        |值格式            |
  |:------------- |:------------- |
  |網域名稱    | `<root_domain>` |  
  |完整的 ESXi 伺服器名稱| `<host_prefix><n>.<subdomain_label>.<root_domain>`，其中 `<n>` 是 ESXi 伺服器的序號。長度上限為 50 個字元。|   
  |vCenter Server 登入使用者名稱  | `<user_id>@<root_domain>`（Microsoft Active Directory 使用者）或 `administrator@vsphere.local` |
  |vCenter Server FQDN |`vcenter-1.<subdomain_label>.<root_domain>`。長度上限為 50 個字元。|  
  |SDDC Manager FQDN |`sddcmanager.<subdomain_label>.<root_domain>`。長度上限為 50 個字元。|
  |單一登入 (SSO) 站台名稱| `<subdomain_label>`
  |PSC FQDN |`PSC-<subdomain_label>.<subdomain_label>.<root_domain>`。長度上限為 50 個字元。|  

  SDDC Manager FQDN 不能是可公開解析的。否則，Cloud Foundation 實例配置可能會失敗，且無法回復。請先檢閱[選擇根網域名稱時的考量](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_limitations#considerations-when-choosing-a-root-domain-name-for-cloud-foundation-instances)，再指定網域名稱。

### VLAN
{: #sd_orderinginstance-vlans}

網路設定是根據您選取**訂購新的 VLAN** 或**選取現有的 VLAN** 而定。

您的實例訂單需要一個公用 VLAN 及兩個專用 VLAN。兩個專用 VLAN 成為每部 Bare Metal Server 的主幹。

#### 訂購新的 VLAN
{: #sd_orderinginstance-new-vlans}

選取訂購一個新的公用 VLAN 和兩個新的專用 VLAN。

#### 選取現有的 VLAN
{: #sd_orderinginstance-existing-vlans}

視您選取的 {{site.data.keyword.CloudDataCent_notm}} 而定，可能會提供現有的公用和專用 VLAN。

當您選擇重複使用現有的公用及專用 VLAN 時，請指定 VLAN 及子網路：
  * **公用 VLAN** 適用於公用網路存取。
  * **專用 VLAN** 適用於 {{site.data.keyword.cloud_notm}} 內資料中心與服務之間的連線功能。
  * **次要專用 VLAN** 適用於 VMware 特性（例如 vSAN）。
  * **主要子網路**已指派給實體主機，以進行公用網路存取。
  * **專用主要子網路**已指派給實體主機，以處理管理資料流量。

確保所選取 VLAN 上的防火牆配置未封鎖管理資料流量。確保您選取的所有 VLAN 都在相同的 Pod 中，因為無法在混合 Pod VLAN 上佈建 ESXi 伺服器。{:important}

## 服務
{: #sd_orderinginstance-addon-services}

當您訂購 Cloud Foundation 實例時，也可以訂購附加程式服務。如需可用服務的相關資訊，請參閱 [Cloud Foundation 實例的服務](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_planning#services-for-cloud-foundation-instances)。

## 訂單摘要
{: #sd_orderinginstance-order-summary}

根據您選取的實例及附加程式服務配置，預估成本會立即產生並顯示在右窗格中。按一下右窗格的**定價詳細資料**，以產生提供預估詳細資料的 PDF 文件。

## 訂購 Cloud Foundation 實例的程序
{: #sd_orderinginstance-procedure}

1. 從 {{site.data.keyword.cloud_notm}} 型錄中，按一下左導覽窗格中的 **VMware**，然後按一下**虛擬資料中心**區段中的 **Cloud Foundation**。
2. 在 **VMware Cloud Foundation on IBM Cloud** 頁面上，按一下**建立**。
3. 在 **Cloud Foundation** 頁面上，輸入實例名稱。
4. 選取實例類型：
   * 按一下**主要實例**，以在環境中部署單一實例，或是部署多站台拓蹼中的第一個實例。
   * 按一下**次要實例**，以連接該實例與環境中的現有（主要）實例以獲得高可用性。請完成下列步驟：
     1. 選取您要與次要實例連接的主要實例。
     2. 對於主要實例 2.5 版或更新版本，輸入**主要實例 PSC 的管理者密碼**的值。
     3. 對於主要實例 2.4 版或更早版本，驗證**主要實例 PSC 的管理者密碼**欄位的預先填入值正確無誤。
5. 完成實例元件的授權設定：
   *  若要使用 IBM 提供的授權，請選取**購買隨附**。
   *  若要使用您自己的授權，請選取**我將提供**，然後輸入授權碼。  
6. 完成 Bare Metal Server 設定：
   1. 選取 {{site.data.keyword.CloudDataCent_notm}} 來管理實例。
   2. 選取 Bare Metal Server 配置，然後指定 CPU 型號及 RAM 大小。
7. 完成儲存空間配置。
   1. 指定 vSAN 容量及快取磁碟的磁碟類型，以及磁碟數目。
   2. 如果您想要更多儲存空間，請選取 **Intel Optane 的高效能**勾選框。
8. 完成網路介面設定：
   1. 輸入主機名稱字首、子網域標籤及根網域名稱。對於次要實例，會自動完成網域名稱。
   2. 選取 VLAN 設定：
      * 如果您要訂購新的公用及專用 VLAN，則請按一下**訂購新的 VLAN**。
      * 如果您要重複使用可用的現有公用及專用 VLAN，則請按一下**選取現有的 VLAN**，然後指定 VLAN 及子網路。

9. 按一下對應的服務卡，以選取要部署到實例中的附加程式服務。如果需要配置服務，則請完成服務特定設定，然後按一下蹦現配置視窗中的**新增服務**。如需如何提供服務設定的相關資訊，請參閱對應的訂購服務主題。

10. 在**訂單摘要**窗格上，先驗證實例配置，再下訂單。
    1. 檢閱實例的設定。
    2. 檢閱預估實例成本。按一下**定價詳細資料**以產生 PDF 摘要。若要儲存或列印訂單摘要，請按一下 PDF 視窗右上方的**列印**或**下載**圖示。
    3. 確定要收費的帳戶正確，然後選取**我瞭解將會向下面列出的帳戶收費**勾選框。
    4. 按一下適用於您訂單的條款鏈結。確定您同意這些條款，然後選取**我已閱讀並同意下面列出的協力廠商服務合約**勾選框。
    5. 按一下**佈建**。

## 結果
{: #sd_orderinginstance-results}

實例的部署會自動啟動。您會收到正在處理訂單的確認，並且可以檢視實例詳細資料來檢查部署的狀態。

順利部署實例之後，會在 VMware 虛擬平台上安裝 [Cloud Foundation 實例的技術規格](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_cloudfoundationoverview#technical-specifications-for-cloud-foundation-instances)中所說明的元件。依預設，您所訂購的 ESXi 伺服器會分組為 **SDDC-Cluster**。如果您已訂購附加程式服務，則會在完成訂單之後開始部署服務。

實例已備妥可供使用時，實例的狀態會變更為**備妥使用**，而且您會透過電子郵件收到通知。

當您訂購次要實例時，可能會在您完成次要實例訂單之後重新啟動主要實例（鏈結至次要實例）的 VMware vSphere Web Client。

## 下一步
{: #sd_orderinginstance-next}

檢視及管理您訂購的 Cloud Foundation 實例。

您只能從 {{site.data.keyword.vmwaresolutions_short}} 主控台，而不能從 {{site.data.keyword.slportal}} 或透過主控台以外的任何其他方法，來管理在 {{site.data.keyword.cloud_notm}} 帳戶中建立的 {{site.data.keyword.vmwaresolutions_short}} 元件。如果您在 {{site.data.keyword.vmwaresolutions_short}} 主控台以外變更這些元件，則變更不會與主控台同步。{:important}

**警告：**從 {{site.data.keyword.vmwaresolutions_short}} 主控台以外來管理您在訂購實例時安裝至 {{site.data.keyword.cloud_notm}} 帳戶的任何 {{site.data.keyword.vmwaresolutions_short}} 元件，會使您的環境變得不穩定。這些管理活動包括：

*  新增、修改、退回或移除元件
*  透過新增或移除 ESXi 伺服器來擴充或縮減實例容量
*  關閉元件電源
*  重新啟動服務

   這些活動的例外包括從 {{site.data.keyword.slportal}} 管理共用儲存空間檔案共用。這類活動包括：訂購、刪除（這可能會影響已裝載的資料儲存庫）、授權及裝載共用儲存空間檔案共用。

## 相關鏈結
{: #sd_orderinginstance-related}

* [註冊 {{site.data.keyword.cloud_notm}} 帳戶](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-signing_softlayer_account)
* [檢視 Cloud Foundation 實例](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_viewinginstances)
* [新增、檢視及刪除 Cloud Foundation 實例的叢集](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-adding-and-viewing-clusters-for-cloud-foundation-instances)
* [擴充及縮減 Cloud Foundation 實例的容量](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_addingremovingservers)
* [訂購、檢視及移除 Cloud Foundation 實例的服務](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_addingremovingservices)
* [刪除 Cloud Foundation 實例](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_deletinginstance)
* [關於 BYOL 的常見問題](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-faq_byol)
