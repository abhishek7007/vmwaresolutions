---

copyright:

  years:  2016, 2019

lastupdated: "2019-02-14"

subcollection: vmware-solutions


---

# 完全分散
{: #caveonix-fully}

額外的基本虛擬機器 (VM) 和橫向擴充 VM 會根據資產數目和資料保留需求而新增。

表 1. 基本 - 使用者介面

|參數	| 值  |
|---|---|
|類型	| 基本 |
|VM 數量	|2 |
|vCPU	|2 |
|RAM	|6 GB|
|磁碟 |60 GB|
|OS	|CentOS 7|
|已安裝的應用程式元件|UI|

表 2. 基本 - 應用程式及外掛程式

|參數	| 值  |
|---|---|
|類型	| 基本 |
|VM 數量	|2 |
|vCPU	| 8                                   |
|RAM	| 16 GB |
|磁碟 |500 GB|
|OS	|CentOS 7|
|已安裝的應用程式元件|應用程式、外掛程式|

表 3. 基本 - 中央收集器

|參數	| 值  |
|---|---|
|類型	| 基本 |
|VM 數量	|3 |
|vCPU	|8 |
|RAM	| 16 GB |
|磁碟 |500 GB |
|OS	|CentOS 7 |
|已安裝的應用程式元件|中央收集器（叢集）|

表 4. 基本關聯式資料庫

|參數	| 值  |
|---|---|
|類型	| 基本 |
|VM 數量	|2 |
|vCPU	|8 |
|RAM	| 16 GB |
|磁碟 |1 TB |
|OS	C|entOS 7 |
|已安裝的應用程式元件|關聯式資料儲存庫（主要 / 次要）|

表 5. 基本 - 傳訊資料儲存庫

|參數	| 值  |
|---|---|
|類型	| 基本 |
|VM 數量	|3 |
|vCPU	|8 |
|RAM	| 16 GB |
|磁碟 |1 TB |
|OS	|CentOS 7 |
|已安裝的應用程式元件|傳訊資料儲存庫（叢集）|

表 6. 基本 - 索引資料儲存庫（主節點）

|參數	| 值  |
|---|---|
|類型	| 基本 |
|VM 數量	|3 |
|vCPU	|8 |
|RAM	| 16 GB |
|磁碟 |1 TB |
|OS	|CentOS 7 |
|已安裝的應用程式元件|索引資料儲存庫（主節點）|

表 7. 資料庫 - 索引資料儲存庫（資料節點）

|參數	| 值  |
|---|---|
|類型	| 基本 |
|VM 數量	|5 |
|vCPU	|8 |
|RAM	| 16 GB |
|磁碟 |4 TB |
|OS	|CentOS 7 |
|已安裝的應用程式元件|索引資料儲存庫（資料節點）|

下表說明橫向擴充 VM 詳細資料。

表 8. 橫向擴充 - 資料節點

|參數	| 值  |
|---|---|
|類型	|橫向擴充 |
|VM 數量	28 |
|vCPU	|8 |
|RAM	| 16 GB |
|磁碟 |4 TB |
|OS	|CentOS 7 |
|已安裝的應用程式元件|資料節點（橫向擴充）|

下表顯示「遠端收集器」VM 詳細資料。

表 9. 遠端收集器

|參數	| 值  |
|---|---|
|VM 數量	|視需要|
|vCPU	|8 |
|RAM	| 8 GB          |
|磁碟 |1 TB |
|OS	|CentOS 7 |
|已安裝的應用程式元件|遠端收集器|

## 相關鏈結
{: #caveonix-fully-related}

* [VMware vCenter Server on {{site.data.keyword.cloud}} with Hybridity Bundle](/docs/services/vmwaresolutions/archiref/vcs?topic=vmware-solutions-vcs-hybridity-intro)
