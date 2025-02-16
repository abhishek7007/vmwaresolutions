---

copyright:

  years:  2016, 2019

lastupdated: "2019-05-13"

subcollection: vmware-solutions


---

# Integration, IP addressing, and network flows
{: #vcsnsxt-overview-integration}

## IBM Cloud Private and VMware vCenter Server on IBM Cloud integration
{: #vcsnsxt-overview-integration-icp-vcs-integration}

{{site.data.keyword.cloud}} Private is installed on several virtual machines (VMs) on a vCenter Server instance. Within the vCenter Server instance, the {{site.data.keyword.icpfull_notm}} instance is deployed with a dedicated NSX Edge Services Gateway (ESG) and Distributed Logical Router (DLR) and uses a VXLAN.

The ESG is configured with a source NAT rule (SNAT) to allow outbound traffic, which enables internet connectivity to download the {{site.data.keyword.icpfull_notm}} prerequisites and to connect to GitHub and Docker. Alternatively, you can use a web-proxy for internet connectivity. The ESG is configured with private connectivity to access DNS and NTP services. The ESG is also configured with a DNAT rule to enable the {{site.data.keyword.icpfull_notm}} Master and Proxy vIPs to be accessed from the {{site.data.keyword.cloud_notm}} 10.x network.

## IBM Cloud Kubernetes Service and vCenter Server integration
{: #vcsnsxt-overview-integration-iks-vcs-integration}

Currently, the following scenarios to integrate {{site.data.keyword.containerlong_notm}} and vCenter Server networking:
- **Common VLAN** - Requires that the {{site.data.keyword.containerlong_notm}} worker nodes are deployed onto the same VLAN as the vCenter Server instance. Common VLAN allows an ESG to be a BGP peer to the worker nodes.
- **strongSwan VPN** – This scenario uses the standard {{site.data.keyword.containerlong_notm}} to enterprise connectivity solution. A strongSwan container provides a VPN gateway for the cluster that forwards packets to remote networks across an IPSec tunnel to the remote gateway. This remote gateway is an ESG on the vCenter Server instance. On the gateways, routes are configure sending all cluster and service IP ranges to the strongSwan container and all vCenter Server BYOIP addresses to the ESG. The target IP addresses for the gateways are the private portable IP address of the load balancer service that is assigned to the strongSwan container and the private portable IP address of the ESG.
- **Static routes and NAT**.
- **BGP Peering** – BGP peering is not a default offering in {{site.data.keyword.cloud_notm}} and must be requested and approved. After enabled, BGP peering allows the Calico vRouters and the ESG to advertise routes to the BCR.

## IBM Cloud Kubernetes Service and IBM Cloud Private integration
{: #vcsnsxt-overview-integration-iks-icp-integration}

{{site.data.keyword.containerlong_notm}} and {{site.data.keyword.icpfull_notm}} integration uses strongSwan VPN connectivity with a strongSwan container in {{site.data.keyword.icpfull_notm}} and {{site.data.keyword.containerlong_notm}}.

## IP address allocation
{: #vcsnsxt-overview-integration-ip-address-allocation}

From an administrative perspective, the reference architecture has the following conceptual network ranges:
-	**{{site.data.keyword.containerlong_notm}} pod network** - All pods that are deployed to a worker node are assigned a private IP address in the 172.30.0.0/16 range and are routed between worker nodes only. To avoid conflicts, don't use this IP range on any nodes that communicate with your worker nodes. Worker nodes and pods can securely communicate on the private network by using private IP addresses. However, when a pod crashes or a worker node needs to be re-created, a new private IP address is assigned.
-	**{{site.data.keyword.containerlong_notm}} service network** – {{site.data.keyword.containerlong_notm}} uses 172.21.0.0/16 for service addresses within the cluster. The following are two other IP address ranges:
    - Public – A public portable subnet with an IP address range provided by {{site.data.keyword.cloud_notm}}. This IP address range is used to expose apps to the internet via ALB or Ingress services.
    - Private – A private portable subnet with an IP address range provided by {{site.data.keyword.cloud_notm}}. This IP address range is used to expose apps to the private network via ALB or Ingress services.
- **{{site.data.keyword.containerlong_notm}} worker nodes network** - There are two worker node network IP address ranges:
    - Public – A public primary subnet with an IP address range provided by {{site.data.keyword.cloud_notm}}.
    - Private – A private primary subnet with an IP address range provided by {{site.data.keyword.cloud_notm}}.
-	**vCenter Server host network** - There are two vCenter Server host network IP address ranges:
    - Public – A public primary subnet with an IP address range provided by {{site.data.keyword.cloud_notm}}.
    - Private – A private primary subnet with an IP address range provided by {{site.data.keyword.cloud_notm}}.
-	**vCenter Server ESG network** - There are two vCenter Server ESG network IP address ranges
    - Public – A public portable subnet with an IP address range provided by {{site.data.keyword.cloud_notm}}.
    - Private – A private portable subnet with an IP address range provided by {{site.data.keyword.cloud_notm}}.
-	**vCenter Server VM network** – An enterprise IP address range that uses a BYOIP range that does not clash with any {{site.data.keyword.cloud_notm}} provided subnet.
-	**{{site.data.keyword.icpfull_notm}} pod network** – An enterprise IP address range that uses a BYOIP range that does not clash with any {{site.data.keyword.cloud_notm}} provided subnet. Pod and service IP address ranges can be configured in cluster/config.yaml.
-	**{{site.data.keyword.icpfull_notm}} service network** – An enterprise IP address range that uses a BYOIP range that does not clash with any {{site.data.keyword.cloud_notm}} provided subnet. Pod and service IP address ranges can be configured in cluster/config.yaml.
-	**{{site.data.keyword.icpfull_notm}} worker nodes network** – An enterprise IP address range that uses a BYOIP range that does not clash with any {{site.data.keyword.cloud_notm}} provided subnet.

## Network traffic flows
{: #vcsnsxt-overview-integration-net-traffic-flows}

The following traffic flows are described:
-	External user on the internet to a web tier hosted in a container in {{site.data.keyword.containerlong_notm}}.
-	External user on the internet to a web tier hosted in a container in {{site.data.keyword.icpfull_notm}}.
-	Web tier hosted in a container in {{site.data.keyword.containerlong_notm}} to database tier hosted in a VM in vCenter Server.
-	Web tier hosted in a container in {{site.data.keyword.icpfull_notm}} to database tier hosted in a VM in vCenter Server.
-	Enterprise user on the corporate network access to a VM in vCenter Server.

### External user on the internet to a web tier hosted in a container in IBM Cloud Kubernetes Service
{: #vcsnsxt-overview-integration-web-tier-iks}

1.	The external user makes a request to the web tier by using the URL.
2.	DNS is used to determine the IP address. This IP address is an {{site.data.keyword.cloud_notm}} public address on a portable subnet that is assigned to the ALB or Ingress Service.
3.	The public network automatically forwardeds the request to worker node that hosts the ALB or Ingres Service.
4.	The worker node forwards the request to the internal cluster IP address and port number of the ALB or Ingress Service. This internal cluster IP address is accessible inside the cluster only.
5.	Within the worker node, kube-proxy routes the request to the ALB or Ingress Service.
6.	If the application is on the same worker node, then iptables is used to determine which internal interface is used to forward the request. If the application is on a different worker node, then the Calico vRouter routes to the applicable worker node, by using IP-in-IP encapsulation only if the worker node is on a different subnet.

### External user on the internet to a web tier hosted in a container in IBM Cloud Private
{: #vcsnsxt-overview-integration-web-tier-icp}

1.	The external user makes a request to the web tier by using the URL.
2.	DNS is used to determine the IP address. This IP address is an {{site.data.keyword.cloud_notm}} public address on a portable subnet that is assigned to the vCenter Server instance.
3.	The public network automatically forwards the request to the vSphere ESXi host that host the ESG.
4.	The ESG forwards the request to the internal cluster IP address and port number of the ALB or Ingress Service. The IP packet is encapsulated in a VXLAN frame if the ESG and the ALB or Ingress Service are on different vSphere ESXi hosts. This internal cluster IP address is accessible inside the cluster only.
5.	Within the worker node, kube-proxy routes the request to the ALB or Ingress Service.
6.	If the application is on the same worker node, then iptables is used to determine which internal interface is used to forward the request. If the application is on a different worker node, then the Calico vRouter routes to the applicable worker node, by using IP-in-IP encapsulation. The IP-in-IP packet is encapsulated in a VXLAN frame for transport to the vSphere ESXi host where the worker node is located.

### Web tier hosted in a container in IBM Cloud Kubernetes Service to database tier hosted in a VM in vCenter Server
{: #vcsnsxt-overview-integration-iks-db-tier-vcs}

How the route tables in the ESG and vRouters are populated depends on the method of integration. See {{site.data.keyword.containerlong_notm}} and vCenter Server integration.
1.	The web tier that is running in a container in {{site.data.keyword.containerlong_notm}} makes a request to a database that is running on a VM in the vCenter Server instance.
2.	DNS is used to resolve the request to the IP address of the database.
3.	The container sends the request to the Calico vRouter.
4.	The vRouter has its route table that is populated with the IP address ranges hosted on the vCenter Server instance.
5.	The vRouter forwards the request but uses SNAT to change the source IP address from the IP address of the pod to the IP address of the worker node.
6.	The worker node that hosts the vRouter sends the request to the BCR.
7.	The BCR forwards the request to the ESG.
8.	The ESG then forwards to the DLR.
9.	The DLR places the request onto the required VXLAN.
10.	The database VM receives the request.

### Web tier hosted in a container in IBM Cloud Private to database tier hosted in a VM in vCenter Server
{: #vcsnsxt-overview-integration-icp-db-tier-vcs}

How the route tables in the ESG and vRouters are populated depends on the method of integration. See {{site.data.keyword.icpfull_notm}} and vCenter Server integration.
1.	The web tier running in a container in {{site.data.keyword.icpfull_notm}} makes a request to a database running on a VM in the same vCenter Server instance.
2.	DNS is used to resolve the request to the IP address of the database.
3.	The container sends the request to the Calico vRouter.
4.	The vRouter has its route table that is populated with the IP address ranges hosted on the vCenter Server instance.
5.	The vRouter forwards the request but uses SNAT to change the source IP address from the IP address of the pod to the IP address of the worker node.
6.	The worker node hosting the vRouter sends the request to the ESG.
7.	The ESG then forwards to the DLR.
8.	The DLR places the request onto the required VXLAN.
9.	The database VM receives the request.

### Enterprise user on the corporate network access to a VM in vCenter Server
{: #vcsnsxt-overview-integration-corporate-network-vcs}

1.	An enterprise user connected to the enterprise internal network makes a request of a resource that is on a VM hosted in vCenter Server.
2.	DNS is used to determine the IP address of the VM. This IP address is on a network that has been stretched to {{site.data.keyword.cloud_notm}}.
3.	The on-premises router directs the traffic to the vSphere host that is hosting the L2 Concentrator.
4.	The L2 concentrator encapsulates the request in a secure tunnel and forwards it to the remote L2 Concentrator hosted in {{site.data.keyword.cloud_notm}} using the private portable subnet IP address that is assigned to the device, via the on-premises router.
5.	The on-premises route looks in its routing table and discerns that the IP address for the remote L2 Concentrator needs to be sent to the WAN interface and it forwards across the WAN, through the {{site.data.keyword.cloud_notm}} XCR router, via the BCR.
6.	The L2 Concentrator receives the request and places it on the VXLAN that hosts the stretched network.
7.	The VM receives the request.

## Related links
{: #vcsnsxt-overview-integration-related}

* [{{site.data.keyword.cloud_notm}} global data centers](https://www.ibm.com/cloud/data-centers/){:new_window}
* [Container white paper](https://communities.vmware.com/servlet/JiveServlet/download/2741654-198902/Containers%20and%20Container%20Networking%20for%20Network%20Engineers.pdf){:new_window} (PDF download)
* [VMware HCX on {{site.data.keyword.cloud_notm}} blog](https://www.ibm.com/cloud/blog/announcements/vmware-hcx-ibm-cloud-aka-really-cool-space-age-kind-now-available){:new_window}
* [VMware HCX on {{site.data.keyword.cloud_notm}} data sheet](https://www.ibm.com/downloads/cas/MPVXKWNM){:new_window}
* [VMware HCX on {{site.data.keyword.cloud_notm}} solution architecture](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcx-archi-intro#hcx-archi-intro)
* [NSX for vSphere 6.4.3 configuration maximums](https://configmax.vmware.com/guest){:new_window}
* [{{site.data.keyword.cloud_notm}} platform documentation](https://www.ibm.com/support/knowledgecenter/en/SSBS6K_3.1.0/kc_welcome_containers.html){:new_window}
* [{{site.data.keyword.containerlong_notm}}](/docs/containers?topic=containers-getting-started#getting-started)
* [Project Calico](https://www.projectcalico.org/){:new_window}
* [GitHub-Calico](https://github.com/projectcalico/calico){:new_window}
* [Kubernetes](https://kubernetes.io/){:new_window}
* [GitHub-Flannel](https://github.com/coreos/flannel/){:new_window}
* [GitHub-Canal](https://github.com/projectcalico/canal){:new_window}
