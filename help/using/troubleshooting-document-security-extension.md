---
title: Solución de problemas de la extensión de AEM Document Security para Microsoft Office
description: Si tiene problemas para instalar, configurar o utilizar la extensión de AEM Document Security para Microsoft Office, siga las instrucciones que se indican en este documento.
uuid: 61001ca8-a25a-4879-98ac-563a6eb126e7
contentOwner: khsingh
content-type: reference
topic-tags: using
discoiquuid: bdc3f174-e417-4d3e-b3af-972cdcc10133
exl-id: 98f24032-0774-47f8-bcc5-1ee37b417833
TQID: https://experienceleague.adobe.com/3YVMcSeYDXCWkVeG8HmlJOgja9OwLqs1gpPWP8rhhs0
product_v2:
  - id: e8f6de9b-cf88-4405-8d10-15efa08c230e
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: fd5d26fd-7180-407d-bbd8-5f8a17f9c0b8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: b2df949228acdc23ca7f2c55b72e62c1dba130b8
workflow-type: tm+mt
source-wordcount: 316
ht-degree: 100%

---

# Solución de problemas de la extensión de AEM Document Security para Microsoft Office{#troubleshooting-aem-document-security-extension-for-microsoft-office}

## Solución de problemas de instalación y configuración {#troubleshootinginstallationandconfiguration}

Si tiene problemas para instalar y configurar AEM Document Security Extension para Microsoft Office, asegúrese de seguir cuidadosamente las instrucciones que se indican en la sección “Antes de realizar la instalación” del artículo de [instalación](installing-configuring-aemdsext.md).

Si ha instalado y configurado todo según la documentación, consulte las siguientes secciones para ver si hay problemas similares a los que está experimentando.

### La extensión de Document Security no se puede cargar para aplicaciones de Microsoft Office {#document-security-extension-fails-to-load-for-microsoft-office-applications}

La propiedad LoadBehavior del Registro de Windows especifica el comportamiento de tiempo de ejecución del complemento de seguridad del documento. Si la propiedad LoadBehavior está establecida en 3, todos los complementos se cargan automáticamente. Antes de instalar Document Security Extension para Microsoft Office, asegúrese de que el valor de la propiedad LoadBehavior está establecido en 3.

1. Realice una copia de seguridad del Registro de Windows antes de realizar cambios en él. Para obtener instrucciones detalladas, consulte [Modificar el Registro de Windows](https://learn.microsoft.com/es-es/troubleshoot/windows-server/performance/windows-registry-advanced-users).
1. En el Editor del Registro, vaya a HKEY_CURRENT_USER\Software\Microsoft\Office\Word\Addins\Adobe.DRMIntegration.WordAddin o HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Word\Addins\Adobe.DRM.
1. Establezca el valor de la propiedad **LoadBehavior** en 3.

1. Cierre el Editor del registro.

Para obtener información detallada sobre LoadBehavior, consulte el artículo [Entradas del Registro para complementos de VSTO](https://learn.microsoft.com/es-es/visualstudio/vsto/registry-entries-for-vsto-add-ins?view=vs-2022&redirectedfrom=MSDN#LoadBehavior).

## Solución de problemas de tareas administrativas {#admintasks}

En esta sección se analizan los posibles problemas con la extensión de AEM Document Security instalada.

### Las aplicaciones de Microsoft Office no se inician correctamente al instalar la extensión de Document Security {#microsoft-office-applications-dont-start-smoothly-on-installing-document-security-extension}

Para garantizar que las aplicaciones de Office se inicien sin problemas en un equipo que tenga instalado Document Security Extension y McAfee VirusScan con la opción de análisis en tiempo real habilitada, deshabilite la opción de protección contra desbordamiento del búfer en la consola de McAfee VirusScan.
