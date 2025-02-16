---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-18"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Expanding and contracting capacity for vCenter Server with Hybridity Bundle instances
{: #vc_hybrid_addingremovingservers}

You can expand or contract the capacity of your VMware vCenter Server on {{site.data.keyword.cloud}} with Hybridity Bundle instance according to your business needs, by adding or removing ESXi servers.

Starting with the V2.9 release, you can add new ESXi servers to a cluster while the cluster is in maintenance mode. Additionally, you can simultaneously add or remove ESXi servers across multiple clusters. The following simultaneous operations are available:

* Add hosts to a cluster and add hosts to additional clusters.
* Remove hosts from a cluster and remove hosts from additional clusters.
* Add hosts to a cluster and remove hosts from additional clusters.
* Remove hosts from a cluster and add hosts to additional clusters.

Because your initial cluster has vSAN as its storage, adding one or more ESXi servers after deployment can increase the cluster storage capacity.

## Adding ESXi servers to vCenter Server with Hybridity Bundle instances
{: #vc_hybrid_addingremovingservers-adding}

### Before you add ESXi servers
{: #vc_hybrid_addingremovingservers-adding-prereq}

* Whenever possible, add ESXi servers by using the {{site.data.keyword.vmwaresolutions_full}} console, because changes that you make on the VMware vSphere Web Client are not synchronized with the {{site.data.keyword.vmwaresolutions_short}} console. Therefore, add ESXi servers to vCenter Server only for on-premises ESXi servers or ESXi servers that you can't or won't manage in the {{site.data.keyword.vmwaresolutions_short}} console.
* vSAN storage requires at least 4 ESXi servers.

## Procedure to add ESXi servers
{: #vc_hybrid_addingremovingservers-adding-procedure}

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Resources** from the left navigation pane.
2. In the **vCenter Server Instances** table, click the instance for which you want to expand capacity.
3. Click **Infrastructure** on the left navigation pane.
4. In the **CLUSTERS** table, click the cluster to which you want to add ESXi servers.
5. In the **ESXi Servers** table, click **Add**.
6. In the **Add Server** window, enter the number of servers that you want to add.
7. Optionally, select the checkbox to add servers during maintenance mode.
8. Review the estimated cost and click **Add**.

### Results after you add ESXi servers
{: #vc_hybrid_addingremovingservers-adding-results}

1. You might experience a slight delay on the console while the instance status changes from **Ready to Use** to **Modifying**. Allow the operation to fully complete before you make more changes to the instance.
2. You're notified by email that your request to add ESXi servers is being processed. On the console, the status of the cluster that is associated with the ESXi servers is changed to **Modifying**.
3. If you don't see the new ESXi servers added to the list in the cluster, check the email or console notifications to find more details about the failure.

If you are adding ESXi servers during maintenance mode, virtual machines (VMs) are not migrated to the new servers until you remove the cluster from maintenance mode.   
{:important}

## Removing ESXi servers from vCenter Server with Hybridity Bundle instances
{: #vc_hybrid_addingremovingservers-removing}

### Before you remove ESXi servers
{: #vc_hybrid_addingremovingservers-removing-prereq}

* Whenever possible, remove ESXi servers by using the {{site.data.keyword.vmwaresolutions_full}} console, because changes that you make on the vSphere Web Client are not synchronized with the {{site.data.keyword.vmwaresolutions_short}} console. Therefore, remove ESXi servers from vCenter Server only for on-premises ESXi servers or ESXi servers that you can't or won't manage in the {{site.data.keyword.vmwaresolutions_short}} console.
* vSAN storage requires at least 4 ESXi servers.
* Before you remove ESXi servers with the F5 on {{site.data.keyword.cloud_notm}} or FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}} service installed, you must migrate the F5 BIG-IP and FortiGate VMs to a different ESXi server than the one that is hosting the VMs.
* Before you remove ESXi servers with the IBM Spectrum Protect&trade; Plus on {{site.data.keyword.cloud_notm}} service installed, ensure that there are no active (failed or in progress) backup or restore operations because these active operations might prevent the ESXi servers to be removed.
* When you remove ESXi servers, the servers are placed in maintenance mode, and after that, all the virtual machines (VMs) running on the servers are migrated before they are removed from vCenter Server. For maximum of control over the relocation of VMs, it is recommended that you place the ESXi servers to be removed in maintenance mode and migrate the VMs running on them manually using the VMware vSphere Web Client. After that, remove the ESXi servers using the {{site.data.keyword.vmwaresolutions_short}} console.

## Procedure to remove ESXi servers
{: #vc_hybrid_addingremovingservers-removing-procedure}

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Resources** from the left navigation pane.
2. In the **vCenter Server Instances** table, click the instance for which you want to contract capacity.
3. Click **Infrastructure** on the left navigation pane.
4. In the **CLUSTERS** table, click the cluster from which you want to remove ESXi servers.
5. In the **ESXi Servers** table, select the servers that you want to remove and click **Remove**.

### Results after removing ESXi servers
{: #vc_hybrid_addingremovingservers-removing-results}

1. You might experience a slight delay on the console while the instance status changes from **Ready to Use** to **Modifying**. Allow the operation to fully complete before making additional changes to the instance.
2. You are notified by email that your request to remove ESXi servers is being processed. On the console, the status of the cluster associated with the ESXi servers is changed to **Modifying**.
3. The ESXi servers are fully reclaimed by {{site.data.keyword.cloud_notm}} infrastructure at the end of the {{site.data.keyword.cloud_notm}} infrastructure billing cycle, which is typically 30 days.

   You are billed until the end of the {{site.data.keyword.cloud_notm}} infrastructure billing cycle for the removed ESXi servers.
   {:note}

## Related links
{: #vc_hybrid_addingremovingservers-related}

* [vCenter Server Bill of Materials](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_bom)
* [Requirements and planning for vCenter Server with Hybridity Bundle instances](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_planning)
* [Adding, viewing, and deleting clusters for vCenter Server with Hybridity Bundle instances](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_addingviewingclusters)
* [Place a host in maintenance mode](https://docs.vmware.com/en/VMware-vSphere/6.0/com.vmware.vsphere.resmgmt.doc/GUID-8F705E83-6788-42D4-93DF-63A2B892367F.html){:new_window}
* [Enhanced vMotion Compatibility (EVC) processor support](https://kb.vmware.com/s/article/1003212){:new_window}
