---

copyright:

  years:  2016, 2019

lastupdated: "2019-01-23"

---

{:tip: .tip}
{:note: .note}
{:important: .important}

# 扩展和收缩 VMware Federal 实例的容量

可以根据业务需求，通过添加或除去 ESXi 服务器，扩展或收缩 VMware Federal 实例的容量。

如果主集群将 vSAN 作为其存储器，那么在部署后添加一个或多个 ESXi 服务器可以增加集群存储容量。

此功能仅可用于尚未受到保护的 VMware Federal 实例。
{:note}

## 向 VMware Federal 实例添加 ESXi 服务器

### 在添加 ESXi 服务器之前

* 不要通过 VMware vSphere Web Client 来添加 ESXi 服务器。在 vSphere Web Client 上所做的更改不会与 {{site.data.keyword.vmwaresolutions_full}} 控制台同步。
* 使用 NFS 存储器的 VMware Federal 实例必须至少具有 2 个 ESXi 服务器。可以将缺省集群扩展为最多具有 51 个 ESXi 服务器。每个非缺省集群可以扩展为最多具有 59 个 ESXi 服务器。
* 使用 vSAN 存储器的 VMware Federal 实例必须至少具有 4 个 ESXi 服务器。

## 添加 ESXi 服务器的过程

1. 在 {{site.data.keyword.vmwaresolutions_short}} 控制台中，单击左侧导航窗格中的**已部署的实例**。
2. 在 **vCenter Server 实例**表中，单击要扩展容量的实例。
3. 在左侧导航窗格上，单击**基础架构**。
4. 在**集群**表中，单击要在其中添加 ESXi 服务器的集群。
5. 在 **ESXi 服务器**表中，单击**添加**。
6. 在**添加服务器**窗口中，选择要添加的服务器数，单击价格链接以复查估算成本，然后单击**添加**。

### 添加 ESXi 服务器后的结果

1. 当实例状态从**可供使用**变为**正在修改**时，您在控制台上可能会遇到轻微延迟。在对实例进行其他更改之前，请允许该操作完全完成。
2. 系统将通过电子邮件通知您，正在处理添加 ESXi 服务器的请求。在控制台上，与 ESXi 服务器关联的集群的状态会更改为**正在修改**。
3. 如果在集群中看不到添加到列表中的新 ESXi 服务器，请检查电子邮件或控制台通知以查找有关该故障的更多详细信息。

## 从 VMware Federal 实例中除去 ESXi 服务器

### 在除去 ESXi 服务器之前

* 不要通过 VMware vSphere Web Client 来除去 ESXi 服务器。在 vSphere Web Client 上所做的更改不会与 {{site.data.keyword.vmwaresolutions_short}} 控制台同步。
* 使用 NFS 存储器的 VMware Federal 实例必须至少有 2 个 ESXi 服务器，使用 vSAN 存储器的 VMware Federal 实例必须至少有 4 个 ESXi 服务器。
* 除去 ESXi 服务器时，会将这些服务器置于维护模式，接着会迁移在这些服务器上运行的所有虚拟机 (VM)，然后从 vCenter Server 中除去这些服务器。为了最大程度地控制 VM 的重新定位，建议您先将要除去的 ESXi 服务器置于维护模式，然后使用 VMware vSphere Web Client 来手动迁移在这些 ESXi 服务器上运行的 VM。在此之后，使用 {{site.data.keyword.vmwaresolutions_short}} 控制台来除去 ESXi 服务器。

## 除去 ESXi 服务器的过程

1. 在 {{site.data.keyword.vmwaresolutions_short}} 控制台中，单击左侧导航窗格中的**已部署的实例**。
2. 在 **vCenter Server 实例**表中，单击要压缩容量的实例。
3. 在左侧导航窗格上，单击**基础架构**。
4. 在**集群**表中，单击要从中除去 ESXi 服务器的集群。
5. 在 **ESXi 服务器**表中，选择要除去的服务器，然后单击**除去**。

### 除去 ESXi 服务器后的结果

1. 当实例状态从**可供使用**变为**正在修改**时，您在控制台上可能会遇到轻微延迟。在对实例进行其他更改之前，请允许该操作完全完成。
2. 系统将通过电子邮件通知您，正在处理除去 ESXi 服务器的请求。在控制台上，与 ESXi 服务器关联的集群的状态会更改为**正在修改**。
3. {{site.data.keyword.cloud_notm}} 基础架构将在 {{site.data.keyword.cloud_notm}} 基础架构计费周期（通常为 30 天）结束时完全回收 ESXi 服务器。

   在所除去 ESXi 服务器的 {{site.data.keyword.cloud_notm}} 基础架构计费周期结束之前，仍然会对您计费。
   {:note}

### 相关链接

* [针对 VMware Federal 实例的需求和规划](/docs/services/vmwaresolutions/vcenter/vc_fed_planning.html)
* [添加、查看和删除 VMware Federal 实例的集群](/docs/services/vmwaresolutions/vcenter/fed_addviewdeleteclusters.html)
* [将主机置于维护模式](http://pubs.vmware.com/vsphere-60/index.jsp?topic=%2Fcom.vmware.vsphere.resmgmt.doc%2FGUID-8F705E83-6788-42D4-93DF-63A2B892367F.html){:new_window}
* [Enhanced vMotion Compatibility (EVC) 处理器支持](https://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1003212){:new_window}
