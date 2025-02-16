---

copyright:

  years:  2016, 2019

lastupdated: "2019-05-13"

subcollection: vmware-solutions


---

# Migrando instâncias do NetApp ONTAP Select pré-V2.5 para contas do IBM Cloud
{: #np_addinstancetousraccount}

As instâncias do NetApp ONTAP Select que são implementadas na V2.5 e liberações mais recentes em sua conta do {{site.data.keyword.cloud}} são incluídas automaticamente em sua conta e são gerenciadas pelo {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM).

Para obter instâncias que foram implementadas na V2.4 e em liberações anteriores, é possível migrá-las para contas especificadas do {{site.data.keyword.cloud_notm}} para gerenciamento de usuário ativado pelo IAM.

## Antes de iniciar
{: #np_addinstancetousraccount-prereq}

Assegure-se de que a conta do {{site.data.keyword.cloud_notm}} para a qual você deseja migrar a instância não seja uma conta somente IaaS. Uma conta somente IaaS é uma conta de infraestrutura {{site.data.keyword.cloud_notm}} (IBM Cloud) que não está vinculada a uma conta do {{site.data.keyword.cloud_notm}}.

Para obter mais informações sobre como vincular sua conta somente IaaS à sua conta PaaS, consulte [Siga estas etapas para vincular suas contas IaaS e PaaS](https://www.ibm.com/cloud/blog/follow-steps-link-iaas-paas-accounts){:new_window}.

## Procedimento para migrar instâncias
{: #np_addinstancetousraccount-procedure}

1. No console do {{site.data.keyword.vmwaresolutions_short}}, clique em **Recursos** na área de janela de navegação esquerda.
2. No banner do console, clique em seu ícone de conta do usuário e, em seguida, clique no campo **Conta** para selecionar a conta do usuário para a qual deseja migrar a instância.
3. Na tabela **Instâncias do NetApp ONTAP Select**, localize a instância pré-V2.5.
4. Na coluna **Ações**, clique no ícone de menu overflow e, em seguida, clique em **Migrar instância para a conta**.
5. Na janela **Migrar instância para a conta**, confirme a conta para a qual migrar a instância e, em seguida, clique em **Migrar**.

## Resultados
{: #np_addinstancetousraccount-results}

1. Você obtém uma notificação do console de que sua solicitação para migrar a instância para a conta especificada do {{site.data.keyword.cloud_notm}} foi aceita.
2. Quando a migração da instância for concluída, a instância será exibida na página **Recursos** sob a conta para a qual ela foi migrada. A instância migrada não é mais exibida na conta original da qual foi migrada.

## Links relacionados
{: #np_addinstancetousraccount-related}

* [ Gerenciando o acesso de usuário com o IAM ](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-iam#iam)
* [Convidando usuários para acessar serviços e recursos](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-iamuserinvite)
* [ O que é IBM Cloud IAM ](/docs/iam?topic=iam-iamoverview)
