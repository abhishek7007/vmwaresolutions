---

copyright:

  years:  2016, 2019

lastupdated: "2019-05-09"

subcollection: vmware-solutions


---

# Design Detalhado
{: #vcsicp-detail-design}

## Componentes de serviços comuns
{: #vcsicp-detail-design-common-services}

Os serviços comuns fornecem os serviços que são usados por outros serviços na plataforma de gerenciamento de nuvem. Os serviços comuns incluem serviços de identidade e acesso, serviços de nome de domínio e serviços NTP.

![Serviços comuns do {{site.data.keyword.icpfull_notm}}](../../images/vcsicp-icp-commonservices.svg "Serviços comuns do {{site.data.keyword.icpfull_notm}}")

### Serviços de identidade e de acesso
{: #vcsicp-detail-design-identity}

Como parte da automação do VMware vCenter Server on {{site.data.keyword.cloud}}, um Microsoft Active Directory (AD) é empregado para Gerenciamento de Identidade. Uma única instância de servidor virtual (VSI) do AD é implementada. O vCenter está configurado para usar a autenticação do AD e é possível configurar o {{site.data.keyword.icpfull_notm}} para Autenticação LDAP.

###	Domain Name Services
{: #vcsicp-detail-design-dns}

A implementação do vCenter Server usa as VSIs do AD implementadas como servidores DNS para a instância. Todos os componentes implementados, como vCenter, PSC, NSX e hosts ESXi, são configurados para apontar para AD como seu DNS padrão.

###	Serviços NTP
{: #vcsicp-detail-design-ntp}

A implementação do vCenter Server usa os servidores NTP de infraestrutura do {{site.data.keyword.cloud_notm}}. Todos os componentes implementados são configurados para usar esses servidores NTP. Ter todos os componentes dentro do design que usa os mesmos servidores NTP é crítico para que os certificados e a autenticação do AD funcionem corretamente.

## Rede
{: #vcsicp-detail-design-networking}

### Rede NSX-V
{: #vcsicp-detail-design-nsx-v}

O NSX-V foi projetado para que uma única plataforma do gerenciador NSX-V esteja ligada a uma única instância do vCenter Server. Ele fornece serviços de rede para aplicativos que são executados dentro de um ambiente do vSphere.

Usando a rede NSX-V incluída na implementação do VCS, é possível implementar o {{site.data.keyword.icpfull_notm}} em uma rede de sobreposição VXLAN.

O {{site.data.keyword.icpfull_notm}} é implementado com a pilha de rede padrão do Calico para Kubernetes, que fornece isolamento de rede em seu cluster.

![{{site.data.keyword.icpfull_notm}} com a rede NSX-V](../../images/vcsicp-nsxv-networking.svg "{{site.data.keyword.icpfull_notm}} com a rede NSX-V")

Para obter mais informações, consulte o [Guia de rede do vCenter Server](/docs/services/vmwaresolutions/archiref/vcsnsxt?topic=vmware-solutions-vcsnsxt-intro).

### Rede NSX-T
{: #vcsicp-detail-design-nst-t}

O NSX-T foi projetado para que uma única plataforma de rede possa se conectar a qualquer tipo de aplicativo, seja baseado em máquina virtual ou em contêiner, em execução dentro ou fora de um ambiente do vSphere.

O {{site.data.keyword.icpfull_notm}} fornece uma opção para substituir a rede Calico por uma instância do NSX-T, fornecendo um único local para gerenciar a rede e a segurança.

![{{site.data.keyword.icpfull_notm}} com a rede NSX-T](../../images/vcsicp-icp-nsxt-networking.svg "{{site.data.keyword.icpfull_notm}} com a rede NSX-T")

## Links relacionados
{: #vcsicp-detail-design-related}

* [Visão geral do vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle](/docs/services/vmwaresolutions/archiref/vcs?topic=vmware-solutions-vcs-hybridity-intro)
