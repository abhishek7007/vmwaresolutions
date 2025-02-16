---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-25"

subcollection: vmware-solutions


---

# NSX 업데이트
{: #vum-updating-nsx}

다음 정보는 NSX에 대한 업데이트 프로세스의 예입니다. 업그레이드 중인 NSX 버전에 대한 업데이트 프로세스는 VMware 안내서를 참조하십시오.

NSX 및 vSphere를 모두 업그레이드해야 하는 경우 VMware에서는 먼저 NSX 업그레이드를 완료한 후 vSphere 업그레이드를 완료하도록 권장합니다. NSX VIB는 호스트에 설치된 ESXi 버전에 특정하기 때문입니다. 그러나 한 번에 하나의 호스트에서 수동으로 다음 워크플로우를 사용하는 경우 이 문서에 문서화된 대로 VUM을 사용하도록 권장합니다.

1. **ESXi 업그레이드** - ESXi 업그레이드가 완료된 후 호스트가 유지보수 모드를 종료하지만 다음 단계가 완료될 때까지 논리 스위치에 연결된 VM을 호스트로 이동할 수 없습니다.
2. **NSX VIB 업그레이드** - VIB가 업그레이드되고 호스트가 유지보수 모드에서 제거된 후 논리 스위치에 연결된 VM을 호스트로 이동할 수 있습니다.

NSX는 _my.vmware.com_에서 받은 다운로드로 NSX Manager를 업데이트하여 업데이트됩니다. 따라서 업데이트를 다운로드하려면 계정이 필요합니다. VMware vCenter Server on {{site.data.keyword.cloud_notm}} 인스턴스에 {{site.data.keyword.cloud}} 구독 라이센싱을 이용하는 경우 **my.vmware.com** 계정을 사용하여 업데이트를 다운로드할 수 없습니다. 따라서 [IBM 지원 센터에 문의](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support)해야 합니다.

업그레이드를 시작하기 전에 업그레이드 문제 및 임시 해결책에 대한 NSX 참고사항을 확인하십시오. 릴리스 정보를 사용하여 vCenter가 NSX에 대한 새로운 시스템 요구사항을 충족하는지 확인하십시오.

VMware 비즈니스 파트너의 추가 소프트웨어를 설치한 경우 비즈니스 파트너 문서를 참조하여 호환성 및 업그레이드 세부사항을 확인하십시오. vCenter Server 기본 및 보조 인스턴스를 배치했으며 교차 vCenter NSX 환경이 있는 경우 올바른 업그레이드 프로세스는 릴리스 정보를 참조하십시오.

교차 vCenter NSX 환경에서는 기본 NSX Manager 어플라이언스가 먼저 업데이트되고 다음으로 모든 보조 NSX Manager 어플라이언스가 업데이트됩니다.
**다운그레이드는 지원되지 않습니다.** 따라서 업그레이드를 진행하기 전에 NSX Manager의 백업을 작성하십시오. 모든 NSX Edge 구성, 논리 라우터, 에지 서비스 게이트웨이가 NSX Manager 백업의 일부로 백업됩니다.

NSX Manager를 업그레이드된 후 NSX를 다운그레이드할 수 없습니다. 그러므로 회사 지침에 따라 합의된 유지보수 기간에 유지보수 활동을 수행하는 것이 좋습니다. 작동 중단을 최소화하고 기능 문제를 줄이기 위해 모든 NSX 컴포넌트를 단일 가동 중단 기간에 업그레이드하도록 권장합니다. NSX 업그레이드 프로세스에는 다소 시간이 걸릴 수 있으므로 NSX 배치 업그레이드 순서를 이해하는 것이 중요합니다.
* NSX Manager
* NSX Controller 클러스터
* NSX 호스트 클러스터
* Edge Services Gateway는 NSX Manager 업그레이드 후에 언제든지 업그레이드할 수 있습니다.
* Guest Introspection, 사용되는 경우 릴리스 정보의 지시사항에 따르십시오.

워크플로우는 다음과 같습니다.
1. 점프 서버에 로그인한 후 브라우저를 여십시오.
2. _my.vmware.com_ 인증 정보를 사용하여 다운로드 섹션으로 이동하고 _NSX for vSphere_를 검색하십시오.
3. 필요한 버전을 선택하십시오.
4. 다운로드 페이지에서 **업그레이드 번들, 지금 다운로드**를 선택하십시오.
5. 적합한 폴더에 다운로드하십시오.
6. **NSX Manager 업그레이드**:
  - IC4VS 콘솔에 문서화된 IP 주소 및 인증 정보를 사용하여 NSX Manager 가상 어플라이언스에 로그인하고 홈 페이지에서 업그레이드 단추를 클릭하십시오.
  - NSX Manager에 로그인하십시오.
  - **어플라이언스 관리**에서 **백업 및 복원**을 클릭하십시오.
  - 백업을 클릭하고 적절한 파일 이름을 입력하십시오. VMware에서는 NSX Manager 데이터를 복원하기 전에 NSX Manager 어플라이언스를 다시 설치할 것을 권장합니다. 기존 NSX Manager 어플라이언스에 대한 복원 오퍼레이션이 작동할 수 있지만 공식적으로 지원되지는 않습니다. 새로 배치된 NSX Manager 어플라이언스에 대한 IP 정보 및 백업 위치 정보를 지정하는 데 사용될 수 있도록 NSX Manager 어플라이언스에 대한 IP 설정을 기록해 두는 것이 좋습니다.
  - 오른쪽 상단에서 **번들 업로드**를 클릭하고 _my.vmware.com_에서 다운로드한 파일을 업로드하십시오.
  - 업그레이드 정보를 읽고 SSH를 사용으로 설정할지 여부와 VMware 고객 환경 향상 프로그램에 참여할지 여부를 선택하십시오.
  - **업그레이드**를 클릭하십시오.
  - 업로드가 완료되면 NSX Manager 로그인 페이지로 경로 재지정됩니다. 다시 로그인하여 현재 소프트웨어 버전 표시가 올바른지 확인하십시오.
7. **NSX Controller 클러스터 업그레이드**:
  - vSphere Web Client를 열고 VCSA에 로그인하십시오.
  - **홈** > **네트워킹 및 보안** > **설치**로 이동하여 **관리** 탭을 선택하고 제어기 클러스터 상태 열에서 **업그레이드 사용 가능**을 클릭하십시오.
  - 사용자 환경의 제어기가 차례로 업그레이드되고 다시 부팅됩니다. 업그레이드를 시작하면 시스템에서 업그레이드 파일을 다운로드하고, 각 제어기를 업그레이드하고, 각 제어기를 다시 시작하고, 각 제어기의 업그레이드 상태를 업데이트합니다.
8. **NSX 호스트 클러스터 업그레이드**:
  - NSX Manager 및 NSX Controller를 업그레이드하면 호스트 클러스터가 vSphere ESXi 호스트의 NSX VIB로 업데이트됩니다.
  - vSphere Web Client에서 **홈** > **네트워킹 및 보안** > **설치**로 이동하고 **호스트 준비** 탭을 선택하십시오. 업그레이드할 각 클러스터에 대해 **업그레이드 사용 가능**을 클릭하십시오. 설치 상태에 설치 중이 표시됩니다.
  - 클러스터 설치 상태에 _준비되지 않음_이 표시됩니다. **준비되지 않음**을 클릭하여 자세한 정보를 표시하고 **모두 해결**을 클릭하여 VIB 설치를 완료하십시오. 호스트가 유지보수 모드로 전환되며 업그레이드 완료를 위해 필요한 경우 다시 부팅됩니다. 설치 상태 열에 설치 중이 표시됩니다. 업그레이드가 완료되면 설치 상태 열에 초록색 확인 표시와 업그레이드된 NSX 버전이 표시됩니다.
9. **Edge Services Gateway**:
  - 업그레이드 프로세스 중에 새 Edge 가상 어플라이언스가 기존 Edge 가상 어플라이언스와 함께 배치됩니다. 새 Edge가 준비되면 이전 Edge의 vNIC 연결이 끊기고 새 Edge의 vNIC가 연결됩니다. 그런 다음 새 Edge가 GARP(Gratuitous ARP) 패킷을 전송하여 연결된 스위치의 ARP 캐시를 업데이트합니다. HA가 배치되는 경우 업그레이드 프로세스가 두 번 수행됩니다. 이 프로세스는 패킷 전달에 일시적으로 영향을 줄 수 있습니다.
  - vSphere Web Client에서 **네트워킹 및 보안** > **NSX Edge**를 선택하십시오. 각 NSX Edge 인스턴스에 대해 **조치** 메뉴에서 **버전 업그레이드**를 선택하십시오.
  - NSX Edge가 성공적으로 업그레이드되면 상태가 배치됨이 되고 버전 열에 새 NSX 버전이 표시됩니다. Edge 업그레이드에 실패하고 이전 버전으로 롤백되지 않은 경우 **NSX Edge 다시 배치** 아이콘을 클릭한 후 업그레이드를 재시도하십시오.

## 관련 링크
{: #vum-updating-nsx-related}

* [VMware HCX on {{site.data.keyword.cloud_notm}} 솔루션 아키텍처](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcx-archi-intro#hcx-archi-intro)
* [VMware Solutions on {{site.data.keyword.cloud_notm}} 디지털 기술 업무](https://ibm-dte.mybluemix.net/vmware)(데모)
