---

copyright:

  years:  2016, 2018

lastupdated: "2018-12-14"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}

# Notas del release para V2.7
{: #relnotes_v27}

Este release incluye nuevas características, actualizaciones de componentes, mejoras en la usabilidad y correcciones de errores. Para ver una lista de los problemas solucionados en distintos releases, problemas conocidos del producto y sugerencias para utilizar {{site.data.keyword.vmwaresolutions_full}}, consulte [{{site.data.keyword.vmwaresolutions_short}} dW Answers](https://developer.ibm.com/answers/topics/cloudvmw/){:new_window}.

## Soporte de servidor 6140 certificado por SAP
{: #relnotes_v27-sap}

A partir del release V2.7, están disponibles los siguientes nuevos modelos de CPU de {{site.data.keyword.baremetal_short_sing}} de {{site.data.keyword.cloud_notm}} para su despliegue en instancias y clústeres de VMware vCenter Server on {{site.data.keyword.cloud_notm}} y VMware vSphere on {{site.data.keyword.cloud_notm}}:
* Procesador Dual Intel Xeon Gold 6140 / 36 núcleos en total, 2,3 GHz / 192 GB de RAM
* Procesador Dual Intel Xeon Gold 6140 / 36 núcleos en total, 2,2 GHz / 384 GB de RAM
* Procesador Dual Intel Xeon Gold 6140 / 36 núcleos en total, 2,3 GHz / 768 GB de RAM

Para obtener más información, consulte la sección *Configuración de {{site.data.keyword.baremetal_short_sing}}* en:
* [Pedido de instancias de vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance#vc_orderinginstance-bare-metal-settings)
* [Solicitud de clústeres nuevos de vSphere](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_orderinginstances#vs_orderinginstances-bare-metal-settings)

## Actualizaciones de servicios complementarios
{: #relnotes_v27-services}

### IBM Cloud Private Hosted
{: #relnotes_v27-icp}

El servicio {{site.data.keyword.cloud_notm}} Private Hosted está ahora disponible para VMware vCenter Server con instancias de paquete híbrido (Hybridity), además de las instancias de VMware vCenter Server que se despliegan en (o que se han actualizado a) la versión V2.5 y releases posteriores. Ahora puede solicitar una instancia de vCenter Server o una instancia de vCenter Server con el paquete híbrido (Hybridity) con el servicio incluido. También puede añadir el servicio a una instancia existente de vCenter Server o de vCenter Server con el paquete híbrido (Hybridity) tras el despliegue inicial.

Para obtener más información, consulte los temas siguientes:
* [Visión general de {{site.data.keyword.cloud_notm}} Private Hosted](/docs/services/vmwaresolutions/services?topic=vmware-solutions-icp_overview)
* [Solicitud de {{site.data.keyword.cloud_notm}} Private Hosted](/docs/services/vmwaresolutions/services?topic=vmware-solutions-icp_ordering)

### Mission Critical VMware on IBM Cloud
{: #relnotes_v27-mcv}

El servicio Mission Critical VMware on {{site.data.keyword.cloud_notm}} ya está disponible para las instancias que se han desplegado en la V2.7 y posteriores releases o que se han actualizado a estos.

Mission Critical VMware on {{site.data.keyword.cloud_notm}} proporciona una arquitectura de nube multizona que ayuda a las empresas a evitar el tiempo de inactividad de las aplicaciones en la nube y a automatizar las migraciones tras error dentro de una región de nube. Con esta arquitectura de nube, puede conseguir una mayor disponibilidad y una tasa de éxito de migración tras error superior al que obtienen la mayoría de los clientes de VMware con entornos locales o con plataformas de nube de la competencia.

Para obtener más información, consulte [Visión general de Mission Critical VMware on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-mcv_overview).

### F5 on IBM Cloud
{: #relnotes_v27-f5}

Ahora, cuando solicite el servicio F5 on {{site.data.keyword.cloud_notm}}, puede seleccionar si desea que F5 aplique la licencia sobre la red pública o sobre la red privada con un servidor proxy. Para obtener más información, consulte [Solicitud de F5 on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-f5_ordering).

### FortiGate Virtual Appliance on IBM Cloud
{: #relnotes_v27-fva}

Durante el tercer trimestre de 2018, Fortinet ha modificado sus paquetes de suscripción. Para obtener más información, consulte [Solicitud de FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-fortinetvm_ordering).

Para el servicio FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}} que se despliega en instancias de Cloud Foundation y en instancias de vCenter Server V2.7 y posteriores, se suministran FortiOS 6.0.3.

Cuando solicite el servicio FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}}, puede seleccionar si desea que FortiGuard aplique la licencia y las actualizaciones de seguridad sobre la red pública o sobre la red privada con un servidor proxy. Para obtener más información, consulte [Solicitud de FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-fortinetvm_ordering).

### Actualizaciones de componentes del servicio Zerto on IBM Cloud
{: #relnotes_v27-zerto}

Para el servicio Zerto on {{site.data.keyword.cloud_notm}} desplegado en instancias de Cloud Foundation y de vCenter Server V2.7 y posteriores, se suministra Zerto Virtual Replication 6.0 actualización 3. Para obtener más información, consulte [Visión general de Zerto on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-addingzertodr).

### Integración de KMIP for VMware on IBM Cloud con IBM Cloud Activity Tracker
{: #relnotes_v27-kmip-icat}

Además de los sucesos de instancia de VMware, ahora los sucesos correspondientes a KMIP for VMware on {{site.data.keyword.cloud_notm}}, como la creación de claves, la supresión de claves y el acceso a claves, están integrados con la instancia de {{site.data.keyword.cloud_notm}} Activity Tracker.

### KMIP for VMware on IBM Cloud - en desuso
{: #relnotes_v27-kmip-deprecated}

(Actualizado el 14 de diciembre de 2018) La versión actual de KMIP for VMware on {{site.data.keyword.cloud_notm}} ha quedado en desuso. Para obtener más información, [póngase en contacto con el equipo de soporte de IBM](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support).
{:deprecated}

## Documentación nueva y actualizada
{: #relnotes_v27-new-docs}

### Documentación de arquitectura de referencia
{: #relnotes_v27-ref-archi}

Los siguientes documentos técnicos están ahora disponibles en la sección *Consulta* de la documentación del usuario:

* [Arquitectura de la solución NSX Edge Services Gateway](/docs/services/vmwaresolutions/archiref/nsx?topic=vmware-solutions-nsx_overview)
* [Guía de VMware Update Manager](/docs/services/vmwaresolutions/archiref/vum?topic=vmware-solutions-vum-intro)
* [Guía del sistema de red de vCenter Server](/docs/services/vmwaresolutions/archiref/vcsnsxt?topic=vmware-solutions-vcsnsxt-intro)
* [Guía de vCenter Server e {{site.data.keyword.cloud_notm}} Private](/docs/services/vmwaresolutions/archiref/vcsicp?topic=vmware-solutions-vcsicp-intro)
* [Guía de vCenter Server y del servicio IBM Kubernetes](/docs/services/vmwaresolutions/archiref/vcsiks?topic=vmware-solutions-vcsiks-intro)
* [Guía de VMware y Skate Advisor Concept Car](/docs/services/vmwaresolutions/archiref/vcscar?topic=vmware-solutions-vcscar-intro)
* [VMware: el proceso de modernización de Stock Trader](/docs/services/vmwaresolutions/archiref/vcscontent?topic=vmware-solutions-vcscontent-modjourney)

## Actualizaciones y mejoras de la interfaz de usuario
{: #relnotes_v27-ui}

La interfaz de usuario se actualiza y proporciona las mejoras siguientes:

* El separador **Personalizado** que aparecía al especificar el modelo de CPU y la RAM para los valores de {{site.data.keyword.baremetal_short_sing}} al solicitar instancias se ha dividido en el separador **Skylake** y el separador **Broadwell**, en función del tipo de servidor, para ayudarle a seleccionar el servidor.
* Las opciones **preconfiguradas** para la configuración del servidor nativo ya no están disponibles.
* Ahora la columna **Tipo** se incluye en la tabla **Instancias de vCenter Server** en la página **Recursos** para identificar las instancias de vCenter Server, vCenter Server con el paquete híbrido (Hybridity) y vCenter Limited Test Drive.
* Hay varios mensajes de error y mejoras de ayuda contextual disponibles para ayudarle a seleccionar el valor adecuado en la interfaz de usuario.
