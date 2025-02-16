---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-16"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Gerenciando contas de usuário e configurações
{: #useraccount}

O {{site.data.keyword.vmwaresolutions_full}} se comunica com a infraestrutura do {{site.data.keyword.cloud_notm}} por meio de chamadas do {{site.data.keyword.slapi_short}}. Para acessar o {{site.data.keyword.slapi_short}} com segurança, deve-se vincular as credenciais de sua conta de infraestrutura do {{site.data.keyword.cloud_notm}} à sua conta do {{site.data.keyword.cloud_notm}}.

Também é possível especificar se você deseja receber notificações por e-mail e do console para vários eventos.

## Antes de iniciar
{: #useraccount-reqs}

* É possível vincular somente uma conta de infraestrutura do {{site.data.keyword.cloud_notm}} a uma conta do usuário do {{site.data.keyword.cloud_notm}}.
* A conta de infraestrutura do {{site.data.keyword.cloud_notm}} que você está usando deve atender a determinados requisitos. Para obter mais informações, consulte [Requisitos de conta da infraestrutura do {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-slaccountrequirement).
* Se a chave API para sua conta de infraestrutura do {{site.data.keyword.cloud_notm}} muda, deve-se atualizar a chave na página **Configurações** no console do {{site.data.keyword.vmwaresolutions_short}}.

   **Importante:** é sua responsabilidade assegurar que a chave API salva na página **Configurações** esteja correta e atualizada. Caso contrário, as operações que requerem validação da chave API podem falhar.

## Procedimento para gerenciar contas do usuário e configurações
{: #useraccount-procedure}

1. No console do {{site.data.keyword.vmwaresolutions_short}}, clique em **Configurações** na área de janela de navegação esquerda.
2. Na área **Notificações**, especifique suas configurações de notificação.
   * Se você desejar ser notificado por e-mail quando eventos ocorrerem, clique em **Ativar notificações por e-mail**.
   * Se você desejar ser notificado no console quando eventos ocorrerem, clique em **Ativar notificações do console**.
3. Na área **Credenciais de infraestrutura do IBM Cloud**, insira o nome do usuário e a chave de API de sua conta de infraestrutura do {{site.data.keyword.cloud_notm}}:
   * Se a sua conta de infraestrutura do {{site.data.keyword.cloud_notm}} e sua conta do {{site.data.keyword.cloud_notm}} estão vinculadas, clique em **Recuperar** para inserir as credenciais automaticamente.
   * Se a sua conta de infraestrutura do {{site.data.keyword.cloud_notm}} e sua conta do {{site.data.keyword.cloud_notm}} não estão vinculadas, deve-se vinculá-las. Efetue login no [Portal do cliente de infraestrutura do{{site.data.keyword.cloud_notm}}](https://control.softlayer.com/) e siga as instruções no console para obter as credenciais e, em seguida, insira-as.
   * Se você não tem uma conta de infraestrutura do {{site.data.keyword.cloud_notm}}, [inscreva-se para uma](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-signing_softlayer_account) e siga as instruções no console para obter as credenciais e, em seguida, insira-as.
4. Clique em **Salvar Credenciais**.

## Resultados
{: #useraccount-results}

Depois que a conta do {{site.data.keyword.cloud_notm}} e a conta de infraestrutura do {{site.data.keyword.cloud_notm}} são vinculadas, o console recupera automaticamente as credenciais de conta de infraestrutura do {{site.data.keyword.cloud_notm}} para se comunicar com o ambiente do VMware no {{site.data.keyword.cloud_notm}}.

As credenciais de conta de infraestrutura armazenadas do {{site.data.keyword.cloud_notm}} são usadas em operações futuras que requerem interação com a infraestrutura do {{site.data.keyword.cloud_notm}}.

Se as notificações por e-mail ou de console estiverem ativadas para determinados eventos de instância, você será notificado por e-mail ou mensagens do console quando esses eventos ocorrerem.

## Links relacionados
{: #useraccount-related}

* [Perguntas mais frequentes](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-faq)
* [Pedindo instâncias do vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance)
* [Notificações](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-notifications)
* [SoftLayer API](/docs/customer-portal?topic=customer-portal-customerportal_api)
