---

copyright:

  years:  2016, 2019

lastupdated: "2019-03-04"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Viewing NetApp ONTAP Select instances
{: #np_viewinginstances}

View the summary and detailed information of the NetApp ONTAP Select instances that are provisioned for different user accounts.

## Procedure to view the NetApp ONTAP Select instances summary
{: #np_viewinginstances-procedure-view-inst-summary}

To view a summary of all the NetApp ONTAP Select instances that are provisioned for a user account, complete the following steps:

1. From the {{site.data.keyword.vmwaresolutions_full}} console, click **Resources** on the left navigation pane.
2. From the console banner, click your user account icon, and then click the **Account** field to select the user account that you want to check instances for.
3. In the **NetApp ONTAP Select Instances** table, view the list of instances that are provisioned in the selected user account.

Table 1. NetApp ONTAP Select instance items

| Item        | Description       |  
|:------------- |:--------------- |
| Name | The name of the instance. |
| Version | The version of the instance. |  
| Location | The data center where the instance is hosted. |
| Creation time | The date and time that the instance was created. |   
| Status | The status of the instance. The status can have one of the following values:<ul><li>Creating: The instance is being created.</li><li>Building: The instance is being configured.</li><li>Ready to Use: The instance is ready to use.</li><li>Modifying: The instance is being modified.</li><li>Failed: The creation, configuration, or modification process failed.</li><li>Deleting: The instance is being deleted.</li><li>Deletion Error: An error occurred when the instance was being deleted.</li><li>Deleted: The instance is deleted.</li></ul>|

## Procedure to view NetApp ONTAP Select instances property details
{: #np_viewinginstances-procedure-view-inst-property}

To view the property details of an instance:

1. In the **NetApp ONTAP Select Instances** table, click an instance name.
2. Under **Properties**, view the details for the instance.

Table 2. NetApp ONTAP Select instance properties

| Property        | Description       |
|:--------------- |:----------------- |
| Name | The name of the instance. |
| ID | The ID of the instance. |
| Location | The data center where the instance is hosted. |
| Deployed version | The deployed version of {{site.data.keyword.vmwaresolutions_short}}. |
| vCenter version | The version of VMware vCenter Server.<br><br>**Note**: There is a slight variation between the vCenter Server version that is displayed on the {{site.data.keyword.vmwaresolutions_short}} console and the VMware vSphere Web Client. Both are correct. |
| NSX for vSphere | The VMware NSX for vSphere product version. |
| NSX license edition | The version and edition of the VMware NSX license. |
| NetApp version | The version of NetApp ONTAP Select. |
| NetApp license type | The type of the NetApp ONTAP Select license. |
| DNS, Root Domain | The root domain name is the DNS (Domain Name System) domain name and the Microsoft Active Directory (AD) forest root name for the instance. |
| DNS, SSO Domain | The SSO domain is the vSphere Single Sign-On domain. The SSO domain name is set for all deployed NetApp ONTAP Select instances with a value of `vsphere.local`. |
| DNS, Subdomain | The subdomain is the DNS subdomain name of the root domain name where the local NetApp ONTAP Select instance host names reside. The subdomain name is in the format `<subdomain_label>.<root_domain>`. |
| Status | The status of the instance. |

## Procedure to view access information for NetApp ONTAP Select instances
{: #np_viewinginstances-procedure-view-inst-access-info}

Under **Access Information**, view the access information for the instance-related components. These passwords are initial passwords that are generated by the system. If you change them outside of the {{site.data.keyword.vmwaresolutions_short}} console, they are not updated on the instance summary page.

Table 3. Access information for NetApp ONTAP Select instance-related components

| Component        | Description       |
|:---------------- |:----------------- |
| AD/DNS IPs | The IP addresses of the two AD servers. |
| AD/DNS FQDN | The AD/DNS server fully qualified domain name. |
| AD/DNS ADMIN (Remote Desktop) | The user name and password that you can use to access the AD server via a remote desktop connection. |
| NSX Manager IP | The IP address of the NSX Manager. |
| NSX Manager FQDN | The NSX Manager fully qualified domain name. |
| NSX Manager HTTP | The user name and password that you can use to access the NSX Manager web console. |
| NetApp Cluster IP | The IP address of the NetApp ONTAP Select cluster. |
| NetApp Cluster FQDN | The NetApp ONTAP cluster fully qualified domain name. |
| NetApp Cluster HTTPS | The user name and password that you can use to access the NetApp ONTAP Select cluster. |
| NetApp Deploy Tool IP | The IP address of the NetApp ONTAP Select Deploy virtual machine. |
| NetApp Deploy Tool FQDN | The NetApp ONTAP Select Deploy fully qualified domain name. |
| NetApp Deploy Tool HTTPS | The user name and password that you can use to access the NetApp ONTAP Select Deploy virtual machine. |
| vCenter IP | The IP address of the vCenter Server. |
| vCenter FQDN | The vCenter Server fully qualified domain name. |
| vCenter ADMIN | The VMware vCenter Single Sign-On user name and password that you can use to log in to the vCenter Server by using the vSphere Web Client. |
| vCenter SSH | The user name and password that you can use to access the vCenter Server VM via SSH connection. |

## Procedure to view the deployment history for NetApp ONTAP Select instances
{: #np_viewinginstances-procedure-view-inst-deploy-history}

Click **Deployment History** from the left navigation pane to view the deployment history for the instance.

Table 4. NetApp ONTAP Select instance deployment history

| Item        | Description       |  
|:------------|:------------- |
| Date | The date and time when the instance status is changed |
| Summary | The details of the change |

If errors occur during instance deployment or instance deletion, the {{site.data.keyword.cloud_notm}} Support team is automatically notified. To inquire about the status of your ticket, you can [contact IBM Support](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support).

## Procedure to view NetApp ONTAP Select clusters
{: #np_viewinginstances-procedure-view-cluster}

1. Click **Infrastructure** from the left navigation pane.
2. Under **CLUSTERS**, view the summary about the NetApp ONTAP Select clusters.

	Table 5. NetApp ONTAP Select clusters items

	 <table>
	   <tr>
	     <th>Item</th>
	     <th>Description</th>
	   </tr>
	   <tr>
	     <td>Name</td>
	     <td>The name of the cluster.</td>
	   </tr>
	   <tr>
	     <td>ESXi servers</td>
	     <td>The number of ESXi servers in the cluster.</td>
	   </tr>
	   <tr>
	      <td>CPU</td>
	      <td>The CPU specification of the ESXi servers in the cluster.</td>
	   </tr>
	   <tr>
	      <td>Effective storage</td>
	      <td>The total disk capacity of the ESXi servers in the cluster.</td>
	   </tr>
	   <tr>
	      <td>Memory</td>
	      <td>The total memory size of the ESXi servers in the cluster.</td>
	   </tr>
	   <tr>
	      <td>Data center location</td>
	      <td>The data center where the cluster is hosted. It is same with the data center location of the instance.</td>
	   </tr>
		 <tr>
		   <td>Pod</td>
			 <td>The pod in which the cluster is created.</td>
		 </tr>
		 <tr>
		  <td>Status</td>
			<td>The status of the cluster. The status can have one of the following values:<ul><li>Initializing: The cluster is being created and configured.</li><li>Modifying: The cluster is being modified.</li><li>Ready to Use: The cluster is ready to use.</li></ul></td>
		 </tr>
		 <tr>
		  <td>Actions</td>
			<td>Click the **Delete** icon to delete the cluster.</td>
		 </tr>
	 </table>

3. Click the cluster name to view its ESXi server details.

Table 6. ESXi server details of a NetApp ONTAP Select cluster

| Item        | Description       |  
|:------------|:----------------- |
| Name | The name of the ESXi server is in the format `<host_prefix><n>.<subdomain_label>.<root_domain>`, where:<br><br>`host_prefix` is the host name prefix, `n` is the sequence of the server, `subdomain_label` is the subdomain label, and `root_domain` is the root domain name. |
| Version | The version of the ESXi server. |
| Credentials | The user name and password to access the ESXi server. |
| Private IP | The private IP address of the ESXi server. |
| Status | The status of the ESXi server, which can be one of the following values:<ul><li>Active: The ESXi server is ready for use.</li><li>Deleting: The ESXi server is being deleted.</li></ul> |

## What to do next
{: #np_viewinginstances-next}

Manage your instances from the {{site.data.keyword.vmwaresolutions_short}} console, the VMware vSphere Web Client, or the NetApp console.

Before you click **vCenter console** on the instance summary page to go to the vSphere Web Client and start managing your ESXi servers, you must log in to the VPN portal of the {{site.data.keyword.CloudDataCent_notm}}. Hover over the **vCenter console** button and follow the instructions to ensure that you meet all requirements and you completed the necessary steps before you access the vSphere Web Client.
{:important}

For more information to help you complete the login instructions, review the following topics:

*  For the requirements and necessary steps before you access the vSphere Web Client, see [Timeout reached while connecting to the vSphere Web Client](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_timeout_vc_console).
*  For a list of access points to log in to the {{site.data.keyword.cloud_notm}} infrastructure Private Network using VPN, see [VPN Access](http://www.softlayer.com/vpn-access){:new_window}.
*  If you have problems when you deploy an OVF (Open Virtualization Format) file using the vSphere Web Client, see [Deploying an OVF file using the vSphere Web Client](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_deploy_ovf).

## Related links
{: #np_viewinginstances-related}

* [Ordering NetApp ONTAP Select instances](/docs/services/vmwaresolutions/netapp?topic=vmware-solutions-np_orderinginstances)
* [Deleting NetApp ONTAP Select instances](/docs/services/vmwaresolutions/netapp?topic=vmware-solutions-np_deletinginstance)
* [Attach dedicated storage to NetApp ONTAP Select deployments](https://developer.ibm.com/recipes/tutorials/steps-to-attach-dedicated-storage-to-existing-ic4v-deployments-on-ibm-cloud/)
