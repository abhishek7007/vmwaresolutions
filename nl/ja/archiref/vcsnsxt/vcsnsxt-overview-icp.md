---

copyright:

  years:  2016, 2019

lastupdated: "2019-02-15"

subcollection: vmware-solutions


---

# IBM Cloud Private
{: #vcsnsxt-overview-icp}

{{site.data.keyword.icpfull_notm}} は、コンテナー化されたアプリケーションを開発して管理するためのアプリケーション・プラットフォームです。 これは、コンテナー・オーケストレーター Kubernetes、プライベート・イメージ・リポジトリー、管理コンソール、モニター・フレームワーク、グラフィカル・ユーザー・インターフェースで構成される統合環境であり、ユーザーがアプリケーションのデプロイ、管理、モニター、スケーリングを行うことができる一元的な場所を提供します。

{{site.data.keyword.cloud_notm}} Private には以下の機能があります。
-	**統合インストーラー** - このインストーラーは、Ansible ベースのインストーラーを使用して、マスター・ノード、ワーカー・ノード、プロキシー・ノードを含む Kubernetes ベースのクラスターを迅速にセットアップします。
-	**{{site.data.keyword.cloud_notm}} Private 管理コンソール** – 一元化された単一のセキュアな管理コンソールから、アプリケーションとクラスターを管理、モニター、トラブルシューティングします。
-	**Private Docker イメージ・レジストリー** - このローカル・レジストリーには、Docker Hub のすべての機能に加えて、イメージを表示またはプルできるユーザーを制限する機能があります。
-	**コンテナー化されたソフトウェアおよびサービスのカタログ** - このカタログは、クラスター内のパッケージを一元的に参照およびインストールできる場所になります。 デフォルトの {{site.data.keyword.cloud_notm}} Private リポジトリー・リストに含まれている厳選されたリポジトリー内の IBM 製品のパッケージも追加で使用可能です。
-	**分離されたテナント・ネットワーク** - Calico により、クラスター内のパフォーマンスとネットワーク分離を向上させることができます。 Calico では、クラスター内のプロジェクトごとに分離したサブネットを作成できます。 このネットワーク分離により、データ伝送時のセキュリティーが強化され、アプリケーションとそのデータの暗号漏えいの可能性が小さくなります。 また、Calico により、単一の名前空間でのオブジェクトの共有を細かく制御するネットワーク・ポリシーを簡単に新規作成できます。
-	**ELK スタックによる堅固なモニターとロギング** - {{site.data.keyword.cloud_notm}} Private は、ログとメトリックの収集、保管、照会に、Elasticsearch、Logstash、Filebeat、Heapster を使用します。 このモニターとロギングのプロセスでは、すべてのログとメトリックを一元的に保管し、パフォーマンスを向上させ、より安定したログやメトリックのアクセスおよび照会が可能になります。

## IBM Cloud Private コンポーネント
{: #vcsnsxt-overview-icp-comp}

{{site.data.keyword.cloud_notm}} Private クラスターには、4 つの主要なノード・クラス (ブート、マスター、ワーカー、プロキシー) があります。 必要に応じて、クラスター内に管理ノード、脆弱性アドバイザー (VA) ノード、etcd ノードを指定できます。
-	**ブート・ノード** - ブート・ノードは、インストール、構成、ノード・スケーリング、クラスター更新の実行に使用されます。
-	**マスター・ノード** - マスター・ノードは管理サービスを提供し、クラスター内のワーカー・ノードを制御します。 マスター・ノードは、リソース割り振り、状態保守、スケジューリング、モニターを行うプロセスをホストします。
-	**ワーカー・ノード** - ワーカー・ノードは、タスクを実行するためのコンテナー化された環境を提供するノードです。 要求の増加に対応してパフォーマンスと効率を向上させるために、クラスターにさらにワーカー・ノードを簡単に追加できます。
-	**プロキシー・ノード** - プロキシー・ノードは、クラスター内で作成されたサービスに外部要求を送信するノードです。
-	**管理ノード** - 管理ノードは、モニター、課金、ロギングなどの管理サービスのみをホストするオプション・ノードです。 専用の管理ノードを構成することにより、マスター・ノードが過負荷になることを防止できます。
-	**脆弱性アドバイザー (VA) ノード** - VA ノードは、脆弱性アドバイザー・サービスの実行に使用されるオプション・ノードです。
-	**etcd** ノード - etcd ノードは、etcd 分散キー値ストアの実行に使用されるオプション・ノードです。

## IBM Cloud Private ネットワーキング
{: #vcsnsxt-overview-icp-networking}

Calico を使用すると {{site.data.keyword.icpfull_notm}} ネットワーク管理が簡単になります。
Calico は、Open System Interconnection (OSI) モデルのレイヤー 3 (つまりネットワーク層) を使用します。 Calico は、Border Gateway Protocol (BGP) を使用して、エージェント・ノード間の通信を容易にするルーティング・テーブルを構築します。

Calico ネットワーキングについて詳しくは、[{{site.data.keyword.containerlong_notm}}](/docs/services/vmwaresolutions/archiref/vcsnsxt?topic=vmware-solutions-vcsnsxt-overview-iks) を参照してください。

## 関連リンク
{: #vcsnsxt-overview-icp-related}

* [vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle の概要](/docs/services/vmwaresolutions/archiref/vcs?topic=vmware-solutions-vcs-hybridity-intro)
