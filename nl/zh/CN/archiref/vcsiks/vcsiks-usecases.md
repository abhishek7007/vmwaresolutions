---

copyright:

  years:  2016, 2019

lastupdated: "2019-05-08"

subcollection: vmware-solutions


---

# 用例
{: #vcsiks-usecases}

## 工作负载迁移到 IBM Cloud
{: #vcsiks-usecases-workload-mig}

Acme Skateboards 希望将其内部部署 VMware SDDC 无缝扩展到 VMware vCenter Server on {{site.data.keyword.cloud}} 实例。他们需要业务保持正常运行，并尽可能减少停机时间。但将其应用程序重新配置为在云中运行并不是最佳解决方案。

VMware vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle 支持在 {{site.data.keyword.cloud_notm}} 与内部部署 VMware 虚拟化数据中心之间创建无缝连接。

{{site.data.keyword.cloud_notm}} 提供的 vCenter Server with Hybridity Bundle 产品支持对等内部部署源站点与 {{site.data.keyword.cloud_notm}} 目标站点之间建立安全连接。

![VMware Hybrid Cloud Extension 服务](../../images/vcsiks-hcx.svg "VMware Hybrid Cloud Extension 服务")

vCenter Server with Hybridity Bundle 将在内部部署和 {{site.data.keyword.cloud_notm}} 之间创建松散耦合的互连，并支持以下功能：
- **简单互连** - 通过任何物理连接（包括公用因特网、专用 VPN 或 {{site.data.keyword.cloud_notm}} Direct Link）轻松建立逻辑网络连接。
- **第 2 层扩展** - 包括内部部署子网和 IP 寻址的内部部署网络扩展到云中。
- **加密** - 安全地加密对等站点之间的网络流量。
- **网络优化** - 选择最佳连接并高效处理洪流连接，以便网络流量尽快移动。
- **数据去重** - 最高可减少 50% 的网络流量。
- **智能路由** - 移动工作负载时，邻近路由可以更改网络路径（即网关），以便网络流量使用目标站点网关，而不会发生“发夹”问题而返回到源站点。
- **零停机时间迁移** - 可以使用 vMotion 将正在运行的虚拟机移至云或从云移回原处。
- **安排的迁移** - 可以将任意数量的虚拟机复制到目标站点，然后在该站点上的指定时间激活，以替换在源站点上运行的系统。
- **安全策略迁移** - 如果 NSX 是以内部部署方式使用的，那么任何安全策略、防火墙等都会随工作负载一起移动。

通过使用此解决方案，Acme Skateboards 成功地将其内部部署 VMware 工作负载迁移到 {{site.data.keyword.cloud_notm}}，满足了几乎或完全不发生停机时间，也无需重新配置应用程序的要求。

## 混合体系结构部署
{: #vcsiks-usecases-hybrid-archi-deployment}

Acme Skateboards 希望在其应用程序现代化之旅中，在 {{site.data.keyword.cloud_notm}} 上部署由 vCenter Server 和 {{site.data.keyword.icpfull_notm}} 组成的混合体系结构。其需求是在虚拟机上运行其数据库，在容器中运行应用程序和 Web Service，并使用一组通用工具进行网络和安全管理。

![Acme Skateboards 混合应用程序图](../../images/vcsiks-acme-app-arch.svg "Acme Skateboards 混合应用程序图")

{{site.data.keyword.vmwaresolutions_short}} 提供了自动化功能，可将 VMware 技术组件部署到全球范围的 {{site.data.keyword.CloudDataCents_notm}} 中。该体系结构包含一个云区域，并支持扩展到其他地理位置中的更多云区域或扩展到同一数据中心内的其他 {{site.data.keyword.cloud_notm}} pod 中。

{{site.data.keyword.icpfull_notm}} 和 Cloud Automation Manager (CAM) 产品可手动部署到内部部署虚拟化平台中，从而支持通过内部部署位置进行云管理。或者，{{site.data.keyword.icpfull_notm}} 和 CAM 可借助自动化功能，作为服务扩展提供给现有或新的 vCenter Server 部署，从而支持通过 {{site.data.keyword.cloud_notm}} 进行云管理。

下图表示基于 vCenter Server 实例运行的 {{site.data.keyword.icpfull_notm}}。NSX-V 配置有专用交换机/VXLAN、DLR 和专门针对 {{site.data.keyword.icpfull_notm}} 覆盖网络的 ESG，并且路由设置为通过 ESG 对底层网络进行访问。

通过使用 {{site.data.keyword.cloud_notm}} 自动化，Acme Skateboards 可以供应混合解决方案，该解决方案包含 VMware on {{site.data.keyword.cloud_notm}}（用于运行其数据库 VM）和 {{site.data.keyword.icpfull_notm}} on VMware on {{site.data.keyword.cloud_notm}}（用于在容器中运行其应用程序和前端 Web Service）。NSX 为其提供了一组通用管理工具，用于管理网络和覆盖网络中的安全性。

## 相关链接
{: #vcsiks-usecases-related}

* [vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle 概述](/docs/services/vmwaresolutions/archiref/vcs?topic=vmware-solutions-vcs-hybridity-intro)
