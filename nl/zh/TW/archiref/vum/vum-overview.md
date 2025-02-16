---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-25"

subcollection: vmware-solutions


---

# VMware Update Manager 概觀
{: #vum-overview}

VMware Update Manager (VUM) 使用多階段處理程序來升級 vSphere 物件以及套用修補程式或延伸規格。此處理程序會啟用具有最小系統關閉時間的順利更新程序。在我們查看此處理程序之前，必須瞭解下列術語：
* **庫存物件** - vCenter 內的物件，例如虛擬機器、虛擬應用裝置或 vSphere ESXi 主機。
* **基準線** - 基準線包含一個以上修補程式、延伸規格、服務套件、錯誤修正程式或升級的集合，而且可以分類為修補程式、延伸規格或升級基準線。有兩種分類的基準線：「主機」及 VM/VA，而且兩者都有 VMware 預先定義的基準線，「自訂」基準線可以新增為必要項目：
  - 預先定義的主機基準線：
    - 重要主機修補程式
    - 非重要主機修補程式

  - 預先定義的 VM/VA 基準線：
    - VA 升級至最新
    - VM 硬體升級以符合主機
    - VMware Tools 升級以符合主機

* **基準線群組** - 一組非衝突的基準線，其結合不同類型的基準線，並根據將所有基準線都視為整體來掃描及重新修補庫存物件。如果基準線群組同時包含升級及修補程式或延伸規格基準線，則會先執行升級。
* **掃描** - 掃描是根據基準線或基準線群組來評估一或數個「庫存」物件的處理程序。
* **編譯打包** - 編譯打包可確保在補救之前先將修補程式及延伸規格下載至 vSphere ESXi 主機，而且是選用步驟，可將主機處於維護模式的時間減到最少。
* **補救** - 補救是一種處理程序，其中，VUM 會將修補程式、延伸規格及升級套用至一或數個庫存物件。

因此，VUM 處理程序如下：
* 根據基準線或基準線群組，掃描庫存物件或物件群組的法規遵循。
* 檢閱之後，在補救之前，可以選擇性地編譯打包修補程式及延伸規格。

下載升級、主機修補程式、延伸規格及相關 meta 資料是可修改的預先定義自動處理程序。依預設，VUM 會依一般可配置的間隔聯絡 VMware 或協力廠商來源，以收集有關可用升級、修補程式或延伸規格的下列資訊：

* 有關所有 ESXi 5.5 及 ESXi 6.x 修補程式的 meta 資料，不論您的環境中是否有這類版本的主機。
* 有關 ESXi 5.5 及 ESXi 6.x 修補程式的 meta 資料，以及有關來自協力廠商供應商 URL 位址之延伸規格的 meta 資料。
* ESXi 5.5 及 ESXi 6.x 主機的通知、警示及修補程式取消。
* 有關虛擬應用裝置之升級的 meta 資料。

VUM 支援取消執行 ESXi 5.0 或更新版本之主機的修補程式。如果發行的修補程式發生問題或潛在問題，則會取消修補程式。掃描您 VMware vCenter Server on {{site.data.keyword.cloud}} 實例中的主機之後，VUM 會警示您是否已在特定主機上安裝已恢復的修補程式。無法在具有 VUM 的主機上安裝已取消的修補程式。VUM 也會刪除修補程式儲存庫中所有已取消的修補程式。發行修正問題的修補程式之後，VUM 會將新的修補程式下載至其修補程式儲存庫。如果您安裝有問題的修補程式，則 VUM 會通知您已發行修正程式，並提示您套用新的修補程式。

VUM 用戶端介面提供兩個主視圖：
*	管理視圖
*	法規遵循視圖

##	管理視圖
{: #vum-overview-admin-view}

管理視圖的存取方式是導覽至：**首頁** > **Update Manager**，然後選取 Update Manager 實例的 IP 位址。在「管理」視圖中，您可以執行下列作業：
*	配置 Update Manager 設定
*	建立及管理基準線和基準線群組
*	檢視 Update Manager 事件
*	檢閱修補程式儲存庫及可用的虛擬應用裝置升級
*	檢閱及檢查通知
*	匯入 ESXi 映像檔

##	法規遵循視圖
{: #vum-overview-compliance-view}

所選取庫存物件之法規遵循視圖的存取方式是導覽至**主機及叢集**或 **VM 及範本**，然後按一下 **Update Manager** 標籤。在「Update Manager 法規遵循」視圖中，您可以執行下列作業：
*	檢視每個所選取庫存物件的法規遵循及掃描結果
*	連接及分離基準線和基準線群組與選取的庫存物件
*	掃描選取的庫存物件
*	將修補程式或延伸規格編譯打包至主機
*	重新修補選取的庫存物件

## 相關鏈結
{: #vum-overview-related}

* [VMware HCX on {{site.data.keyword.cloud_notm}} 解決方案架構](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcx-archi-intro#hcx-archi-intro)
* [VMware Solutions on {{site.data.keyword.cloud_notm}} Digital Technical Engagement](https://ibm-dte.mybluemix.net/vmware)（示範）
