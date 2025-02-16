---

copyright:

  years:  2016

lastupdated: "2016-11-04"

subcollection: vmware-solutions


---

# Notas sobre a liberação para V1.1
{: #relnotes_v11}

Esta liberação inclui novos recursos, aprimoramentos de usabilidade e correções de bug. Para obter uma lista de problemas corrigidos em diferentes liberações, problemas conhecidos com o produto e dicas para usar o {{site.data.keyword.vmwaresolutions_full}}, consulte o [{{site.data.keyword.vmwaresolutions_short}}dW Answers](https://developer.ibm.com/answers/topics/cloudvmw/){:new_window}.

## Requisito de ampliação da VLAN
{: #relnotes_v11-vlan-spanning}

Se você estiver usando uma conta SoftLayer® clássica (não VRF), a ampliação da VLAN deverá ser ativada. Se a ampliação da VLAN não estiver ativada para contas clássicas, os vários componentes do ambiente de virtualização do VMware poderão não ser capazes de se comunicar entre si. Para ativar a ampliação da VLAN em sua conta SoftLayer, veja [Ativar ou desativar a VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning){:new_window}.

## Configurações e notificações por e-mail
{: #relnotes_v11-email}

É possível configurar as notificações por e-mail na página **Configurações**. Por padrão, a configuração é ativada, o que significa que você recebe uma notificação por e-mail para qualquer instância recém-pedida, quando essa instância é fornecida e está pronta para uso. É possível também desativar as notificações por e-mail na página **Configurações**. Para obter mais informações, veja [Contas e configurações do usuário](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-useraccount).

## Informações de status detalhadas
{: #relnotes_v11-status-info}

As informações de status detalhadas estão, agora, disponíveis para instâncias do Cloud Foundation. Quando você clica no nome de uma instância, as informações de status que são exibidas fornecem mais detalhes sobre o progresso da implementação. Se ocorrer um erro, serão exibidas mensagens para ajudá-lo com o problema.
