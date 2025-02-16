---

copyright:

  years:  2016, 2019

lastupdated: "2019-03-13"

subcollection: vmwaresolutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Cloud Foundation 實例的多站台配置
{: #sd_multisite}

{{site.data.keyword.vmwaresolutions_full}} 容許在不同的位置部署實例，並在短時間內啟動並執行它們。

##  附註 
{: #sd_multisite-notes}

* 您無法在多站台配置中鏈結 VMware Cloud Foundation 與 VMware vCenter Server 實例。
* 您無法鏈結 2.0 版中所部署的實例與舊版本中的實例（即使已升級至 2.0 版也是一樣）。

## 多站台部署元件
{: #sd_multisite-deployment-components}

多站台部署包含下列元件。

* **主要實例**：主要 VMware Cloud Foundation 實例具有下列配置：
  *  Microsoft Active Directory (AD) 及 DNS（網域名稱系統）根網域
  *  Cloud Foundation 子網域
  *  SSO（單一登入）網域
  *  SSO 站台名稱
* **一個以上的次要實例**：具有下列配置的一個以上的次要 Cloud Foundation 實例（已鏈結至主要實例）：
   *  SSO 站台名稱
   *  鏈結至主要實例上之根網域的 DNS 子網域
   *  在主要及次要實例上的 AD 虛擬機器之間設定 DNS 及 AD 抄寫
   *  已部署並配置為向主要實例上的 PSC (Platform Services Controller) 抄寫的 PSC
   *  使用「加強型鏈結模式」將次要實例上的 VMware vCenter 設定為主要實例上的 vCenter

## Cloud Foundation 多站台部署
{: #sd_multisite-deployment}

多站台配置特性會搭配使用中心及分支拓蹼與主要站台及最多七個次要站台。支援單層站台，亦即，您無法配置鏈結至其他次要站台的後續站台。在所有實例中，您在多站台配置中共有 128 部 ESXi 伺服器。

如果您的配置需要超過 128 部 ESXi 伺服器的多站台部署，請與「IBM 支援中心」聯絡以取得協助。如需相關資訊，請參閱[與 IBM 支援中心聯絡](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support)。
{:note}

下圖說明 Cloud Foundation 多站台部署的整體視圖。

圖 1. Cloud Foundation 多站台部署

![Cloud Foundation 多站台部署](../vcenter/multisite-hub-spoke.svg "Cloud Foundation 多站台部署")

此模型包含下列各層：

* **主要實例**：在多網站配置中，第一個實例已在實例訂購程序期間定義為主要實例。
* **次要實例**：在多網站配置中，附加至主要實例的實例已在訂購程序期間定義為次要實例。

您最多可以在多站台配置中部署 8 個（1 個主要及 7 個次要）實例。

刪除屬於多站台配置的 Cloud Foundation 實例需要特殊規劃。如需相關資訊，請參閱[刪除多站台配置中的 Cloud Foundation 實例](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_deletinginstance_multi)。
{:note}

## 相關鏈結
{: #sd_multisite-related}

* [Assign Primary Role to NSX Manager](https://pubs.vmware.com/NSX-62/topic/com.vmware.nsx-cross-vcenter-install.doc/GUID-44E8AE16-BA3F-4DD9-B582-FC1E137E6CFC.html){:new_window}
* [Configuring Secondary NSX Managers](https://pubs.vmware.com/NSX-62/topic/com.vmware.nsx-cross-vcenter-install.doc/GUID-9E48BC57-15E3-49C7-8BC5-F94ED8918BBE.html){:new_window}
* [Active Directory Trusts supported with VMware vCenter Single Sign-On](https://kb.vmware.com/kb/2064250){:new_window}
* [Securely connect your private VMware workloads in the {{site.data.keyword.cloud_notm}}](https://www.ibm.com/developerworks/library/se-securely-connect-private-vmware-workloads-ibm-cloud/index.html){:new_window}
