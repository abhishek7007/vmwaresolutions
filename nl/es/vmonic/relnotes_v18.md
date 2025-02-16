---

copyright:

  years:  2016, 2017

lastupdated: "2017-08-28"

subcollection: vmware-solutions


---

# Notas del release para V1.8
{: #relnotes_v18}

Este release incluye nuevas características, actualizaciones de componentes, mejoras en la usabilidad y correcciones de errores. Para ver una lista de los problemas solucionados en distintos releases, problemas conocidos del producto y sugerencias para utilizar {{site.data.keyword.vmwaresolutions_full}}, consulte [{{site.data.keyword.vmwaresolutions_short}} dW Answers](https://developer.ibm.com/answers/topics/cloudvmw/){:new_window}.

## Servicio Fortinet on IBM Cloud
{: #relnotes_v18-fortinet}

El servicio Fortinet on {{site.data.keyword.cloud_notm}} ya está disponible tanto para instancias de Cloud Foundation como para instancias de vCenter Server. Este servicio despliega un par de dispositivos FortiGate Security Appliance (FSA) serie 300 en modalidad altamente disponible para ofrecer servicios de cortafuegos, direccionamiento, NAT y VPN para proteger todos los servidores y máquinas virtuales de la VLAN pública de sus instancias. Puede solicitar instancias con el servicio Fortinet incluido al solicitar la instancia, o puede añadir este servicio a las instancias existentes más adelante desde la página de detalles de la instancia.

Después de que se instale correctamente el servicio Fortinet, podrá gestionar y configurar reglas de cortafuegos para FSA desde la consola de FortiGate. Debe asegurarse de que las reglas de cortafuegos de FSA estén definidas de modo que permitan comunicaciones HTTPS salientes iniciadas por componentes de gestión, como la máquina virtual IBM CloudDriver o la máquina virtual Zerto, para establecer comunicación con la base de datos de gestión externa de IBM Bluemix® a través de Internet. Las comunicaciones HTTPS salientes se originan en la dirección IP pública de los servicios de gestión de VMware NSX Edge Services Gateway (ESG) de su instancia.

Para obtener más información, consulte los temas siguientes:
* [Visión general de Fortinet on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-fsa_considerations)
* [Gestión de Fortinet on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-managingfsa)

## Servicio Veeam on IBM Cloud
{: #relnotes_v18-veeam}

Este release incorpora el servicio Veeam on {{site.data.keyword.cloud_notm}}, que puede hacer copia de seguridad de las cargas de trabajo y de los componentes de gestión. El nuevo servicio sustituye la VSI de Veeam anterior que venía integrada en los releases anteriores a V1.8 solo para los componentes de copia de seguridad y de gestión.

Debido a este cambio, aunque la VSI Veeam de las instancias anteriores a V1.8 sigue funcionando, los puntos de copia seguridad para las instancias ya no están disponibles en la consola de {{site.data.keyword.vmwaresolutions_short}} y debe crear una incidencia de soporte para obtener ayuda con una restauración.

Además, la licencia de la VSI de Veeam en instancias anteriores a V1.8 caducó el 14 de octubre de 2017. Por lo tanto, debe sustituir la VSI de Veeam anterior por el nuevo servicio Veeam en cuando pueda.

Para obtener más información, consulte los temas siguientes:
* [Visión general de Veeam on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-veeam_considerations)
* [Gestión de Veeam on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-managingveeam)

## Actualizaciones de instancias de VMware Cloud Foundation
{: #relnotes_v18-vcf}

### Puede traer sus propias licencias (BYOL) de VMware cuando solicite instancias de Cloud Foundation
{: #relnotes_v18-byol}

A partir del release V1.8, cuando solicite una instancia de Cloud Foundation, dispone de dos opciones para obtener licencias de los componentes de VMware de la instancia, que incluyen vSphere, vCenter Server, NSX y vSAN. Puede utilizar nuevas licencias que se deben adquirir en su nombre.

También puede optar por utilizar su propia licencia de VMware para un componente, en cuyo caso debe proporcionar las claves de licencia. En este caso, el soporte para los componentes de VMware para los que suministre licencias lo ofrece VMware, no el equipo de soporte de IBM.

## Actualizaciones de instancias de VMware vCenter Server
{: #relnotes_v18-vcs}

### Personalice la CPU y la memoria de su instancia
{: #relnotes_v18-custom-cpu}

Dispone de una opción de servidor personalizable junto con las opciones integradas y probadas Pequeño, Medio y Grande. Puede realizar su selección en una lista de servicios compatibles con HCL de VMware en función de las CPU duales y del número total de núcleos, además de la cantidad de RAM. El almacenamiento local no se puede personalizar.

Para obtener más información, consulte los temas siguientes:
* [Pedido de instancias de vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance)
* [Adición, visualización y supresión de clústeres para instancias de vCenter Server](/docs/services/vmwaresolutions?topic=vmware-solutions-vc_addingviewingclusters#vc_addingviewingclusters)

### Soporte para añadir más de 7 comparticiones de archivos NFS
{: #relnotes_v18-nfs}

 Puede conectar hasta un máximo de 32 comparticiones de archivos entre todos los servidores ESXi de un clúster.

 Para obtener más información, consulte los temas siguientes:
* [Pedido de instancias de vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_orderinginstance)
* [Adición, visualización y supresión de clústeres para instancias de vCenter Server](/docs/services/vmwaresolutions?topic=vmware-solutions-vc_addingviewingclusters#vc_addingviewingclusters)

### Actualizaciones de centros de datos
{: #relnotes_v18-dc}

Dispone de los siguientes nuevos centros de datos para el despliegue: **DAL-09, DAL-12, DAL-13 - Dallas**; **LON-04, LON-06 - Londres**; **SJC-04 - San José**; **WDC-06, WDC-07 - Washington, DC**

Para obtener más información, consulte [Requisitos y planificación de instancias de vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_planning)

## Mejoras en la usabilidad
{: #relnotes_v18-ui}

Se han realizado mejoras en la interfaz de usuario:
* Puede obtener información sobre los servicios y solicitar una instancia en la página **Cómo comenzar** del panel de navegación izquierdo.
* Utilice el menú de desbordamiento de la página de detalles de la instancia para suprimir una instancia en estado **Listo para su uso**.
* La opción para actualizar la edición de la licencia de NSX ahora está disponible en el separador **Actualización y parche**. La actualización de licencia sustituye todas las licencias existentes de NSX en la cuenta de IBM SoftLayer por la nueva instancia.
* El separador **Copia de seguridad y restauración** de la página de detalles de la instancia ya no está disponible.
* Puede seleccionar varios servicios para desplegarlos al principio de un pedido. Además del servicio Zerto on {{site.data.keyword.cloud_notm}}, también dispone de opciones para seleccionar el servicio Veeam on {{site.data.keyword.cloud_notm}} y el servicio Fortinet on {{site.data.keyword.cloud_notm}}.
* Se ha cambiado el nombre del separador **Servicios disponibles** del separador **Servicios** de la página de detalles de la instancia por **Añadir servicios**.
