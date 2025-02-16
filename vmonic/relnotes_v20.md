---

copyright:

  years:  2016, 2017

lastupdated: "2017-11-20"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Release notes for V2.0
{: #relnotes_v20}

This release includes new features, component updates, usability enhancements, and bug fixes. For a list of fixed issues in different releases, known issues with the product, and tips to use {{site.data.keyword.vmwaresolutions_full}}, see [{{site.data.keyword.vmwaresolutions_short}} dW Answers](https://developer.ibm.com/answers/topics/cloudvmw/){:new_window}.

## FortiGate Virtual Appliance on IBM Cloud
{: #relnotes_v20-fva}

The FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}} service is now available to V2.0 and later VMware Cloud Foundation instances and VMware vCenter Server instances. This service deploys a high-availability (HA) pair of FortiGate Virtual Appliances to your environment, which can help you to reduce risk by implementing critical security controls within your virtual infrastructure.

Order instances with the FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}} service included when you order your instance, or add this service to your existing instances later from the **Services** tab on the instance details page. Depending on your requirements, select one of the three deployment sizes and licensing options for this service. After the service is installed successfully, manage and configure firewall rules for the FortiGate Virtual Appliances from the FortiGate console.

For more information, see the following topics:
* [Components and considerations for FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-fortinetvm_considerations)
* [Managing FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-managingfortinetvm)

## Multiple service installation for F5 on IBM Cloud and FortiGate Virtual Appliance on IBM Cloud
{: #relnotes_v20-multiple-services}

You can now install multiple instances of the F5 on {{site.data.keyword.cloud_notm}} service and the FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}} service for a Cloud Foundation instance or a vCenter Server instance. When you select the F5 service or the FortiGate service during your instance order, you must specify a name for the service instance to distinguish it from the additional service instances that you install later.

After the instance deployment is completed, you can add more instances of the F5 or the FortiGate service by installing the service on the **Add Services** tab of the instance details page. You can add only one service instance at a time, and you must repeat the process for all the instances that you want to add for a service.

For more information, see [Ordering, viewing, and removing services for vCenter Server instances](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_addingremovingservices).

## Updates for FortiGate Security Appliance on IBM Cloud
{: #relnotes_v20-fsa}

In this release, the Fortinet on {{site.data.keyword.cloud_notm}} service is renamed to FortiGate Security Appliance on {{site.data.keyword.cloud_notm}}. The pair of FortiGate Security Appliances (FSAs) of the service is configured to be secure by default when they are deployed to your instance.
* If you deploy a pair of FSAs as part of a new Cloud Foundation instance or vCenter Server instance, the FSAs are configured to allow only the required outbound communications from your instance to the public network and deny all other communications.
* If you deploy a pair of FSAs as part of an existing Cloud Foundation instance or vCenter Server instance, the FSAs are configured with an explicit rule to allow all the required outbound management communications from your instance to the public network, and the FSAs are also configured with a rule to allow all other communications to ensure that your existing application traffic is not interrupted.

In all cases, you must manage the FSAs configuration carefully to allow only necessary communications and deny all other communications.

## Fully qualified domain name format consistency
{: #relnotes_v20-fqdn}

The fully qualified domain name (FQDN) is now represented in a consistent way for all instances. When you place an order, you can enter your own subdomain prefix and host name prefix to ensure that the industry convention for the FQDN format is followed. For example, `host-name-prefix<n>.subdomain-prefix.domain-name`.

For more information, see the following topics:
* [Ordering vCenter Server instances](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance)
* [Ordering new vSphere clusters](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_orderinginstances)

## Workload and storage estimates during an instance order
{: #relnotes_v20-estimates-order}

* During a VMware vSphere on {{site.data.keyword.cloud_notm}} order, you are provided with an estimate of how many virtual machines can run on the ordered instance.
* During a Cloud Foundation and vCenter Server order, you are provided with an estimate of the usable storage capacity for the ordered instance.

For more information, see the following topics:
* [Ordering vCenter Server instances](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance)
* [Ordering new vSphere clusters](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_orderinginstances)

## Updates for VMware Cloud Foundation instances
{: #relnotes_v20-vcf}

The current release applies the following component updates and improvements for new deployments:

* VMware vSphere Enterprise Plus 6.5u1 (5969303)
* VMware SDDC Manager 2.4
* VMware vCenter Server 6.5U1a
* VMware vSAN 6.6.1
* VMware NSX for vSphere 6.3.4
* VMware ESXi 6.5, Patch Release ESXi650-201710401-BG. Updates esx-base, esx-tboot, vsan, and vsanhealth VIBs (2151061). For more information about patch details, see [VMware vCenter Server Appliance Photon OS Security Patches](https://docs.vmware.com/en/VMware-vSphere/6.5/rn/vcenter-server-appliance-photonos-security-patches.html){:new_window}.

Existing instances (from releases V1.9 and earlier) cannot be upgraded to the component versions in this list.
{:note}

### Cluster support for Cloud Foundation instances
{: #relnotes_v20-vcf-cluster}

You can now use clusters to manage ESXi servers in Cloud Foundation instances that are deployed in V2.0 and later releases for better resource management and high availability. The ESXi servers that you configured when you ordered an instance are grouped as **SDDC-Cluster** by default.

You can view the cluster details or add up to a total of five clusters to an instance on the **Infrastructure** tab of the instance details page. When you are expanding or contracting capacity for an instance, you can select which cluster to add ESXi servers to or to remove ESXi servers from.

### Support for custom vSAN storage for Cloud Foundation instances
{: #relnotes_v20-custom-vsan-vcf}

You can now customize the vSAN storage configuration by selecting the number and size of the vSAN storage drives as part of your instance order.

### Choice of VMware vSAN license edition for Cloud Foundation instances: Advanced or Enterprise
{: #relnotes_v20-vsan-license}

You can now select the vSAN license edition that you want during the Cloud Foundation instance order. You can either purchase the license as part of your order, or Bring Your Own License (BYOL).

### New standardized IBM Bare Metal Server configurations for Cloud Foundation instances
{: #relnotes_v20-vcf-bare-metal}

The following Bare Metal Server configuration settings are now available:
* Small (Dual Intel Xeon E5-2650 v4 / 24 cores total, 2.2 GHz / 128 GB RAM / 12 disks)
* Large (Dual Intel Xeon E5-2690 v4 / 28 cores total, 2.6 GHz / 512 GB RAM / 12 disks)

The chassis has space for 12 disks. Not all slots are filled in. The **Small** configuration provides two 1.9 TB Micron 5100 MAX drives and the **Large** configuration provides four 3.8 TB Micron 5100 PRO drives.
{:note}

## Updates for VMware vCenter Server instances
{: #relnotes_v20-vcs}

The current release applies the following component updates for new deployments:

* VMware vSphere Enterprise Plus 6.5u1 (5969303)
* VMware vCenter Server 6.5U1a
* VMware vSAN 6.6.1
* VMware NSX for vSphere 6.3.4

vCenter Server customized orders with or without the VMware vSAN component always include a 12-disk chassis server. This server results in a slightly higher cost for the {{site.data.keyword.baremetal_short}} for the non-vSAN order case in the price estimate PDF.
{:note}

For more information about components, see [vCenter Server overview](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_vcenterserveroverview).

### Multi-site configuration support for vCenter Server instances
{: #relnotes_v20-vcs-multisite}

You can now deploy a single vCenter Server instance in addition to secondary instances that are attached to a primary instance. The multi-site configuration model uses a hub and spoke topology with a primary site and a maximum of seven secondary sites.

For more information, see [Multi-site configuration for vCenter Server instances](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_multisite).

### Support for custom vSAN storage for vCenter Server instances
{: #relnotes_v20-custom-vsan-vcs}

vSAN storage is now available on vCenter Server instances for both primary and secondary instances. It is available only when you select a user-customized configuration. You can now select the vSAN license edition (Advanced or Enterprise) that you want during the vCenter Server instance order. You can either purchase the license as part of your order, or Bring Your Own License (BYOL).

For more information, see [Ordering vCenter Server instances](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance).

### Bring Your Own License (BYOL) for VMware vCenter Server instances
{: #relnotes_v20-byol}

BYOL is now available to vCenter Server instances. Use one or more of your own vCenter Server, vSphere, vSAN, and NSX VMware licenses when you order vCenter Server instances.

For more information, see the following topics:
* [Ordering vCenter Server instances](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance)
* [Ordering new vSphere clusters](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_orderinginstances)

## Updates for VMware vSphere on IBM Cloud
{: #relnotes_v20-vss}

### New disk types for Bare Metal Servers
{: #relnotes_v20-disk-type}

For the VMware vSAN component, the following disk types are now available for {{site.data.keyword.baremetal_short}}:
* 960 GB SSD SED
* 1.9 TB SSD SED
* 3.8 TB SSD SED

**Notes**:
* 3.8 TB SSD SED drives are supported when they are made generally available in an {{site.data.keyword.CloudDataCent_notm}}.
* Orders with or without the VMware vSAN component always include a 12-disk chassis server. This server results in a slightly higher cost for the {{site.data.keyword.baremetal_short}} for the non-vSAN order case in the price estimate PDF.

For more information, see [Ordering new vSphere clusters](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_orderinginstances).

## Updates for NetApp ONTAP Select on IBM Cloud
{: #relnotes_v20-netapp}

### New bare metal server options
{: #relnotes_v20-netapp-bare-metal}

The following bare metal server configuration options are now available:
* **High Performance (Medium)** – Premium license / Dual Intel Xeon E5-2650 v4 (24 cores total, 2.2 GHz) / 128 GB RAM / 22 1.9 TB SSD drives capacity per node / Effective capacity of a 4-node cluster – 59 TB
* **High Performance (Large)** – Premium license / Dual Intel Xeon E5-2650 v4 (24 cores total, 2.2 GHz) / 128 GB RAM / 22 3.8 TB SSD drives capacity per node / Effective capacity of a 4-node cluster – 118 TB
* **High Capacity** – Standard license / Dual Intel Xeon E5-2650 v4 (24 cores total, 2.2 GHz) / 64 GB RAM / Ten 4 TB SATA drives capacity per node / Effective capacity of a 4-node cluster – 60 TB

3.8 TB SSD drives are supported when they are made generally available in an {{site.data.keyword.CloudDataCent_notm}}.
{:note}

For more information, see the following topics:
* [NetApp ONTAP Select overview](/docs/services/vmwaresolutions/netapp?topic=vmware-solutions-np_netappoverview)
* [Ordering NetApp ONTAP Select instances](/docs/services/vmwaresolutions/netapp?topic=vmware-solutions-np_orderinginstances)

## New and updated documentation
{: #relnotes_v20-new-docs}

VMware Cloud Foundation users can use step-by-step instructions along with VMware's NSX platform on the {{site.data.keyword.cloud_notm}} to allow virtual machines to communicate with each other and the internet. For more information, see [Setting up NSX for workload VMs on VMware Cloud Foundation on {{site.data.keyword.cloud_notm}} (VCF)](https://developer.ibm.com/recipes/tutorials/setting-up-nsx-for-workload-vms-on-vmware-cloud-foundation-on-ibm-cloud-vcf/){:new_window}.

## User interface updates and enhancements
{: #relnotes_v20-ui}

* The maximum number of ESXi servers that can be added to a cluster is now updated to 32 servers. The maximum number of clusters continues to be five.
* On the **Resources** page, the **ESXi servers** column in the instance summary tables is replaced by the **Version** column, in which you can find the release version that instances were deployed in or updated to.
* The version of the SDDC Manager for Cloud Foundation instances is now available on the instance details page.
* Various error messages and tooltip enhancements are available to assist you in selecting the appropriate setting on the user interface.
