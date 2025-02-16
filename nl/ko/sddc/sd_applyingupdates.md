---

copyright:

  years:  2016, 2019

lastupdated: "2019-03-12"

subcollection: vmwaresolutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# 업데이트를 Cloud Foundation 인스턴스에 적용
{: #sd_applyingupdates}

{{site.data.keyword.vmwaresolutions_full}} 콘솔은 VMware 가상 환경에 적용할 수 있는 사용 가능한 소프트웨어 업데이트를 주기적으로 발견하고 나열합니다.

사용 가능한 업데이트는 인스턴스의 소프트웨어 업데이트 목록에 있는 레코드로, 즉시 적용되거나 나중에 실행되도록 스케줄될 수 있습니다. 업데이트는 IBM 관리 컴포넌트 및 VMware 컴포넌트를 업데이트하기 위해 하나 이상의 패키지가 포함된 번들입니다.

자동 업데이트가 사용되기 때문에 IBM CloudDriver 업데이트는 더 이상 나열되지 않습니다. ESXi 서버 추가, 클러스터 추가 및 서비스 주문과 같은 조치를 수행하면 인스턴스가 최신 버전으로 자동 업데이트됩니다. 자동 업데이트에 대한 자세한 정보는 [V2.5 릴리스 정보](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-relnotes_v25)에서 *IBM CloudDriver 복원성* 섹션을 참조하십시오.
{:note}

## 시작하기 전에
{: #sd_applyingupdates-prereq}

업데이트를 적용하기 전에 아래로 화살표를 클릭하여 업데이트 항목을 펼치고 다음 정보를 확인하십시오.
* 업데이트의 버전입니다. 가장 이전 업데이트부터 최신 업데이트까지 시간 순으로 업데이트를 적용해야 합니다. 최신 업데이트를 적용하기 전에 이전 업데이트를 모두 적용했는지 확인하십시오. 예를 들어, V2.5 업데이트를 적용하기 전에 V2.4 업데이트를 적용해야 합니다.
* 작동 중단의 필요 여부입니다.
* 업데이트를 완료할 총 예상 시간입니다.
* 업데이트가 VMware 가상 환경에 미치는 영향입니다. 표 1에서는 여러 업데이트 레벨이 시스템에 어떤 영향을 주는지 보여줍니다.
* 업데이트 세부사항입니다.

표 1. 업데이트 레벨 및 영향

<table>
  <tr>
    <th>업데이트 레벨</th>
    <th>영향</th>
  </tr>
  <tr>
    <td>낮음</td>
    <td>이 업데이트는 시스템에 영향을 주지 않습니다. 스케줄된 작동 중단 중에 업데이트를 적용할 필요는 없습니다.</td>
  </tr>
  <tr>
    <td>중간</td>
  <td>이 업데이트는 일부 시스템에 영향을 줄 수 있습니다. 스케줄된 작동 중단 중에 업데이트를 적용하는 것이 좋습니다.</td>
  </tr>
    <tr>
    <td>주요</td>
  <td>이 업데이트는 일부 또는 모든 시스템에 영향을 줍니다. 스케줄된 작동 중단 중에 업데이트를 적용해야 합니다.</td>
  </tr>
</table>

## Cloud Foundation 인스턴스에 업데이트를 적용하는 프로시저
{: #sd_applyingupdates-procedure}

1. {{site.data.keyword.vmwaresolutions_short}} 콘솔의 왼쪽 탐색 분할창에서 **리소스**를 클릭하십시오.
2. **Cloud Foundation 인스턴스** 테이블에서 업데이트할 인스턴스를 클릭하십시오.
3. **요약** 페이지에서 모든 인스턴스 세부사항이 올바르게 표시되는지 확인하십시오. 그런 다음, 왼쪽 탐색 분할창에 있는 **인프라**를 클릭하여 **인프라** 페이지의 세부사항을 확인하십시오.
   세부사항이 표시되지 않는 경우, 방화벽 규칙 또는 다른 네트워킹 문제로 인해 IBM CloudDriver VSI(Virtual Server Instance)에 연결 문제점이 있음을 나타낼 수 있습니다. 다음 단계를 계속하기 전에 문제점을 해결하십시오. 그렇지 않으면, 업데이트에 실패할 수 있습니다.
4. 왼쪽 탐색 분할창에서 **업데이트 및 패치**를 클릭하십시오.
5. 아래로 화살표를 클릭하여 적용할 업데이트를 펼친 후 다음 단계 중 하나를 완료하십시오.
   *  업데이트를 즉시 시작하려면 업데이트 항목의 **조치** 열에 있는 오버플로우 메뉴 아이콘을 클릭한 후 **지금 업데이트**를 클릭하십시오.
   *  이후 업데이트를 스케줄하려면 업데이트 항목의 **조치** 열에 있는 오버플로우 메뉴 아이콘을 클릭한 후 **업데이트 스케줄 설정**을 클릭하십시오. 업데이트를 시작할 경우 날짜, 시간 및 시간대를 선택하십시오. **확인**을 클릭하십시오.
6. 다중 사이트 배치 구성에서 업데이트를 Cloud Foundation 인스턴스에 적용하는 경우 **업데이트하는 데 필요한 단계**라는 제목의 섹션이 표시되며, 다중 사이트 배치에서 모든 인스턴스에 필요한 업데이트 오퍼레이션이 나열됩니다. 각 단계마다 **업데이트 적용**을 클릭하여 순서대로 단계를 완료해야 합니다. 다음 단계를 시작하기 전에 이전 단계가 완료될 때까지 기다려야 합니다.

## 결과
{: #sd_applyingupdates-results}

1. 업데이트 오퍼레이션이 시작되기 전에 인스턴스의 상태 검사가 완료됩니다. 상태 검사에 실패하면 업데이트를 적용하기 전에 문제점을 수정할 수 있도록 알림을 받습니다.
2. VMware 컴포넌트 업데이트를 포함하는 업데이트 중에, 유지보수 모드로 전환하려면 VM을 ESXi 서버로부터 마이그레이션해야 할 수 있습니다. VM에 로컬 데이터 저장소 또는 마운트된 CD-ROM이 있는 경우 VM 마이그레이션이 수행되지 않을 수 있습니다.
3. 새 환경의 프로비저닝 중에 {{site.data.keyword.vmwaresolutions_short}}는 업데이트 적용을 포함하여 인스턴스 관리에 사용되는 **automationuser** ID를 작성합니다. 이 사용자 ID의 비밀번호를 변경하지 마십시오. 비밀번호를 변경하면 업데이트에 실패할 수 있습니다.

4. 업데이트를 적용한 후 자세한 진행상태 및 업데이트 상태를 볼 수 있는 소프트웨어 업데이트 상태 목록에 레코드가 표시됩니다. 업데이트가 완료되면 설치된 소프트웨어 업데이트 목록에 레코드가 표시됩니다.

  업데이트 작업의 최신 상태를 검색하려면 페이지의 오른쪽 상단에 있는 새로 고치기 아이콘을 클릭하십시오.
  {:tip}

5. 업데이트 상태에 대한 자세한 정보는 다음 표를 참조하십시오.

   표 2. 업데이트 상태의 세부사항

    <table>
      <tr>
        <th>상태</th>
        <th>세부사항</th>
      </tr>
      <tr>
        <td>사용 가능</td>
        <td>업데이트는 적용될 수 있습니다. 이전 업데이트가 적용될 때까지 사용 가능한 업데이트를 선택할 수 없습니다.</td>
      </tr>
      <tr>
        <td>진행 중</td>
      <td>업데이트 작업이 시작되었으나 아직 완료되지 않았습니다. 현재 업데이트 작업이 완료될 때까지 다른 업데이트를 적용할 수 없습니다. </td>
      </tr>
        <tr>
        <td>설치됨</td>
      <td>업데이트 작업이 완료되었습니다. VMware 플랫폼의 해당 컴포넌트가 업데이트됩니다.</td>
      </tr>
        <tr>
        <td>실패</td>
      <td>업데이트 작업에 실패합니다. 콘솔은 업데이트 실패에 대한 오류를 보고합니다. 업데이트를 다시 적용하기 전에 오류를 검토하고 보고된 문제를 수정하십시오.</td>
      </tr>
          <tr>
        <td>스케줄됨</td>
      <td>업데이트 작업이 나중에 실행되도록 스케줄되었습니다. 업데이트 작업은 스케줄할 때 자동으로 시작됩니다.</td>
      </tr>
          <tr>
        <td>알 수 없음</td>
      <td>업데이트 작업의 상태를 가져올 수 없습니다. IBM 지원 센터에 문의하여 도움을 받으십시오.</td>
      </tr>
    </table>

6. 특정 단계에서 업데이트 프로세스에 실패하는 경우 [IBM 지원 센터에 문의](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support)하여 도움을 받으십시오. 문제 해결 방법에 대한 정보를 얻고 실패한 단계에서 업그레이드를 다시 시작하도록 안내됩니다.

## 관련 링크
{: #sd_applyingupdates-related}

* [Cloud Foundation 개요](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_cloudfoundationoverview)
* [Veeam on {{site.data.keyword.cloud_notm}} 개요](/docs/services/vmwaresolutions/services?topic=vmware-solutions-veeam_considerations)
* [IBM 지원 센터에 문의](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support)
* [FAQ](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-faq)
