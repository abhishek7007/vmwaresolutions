---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-09"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# 訂購 Zerto on IBM Cloud
{: #zerto_ordering}

您可以在訂購包含服務的新實例時，同時訂購 Zerto on {{site.data.keyword.cloud}} 服務，或將服務新增至現有實例。

## 為新實例訂購 Zerto on IBM Cloud
{: #zerto_ordering-new}

您可以使用下列其中一種方法，訂購包含 Zerto on {{site.data.keyword.cloud_notm}} 的新實例：
* 當您從 {{site.data.keyword.vmwaresolutions_short}} 主控台訂購新實例時，請選取**服務**區段中的 **Zerto on IBM Cloud**。
* 從 {{site.data.keyword.cloud_notm}} 型錄中，選取 **Zerto on IBM Cloud**，指定服務設定，然後選取**新增至新實例**。

## 為現有實例訂購 Zerto on IBM Cloud
{: #zerto_ordering-existing}

您可以使用下列其中一種方法，將 Zerto on {{site.data.keyword.cloud_notm}} 服務新增至現有實例：
* 從 {{site.data.keyword.vmwaresolutions_short}} 主控台，檢視您要為其新增服務的實例，按一下左導覽窗格上的**服務**，然後按一下**新增**。
* 從 {{site.data.keyword.cloud_notm}} 型錄中，選取 **Zerto on IBM Cloud**，指定服務設定，然後選取**新增至現有實例**。

如果您將 Zerto for {{site.data.keyword.cloud_notm}} 新增至具有處於維護模式的 ESXi 伺服器的 vCenter Server 實例，您必須使用 Zerto Virtual Manager (ZVM) 主控台及預先移入的 Zerto Virtual Replication Appliance (VRA) IP 位址來手動部署 VRA 虛擬機器 (VM)。
{:note}

## 為僅限專用實例訂購 Zerto on IBM Cloud
{: #zerto_ordering-private-only}

如果您要將 Zerto on {{site.data.keyword.cloud_notm}} 新增至僅限專用實例，請確保符合下列需求：
* 您負責設定您自己的 Proxy 伺服器來連接至網際網路。如需相關資訊，請參閱[公用網路連線功能](/docs/services/vmwaresolutions/services?topic=vmware-solutions-design_virtualinfrastructure#public-network-connectivity)。
* 您還必須配置 Zerto 的 Call Home 特性。如需 Zats Call Home 的相關資訊，請參閱 [Zerto Reporting for Enterprise environments (Call Home)](https://www.zerto.com/myzerto/knowledge-base/zerto-reporting-for-enterprise-environments-call-home/){:new_window}。

## 相關鏈結
{: #zerto_ordering-related}

* [Zerto on {{site.data.keyword.cloud_notm}} 概觀](/docs/services/vmwaresolutions/services?topic=vmware-solutions-addingzertodr)
* [管理 Zerto on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-managingzertodr)
* [要求 Zerto on {{site.data.keyword.cloud_notm}} 的受管理服務](/docs/services/vmwaresolutions/services?topic=vmware-solutions-managing_zerto_services)
* [zerto.com 網站](https://www.zerto.com){:new_window}
* [Zerto 技術文件](https://www.zerto.com/myzerto/technical-documentation/){:new_window}
