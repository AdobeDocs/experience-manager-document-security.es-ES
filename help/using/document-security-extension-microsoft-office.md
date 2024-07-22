---
title: Introducción a la extensión Document Security de AEM para Microsoft® Office
description: Con la extensión de Document Security para Microsoft&reg; Office, puede aplicar parámetros de confidencialidad predefinidos a sus archivos de Microsoft&reg; Office.
uuid: a5428c50-fae3-4823-9e6f-0f5306e7248f
content-type: reference
topic-tags: using
discoiquuid: cf93f9f5-1fb6-4909-815e-0ffb8c6ea6d1
exl-id: 3e07c031-3f88-4bde-bdb3-b136ef5f9527
source-git-commit: 3b6a686966fb8d006bed8cc4a4bf5eebe0dfb030
workflow-type: tm+mt
source-wordcount: '1248'
ht-degree: 68%

---

# Introducción a la extensión Document Security de AEM para Microsoft® Office{#introduction-to-aem-document-security-extension-for-microsoft-office}

La extensión Document Security de Adobe® Experience Manager para Microsoft® Office garantiza que solo las personas autorizadas por usted puedan utilizar archivos de Word, Excel y PowerPoint que contengan su propiedad intelectual. Con la extensión de Document Security para Microsoft® Office, puede aplicar una configuración de confidencialidad predefinida a sus archivos.

La extensión de Document Security para Microsoft® Office mejora LiveCycle Rights Management y Document Security para Adobe Experience Manager Forms. Protege los archivos de Office y permite a los usuarios autorizados acceder a los archivos protegidos por directivas según la configuración de confidencialidad establecida.

## Document Security y la protección de la propiedad intelectual {#how-document-security-protects-intellectual-property}

Document Security garantiza que solo las personas autorizadas por usted puedan utilizar archivos que contengan su propiedad intelectual. Con Document Security, puede proteger archivos mediante directivas de confidencialidad. Una *directiva* es una recopilación de información que incluye parámetros de confidencialidad y una lista de usuarios autorizados. La configuración especificada en una directiva determina cómo puede un destinatario utilizar un archivo al que se aplica la directiva. Por ejemplo, puede especificar si los destinatarios pueden imprimir o copiar texto o guardar cambios.

Los administradores y usuarios de Document Security crean directivas. Los administradores crean directivas organizativas que están disponibles para todos los usuarios autorizados. Los administradores o coordinadores de conjuntos de directivas también pueden crear grupos de directivas llamados *conjuntos de directivas* que están disponibles para un subconjunto de usuarios. Los usuarios pueden crear sus propias directivas, que solo ellos pueden utilizar. Los administradores, coordinadores de conjuntos de directivas y usuarios crean directivas mediante las páginas web de Document Security.

Aunque las directivas se almacenan en Document Security, puede aplicarlas a los archivos a través de Word, Excel o PowerPoint. Cuando se aplica una directiva a un archivo, la información que contiene el archivo está protegida por la configuración de confidencialidad especificada en la directiva. Al distribuir el archivo protegido por una directiva, solo los destinatarios autorizados pueden acceder a su contenido.

El uso de una directiva para proteger un archivo le proporciona un control continuo sobre dicho archivo, incluso después de distribuirlo. Puede auditar eventos para rastrear cuándo y cómo utilizan el archivo los destinatarios. También puede realizar cambios en la directiva, impedir que los usuarios sigan teniendo acceso al archivo y cambiar la directiva adjunta al archivo.

## Funcionamiento de las directivas {#how-policies-work}

Las directivas contienen información sobre los usuarios autorizados y los parámetros de confidencialidad que deben aplicarse a la propiedad intelectual. Document Security reconoce a los usuarios incluidos en un LDAP vinculado o en una lista de Active Directory. Los usuarios también pueden ser personas invitadas a registrarse en Document Security o para las que el administrador haya creado una cuenta.

La configuración de confidencialidad de una directiva determina cómo pueden utilizar los destinatarios los archivos protegidos por la directiva. Por ejemplo, las directivas especifican si los destinatarios pueden imprimir archivos, copiar contenido en otros archivos o guardar cambios en archivos protegidos. Las directivas también pueden especificar diferentes parámetros de confidencialidad para distintos usuarios.

Cuando se aplica una directiva a un archivo, la información que contiene el archivo está protegida por la configuración de confidencialidad especificada en la directiva. Al distribuir el archivo, Document Security autentica los destinatarios que intentan abrir el archivo y autoriza el acceso según los privilegios especificados en la directiva.

Después de aplicar una directiva a un archivo, la configuración de confidencialidad de esta se puede cambiar en cualquier momento. Puede agregar o quitar usuarios autorizados o cambiar los privilegios de los usuarios después de que hayan recibido el archivo. La directiva aplicada al archivo se puede cambiar. Además, el acceso al archivo se puede revocar para que cualquier persona que tenga una copia del archivo ya no pueda abrirlo.

Si la directiva permite el acceso sin conexión, los destinatarios también pueden utilizar archivos protegidos por directivas sin conexión (sin una conexión activa a Internet o a la red) durante el período de tiempo especificado en la directiva.

## Funcionamiento de los archivos protegidos por directivas {#how-policy-protected-files-work}

Para que un usuario pueda abrir y utilizar archivos de Word, Excel y PowerPoint protegidos por directivas, la directiva debe incluir al usuario como destinatario. O bien, debe permitir el acceso anónimo. El usuario debe tener instalada la extensión de Document Security para Microsoft® Office. Para proporcionar un archivo protegido por una directiva a una persona que no tenga la extensión de Document Security para Microsoft® Office, puede proporcionarle una copia del software. O bien, puede indicarles cómo descargarlo desde su sitio web. Si no tiene el programa de instalación, puede descargarlo desde la [página de descargas](https://experienceleague.adobe.com/en/docs/experience-manager-document-security/using/download-installer).

Cuando un usuario intenta abrir un archivo protegido por una directiva, la extensión de Document Security para Microsoft® Office se conecta a Document Security para autenticar al usuario. Si Document Security está configurado para auditar el uso de archivos, el usuario verá una notificación que indica que se está auditando el uso del archivo. Document Security determina qué permisos de archivo se concederán al usuario y el usuario podrá usar el archivo según la configuración de la directiva, bajo estas condiciones:

* Para el período de validez especificado en la directiva.
* Hasta que un administrador o la persona que aplicó la directiva anulen el acceso al archivo o cambien la directiva.

  Si la persona que aplicó la directiva la cambia o anula el acceso al archivo, los permisos del usuario cambian o se eliminan aunque el usuario ya tenga el archivo. Si se revoca el archivo, se puede proporcionar una URL para que el usuario obtenga una copia actualizada.

  Si la directiva permite el acceso sin conexión, los usuarios pueden abrir archivos protegidos por directivas sin conexión a Internet o a la red durante el período de concesión sin conexión especificado. Cuando finaliza el período de concesión sin conexión, el usuario debe conectarse y sincronizar con Document Security, que inicio un nuevo período de concesión.

  Si la directiva permite el acceso sin conexión, los usuarios pueden abrir archivos protegidos por directivas sin conexión a Internet o a la red durante el período de concesión sin conexión especificado. Los eventos, como los intentos de abrir el nuevo archivo, también se auditan y registran del mismo modo que en el archivo original.

## Uso de Document Security para proteger los archivos {#using-document-security-to-protect-your-files}

Puede utilizar directivas para proteger los archivos en diversas situaciones.

Por ejemplo, un fabricante acepta ofertas de proveedores que proporcionarán piezas para un nuevo producto. El fabricante deberá facilitar a los licitadores la información de propiedad que necesiten para finalizar sus envíos. El fabricante utiliza Document Security para proteger los archivos con una directiva que permite a los proveedores abrir los archivos y ver la información. Sin embargo, se impide a los proveedores cambiar, imprimir o copiar los archivos, y a cualquier persona que no tenga permiso se le impide abrir los archivos.

Después de aceptar una oferta, el fabricante actualiza la directiva para conceder al proveedor seleccionado permisos para imprimir, copiar y guardar cambios localmente. El fabricante también elimina los proveedores no seleccionados, revocando su permiso para abrir los archivos.

Mientras trabajan con el licitador final, los ingenieros del fabricante cambian algunas de las especificaciones de diseño de los archivos. Para publicar las nuevas especificaciones, el fabricante anula el acceso a algunos de los archivos y publica nuevas versiones. Cuando los ingenieros del proveedor seleccionado intentan abrir el archivo, ven un mensaje que indica que se ha revocado el acceso al archivo. El mensaje contiene una dirección URL donde pueden descargar una nueva versión del archivo.

## Información adicional {#additional-information}

Los recursos de esta tabla pueden ayudarle a obtener más información sobre AEM Document Security:

<table >
 <tbody>
  <tr>
   <th><p>Para obtener información acerca de</p> </th>
   <th><p>Consulte</p> </th>
  </tr>
  <tr>
   <td><p>Ayuda para el administrador de AEM Forms</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/forms/administrator-help/get-started/configure-general-aem-forms-settings">Ayuda para el administrador </a>o, en las páginas de administración de Document Security, haga clic en el vínculo Ayuda en la esquina superior derecha de una página.</p> </td>
  </tr>
  <tr>
   <td><p>Actualizaciones de parches, notas técnicas e información adicional sobre esta versión del producto</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/?support-solution=General&amp;support-tab=home&amp;lang=es#support">Soporte técnico de Experience Cloud</a></p> </td>
  </tr>
 </tbody>
</table>
