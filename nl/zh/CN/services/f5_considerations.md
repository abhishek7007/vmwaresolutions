---

copyright:

  years:  2016, 2019

lastupdated: "2019-05-01"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# F5 on IBM Cloud 概述
{: #f5_considerations}

F5 on {{site.data.keyword.cloud}} 服务 (F5 BIG-IP® Virtual Edition) 用于提供本地和全球规模的智能 L4-L7 负载均衡和流量管理服务、稳健的网络和 Web 应用程序防火墙保护，以及安全和联合的应用程序访问。

可以根据需要安装此服务的多个实例。

此服务仅可用于在 V1.9 或更高发行版中部署的实例。当前安装的 BIG-IP VE 版本为 v14.1.0.2。
{:note}

## F5 on IBM Cloud 的技术规范
{: #f5_considerations-specs}

F5 on {{site.data.keyword.cloud_notm}} 服务随附以下组件：

### 虚拟机
{: #f5_considerations-specs-vms}

* 提供了所有选项的两个虚拟机 (VM)。
* 每个虚拟机 2、4 或 8 个 vCPU，具体取决于许可选项。
* 每个虚拟机 4、8 或 16 GB RAM，具体取决于许可选项。

### 联网
{: #f5_considerations-specs-network}

* 用于高可用性 (HA) 同步的专用虚拟可扩展 LAN (VXLAN)。
* 通过专用管理网络访问流量管理 Shell (TMSH) 和管理控制台。

### 许可证和费用
{: #f5_considerations-specs-license}

每个 VM 的许可费用将应用于每个计费周期，具体取决于许可选项（“良好”、“更佳”或“最佳”）和所选带宽。

服务安装后即无法更改许可级别。要更改许可级别，必须除去现有服务，然后使用其他许可选项来重新安装该服务。
{:important}

## F5 on IBM Cloud 的安装注意事项
{: #f5_considerations-install}

安装 F5 on {{site.data.keyword.cloud_notm}} 服务之前，请查看以下注意事项。

基于选择的许可模型和带宽，将使用以下配置部署两个 BIG-IP VE VM（虚拟机）：

表 1. 不同带宽和许可模型选择的 CPU 和 RAM 部署

|最大带宽|许可模型：良好|许可模型：更佳|许可模型：最佳|
|:------------------|:--------------------|:----------------------|:--------------------|
|25 Mbps|2 个 vCPU，4 GB RAM|4 个 vCPU，8 GB RAM|8 个 vCPU，16 GB RAM|
|200 Mbps|2 个 vCPU，4 GB RAM|4 个 vCPU，8 GB RAM|8 个 vCPU，16 GB RAM|
|1 Gbps|2 个 vCPU，4 GB RAM|4 个 vCPU，8 GB RAM|8 个 vCPU，16 GB RAM|
|3 Gbps|8 个 vCPU，16 GB RAM|8 个 vCPU，16 GB RAM|8 个 vCPU，16 GB RAM|
|5 Gbps|8 个 vCPU，16 GB RAM|8 个 vCPU，16 GB RAM|8 个 vCPU，16 GB RAM|
|10 Gbps|8 个 vCPU，16 GB RAM|8 个 vCPU，16 GB RAM|8 个 vCPU，16 GB RAM|

### 其他注意事项
{: #f5_considerations-additional}

* F5 BIG-IP 根据选择的最大带宽来限制设备吞吐量。由于网络性能受许多因素的影响，因此并非所有配置和拓扑都能达到所选的最大带宽。
* BIG-IP VE VM 的 HA（高可用性）对将仅部署到缺省集群中。

  此外，还为这两个 BIG-IP VE VM 保留了 100% 的 CPU 和 RAM，因为这两个 VM 位于网络通信的数据平面中，并且资源仍然可用对这两个 VM 而言至关重要。

  要计算单个 BIG-IP VE VM 的 CPU 和 RAM 保留量，请使用以下公式：

  `CPU 保留量 = ESXi 服务器的 CPU 速度 * vCPU 数`（取自表 1）

  `RAM 保留量 = RAM 大小`（取自表 1）

### 规划注意事项
{: #f5_considerations-planning}

必须满足以下需求，以避免 F5 on {{site.data.keyword.cloud_notm}} 上发生故障：
* 至少有两个活动 ESXi 服务器可用，以使用可使这两个 VM 位于不同服务器上的反关联性规则来部署这两个 BIG-IP VE VM。
* 这两个活动 ESXi 服务器有足够的资源可用，以便每个 ESXi 服务器上可以托管一个 BIG-IP VE VM，并具有 100% 的 CPU 和 RAM 保留量。
* VMware vSphere HA 有足够的资源来托管具有 100% 的 CPU 和 RAM 的两个 BIG-IP VM。

由于这些需求，您必须规划 F5 on {{site.data.keyword.cloud_notm}} 所需的空间。如果需要，在订购 F5 on {{site.data.keyword.cloud_notm}} 之前，请向实例添加 1 到 2 个 ESXi 服务器和/或减少用于故障转移的 vSphere HA CPU 保留量。

## F5 on IBM Cloud 订购示例
{: #f5_considerations-example}

您订购了具有 2 个 ESXi 服务器的 VMware vCenter Server **小型**实例，配置如下：16 个核心 (2.10 GHz)，每个核心 128 GB RAM。对于 F5 on {{site.data.keyword.cloud_notm}}，您选择了**最佳**许可模型，并且对于**最大带宽**，选择了值 5 Gbps。

在本例中，在每个服务器上，单个 BIG-IP VM 需要：
* 2.1 GHz * 8 个 vCPU = 16.8 GHz CPU，以及
* 16 GB RAM

对于两个 BIG-IP VM，共需要 33.6 GHz 的 CPU 和 32 GB RAM。

每个 ESXi 服务器的容量都为 16 个核心 * 2.1 GHz = 33.6 GHz，因此如果这两个服务器都处于活动状态，并且每个服务器上至少有 16.8 GHz 的 CPU 和 16 GB RAM 可用，那么可满足前两个需求。

但是，缺省情况下，vSphere HA 会将 50% 的 CPU 和 RAM 保留用于在最初部署有 2 个 ESXi 服务器的 vCenter Server 实例上进行故障转移。对于此示例，以下资源可用：

`2 * 16 个核心 * 2.1 GHz * 50% = 33.6 GHz 可用`

由于 ESXi 服务器上会存在其他工作负载（例如 VMware vCenter Server、VMware NSX Controller 和 VMware NSX Edge），因此使用这些资源无法满足第三个需求，因为两个 BIG-IP VM 需要 33.6 GHz 的 CPU 和 32 GB RAM。

在这种情况下，F5 on {{site.data.keyword.cloud_notm}} 安装可能会失败，除非至少向环境中添加一个 ESXi 服务器，并且相应地更新 vShpere HA 故障转移保留量，以确保有足够资源可用于这两个 BIG-IP VE VM。如果需要更多资源来运行 F5 on {{site.data.keyword.cloud_notm}} 服务，可以在安装 F5 on {{site.data.keyword.cloud_notm}} 之前添加更多 ESXi 服务器。

## 除去 F5 on IBM Cloud 时的注意事项
{: #f5_considerations-remove}

除去 F5 on {{site.data.keyword.cloud_notm}} 服务之前，请确保正确除去了现有 BIG-IP VE 配置。具体来说，网络流量必须围绕 BIG-IP VE 而不是通过 BIG-IP VE 来路由。否则，可能会影响环境中的现有数据流量。

## 相关链接
{: #f5_considerations-related}

* [订购 F5 on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-f5_ordering)
* [管理 F5 on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-managing_f5)
* [联系 IBM 支持人员](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support)
* [常见问题](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-faq)
* [F5 Web 站点](https://www.f5.com/){:new_window}
