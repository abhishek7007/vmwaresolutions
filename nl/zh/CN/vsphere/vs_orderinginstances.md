---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-26"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# 订购新的 vSphere 集群
{: #vs_orderinginstances}

要部署高度可定制的 VMware 虚拟化平台，请订购 VMware vSphere on {{site.data.keyword.cloud}} 集群。使用此过程可定义新的 vSphere 集群。

此过程将引导您选择 VMware 组件、{{site.data.keyword.cloud_notm}} 裸机服务器设置、存储设置和联网选项，以创建新集群。下订单后，系统将捕获集群配置，以便您可以返回并继续根据需要向外扩展集群。完成订单后，可以根据需求手动配置 VMware 集群。

## 需求
{: #vs_orderinginstances-req}

确保已完成以下任务：
*  已在**设置**页面上配置 {{site.data.keyword.cloud_notm}} 基础架构凭证。有关更多信息，请参阅[管理用户帐户和设置](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-useraccount)。
*  已查看[针对 vSphere 集群的需求和规划](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_planning)中的需求和注意事项。

## 系统设置
{: #vs_orderinginstances-sys-settings}

订购新的 vSphere 集群时，必须指定以下系统设置。

### 集群名称
{: #vs_orderinginstances-cluster-name}

集群名称在您的帐户中必须唯一。

## 许可证设置
{: #vs_orderinginstances-licensing-settings}

选择要随集群一起订购的 VMware 组件，并指定组件的许可选项。

### 针对 IBM 业务合作伙伴用户的组件捆绑软件
{: #vs_orderinginstances-component-bundles-for-bp-users}

如果您是 IBM 业务合作伙伴用户，那么可以在订购新的 vSphere 集群时选择组件许可证捆绑软件。以下捆绑软件可用：

表 1. 用于 vSphere 集群的 IBM 业务合作伙伴组件捆绑软件

|捆绑软件|组件|
|:------------------------- |:----------------------- |
|标准（带管理）|vSphere Enterprise Plus、vCenter Server Standard、vRealize Log Insight 和 vRealize Operations Enterprise|
|高级|vSphere Enterprise Plus、vCenter Server Standard、vRealize Log Insight、vCloud Director 和 NSX Base|
|高级（带联网）|vSphere Enterprise Plus、vCenter Server Standard、vRealize Log Insight 和 NSX Advanced|
|高级（带联网和管理）|vSphere Enterprise Plus、vCenter Server Standard、vRealize Log Insight、vRealize Operations Enterprise、vCloud Director 和 NSX Enterprise|

您还可以在订单中包含以下 VMware 组件：
* VMware vSAN
* VMware Site Recovery Manager
* VMware vRealize Automation Enterprise

对于 IBM 业务合作伙伴用户，自带许可证 (BYOL) 选项不可用。
{:note}

### 针对非业务合作伙伴用户的单独组件
{: #vs_orderinginstances-individual-components-for-non-bp-users}

如果您是非业务合作伙伴，那么可以为 vSphere 集群选择以下组件：
* VMware vSphere Enterprise Plus 6.7 U1 或 6.5 U2
* VMware vCenter Server
* VMware NSX
* VMware vSAN
* VMware Site Recovery Manager
* VMware vRealize Automation Enterprise
* VMware vRealize Operation Enterprise
* VMware vRealize Log Insight

订购 VMware vSphere Enterprise Plus 6.0 时，VMware vSAN 组件不可用。如果计划使用您自己的 VMware vSphere Enterprise Plus 6.0 许可证，那么系统将代表您开具 {{site.data.keyword.cloud_notm}} 基础架构凭单。凭单会请求用您提供的许可证替换已订购的 {{site.data.keyword.baremetal_short}} 的 vSphere 许可证。
{:note}

### 许可选项
{: #vs_orderinginstances-licensing-options}

可以选择以下选项来对所选 VMware 组件进行许可：
* **购买时包含许可证**：选择此项时，系统将以您的名义为 VMware 组件购买新许可证。将生成组合 VMware 许可证以匹配订单的集群大小。
* **我将提供许可证**：在这种情况下，将对 VMware 组件使用您自己的许可证。

如果选择购买任何许可证（vSphere Enterprise Plus 和 vCenter Server 除外），并且订购了多个 ESXi 服务器，那么系统会自动代表您开具 {{site.data.keyword.cloud_notm}} 凭单以组合许可证密钥。您负责跟踪凭单以确保仅使用 DevOps 团队生成的许可证密钥。

将单独的许可证密钥与组合的许可证密钥配合使用，不符合您所需许可证的付款需求。
{:important}

## 裸机服务器设置
{: #vs_orderinginstances-bare-metal-settings}

### 数据中心位置
{: #vs_orderinginstances-dc-location}

选择要托管集群的 {{site.data.keyword.CloudDataCent_notm}}。

**注：**
* 如果选择的是 vSAN 组件，那么位置列表将按 SSD 可用性进行过滤。

* Broadwell 裸机服务器不可用于 **FRA05 - 法兰克福**数据中心位置。
* SAP 认证的裸机服务器和 Broadwell 裸机服务器不可用于 **LON05 - 伦敦**数据中心位置。

### Skylake
{: #vs_orderinginstances-skylake}

选择 **Skylake** 时，可以根据需要为裸机服务器选择 CPU 和 RAM 组合。可用的选项取决于是否选择了 VMware vSAN 组件。

表 2. Skylake {{site.data.keyword.baremetal_short}} 的选项

| CPU 模型选项   |RAM 选项|
|:------------- |:------------- |
|双 Intel Xeon Silver 4110 处理器 / 共 16 个核心，2.1 GHz|64 GB、96 GB、128 GB、192 GB、384 GB、768 GB、1.5 TB|
|双 Intel Xeon Gold 5120 处理器 / 共 28 个核心，2.2 GHz|64 GB、96 GB、128 GB、192 GB、384 GB、768 GB、1.5 TB|
|双 Intel Xeon Gold 6140 处理器 / 共 36 个核心，2.3 GHz|64 GB、96 GB、128 GB、192 GB、384 GB、768 GB、1.5 TB|

### SAP 认证
{: #vs_orderinginstances-sap}

如果先前选择的是 VMware vSAN，那么 **SAP 认证**选项卡不可用。选择 **SAP 认证**后，无法变更 CPU 或 RAM 设置。

根据需求，选择裸机服务器配置：
  * 双 Intel Xeon Gold 6140 处理器 / 共 36 个核心，2.3 GHz / 192 GB RAM
  * 双 Intel Xeon Gold 6140 处理器 / 共 36 个核心，2.3 GHz / 384 GB RAM
  * 双 Intel Xeon Gold 6140 处理器 / 共 36 个核心，2.3 GHz / 768 GB RAM
  * 双 Intel Xeon E5-2690 V4 处理器 / 共 28 个核心，2.6 GHz / 512 GB RAM
  * 四核 Intel Xeon E7-8890 V4 处理器 / 共 96 个核心，2.2 GHz / 1024 GB RAM
  * 四核 Intel Xeon E7-8890 V4 处理器 / 共 96 个核心，2.2 GHz / 2048 GB RAM
  * 四核 Intel Xeon E7-8890 V4 处理器 / 共 96 个核心，2.2 GHz / 4096 GB RAM

### Broadwell
{: #vs_orderinginstances-broadwell}

选择 **Broadwell** 时，可以根据需要为裸机服务器选择 CPU 和 RAM 组合。可用的选项取决于是否选择了 VMware vSAN 组件。

表 3. Broadwell {{site.data.keyword.baremetal_short}} 的选项

| CPU 模型选项   |RAM 选项|
|:------------- |:------------- |
|四核 Intel Xeon E7-4820 V4 / 共 40 个核心，2.0 GHz|128 GB、256 GB、512 GB、1 TB、2 TB、3 TB|
|四核 Intel Xeon E7-4850 V4 / 共 64 个核心，2.1 GHz|128 GB、256 GB、512 GB、1 TB、2 TB、3 TB|

### 裸机服务器的数量
{: #vs_orderinginstances-bare-metal-number}

要添加到 vSphere 集群的 ESXi 服务器数。所有 ESXi 服务器的配置都相同。
* 如果选择了 VMware NSX 组件，那么至少需要三个服务器。
* 如果选择了 VMware vSAN 组件，那么至少需要四个服务器。

## 存储设置
{: #vs_orderinginstances-storage-settings}

对于不包含 vSAN 的订单，将随 ESXi 服务器一起订购一个可容纳 12 个磁盘的机箱，其中两个磁盘用于 ESXi 操作系统 (OS)。

对于包含 vSAN 的订单，将随 ESXi 服务器一起订购一个可容纳 12 个磁盘的机箱并订购 4 个磁盘：其中两个磁盘用于 ESXi OS，另外两个磁盘保留用于高速缓存。这些设置是缺省配置的，不能进行更改。可以通过选择 **vSAN 容量磁盘的磁盘类型和大小**以及 **vSAN 容量磁盘数**来订购更多容量磁盘。

如果为集群选择了 VMware vSAN 组件，请指定以下设置。
* **vSAN 容量磁盘的磁盘类型和大小**：选择与所需容量磁盘相应的选项。
* **vSAN 容量磁盘数**：指定要添加的容量磁盘数。
* 如果要添加的容量磁盘数超过 8 个的限制，请选中**高性能 Intel Optane** 框。此选项用于提供两个额外的容量磁盘托架，总共可容纳 10 个容量磁盘；此选项对于需要更短等待时间和更高 IOPS 吞吐量的工作负载而言非常有用。

  **高性能 Intel Optane** 选项仅可用于 Skylake CPU 型号。
{:note}

* 查看 **vSAN 高速缓存磁盘的磁盘类型**和 **vSAN 高速缓存磁盘数**值。这些值依赖于是否选中了**高性能 Intel Optane** 框。

## 网络接口设置
{: #vs_orderinginstances-network-interface-settings}

订购新的 vSphere 集群时，必须指定以下网络接口设置。

### 主机名前缀
{: #vs_orderinginstances-host-name-prefix}

主机名用于所有裸机服务器订单。建议将主机名用于所有管理虚拟机，例如 vCenter Server 和 NSX。

主机名前缀必须满足以下需求：
* 名称必须以字母数字字符开头和结尾。
* 只允许使用字母数字字符和短划线 (-) 字符。
* 最大长度为 10 个字符。

### 子域标签
{: #vs_orderinginstances-subdomain-label}

子域标签必须满足以下需求：
*  只允许使用字母数字字符和短划线 (-) 字符。
*  子域标签必须以字母数字字符开头和结尾。
*  子域标签的最大长度为 10 个字符。
*  子域标签在您的帐户中必须唯一。

### 域名
{: #vs_orderinginstances-domain-name}

域名用于所有 {{site.data.keyword.baremetal_short}} 且必须满足以下需求：
* 名称必须包含两个或更多用句点 (.) 分隔的字符串。
* 只允许使用字母数字字符和短划线 (-) 字符。
* 每个字符串必须以字母字符开头并以字母数字字符结尾，并且最后一个字符串只能包含字母字符。
* 最后一个字符串的长度必须在 2 到 24 个字符范围内。
* 其他字符串的长度必须在 1 到 63 个字符范围内。
* 域名的最大长度为 189 个字符。

### 公用或专用网络
{: #vs_orderinginstances-public-private-network}

网络接口卡 (NIC) 启用设置基于您选择的是**公用和专用网络**还是**仅专用网络**。

### VLAN
{: #vs_orderinginstances-vlans}

网络设置基于您选择的是**订购新 VLAN** 还是**选择现有 VLAN**。

订购集群时，需要包含一个公用 VLAN 和两个专用 VLAN。两个专用 VLAN 用于中继到每个裸机服务器中。

#### 订购新的 VLAN
{: #vs_orderinginstances-new-vlans}

选择此项可订购一个新的公用 VLAN 和两个新的专用 VLAN。

#### 选择现有 VLAN
{: #vs_orderinginstances-existing-vlans}

根据选择的 {{site.data.keyword.CloudDataCent_notm}}，可能会有现有公用和专用 VLAN 可用。

  选择复用现有公用和专用 VLAN 时，请指定 VLAN 和子网：
  * **公用 VLAN** 用于公用网络访问。
  * **专用 VLAN** 用于连接 {{site.data.keyword.cloud_notm}} 中的各数据中心和服务。
  * **辅助专用 VLAN** 用于 VMware 功能部件，例如 vSAN。
  * **主子网**分配给物理主机以用于公用网络访问。
  * **主专用子网**分配给物理主机以用于管理流量。

**重要信息：**
* 确保所选 VLAN 上的防火墙配置不会阻止管理数据流量。
* 确保您选择的所有 VLAN 都在相同的 pod 上。在混合 pod VLAN 上无法供应 ESXi 服务器。

#### FortiGate Physical Appliance 300 序列 HA 对
{: #vs_orderinginstances-fortigate-physical-appliance}

您还可以选择是否包含 FortiGate Physical Appliance 300 系列 HA 对以确保云环境安全。有关更多信息，请参阅 [FortiGate Security Appliance on {{site.data.keyword.cloud_notm}} 概述](/docs/services/vmwaresolutions/services?topic=vmware-solutions-fsa_considerations)。

## 订单摘要
{: #vs_orderinginstances-order-summary}

根据配置，估算成本会立即生成并显示在右侧的**订单摘要**窗格中。单击**定价详细信息**以生成提供估算详细信息的 PDF 文档。

## 订购 vSphere 集群的过程
{: #vs_orderinginstances-procedure}

1. 在 {{site.data.keyword.cloud_notm}}“目录”中，单击左侧导航窗格上的 **VMware**，然后单击**虚拟数据中心**部分中的 **VMware vSphere**。
2. 在 **VMware vSphere on IBM Cloud** 页面上，单击**创建**。  
   确保位于**新建**选项卡上，并且**集群配置**列表中显示了**新集群**。
3. 输入集群名称。
4. 选择 VMware 组件：
  * 如果您是 IBM 业务合作伙伴，请选择许可证捆绑软件和其他任何可用的 VMware 组件。
  * 如果您是非业务合作伙伴，请选择组件、版本（如果有），并指定许可选项。选择对 VMware vSphere Enterprise Plus 使用自带许可证 (BYOL) 时，系统将代表您自动开具 {{site.data.keyword.cloud_notm}} 凭单，以请求将所订购 {{site.data.keyword.baremetal_short}} 的缺省 vSphere 许可证替换为您提供的许可证。   

    **重要信息**：您负责跟踪凭单以确保替换新订购的 ESXi 服务器上的 vSphere 许可证。这样 {{site.data.keyword.cloud_notm}} 基础架构就会授权取消对初始提供的 {{site.data.keyword.cloud_notm}} 基础架构 vSphere 许可证收费。要替换 ESXi vSphere 许可证，请参阅[为 ESXi 主机配置许可证设置](https://docs.vmware.com/en/VMware-vSphere/6.0/com.vmware.vsphere.vcenterhost.doc/GUID-1B128360-0060-40F2-A6F0-43CD2534B034.html){:new_window}。
5. 完成裸机服务器设置：
   1. 选择要托管集群的 {{site.data.keyword.CloudDataCent_notm}}。
   2. 选择裸机服务器配置。
      * 选择 **Skylake** 或 **Broadwell** 时，请指定 CPU 型号和 RAM 大小。
      * 选择的是 **SAP 认证**时，请选择其中一个预设配置。
   3. 指定裸机服务器数。
6. 如果选择的是 **VMware vSAN** 组件，请完成 vSAN 存储配置。指定容量和高速缓存磁盘的磁盘类型以及磁盘数。如果需要更多存储器，请选中**高性能 Intel Optane** 框。
7. 完成网络接口设置：
   1. 输入主机名前缀、子域标签和域名。
   2. 选择网络设置**公用和专用网络**或**仅专用网络**。
   3. 选择要使用的网络接口。
    * 如果要订购新的公用和专用 VLAN，请单击**订购新的 VLAN**。
    * 如果要复用可用的现有公用和专用 VLAN，请单击**选择现有 VLAN**，然后指定 VLAN 和（可选）子网。
    4. 指定是否应用 FortiGate Physical Appliance 300 系列 HA 对以确保云环境安全。  
8. 在**订单摘要**窗格中，验证集群配置和估算成本。
   * 要将配置另存为模板而不下订单，请单击**保存配置**。
   * 要下订单，请确保要向其收费的帐户正确，复查并接受条款，然后单击**供应**。

   这将仅安装 {{site.data.keyword.baremetal_short}}。您负责在集群部署后安装和配置各种组件（例如，VMware vCenter、VMware NSX 和 VMware vSAN）。
   {:note}

### 结果
{: #vs_orderinginstances-results}

如果已将集群配置另存为模板，那么会收到控制台通知，指示配置已成功保存，然后您可以在**集群配置**列表中找到该模板。

如果已下订单，那么集群的部署将自动启动，并且您将收到电子邮件确认，指示正在处理订单。集群准备就绪可供使用时，将通过电子邮件通知您。

与 vCenter Server 实例不同，vSphere 集群不会显示在**资源**页面上。
{:note}

## 相关链接
{: #vs_orderinginstances-related}

* [基于现有配置订购 vSphere 集群](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_orderingbasedonexistingconfig)
* [缩放现有集群](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_scalingexistingclusters)
* [缩放在控制台外部创建的集群](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_orderingforclustersoutside)
