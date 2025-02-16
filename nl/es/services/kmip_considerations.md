---

copyright:

  years:  2016, 2019

lastupdated: "2019-02-15"

---

{:tip: .tip}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}

# Visión general de KMIP for VMware on IBM Cloud - en desuso
{: #kmip_considerations}

La versión actual de KMIP for VMware on IBM Cloud ha quedado en desuso. Para obtener más información, [póngase en contacto con el equipo de soporte de IBM](../vmonic/trbl_support.html).
{:deprecated}

El servicio KMIP for VMware on {{site.data.keyword.cloud}} ofrece un servicio altamente disponible de tipo 24x7 para gestionar las claves de cifrado que utiliza VMware en {{site.data.keyword.cloud_notm}}. Este servicio ofrece capacidad de tiempo de ejecución que permite a los clientes crear, recuperar, activar, revocar y destruir las claves de cifrado. También proporciona capacidad de gestión para mantener las asociaciones entre las credenciales del cliente y las claves de cifrado.

## Especificaciones técnicas para KMIP for VMware on IBM Cloud
{: #kmip_considerations-specs}

Las siguientes especificaciones se incluyen con el servicio KMIP for VMware on {{site.data.keyword.cloud_notm}}:

* Un protocolo Key Management Interoperability (KMIP) compatible con VMware
* Un servicio gestionado
* Disponible en múltiples regiones geográficas de todo el mundo
* Un punto final de servicio KMIP altamente disponible en cada región

## Consideraciones al instalar KMIP for VMware on IBM Cloud
{: #kmip_considerations-install}

KMIP for VMware on {{site.data.keyword.cloud_notm}} utiliza el servicio IBM Key Protect para {{site.data.keyword.cloud_notm}} para crear, cifrar y descifrar claves de cifrado. Por lo tanto, antes de instalar KMIP para VMware en {{site.data.keyword.cloud_notm}}, asegúrese de que:
* Ha solicitado un servicio utilizable de Key Protect.
* Se ha creado un ID de servicio de {{site.data.keyword.cloud_notm}} siguiendo los pasos indicados en [Creación de un ID de servicio](../../../iam/serviceid.html). Este ID de servicio se utiliza para acceder a la instancia del servicio Key Protect que ha creado.
* Ha otorgado los siguientes niveles de acceso al ID de servicio:
   * A nivel de acceso a la plataforma: autorización de visualización a la instancia de IBM Key Protect.
   * A nivel de acceso al servicio: autorización de escritura a la de IBM Key Protect.
* Tiene una clave de API para el ID de servicio creado. La clave es necesaria al solicitar el servicio.
* Ha creado al menos una clave raíz de cliente (CRK) desde la interfaz de usuario de Key Protect siguiendo los pasos del apartado [Creación de claves raíz](../../keymgmt/keyprotect_create_root.html) o utilizando la API REST de [IBM Key Protect](https://cloud.ibm.com/apidocs/key-protect).

   **Importante:** No puede solicitar el servicio sin CRK. Se recomienda utilizar el método para crear una CRK utilizando el material de claves existente y hacer una copia de seguridad del material de claves que se crea. De este modo se asegura de que puede recuperar sus claves en el caso de que se produzca un fallo del centro de datos en el que se aplica IBM Key Protect para almacenar los CRK.

## Consideraciones al utilizar KMIP for VMware on IBM Cloud
{: #kmip_considerations-use}

* Para utilizar un servicio KMIP for VMware on {{site.data.keyword.cloud_notm}} solicitado como Servidor de gestión de claves (KMS) registrado ante VMware vCenter Server, asegúrese de que la conectividad de red entre vCenter Server y el punto final del servicio KMIP for VMware on {{site.data.keyword.cloud_notm}} solicitado resulte funcional.
* Para utilizar el servicio con el cifrado de VMware vSAN, asegúrese de que la conectividad de red entre los hosts del vSAN de destino y el punto final del servicio KMIP for VMware on {{site.data.keyword.cloud_notm}} resulte funcional.
* Cuando utiliza KMIP for VMware con cifrado de vSAN, la comprobación de estado de vSAN puede emitir avisos periódicos que indican que no se puede conectar al clúster de KMS desde uno de los hosts de vSphere. Estos avisos se producen porque el tiempo de espera de conexión de la comprobación de estado de vSAN se excede demasiado rápido. Puede pasar por alto estos avisos.

## Consideraciones sobre la eliminación de KMIP para VMware on IBM Cloud
{: #kmip_considerations-remove}

El certificado público de VMware que proporcione durante la solicitud o la utilización del servicio se utiliza como el certificado cliente para comunicarse con la instancia de servicio. Cuando se elimine el servicio, también se eliminan todas las claves de cifrado creadas por esta instancia de servicio para el certificado público de VMware asociado.

Por lo tanto, antes de eliminar el servicio, asegúrese de que ninguna máquina virtual o vSAN se cifren utilizando las claves creadas por el servicio KMIP.

## Enlaces relacionados
{: #kmip_considerations-related}

* [Solicitud de KMIP for VMware on {{site.data.keyword.cloud_notm}}](kmip_ordering.html)
* [Sucesos de {{site.data.keyword.cloudaccesstrailshort}}](../vmonic/at-events.html)
* [IBM Key Protect para {{site.data.keyword.cloud_notm}}](../../keymgmt/index.html)
* [Seguridad de vSphere](https://docs.vmware.com/en/VMware-vSphere/6.5/com.vmware.vsphere.security.doc/GUID-52188148-C579-4F6A-8335-CFBCE0DD2167.html)
* [Preguntas frecuentes](../vmonic/faq.html)
* [Cómo ponerse en contacto con el equipo de soporte de IBM](../vmonic/trbl_support.html)
