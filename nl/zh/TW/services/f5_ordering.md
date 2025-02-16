---

copyright:

  years:  2016, 2019

lastupdated: "2019-05-09"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# 訂購 F5 on IBM Cloud
{: #f5_ordering}

您可以在訂購包含服務的新實例時，同時訂購 F5 on {{site.data.keyword.cloud}} 服務，或將服務新增至現有實例。

## 為新實例訂購 F5 on IBM Cloud
{: #f5_ordering-new}

您可以使用下列其中一種方法，訂購包含 F5 on {{site.data.keyword.cloud_notm}} 的新實例：
* 當您從 {{site.data.keyword.vmwaresolutions_short}} 主控台訂購新實例時，請選取**服務**區段中的 **F5 on IBM Cloud**。
* 從 {{site.data.keyword.cloud_notm}} 型錄中，選取 **F5 on IBM Cloud**，指定服務設定，然後選取**新增至新實例**。

## 為現有實例訂購 F5 on IBM Cloud
{: #f5_ordering-existing}

您可以使用下列其中一種方法，將 F5 on {{site.data.keyword.cloud_notm}} 服務新增至現有實例：
* 從 {{site.data.keyword.vmwaresolutions_short}} 主控台，檢視您要為其新增服務的實例，按一下左導覽窗格上的**服務**，然後按一下**新增**。
* 從 {{site.data.keyword.cloud_notm}} 型錄中，選取 **F5 on IBM Cloud**，指定服務設定，然後選取**新增至現有實例**。

## 為專用實例訂購 F5 on IBM Cloud
{: #f5_ordering-private}

為未使用公用介面配置的實例訂購 F5 on {{site.data.keyword.cloud_notm}} 時，必須提供 Proxy 伺服器以完成安裝。HTTP Proxy 伺服器必須已配置並透過虛擬遞送及轉遞 (VRF) 提供，才能開始安裝 F5 on {{site.data.keyword.cloud_notm}}。

BigIP Virtual Edition (VE) 端點必須可以啟動其授權，才能正常運行。安裝 BigIP VE 端點後，不再需要使用 Proxy 伺服器。

安裝服務時，如果沒有正常運行的 Proxy 伺服器，那麼無法新增 F5 on {{site.data.keyword.cloud_notm}} 服務。
{:note}

## F5 on IBM Cloud 服務配置
{: #f5_ordering-config}

當您訂購此服務時，請提供下列設定。

### F5 授權啟動連線
{: #f5_ordering-config-license}

選取**公用網路**或**專用網路**來啟動授權。如果目標叢集配置了僅限專用網路介面，則只能使用**專用網路**選項。此選項可決定 F5 虛擬伺服器如何聯絡 F5 授權伺服器，這不會影響工作負載資料平面。

如果您選取**專用網路**，請指定下列設定：
* **Proxy IP 位址**：Proxy 伺服器的 IPv4 位址。
* **Proxy 埠號**：Proxy 伺服器的埠號，通常是 8080 或 3128。

不支援已鑑別的 Proxy。
{:note}

### 名稱 
{: #f5_ordering-config-name}

輸入服務名稱。

### 頻寬上限
{: #f5_ordering-config-bandwidth}

指定 F5 BIG-IP 應用裝置的傳輸量上限。

### 授權模型
{: #f5_ordering-config-license-model}

F5 on {{site.data.keyword.cloud_notm}} 服務的授權模型提供下列選項：
<dl class="dl">
        <dt class="dt dlterm">良好</dt>
        <dd class="dd">此供應項目使用 BIG-IP Local Traffic Manager™ (LTM) VE（作為完整 Proxy 架構運作），以提供智慧型本端資料流量管理、完整 SSL 資料流量可見性，以及分析和性能監視，確保應用程式伺服器隨時可供您的使用者使用。</dd>
        <dt class="dt dlterm">更佳</dt>
        <dd class="dd">此供應項目是根據**良好**選項的優點而建置，並加上 BIG-IP DNS™、BIG-IP Advanced Firewall Manager™ (AFM) 及 BIG-IP Application Acceleration Manager™ (AAM) 模組。它提供廣域資料流量管理服務、應用程式效能最佳化，以及進階網路防火牆和「分散式阻斷式服務 (DDoS)」安全防護功能。</dd>
        <dt class="dt dlterm">最佳</dt>
        <dd class="dd">除了**良好**及**更佳**供應項目之外，BIG-IP Application Security Manager™ (ASM) 還提供 L7 DDoS（開放性 Web 應用程式安全專案 (OWASP) 前 10 大威脅和一般應用程式漏洞）的完整應用程式保護。BIG-IP Access Policy Manager™ (APM) 將位在多雲端環境內任何位置之應用程式的安全且簡化存取權提供給使用者，而此環境包含 SSO（單一登入）及 MFA（多因子鑑別）這類特性。</dd>
</dl>

您無法在安裝服務之後變更授權模型。若要變更授權模型，您必須移除現有服務，然後選擇不同的授權模型來重新安裝服務。
{:important}

## 相關鏈結
{: #f5_ordering-releated}

* [F5 on {{site.data.keyword.cloud_notm}} 概觀](/docs/services/vmwaresolutions/services?topic=vmware-solutions-f5_considerations)
* [管理 F5 on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-managing_f5)
* [訂購、檢視及移除 vCenter Server 實例的服務](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_addingremovingservices)
* [訂購、檢視及移除 vCenter Server with Hybridity Bundle 實例的服務](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_addingremovingservices)
* [與 IBM 支援中心聯絡](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support)
* [常見問題](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-faq)
* [F5 部署手冊](https://www.f5.com/services/resources/deployment-guides){:new_window}
