---

copyright:

  years:  2016, 2019

lastupdated: "2019-01-25"

---

{:faq: data-hd-content-type='faq'}

# VMware Federal インスタンスのネットワーキングに関する考慮事項

VMware Federal インスタンスに関するネットワーキングの考慮事項と要件について詳しくは、以下の情報を確認してください。 インスタンスが正常に機能するように、要件を満たしていることを確認してください。

## VMware Federal インスタンスに関するネットワーキング・コンポーネント
{: faq}

VMware Federal インスタンスに含まれているネットワーキング・コンポーネントを確認するには、[{{site.data.keyword.cloud}} インスタンスの技術仕様](/docs/services/vmwaresolutions/vcenter/vc_fed_overview.html#technical-specifications-for-vmware-federal-on-ibm-cloud-instances)を参照してください。

## ファイアウォールに関する考慮事項

ファイアウォールを使用している場合は、IBM CloudDriver 仮想サーバー・インスタンス (VSI) と SDDC Manager 仮想マシン (VM) からのすべての通信に関してルールを構成する必要があります。 これらのルールでは、すべてのプロトコルが IP アドレス `10.0.0.0/8` と `161.26.0.0/16` 上で通信できるよう許可する必要があります。 このようなファイアウォールの例としては、NSX Distributed Firewalls (DFW)、Vyatta ファイアウォールなどがあります。

## 仮想マシンでの NSX の使用

VMware Federal インスタンスのデプロイ時に、インスタンス内で VMware NSX の注文、インストール、ライセンス交付、構成が行われます。 また、NSX Manager、NSX Controllers、および NSX Transport Zone がセットアップされ、各 ESXi サーバーに NSX コンポーネントが構成されます。

ワークロード仮想マシン (VM) で使用するための NSX Edge Services Gateway もデプロイされます。 詳しくは、[ユーザー管理の NSX ESG を VM で使用するためのネットワークの構成](/docs/services/vmwaresolutions/vcenter/vc_esg_config.html#configuring-your-network-to-use-the-customer-managed-nsx-esg-with-your-vms)を参照してください。

## NSX コンポーネントのパスワードを変更する際の考慮事項

NSX Manager、NSX Controllers、NSX Edges のパスワードを変更する前に、以下の考慮事項を確認してください。
* {{site.data.keyword.vmwaresolutions_short}} コンソールのインスタンスの**「サマリー」**ページに表示される NSX Manager のパスワードは変更しないでください。
* NSX Controller のパスワードは変更できます。 NSX Controller のパスワードを変更する方法については、[コントローラ パスワードの変更](https://docs.vmware.com/en/VMware-NSX-for-vSphere/6.2/com.vmware.nsx.admin.doc/GUID-2667DD9E-E2F5-4403-BAC2-C7D1BBC23228.html)を参照してください。
* ユーザー管理の VMware NSX Edge Services Gateway (ESG) のパスワードと SSH 設定を変更できます。 Management VMware NSX Edge Services Gateway (ESG) および関連する Distributed Logical Router のパスワードは変更しないでください。

### 関連リンク

* [NSX の概要](https://docs.vmware.com/en/VMware-NSX-for-vSphere/6.2/com.vmware.nsx-cross-vcenter-install.doc/GUID-10944155-28FF-46AA-AF56-7357E2F20AF4.html){:new_window}
* [NSX Edge Services Gateway](https://www.ibm.com/cloud/garage/architectures/implementation/virtualization_nsx){:new_window}
* [NAT ルールの管理](https://docs.vmware.com/en/VMware-NSX-for-vSphere/6.2/com.vmware.nsx.admin.doc/GUID-5896D8CF-20E0-4691-A9EB-83AFD9D36AFD.html){:new_window}
