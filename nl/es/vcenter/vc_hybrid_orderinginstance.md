---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-25"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Solicitud de instancias de vCenter Server con el paquete híbrido (Hybridity)
{: #vc_hybrid_orderinginstance}

Para desplegar una plataforma virtualizada VMware flexible y personalizable que se adapte perfectamente a sus necesidades de carga de trabajo, solicite una instancia de VMware vCenter Server on {{site.data.keyword.cloud}} con el paquete híbrido (Hybridity). El pedido de la instancia de vCenter Server con el paquete híbrido (Hybridity) incluye la licencia de VMware Hybrid Cloud Extension (HCX) y le autoriza al servicio de VMware HCX on {{site.data.keyword.cloud_notm}}. También puede añadir servicios, como [Zerto on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-addingzertodr), para la recuperación tras desastre.

## Requisitos para solicitar vCenter Server con instancias del paquete híbrido (Hybridity)
{: #vc_hybrid_orderinginstance-req}

Asegúrese de haber realizado las tareas siguientes:
*  Ha configurado las credenciales de la infraestructura de {{site.data.keyword.cloud_notm}} en la página **Configuración**. Para obtener más información, consulte [Gestión de cuentas y valores de usuario](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-useraccount).
*  Ha revisado la información de [Requisitos y planificación para vCenter Server con el paquete híbrido (Hybridity)](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_planning).
* Ha revisado el formato del nombre de dominio e instancia. El nombre de dominio y la etiqueta de subdominio se utilizan para generar el nombre de usuario y los nombres de servidor de la instancia.

Tabla 1. Formato del valor de nombres de instancia y de dominio

| Nombre        | Formato del valor      |
  |:------------- |:------------- |
  | Nombre de dominio | `<root_domain>` |  
  | Nombre usuario inicio sesión vCenter Server | `<user_id>@<root_domain>` (usuario de Microsoft Active Directory) o `administrator@vsphere.local` |
  | vCenter Server (con PSC incorporado) FQDN | `vcenter-<subdomain_label>.<subdomain_label>.<root_domain>`. La longitud máxima es de 50 caracteres. |
  | Nombre sitio inicio sesión único (SSO) | `<subdomain_label>` |
  | Nombre completo de servidor ESXi | `<host_prefix><n>.<subdomain_label>.<root_domain>`, donde `<n>` es la secuencia del servidor ESXi. La longitud máxima es de 50 caracteres. |

No modifique ningún valor definido durante la solicitud o el despliegue de la instancia. Hacerlo puede hacer que la instancia se vuelva inutilizable. Por ejemplo, si se cierra la red pública, si los servidores y las Instancias de servidor virtual (VSI) se mueven detrás de una media disposición de Vyatta, o si el VSI de IBM CloudBuilder se detiene o se suprime.
{:important}

## Valores del sistema
{: #vc_hybrid_orderinginstance-sys-settings}

Debe especificar los siguientes valores del sistema cuando solicite una instancia de vCenter Server con el paquete híbrido (Hybridity).

### Nombre de instancia
{: #vc_hybrid_orderinginstance-inst-name}

El nombre de instancia debe cumplir los siguientes requisitos:
* Solo se permiten caracteres alfanuméricos y el guión (-).
* El nombre de instancia debe empezar por un carácter alfabético y terminar por un carácter alfanumérico.
* La longitud máxima del nombre de instancia es de 10 caracteres.
* El nombre de instancia debe ser exclusivo dentro de su cuenta.

### Licencias de VMware vSphere
{: #vc_hybrid_orderinginstance-vsphere-license}

Seleccione si desea solicitar vSphere Enterprise Plus 6.7u1 o vSphere Enterprise Plus 6.5u2.

vSphere Enterprise Plus 6.7u1 está disponible solo para {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} Broadwell y Skylake.
{:note}

### Primaria o secundaria
{: #vc_hybrid_orderinginstance-primary-secondary}

Seleccione si desea solicitar una nueva instancia primaria o una instancia secundaria para una instancia primaria existente.

## Valores de licencia
{: #vc_hybrid_orderinginstance-licensing-settings}

Las siguientes licencias de VMware se incluyen con el pedido de instancia de vCenter Server con el paquete híbrido (Hybridity). Debe especificar la edición para las licencias NSX y vSAN.

* vCenter Server 6.5
* vSphere Enterprise Plus 6.5 o 6.7
* NSX Service Providers 6.4 (edición Advanced o Enterprise)
* vSAN 6.6 (edición Advanced o Enterprise)

### Atención:
{: #vc_hybrid_orderinginstance-attention}

* Las instancias de vCenter Server con el paquete híbrido (Hybridity) no admiten la opción de traer su propia licencia.
* Las ediciones de licencia mínimas se indican en la interfaz de usuario. Si se da soporte a distintas ediciones de componentes, puede seleccionar la edición que desee.

## Valores de Servidor nativo
{: #vc_hybrid_orderinginstance-bare-metal-settings}

Los valores de servidor nativo dependen de la selección del {{site.data.keyword.CloudDataCent_notm}} y de la configuración del servidor nativo.

Se necesitan cuatro servidores ESXi para el clúster inicial y los clústeres posteriores al despliegue para las configuraciones de vSAN. Todos los servidores ESXi comparten la misma configuración. Después del despliegue, puede añadir cuatro clústeres más.

### Ubicación del centro de datos
{: #vc_hybrid_orderinginstance-dc-location}

Seleccione el {{site.data.keyword.CloudDataCent_notm}} en el que se alojará la instancia.

### Skylake
{: #vc_hybrid_orderinginstance-skylake}

Si selecciona **Skylake**, puede elegir la combinación de CPU y RAM del servidor nativo que se ajuste a sus necesidades.

Tabla 2. Opciones para {{site.data.keyword.baremetal_short}} Skylake

| Opciones de modelo de CPU        | Opciones de RAM       |
|:------------- |:------------- |
| Procesador Dual Intel Xeon Silver 4110 / 16 núcleos en total, 2,1 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1,5 TB |
| Procesador Dual Intel Xeon Gold 5120 / 28 núcleos en total, 2,2 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1,5 TB |
| Dual Intel Xeon Gold Procesador 6140 / 36 núcleos en total, 2,3 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1,5 TB |

### Broadwell
{: #vc_hybrid_orderinginstance-broadwell}

Si selecciona **Broadwell**, puede elegir la combinación de CPU y RAM del servidor nativo que se ajuste a sus necesidades.

Tabla 3. Opciones para {{site.data.keyword.baremetal_short}} Broadwell

| Opciones de modelo de CPU        | Opciones de RAM       |
|:------------- |:------------- |
| Quad Intel Xeon E7-4820 v4 / 40 núcleos en total, 2,0 GHz | 128 GB, 256 GB, 512 GB, 1 TB, 2 TB, 3 TB |
| Quad Intel Xeon E7-4850 v4 / 64 núcleos en total, 2,1 GHz | 128 GB, 256 GB, 512 GB, 1 TB, 2 TB, 3 TB |

### Número de servidores nativos
{: #vc_hybrid_orderinginstance-bare-metal-number}

* Todos los servidores que solicite tienen la misma configuración.
* Puede solicitar entre 4 y 20 servidores.

## Valores de almacenamiento
{: #vc_hybrid_orderinginstance-storage-settings}

Se incluye VMware vSAN 6.6 en el pedido de la instancia de vCenter Server con el paquete híbrido (Hybridity). Especifique las siguientes opciones de vSAN:
* **Tipo y tamaño de disco para discos de capacidad vSAN**: Seleccione una opción para los discos de capacidad que necesite.
* **Número de discos de capacidad de vSAN**: Especifique el número de discos de capacidad que desea añadir.
* Si desea añadir discos de capacidad por encima del límite de 10, marque el recuadro **Intel Optane de alto rendimiento**. Esta opción proporciona dos bahías de disco de capacidad adicional para un total de 12 discos de capacidad y es útil para cargas de trabajo que requieren menos latencia y un rendimiento de IOPS más alto.

  La opción **Alto rendimiento con Intel Optane** está disponible únicamente para los modelos de CPU Skylake.
  {:note}

* Revise los valores **Tipo de disco para discos de memoria caché vSAN** y **Número de discos de memoria caché de vSAN**. Estos valores dependen de si ha marcado el recuadro **Intel Optane de alto rendimiento**.

## Valores de interfaz de red
{: #vc_hybrid_orderinginstance-network-interface-settings}

Debe especificar los siguientes valores de interfaz de red cuando solicite una instancia de vCenter Server con el paquete híbrido (Hybridity).

### Prefijo de nombre de host
{: #vc_hybrid_orderinginstance-host-name-prefix}

  El prefijo del nombre de host debe cumplir los siguientes requisitos:
  *  Solo se permiten caracteres alfanuméricos y el guión (-).
  *  El prefijo de nombre de host debe empezar y terminar por un carácter alfanumérico.
  *  La longitud máxima del prefijo de nombre de host es de 10 caracteres.

### Etiqueta de subdominio
{: #vc_hybrid_orderinginstance-subdomain-label}

La etiqueta de subdominio debe cumplir los siguientes requisitos:
*  Solo se permiten caracteres alfanuméricos y el guión (-).
*  La etiqueta de subdominio debe empezar por un carácter alfabético y terminar por un carácter alfanumérico.
*  La longitud máxima de la etiqueta de subdominio es de 10 caracteres.
*  La etiqueta de subdominio debe ser exclusiva dentro de su cuenta.

### Nombre de dominio
{: #vc_hybrid_orderinginstance-domain-name}

El nombre del dominio raíz debe cumplir los siguientes requisitos:
* El nombre de dominio debe constar de dos o más series de caracteres separadas por un punto (.)
* La primera serie debe empezar por un carácter alfabético y terminar por un carácter alfanumérico.
* Todas las series, excepto la última, solo pueden contener caracteres alfanuméricos y caracteres de guión (-).
* La última serie solo puede contener caracteres alfabéticos.
* La longitud de la última serie debe estar comprendida entre 2 y 24 caracteres.

La longitud máxima del FQDN (nombre de dominio completo) para hosts y máquinas virtuales (VM) es de 50 caracteres. Los nombres de dominio deben cumplir con esta longitud máxima.
{:note}

### Red pública o privada
{: #vc_hybrid_orderinginstance-public-private-network}

Los valores de habilitación de la tarjeta de interfaz de red (NIC) se basan en la selección de **Red pública y privada** o de **Solo red privada**.

Si selecciona la opción **Solo red privada**:
* No se suministrarán VMware NSX Edge Services Gateways (ESG) (ni ESG de servicios de gestión ni ESG gestionadas por el cliente).
* Los servicios de complemento siguientes, que requieren NIC públicas, no están disponibles:
  * F5 on {{site.data.keyword.cloud_notm}}
  * Fortigate Security Appliance on {{site.data.keyword.cloud_notm}}
  * Fortigate Virtual Appliance on {{site.data.keyword.cloud_notm}}

### Realizar pedido de nuevas VLAN
{: #vc_hybrid_orderinginstance-new-vlans}

Seleccione **Realizar pedido de nuevas VLAN** para solicitar una VLAN pública nueva y dos VLAN privadas nuevas.

Se necesita una VLAN pública y dos VLAN privadas para el pedido de la instancia. Las dos VLAN privadas se conectan en modalidad troncal en cada servidor nativo.

### Seleccionar las VLAN existentes
{: #vc_hybrid_orderinginstance-existing-vlans}

En función del {{site.data.keyword.CloudDataCent_notm}} que haya seleccionado, puede que haya VLAN públicas y privadas existentes disponibles.

Se necesita una VLAN pública y dos VLAN privadas para el pedido de la instancia. Las dos VLAN privadas se conectan en modalidad troncal en cada servidor nativo.

Seleccione **Seleccionar las VLAN existentes** para reutilizar las VLAN públicas y privadas existentes y elegir entre las VLAN y las subredes disponibles.

* Asegúrese de que la configuración del cortafuegos en las VLAN seleccionadas no bloquee el tráfico de datos de gestión.
* Asegúrese de que todas las VLAN que seleccione estén en el mismo pod, porque los servidores ESXi no se pueden suministrar en VLAN de pod mixtos.
{:important}

### Configuración DNS
{: #vc_hybrid_orderinginstance-dns-config}

Seleccione la configuración de DNS (sistema de nombres de dominio) para la instancia:

* **Una sola VSI pública de Windows para Active Directory/DNS**: Se despliega y se puede consultar una sola VSI de Microsoft Windows Server para Microsoft Active Directory (AD), que funciona como DNS para la instancia en la que se han registrado los hosts y VM.
* **Dos VM dedicadas y altamente disponibles de Windows Server en el clúster de gestión**: Se despliegan dos VM Microsoft Windows, que ayudan a mejorar la seguridad y la solidez.

Debe proporcionar dos licencias de Microsoft Windows Server 2016 si configura la instancia de modo que utilice las dos máquinas virtuales Microsoft Windows. Utilice la licencia de Microsoft Windows Server 2016 Standard Edition, o la licencia de Microsoft Windows Server 2016 Datacenter Edition, o ambas.
{:important}

Cada licencia solo se puede asignar a un solo servidor físico y cubre un máximo de dos procesadores físicos. Una licencia de Standard Edition puede ejecutar dos VM Microsoft Windows virtualizadas por servidor de 2 procesadores. Por lo tanto, se necesitan dos licencias, ya que se despliegan dos VM Microsoft Windows en dos hosts distintos.

Tiene 30 días para activar las VM.

Para obtener más información sobre cómo solicitar licencias de Windows Server 2016, consulte [Iniciación a Windows Server 2016](https://docs.microsoft.com/en-us/windows-server/get-started/server-basics){:new_window}.

## Valores de servicios
{: #vc_hybrid_orderinginstance-addon-services}

Cuando solicite una instancia de vCenter Server con el paquete híbrido (Hybridity), también puede solicitar servicios adicionales. Para obtener más información sobre los servicios, consulte [Servicios disponibles para instancias de vCenter Server con el paquete híbrido (Hybridity)](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_addingremovingservices#available-services-for-vcenter-server-with-hybridity-bundle-instances).

## Resumen del pedido
{: #vc_hybrid_orderinginstance-order-summary}

En función de la configuración seleccionada para la instancia y los servicios de complementos, el coste estimado se genera y se muestra al instante en la sección **Resumen de pedido** en el panel derecho. Pulse **Detalles sobre precios** en la parte inferior del panel derecho para generar un documento PDF que proporcione la información estimada.

## Procedimiento para solicitar instancias de vCenter Server con el paquete híbrido (Hybridity)
{: #vc_hybrid_orderinginstance-procedure}

1. Desde el catálogo de {{site.data.keyword.cloud_notm}}, pulse **VMware** desde el panel de navegación de la izquierda y, a continuación, pulse **vCenter Server** en la sección **Centros de datos virtuales**.
2. En la página **VMware vCenter Server on IBM Cloud**, pulse la tarjeta **vCenter Server con el paquete híbrido (Hybridity)** y pulse **Crear**.
3. En la página **vCenter Server**, escriba el nombre de la instancia.
5. Seleccione la versión de vSphere.
4. Seleccione el tipo de instancia:
   * Pulse **Instancia primaria** para desplegar una sola instancia en el entorno o para desplegar la primera instancia en una topología de varios sitios.
   * Pulse **Instancia secundaria** para conectar la instancia con una instancia existente (primaria) en el entorno para conseguir alta disponibilidad y siga estos pasos:
     1. Seleccione la instancia primaria a la que desea conectar la instancia secundaria.
     2. Para las instancias primarias V2.8 o posteriores, especifique la contraseña del administrador de vCenter Server para la instancia primaria.
     3. Para las instancias primarias V2.7 o anteriores, especifique la contraseña del administrador de PSC para la instancia primaria.
6. Seleccione la edición de licencia de NSX y la edición de licencia de vSAN.
7. Complete los valores del servidor nativo.
  1. Seleccione el {{site.data.keyword.CloudDataCent_notm}} que va a alojar la instancia.
  2. Seleccione el modelo de CPU y la cantidad de **RAM** de **Skylake** o **Broadwell**.
8. Complete la configuración del almacenamiento. Especifique los tipos de disco para la capacidad y los discos de memoria caché y el número de discos. Si desea más almacenamiento, marque el recuadro **Intel Optane de alto rendimiento**.
9. Complete la configuración de interfaz de red.
  1. Especifique el prefijo de nombre de host para la instancia que se va a suministrar, la etiqueta de subdominio y el nombre de dominio raíz.
  2. Seleccione el valor de red de **Red pública y privada** o **Solo red privada**.
  3. Seleccione la configuración de VLAN.
     *  Si desea solicitar nuevas VLAN públicas y privadas, pulse **Realizar pedido de nuevas VLAN**.
     *  Si desea reutilizar las VLAN públicas y privadas existentes cuando estén disponibles, pulse **Seleccionar las VLAN existentes** y luego seleccione la VLAN pública, la subred primaria, la VLAN privada, la subred primaria privada y la VLAN privada secundaria.
  4. Seleccione la configuración de DNS.
10. Complete la configuración para el servicio de HCX on {{site.data.keyword.cloud_notm}} incluido. Para obtener más información sobre cómo proporcionar valores para el servicio, consulte la sección _Configuración de VMware HCX on IBM Cloud_ en [Solicitud de VMware HCX on IBM Cloud](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcx_ordering#vmware-hcx-on-ibm-cloud-configuration).
11. Seleccione los servicios complementarios que desea desplegar en la instancia pulsando la tarjeta del servicio correspondiente. Si un servicio requiere configuración, complete los valores específicos del servicio y pulse **Añadir servicio** en la tarjeta.  
Para obtener más información sobre cómo proporcionar valores para un servicio, consulte el tema de ordenación de servicio correspondiente.

12. En el panel **Resumen del pedido**, verifique la configuración de la instancia antes de realizar el pedido.
   1. Revise los valores de la instancia.
   2. Revise el coste estimado de la instancia. Pulse **Detalles sobre precios** para generar un resumen en PDF. Para guardar o imprimir el resumen del pedido, pulse el icono **Imprimir** o **Descargar** en la parte superior derecha de la ventana del PDF.
   3. Pulse el enlace o enlaces de los términos que se aplican a su pedido y confirme que acepta estos términos antes de solicitar la instancia.
   4. Pulse **Suministro**.

## Resultados
{: #vc_hybrid_orderinginstance-results}

El despliegue de la instancia comienza automáticamente. Recibirá una confirmación de que el pedido se está procesando y puede comprobar el estado del despliegue consultando los detalles de la instancia.

Cuando la instancia se haya desplegado correctamente, los componentes que se describen en [Especificaciones técnicas para las instancias de vCenter Server con el paquete híbrido (Hybridity)](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_overview#specs) se instalan en la plataforma virtual de VMware. Los servidores ESXi que ha solicitado se agrupan de forma predeterminada como **cluster1**. Si ha solicitado servicios adicionales, el despliegue de los servicios se inicia después de que se haya completado el pedido.

Cuando la instancia esté lista para ser utilizada, el estado de la instancia pasará a ser **Listo para su uso** y recibirá una notificación por correo electrónico.

Cuando se solicita una instancia secundaria, es posible que el cliente web de VMware vSphere para la instancia primaria (enlazada a la secundaria) se rearranque cuando finalice el pedido de la instancia secundaria.

## Qué hacer a continuación
{: #vc_hybrid_orderinginstance-next}

Puede ver y gestionar la instancia de vCenter Server con el paquete híbrido (Hybridity) que ha solicitado.

Solo debe gestionar los componentes de {{site.data.keyword.vmwaresolutions_short}} que se crean en la cuenta de {{site.data.keyword.cloud_notm}} desde la consola de {{site.data.keyword.vmwaresolutions_short}}, no a través del {{site.data.keyword.slportal}} ni por ningún otro medio fuera de la consola.
Si cambia estos componentes fuera de la consola de {{site.data.keyword.vmwaresolutions_short}}, los cambios no se sincronizan con la consola.
{:important}

**ATENCIÓN:** el hecho de gestionar los componentes de {{site.data.keyword.vmwaresolutions_short}} (que se instalaron en la cuenta de {{site.data.keyword.cloud_notm}} al solicitar la instancia) desde fuera de la consola de {{site.data.keyword.vmwaresolutions_short}} podría hacer que el entorno quedara inestable. Estas actividades de gestión incluyen:
*  Añadir, modificar, devolver o eliminar componentes
*  Ampliar o reducir la capacidad de la instancia mediante la adición o eliminación de servidores ESXi
*  Apagar componentes
*  Rearrancar servicios

   Las excepciones a estas actividades incluyen la gestión de comparticiones del archivo de almacenamiento compartido desde el {{site.data.keyword.slportal}}. Estas actividades incluyen: solicitar, suprimir (lo que puede afectar los almacenes de datos si están montados), autorizar y montar comparticiones del archivo de almacenamiento compartido.

## Enlaces relacionados
{: #vc_hybrid_orderinginstance-related}

* [Registro de una cuenta de {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-signing_softlayer_account)
* [Visualización de instancias de vCenter Server con el paquete híbrido (Hybridity)](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_viewinginstances)
* [Configuración de varios sitios para instancias de vCenter Server con el paquete híbrido (Hybridity)](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_multisite)
* [Adición y visualización de clústeres correspondientes a instancias de vCenter Server con el paquete híbrido (Hybridity)](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_addingviewingclusters)
* [Ampliación y reducción de la capacidad para instancias de vCenter Server con el paquete híbrido (Hybridity)](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_addingremovingservers)
* [Solicitud, visualización y eliminación de servicios para instancias de vCenter Server con el paquete híbrido (Hybridity)](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_addingremovingservices)
* [Supresión de instancias de vCenter Server con el paquete híbrido (Hybridity)](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_hybrid_deletinginstance)
