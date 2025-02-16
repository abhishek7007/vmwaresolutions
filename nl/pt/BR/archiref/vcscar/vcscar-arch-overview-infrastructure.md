---

copyright:

  years:  2016, 2019

lastupdated: "2019-05-07"

subcollection: vmware-solutions


---

# Rede e infraestrutura do IBM Cloud
{: #vcscar-arch-overview-infrastructure}

## Virtual Routing and Forwarding
{: #vcscar-arch-overview-infrastructure-vrf}

As contas do {{site.data.keyword.cloud}} podem ser configuradas como uma conta de Virtual Routing and Forwarding (VRF). Uma conta de VRF ativa o roteamento global automático entre blocos de IP de sub-rede. Todas as contas com conexões de Link direto devem ser convertidas ou criadas como uma conta do VRF.

## Link Direto
{: #vcscar-arch-overview-infrastructure-direct-link}

O {{site.data.keyword.cloud_notm}} Direct Link Connect oferece acesso privado à infraestrutura do {{site.data.keyword.cloud_notm}} e a quaisquer outras nuvens vinculadas ao seu Provedor de serviços de rede por meio do {{site.data.keyword.CloudDataCent_notm}} local. Essa opção é perfeita para criar conectividade com múltiplas nuvens em um único ambiente.

Nós conectamos os clientes à rede do {{site.data.keyword.cloud_notm}} Private usando uma topologia de largura de banda compartilhada. Como ocorre com todos os produtos Direct Link, é possível incluir roteamento global, que permite tráfego de rede privada para todos os locais do {{site.data.keyword.cloud_notm}}.

## Redes privadas virtuais
{: #vcscar-arch-overview-infrastructure-virt-private-net}

### VPN do strongSwan
{: #vcscar-arch-overview-infrastructure-strongswan}

O serviço de VPN do IPSec do strongSwan fornece um canal de comunicação seguro de ponta a ponta sobre a Internet que é baseado no conjunto de protocolos padrão de mercado da Internet Protocol Security (IPSec).

### Hybridity (HCX)
{: #vcscar-arch-overview-infrastructure-hcx}

O serviço VMware vCenter Server on {{site.data.keyword.cloud_notm}} Hybridity Bundle pode ampliar ininterruptamente as redes de data centers no local para o {{site.data.keyword.cloud_notm}}, que permite que máquinas virtuais (MVs) sejam migradas para e do {{site.data.keyword.cloud_notm}} sem nenhuma conversão ou mudança.

## Estrutura física
{: #vcscar-arch-overview-infrastructure-phys-structure}

A infraestrutura física necessária para implementar uma instância de produção do {{site.data.keyword.icpfull_notm}} em um cluster do VMware vCenter Server on {{site.data.keyword.cloud_notm}} requer a especificação mínima a seguir.

Tabela 1. Especificação do vCenter Server para o  {{site.data.keyword.icpfull_notm}}

| | Implementação do NFS | Implementação da vSAN |
|:---------- |:---------- |:---------- |
| Número de servidores | 3 | 4 |
| CPU | 28 Núcleos de 2,2 GHz | 28 Núcleos de 2,2 GHz |
| Memória | 384 GB | 384 GB |
| Armazenamento | Gerenciamento de 2IOPS/GB de 2000 GB, Carga de trabalho de 4IOPS/GB de 2000 GB, {{site.data.keyword.icpfull_notm}} de 4IOPS/GB de 4000 GB | SSD x 2 com no mínimo 960 GB |

Além dos requisitos de hardware do {{site.data.keyword.cloud_notm}} Private, deve-se criar volumes persistentes no ambiente do {{site.data.keyword.icpfull_notm}} para armazenar dados do banco de dados e do log do Cloud Automation Manager (CAM). Embora o CAM suporte todos os tipos de volume persistente suportados pelo {{site.data.keyword.icpfull_notm}}, as duas configurações de armazenamento recomendadas para o CAM são NFS e GlusterFS.

## Estrutura virtual
{: #vcscar-arch-overview-infrastructure-virt-structure}

![Estrutura do vCenter Server e implementação do {{site.data.keyword.icpfull_notm}}](../../images/vcscar-icp.svg "Estrutura do vCenter Server e implementação do {{site.data.keyword.icpfull_notm}}")

Na instância do vCenter Server, a instância do {{site.data.keyword.icpfull_notm}} é implementada com um NSX Edge Services Gateway (ESG) dedicado e o Distributed Logical Router (DLR).
A instalação do {{site.data.keyword.icpfull_notm}} é carregada na sub-rede VXLAN que está definida nos componentes anteriores.

O ESG é configurado com uma regra NAT de origem (SNAT) para permitir tráfego de saída, que permite que a conectividade de Internet faça download dos pré-requisitos do {{site.data.keyword.icpfull_notm}} e se conecte ao GitHub e ao Docker. Como alternativa, é possível usar um proxy da web para conectividade de Internet. O ESG também é configurado para fornecer acesso a serviços DNS e NTP.

O ESG também é configurado com uma regra NAT de destino (DNAT) para os endereços IP virtuais Principais/Proxy do {{site.data.keyword.icpfull_notm}} da rede {{site.data.keyword.cloud_notm}} 10.x para o ambiente VXLAN.

## Links relacionados
{: #vcscar-arch-overview-infrastructure-related}

* [Visão geral do vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle](/docs/services/vmwaresolutions/archiref/vcs?topic=vmware-solutions-vcs-hybridity-intro)
