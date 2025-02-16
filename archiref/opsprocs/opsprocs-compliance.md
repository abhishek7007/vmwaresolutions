---

copyright:

  years:  2016, 2019

lastupdated: "2019-05-16"

---

# Compliance
{: #opsprocs-compliance}

Compliance is a set of requirements necessary to meet the minimum controls established by either a regulatory agency or industry best practices. Regularity compliance frameworks are usually broad frameworks that provide guidance on a broad range of technology, whereas industry best practice from vendors are typically technology specific to address technological risks.

For your vCenter Server instance, we suggest that security is managed using a dedicated team post-deployment. This separation of duties should augment and monitor the security posture of your instance. HyTrust CloudControl may assist your teams with role-based separation.

HyTrust DataControl and KeyControl may assist you in delivering workload protection such as at-rest encryption and geo-fencing. You may be interested in deploying the Caveonix RiskForesight service to assist you in, not only your compliance requirements but also cyber-risk and forensic management.

The VMware Security Hardening Guides provide prescriptive guidance on how to deploy and operate VMware products in a secure manner. Guides for vSphere are provided in an easy to consume spreadsheet format, with rich metadata to allow for guideline classification and risk assessment. They also include script examples for enabling security automation. Comparison documents are provided that list changes in guidance in successive versions of the guide.

While many of the controls documented in the VMware Security Hardening Guides have been incorporated in the {{site.data.keyword.vmwaresolutions_full}} reference architecture and, therefore, automatically deployed, ensure that you tailor the security posture of the platform to your own needs and enterprise policy. The VMware Security Hardening Guides provide the technology specific controls required for you to carry out this review. Caveonix RiskForesight on {{site.data.keyword.cloud_notm}} automates this compliance task and provides additional regulatory agency guidance.

vRealize Operations Manager allows you to monitor VMware objects for violations against the compliance rules in the vSphere Security Configuration Guide. The compliance alerts trigger on the vCenter Server instance, hosts, virtual machines, distributed port groups, or distributed switches, allowing the investigation of the compliance violation. Additionally, for clients interested in Health Insurance Portability and Accountability Act (HIPAA) and Payment Card Industry Data Security Standard (PCI DSS) compliance, vRealize Operations Manager Compliance Packs can be downloaded from the VMWare Solutions Exchange website, licensed, and installed. These Compliance Packs provide Alerts, Policies, and Reports to validate the vSphere resources against the HIPAA and PCI hardening guides.


## Related links
{: #opsprocs-compliance-links}

* [VMware security hardening guide](https://www.vmware.com/uk/security/hardening-guides.html){:new_window}
* [vSphere security guide](https://docs.vmware.com/en/VMware-vSphere/6.7/vsphere-esxi-vcenter-server-67-security-guide.pdf){:new_window}
* [Fortigate Security Appliance on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/archiref/solution?topic=vmware-solutions-fsa_considerations#fsa_considerations)
* [Fortigate Virtual Appliance on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/archiref/solution?topic=vmware-solutions-fortinetvm_considerations#fortinetvm_considerations)
* [F5 on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/archiref/solution?topic=vmware-solutions-f5_considerations#f5_considerations)
* [HyTrust CloudControl on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services/htcc_considerations.html#hytrust-cloudcontrol-on-ibm-cloud-overview)
* [HyTrust DataControl on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services/htdc_considerations.html#hytrust-datacontrol-on-ibm-cloud-overview)
* [HyTrust KeyControl on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services/htkc_considerations.html#hytrust-keycontrol-on-ibm-cloud-overview)
* [Caveonix RiskForesight on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/archiref/caveonix/caveonix-intro.html#caveonix-riskforesight)
* [Operations Management on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-opsmgmt-intro)
