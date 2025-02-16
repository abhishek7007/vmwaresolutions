---

copyright:

  years:  2016, 2019

lastupdated: "2019-05-17"

---

# Troubleshooting
{: #opsprocs-trouble}

To troubleshoot your vCenter Server instance issues, your system administrators must identify the symptoms of the issue, determine which of the solution components are affected, research and propose a fix or workaround, and test the fix.

* Identifying Symptoms - A number of potential causes might lead to the under-performance or non-performance of your instance. The first step in efficient troubleshooting is to identify exactly what is going wrong. These symptoms may be reported from; vSphere events and alarms, Operations Management in 	{{site.data.keyword.cloud}} or reported via your Service Desk from one of your users.
* Isolating the affected components - After you have identified the symptoms of the issue, you must identify the software or hardware components that are affected and might be causing the issue and those components that are not involved. Tools such as vCenter Operations Management in {{site.data.keyword.cloud_notm}} assist with this step.
* Proposing a fix or workaround - Once you understand the symptoms and have isolated the components, you can research possible fixes and workarounds. Your system administrators also make use of the {{site.data.keyword.cloud_notm}} Portal, including the troubleshooting scenarios in this document as well as IBM ServiceNow and VMware Knowledgebase. In addition, there are many wikis and blogs that may assist you. For even quicker resolutions, Operations Management in {{site.data.keyword.cloud_notm}} includes a number of remediations for identified issues.
* Testing Possible Solutions - When you know what the symptoms of the issue are, which components are involved and have proposed a fix/workaround, your system administrators test the solutions systematically until the issue is resolved.

vSphere includes a user-configurable events and alarms subsystem which tracks events that occur throughout the vSphere environment and stores the data in log files and the vCenter database. This subsystem also enables system administrators to specify the conditions under which alarms are triggered. Alarms change state from warnings to more serious alerts as system conditions change, and can trigger automated alarm actions such as to email the system administrator team. This functionality is useful when you want to be informed, or take immediate action, when certain events or conditions occur for a specific inventory object, or group of objects.

Additional tools such as those incorporated into the Operations Management on {{site.data.keyword.cloud_notm}} architecture provide greater assistance with; identifying symptoms, isolating the affected components and proposing a fix/workaround.

## Guidelines
{: #opsprocs-trouble-guidelines}

The following guidelines are considered best practice for troubleshooting your {{site.data.keyword.vmwaresolutions_short}} issue:
* Approach troubleshooting and problem-solving systematically.
* Are the symptoms related to; availability, utilization or configuration:
 *  Availability - These symptoms relate to the availability of hardware and software components and are typified by a no response. Often high availability design masks these issues so that they do not impact your workloads and users directly.
 * Utilization - These symptoms relate to capacity and performance and are typified by slow-running or in-ability to load. Proactively managing capacity drastically reduces these issues.
 * Configuration - These issues are typically discovered in the provision of new services or a result to applying a change. Incorrect settings can surface as either availability or utilization symptoms. For example, an incorrect IP address displays as an availability issue, whereas virtual machine (VM) RAM settings being too low cause utilization symptoms.
* Try to isolate the issue to a component in the environment.
* Take notes so you can trace your steps.
* Understand and document you software versions.
* Document your subnets and IP address usage, including VIP and NAT addresses.
* Have diagrams of your network. You need a number of diagrams that show the physical (underlay) and logical (overlay) layers.
* Understand any recent changes to the environment.
* Research the impact of the fix, do not lock yourself out of any management interfaces.
* Make sure you have backups of all key components; in case they need to be reloaded or reset.
* Do not change more than one thing at a time.
* Document each change and its result.
* When raising a support request, ensure that you document carefully and provide pertinent information. Be very clear in what symptoms you are seeing and identifying the components you believe is at fault. Make sure you use the correct terminology. Try to minimize any confusion or ambiguity in your choice of words.
* vSphere ESXi and vCenter Server configuration files control the behavior of the system, understand where they are. Most configuration file settings are set during installation, but can be modified after installation.
* Log files capture messages generated by the kernel and different subsystems and services. vSphere ESXi and vCenter services maintain separate log files, understand where they are located and how they can be accessed.
* Understand how to use popular system administration tools for help in diagnostics.

For more information, see [Troubleshooting Guidelines KB0012073](https://watson.service-now.com/nav_to.do?uri=kb_knowledge.do?sys_id=4a205910dbe0f7c06001327e9d96197b){:new_window}.

## Troubleshooting with log files
{: #opsprocs-trouble-logs}

Log files are an excellent source of information to troubleshoot issues, however, in practice, the number of log files and the vast amount of entries in each log make it difficult. [Troubleshooting with Log Files KB0012074](https://watson.service-now.com/nav_to.do?uri=kb_knowledge.do?sys_id=c74f91d0dbe4f7c06001327e9d9619b1){:new_window} details where these log files are located in the VMware environment. Due to the number of log files and the vast amount of entries in each log, you should consider the tooling in the Operations Management on {{site.data.keyword.cloud_notm}} to assist in capturing and analyzing event logs.

## Troubleshooting common scenarios
{: #opsprocs-trouble-common}

In an aid to isolating the affected components, this documentation on troubleshooting common scenarios has been classified into the following:

* Virtual Machines - these troubleshooting topics provide guidance to potential issues on VMs.
* Hosts  - these troubleshooting topics provide guidance on vSphere ESXi host issues.
* Cluster - these troubleshooting topics provide guidance on availability and resource management.
* Storage - these troubleshooting topics provide guidance on resolving vSAN and NFS storage issues.
* Network - these troubleshooting topics provide guidance on resolving network issues.
* vCenter - these troubleshooting topics provide guidance on resolving vCenter issues.
* Licenses - these troubleshooting topics provide guidance on resolving license issues. These typically relate to clients who have brought their own licenses to {{site.data.keyword.cloud_notm}}.

### Virtual machines
{: #opsprocs-trouble-common-vm}

Table 1. Virtual machine troubleshooting

| Title | Description |
|---|---|
| Generic VM troubleshooting | For more information, see [Troubleshooting Virtual Machines](https://docs.vmware.com/en/VMware-vSphere/6.7/com.vmware.vsphere.vm_admin.doc/GUID-EE645240-83CA-4F9E-B2F7-BECE864982C3.html){:new_window}. |
| VM performance issues | For information about troubleshooting the symptoms of VM performance issues including guest OS boots slowly, applications perform poorly, applications take a long time to launch or applications become unresponsive, see [Troubleshooting ESX/ESXi virtual machine performance issues (2001003)](https://kb.vmware.com/s/article/2001003){:new_window}. |
| Recover orphaned VM | For information about recovering orphaned VMs, which are VMs that exist in the vCenter database, but are not recognized by the vSphere ESXi host, see [Knowledge - KB0012862 v0.01](https://watson.service-now.com/nav_to.do?uri=kb_knowledge.do?sys_id=57c90b74dbdd7300c4fa302f9d96199e){:new_window}. |
| VM does not power on | For more information, see [Troubleshooting a virtual machine that is unable to power on (2001005)](https://kb.vmware.com/s/article/2001005){:new_window}. |
| VM does not power on after cloning or deploying from a template | [VMware article](https://docs.vmware.com/en/VMware-vSphere/6.7/com.vmware.vsphere.vm_admin.doc/GUID-2742CE14-20FD-416F-B89C-A156053A973F.html){:new_window} looks at issues that effect a VM after it has been cloned or deployed from a template. |
| VMware Tools are outdated or not installed - VMware Tools should be installed on the VMs and kept up to date. | [IBM Cloud KB0012161](https://watson.service-now.com/nav_to.do?uri=kb_knowledge.do?sys_id=797afaf0dbb477486001327e9d9619e6){:new_window} provides guidance on these tasks. |
| Old VM network devices | If VM network devices are not kept up-to-date network performance and, therefore, application performance could be impacted. For more information about deploying a new virtual network device and driver, see [Choosing a network adapter for your virtual machine (1001805)](https://kb.vmware.com/s/article/1001805){:new_window}. |
| Virtual Machine Memory Limit | Memory limits are often used, however, if a guest OS cannot access the memory it needs, the applications inside the guest OS may perform poorly. For more information about resolving the issue, see [Configuring Resource Allocation Settings](https://docs.vmware.com/en/VMware-vSphere/6.7/com.vmware.vsphere.resmgmt.doc/GUID-14102AB7-2CF9-42E3-9642-3EB6629EF530.html){:new_window}. |
| VM snapshots | While snapshots are very useful, the quantity and age of a VM's snapshots directly impact the performance of the VM. For information about resolving the issue, see [Consolidate Snapshots](https://docs.vmware.com/en/VMware-vSphere/6.7/com.vmware.vsphere.vm_admin.doc/GUID-2F4A6D8B-33FF-4C6B-9B02-C984D151F0D5.html){:new_window}. |
| VM logging | If logging has not been configured correctly the capacity of the datastore could be adversely impacted. For information about resolving the issue, see [Configuring Logging Levels for the Guest Operating System](https://docs.vmware.com/en/VMware-vSphere/6.7/com.vmware.vsphere.monitoring.doc/GUID-F465D340-6556-49E8-B137-C0B4A060E83B.html){:new_window}. |
| Troubleshooting network connection issues | Symptoms can include VM fails to connect to the network, or no network connectivity to or from a single VM. For information about resolving the issue, see [Troubleshooting virtual machine network connection issues (1003893)](https://kb.vmware.com/s/article/1003893?CoveoV2.CoveoLightningApex.getInitializationData=1&r=2&ui-communities-components-aura-components-forceCommunity-seoAssistant.SeoAssistant.getSeoData=1&other.KM_Utility.getArticleDetails=1&other.KM_Utility.getArticleMetadata=2&other.KM_Utility.getUrl=1&other.KM_Utility.getUser=1&other.KM_Utility.getAllTranslatedLanguages=2&ui-comm-runtime-components-aura-components-siteforce-qb.Quarterback.validateRoute=1){:new_window}.  |
| Determining if multiple virtual CPUs are causing performance issues  | For information about troubleshooting VMs experiencing performance issues when they are configured with multiple CPUs, see [Determining if multiple virtual CPUs are causing performance issues (1005362)](https://kb.vmware.com/s/article/1005362?CoveoV2.CoveoLightningApex.getInitializationData=1&r=2&ui-communities-components-aura-components-forceCommunity-seoAssistant.SeoAssistant.getSeoData=1&other.KM_Utility.getArticleDetails=1&other.KM_Utility.getArticleMetadata=2&other.KM_Utility.getUrl=1&other.KM_Utility.getUser=1&other.KM_Utility.getAllTranslatedLanguages=2&ui-comm-runtime-components-aura-components-siteforce-qb.Quarterback.validateRoute=1){:new_window}. These issues can include poor transfer speeds when copying data to or from a VM, backup jobs time out or are very slow, or a VM performs poorly.  |
| A VM was powered off or restarted  | For information about resolving the issue, see [Determining why a virtual machine was powered off or restarted (1019064)](https://kb.vmware.com/s/article/1019064?CoveoV2.CoveoLightningApex.getInitializationData=1&r=2&ui-communities-components-aura-components-forceCommunity-seoAssistant.SeoAssistant.getSeoData=1&other.KM_Utility.getArticleDetails=1&other.KM_Utility.getArticleMetadata=2&other.KM_Utility.getUrl=1&other.KM_Utility.getUser=1&other.KM_Utility.getAllTranslatedLanguages=2&ui-comm-runtime-components-aura-components-siteforce-qb.Quarterback.validateRoute=1){:new_window}. |
| One or more of your VMs has a poor response time |  For information about isolating a performance issue on a vSphere ESXi host, see [Troubleshooting ESX/ESXi virtual machine performance issues (2001003)](https://kb.vmware.com/s/article/2001003?lang=en_US){:new_window}. Performance issues can be caused by CPU constraints, memory over commitment, storage latency, or network latency. |

### vSphere ESXi hosts
{: #opsprocs-trouble-common-host}

Table 2. Typical vSphere ESXi hosts troubleshooting

| Title | Description |
|---|---|
| ESXI Commands |For an overview of command-line interfaces in vSphere, ESXi Shell commands, and VMware vSphere Command-Line Interface (vCLI) commands, see [Getting Started with vSphere Command-Line Interfaces](https://vdc-download.vmware.com/vmwb-repository/dcr-public/bc4fa31a-40ac-4aa9-a6a1-7171d1fff7f4/740990ee-4d65-4627-a9d4-0f046cb78aec/vsphere-esxi-vcenter-server-67-command-line-interface-getting-started-guide.pdf){:new_window}. |
| vSphere HA Host States | If vCenter reports a vSphere HA host state that indicate an error condition on the host, these need to be remediated as this issue can prevent vSphere HA from restarting VMs after a failure. For more information, see [Troubleshooting vSphere HA Host States](https://docs.vmware.com/en/VMware-vSphere/6.7/com.vmware.vsphere.vcenterhost.doc/GUID-DF7CEF44-98EC-458A-8614-50CCAEC0A7C5.html){:new_window}. |
| vSphere ESXi host is in a non-responding state | For information about troubleshooting a vSphere ESXi host that shows as Not Responding, Disconnected, or the VMs on the host show as grayed out in vCenter, see [ESX/ESXi hosts do not respond and is grayed out (1019082)](https://kb.vmware.com/s/article/1019082){:new_window}. |
| When powering on a VM, you see a File not found error  | For information about recreating a lost virtual disk descriptor file (VMDK), see [Recreating a missing virtual machine disk descriptor file (1002511)](https://kb.vmware.com/s/article/1002511){:new_window}. |
| VM Performance issues | For information about isolating a performance issue on a vSphere ESXi host, see [Troubleshooting ESX/ESXi virtual machine performance issues (2001003)](https://kb.vmware.com/s/article/2001003?lang=en_US){:new_window}. Performance issues can be caused by CPU constraints, memory over commitment, storage latency, or network latency. |
|  Bare Metal Server is down | If the Bare Metal Server running vSphere ESXi is unresponsive or down then log on to the {{site.data.keyword.cloud_notm}} management UI or console and check the status. If required, open a case to get assistance with your Bare Metal Server. For more information, see [Working with support cases](/docs/get-support?topic=get-support-open-case#open-case){:new_window}. |
| vSphere ESXi host is in disconnected or a not responding state  | For more information, see [Troubleshooting an ESXi/ESX host in non responding state (1003409)](https://kb.vmware.com/s/article/1003409?lang=en_US){:new_window}. |
| Purple screen of death  | The Purple Screen of Death (PSOD) is a kernel panic and the vSphere ESXi kernel (vmkernel) triggers this safety measure in response to an event/error which is unrecoverable and would mean that continuing to run would pose a high risk for the services and VMs. When the panic occurs and the vSphere ESXi host crashes, it terminates all the services running on it together with all the VMs hosted. The VMs are not gracefully shutdown, but rather abruptly powered off. If the host is part of a cluster and you’ve configured HA, these VMs are re-started on the other hosts in the cluster. For more information, see [Knowledge - KB0012864 v0.01](https://watson.service-now.com/nav_to.do?uri=kb_knowledge.do?sys_id=dd5d2330db11f300c4fa302f9d96198d){:new_window}. |

### Storage
{: #opsprocs-trouble-common-storage}

Table 3. Typical storage troubleshooting

| Title | Description |
|---|---|
| Storage troubleshooting | For more information about slow performance, unpredictable failures, disk corruption, or VM corruption, see [Troubleshooting storage issues when using VMware products (2013160)](https://kb.vmware.com/s/article/2013160?lang=en_US){:new_window}. |
| vSAN troubleshooting | For more information, see [Failure Handling in vSAN](https://docs.vmware.com/en/VMware-vSphere/6.7/com.vmware.vsphere.vsan-monitoring.doc/GUID-35A4B700-6640-4519-A885-440A1AE8D3BD.html){:new_window}.  |
| vSAN Disk Failure | For more information about identifying a failed disk and request replacement, see [A hard disk/magnetic disk in a VMware vSAN disk group fails (2077185)](https://kb.vmware.com/s/article/2077185){:new_window}. |
| Clear vSAN health issues | In the VMware vSphere Web Client Monitor page, you might see alerts and warnings that relate to vSAN Health issues. For information about clearing these issues, see [Virtual SAN Health alerts and warnings](/docs/services/vmwaresolutions?topic=vmware-solutions-trbl_vsan_alerts#trbl_vsan_alerts){:new_window}.|
| vSAN rebalance | If disks report errors in the health check indicating that the cluster is imbalanced and there are disks that are high on space usage while others are very low, and you should run a proactive rebalance. This manually initiates a rebalance of the objects in a vSAN cluster. For more information about vSAN proactive rebalance and when it may be applicable, see [vSAN proactive rebalance (2149809)](https://kb.vmware.com/s/article/2149809){:new_window}. |
| Initiate vSAN health test | If you suspect there is an issue with vSAN, you can initiate a health test to verify that the cluster components are working as expected. Running the VM creation test creates a VM on each host in the cluster and then deletes it. If these tasks are successful, then the cluster components are working as expected and the cluster is functional. Then network performance test is used to detect and diagnose connectivity issues, and to make sure the network bandwidth between the hosts is adequate. For more information, see [Proactive Tests](https://docs.vmware.com/en/VMware-vSphere/6.7/com.vmware.vsphere.vsan-monitoring.doc/GUID-B88B5900-33A4-4821-9659-59861EF70FB8.html){:new_window}. |
| Monitoring vSAN performance | For more information, see [Monitoring vSAN Performance](https://docs.vmware.com/en/VMware-vSphere/6.7/com.vmware.vsphere.vsan-monitoring.doc/GUID-3D2D1382-9DDC-44D4-AF3B-ACA4F1DDBDCC.html){:new_window}. Performance charts are available for clusters, hosts, physical disks, VMs, and virtual disks. |
| vSAN troubleshooting | For more information, see [Handling Failures and Troubleshooting vSAN](https://docs.vmware.com/en/VMware-vSphere/6.7/com.vmware.vsphere.vsan-monitoring.doc/GUID-0F3C4D3F-9B86-4879-9C60-D6A977523112.html){:new_window}. |


### Network
{: #opsprocs-trouble-common-network}

Table 4. Typical network troubleshooting

| Title | Description |
|---|---|
|  NSX Edge /var/log is getting full on active Edge | For information about a workaround if you are alerted that the Edge disk is filling up and discover that the /var/log partition is getting full, see [NSX Edge /var/log is getting full on active Edge (50108355)](https://kb.vmware.com/s/article/50108355){:new_window}.  |
| Testing HCX bandwidth  | For information about using 'perftest' to find the available bandwidth within the HCX tunnels if you believe that you have a network bandwidth issue with HCX, see [Steps to Run Perftest in HCX (56211)](https://kb.vmware.com/s/article/56211?lang=en_US){:new_window}. Bidirectional tests are carried out for each perftest. For the pair of gateways, one is inside the source data center, which we call OnPrem and the other one is in {{site.data.keyword.cloud_notm}}. The way perftest throughput works is to have the sender try to send as fast as the link can sustain. Therefore, for each test, you'll see higher "sender" rate than "receiver" rate and you can take the "receiver" rate as the number as one-way throughput result. |
| HCX troubleshooting | For more information, see [HCX troubleshooting](/docs/services/vmwaresolutions?topic=vmware-solutions-vcshcx-troubleshooting#vcshcx-troubleshooting){:new_window}. |
| HCX Syncing state with 0% progress and 0 bytes with status Error | For more information, see [HCX replication are in Syncing state with 0% progress and 0 bytes with status Error (56710)](https://kb.vmware.com/s/article/56710?lang=en_US#q=HCX){:new_window}. |
| Poor VM network performance | Review the VM virtual NIC settings. VMware recommend VMXNET 3 virtual NICs for VMs as it is the latest generation of paravirtualized NICs designed from the ground up for performance. Check for compatibility of VMXNET 3 using the VMware compatibility list, and if supported change the virtual NIC for additional network performance. For more information, see [Troubleshooting Networking](https://docs.vmware.com/en/VMware-vSphere/6.7/com.vmware.vsphere.networking.doc/GUID-217384C2-B361-471D-90C8-BC2676A0ECA6.html){:new_window}. |

### vCenter
{: #opsprocs-trouble-common-vcenter}

Table 5. Typical vCenter troubleshooting

| Title | Description |
|---|---|
| Virtual Machine Console Access | For more information, see [Knowledge - KB0012863 v0.01](https://watson.service-now.com/nav_to.do?uri=kb_knowledge.do?sys_id=5446a73cdb1db300c4fa302f9d961934){:new_window}. |
| New vCenter Server Certificate Does Not Appear to Load | After the replacement of the default vCenter Server certificates, the new certificates might not appear to load. For more information, see [New vCenter Server Certificate Does Not Appear to Load](https://docs.vmware.com/en/VMware-vSphere/6.7/com.vmware.vsphere.vcenterhost.doc/GUID-415CF843-42E8-4AD7-98EC-7265227337B6.html){:new_window}. |
| vCenter Server Cannot Connect to Managed Hosts | After the replacement of the default vCenter Server certificates and restarting the system, vCenter Server cannot connect to managed hosts. For more information, see [vCenter Server Cannot Connect to Managed Hosts](https://docs.vmware.com/en/VMware-vSphere/6.7/com.vmware.vsphere.vcenterhost.doc/GUID-8D3DCEC4-50B6-4523-BF24-0DE6C65600E9.html){:new_window}. |
| Cannot Configure vSphere HA When Using Custom SSL Certificates | After the installation of custom SSL certificates, attempts to enable vSphere High Availability (HA) fail. For more information, see [Cannot Configure vSphere HA When Using Custom SSL Certificates](https://docs.vmware.com/en/VMware-vSphere/6.7/com.vmware.vsphere.vcenterhost.doc/GUID-3FC16DC8-7157-4340-AB8A-B8DC87D7DC0F.html){:new_window}. |

### Licenses
{: #opsprocs-trouble-common-licenses}

Table 6. Typical license troubleshooting

| Title | Description |
|---|---|
|  Incompatible or incorrect license configuration | For more information, see [Troubleshooting Host Licensing](https://docs.vmware.com/en/VMware-vSphere/6.7/com.vmware.vsphere.vcenterhost.doc/GUID-B9DAAF47-94EC-47F5-8523-9C8C019412E1.html){:new_window}. |
|  VM does not power on | There may be a license issue if you can't power on a VM on a vSphere ESXi host and you receive the ``The 60-day evaluation period of the host is expired or the license of the host is expired`` message. For more information, see [Unable to Power On a Virtual Machine](https://docs.vmware.com/en/VMware-vSphere/6.7/com.vmware.vsphere.vcenterhost.doc/GUID-D4770546-9F9A-4F1E-AC1C-CF313E6130F4.html){:new_window}. |
| A feature is unavailable or inability to change a configuration  | For more information, see [Unable to Configure or Use a Feature](https://docs.vmware.com/en/VMware-vSphere/6.7/com.vmware.vsphere.vcenterhost.doc/GUID-26C0E2F0-A581-4A5A-B1F7-2BA4F151E27A.html){:new_window}.  |


## Related links
{: #opsprocs-trouble-links}
* [Contacting IBM Support](/docs/services/vmwaresolutions/archiref/solution?topic=vmware-solutions-trbl_support#trbl_support)
* [Troubleshooting Guidelines - KB0012073](https://watson.service-now.com/nav_to.do?uri=kb_knowledge.do?sys_id=4a205910dbe0f7c06001327e9d96197b){:new_window}
* [Troubleshooting with Log Files - KB0012074](https://watson.service-now.com/nav_to.do?uri=kb_knowledge.do?sys_id=c74f91d0dbe4f7c06001327e9d9619b1){:new_window}
* [Operations Management on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-opsmgmt-intro)
* [Support Log Gathering](https://kb.vmware.com/s/article/1010705){:new_window}
* [Monitoring Events, Alarms, and Automated Actions](https://docs.vmware.com/en/VMware-vSphere/6.5/com.vmware.vsphere.monitoring.doc/GUID-9272E3B2-6A7F-427B-994C-B15FF8CADC25.html){:new_window}
* [vSphere System Log Files](https://docs.vmware.com/en/VMware-vSphere/6.5/com.vmware.vsphere.monitoring.doc/GUID-DABCB024-E083-4A4D-8AE0-D1AF4CB3800C.html){:new_window}
* [Considerations about changing vCenter Server artifacts](/docs/services/vmwaresolutions?topic=vmware-solutions-vcenter_chg_impact#vcenter_chg_impact)
