---

copyright:

  years: 2016, 2019

lastupdated: "2019-04-16"

keywords: IBM Cloud for VMware Solutions, getting started, vmware solutions offerings, add-on services for vmwaresolutions, vmwaresolutions use cases

subcollection: vmware-solutions


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:note: .note}
{:important: .important}
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:table: .aria-labeledby="caption"}

# 入门教程
{: #getting-started}

在本入门教程中，我们将引导您完成订购实例及其某些附加服务的过程。
{:shortdesc}

## 开始之前
{: #getting-started-prereqs}

在开始使用 {{site.data.keyword.vmwaresolutions_full}} 之前，请先查看有关浏览器需求、用户帐户、部署选项和附加服务的以下重要信息。

### 浏览器需求
{: #getting-started-browser-req}

支持以下浏览器：
  *  Mozilla Firefox
  *  Google Chrome
  *  Apple Safari

不支持 Microsoft Internet Explorer。
{:note}

为了使 {{site.data.keyword.vmwaresolutions_short}} 控制台上的查看和工作达到最佳效果，请将屏幕分辨率设置为至少 1024 x 500 像素（宽 x 高）。

### 用户帐户
{: #getting-started-user-accts}

您需要 {{site.data.keyword.cloud_notm}} 帐户和 {{site.data.keyword.cloud_notm}} 基础架构帐户。这些帐户必须满足某些需求。

   表 1. 需要的用户帐户
   <table>
   <tr>
      <th>帐户</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>IBM 标识</td>
      <td>通过使用 **IBM 标识**，您可以对使用的所有 IBM 产品和服务（包括 {{site.data.keyword.cloud_notm}}）使用一个登录用户名。{{site.data.keyword.vmwaresolutions_short}} 在 {{site.data.keyword.cloud_notm}}“目录”中作为基础架构解决方案提供。要访问 {{site.data.keyword.vmwaresolutions_short}} 控制台，您必须具有 **IBM 标识**。<br><br>要使用 **IBM 标识**登录到 {{site.data.keyword.vmwaresolutions_short}} 控制台，必须将 **IBM 标识**与 {{site.data.keyword.cloud_notm}} 帐户相关联。首次登录到控制台时，系统会引导您将现有 **IBM 标识**与 {{site.data.keyword.cloud_notm}} 帐户相关联，或者注册一个新的 {{site.data.keyword.cloud_notm}} 帐户。新的 {{site.data.keyword.cloud_notm}} 帐户将自动与您的 **IBM 标识**关联。您只需要完成此过程一次。<br><br>如果将 **IBM 标识**与 {{site.data.keyword.cloud_notm}} 帐户相关联时发生问题，请参阅[访问 {{site.data.keyword.cloud_notm}} 的故障诊断](/docs/account?topic=account-accessing#accessing)。</td>
   </tr>
   <tr>
      <td>IBM Cloud 帐户</td>
      <td>要订购和使用 {{site.data.keyword.cloud_notm}} 服务，需要 {{site.data.keyword.cloud_notm}} 帐户。帐单信息与 {{site.data.keyword.cloud_notm}} 帐户相关联。物理和虚拟基础架构的成本以及生成的许可证都将向您的 {{site.data.keyword.cloud_notm}} 帐户收费。</td>
   </tr>
   <tr>
      <td>IBM Cloud 基础架构帐户</td>
      <td>有关 {{site.data.keyword.cloud_notm}} 基础架构帐户的需求的信息，请参阅 [{{site.data.keyword.cloud_notm}} 基础架构帐户需求](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-slaccountrequirement)。<br><br>您可以将 {{site.data.keyword.cloud_notm}} 基础架构帐户与 {{site.data.keyword.cloud_notm}} 帐户相链接，以组合使用基础架构即服务 (IaaS) 和平台即服务 (PaaS) 资源。然后，您可以通过单点登录来访问 IaaS 资源和 PaaS 资源。链接帐户以后，还会将您使用的所有 PaaS 和 IaaS 资源的费用都开具在一张发票中。<ul><li>如果您没有 {{site.data.keyword.cloud_notm}} 基础架构帐户，请遵循[注册 IBM Cloud 基础架构帐户](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-signing_softlayer_account#signing_softlayer_account-infra)中的过程请求基础架构帐户，然后遵循[切换到 IBM 标识和链接帐户](/docs/account?topic=account-unifyingaccounts#unifyingaccounts)中的过程将 {{site.data.keyword.cloud_notm}} 基础架构帐户与 {{site.data.keyword.cloud_notm}} 帐户相链接。</li><li>如果您已有 {{site.data.keyword.cloud_notm}} 基础架构帐户，那么可以通过遵循[切换到 IBM 标识和链接帐户](/docs/account?topic=account-unifyingaccounts#unifyingaccounts)中的过程将其与 {{site.data.keyword.cloud_notm}} 帐户相链接。</li></ul></td>
   </tr>
   </table>

### 部署产品
{: #getting-started-depl-offerings}

查看并选择部署产品。

  表 2. 部署产品
  <table>
    <tr>
       <th>部署产品</th>
       <th>描述</th>
    </tr>
    <tr>
       <td>[VMware vCenter Server on IBM Cloud](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_vcenterserveroverview)</td>
       <td>利用 vCenter Server 产品，您可以使用定制计算、存储器和网络资源来部署最符合您的业务需要的 VMware 虚拟环境。</td>
    </tr>
    <tr>
       <td>[VMware vCenter Server on IBM Cloud with Hybridity Bundle](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_overview)</td>
       <td>vCenter Server with Hybridity 产品是一种托管的专用云，可帮助您快速、轻松地将内部部署基础架构扩展到云中。VMware 环境基于 IBM 提供的 VMware 软件定义的数据中心许可证，并包含 VMware Hybrid Cloud Extension (HCX)。通过使用 HCX，可以安全地将内部部署 vSphere 5.0+ 环境与 {{site.data.keyword.cloud_notm}} 站点相连接，以实现无缝的基础架构混合性和真正的应用程序移动性。</td>
    </tr>
    <tr>
       <td>[VMware vSphere on IBM Cloud](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_vsphereclusteroverview)</td>
       <td>vSphere on {{site.data.keyword.cloud_notm}} 产品提供可定制的虚拟化服务，用于组合使用与 VMware 兼容的 {{site.data.keyword.baremetal_short}}、硬件组件和许可证，以构建您自己的 IBM 托管的 VMware 环境。</td>
    </tr>
    <tr>
       <td>[NetApp ONTAP Select](/docs/services/vmwaresolutions/netapp?topic=vmware-solutions-np_netappoverview)</td>
       <td>NetApp ONTAP Select 产品支持部署软件定义的存储器集群，以满足您对基于 NetApp ONTAP Select 的专用和高可用性存储设备的需求。</td>
    </tr>
  </table>

### 附加组件服务
{: #getting-started-add-on-services}

查看并选择部署产品的附加服务。

  表 3. 可用于部署产品的附加服务
  <table>
    <tr>
       <th>服务名称</th>
       <th>描述</th>
    </tr>
    <tr>
       <td>[F5 on IBM Cloud](/docs/services/vmwaresolutions/services?topic=vmware-solutions-f5_considerations)</td>
       <td>F5 on {{site.data.keyword.cloud_notm}} 服务 (F5 BIG-IP® Virtual Edition) 用于提供本地和全球规模的智能 L4-L7 负载均衡和流量管理服务、稳健的网络和 Web 应用程序防火墙保护，以及安全和联合的应用程序访问。</td>
    </tr>
    <tr>
       <td>[FortiGate Security Appliance on IBM Cloud](/docs/services/vmwaresolutions/services?topic=vmware-solutions-fsa_considerations)</td>
       <td>FortiGate Security Appliance on {{site.data.keyword.cloud_notm}} 服务用于以高可用性方式部署 FortiGate Security Appliance (FSA) 300 系列设备对，以提供防火墙、路由、NAT 和 VPN 服务来保护实例公用 VLAN 上的所有服务器和虚拟机。</td>
    </tr>
    <tr>
       <td>[FortiGate Virtual Appliance on IBM Cloud](/docs/services/vmwaresolutions/services?topic=vmware-solutions-fortinetvm_considerations)</td>
       <td>FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}} 服务用于将 FortiGate Virtual Appliance 成对部署到环境中，这可帮助通过在虚拟基础架构中实施关键安全控制来降低风险。</td>
    </tr>
    <tr>
       <td>[HyTrust CloudControl on IBM Cloud](/docs/services/vmwaresolutions/services?topic=vmware-solutions-htcc_considerations)</td>
       <td>HyTrust CloudControl on {{site.data.keyword.cloud_notm}} 服务根据安全标准强制实施和控制合规性，并提供详细的基于角色的访问控制 (RBAC)、核准和审计功能。与 HyTrust DataControl 组合使用时，该服务可确保虚拟机和工作负载数据不会离开 {{site.data.keyword.CloudDataCent_notm}} 内的特定区域、集群或 ESXi 服务器。</td>
    </tr>
    <tr>
       <td>[HyTrust DataControl on IBM Cloud](/docs/services/vmwaresolutions/services?topic=vmware-solutions-htdc_considerations)</td>
       <td>HyTrust DataControl on {{site.data.keyword.cloud_notm}} 服务通过集成密钥管理提供高强度加密功能，以确保工作负载在整个生命周期中的安全。此服务可以提供操作系统级别和数据级别的加密，这意味着可以对工作负载中的任何目录、文件夹或文件进行加密和解密。</td>
    </tr>
    <tr>
       <td>[HyTrust KeyControl on IBM Cloud](/docs/services/vmwaresolutions/services?topic=vmware-solutions-htkc_considerations)</td>
       <td>HyTrust KeyControl on {{site.data.keyword.cloud_notm}} 服务通过自动化和简化加密密钥的生命周期来简化已加密工作负载的管理工作。该服务可以使用符合 FIPS 140-2 的加密来轻松管理大批加密密钥。</td>
    </tr>
    <tr>
       <td>[IBM Cloud Private Hosted](/docs/services/vmwaresolutions/services?topic=vmware-solutions-icp_overview)</td>
       <td>{{site.data.keyword.cloud_notm}} Private Hosted on vCenter Server on {{site.data.keyword.cloud_notm}} 服务会将微服务和容器的强大功能引入到 {{site.data.keyword.cloud_notm}} 上的 VMware 环境中。使用此服务，可以将内部部署中您熟悉的 VMware 和 {{site.data.keyword.cloud_notm}} Private 操作模型和工具扩展到 {{site.data.keyword.cloud_notm}} 中。</td>
    </tr>
    <tr>
       <td>[IBM Spectrum Protect Plus on IBM Cloud](/docs/services/vmwaresolutions/services?topic=vmware-solutions-spp_considerations)</td>
       <td>IBM Spectrum Protect&trade; Plus on {{site.data.keyword.cloud_notm}} 服务为虚拟环境的数据保护、数据复用和数据恢复提供高效、可扩展的解决方案。可以将此服务作为独立解决方案实施，也可以与 IBM Spectrum Protect 环境集成，以便卸载用于长期存储和数据监管的副本。</td>
    </tr>
    <tr>
       <td>[KMIP for VMware on IBM Cloud](/docs/services/vmwaresolutions/services?topic=vmware-solutions-kmip_standalone_considerations)</td>
       <td>KMIP for VMware on {{site.data.keyword.cloud_notm}} 服务用于提供高可用性服务，以管理 {{site.data.keyword.cloud_notm}} 中 VMware 使用的加密密钥。此服务提供了运行时功能，以支持客户创建、检索、激活、撤销和销毁加密密钥。还提供了管理功能，以维护客户机凭证与加密密钥之间的关联。</td>
    </tr>
    <tr>
       <td>[Veeam on IBM Cloud](/docs/services/vmwaresolutions/services?topic=vmware-solutions-veeam_considerations)</td>
       <td>Veeam on {{site.data.keyword.cloud_notm}} 服务可与 VMware 系统管理程序无缝集成，以帮助企业实现高可用性。此服务可为应用程序和数据提供恢复点和时间目标。在完成配置后的 15 分钟内就会提供恢复点和时间目标。通过使用此服务，您可以在 Veeam 控制台中直接控制基础架构的所有虚拟机的备份和复原。</td>
    </tr>
    <tr>
       <td>[VMware HCX on IBM Cloud](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcx_considerations#hcx_considerations)</td>
       <td>HCX on {{site.data.keyword.cloud_notm}} 服务可以将内部部署数据中心的网络无缝扩展到 {{site.data.keyword.cloud_notm}}，这允许虚拟机 (VM) 在不进行任何转换或更改的情况下，迁移到 {{site.data.keyword.cloud_notm}} 或从中迁移出来。</td>
    </tr>
    <tr>
       <td>[Zerto on IBM Cloud](/docs/services/vmwaresolutions/services?topic=vmware-solutions-addingzertodr)</td>
       <td>Zerto on {{site.data.keyword.cloud_notm}} 服务用于提供复制和灾难恢复功能，这些功能可以集成到部署产品中，以保护和恢复 {{site.data.keyword.cloud_notm}} 上 VMware 虚拟环境中的数据。</td>
    </tr>
   </table>

## 步骤 1：访问 IBM Cloud for VMware Solutions 控制台
{: #getting-started-step1}

{{site.data.keyword.vmwaresolutions_short}} 控制台是用于订购和管理部署的界面。每个部署在控制台中作为一个实例进行管理。控制台是与 {{site.data.keyword.cloud_notm}} 基础架构客户门户网站分开的独立用户界面。

要访问 {{site.data.keyword.vmwaresolutions_short}} 控制台：
1. 转至 https://cloud.ibm.com/infrastructure/vmware-solutions/console。
2. 使用 **IBM 标识**登录到控制台。

## 步骤 2：配置用户帐户和设置
{: #getting-started-step2}

在订购实例之前，必须先在控制台的**设置**页面上输入 {{site.data.keyword.cloud_notm}} 基础架构帐户的用户名和 API 密钥。

有关如何配置用户帐户和设置的信息，请参阅[管理用户帐户和设置](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-useraccount)。

## 步骤 3：订购实例
{: #getting-started-step3}

在决定部署产品（在控制台中作为实例进行管理）之后，开始订购过程。

有关如何订购实例的信息，请参阅基于您选择的部署产品的以下主题：
* [订购 vCenter Server 实例](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance)
* [订购 vCenter Server with Hybridity Bundle 实例](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_orderinginstance)
* [订购新的 vSphere 集群](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_orderinginstances)
* [订购 NetApp ONTAP Select 实例](/docs/services/vmwaresolutions/netapp?topic=vmware-solutions-np_orderinginstances)

## 步骤 4：查看实例
{: #getting-started-step4}

在**步骤 3** 中下好实例订单之后，会自动开始部署实例。您可以通过查看实例详细信息来跟踪部署的状态。实例部署完成后，您也可以在实例详细信息页面上查看实例及其附加服务的摘要和详细信息。

有关如何查看您订购的实例的信息，请参阅以下主题：
* [查看 vCenter Server 实例](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_viewinginstances)
* [查看 vCenter Server with Hybridity Bundle 实例](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_viewinginstances)
* [查看 NetApp ONTAP Select 实例](/docs/services/vmwaresolutions/services?topic=vmware-solutions-np_viewinginstances#np_viewinginstances)
