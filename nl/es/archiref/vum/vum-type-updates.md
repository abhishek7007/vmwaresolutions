---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-25"

subcollection: vmware-solutions


---

# Tipos de actualizaciones de software VMware
{: #vum-type-updates}

VMware utiliza los términos siguientes para describir actualizaciones de software.

Tabla 1. Términos y definiciones de la actualización de VMware

| Término | Definición |
|:------- |:----------- |
| Boletín |	Una agrupación de uno o más VIB. Los boletines se definen en los metadatos. |
| Depósito |	Una agrupación lógica de VIB y los metadatos asociados que se publican en línea |
| Imagen de actualización de host |	Una imagen ESXi que puede importar en el repositorio de Update Manager y utilizar para actualizar hosts ESXi 5.5 o ESXi 6.0 a ESXi 6.5. |
| Ampliación | 	Un boletín que define un grupo de VIB para añadir un componente opcional a un host ESXi. Normalmente es el tercero responsable de los parches o actualizaciones de la extensión el que proporciona una extensión. |
| Metadatos |	Datos adicionales que definen la información de dependencias, las descripciones textuales, los requisitos del sistema y los boletines. |
| Archivo comprimido de paquete fuera de línea |	Un archivo que encapsula VIB y los metadatos correspondientes en un paquete autocontenido útil para la aplicación de parches fuera de línea. No se pueden utilizar paquetes fuera de línea de terceros o paquetes fuera de línea generados a partir de conjuntos VIB personalizados para actualizar hosts de ESXi 5.5 o ESXi 6.0 a ESXi 6.5. |
| Parche |	Un boletín que agrupa una o varias VIB juntas para solucionar un problema concreto o una mejora. |
| Acumular |	Una colección de parches que se agrupa para facilitar la descarga y el despliegue. |
| Actualización de VA |	Actualizaciones para un dispositivo virtual, que el proveedor considera una actualización. |
| VIB |	Un VIB es un único paquete de software. |

## Enlaces relacionados
{: #vum-type-updates-related}

* [Arquitectura de la solución VMware HCX on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcx-archi-intro#hcx-archi-intro)
* [VMware Solutions on {{site.data.keyword.cloud_notm}} Digital Technical Engagement](https://ibm-dte.mybluemix.net/vmware) (demostraciones)
