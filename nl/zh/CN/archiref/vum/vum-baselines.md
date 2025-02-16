---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-29"

subcollection: vmware-solutions


---

# 创建基线并连接到库存对象
{: #vum-baselines}

基线包含由一个或多个补丁、扩展、Service Pack、错误修订或升级构成的集合，可以分类为补丁、扩展或升级基线。基线组基于现有基线组合而成。主机基线组可以具有单个升级基线以及各种补丁和扩展基线。虚拟机和虚拟设备基线组最多可具有三个升级基线：一个 VMware Tools 升级基线、一个虚拟机硬件升级基线和一个虚拟设备升级基线。

VMware Update Manager (VUM) 包含预定义的基线，您无法编辑或删除这些基线。您可以使用预定义的基线，也可以创建满足您条件的补丁、扩展和升级基线。可以在基线组中组合使用您创建的定制基线和预定义的基线。

VUM 包含缺省基线，您可以使用这些基线来扫描以下任何设备，以确定环境中的主机是否已使用最新补丁更新，或者是否虚拟设备和虚拟机已升级到最新版本：
* 任何虚拟机
* 任何虚拟设备
* 任何主机

预定义基线如下：
* **关键主机补丁（预定义）** - 检查 ESXi 主机是否与所有关键补丁一致。
* **非关键主机补丁（预定义）** - 检查 ESXi 主机是否与所有可选补丁一致。
* **VMware Tools 升级以匹配主机（预定义）** - 检查虚拟机是否与主机上的最新 VMware Tools 版本一致。Update Manager 支持升级运行 ESXi 5.5.x 和更高版本的主机上虚拟机的 VMware Tools。
* **VM 硬件升级以匹配主机（预定义）** - 检查虚拟机的虚拟硬件是否与主机支持的最新版本一致。Update Manager 支持在运行 ESXi 6.5 的主机上升级到虚拟硬件版本 vmx-13。
* **VA 升级到最新版本（预定义）** - 检查虚拟设备是否与最新发布的虚拟设备版本一致。

要使用基线和基线组，必须将其连接到所选库存对象（例如，容器对象、虚拟机、虚拟设备或主机）。尽管您可以将基线和基线组连接到单个对象，但更高效的方法是将其连接到容器对象（例如，文件夹、vApp、集群或数据中心）。在此步骤中，我们将对集群中的主机使用预定义的基线。

1. 使用 vSphere Web Client，转至**主页** > **主机和集群**。
2. 单击要扫描的集群对象。
3. 转至 VUM，单击**连接基线**，然后选择两个预定义的补丁基线。单击**确定**。

## 相关链接
{: #vum-baselines-related}

* [VMware HCX on {{site.data.keyword.cloud_notm}} 解决方案体系结构](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcx-archi-intro#hcx-archi-intro)
* [VMware Solutions on {{site.data.keyword.cloud_notm}} 数字技术互动](https://ibm-dte.mybluemix.net/vmware)（演示）
