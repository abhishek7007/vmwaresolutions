---

copyright:

  years:  2016, 2019

lastupdated: "2019-02-14"

---

# Lidando com as vulnerabilidades Spectre e Meltdown
{: #trbl_fix_spectre}

Para lidar com as vulnerabilidades Spectre e Meltdown, deve-se aplicar várias correções em uma ordem específica.

## Atualizando o firmware
{: #trbl_fix_spectre-firmware-update}

Para obter as informações mais recentes sobre como atualizar o firmware, veja [Proteção contra vulnerabilidades de segurança recentes](https://www.ibm.com/blogs/bluemix/2018/01/ibm-cloud-spectre-meltdown-vulnerabilities/).

## Atualizando instâncias que foram implementadas na V2.0 ou mais recente
{: #trbl_fix_spectre-instance2.0-update}

Instâncias da V2.0 ou mais recente foram implementadas com o VMware vSphere 6.5 e o VMware vCenter Server 6.5. Ambos os componentes de software requerem correção.

### Instâncias do vCenter Server que foram implementadas na V2.0 ou mais recente
{: #trbl_fix_spectre-vcs2.0}

#### Para VMware vSphere 6.5
{: #trbl_fix_spectre-vcs2.0-vsphere}

* Para todas as novas instâncias da V2.6, o vSphere será implementado com as seguintes correções aplicadas: ESXi650-201712101-SG, ESXi650-201803401-BG, ESXi650-201803402-BG, ESXi650-201808401-BG, ESXi650-201808402-BG e ESXi650-201808403-BG.
* Para todas as instâncias existentes implementadas antes da V2.5, mas submetidas a upgrade para a V2.5, todos os novos clusters e servidores ESXi serão atualizados com as seguintes correções: ESXi650-201712101-SG, ESXi650-201803401-BG, ESXi650-201803402-BG, ESXi650-201808401-BG, ESXi650-201808402-BG e ESXi650-201808403-BG.
* Para todos os servidores ESXi existentes e para quaisquer clusters ou servidores ESXi que você continua a implementar antes de fazer upgrade para a V2.5, deve-se aplicar as seguintes correções: ESXi650-201712101-SG, ESXi650-201803401-BG, ESXi650-201803402-BG, ESXi650-201808401-BG, ESXi650-201808402-BG e ESXi650-201808403-BG por meio do [site de Correções do produto VMware](https://my.vmware.com/group/vmware/patch).

#### Para o VMware vCenter Server 6.5
{: #trbl_fix_spectre-vcs2.0-vcenter}

* Para todas as novas instâncias da V2.6, o vCenter Server será implementado com as correções acumulativas do vCenter 6.5 U2c aplicadas.
* Para todas as instâncias existentes implementadas antes da V2.6, deve-se aplicar a correção vCenter 6.5 U2c por meio do [site de Correções do produto VMware](https://my.vmware.com/group/vmware/patch).

### Instâncias do Cloud Foundation que foram implementadas na V2.0 ou mais recente
{: #trbl_fix_spectre-cf2.0}

Para aplicar as correções necessárias para o VMware vSphere 6.5 e o VMware vCenter Server 6.5, deve-se fazer upgrade de suas instâncias do Cloud Foundation para o pacote configurável de correções mais recente do VMware. Para todas as instâncias e servidores ESXi existentes, você será solicitado a aplicar as correções na página **Atualização e correção** do console do {{site.data.keyword.vmwaresolutions_full}}. Para obter mais informações, veja [Aplicando atualizações a instâncias do Cloud Foundation](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_applyingupdates).

### Clusters do VMware vSphere que foram implementados na V2.0 ou mais recente
{: #trbl_fix_spectre-vss2.0}

Para todos os novos clusters e servidores ESXi do VMware vSphere 6.5, deve-se aplicar as seguintes correções: ESXi650-201808401-BG, ESXi650-201808402-BG e ESXi650-201808403-BG, por meio do [site de Correções do produto VMware](https://my.vmware.com/group/vmware/patch).

Para todos os clusters existentes do VMware vSphere 6.5, deve-se aplicar as seguintes correções: ESXi650-201712101-SG, ESXi650-201803401-BG, ESXi650-201803402-BG, ESXi650-201808401-BG, ESXi650-201808402-BG e ESXi650-201808403-BG, por meio do [site de Correções do produto VMware](https://my.vmware.com/group/vmware/patch).

Para o VMware vCenter Server 6.5, deve-se aplicar a correção vCenter 6.5 U2c por meio do [site de Correções do produto VMware](https://my.vmware.com/group/vmware/patch) a todos os servidores vCenter, recém-implementados ou existentes.

## Instâncias que foram implementadas na V1.9 ou anterior
{: #trbl_fix_spectre-instance1.9-update}

Instâncias do Cloud Foundation, instâncias do vCenter Server e clusters do VMware vSphere da V1.9 ou anterior foram implementados com o VMware vSphere 6.0 e o VMware vCenter Server 6.0.

### Instâncias do vCenter Server que foram implementadas na V1.9 ou anterior
{: #trbl_fix_spectre-vcs1.9}

Para o VMware vSphere 6.0 e o VMware vCenter Server 6.0, deve-se aplicar as correções (ESXi600-201711101-SG, ESXi600-201803401-BG, ESXi600-201803402-BG, ESXi600-201808401-BG, ESXi600-201808402-BG e ESXi600-201808403-BG para o vSphere e o vCenter 6.0 U3h para o vCenter Server) por meio do [site de Correções do produto VMware](https://my.vmware.com/group/vmware/patch) a todas as instâncias e servidores ESXi, recém-implementadas ou existentes.

### Instâncias do Cloud Foundation que foram implementadas na V1.9 ou anterior
{: #trbl_fix_spectre-cf1.9}

Atualizações para essas instâncias estarão disponíveis quando as atualizações necessárias do fornecedor das quais essas instâncias dependem forem liberadas.

### Clusters do VMware vSphere que foram implementados na V1.9 ou anterior
{: #trbl_fix_spectre-vss1.9}

Para o VMware vSphere 6.0 e o VMware vCenter Server 6.0, deve-se aplicar as correções (ESXi600-201711101-SG, ESXi600-201803401-BG, ESXi600-201803402-BG, ESXi600-201808401-BG, ESXi600-201808402-BG e ESXi600-201808403-BG para o vSphere e o vCenter 6.0 U3h para o vCenter Server) por meio do [site de Correções do produto VMware](https://my.vmware.com/group/vmware/patch) a todos os clusters do vSphere e servidores ESXi, recém-implementados ou existentes.

## Links relacionados
{: #trbl_fix_spectre-related}

* [Aplicando atualizações a instâncias do Cloud Foundation](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_applyingupdates)
* [Proteger contra vulnerabilidades de segurança recentes](https://www.ibm.com/blogs/bluemix/2018/01/ibm-cloud-spectre-meltdown-vulnerabilities/)
* [Site de Correções de Produtos VMware](https://my.vmware.com/group/vmware/patch)
