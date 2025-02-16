---

copyright:

  years:  2016, 2019

lastupdated: "2019-01-23"

---

{:tip: .tip}
{:note: .note}
{:important: .important}

# VMware Federal インスタンスのクラスターの追加、表示、削除

インスタンスの注文時に構成した ESXi サーバーは、デフォルトでは **cluster1** としてグループ化されます。

クラスターを VMware Federal インスタンスに追加して、コンピュート能力やストレージ容量を拡張できます。 クラスター内で ESXi サーバーを管理すると、リソース割り振りを改善したり高可用性を実現したりできます。 不要になった場合は、追加したクラスターをインスタンスから削除できます。

**利用可否:** クラスター追加/削除機能は、V2.3 以降のリリースでデプロイ (または V2.3 以降のリリースにアップグレード) されたインスタンスでのみ利用可能です。

## VMware Federal インスタンスへのクラスターの追加

インスタンスに追加できるクラスターの数は、インスタンスのバージョンに応じて以下のように異なります。
* V2.5 以降でデプロイ (または V2.5 以降にアップグレード) されたインスタンスの場合は、追加できるクラスター数の上限は、クラスター、ホスト、および VM の数によって決まります。 VMware のサイズ設定についてのガイドラインおよびデプロイに応じた上限を守る必要があります。
* V2.2 以降でデプロイ (または V2.2 以降にアップグレード) されたインスタンスの場合、最大 10 個のクラスターを追加できます。

上限について詳しくは、[VMware Configuration Maximums](https://configmax.vmware.com/home){:new_window} を参照してください。

### システム設定

VMware Federal インスタンスにクラスターを追加するときには、以下の設定を指定する必要があります。

#### クラスター名

クラスター名は、以下の要件を満たしている必要があります。
* 英数字とダッシュ (-) の文字だけを使用できます。
* クラスター名の先頭と末尾は、英数字でなければなりません。
* クラスター名の最大の長さは 30 文字です。
* クラスター名は、VMware Federal インスタンス内で固有でなければなりません。

#### データ・センターの場所

クラスターのデータ・センターは、デフォルトでは VMware Federal インスタンスのデータ・センターに設定されます。

### ベア・メタル・サーバーの設定

#### Skylake

ベア・メタル・サーバーの CPU モデルと RAM を指定します。 利用できるオプションは、インスタンスを最初にデプロイしたバージョンによって異なる場合があります。

表 1. Skylake {{site.data.keyword.baremetal_short}}のオプション

| CPU モデル・オプション        | RAM オプション       |
|:------------- |:------------- |
| Dual Intel Xeon Silver 4110 プロセッサー / 合計 16 コア、2.1 GHz | 64 GB、96 GB、128 GB、192 GB、384 GB、768 GB、1.5 TB |
| Dual Intel Xeon Gold 5120 Processor / 合計 28 コア、2.2 GHz | 64 GB、96 GB、128 GB、192 GB、384 GB、768 GB、1.5 TB |
| Dual Intel Xeon Gold 6140 Processor / 合計 36 コア、2.3 GHz | 64 GB、96 GB、128 GB、192 GB、384 GB、768 GB、1.5 TB |

#### Broadwell

ベア・メタル・サーバーの CPU モデルと RAM を指定します。 利用できるオプションは、インスタンスを最初にデプロイしたバージョンによって異なる場合があります。

表 2. Broadwell {{site.data.keyword.baremetal_short}}のオプション

| CPU モデル・オプション        | RAM オプション       |
|:------------- |:------------- |
| デュアル Intel Xeon E5-2620 v4 / 合計 16 コア、2.1 GHz | 64 GB、128 GB、256 GB、512 GB、768 GB、1.5 TB |
| デュアル Intel Xeon E5-2650 v4 / 合計 24 コア、2.2 GHz | 64 GB、128 GB、256 GB、512 GB、768 GB、1.5 TB |
| デュアル Intel Xeon E5-2690 v4 / 合計 28 コア、2.6 GHz | 64 GB、128 GB、256 GB、512 GB、768 GB、1.5 TB |

#### ベア・メタル・サーバーの数

クラスター 1 つにつき、2 つ以上の{{site.data.keyword.baremetal_short}}が必要です。

V2.3 以降でデプロイされた VMware Federal インスタンスの場合は、1 つのクラスターに最大 59 台の{{site.data.keyword.baremetal_short}}を追加できます。1 台から 59 台の ESXi サーバーを一度に追加できます。

デプロイメント後に、最大 4 つのクラスターを追加で作成できます。 vSAN ストレージ設定の場合、初期クラスターとデプロイメント後のクラスターの両方に 4 つのサーバーが必要です。

### ストレージ設定

ストレージ設定は、選択したベア・メタル・サーバー構成とストレージ・タイプによって異なります。

#### vSAN ストレージ

以下の vSAN オプションを指定します。
* **vSAN 容量ディスクのディスク・タイプとサイズ**: 必要な容量ディスクのオプションを選択します。
* **vSAN 容量ディスクの数**: 追加する容量ディスク数を指定します。
* 容量ディスクを上限の 8 個を超えて追加する場合は、**「High-Performance Intel Optane」**ボックスにチェック・マークを付けます。 このオプションでは、合計 10 個の容量ディスクに 2 つの追加の容量ディスク・ベイが提供されますので、より少ない待ち時間とより高い IOPS スループットが求められるワークロードを扱うときに役立ちます。

  **High-Performance Intel Optane** オプションは、Skylake の CPU モデルの Dual Intel Xeon Gold 5120 および Dual Intel Xeon Gold 6140 でのみ使用できます。
  {:note}

* **「Disk Type for vSAN Cache Disks」**および**「Number of vSAN Cache Disks」**の値を確認します。 これらの値は、**「High-Performance Intel Optane」**ボックスにチェック・マークを付けたかどうかによって異なります。
* **vSAN ライセンス**: VMware vSAN 6.6 ライセンス・エディション (Advanced または Enterprise) を選択します。

初期クラスターが vSAN クラスターとして追加された場合、追加の vSAN クラスターは同じ vSAN ライセンスを使用し、初期 vSAN クラスターと同じ構成になります。 インスタンス内のいずれかのクラスター (初期または追加) に対し、vSAN を選択してデプロイした場合も同様になります。 初めてクラスターを追加するときには、vSAN ライセンスとエディションを入力するように求められます。 次回に新規クラスター用に vSAN を選択するときには、初回に選択した内容が再使用されます。

#### NFS ストレージ

**「NFS Storage」**を選択する場合は、インスタンスにファイル・レベルの共有ストレージを追加し、すべての共有で同じ設定を使用することも、ファイル共有ごとに別々の構成設定を指定することもできます。 以下の NFS オプションを指定します。

ファイル共有の数は 1 から 32 までの範囲で指定する必要があります。
{:note}

* **Configure shares individually**: ファイル共有ごとに異なる構成設定を指定する場合に選択します。
* **Number of Shares**: どのファイル共有でも同じ構成設定を使用する場合に、追加する NFS 共有ストレージのファイル共有の数を指定します。
* **サイズ**: 共有ストレージのニーズを満たす容量を選択します。
* **パフォーマンス**: ワークロードの要件に基づいて、1 GB あたりの IOPS (入出力操作数/秒) を選択します。
* **ADD NFS**: 別々の構成設定を使用する個々のファイル共有を追加する場合に選択します。

表 3. NFS パフォーマンス・レベルのオプション

| オプション        | 詳細       |
  |:------------- |:------------- |
  | 2 IOPS/GB | このオプションは、最も汎用的なワークロード用に設計されています。 例えば、小規模なデータベースのホスト、Web アプリケーションのバックアップ、ハイパーバイザーの仮想マシン・ディスク・イメージなどの用途があります。 |
  | 4 IOPS/GB | このオプションは、同時に高い割合のデータがアクティブになる高負荷のワークロード用に設計されています。 例えば、トランザクション・データベースなどの用途があります。 |
  | 10 IOPS/GB | このオプションは、分析などの最も要求の厳しいワークロード・タイプ用に設計されています。 例えば、トランザクションの多いデータベースやその他のパフォーマンス重視のデータベースなどの用途があります。 このパフォーマンス・レベルは、ファイル共有あたり最大 4 TB の容量に制限されています。|

### ライセンス交付の設定

{{site.data.keyword.IBM}} では、以下の VMware コンポーネントのライセンスを提供しています。
  * vSphere Enterprise Plus 6.5u1
  * vCenter Server 6.5
  * NSX Service Providers 6.4 (Base、Advanced、または Enterprise エディション)
  * (vSAN クラスターの場合) vSAN 6.6 (Advanced または Enterprise エディション)

### 注文のサマリー

選択したクラスター構成に基づいて、見積もりコストがすぐに生成され、右側のペインの**「注文の要約」**に表示されます。

## VMware Federal インスタンスにクラスターを追加する手順

1. {{site.data.keyword.vmwaresolutions_short}} コンソールで、左側のナビゲーション・ペインの**「デプロイ済みインスタンス」**をクリックします。
2. **「vCenter Server インスタンス」**テーブルで、クラスターを追加するインスタンスをクリックします。

   インスタンスの状況が**「使用可能」**であることを確認してください。 そうでない場合、インスタンスにクラスターを追加できません。
   {:note}
3. 左側のナビゲーション・ペインにある**「インフラストラクチャー」**をクリックし、**「クラスター」**テーブルの右上隅にある**「追加」**をクリックします。
4. **「Add Cluster」**ページで、クラスター名を入力します。
5. ベアメタル構成として、**CPU モデル**、**RAM** の量、**ベア・メタル・サーバーの数**を選択します。
6. ストレージ構成を次の手順で実行します。
  * **「vSAN Storage」**を選択した場合は、容量ディスクおよびキャッシュ・ディスクのディスク・タイプとディスク数を指定します。 さらにストレージが必要な場合は、**「High-Performance Intel Optane」**ボックスにチェック・マークを付けます。
  * **「NFS Storage」**を選択し、すべてのファイル共有に同じ設定を追加して構成する場合は、**「Number of Shares」**、**「Size」**、**「Performance」**を指定します。
  * **「NFS Storage」**を選択し、ファイル共有を個別に追加して構成する場合は、**「Configure shares individually」**を選択し、ファイル共有ごとに、**「Add NFS」**ラベルの横にある**「+」**アイコンをクリックして、**「Size」**と**「Performance」**を選択します。 少なくとも 1 つのファイル共有を選択する必要があります。
7. ライセンス構成として、VMware vSAN のライセンス・エディションを選択します。
8. **「発注要約」**ペインで、クラスター構成を確認してからクラスターを追加します。
   1. クラスターの設定を確認します。
   2. クラスターの見積もりコストを確認します。 PDF のサマリーを生成するには、**「料金詳細」**をクリックします。 注文の要約を保存または印刷するには、PDF ウィンドウの右上隅にある**「印刷」**アイコンまたは**「ダウンロード」**アイコンをクリックします。
   3. 注文に適用される使用条件のリンクをクリックして、クラスターを追加する前にそれらの条件に同意することを確認する必要があります。
   4. **「プロビジョン」**をクリックします。

## VMware Federal インスタンスにクラスターを追加した結果

1. クラスターのデプロイメントが自動的に開始され、クラスターの状況が**「初期化中」**に変更されます。 デプロイメントの状況を、インスタンスのサマリー・ページでデプロイメント履歴を参照して確認できます。
2. クラスターを使用する準備ができると、状況が**「使用可能」**に変更されます。 新しく追加されたクラスターで、vSphere High Availability (HA) と vSphere Distributed Resource Scheduler (DRS) が有効になります。

クラスター名は変更できません。 クラスター名を変更すると、クラスター内の ESXi サーバーの追加または削除の操作が失敗することがあります。
{:important}

## VMware Federal インスタンスでクラスターを表示する手順

1. {{site.data.keyword.vmwaresolutions_short}} コンソールで、左側のナビゲーション・ペインの**「デプロイ済みインスタンス」**をクリックします。
2. **「vCenter Server インスタンス」**テーブルで、クラスターを表示するインスタンスをクリックします。
3. 左側のナビゲーション・ペインの**「インフラストラクチャー」**をクリックします。 **「クラスター」**表で、クラスターに関する要約を表示します。
   * **名前**: クラスターの名前。
   * **ESXi サーバー**: クラスター内の ESXi サーバー数。
   * **CPU**: クラスター内の ESXi サーバーの CPU 仕様。
   * **カスタマイズ vSAN ディスク**: クラスター内の vSAN ディスクの数 (ディスク・タイプおよび容量も含む)。
   * **メモリー**: クラスター内の ESXi サーバーの合計メモリー・サイズ。
   * **データ・センターの場所**: クラスターがホストされるデータ・センター。
   * **ポッド (Pod)**: クラスターがデプロイされているポッド。
   * **状況**: クラスターの状況。 状況は、以下のいずれかの値になります。
     <dl class="dl">
         <dt class="dt dlterm">初期化中</dt>
         <dd class="dd">クラスターは作成され、構成されています。</dd>
         <dt class="dt dlterm">変更中</dt>
         <dd class="dd">クラスターは変更されています。</dd>
         <dt class="dt dlterm">使用可能</dt>
         <dd class="dd">クラスターは使用可能です。</dd>
         <dt class="dt dlterm">削除中</dt>
         <dd class="dd">クラスターは削除中です。</dd>
         <dt class="dt dlterm">削除済み</dt>
         <dd class="dd">クラスターが削除された場合。</dd>
     </dl>
   * **アクション**: **「削除」**アイコンをクリックしてクラスターを削除できます。
4. クラスター名をクリックして ESXi サーバー、ストレージ、ライセンスの詳細情報を確認します。

### ESXi サーバー

   * **名前**: ESXi サーバーの名前は、`<host_prefix><n>.<subdomain_label>.<root_domain>` という形式です。各部の意味は次のとおりです。

      `host_prefix` はホスト名接頭部、
      `n` は ESXi サーバーの順序、
      `subdomain_label` はサブドメイン・ラベル、
      `root_domain` はルート・ドメイン・ネームです。

   * **バージョン**: ESXi サーバーのバージョン。
   * **資格情報**: ESXi サーバーにアクセスするためのユーザー名とパスワード。
   * **プライベート IP**: ESXi サーバーのプライベート IP アドレス。
   * **状況**: ESXi サーバーの状況。以下の値のいずれかになります。
        <dl class="dl">
        <dt class="dt dlterm">追加済み</dt>
        <dd class="dd">ESXi サーバーが追加され、使用可能な状態です。 </dd>
        <dt class="dt dlterm">追加中</dt>
        <dd class="dd">ESXi サーバーが追加されています。 </dd>
        <dt class="dt dlterm">削除中</dt>
        <dd class="dd">ESXi サーバーが削除されています。</dd>
        </dl>

### ストレージ

   * **名前**: データ・ストア名。
   * **サイズ**: ストレージの容量。
   * **IOPS/GB**: ストレージのパフォーマンス・レベル。
   * **NFS/ポータル**: ストレージの NFS バージョン。
   * **状況**: ストレージの状況。以下の値のいずれかになります。:
        <dl class="dl">
        <dt class="dt dlterm">追加済み</dt>
        <dd class="dd">ESXi サーバーが追加され、使用可能な状態です。 </dd>
        <dt class="dt dlterm">追加中</dt>
        <dd class="dd">ESXi サーバーが追加されています。 </dd>
        <dt class="dt dlterm">削除中</dt>
        <dd class="dd">ESXi サーバーが削除されています。</dd>
        </dl>

### ライセンス

   * **ライセンス**: ライセンス・タイプ。
   * **注文タイプ**: IBM 提供のライセンスであるかユーザー提供のライセンスであるか。
   * **ライセンス・エディション**: ライセンスのバージョンとエディション。
   * **ライセンス・キー**: ライセンス・キー。
   * **合計容量 (CPU)**: ライセンスの合計 CPU 容量。
   * **空き容量 (CPU)**: ライセンスの CPU の空き容量。

## VMware Federal インスタンスからのクラスターの削除

不要になったクラスターをインスタンスから削除したい場合があります。

この手順を使用して、V2.3 以降のリリースでデプロイ (または V2.3 以降のリリースにアップグレード) されたインスタンスからクラスターを削除できます。
{:note}

### 削除する前に

* この手順を使用して、V2.3 以降のリリースでデプロイされたインスタンスからクラスターを削除できます。
* V2.2 以前のインスタンスでデプロイしたクラスターの場合に、インスタンスに追加したクラスターを削除するには、インスタンスを V2.3 にアップグレードする必要があります。
* クラスターは一度に 1 つしか削除できません。 複数のクラスターを削除する場合は、順番に削除する必要があります。つまり、前のクラスターが削除されるまで待ってから、次のクラスターを削除してください。
* クラスターを削除する前に、クラスター内のすべてのノードが電源オンの状態で作動可能であることを確認します。
* クラスターを削除すると、クラスターのすべての VM (仮想マシン) も削除され、復旧できなくなります。 VM を保持したい場合は、他のクラスターに移行してください。
* デフォルトのクラスターは削除できません。

## VMware Federal インスタンスからクラスターを削除する手順

1. {{site.data.keyword.vmwaresolutions_short}} コンソールで、左側のナビゲーション・ペインの**「デプロイ済みインスタンス」**をクリックします。
2. **「vCenter Server インスタンス」**テーブルで、クラスターを削除するインスタンスをクリックします。

   インスタンスの状況が**「使用可能」**であることを確認してください。 そうでない場合、インスタンスからクラスターを削除できません。
   {:note}

3. 左側のナビゲーション・ペインの**「インフラストラクチャー」**をクリックします。 **「クラスター」**テーブルで、削除するクラスターを見つけて、**「アクション」**列にある**「削除」**アイコンをクリックします。

### 関連リンク

* [VMware Federal インスタンスの表示](/docs/services/vmwaresolutions/vcenter/vc_fed_viewinginstance.html)
* [VMware Federal インスタンスの容量の拡張と縮小](/docs/services/vmwaresolutions/vcenter/vc_fed_addingremovingservers.html)
