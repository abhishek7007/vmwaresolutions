---

copyright:

  years:  2016, 2019

lastupdated: "2019-02-15"

---

{:tip: .tip}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}

# KMIP for VMware on IBM Cloud 概觀 - 已淘汰
{: #kmip_considerations}

現行 KMIP for VMware on IBM Cloud 版本即將淘汰。如需相關資訊，請參閱[與 IBM 支援中心聯絡](../vmonic/trbl_support.html)。
{:deprecated}

KMIP for VMware on {{site.data.keyword.cloud}} 服務提供全年無休高可性服務，以管理 {{site.data.keyword.cloud_notm}} 中 VMware 所使用的加密金鑰。此服務提供運行環境功能，以容許客戶建立、擷取、啟動、撤銷及毀損加密金鑰。同時提供管理功能來維護用戶端認證與加密金鑰之間的關聯。

## KMIP for VMware on IBM Cloud 的技術規格
{: #kmip_considerations-specs}

KMIP for VMware on {{site.data.keyword.cloud_notm}} 服務隨附下列規格：

* VMware 相容的「金鑰管理交互作業通訊協定 (KMIP)」
* 受管理服務
* 可在全球多個地理區域使用
* 每個地區中的高可用性 KMIP 服務端點

## 安裝 KMIP for VMware on IBM Cloud 時的考量
{: #kmip_considerations-install}

KMIP for VMware on {{site.data.keyword.cloud_notm}} 使用 IBM Key Protect for {{site.data.keyword.cloud_notm}} 服務來建立、加密及解密加密金鑰。因此，在安裝 KMIP for VMware on {{site.data.keyword.cloud_notm}} 之前，請先確定下列項目：
* 您已訂購可用的 Key Protect 服務。
* 已遵循[建立服務 ID](../../../iam/serviceid.html) 中的步驟建立 {{site.data.keyword.cloud_notm}} 服務 ID。此服務 ID 用來存取您所建立的 Key Protect 服務實例。
* 已為服務 ID 授與下列存取層次：
   * 在平台存取層次：IBM Key Protect 實例的「檢視者」權限。
   * 在服務存取層次：IBM Key Protect 實例的「寫入者」權限
* 您具有適用於所建立服務 ID 的 API 金鑰。當您訂購服務時，需要此金鑰。
* 您已從 Key Protect 使用者介面建立至少一個客戶主要金鑰 (CRK)，方法是遵循[建立主要金鑰](../../keymgmt/keyprotect_create_root.html)中的步驟，或使用 [IBM Key Protect](https://cloud.ibm.com/apidocs/key-protect) 中的 RESTful API。

   **重要事項：**沒有 CRK 就無法訂購服務。強烈建議您使用下列方法：使用現有金鑰資料建立 CRK，並備份您要建立的金鑰資料。這樣做，即可確保您可在套用 IBM Key Protect 以儲存您 CRK 的資料中心故障時回復金鑰。

## 使用 KMIP for VMware on IBM Cloud 時的考量
{: #kmip_considerations-use}

* 若要使用已訂購的 KMIP for VMware on {{site.data.keyword.cloud_notm}} 服務作為已登錄至 VMware vCenter Server 的「金鑰管理伺服器 (KMS)」，請確定從 vCenter Server 到已訂購 KMIP for VMware on {{site.data.keyword.cloud_notm}} 服務之端點的網路連線功能正常運作。
* 若要使用此服務進行 VMware vSAN 加密，請確定目標 vSAN 上之主機與已訂購 KMIP for VMware on {{site.data.keyword.cloud_notm}} 服務之端點間的網路連線功能正常運作。
* 當您使用 KMIP for VMware 進行 vSAN 加密時，vSAN 性能檢查可能會定期發出警告，指出它無法從您的一個以上 vSphere 主機連接至 KMS 叢集。這些警告發生的原因是 vSAN 性能檢查連線太快逾時。您可以忽略這些警告。

## 移除 KMIP for VMware on IBM Cloud 時的考量
{: #kmip_considerations-remove}

將訂購期間或使用服務時所提供的 VMware 公用憑證用作用戶端憑證，以與服務實例通訊。移除服務時，會同時移除相關聯 VMware 公用憑證的這個服務實例所建立的所有加密金鑰。

因此，移除此服務之前，請確定未使用 KMIP 服務所建立的金鑰來加密虛擬機器或 vSAN。

## 相關鏈結
{: #kmip_considerations-related}

* [訂購 KMIP for VMware on {{site.data.keyword.cloud_notm}}](kmip_ordering.html)
* [{{site.data.keyword.cloudaccesstrailshort}} 事件](../vmonic/at-events.html)
* [IBM Key Protect for {{site.data.keyword.cloud_notm}}](../../keymgmt/index.html)
* [vSphere Security](https://docs.vmware.com/en/VMware-vSphere/6.5/com.vmware.vsphere.security.doc/GUID-52188148-C579-4F6A-8335-CFBCE0DD2167.html)
* [常見問題](../vmonic/faq.html)
* [與 IBM 支援中心聯絡](../vmonic/trbl_support.html)
