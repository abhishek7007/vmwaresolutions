---

copyright:

  years:  2016, 2019

lastupdated: "2019-05-06"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Single-node Trial for Migration and App Modernization overview
{: #cloud_modern_bundle_overview}

The Single-node Trial for Migration and App Modernization allows you to test drive {{site.data.keyword.cloud_notm}} to migrate VMware workloads to the {{site.data.keyword.cloud}} and then modernize simple workloads using containers.

The Single-node Trial is a trial version of {{site.data.keyword.cloud_notm}} Private Hosted on VMware vCenter Server on {{site.data.keyword.cloud_notm}} that provides the Kubernetes management platform for containers and the single-tenant VMware platform that can be managed using the same tools as in on-premises environments. You can take advantage of the speed and scale of the cloud while maintaining the same level of control and visibility that is provided on-premises.

The trial is designed for migration of up to 20 simple development or test workloads using vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle and containerization of those workloads with the Kubernetes-based {{site.data.keyword.cloud_notm}} Private Hosted application development platform. Automation will install and configure VMware HCX in the {{site.data.keyword.cloud_notm}}, provide an on-premises HCX activation key, and install and configure a small development/test topology of {{site.data.keyword.cloud_notm}} Private Hosted in a matter of hours.

The Single-node Trial for Migration and App Modernization is for proof of concept (POC) only. Do not run production workloads on this environment. Management functions such as adding and removing hosts and clusters, ordering add-on services, and applying updates are not supported.
{:important}

To get the most out of the Single-node Trial instance, you can use [IBM On Demand Consulting for Hybrid Cloud](https://public.dhe.ibm.com/software/data/sw-library/services/ODC.pdf){:new_window} from [IBM Analytics Cloud Expert Services](https://www.ibm.com/analytics/us/en/services/cloud-expert-services.html){:new_window}, who can help you migrate your VMware workloads to the {{site.data.keyword.cloud_notm}}. Additionally, [{{site.data.keyword.cloud_notm}} Garage Services](https://www.ibm.com/cloud/garage/){:new_window} can help you accelerate application modernization through the latest cloud native practices.

This trial is intended for use up to 90 days. When you are finished with the trial, you can delete this environment and provision a new environment that meets your capacity needs.
{:note}

## Technical specifications for Single-node Trial for Migration and App Modernization instances
{: #cloud_modern_bundle_overview-tech-specs}

The following components are included in your Single-node Trial for Migration and App Modernization instance.

The availability and pricing of standardized hardware configurations might vary based on the {{site.data.keyword.CloudDataCent_notm}} that is selected for deployment.
{:note}

### Bare Metal Server
{: #cloud_modern_bundle_overview-bare-metal}

Dual Intel Xeon Gold 5120 Processor / 28 cores total, 2.2 GHz with 384 GB RAM) for up to about 20 VMs

#### CPU over-commits
{: #cloud_modern_bundle_overview-cpu}

* 16:1 CPU over-commit for vCenter Server management, HCX, and 20 customer workload VMs
* 11:1 CPU over-commit for {{site.data.keyword.cloud_notm}} Private

#### RAM over-commits
{: #cloud_modern_bundle_overview-ram}

* 1.22:1 RAM over-commit for a customer deployment of 20 workload VMs with 8 GB each
* 1:1 (no over-commit) for a customer deployment of nine workload VMs with 8 GB each

### NFS storage
{: #cloud_modern_bundle_overview-nfs-storage}

* 2 TB for management
* 1 TB for customer workload (for 20 customer VMs)
* 4 TB for {{site.data.keyword.cloud_notm}} Private Hosted

### Networking specifications for Single-node Trial for Migration and App Modernization instances
{: #cloud_modern_bundle_overview-networking-specs}

The following networking components are ordered:
*  10 Gbps dual public and private network uplinks
*  Three VLANs (Virtual LANs): one public VLAN and two private VLANs
*  One VXLAN (Virtual eXtensible LAN) with DLR (Distributed Logical Router) for potential east-west communication between local workloads that are connected to layer 2 (L2) networks. The VXLAN is deployed as a sample routing topology, which you can modify, build on it, or remove it. You can also add security zones by attaching more VXLANs to new logical interfaces on the DLR.
*  Two VMware NSX Edge Services Gateways:
  * A secure management services VMware NSX Edge Services Gateway (ESG) for outbound HTTPS management traffic, which is deployed by IBM as part of the management networking typology. This ESG is used by the IBM management VMs to communicate with specific external IBM management components that are related to automation.

    This ESG is not accessible to you and you cannot use it. If you modify it, you might not be able to manage the Single-node Trial for Migration and App Modernization instance from the {{site.data.keyword.vmwaresolutions_short}} console. In addition, note that using a firewall or disabling the ESG communications to the external IBM management components will cause {{site.data.keyword.vmwaresolutions_short}} to become unusable.
    {:important}
  * A secure customer-managed VMware NSX Edge Services Gateway for outbound and inbound HTTPS workload traffic, which is deployed by IBM as a template that can be modified by you to provide VPN access or public access.

### Virtual Server Instances
{: #cloud_modern_bundle_overview-vsi}

The following virtual server instances (VSIs) are ordered:

* A VSI for IBM CloudBuilder, which is cancelled after the instance deployment is completed.
* A Microsoft Windows Server VSI for Microsoft Active Directory (AD) is deployed and can be looked up. The VSI functions as the DNS for the instance where the hosts and VMs are registered.

### IBM-provided licenses and fees
{: #cloud_modern_bundle_overview-license-and-fee}

The following licenses are included with your Single-node Trial for Migration and App Modernization instance order.

* VMware vSphere Enterprise Plus 6.7u1
* VMware vCenter Server 6.5
* VMware NSX Service Providers Advanced Edition 6.4
* {{site.data.keyword.cloud_notm}} Private Hosted 3.1.2
* {{site.data.keyword.cloud_notm}} Automation Manager 3.1.2

Single-node Trial for Migration and App Modernization instances do not support Bring Your Own License.
{:note}

## Technical specifications for VMware HCX on IBM Cloud
{: #cloud_modern_bundle_overview-hcx-tech-specs}

The Single-node Trial for Migration and App Modernization includes HCX on {{site.data.keyword.cloud_notm}}. The following components are ordered and included in the HCX on {{site.data.keyword.cloud_notm}} service.

On-premises HCX instances include only licensing and activation.
{:note}

### An active/passive pair of VMware NSX Edge Services Gateways for HCX Management
{: #cloud_modern_bundle_overview-esg}

* CPU: 6 vCPU
* RAM: 8 GB
* Disk: 3 GB VMDK

### HCX Management Appliance - Virtual Machine
{: #cloud_modern_bundle_overview-hcx-mgmt-appliance}

* CPU: 4 vCPU
* RAM: 12 GB
* Disk: 60 GB VMDK

Additional HCX appliances are deployed during configuration as necessary for L2 connectivity, WAN optimization, and gateway connections.

### Networking specifications for HCX on IBM Cloud
{: #cloud_modern_bundle_overview-hcx-networking-specs}

* One public portable subnet with 16 IP addresses
* Two private portable subnets with 64 IP addresses
* Eight IP addresses from private portable vMotion subnet

## Technical specifications for IBM Cloud Private Hosted
{: #cloud_modern_bundle_overview-icp-tech-specs}

{{site.data.keyword.cloud_notm}} Private Hosted 3.1.2 is installed using the Development/Test topology on all Single-node Trial for Migration and App Modernization instances. For more information about {{site.data.keyword.cloud_notm}} Private Hosted, see [{{site.data.keyword.cloud_notm}} Private Hosted overview](/docs/services/vmwaresolutions/services?topic=vmware-solutions-icp_overview).

## Technical specifications for IBM Cloud Automation Manager
{: #cloud_modern_bundle_overview-cam-tech-specs}

{{site.data.keyword.cloud_notm}} Automation Manager 3.1.2 is installed using the Development/Test topology on all Single-node Trial for Migration and App Modernization instances. For more information about {{site.data.keyword.cloud_notm}} Automation Manager, see [{{site.data.keyword.cloud_notm}} Automation Manager documentation](https://www.ibm.com/support/knowledgecenter/en/SS2L37_3.1.2.0/kc_welcome.html){: new_window}.

## Related links
{: #cloud_modern_bundle_overview-related}

* [vCenter Server and {{site.data.keyword.cloud_notm}} Private guide](/docs/services/vmwaresolutions/archiref/vcsicp?topic=vmware-solutions-vcsicp-intro)
* [Open a Ticket for {{site.data.keyword.cloud_notm}} Private](https://www.ibm.com/mysupport/s/?language=en_US){:new_window}
* [VMware HCX resources](https://hcx.vmware.com/#/docs){:new_window}
* [VMware HCX User Guide](https://docs.vmware.com/en/VMware-HCX/services/user-guide/GUID-BFD7E194-CFE5-4259-B74B-991B26A51758.html){:new_window}
