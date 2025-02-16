---

copyright:

  years:  2016, 2019

lastupdated: "2019-02-15"

---

{:tip: .tip}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}

# KMIP for VMware on IBM Cloud 개요 - 더 이상 사용되지 않음
{: #kmip_considerations}

KMIP for VMware on IBM Cloud의 현재 버전은 더 이상 사용되지 않습니다. 자세한 정보는 [IBM 지원 센터에 문의](../vmonic/trbl_support.html)하십시오.
{:deprecated}

KMIP for VMware on {{site.data.keyword.cloud}} 서비스는 {{site.data.keyword.cloud_notm}}의 VMware에서 사용되는 암호화 키를 관리하기 위해 고가용성 서비스를 연중무휴로 제공합니다. 이 서비스는 고객이 암호화 키를 작성, 검색, 활성화, 취소 및 영구 삭제할 수 있도록 하는 런타임 기능을 제공합니다. 또한 클라이언트 인증 정보와 암호화 키 간의 연관을 유지보수하는 관리 기능도 제공합니다.

## KMIP for VMware on IBM Cloud의 기술 스펙
{: #kmip_considerations-specs}

다음 스펙이 KMIP for VMware on {{site.data.keyword.cloud_notm}} 서비스에 포함되어 있습니다.

* VMware 호환 가능 KMIP(Key Management Interoperability Protocol)
* 관리 서비스
* 전세계 여러 지리적 지역에서 사용 가능
* 각 지역의 고가용성 KMIP 서비스 엔드포인트

## KMIP for VMware on IBM Cloud 설치 시 고려사항
{: #kmip_considerations-install}

KMIP for VMware on {{site.data.keyword.cloud_notm}}는 암호화 키를 작성, 암호화 및 복호화하는 데 IBM Key Protect for {{site.data.keyword.cloud_notm}} 서비스를 사용합니다. 따라서 KMIP for VMware on {{site.data.keyword.cloud_notm}}를 설치하기 전에 다음 항목을 확인하십시오.
* 사용 가능한 Key Protect 서비스를 주문했습니다.
* [서비스 ID 작성](../../../iam/serviceid.html)의 단계에 따라 {{site.data.keyword.cloud_notm}} 서비스 ID를 작성했습니다. 이 서비스 ID는 작성한 Key Protect 서비스 인스턴스에 액세스하는 데 사용됩니다.
* 서비스 ID에 다음 액세스 레벨을 부여했습니다.
   * 플랫폼 액세스 레벨: IBM Key Protect 인스턴스에 대한 뷰어 권한.
   * 서비스 액세스 레벨: IBM Key Protect 인스턴스에 대한 작성자 권한
* 작성된 서비스 ID에 대한 API 키가 있습니다. 이 키는 서비스를 주문할 때 필요합니다.
* [루트 키 작성](../../keymgmt/keyprotect_create_root.html)의 단계를 따르거나 [IBM Key Protect](https://cloud.ibm.com/apidocs/key-protect)의 RESTful API를 사용하여 Key Protect 사용자 인터페이스에서 하나 이상의 고객 루트 키(CRK)를 작성했습니다.

   **중요:** CRK 없이는 서비스를 주문할 수 없습니다. 기존 키 자료를 사용하여 CRK를 작성하는 방법을 사용하고 작성하는 키 자료를 백업하는 것이 좋습니다. 이렇게 하면 CRK를 저장하기 위해 IBM Key Protect가 적용된 데이터 센터에 장애가 발생하는 경우 키를 복구할 수 있습니다.

## KMIP for VMware on IBM Cloud 사용 시 고려사항
{: #kmip_considerations-use}

* 주문된 KMIP for VMware on {{site.data.keyword.cloud_notm}} 서비스를 VMware vCenter Server에 등록되는 KMS(Key Management Server)로 사용하려는 경우에는 vCenter Server와 주문된 KMIP for VMware on {{site.data.keyword.cloud_notm}} 서비스의 엔드포인트 간의 네트워크 연결이 작동하는지 확인하십시오.
* 서비스를 VMware vSAN 암호화에 사용하려는 경우에는 대상 vSAN의 호스트와 주문된 KMIP for VMware on {{site.data.keyword.cloud_notm}} 서비스의 엔드포인트 간의 네트워크 연결이 작동하는지 확인하십시오.
* KMIP for VMware(vSAN 암호화 사용)를 사용하는 경우, vSAN 상태 검사 시 하나 이상의 vSphere 호스트에서 KMS 클러스터에 연결할 수 없다는 경고가 주기적으로 나타날 수 있습니다. 이러한 경고는 vSAN 상태 검사 연결 제한시간이 너무 빨리 초과하기 때문에 발생합니다. 이 경고는 무시해도 됩니다.

## KMIP for VMware on IBM Cloud 제거 시 고려사항
{: #kmip_considerations-remove}

주문 중이나 서비스를 사용할 때 제공한 VMware 공용 인증서가 서비스 인스턴스와 통신하는 데 클라이언트 인증서로 사용됩니다. 서비스가 제거되면 연관된 VMware 공용 인증서에 대해 이 서비스 인스턴스에서 작성한 모든 암호화 키가 함께 제거됩니다.

따라서 서비스를 제거하기 전에 KMIP 서비스에서 작성된 키를 사용하여 암호화되고 있는 가상 머신 또는 vSAN이 있지 않은지 확인하십시오.

## 관련 링크
{: #kmip_considerations-related}

* [KMIP for VMware on {{site.data.keyword.cloud_notm}} 주문](kmip_ordering.html)
* [{{site.data.keyword.cloudaccesstrailshort}} 이벤트](../vmonic/at-events.html)
* [IBM Key Protect for {{site.data.keyword.cloud_notm}}](../../keymgmt/index.html)
* [vSphere Security](https://docs.vmware.com/en/VMware-vSphere/6.5/com.vmware.vsphere.security.doc/GUID-52188148-C579-4F6A-8335-CFBCE0DD2167.html)
* [FAQ](../vmonic/faq.html)
* [IBM 지원 센터에 문의](../vmonic/trbl_support.html)
