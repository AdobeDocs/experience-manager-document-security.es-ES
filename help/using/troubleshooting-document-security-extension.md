---
title: Solución de problemas de la extensión de AEM Document Security para Microsoft Office
description: Si tiene problemas para instalar, configurar o utilizar la extensión de AEM Document Security para Microsoft Office, siga las instrucciones que se indican en este documento.
uuid: 61001ca8-a25a-4879-98ac-563a6eb126e7
contentOwner: khsingh
content-type: reference
topic-tags: using
discoiquuid: bdc3f174-e417-4d3e-b3af-972cdcc10133
exl-id: 98f24032-0774-47f8-bcc5-1ee37b417833
source-git-commit: 28137f26afc024d411857d44887bf69fe1ee2b81
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 100%

---

# Solución de problemas de la extensión de AEM Document Security para Microsoft Office{#troubleshooting-aem-document-security-extension-for-microsoft-office}

## Solución de problemas de instalación y configuración {#troubleshootinginstallationandconfiguration}

Si tiene problemas para instalar y configurar la extensión de AEM Document Security para Microsoft Office, asegúrese de seguir cuidadosamente las instrucciones que se indican en la sección “Antes de instalar” del artículo [Instalación](installing-configuring-aemdsext.md).

Si ha instalado y configurado todo según la documentación, consulte las siguientes secciones para ver si hay problemas similares a los que está experimentando.

### La extensión de Document Security no se puede cargar para aplicaciones de Microsoft Office {#document-security-extension-fails-to-load-for-microsoft-office-applications}

La propiedad LoadBehavior del Registro de Windows especifica el comportamiento de tiempo de ejecución del complemento de Document Security. Si la propiedad LoadBehavior está establecida en 3, todos los complementos se cargan automáticamente. Antes de instalar la extensión de Document Security para Microsoft Office, asegúrese de que el valor de la propiedad LoadBehavior está establecido en 3.

1. Realice una copia de seguridad del Registro de Windows antes de realizar cambios en él. Para obtener instrucciones detalladas, consulte [Modificar el Registro de Windows](https://support.microsoft.com/es-es/kb/136393).
1. En el Editor del Registro, vaya a HKEY_CURRENT_USER\Software\Microsoft\Office\Word\Addins\Adobe.DRMIntegration.WordAddin o HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Word\Addins\Adobe.DRM.
1. Establezca el valor de la propiedad **LoadBehavior** en 3.

1. Cierre el Editor del Registro.

Para obtener información detallada sobre LoadBehavior, consulte el artículo [Entradas del Registro para complementos de VSTO](https://msdn.microsoft.com/es-es/library/bb386106.aspx#LoadBehavior).

## Solución de problemas de tareas administrativas {#admintasks}

En esta sección se analizan los posibles problemas con la extensión de AEM Document Security instalada.

### Las aplicaciones de Microsoft Office no se inician correctamente al instalar la extensión de Document Security {#microsoft-office-applications-dont-start-smoothly-on-installing-document-security-extension}

Para garantizar que las aplicaciones de Office se inicien sin problemas en un equipo que tenga instalado la extensión de Document Security y McAfee VirusScan con la opción de protección de acceso activada, desactive la opción protección contra desbordamientos de búfer en la consola de McAfee VirusScan.
