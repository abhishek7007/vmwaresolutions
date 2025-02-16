---

copyright:

  years:  2016, 2019

lastupdated: "2019-05-03"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Expanding and contracting capacity for vCenter Server instances
{: #vc_addingremovingservers}

You can expand or contract the capacity of your VMware vCenter Server instance according to your business needs, by adding or removing ESXi servers or network file system (NFS) storage.

* Starting with the V3.0 release you can simultaneously add or remove NFS storage and ESXi servers to clusters that are in the **Ready to Use** state. For example, you can add or remove an ESXi server in a cluster and add or remove NFS storage in another cluster.
* Starting with the V2.9 release, you can add new ESXi servers to a cluster while the servers are in maintenance mode. Additionally, you can simultaneously add or remove ESXi servers across multiple clusters.

**Notes**:
* If your initial cluster has vSAN as its storage, adding one or more ESXi servers after deployment can increase the cluster storage capacity.
* You can add or remove NFS storage shares to or from an existing NFS or vSAN vCenter Server cluster.

## Adding ESXi servers to vCenter Server instances
{: #vc_addingremovingservers-adding}

### Before you add ESXi servers
{: #vc_addingremovingservers-adding-prereq}

* Whenever possible, add ESXi servers by using the {{site.data.keyword.vmwaresolutions_full}} console, because changes that you make on the VMware vSphere Web Client are not synchronized with the {{site.data.keyword.vmwaresolutions_short}} console. Therefore, add ESXi servers to vCenter Server only for on-premises ESXi servers or ESXi servers that you can't or won't manage in the {{site.data.keyword.vmwaresolutions_short}} console.
* A vCenter Server instance with NFS storage must have at least 2 ESXi servers. For instances that are deployed in V2.1 or later, you can expand the default cluster to have up to 51 ESXi servers. Each of the non-default clusters can be expanded to have up to 59 ESXi servers.
* A vCenter Server instance with vSAN storage must have at least 4 ESXi servers.
* For vCenter Server instances that were deployed in V2.0 or earlier, you can expand each cluster to have up to 32 ESXi servers.
* You can add 1 - 20 ESXi servers at a time. For more information about the minimum of ESXi servers, see [Is a two-node vCenter Server instance highly available?](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-faq#is-a-two-node-vcenter-server-instance-highly-available-)

### Procedure to add ESXi servers
{: #vc_addingremovingservers-adding-procedure}

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Resources** from the left navigation pane.
2. In the **vCenter Server Instances** table, click the instance for which you want to expand capacity.
3. Click **Infrastructure** on the left navigation pane.
4. In the **CLUSTERS** table, click the cluster to which you want to add ESXi servers.
5. In the **ESXi Servers** section, click **Add**.
6. In the **Add Server** window, enter the number of servers that you want to add.
7. Optionally, select the checkbox to add servers during maintenance mode.
8. Review the estimated cost and click **Add**.

### Results after you add ESXi servers
{: #vc_addingremovingservers-adding-results}

1. You might experience a slight delay on the console while the instance status changes from **Ready to Use** to **Modifying**. Allow the operation to fully complete before you make more changes to the instance.
2. You are notified by email that your request to add ESXi servers is being processed. On the console, the status of the cluster that is associated with the ESXi servers is changed to **Modifying**.
3. If you do not see the new ESXi servers added to the list in the cluster, check the email or console notifications to find more details about the failure.
4. You must use the Zerto Virtual Manager (ZVM) console and the pre-populated Zerto Virtual Replication Appliance (VRA) IP address to manually deploy the VRA virtual machine (VM) in the following circumstances:
   * If you add ESXi servers to a default cluster while the servers are in maintenance mode and Zerto for {{site.data.keyword.cloud_notm}} is installed.
   * If you add Zerto for {{site.data.keyword.cloud_notm}} to a vCenter Server instance that has an ESXi server that is in maintenance mode.

If you are adding ESXi servers during maintenance mode, virtual machines are not migrated to the new servers until you remove maintenance mode.   
{:important}

## Removing ESXi servers from vCenter Server instances
{: #vc_addingremovingservers-removing}

### Before you remove ESXi servers
{: #vc_addingremovingservers-removing-prereq}

* Whenever possible, remove ESXi servers by using the {{site.data.keyword.vmwaresolutions_full}} console, because changes that you make on the vSphere Web Client are not synchronized with the {{site.data.keyword.vmwaresolutions_short}} console. Therefore, remove ESXi servers from vCenter Server only for on-premises ESXi servers or ESXi servers that you can't or won't manage in the {{site.data.keyword.vmwaresolutions_short}} console.
* A vCenter Server instance with NFS storage must have at least 2 ESXi servers and a vCenter Server instance with vSAN storage must have at least 4 ESXi servers.
* Before you remove ESXi servers with the F5 on {{site.data.keyword.cloud_notm}} or FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}} service installed, you must migrate the F5 BIG-IP and FortiGate VMs to a different ESXi server than the one that is hosting the VMs.
* Before you remove ESXi servers with the IBM Spectrum Protect&trade; Plus on {{site.data.keyword.cloud_notm}} service installed, ensure that there are no active (failed or in progress) backup or restore operations, because these active operations might prevent the ESXi servers to be removed.
* When you remove ESXi servers, the servers are placed in maintenance mode, and after that, all the virtual machines (VMs) running on the servers are migrated before they are removed from vCenter Server. For maximum of control over the relocation of VMs, it is recommended that you place the ESXi servers to be removed in maintenance mode and migrate the VMs running on them manually using the VMware vSphere Web Client. After that, remove the ESXi servers by using the {{site.data.keyword.vmwaresolutions_short}} console.

### Procedure to remove ESXi servers
{: #vc_addingremovingservers-removing-procedure}

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Resources** from the left navigation pane.
2. In the **vCenter Server Instances** table, click the instance for which you want to contract capacity.
3. Click **Infrastructure** on the left navigation pane.
4. In the **CLUSTERS** table, click the cluster from which you want to remove ESXi servers.
5. In the **ESXi Servers** section, select the servers that you want to remove and click **Remove**.

### Results after you remove ESXi servers
{: #vc_addingremovingservers-removing-results}

1. You might experience a slight delay on the console, while the instance status changes from **Ready to Use** to **Modifying**. Allow the operation to fully complete before you make more changes to the instance.
2. You are notified by email that your request to remove ESXi servers is being processed. On the console, the status of the cluster that is associated with the ESXi servers is changed to **Modifying**.
3. The ESXi servers are fully reclaimed by {{site.data.keyword.cloud_notm}} infrastructure at the end of the {{site.data.keyword.cloud_notm}} infrastructure billing cycle, which is typically 30 days.

   You are billed until the end of the {{site.data.keyword.cloud_notm}} infrastructure billing cycle for the removed ESXi servers.
   {:note}

## Adding NFS storage to vCenter Server instances
{: #section-adding-nfs-storage-to-vcenter-server-instances}

### Before you add NFS storage
{: #vc_addingremovingservers-adding-nfs-storage-prereq}

Do not add NFS storage from the VMware vSphere Web Client. The changes that you make on the vSphere Web Client are not synchronized with the {{site.data.keyword.vmwaresolutions_short}} console. IBM will not manage NFS file shares that you manually add to an instance.

### Procedure to add NFS storage
{: #vc_addingremovingservers-adding-nfs-storage-procedure}

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Resources** from the left navigation pane.
2. In the **vCenter Server Instances** table, click the instance for which you want to expand capacity.
3. Click **Infrastructure** on the left navigation pane.
4. In the **CLUSTERS** table, click the cluster to which you want to add NFS storage.
5. In the **Storage** section, click **Add**.
6. In the **Storage** window, complete the storage configuration.
   * If you want to add and configure the same settings to all file shares, specify the **Number of Shares**, **Performance**, and **Size (GB)**.
   * If you want to add and configure file shares individually, select **Configure shares individually**, then click the **+** icon next to the **Add Shared Storage** label and select the **Performance** and **Size (GB)** for each individual file share. You must select at least one file share.
7. Click **Add NFS Storage**.

### Results after you add NFS storage
{: #vc_addingremovingservers-adding-nfs-storage-results}

1. You might experience a slight delay on the console while the instance status changes from **Ready to Use** to **Modifying**. Allow the operation to fully complete before you make more changes to the instance.
2. You are notified by email that your request to add NFS storage is being processed. On the console, the status of the cluster that is associated with the NFS storage is changed to **Modifying**.
3. If you do not see the new NFS storage added to the list in the cluster, check the email or console notifications to find more details about the failure.

## Removing NFS storage from vCenter Server instances
{: #vc_addingremovingservers-removing-nfs-storage}

### Before you remove NFS storage
{: #vc_addingremovingservers-removing-nfs-storage-prereq}

* Do not remove NFS storage from the VMware vSphere Web Client. The changes that you make on the vSphere Web Client are not synchronized with the {{site.data.keyword.vmwaresolutions_short}} console.
* Before you remove the NFS storage, ensure that you removed all the VMs that reside on the storage.
* Ensure that the shares you plan to remove are associated with the correct vCenter Server instance.
* The cluster must be in **Ready to Use** status.

### Procedure to remove NFS storage
{: #vc_addingremovingservers-removing-nfs-storage-procedure}

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Resources** from the left navigation pane.
2. In the **vCenter Server Instances** table, click the instance for which you want to contract capacity.
3. Click **Infrastructure** on the left navigation pane.
4. In the **CLUSTERS** table, click the cluster from which you want to remove NFS storage.
5. In the **Storage** section, select the storage share that you want to remove and click **Delete**.
6. Click **Remove** in the **Remove Storage** window.

### Results after you remove NFS storage
{: #vc_addingremovingservers-removing-nfs-storage-results}

1. You might experience a slight delay on the console, while the instance status changes from **Ready to Use** to **Modifying**. Allow the operation to fully complete before you make more changes to the instance.
2. You are notified by email that your request to remove NFS storage is being processed. On the console, the status of the cluster that is associated with the NFS storage is changed to **Modifying**.
3. The NFS storage is fully reclaimed by {{site.data.keyword.cloud_notm}} infrastructure at the end of the {{site.data.keyword.cloud_notm}} infrastructure billing cycle, which is typically 30 days.

   You are billed until the end of the {{site.data.keyword.cloud_notm}} infrastructure billing cycle for the removed NFS storage.
   {:note}

## Related links
{: #vc_addingremovingservers-related}

* [vCenter Server Bill of Materials](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_bom)
* [Requirements and planning for vCenter Server instances](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_planning)
* [Ordering vCenter Server instances](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance)
* [Adding, viewing, and deleting clusters for vCenter Server instances](/docs/services/vmwaresolutions/services?topic=vmware-solutions-vc_addingviewingclusters#vc_addingviewingclusters)
* [Place a host in maintenance mode](https://docs.vmware.com/en/VMware-vSphere/6.0/com.vmware.vsphere.resmgmt.doc/GUID-8F705E83-6788-42D4-93DF-63A2B892367F.html){:new_window}
* [Enhanced vMotion Compatibility (EVC) processor support](https://kb.vmware.com/s/article/1003212){:new_window}
