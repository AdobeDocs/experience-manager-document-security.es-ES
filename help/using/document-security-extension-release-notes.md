---
title: 'AEM Document Security para Microsoft Office: Notas de la versión'
description: Lea las notas de la versión antes de instalar la extensión de AEM Document Security 6.2 para Microsoft Office.
uuid: f6ab73d4-ac4e-4fff-9bb8-917b75401653
content-type: reference
topic-tags: installing
discoiquuid: c9342c28-8289-4831-a613-4bc03431f557
exl-id: 582f10bb-60d2-46ed-b81d-5818a040edc6
source-git-commit: 3b6a686966fb8d006bed8cc4a4bf5eebe0dfb030
workflow-type: ht
source-wordcount: '1010'
ht-degree: 100%

---

# AEM Document Security para Microsoft Office: Notas de la versión{#aem-document-security-for-microsoft-office-release-notes}

## Novedades de AEM Document Security para Microsoft Office {#whats-new-in-aem-document-security-for-microsoft-office}

* **Apoyo a Office 2019**: La extensión de Document Security para Microsoft Office ahora es compatible con Microsoft Office 2019. También se espera que funcione con las aplicaciones de escritorio de Microsoft Office 2019 instaladas como parte de Office 365.

>[!NOTE]
>
>El documento utiliza los siguientes términos indistintamente:
>
>* Adobe Experience Manager Document Security para Microsoft Office
>* Adobe Experience Manager Document Security Extension para Microsoft Office
>* Document Security Extension para Microsoft Office

## Instalación y configuración de la extensión de AEM Document Security para Microsoft Office {#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

Esta versión de la extensión de Document Security para Microsoft Office es compatible con Adobe LiveCycle Rights Management ES2 y posterior y el complemento Document Security para AEM Forms.

Revise la información de este documento antes de instalar la extensión de AEM Document Security para Microsoft Office. Para obtener instrucciones de instalación detalladas, consulte el artículo [Instalación y configuración de la extensión de AEM Document Security para Microsoft Office](installing-configuring-aemdsext.md).

## Problemas solucionados {#fixed-issues}

* Las cadenas se muestran verticalmente y se añaden saltos de línea incorrectos al contenido. (CQ-4201054)

## Problemas conocidos {#known-issues}

### Los complementos de terceros no son compatibles {#third-party-plug-ins-not-supported}

La extensión de AEM Document Security para Microsoft Office no funciona con complementos de terceros. Desinstale los complementos de terceros para Microsoft Office antes de instalar Document Security Extension para Microsoft Office.

### Opciones de menú desactivadas en Microsoft Word, Excel y PowerPoint {#disabled-menu-options-in-microsoft-word-excel-and-powerpoint}

La extensión de AEM Document Security para Microsoft Office utiliza funciones de protección integradas para proteger documentos, hojas de cálculo y presentaciones. Desactiva algunas opciones de menú de Excel, Word y PowerPoint.

### Restricciones para Microsoft Office 2013, 2016 y 2019 {#restrictions-for-microsoft-office}

En Microsoft Office, las siguientes opciones no están disponibles durante una sesión protegida:

* Microsoft Office 2016 o Microsoft Office 2019

   * Archivo > Guardar como
   * Archivo > Historial
   * Archivo > Compartir
   * Archivo > Exportar
   * Archivo > Publicar
   * Archivo > Cuenta
   * Archivo > Información > Proteger documento/Libro/Presentación > Cifrar con contraseña
   * Archivo > Información > Proteger documento > Añadir una firma digital
   * Archivo > Información > Proteger documento > Marcar como final
   * Opción Compartir en la parte superior derecha

* Microsoft Office 2013

   * Archivo > Guardar como
   * Archivo > Compartir
   * Archivo > Exportar
   * Archivo > Cuenta
   * Archivo > Información > Proteger documento/Libro/Presentación > Cifrar con contraseña
   * Archivo > Información > Proteger documento > Añadir una firma digital
   * Archivo > Información > Proteger documento > Marcar como final

### Abrir un documento protegido desde SharePoint Server {#opening-a-protected-document-from-sharepoint-server}

Para abrir un documento protegido en Document Security Extension para Microsoft Office desde SharePoint Server, abra primero el programa de Microsoft Office asociado (Word, Excel o PowerPoint) o es posible que el documento no se abra. Aparece un mensaje de error que indica que se debe instalar el complemento correspondiente. Por lo tanto, se recomienda abrir el programa de Microsoft Office asociado antes de abrir un documento protegido en la extensión de Document Security para Microsoft Office desde SharePoint Server.

(Opcional) Se recomienda borrar la carpeta de la memoria caché antes de abrir un documento protegido en la extensión de Document Security para Microsoft Office desde SharePoint Server.

Cuando se abre un documento protegido desde SharePoint Server, todos los permisos del documento se desactivan, independientemente de la directiva que se haya aplicado.

### Aplicar una directiva con una marca de agua dinámica al archivo de Microsoft Excel 2013, Microsoft Excel 2016 y Microsoft Excel 2019 sin ninguna impresora instalada {#apply-a-policy-with-a-dynamic-watermark-to-microsoft-excel-microsoft-excel-and-microsoft-excel-file-with-no-printer-installed}

La aplicación de una directiva con marca de agua dinámica a los archivos de Excel 2013, 2016 o 2019 en un equipo sin impresoras instaladas provoca el siguiente error: &quot;Error interno al aplicar marca de agua dinámica&quot;. Este error también aparece cuando vuelve a abrir el archivo protegido. La marca de agua no se aplica y no está visible desde Vista > Diseño de página.

### Deshabilitar la prevención de ejecución de datos de Windows para aplicaciones de Office admitidas {#disable-windows-data-execution-prevention-for-supported-office-applications}

Se recomienda desactivar la configuración de Windows Data Execution Prevention (DEP) al usar la extensión de Document Security para Microsoft Office.

### Los archivos compartidos de Microsoft Office no se pueden proteger con la extensión de Document Security {#shared-microsoft-office-files-cannot-be-protected-using-document-security-extension}

Al proteger cualquier archivo compartido de Microsoft Office mediante la extensión de Document Security, se produce un error y el archivo compartido no está protegido.

### Inicio de aplicaciones de Office en un equipo que contiene la extensión de Document Security para Microsoft Office y McAfee VirusScan {#starting-office-applications-on-a-machine-containing-document-security-extension-for-microsoft-office-and-mcafee-virusscan}

Para garantizar que las aplicaciones de Office se inicien sin problemas en un equipo que tenga instalado Document Security y McAfee VirusScan (análisis en tiempo real activado), desactive la opción de protección contra desbordamiento del búfer en la consola de McAfee VirusScan.

### Instalación de la extensión de Document Security para Microsoft Office en un equipo con un idioma no admitido de Microsoft Office {#installing-document-security-extension-for-microsoft-office-on-a-machine-with-an-unsupported-microsoft-office-language}

Antes de instalar la extensión de Document Security para Microsoft Office en un equipo que tenga una aplicación de Microsoft Office con un idioma no admitido, abra la aplicación de Office al menos una vez.

### El botón Sincronizar sin conexión está habilitado incluso cuando un usuario no tiene permisos sin conexión {#synchronize-offline-button-is-enabled-even-when-a-user-does-not-have-offline-permissions}

El botón Sincronizar sin conexión está disponible aunque el usuario no tenga permisos sin conexión para el documento. Sin embargo, seleccionar el botón no hace nada.

### No es compatible con versiones de prueba de Microsoft Office {#no-support-for-trial-versions-of-microsoft-office}

Document Security Extension para Microsoft Office no es compatible con las versiones de prueba de Microsoft Office. Antes de instalar la extensión, asegúrese de que ha instalado una copia con licencia de Microsoft Office y que está activada.

### No se puede abrir un archivo protegido de Microsoft Office {#unable-to-open-a-protected-microsoft-office-files}

Si la vista protegida de Microsoft Office está habilitada, la extensión de Right Management no puede abrir archivos protegidos de Microsoft Excel (XLS, XLSX) ni archivos protegidos de Microsoft PowerPoint (PPT) desde una ubicación remota.

### Las celdas del documento de Microsoft Excel que contienen una imagen o un color de fondo aparecen encima de la marca de agua {#cells-of-microsoft-excel-document-containing-an-image-or-background-color-appear-on-top-of-watermark}

Si una celda de un documento de Excel tiene una imagen o un color de fondo y se aplica una marca de agua dinámica, la imagen o el color cubre la marca de agua. Este enfoque significa que la marca de agua está cubierta por la imagen o el color de fondo de la celda.

### Problema de uso con varios certificados {#usability-issue-with-multiple-certificates}

Si hay varios certificados en el equipo cliente y el usuario cancela el cuadro de diálogo de selección de certificado, el cuadro de diálogo vuelve a aparecer. El usuario tiene que cancelar el cuadro de diálogo dos veces.

### Microsoft PowerPoint permite editar documentos protegidos {#microsoft-powerpoint-allows-editing-protected-documents}

Al intentar editar un documento protegido, Microsoft PowerPoint muestra un mensaje: “No puede modificar este documento. No puede guardar los cambios&quot;. Después de cerrar el mensaje, los usuarios pueden seguir agregando texto o editando el documento. Sin embargo, los cambios realizados en los documentos protegidos no se guardan.

El comportamiento mencionado es el esperado en PowerPoint 2013, PowerPoint 2016 y PowerPoint 2019.
