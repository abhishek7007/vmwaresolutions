---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-22"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# vCenter Server インスタンスのサービスの注文、表示、削除
{: #vc_addingremovingservices}

災害復旧ソリューションなど、VMware vCenter Server インスタンス向けのサービスを注文できます。 これらのサービスが不要になった場合は、インスタンスから削除できます。

## vCenter Server インスタンスで使用可能なサービス
{: #vc_addingremovingservices-available-services}

vCenter Server インスタンスで使用できるサービスと、インストール済みのサービスのバージョンを以下の表にまとめます。

表 1. vCenter Server インスタンスに使用可能なサービス

| サービス名 | 現在のサービスのバージョン | インスタンスのバージョン |
|----------------------------------------------------------------------------------------|------------------|
| [Caveonix RiskForesight on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-caveonix_considerations) | 2.2 | V2.9 以降 |
| [F5 on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-f5_considerations) | BIG-IP VE v14.1.0.2 | V1.9 以降 |
| [FortiGate Security Appliance on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-fsa_considerations) | 300 シリーズ | V2.0 以降 |
| [FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-fortinetvm_considerations) | 6.0.3 | V2.0 以降 |
| [HyTrust CloudControl on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-htcc_considerations) | 5.5 | V2.3 以降 |
| [HyTrust DataControl on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-htdc_considerations)  | 4.3 | V2.3 以降 |
| [HyTrust KeyControl on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-htkc_considerations) | 4.3 | V2.5 以降 |
| [{{site.data.keyword.cloud_notm}} Private Hosted](/docs/services/vmwaresolutions/services?topic=vmware-solutions-icp_overview) | 3.1.2 | V2.5 以降 |
| [IBM Spectrum Protect&trade; Plus on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-spp_considerations) | 10.1.3 | V2.2 以降 |
| [KMIP for VMware on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-kmip_standalone_considerations) | 2.0  | N/A  |
| [Veeam on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-veeam_considerations) | 9.5u4 | V1.8 以降 |
| [Zerto on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-addingzertodr) | 6.5 update 3 | V1.2 以降 |

## vCenter Server インスタンスにサービスを追加する手順
{: #vc_addingremovingservices-adding-procedure}

vCenter Server インスタンスにサービスを追加するには、前のテーブルで該当サービスのリンクをクリックし、そのサービスに関する考慮事項を確認し、デプロイするコンポーネントにチェック・マークを付けます。 その後、サービス注文トピックに記されている指示に従って、インスタンスにサービスを追加します。

### サービスのインストールの結果
{: #vc_addingremovingservices-adding-results}

サービスのインストールが正常に完了すると、E メールで通知が届きます。また、そのサービスがインスタンスの**「サービス」**ページに表示され、サービスの状況が**「インストール済み」**になります。

## vCenter Server インスタンス用サービスを表示する手順
{: #vc_addingremovingservices-viewing-procedure}

1. {{site.data.keyword.vmwaresolutions_short}} コンソールで、左側のナビゲーション・ペインの**「リソース」**をクリックします。
2. **「vCenter Server インスタンス」**テーブルで、サービスを表示するインスタンスをクリックします。
3. 左側のナビゲーション・ペインの**「サービス」**をクリックします。
4. **「サービス」**ページでサービスをクリックし、そのサービスの情報 (サービス状況などの詳細) を確認します。
5. 表示したサービスによっては、サービスの詳細情報に記されている資格情報を使用してサービス・コンソールにアクセスし、そこからサービスを管理することもできます。

## vCenter Server インスタンス用サービスを削除する手順
{: #vc_addingremovingservices-removing-procedure}

1. {{site.data.keyword.vmwaresolutions_short}} コンソールで、左側のナビゲーション・ペインの**「リソース」**をクリックします。
2. **「vCenter Server インスタンス」**テーブルで、サービスを削除するインスタンスをクリックします。
3. 左側のナビゲーション・ペインの**「サービス」**をクリックします。
4. **「サービス」**ページで、削除するサービス・インスタンスを見つけて**「削除」**アイコンをクリックします。
5. **「サービスの削除」**ウィンドウで、考慮事項または警告が示されているなら、それを確認します。 **「了解」**を選択し、**「削除」**をクリックします。

### サービスの削除結果
{: #vc_addingremovingservices-removing-results}

サービスの削除要求が受け入れられると、サービス状況が**「削除中」**に変更されます。

サービスの削除が正常に完了すると、お客様に E メールで通知され、サービスがインスタンスの**「サービス」**ページから削除されます。

削除したサービスは、{{site.data.keyword.cloud_notm}} インフラストラクチャーの請求サイクルの最後まで課金されます。
{:note}

## 関連リンク
{: #vc_addingremovingservices-related}

* [よくある質問](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-faq)
