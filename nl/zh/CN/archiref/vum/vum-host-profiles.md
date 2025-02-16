---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-25"

subcollection: vmware-solutions


---

#	主机概要文件
{: #vum-host-profiles}

vCenter 具有称为“主机概要文件”的功能。此功能可创建概要文件，用于捕获预配置并已验证的参考主机配置，以及帮助系统管理员管理集群中的主机配置。主机概要文件提供了面向主机配置和配置一致性的自动化集中管理机制。通过主机概要文件，可以将配置视为受管对象，其中包含要配置的参数目录以及联网、存储、安全性和其他主机级参数。这些主机概要文件可应用于与主机概要文件关联的单个主机、一个集群或所有主机和集群。

随着部署了原始集群的 IC4VS 自动化部署的 VMware vCenter Server on {{site.data.keyword.cloud}} vSphere ESXi 主机越来越多，配置漂移会比手动主机添加方法要少。但是，除了自动化操作外，系统管理员操作可能会使主机配置不同。例如，添加了更多 NFS 存储器或添加了额外的 VLAN。使用主机概要文件通过检查新主机与现有主机的一致性来验证该主机的配置，是 {{site.data.keyword.cloud_notm}} 中此工具的一个有效用例。

要向 vCenter Server 集群添加更多主机，请参阅[扩展和收缩 vCenter Server 实例的容量](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_addingremovingservers)。

注：
*	对于部署或升级到 V2.1 或更高版本的实例，将使用 VMware 中近期（但不一定是最新）的 ESXi 更新，对新部署的 ESXi 服务器和集群进行修补。
*	您负责对 VMware 组件执行其他所有更新，包括确保新部署的 ESXi 服务器和集群都具有全部所需的最新更新。

我们建议在向集群添加新主机后，将该主机置于维护模式，以便在托管任何工作负载之前，可以先复查其一致性漂移并对其进行修复。

检查一致性需要按顺序执行以下操作：
1.	通过现有主机创建主机概要文件。
2.	将新主机连接到主机概要文件。
3.	使用主机概要文件检查新主机的一致性。
4.	复查一致性不符合情况并进行修复。

##	通过现有主机创建主机概要文件
{: #vum-host-profiles-create-host-profile}

1.	在 vSphere Web Client 的主页中，单击**策略和概要文件**。
2.	单击**主机概要文件**，并导航至“主机概要文件”视图。
3.	单击**从主机中抽取概要文件**图标。
4.	选择将充当参考主机的现有主机，然后单击**下一步**。
5.	输入新概要文件的名称和描述，然后单击**下一步**。
6.	复查新概要文件的摘要信息，然后单击**完成**。
7.	新概要文件将显示在概要文件列表中。

##	将新主机连接到主机概要文件
{: #vum-host-profiles-attach-to-profile}

1.	从“主机概要文件”主视图的**概要文件列表**中，选择要应用于新主机的先前创建的主机概要文件。
2.	单击**将主机概要文件连接到主机和集群/从主机和集群拆离主机概要文件**图标。
3.	从展开的列表中选择新主机，然后单击**连接**。
4.	新主机将添加到“连接的实体”列表中。
5.	单击**下一步**，然后单击**完成**。

##	使用主机概要文件检查新主机的一致性
{: #vum-host-profiles-check-compliance}

1.	导航至先前已完成的主机概要文件。
2.	单击**检查主机概要文件一致性**图标。
3.	在**对象**选项卡上，一致性状态会更新为：_一致、未知或不一致_。不一致状态指示发现概要文件和新主机之间有特定的不一致问题。

##	复查一致性不符合情况并进行修复
{: #vum-host-profiles-review-compliance}

1. 要查看有关一致性不符合情况的更多详细信息，请在一致性检查中使用的**对象**选项卡中，选择**主机概要文件**。
2. 要查看关于不符合一致性的主机与主机概要文件之间有哪些参数不同的具体详细信息，请单击**监视**选项卡，然后选择**一致性**视图。
3. 展开对象层次结构，然后选择不符合的主机。
4. 有差异的参数会显示在“一致性”窗口中的层次结构下面。
5. 复查参数并了解为何新主机可能会与参考主机有所不同。对于一致性不可接受的参数，请先进行修复，然后使新主机退出维护模式。例如，由系统管理员操作引起配置漂移的情况。

## 相关链接
{: #vum-host-profiles-related}

* [VMware HCX on {{site.data.keyword.cloud_notm}} 解决方案体系结构](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcx-archi-intro#hcx-archi-intro)
* [VMware Solutions on {{site.data.keyword.cloud_notm}} 数字技术互动](https://ibm-dte.mybluemix.net/vmware)（演示）
