---

copyright:

  years:  2016, 2019

lastupdated: "2019-05-13"

subcollection: vmware-solutions


---

# 將 2.5 版之前的 NetApp ONTAP Select 實例移轉至 IBM Cloud 帳戶
{: #np_addinstancetousraccount}

{{site.data.keyword.cloud}} 帳戶中部署於 2.5 版及更新版本的 NetApp ONTAP Select 實例會自動新增至您的帳戶，並由 {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM) 管理。

對於已部署在 2.4 版及更早版本的實例，您可以將它們移轉至指定的 {{site.data.keyword.cloud_notm}} 帳戶，以進行啟用 IAM 功能的使用者管理。

## 開始之前
{: #np_addinstancetousraccount-prereq}

請確定您要將實例移轉至的 {{site.data.keyword.cloud_notm}} 帳戶不是僅限 IaaS 帳戶。僅限 IaaS 帳戶是未鏈結至 {{site.data.keyword.cloud_notm}} 帳戶的 {{site.data.keyword.cloud_notm}} 基礎架構 (IBM Cloud) 帳戶。

如需如何將僅限 IaaS 帳戶鏈結至 PaaS 帳戶的相關資訊，請參閱 [Follow these steps to link your IaaS and PaaS accounts](https://www.ibm.com/cloud/blog/follow-steps-link-iaas-paas-accounts){:new_window}。

## 移轉實例的程序
{: #np_addinstancetousraccount-procedure}

1. 從 {{site.data.keyword.vmwaresolutions_short}} 主控台中，按一下左導覽窗格中的**資源**。
2. 從主控台橫幅，按一下您的使用者帳戶圖示，然後按一下**帳戶**欄位，以選取您要將實例移轉至其中的使用者帳戶。
3. 在 **NetApp ONTAP Select 實例**表格上，尋找 2.5 版之前的實例。
4. 在**動作**直欄中，按一下溢位功能表圖示，然後按一下**將實例移轉至帳戶**。
5. 在**將實例移轉至帳戶**視窗中，確認要將實例移轉至其中的帳戶，然後按一下**移轉**。

## 結果
{: #np_addinstancetousraccount-results}

1. 您會收到主控台通知，指出已接受將實例移轉至指定 {{site.data.keyword.cloud_notm}} 帳戶的要求。
2. 當實例移轉完成時，實例會顯示在**資源**頁面上對其移轉實例的帳戶之下。移轉的實例不再顯示於移轉來源的原始帳戶。

## 相關鏈結
{: #np_addinstancetousraccount-related}

* [利用 IAM 管理使用者存取](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-iam#iam)
* [邀請使用者存取服務及資源](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-iamuserinvite)
* [何謂 IBM Cloud IAM](/docs/iam?topic=iam-iamoverview)
