---

copyright:

  years:  2016, 2019

lastupdated: "2019-05-01"

subcollection: vmware-solutions


---

# 订购 IBM Cloud Private Hosted
{: #icp_ordering}

订购 {{site.data.keyword.cloud}} Private Hosted 服务时，可订购包含此服务的新实例，也可通过向现有实例添加此服务来进行订购。

## 为新实例订购 IBM Cloud Private Hosted
{: #icp_ordering-new}

可以使用下列其中一种方法订购包含 {{site.data.keyword.cloud_notm}} Private Hosted 服务的新实例：
* 在 {{site.data.keyword.vmwaresolutions_short}} 控制台中，订购新实例时，请在**可选服务**部分中选择 **IBM Cloud Private Hosted**。
* 在 {{site.data.keyword.cloud_notm}}“目录”中，选择 **IBM Cloud Private Hosted**，指定服务设置，然后选择**添加到新实例**。

## 为现有实例订购 IBM Cloud Private Hosted
{: #icp_ordering-existing}

可以使用下列其中一种方法将 {{site.data.keyword.cloud_notm}} Private Hosted 服务添加到现有实例中：
* 在 {{site.data.keyword.vmwaresolutions_short}} 控制台中，查看要为其添加服务的实例，单击左侧导航窗格上的**服务**，然后单击**添加**。
* 在 {{site.data.keyword.cloud_notm}}“目录”中，选择 **IBM Cloud Private Hosted**，指定服务设置，然后选择**添加到现有实例**。

## IBM Cloud Private Hosted 服务配置
{: #icp_ordering-config}

订购此服务时，请提供以下设置：
* 根据需要选择**生产就绪**或**开发/测试**。
* 选中必需的复选框以证明您已获得部署 {{site.data.keyword.cloud_notm}} Private Hosted 服务所需的许可证。

## 部署更多节点
{: #icp_ordering-deploy-nodes}

如果要部署更多节点，请查看以下信息：
* 使用随初始 {{site.data.keyword.cloud_notm}} Private Hosted 安装一起部署的 {{site.data.keyword.cloud_notm}} Private Ubuntu 模板 (Ubuntu 1604)。
* 要查找 Ubuntu 模板，请在 VMware vSphere Web Client 中，转至 `cam` 文件夹下的 **VM 和模板**选项卡。
* Ubuntu 模板的缺省密码为 `icponcloud`。建议您在使用该模板之前更改该密码。
* {{site.data.keyword.vmwaresolutions_short}} 不支持应用 Ubuntu 模板的更新和补丁。您必须自行监视并应用这些更新。


## 相关链接
{: #icp_ordering-related}

* [IBM Cloud Private Hosted 概述](/docs/services/vmwaresolutions/services?topic=vmware-solutions-icp_overview)
* [订购、查看和除去 vCenter Server 实例的服务](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_addingremovingservices)
* [订购、查看和除去 vCenter Server with Hybridity Bundle 实例的服务](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_addingremovingservices)
* [联系 IBM 支持人员](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support)
* [常见问题](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-faq)
