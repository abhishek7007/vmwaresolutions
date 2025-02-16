---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-16"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# vCenter Server インスタンスからの Hybridity Bundle の削除
{: #vc_hybrid_deletingbundle}

vCenter Server インスタンスから Hybridity Bundle ライセンスを削除するには、VMware NSX および VMware vSAN のレンタル・ライセンス・キーを VMware vSphere Web Client のライセンス持ち込み (BYOL) キーに置き換える必要があります。 さらに、レンタル・ライセンスの料金を取り消すために、サポート・チケットを開く必要があります。

ライセンスをダウングレードすると、vCenter Server インスタンスに障害が起こる可能性があります。 自己責任でのライセンスのダウングレードを選択することもできますが、ダウングレード時に利用できなくなる機能についてまず考慮する必要があります。 詳しくは、[VMware コンポーネント・エディションの比較チャート](/docs/services/vmwaresolutions/archiref/solution?topic=vmware-solutions-solution-appendix)を参照してください。
{:important}

## Hybridity Bundle をマルチサイト環境から削除する前の重要な考慮事項
{: #vc_hybrid_deletingbundle-considerations}

Hybridity Bundle をマルチサイト環境から削除する前に、以下の考慮事項を確認してください。

* レンタル・ライセンスを削除する前に、すべてのマルチサイト・デプロイメントに BYOL ライセンスを適用する必要があります。
* VMware NSX ライセンスを結合し、すべてのマルチサイト・デプロイメントで使用するのに十分な容量を確保する必要があります。
* Hybridity バンドルをすべてのマルチサイト・デプロイメントから削除するには、単一のサポート・チケットを作成する必要があります。

マルチサイト環境から Hybridity バンドルを削除中に、BYOL ライセンスが適用されます。 マルチサイト構成に含まれるすべてのサイトでライセンス・エディションが統一されていることを確認するのはお客様の責任となります。
{:note}

## Hybridity Bundle を削除する前に
{: #vc_hybrid_deletingbundle-prereq}

Hybridity Bundle を削除する前に、以下の要件を確認してください。

* Hybridity Bundle を有効にした V2.4 以降の vCenter Server インスタンスがある。
* vCenter Server インスタンスに VMware HCX on {{site.data.keyword.cloud_notm}} サービスがインストールされていない。
* VMware vSphere Web Client に管理者としてアクセスできる。
* VMware NSX および各 VMware vSAN クラスターに適用する BYOL キーがある (まだ適用していない場合)。
* (オプション) VMware vCenter Server および VMware vSphere Enterprise Plus のライセンスに適用する BYOL キーがある (まだ適用していない場合)。

## Hybridity Bundle を削除する手順
{: #vc_hybrid_deletingbundle-procedure}

1. Hybridity Bundle を削除する VMware vSphere Web Client に、**管理者**としてログインします。
2. **「ホーム」>「管理」>「ライセンス」>「ライセンス」**をクリックします。
3. **「資産」**タブをクリックします。
4. 以下の手順を実行して、VMware NSX BYOL をインストールします。
   1. **「ソリューション」**タブをクリックします。
   2. NSX for vSphere を選択し、**「すべてのアクション」>「ライセンスの割り当て (Assign license)」**をクリックします。
   3. **「Add」**アイコンをクリックし、ライセンス・キーを入力します。 **「次へ」**をクリックします。
   4. ライセンスの名前を入力して、**「次へ」**をクリックします。 **「完了」**をクリックし、ライセンスを追加します。
   5. 新規のライセンス・キーを選択します。
   6. 適用するライセンスと置き換えられるライセンスの両方の完全なライセンス・キーを書き留めます。

   ライセンスの詳細は、この手順の後半で利用できるようにしておく必要があります。
   {:important}
   7. **「OK」**をクリックし、ライセンスを割り当てます。
5. 以下の手順を実行して、VMware vSAN BYOL をインストールします。
   1. **「クラスター」**タブをクリックします。
   2. vCenter Server インスタンスに関連付けられている vSAN クラスターごとに以下の手順を実行します。
    1. vSAN クラスターを選択し、**「すべてのアクション」>「ライセンスの割り当て (Assign license)」**をクリックします。
    2. **「Add」**アイコンをクリックし、ライセンス・キーを入力します。 **「次へ」**をクリックします。
    3. ライセンスの名前を入力して、**「次へ」**をクリックします。 **「完了」**をクリックし、ライセンスを追加します。
    4. 新規のライセンス・キーを選択します。
    5. クラスター名、および適用するライセンスと置き換えられるライセンスの両方の完全なライセンス・キーを書き留めます。

    ライセンスの詳細は、この手順の後半で利用できるようにしておく必要があります。
    {:important}
    6. **「OK」**をクリックし、ライセンスを割り当てます。
6. オプションで以下の手順を実行して、VMware vCenter Server BYOL をインストールします。
   1. **「vCenter Server システム (vCenter Server systems)」**タブをクリックします。
   2. vCenter Server を選択し、**「すべてのアクション」>「ライセンスの割り当て (Assign license)」**をクリックします。
   3. **「Add」**アイコンをクリックし、ライセンス・キーを入力します。 **「次へ」**をクリックします。
   4. ライセンスの名前を入力して、**「次へ」**をクリックします。 **「完了」**をクリックし、ライセンスを追加します。
   5. 新規のライセンス・キーを選択します。
   6. 適用するライセンスと置き換えられるライセンスの両方の完全なライセンス・キーを書き留めます。

   ライセンスの詳細は、この手順の後半で利用できるようにしておく必要があります。
   {:important}

   7. **「OK」**をクリックし、ライセンスを割り当てます。
7. オプションで以下の手順を実行して、VMware vSphere Enterprise Plus BYOL をインストールします。
  1. **「ホスト」**タブをクリックします。
  2. vCenter Server インスタンスに関連付けられているクラスターごとに以下の手順を実行します。vCenter Server に関連付けられているすべてのクラスターに同じライセンスが適用されている場合は、同時にすべてのクラスターに対して以下の手順を実行します。
    1. クラスターに関連付けられているすべてのホストを選択し、**「すべてのアクション」>「ライセンスの割り当て (Assign license)」**をクリックします。
    2. **「Add」**アイコンをクリックし、ライセンス・キーを入力します。 **「次へ」**をクリックします。
    3. ライセンスの名前を入力して、**「次へ」**をクリックします。 **「完了」**をクリックし、ライセンスを追加します。
    4. 新規のライセンス・キーを選択します。
    5. クラスター名、および適用するライセンスと置き換えられるライセンスの両方の完全なライセンス・キーを書き留めます。

    ライセンスの詳細は、この手順の後半で利用できるようにしておく必要があります。 すべてのクラスター間でライセンス・キーが同じでない場合は、各ライセンス・キーに関連付けられているクラスター名を書き留めてください。
    {:important}

    6. **「OK」**をクリックし、ライセンスを割り当てます。
8. レンタル・ライセンスを削除します。
   1. **「ライセンス」**タブをクリックします。
   2. 手順 4 から 7 で置き換えられたライセンスを選択します。
   3. **「ライセンスの削除」**アイコンをクリックします。
9. サポート・チケットを開き、次の情報を入力して、レンタル・ライセンスの料金を取り消します。
  * vCenter Server インスタンスの名前。
  * vCenter Server インスタンスに関連付けられている ID。
  * この手順でインストールした BYOL ライセンス・キーのリスト。 該当する場合は、インスタンス名およびクラスター名とともに、vSphere および vSAN クラスターのライセンス・キーを入力します。
  * この手順で削除したレンタル・ライセンス・キーのリスト。 該当する場合は、インスタンス名およびクラスター名とともに、vSphere および vSAN クラスターのライセンス・キーを入力します。

  IBM サポートおよびオペレーション・チームが、{{site.data.keyword.cloud_notm}} インフラストラクチャー・アカウントの vCenter 管理レイヤーにアクセスし、レンタル・ライセンスが削除されたことを確認してから、Hybridity Bundle レンタル・ライセンス料金を取り消します。
  {:note}

## 関連リンク
{: #vc_hybrid_deletingbundle-related}

* [vCenter Server with Hybridity Bundle インスタンスの注文](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_orderinginstance)
* [vCenter Server with Hybridity Bundle インスタンスの表示](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_viewinginstances)
* [IBM サポートへのお問い合わせ](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support)
