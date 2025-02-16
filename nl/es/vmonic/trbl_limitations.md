---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-12"

subcollection: vmware-solutions


---

{:faq: data-hd-content-type='faq'}

# Más limitaciones y consideraciones
{: #trbl_limitations}

Revise las siguientes consideraciones y limitaciones cuando trabaje con {{site.data.keyword.vmwaresolutions_full}}.

## Instalación automática de actualizaciones de Windows
{: #trbl_limitations-windows-update}
{: faq}

Microsoft Active Directory (AD) / Domain Name Server (DNS) está configurado automáticamente para que sólo se descarguen las actualizaciones. No instala estas actualizaciones ni se reinicia automáticamente. Debe instalar manualmente las actualizaciones y reiniciar en un momento planificado que evite cualquier interrupción de la configuración actual del servidor AD y de otros trabajos de copia de seguridad. Para aplicar las actualizaciones de Windows, instale las actualizaciones manualmente.
