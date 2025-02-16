---

copyright:

  years:  2016, 2019

lastupdated: "2019-03-06"

subcollection: vmwaresolutions


---

# Solicitud, visualización y eliminación de servicios para instancias de Cloud Foundation
{: #sd_addingremovingservices}

Puede solicitar servicios para instancias de VMware Cloud Foundation, como una solución de recuperación tras desastre. Cuando ya no necesite estos servicios, puede eliminarlos de sus instancias.

## Servicios disponibles para las instancias de Cloud Foundation
{: #sd_addingremovingservices-available-services}

En la tabla siguiente se muestran los servicios que están disponibles para instancias de Cloud Foundation, junto con las versiones instaladas del servicio.

Tabla 1. Servicios disponibles para las instancias de Cloud Foundation

| Nombre de servicio | Versión de servicio actual | Versión de instancia |
|----------------------------------------------------------------------------------------|------------------|
| [F5 on {{site.data.keyword.cloud}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-f5_considerations) | BIG-IP VE v14.1.0.2 | V1.9 y posterior |
| [FortiGate Security Appliance on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-fsa_considerations)       | serie 300 | V1.8 y posterior |
| [FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-fortinetvm_considerations) | 6.0.3 | V2.0 y posterior |
| [HyTrust CloudControl on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-htcc_considerations)              | 5.4.2 | V2.3 y posterior |
| [HyTrust DataControl on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-htdc_considerations)              | 4.2.1 | V2.3 y posterior |
| [HyTrust KeyControl on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-htkc_considerations) | 4.2 | V2.5 y posterior |
| [IBM Spectrum Protect&trade; Plus on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-spp_considerations)  | 10.1.2 | V2.2 y posterior |
| [KMIP for VMware on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-kmip_standalone_considerations) |  2.0 | N/D |
| [Veeam on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-veeam_considerations) | 9.5u4 | V1.8 y posterior |
| [Zerto on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-addingzertodr) | 6.5 actualización 3 | V1.2 y posterior |

## Procedimiento para añadir servicios a instancias de Cloud Foundation
{: #sd_addingremovingservices-adding-procedure}

Para añadir un servicio a la instancia de Cloud Foundation, pulse el enlace de servicio adecuado en la tabla anterior para revisar las consideraciones para el servicio y comprobar los componentes que se despliegan. A continuación, siga las instrucciones del tema de servicios de ordenación adecuados para añadir el servicio a la instancia.

### Resultados de la instalación de un servicio
{: #sd_addingremovingservices-adding-results}

Cuando la instalación del servicio finalice correctamente, recibirá una notificación por correo electrónico y el servicio se mostrará en la página **Servicios** de la instancia con el estado **Instalado**.

## Procedimiento para visualizar servicios para instancias de Cloud Foundation
{: #sd_addingremovingservices-viewing-procedure}

1. En la consola de {{site.data.keyword.vmwaresolutions_short}}, pulse **Recursos** en el panel de navegación izquierdo.
2. En la tabla **Instancias de Cloud Foundation**, pulse la instancia para la que desea ver los servicios.
3. Pulse **Servicios** en el panel de navegación izquierdo.
4. En la página **Servicios**, pulse un servicio para revisar información sobre el mismo, como por ejemplo el estado del servicio y otros detalles.
5. Dependiendo del servicio visualizado, puede acceder a las consolas de servicio utilizando las credenciales proporcionadas en los detalles del servicio y puede gestionar el servicio desde aquí.

## Procedimiento para eliminar servicios para instancias de Cloud Foundation
{: #sd_addingremovingservices-removing-procedure}

1. En la consola de {{site.data.keyword.vmwaresolutions_short}}, pulse **Recursos** en el panel de navegación izquierdo.
2. En la tabla **Instancias de Cloud Foundation**, pulse la instancia para la que desea eliminar servicios.
3. Pulse **Servicios** en el panel de navegación izquierdo.
4. En la página **Servicios**, localice la instancia de servicio que desea suprimir y pulse el icono **Suprimir**.
5. En la ventana **Suprimir servicio**, revise las consideraciones o los avisos, si los hay. Seleccione **Lo entiendo** y pulse **Suprimir**.

### Resultados de la eliminación de un servicio
{: #sd_addingremovingservices-removing-results}

Una vez aceptada su solicitud de eliminación del servicio, el estado del servicio pasa a ser **Eliminando**.

Cuando la eliminación del servicio finalice correctamente, recibirá una notificación por correo electrónico y el servicio se eliminará de la página **Servicios** de la instancia.

Se le facturará por los servicios eliminados hasta el final del ciclo de facturación de {{site.data.keyword.cloud_notm}}.
{:note}

## Enlaces relacionados
{: #sd_addingremovingservices-related}

* [Preguntas frecuentes](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-faq)
