---

copyright:

  years:  2016, 2019

lastupdated: "2019-05-06"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# IBM Cloud 基础架构帐户需求
{: #slaccountrequirement}

要使用 {{site.data.keyword.vmwaresolutions_full}} 订购实例，您必须具有 {{site.data.keyword.cloud_notm}} 基础架构帐户。在实例中订购的组件的成本将计入到该 {{site.data.keyword.cloud_notm}} 帐户。

## IBM Cloud 基础架构帐户的许可权
{: #slaccountrequirement-permissions}

使用的 {{site.data.keyword.cloud_notm}} 基础架构帐户必须具有特定许可权，才能订购实例中的组件并代表您执行操作。许可权需求适用于要在 {{site.data.keyword.vmwaresolutions_short}} 控制台中订购的所有类型的实例和服务。

授权用户可以在 {{site.data.keyword.slportal}} 中验证和更新 {{site.data.keyword.cloud_notm}} 基础架构帐户的许可权。有关更多信息，请参阅[编辑用户的客户门户网站许可权](/docs/customer-portal?topic=customer-portal-customerportal_accuserprof#cp_editusercpperm){:new_window}。

表 1. {{site.data.keyword.cloud_notm}} 基础架构帐户的必需许可权

|许可权|详细信息|
|:------------------ |:--------------------------------------- |
|添加服务器|以下操作需要此许可权：订购运行 VMware ESXi 的 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}，以及供应要用于实例配置、维护和支持操作的每小时虚拟服务器。|
|取消服务器|需要此许可权来释放并回收运行 VMware ESXi 的 {{site.data.keyword.baremetal_short}}。如果删除实例，那么订购的组件会自动按正确的依赖关系顺序释放。|
|查看虚拟服务器详细信息|需要此许可权来检索服务器供应详细信息，订单验证和自动化配置需要这些详细信息。|
|添加存储器|需要此许可权来为实例订购备份存储器和共享存储器。|
|管理存储器|需要此许可权来管理实例的备份存储器和共享存储器。|
|Hardware Firewall|需要此许可权来编辑或查看实例上安装的 Fortinet on {{site.data.keyword.cloud_notm}} 服务的防火墙日志和设置。|
|使用公用网络端口添加计算|需要此许可权来订购使用公用网络端口的硬件和 VSI（虚拟服务器实例）。|
|添加 IP 地址|需要此许可权来以您的名义订购可移植专用子网范围，这是管理在 vSphere 集群中运行的虚拟机时需要的子网范围。向实例添加更多服务时，会将可移植专用 IP 地址分配给 VMware ESXi 服务器以隔离并分配带宽。|
|添加凭单|需要此许可权来代表您开具服务凭单。可以为以下操作创建凭单：启动复原操作，以及在发现问题时自动启动问题解决过程。|
|编辑凭单|需要此许可权来编辑代表您创建的服务凭单。|
|查看凭单|需要此许可权来监视与实例中的组件相关的服务凭单，以了解 {{site.data.keyword.cloud_notm}} 基础架构供应延迟和问题。|
|查看硬件详细信息|需要此许可权来检索硬件详细信息，订单验证和自动化配置需要这些详细信息。|
|重新引导/控制|删除实例时，需要此许可权才能在硬件取消过程中关闭硬件电源。 |
|查看许可证|需要此许可权来检索和验证实例使用的许可证。|
|查看密码|需要此许可权才能管理订购的 VSI。|
|管理服务器监视|下订单时不需要此许可权，但需要此许可权来检索和验证实例中运行 VMware ESXi 服务器的 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 的监视状态。|

## 启用了服务端点的 VRF
{: #slaccountrequirement-vrf-se}

您的 {{site.data.keyword.cloud_notm}} 基础架构帐户必须是虚拟路由和转发 (VRF) 帐户。如果您的帐户是非 VRF 帐户，那么必须转换为 VRF 帐户。 另外建议您支持 VRF 帐户使用服务端点。

有关更多信息，请参阅：
* [VRF on IBM Cloud 概述](/docs/infrastructure/direct-link?topic=direct-link-overview-of-virtual-routing-and-forwarding-vrf-on-ibm-cloud)
* [支持帐户使用服务端点](/docs/services/service-endpoint?topic=service-endpoint-getting-started#cs_cli_install_steps)

## 相关链接
{: #slaccountrequirement-related}

* [vCenter Server 实例的需求](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_planning)
* [用户帐户和设置](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-useraccount)
* [VRF on IBM Cloud 概述](/docs/infrastructure/direct-link?topic=direct-link-overview-of-virtual-routing-and-forwarding-vrf-on-ibm-cloud)
