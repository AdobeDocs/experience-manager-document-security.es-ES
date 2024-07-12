---
title: Uso de la extensión Document Security de AEM para Microsoft® Office
description: Puede controlar el uso que hacen los destinatarios de los archivos protegidos mediante directivas, independientemente de la amplitud de su distribución. El documento explica cómo proteger archivos y cómo trabajar con archivos protegidos.
uuid: db4abbc8-eb21-4f4a-9950-224ada95ce66
content-type: reference
topic-tags: using
discoiquuid: f4c2460c-174f-4e4d-b804-1eb051d2781e
exl-id: 667a9718-b865-4911-96c2-7c08f75e0732
source-git-commit: 28137f26afc024d411857d44887bf69fe1ee2b81
workflow-type: tm+mt
source-wordcount: '6242'
ht-degree: 100%

---

# Uso de la extensión Document Security de AEM para Microsoft® Office{#using-aem-document-security-extension-for-microsoft-office}

## Proteger archivos con la extensión de AEM Document Security {#usingaemdocumentsecurityextensiontoprotectfiles}

Puede controlar el uso que hacen los destinatarios de los archivos protegidos mediante directivas, independientemente de la amplitud de su distribución.

Con la extensión de Document Security para Microsoft® Office, puede realizar estas tareas:

* Configurar la conexión a Document Security
* Aplicar una directiva a un archivo
* Abrir las páginas web de Document Security para crear y administrar directivas de usuario
* Eliminar la protección de una directiva de un archivo
* Cambiar la directiva aplicada a un archivo
* Abra las páginas web de Document Security para anular el acceso a los archivos o cambiar la directiva del archivo
* Abrir las páginas web de Document Security para ver el historial de auditoría del archivo

### Conectar con un servidor de Document Security {#connect-to-a-document-security-server}

Si desea aplicar directivas a los archivos, debe configurar los parámetros de conexión de Document Security. Según la instalación de la extensión de Document Security para Microsoft® Office, es posible que ya tenga la configuración de conexión predeterminada. Puede agregar la configuración de conexión para una o varias instancias de Document Security. Puede obtener información del servidor del administrador de Document Security.

Configure el servidor que desea utilizar para proteger archivos o administrar los archivos protegidos como servidor predeterminado. Al aplicar una política a un archivo nuevo o abrir las páginas web de Document Security, la extensión de Document Security para Microsoft® Office se conecta al servidor predeterminado. Si protege los archivos con más de una instancia de Document Security, debe cambiar la configuración predeterminada del servidor al cambiar entre servidores. Puede abrir archivos protegidos por cualquier instancia de Document Security siempre y cuando tenga autorización para abrir el archivo.

Si el servidor de Document Security utiliza la autenticación basada en certificados, deberá instalar el certificado que recibió en el equipo local. Se le solicitará que elija la autenticación de certificado y proporcione el certificado que desea utilizar para la autenticación.

Después de configurar los ajustes de conexión para una instancia de Document Security en una aplicación de Microsoft® Office, se configura para todos los formatos de Word, Excel y PowerPoint.

#### Instalar el certificado del lado del cliente {#install-the-client-side-certificate}

Si necesita acceder a las páginas web de Document Security mediante autenticación mediante certificado o autenticación bidireccional, recibirá el certificado que debe instalar en su equipo local. Recibirá un archivo de certificado (archivo .PFX o .P12) y su contraseña.

1. Guarde el archivo de certificado en el equipo local.
1. Haga doble clic en el archivo de certificado para abrir el Asistente de importación de certificado y haga clic en **Siguiente**.
1. Haga clic en **Siguiente** si el archivo de certificado aparece enumerado en el cuadro de nombre de archivo. Haga clic en **Examinar** si desea encontrar otro certificado.
1. Introduzca la contraseña que ha recibido y haga clic en **Siguiente**.
1. En el cuadro de diálogo Almacén de certificados, seleccione Colocar todos los certificados en el siguiente almacén y haga clic en **Examinar**.
1. En el cuadro de diálogo Seleccionar almacén de certificados, seleccione Personal, haga clic en **Aceptar**, haga clic en **Siguiente** y, a continuación, haga clic en **Finalizar**.

#### Establecer la configuración de conexión {#configure-connection-settings}

1. En la extensión de Document Security para Microsoft® Office 2010 y Office 2013, en la pestaña **Document Security**, seleccione **Elegir servidor**.
1. Haga clic en **Nuevo** para crear una nueva configuración de conexión o seleccione una conexión existente y haga clic en **Editar**.
1. Escriba un nombre para la conexión en el cuadro **Nombre**. Puede usar cualquier nombre.
1. Escriba la dirección del servidor en el cuadro **Dirección del servidor**.
1. Escriba el puerto del servidor en el cuadro **Puerto**.
1. (Opcional) Si desea recordar su nombre de usuario y contraseña, seleccione **Recordar contraseña en este equipo** y escriba su nombre de usuario y contraseña en los cuadros correspondientes. Se recomienda no seleccionar esta opción si otras personas pueden tener acceso al equipo.
1. Haga clic en **Conectar a este servidor**. La extensión de Document Security para Microsoft® Office intenta conectarse al servidor especificado. Según el tipo de autenticación especificado, realice una de las siguientes acciones:

   **Nombre de usuario y contraseña**

   Introduzca el nombre de usuario y la contraseña que ha recibido del administrador de Document Security.

   **Autenticación de certificado**

   Elija esta opción para seleccionar el certificado que recibió e instaló en su almacén de certificados personal.

   Si solo se configura un tipo de autenticación en Document Security, solo aparecerá esa opción.

>[!NOTE]
>
>Si no puede conectar con el servidor, intente abrir las páginas web de Document Security en Internet Explorer. Si no puede conectar con el servidor mediante Internet Explorer o si aparece un cuadro de diálogo con una advertencia sobre el certificado del servidor, la extensión de Document Security para Microsoft® Office no podrá conectarse al servidor. Póngase en contacto con el administrador del servidor para obtener ayuda.

>[!NOTE]
>
>Si no puede conectarse a Document Security, aparece un mensaje que indica que “El nombre de usuario y la contraseña son incorrectos, compruebe los ajustes de la configuración e inténtelo de nuevo”. Este mensaje puede aparecer si no se puede conectar por otro motivo. Si se está conectando al servidor por primera vez, compruebe que ha establecido correctamente el nombre y el puerto del servidor.

#### Especificar servidor predeterminado {#specify-the-default-server}

1. Haga lo siguiente:

   * En la extensión de Document Security para Microsoft® Office 2010 y Office 2013, en la pestaña **Document Security**, seleccione **Elegir servidor**.

1. Seleccione un servidor para especificarlo como predeterminado y haga clic en **Establecer predeterminado**. Aparece una estrella junto al servidor predeterminado.

### Uso de proveedores de autenticación de terceros {#using-third-party-authentication-providers}

Puede utilizar proveedores de autenticación de terceros con AEM Forms Document Security. Estos proveedores de autenticación le ayudan a agregar una capa de acceso adicional a los documentos protegidos. AEM Forms Document Security admite los siguientes flujos de trabajo de autenticación extendida:

* Autenticación extendida mediante la URL de AEM Forms predeterminada
* Autenticación extendida mediante una dirección URL personalizada
* Flujo de trabajo de autenticación extendida predeterminado con proveedores de identidad de terceros configurados en AEM Forms en el servidor JEE
* Flujo de trabajo de autenticación extendida personalizado con proveedores de identidad de terceros configurados en AEM Forms en el servidor JEE
* Autenticación extendida mediante una página personalizada para enumerar autenticaciones SAML

#### Autenticación extendida mediante la URL de AEM Forms predeterminada {#extended-authentication-using-default-aem-forms-url}

Puede utilizar la URL de AEM Forms predeterminada para la autenticación extendida. La página de aterrizaje predeterminada contiene la marca de Adobe. Además, la configuración predeterminada de AEM Forms se usa al utilizar la dirección URL predeterminada de AEM Forms para la autenticación extendida.

Realice los siguientes pasos para habilitar la autenticación extendida con la dirección URL de aterrizaje de Adobe predeterminada:

1. Abra la interfaz de usuario del administrador de AEM Forms.
1. Vaya a Servicios > Document Security > Configuración > Configuración del servidor.
1. Active la opción Permitir autenticación extendida.
1. Especifique la URL predeterminada de aterrizaje de autenticación extendida de la dirección URL. La dirección URL predeterminada es http://localhost:8080/edc/extendedauthentication/welcome.jsp.

   Haga clic en **[!UICONTROL Guardar]**.

   >[!NOTE]
   >
   >Utilice un nombre de host completo en la dirección URL. Se recomienda utilizar el protocolo HTTPS.

   Ahora, AEM Forms Document Security está configurada para utilizar la autenticación extendida con la dirección URL de aterrizaje de AEM Forms predeterminada.

   ![](assets/third-party-authentication.png)

#### Autenticación extendida con una dirección URL de aterrizaje personalizada {#extended-authentication-with-a-custom-landing-url}

Puede utilizar una dirección URL personalizada para la autenticación extendida. Proporciona la flexibilidad de mostrar una página de autenticación personalizada con marca personalizada. Por ejemplo, la marca de su organización.

Puede empaquetar la página de autenticación personalizada en un archivo war e implementarlo en el servidor de AEM Forms. El archivo war contiene una lógica completa para aceptar las credenciales de usuario y autenticarse con el servidor de AEM Forms. AEM Forms Document Security tiene los siguientes requisitos para la página de autenticación personalizada:

* La página de autenticación debe enviar el nombre de usuario como j_username y la contraseña como j_password. La página también debe enviar source_url y login_url como parámetros ocultos.
* Si la autenticación se realiza correctamente, la página debe cerrarse automáticamente.

Para habilitar una autenticación extendida con una dirección URL de aterrizaje personalizada:

1. Implemente el archivo war de autenticación personalizada en el servidor de AEM Forms.
1. Abra la interfaz de usuario del administrador de AEM Forms.
1. Vaya a Servicios > Document Security > Configuración > Configuración del servidor.
1. Active la opción Permitir autenticación extendida y especifique la URL de aterrizaje de autenticación extendida personalizada.
1. Añada las siguientes entradas al archivo config.xml en el nodo SSO después de la entrada *&lt;node name=&quot;AllowedUrls&quot;>*:

   >[!NOTE]
   >
   >&lt;entry key=&quot;sso-l&quot; value=&quot;/ sample_/login.jsp&quot;/>!!discoiqbr!!&lt;entry key=&quot;sso-s&quot; value=&quot;/ sample_/welcome.jsp&quot;>!!discoiqbr!!&lt;entry key=&quot;sso-o&quot; value=&quot;/ sample_/logout.jsp&quot;/>!!discoiqbr!!

   Para obtener información detallada sobre la actualización del archivo config.xml, consulte [Edición manual del archivo de configuración de Document Security](https://helpx.adobe.com/es/aem-forms/6-3/admin-help/configuring-client-server-options.html#manually_editing_the_document_security_configuration_file).

   Ahora, AEM Forms Document Security está configurado para utilizar la autenticación extendida con una dirección URL de aterrizaje personalizada

#### Flujo de trabajo de autenticación extendida predeterminado con proveedores de identidad de terceros configurados en el servidor de AEM Forms {#default-extended-authentication-workflow-with-third-party-identity-providers-configured-on-aem-forms-server}

La autenticación extendida puede utilizar diferentes tipos de autenticación disponibles en el servidor de AEM Forms. Por ejemplo, SAML, [Más ejemplos].

Nota: Si los proveedores de SAML están configurados en el servidor de AEM Forms, entonces antes de mostrar la dirección URL de aterrizaje se muestra una página que contiene todos los proveedores de identidad configurados para autenticaciones SAML.

La siguiente pantalla se muestra cuando se abre un documento protegido en Acrobat.

#### Flujo de trabajo de autenticación extendida personalizado cuando los proveedores SAML están configurados en el servidor de AEM Forms {#custom-extended-authentication-workflow-when-saml-providers-are-configured-on-aem-forms-server}

Si los proveedores de SAML están configurados en el servidor de AEM Forms, entonces antes de mostrar la dirección URL de aterrizaje se muestra una página que contiene todos los proveedores de identidad configurados para autenticaciones SAML.

Los requisitos previos para configurar un flujo de trabajo de autenticación extendida personalizado cuando los proveedores SAML están configurados en el servidor de AEM Forms son los siguientes:

* Las autenticaciones SAML deben estar configuradas en el servidor de AEM Forms
* Se debe implementar un archivo war personalizado en el servidor de AEM Forms, que contenga una página de autenticación personalizada y una lógica completa para aceptar las credenciales de usuario y autenticarse con el servidor de AEM Forms.

#### Uso de la página personalizada para enumerar las autenticaciones de SAML {#using-custom-page-for-listing-saml-authentications}

También puede mostrar una página personalizada para incluir todos los proveedores de autenticación configurados en el servidor de AEM Forms. Para crear una página de este tipo:

1. Empaquete la página de autenticación personalizada en un archivo war e implemente el archivo en el servidor de AEM Forms. El archivo war contiene una lógica completa para aceptar las credenciales de usuario y autenticarse con el servidor de AEM Forms.
1. Abra la interfaz de usuario de administración de AEM Forms y vaya a **[!UICONTROL Configuración]** > **[!UICONTROL Administración de usuarios]** > **[!UICONTROL Configuración]** > **[!UICONTROL Configuración de Proveedor de servicio de SAML]**.
1. Añada lo siguiente en el campo Propiedades personalizadas y haga clic en **[!UICONTROL Guardar]**.

   *saml.sp.discovery.url=/demoJSP/saml_discovery.jsp*

   Ahora, AEM Forms Document Security está configurado para mostrar una página personalizada que contenga todos los proveedores de autenticación establecidos.

### Obtener una cuenta de usuario {#obtaining-a-user-account}

Si todavía no tiene una cuenta de Document Security, puede iniciar el proceso de registro cuando se produzcan estos eventos:

* Un usuario de Document Security que desea enviarle un archivo protegido por una directiva le agrega a una directiva.
* El administrador de Document Security crea una cuenta para usted.

Después de registrarse y activar la cuenta, puede utilizar los archivos protegidos por directivas que recibió autorización para utilizar mediante una directiva.

>[!NOTE]
>
>Si recibe un archivo protegido por una directiva y no tiene una cuenta de Document Security, o si recibe una invitación para registrarse, póngase en contacto con la persona que le envió el archivo para obtener ayuda.

Si recibe una invitación por correo electrónico de Document Security para registrarse, puede hacerlo utilizando la URL del mensaje de correo electrónico para abrir la página de registro en línea. Después de registrarse, recibirá un segundo aviso sobre la activación de su cuenta.

#### Obtener una cuenta de usuario externa {#obtain-an-external-user-account}

1. Abra el correo electrónico de registro de Document Security. La dirección URL que contiene el mensaje es un vínculo a la página de registro de usuarios externos de Document Security. Si no recibe un mensaje de registro, póngase en contacto con la persona que le envió el archivo para obtener ayuda.
1. Haga clic en la dirección URL o cópiela y péguela en el explorador.
1. Escriba su nombre, organización y contraseña en los cuadros correspondientes. La contraseña puede ser cualquier combinación de ocho caracteres.

   >[!NOTE]
   >
   >Asegúrese de elegir una contraseña que sea fácil de recordar; no hay ningún método disponible para buscar contraseñas olvidadas.

1. Haga clic en **Registrar**. Aparece un mensaje que le informa de que debe buscar un mensaje de correo electrónico de activación en su correo electrónico.
1. Abra el correo electrónico de confirmación de registro de Document Security.
1. Haga clic en la dirección URL que aparece en el mensaje.
1. Haga clic en el vínculo a la página Inicio de sesión.
1. En el cuadro **Username**, escriba la dirección de correo electrónico en la que se registró con Document Security. Esta dirección de correo electrónico es el nombre de usuario predeterminado de Document Security.
1. En el cuadro **Password**, escriba la contraseña que creó al registrarse.
1. Haga clic en **Login**.

### Crear y administrar directivas {#creating-and-managing-policies}

Si tiene permiso del administrador de Document Security, puede crear directivas para aplicarlas a sus propios archivos en la página de directivas de las páginas web de Document Security.

Algunos de los ajustes de directiva disponibles para crear directivas en las páginas web de Document Security no son compatibles con los archivos de Word, Excel y PowerPoint. Las siguientes tablas describen cómo los permisos de directivas se asignan a las funciones de Word, Excel y PowerPoint.

<table>
 <thead>
  <tr>
   <th><p>Permisos</p></th>
   <th><p>Compatibilidad con Word, Excel y PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Imprimir &gt; No permitido</p></td>
   <td><p>No se permite imprimir el archivo.</p></td>
  </tr>
  <tr>
   <td><p>Imprimir &gt; Permitido</p></td>
   <td><p>Se permite imprimir el archivo.</p><p><strong>Nota</strong>: <i>Si una directiva concede el permiso de copia pero no el permiso de impresión, se puede imprimir el contenido copiado en otro archivo.</i></p></td>
  </tr>
  <tr>
   <td><p>Imprimir &gt; Baja res. Solamente</p></td>
   <td><p>No aplicable.</p></td>
  </tr>
  <tr>
   <td><p>Cambiar &gt; Cualquiera</p></td>
   <td><p>El archivo se puede cambiar.</p><p>Cuando no se concede este permiso, no se pueden modificar los archivos protegidos de Word y Excel. Puede modificar los archivos de PowerPoint, pero no puede guardar los cambios ni ver las presentaciones de diapositivas de los archivos modificados.</p></td>
  </tr>
  <tr>
   <td><p>Cambiar &gt; No permitido</p></td>
   <td><p>Los usuarios no pueden modificar los archivos protegidos.</p></td>
  </tr>
  <tr>
   <td><p>Cambiar &gt; Modificar páginas</p></td>
   <td><p>No aplicable.</p><p>Incluye insertar, eliminar y rotar páginas.</p></td>
  </tr>
  <tr>
   <td><p>Cambiar &gt; Rellenar y firmar</p></td>
   <td><p>No aplicable.</p></td>
  </tr>
  <tr>
   <td><p>Sin conexión</p></td>
   <td><p>El archivo se puede abrir sin conexión.</p></td>
  </tr>
  <tr>
   <td><p>Copiar</p></td>
   <td><p>El contenido del archivo se puede copiar en otros archivos.</p></td>
  </tr>
  <tr>
   <td><p>Lector de pantalla </p></td>
   <td><p>Los lectores de pantalla (dispositivos para usuarios con deficiencias visuales) pueden leer el contenido del archivo.</p></td>
  </tr>
  <tr>
   <td><p>Validez del permiso</p></td>
   <td><p>Compatible.</p></td>
  </tr>
 </tbody>
</table>

<table>
 <thead>
  <tr>
   <th><p>Configuración general</p></th>
   <th><p>Compatibilidad con Word, Excel y PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Período de validez</p></td>
   <td><p>Compatible.</p></td>
  </tr>
  <tr>
   <td><p>Documento de auditoría</p></td>
   <td><p>Compatible.</p></td>
  </tr>
  <tr>
   <td><p>Período de préstamo sin conexión automático</p></td>
   <td><p>Compatible.</p></td>
  </tr>
  <tr>
   <td><p>Proveedores de autorización externa</p></td>
   <td><p>Compatible.</p></td>
  </tr>
 </tbody>
</table>

<table>
 <thead>
  <tr>
   <th><p>Configuración avanzada</p></th>
   <th><p>Compatibilidad con Word, Excel y PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Marcas de agua dinámicas</p></td>
   <td><p>Compatible.</p></td>
  </tr>
  <tr>
   <td><p>Complementos de certificación</p></td>
   <td><p>No aplicable.</p></td>
  </tr>
  <tr>
   <td><p>Algoritmo de codificación y longitud de clave </p></td>
   <td><p>Todas las opciones son compatibles.</p></td>
  </tr>
  <tr>
   <td><p>Restricción de documento</p></td>
   <td><p>Todo el contenido del archivo se cifra, independientemente de la configuración de la directiva.</p></td>
  </tr>
  <tr>
   <td><p>Mensaje de error de acceso denegado</p></td>
   <td><p>Compatible.</p></td>
  </tr>
 </tbody>
</table>

Para obtener más información sobre la creación y administración de directivas, consulte [Ayuda para el usuario final de Document Security](https://help.adobe.com/en_US/AEMForms/6.1/RMHelp/).

### Aplicar directivas {#applying-policies}

Puede aplicar cualquier directiva disponible a un archivo, incluidas las directivas que haya creado y las que formen parte de conjuntos de directivas a las que tenga acceso. Antes de aplicar una directiva, debe guardar el archivo.

Después de aplicar una directiva, se agrega a la lista Utilizadas recientemente en el menú de AEM Document Security para facilitar la aplicación de las directivas que se utilizan con más frecuencia. Si utiliza más de una instancia de Document Security, la lista Utilizado recientemente muestra las directivas únicamente para el servidor al que está conectado actualmente o para el servidor predeterminado si aún no ha iniciado sesión en una instancia de Document Security.

>[!NOTE]
>
>Las políticas solo se pueden aplicar a archivos de documento de Word (.doc, también .docx y .docm en Microsoft® Office 2010 y 2013), archivos de libros de Excel (.xls, también .xlsx y .xlsm en Microsoft® Office 2010 y 2013) y archivos de presentación de PowerPoint (.ppt, también .pptx y .pptm en Microsoft® Office 2010 y 2013). No puede aplicar directivas a archivos de plantilla de Word (.dot), archivos de plantilla de Excel (.xlt) ni archivos de plantilla de diseño de PowerPoint (.pot).

#### Aplicar una directiva {#apply-a-policy}

1. En la extensión de Document Security para Microsoft® Office 2010 y 2013, en la pestaña **Document Security**, seleccione **Seguridad > Elegir directiva**.

   Si ha elegido el nombre de usuario y la contraseña como método de autenticación en el servidor y aún no ha proporcionado la información de inicio de sesión para Document Security, aparecerá un cuadro de diálogo en el que se solicitará su nombre de usuario y contraseña.

1. Seleccione una directiva en la lista y haga clic en **Aplicar**.
1. Guarde el archivo.

#### Aplicar una directiva usada recientemente {#apply-a-recently-used-policy}

1. En la extensión de Document Security para Microsoft® Office 2010 y 2013, en la pestaña **Document Security**, seleccione **Proteger > ***[Nombre de la directiva]*.
1. Guarde el archivo.

## Usar archivos protegidos por directivas {#usingaemdocumentsecurityextensionpolicyprotectedfiles}

Los archivos protegidos por directivas contienen propiedad intelectual propiedad del editor del archivo y archivos protegidos por Document Security.

Puede utilizar archivos protegidos por políticas tanto si pertenece como si no a la organización del editor de archivos. Para abrir archivos protegidos por directivas, Document Security debe reconocerle, ya sea mediante la inclusión en un LDAP vinculado o una lista de Active Directory, agregándolo como usuario local para LiveCycle o AEM Forms en JEE, o mediante el registro en Document Security después de ser invitado como usuario.

Si recibe un archivo protegido por una directiva y no tiene una cuenta de Document Security, o si recibe una invitación para registrarse, póngase en contacto con la persona que le envió el archivo para obtener ayuda.

### Uso de archivos protegidos por políticas en Microsoft® Office {#working-with-policy-protected-files-in-microsoft-office}

La extensión de Document Security para Microsoft® Office restringe ciertas funcionalidades de Word, Excel y PowerPoint para proteger la propiedad intelectual del editor del archivo. Si no tiene permiso para cambiar el archivo, no puede guardar las modificaciones.

Si está trabajando con un archivo protegido por una directiva, es posible que algunas características del producto no estén disponibles o que no funcionen como de costumbre. Si también tiene un archivo no protegido abierto, la mayoría de las funciones se activan para el archivo no protegido, excepto las que permiten importar o copiar contenido de un archivo protegido por una directiva para el que no tiene permisos de copia o exportación.

>[!NOTE]
>
>Cuando se utilizan aplicaciones de Office compatibles con la extensión de Document Security, se recomienda desactivar la configuración DEP de Windows. Además, para garantizar que las aplicaciones de Office se inicien sin problemas en un equipo que tenga instalada la extensión de Document Security y McAfee VirusScan con la opción de protección de acceso activada, desactive la opción Protección contra desbordamientos de búfer en la consola de McAfee VirusScan.

Si una función no está disponible, el nombre del comando en el menú y el botón de barra de herramientas relacionado no estarán disponibles. En la extensión de Document Security para Microsoft® Office, cuando pasa el puntero del ratón sobre el comando o el botón, una sugerencia de herramienta indica que Document Security ha bloqueado el comando.

### Abrir archivos protegidos por directivas {#opening-policy-protected-files}

Puede abrir archivos protegidos por directivas utilizando los mismos métodos que utiliza para abrir cualquier otro archivo. Si no ha iniciado sesión en Document Security, se le pedirá que lo haga a menos que no esté conectado a Internet y pueda abrir el archivo sin conexión. Si cancela el proceso de inicio de sesión, se deniega el acceso.

Si no tiene permiso para abrir el archivo, se le informará de que se ha denegado el acceso. Si se han revocado los privilegios de acceso a archivos, también se le puede dirigir a una versión actualizada del archivo si hay una disponible. Si no puede abrir un archivo protegido por una directiva, póngase en contacto con el editor de archivos para obtener ayuda adicional.

Cuando se abre un archivo protegido, el texto de la barra de título que sigue al nombre del archivo indica que el archivo está protegido por AEM Document Security.

Al abrir un documento protegido en la extensión de Document Security para Microsoft® Office desde SharePoint Server, asegúrese de que esté abierto el programa de Microsoft® Office asociado al tipo de archivo, como Microsoft® Word, Microsoft® Excel o Microsoft® PowerPoint. Si intenta abrir el archivo sin abrir la aplicación asociada, es posible que el documento no se abra y se muestre un mensaje de error que indique que debe instalar el complemento aplicable. Además de abrir la aplicación requerida, se recomienda borrar la carpeta de la memoria caché antes de abrir un documento protegido en la extensión de Document Security para Microsoft® Office desde SharePoint Server. Además, cuando se abre un documento protegido desde SharePoint Server, todos los permisos del documento se desactivan, independientemente de la directiva que se haya aplicado.

Según el método de autenticación implementado en Document Security, se le puede pedir que elija el método de autenticación al abrir un documento protegido. Si Document Security admite más de un método de autenticación, se le presentarán las opciones de autenticación. Por ejemplo, si Document Security Server proporciona autenticación de nombre de usuario/contraseña y de certificado, puede elegir el método de autenticación adecuado. Si la autenticación basada en certificados está habilitada, se le pedirá que utilice el certificado que ha recibido e instalado.

La experiencia del usuario al abrir archivos protegidos depende de la configuración de autenticación mutua en el servidor. Si solo hay un certificado de cliente válido instalado, no aparece ningún cuadro de diálogo de autenticación y los archivos se abren correctamente. Sin embargo, si hay varios certificados de cliente instalados en un equipo, aparece un cuadro de diálogo de autenticación. El usuario debe elegir un certificado válido para abrir el archivo protegido.

### Quitar la protección de directivas de un archivo {#removing-policy-protection-from-a-file}

Si está autorizado, puede eliminar la protección de directivas de los archivos protegidos. Si lo hace, Document Security dejará de proteger el archivo.

1. En la extensión de Document Security para Microsoft® Office 2010 y 2013, en la pestaña **Document Security**, seleccione **Quitar**.

   Si todavía no ha proporcionado la información de inicio de sesión para Document Security, aparecerá un cuadro de diálogo en el que se solicitará su nombre de usuario y contraseña.

>[!NOTE]
>
>Si no puede quitar una directiva de un archivo protegido por usted, póngase en contacto con un administrador de Document Security.

### Visualización de la configuración de seguridad {#viewing-security-settings}

Puede ver los permisos que tiene para imprimir, copiar, cambiar y acceder al archivo sin conexión, junto con el período de validez del archivo.

En la extensión de Document Security para Microsoft® Office 2010, el grupo Estado de seguridad de la pestaña Document Security muestra sus permisos para el archivo.

Haga lo siguiente:

* En la extensión de Document Security para Microsoft® Office 2010 y 2013, en la **pestaña Document Security**, en el grupo **Estado de seguridad**, haga clic en cualquier elemento.

### Guardar documentos cuando la directiva de aplicación automática está habilitada {#saving-documents-when-auto-apply-policy-is-enabled}

Si el administrador ha habilitado la funcionalidad de política de aplicación automática, cualquier documento que cree o edite se protegerá automáticamente al guardar el documento.

Si la política de aplicación automática está activada, la extensión de Document Security para Microsoft® Office le pedirá que inicie sesión en el servidor de Document Security. Debe proporcionar el nombre de usuario y la contraseña para que el servidor los autentique. Si ha proporcionado las credenciales de inicio de sesión correctas, el documento se guardará y protegerá.

>[!NOTE]
>
>Si no puede iniciar sesión en Document Security, es posible que el documento se guarde o no. Esto depende de cómo haya configurado el administrador la directiva de aplicación automática. Consulte con el administrador cómo se gestionan los documentos en esta situación.

### Sincronización del acceso sin conexión {#synchronizing-for-offline-access}

Las directivas pueden permitirle abrir archivos sin conexión y sin estar conectado a Document Security. Debe haber iniciado sesión anteriormente en Document Security para poder establecer sus credenciales con el servidor antes de poder trabajar sin conexión. Si planea trabajar con archivos sin conexión, se recomienda sincronizar con Document Security antes de desconectar para garantizar que la configuración de directiva de los archivos esté actualizada con el servidor. También se recomienda abrir el archivo en línea una vez, antes de abrirlo sin conexión. Si no abre el archivo una vez en línea o no se sincroniza con el servidor, es posible que aún pueda utilizar archivos protegidos por directivas sin conexión. Sin embargo, el período de concesión sin conexión no debe haber caducado y la configuración de directiva del archivo no debe haber cambiado desde la última sincronización manual o automática con el servidor.

Haga lo siguiente:

* En la extensión de Document Security para Microsoft® Office 2010 y 2013, en la pestaña **Document Security**, seleccione **Sincronizar sin conexión**.

  ***Nota**: El botón Sincronizar sin conexión está disponible aunque el usuario no tenga permiso sin conexión para el documento. Sin embargo, seleccionar el botón no hace nada. *

### Uso de marcas de agua dinámicas {#working-with-dynamic-watermarks}

La extensión de Document Security para Microsoft® Office admite la inclusión de marcas de agua dinámicas basadas en texto en documentos protegidos por políticas. Una marca de agua dinámica puede incluir información que puede cambiar, como la fecha, la hora, el nombre de usuario o el nombre de la directiva. Si un usuario imprime un archivo protegido por una directiva y dicho archivo contiene una marca de agua dinámica y el permiso de impresión, la marca de agua aparece en el resultado.

La extensión de Document Security no admite funciones de marca de agua enriquecidas como marcas de agua basadas en PDF, varios elementos en una marca de agua, opciones de formato de texto y rango de páginas.

Puede crear una marca de agua dinámica mediante las páginas web de Document Security. Para obtener más información sobre cómo crear e incluir marcas de agua dinámicas en un documento protegido por una directiva, consulte [Ayuda para el usuario final de Document Security](https://www.adobe.com/go/learn_lc_euRightsMgmt_11_es).

La extensión de Document Security para Microsoft® Office ofrece compatibilidad con estas funciones de marca de agua:

<table>
 <thead>
  <tr>
   <th><p>Opciones de marca de agua de Document Security</p></th>
   <th><p>Compatibilidad con Word, Excel y PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Nombre de directiva</p></td>
   <td><p>Compatible.</p></td>
  </tr>
  <tr>
   <td><p>Nombre de la marca de agua</p></td>
   <td><p>Compatible.</p></td>
  </tr>
  <tr>
   <td><p>Usar como fondo</p></td>
   <td><p>El comportamiento de visualización de una marca de agua dinámica es el mismo independientemente de si selecciona Usar como fondo.</p><p>En Word 2010 y 2013, las marcas de agua dinámicas solo aparecen en Diseño de impresión y Vista previa de impresión. </p><p>Para Excel 2010 y 2013, aparece en Vista previa de impresión y Diseño de página.</p></td>
  </tr>
  <tr>
   <td><p>Posición vertical</p></td>
   <td><p>Compatible</p></td>
  </tr>
  <tr>
   <td><p>Posición horizontal</p></td>
   <td><p>Compatible</p><p>En Excel 2010 y 2013, la colocación horizontal de marcas de agua mediante puntos no funciona.</p></td>
  </tr>
  <tr>
   <td><p>Escala</p></td>
   <td><p>Compatible</p></td>
  </tr>
  <tr>
   <td><p>Posición</p></td>
   <td><p>Compatible</p></td>
  </tr>
  <tr>
   <td><p>Opacidad</p></td>
   <td><p>Compatible</p></td>
  </tr>
 </tbody>
</table>

### Abrir las páginas web de Document Security {#opening-the-document-security-web-pages}

Puede abrir las páginas web de Document Security para crear y actualizar las directivas de usuario, así como la información de estado de vista y auditoría de los archivos protegidos por directivas. También puede utilizar las páginas web de Document Security para cambiar directivas o anular el acceso a un archivo protegido por una directiva.

Para abrir las páginas web de Document Security, en la extensión de Document Security para Microsoft® Office 2010 y 2013, en la pestaña **Document Security**, seleccione **Crear y administrar políticas**. Si todavía no ha proporcionado la información de inicio de sesión, el explorador se abre en la página de inicio de sesión del servidor.

### Cambiar directivas {#changing-policies}

Si tiene permisos, normalmente como administrador de Document Security o editor de archivos, puede aplicar una directiva diferente a un archivo o cambiar la configuración de la directiva aplicada actualmente.

Para cambiar la configuración de una directiva, utilice las páginas web de Document Security.

1. Haga lo siguiente:

   * En la extensión de Document Security para Microsoft® Office 2010 o 2013, en la pestaña **Document Security**, seleccione **Seguridad > Cambiar seguridad**.

1. Seleccione una directiva en la lista y haga clic en **Aplicar**.

### Revocar privilegios de acceso a archivos {#revoking-file-access-privileges}

Puede anular la capacidad de abrir archivos protegidos. Cuando se revocan los privilegios de acceso para un archivo, también se puede especificar el mensaje que aparece para cualquiera que intente abrir el archivo y la dirección URL de una versión actualizada del archivo si se va a reemplazar con una copia revisada.

1. Haga lo siguiente:

   * En la extensión de Document Security para Microsoft® Office 2010 y 2013, en la pestaña **Document Security**, seleccione **Revocar**.

   Las páginas web de Document Security se abren en la página de Revocar documentos.

1. Especifique un mensaje para mostrar y, si está disponible, una dirección URL para la versión actualizada y haga clic en **Aceptar**.

Para obtener más información sobre la anulación de privilegios de acceso a archivos, consulte la [Ayuda del usuario final de Document Security](https://help.adobe.com/en_US/AEMForms/6.1/RMHelp/).

Los privilegios de acceso se pueden restablecer a través de las páginas web de Document Security.

### Visualización del historial de auditoría de archivos {#viewing-the-file-audit-history}

Document Security puede guardar el historial de auditoría de los archivos protegidos por directivas para que pueda auditar las acciones que los usuarios realizan en los archivos.

Los eventos auditados para archivos de Word, Excel y PowerPoint incluyen:

**Proteger un nuevo documento** Directiva aplicada a un archivo

**Ver el documento** Archivo abierto

**Cerrar el documento** Archivo cerrado

**Revocar documento** Privilegios de acceso al archivo eliminados

**Anular revocación del documento** Privilegios de acceso al archivo devueltos

**Modificar Documento** Archivo modificado y guardado localmente

**Imprimir en alta resolución** Archivo impreso

**Cambiar controlador de seguridad** Protección de directiva eliminada del archivo

**Cambiar directiva en el documento** Nueva directiva aplicada al archivo desde las páginas web de Document Security

### Ver el historial de auditoría de un archivo {#view-the-audit-history-for-a-file}

En la extensión de Document Security para Microsoft® Office 2010 y 2013, en la pestaña **Document Security**, seleccione **Historial de auditoría**.

Las páginas web de Document Security se abren en la página Eventos, que muestra eventos auditados para el archivo actual.

### Funciones restringidas de Microsoft® Office {#microsoft-office-restricted-features}

Para proteger la propiedad intelectual, algunas funciones de Microsoft® Office no están disponibles cuando se abre un archivo protegido por una política. La lista de las funciones no disponibles depende de los permisos que se concedan al usuario actual. Algunas funciones no están disponibles solo para un archivo protegido y otras para todos los archivos cuando se encuentra en una sesión protegida. Por lo general, se encuentra en una sesión protegida desde el momento en que abre un archivo protegido por una directiva hasta que cierra la aplicación o la sesión caduca.

La mayoría de las directivas otorgan permisos completos al editor de archivos. Es posible que otros usuarios observen restricciones de funciones adicionales.

Si un comando no está disponible, el nombre del comando en el menú y el botón de barra de herramientas relacionado aparecen atenuados.

>[!NOTE]
>
>La aplicación de una directiva a un archivo que contiene un vínculo a un archivo incrustado no se aplica al archivo vinculado. Document Security para Microsoft® Office no extiende la protección a los archivos vinculados.

* Los archivos de Word, Excel y PowerPoint protegidos por directivas no se pueden abrir en una ventana del explorador de Internet Explorer.
* Los usuarios a los que solo se concedió el permiso de modificación no pueden copiar contenido en un archivo desde otra aplicación mediante el Portapapeles de Windows. Los usuarios pueden copiar contenido en archivos activando la opción Portapapeles de Microsoft® Office.
* Al abrir un archivo protegido por una política en Microsoft® Office, la tecla Impr Pant deja de estar disponible hasta que se cierre la aplicación o la sesión caduque.
* Document Security para Microsoft® Office no admite la creación y el control de versiones distribuidas basadas en la web (Web-based Distributed Authoring and Versioning, WebDAV). En la mayoría de los casos, no se puede abrir un archivo protegido por una directiva desde una carpeta WebDAV. Si puede abrir un archivo protegido por una directiva, no tendrá permisos para guardar, imprimir, cambiar o copiar del archivo.

La seguridad general que se aplica a los archivos protegidos por políticas incluye las siguientes restricciones:

Muchas funciones comunes pueden estar restringidas en Word, Excel y PowerPoint durante una sesión protegida.

Si se abre un archivo protegido por una política que no permite al usuario realizar cambios, los comandos que cambien el archivo de alguna manera no estarán disponibles. Solo están disponibles los comandos que abren o crean nuevos documentos y cambian las preferencias de la aplicación.

#### Restricciones de Word 2010 y Word 2013 {#word-2010-and-word-2013-restrictions}

Al abrir un archivo protegido por una directiva en Word, la información de recuperación automática de archivos no estará disponible hasta que cierre y reinicie Word. Además, las funciones enumeradas a continuación están restringidas en las situaciones descritas:

**Archivo > Nuevo > Nuevo basado en archivo** Disponible, pero no se pueden guardar los archivos creados con este comando mientras esté abierto un archivo protegido por una directiva. El contenido del nuevo archivo no se puede copiar en otro archivo.

**Archivo > Guardar** Restringido con el permiso de modificación.

**Archivo > Guardar como** Todas las opciones restringidas por el permiso de modificación.

**Archivo > Imprimir** Todas las opciones restringidas por el permiso de impresión. No disponible a menos que la directiva permita la impresión de alta resolución.

**Archivo > Guardar y Enviar** Todas las opciones no están disponibles durante una sesión protegida.

**Archivo > Info > Proteger documento > Cifrar con contraseña, Añadir firma digital, Marcar como final, Restringir permisos por personas** No disponibles durante una sesión protegida.

**Archivo > Flujos de trabajo** No disponible durante una sesión protegida.

***Nota **: La capacidad de inicio de un flujo de trabajo de las versiones de Microsoft® Office 2010 de Word, Excel y PowerPoint solo está disponible en los grupos de Office Professional Plus 2010, Office Enterprise 2010 y Office Ultimate 2010, así como en las versiones independientes de estos programas de Office 2010.*

**Publicación de blog > Publicar** No disponible durante una sesión protegida.

**Archivo > Servidor > Menú tareas del servidor de archivos** No disponible durante una sesión protegida.

**Inicio > Portapapeles > Copiar** Restringido con el permiso Copiar. Si no se permite copiar, el contenido copiado no se puede pegar en ningún otro archivo ni en el portapapeles de Office. El contenido se puede copiar dentro del archivo protegido si el usuario tiene el permiso de cambio.

**Inicio > Portapapeles > Pegar** Restringido con el permiso Cambiar.

**Inicio > Portapapeles > Pegado especial** Restringido por el permiso de modificación.

**Insertar > Texto > Objeto** No disponible durante una sesión protegida. Los archivos protegidos por directivas no se pueden insertar en ningún momento.

**Correos** La mayoría de las opciones de esta pestaña no están disponibles durante una sesión protegida.

**Revisar > Revisión > Referencia** Restringido por el permiso Copiar. No disponible si no se permite copiar.

**Revisar > Revisión > Thesaurus** Restringido por el permiso de copia. No disponible si no se permite copiar.

**Revisar > Idioma > Traducir > Traducir documento** Habilitado con el permiso de copia.

**Revisar > Idioma > Traducir > Traducir texto seleccionado** Habilitado con el permiso Copiar.

**Revisar > Idioma > Traducir > Minitraductor** Habilitado con el permiso de copia.

**Revisar > Comparar > Comparar** No disponible durante una sesión protegida. Los archivos protegidos por directivas no se pueden comparar en ningún momento.

**Revisar > Proteger > Bloquear autores** No disponible durante una sesión protegida.

**Revisar > Proteger > Restringir edición** No disponible durante una sesión protegida.

**Ver > Macros** Algunas macros están restringidas por el permiso de copia y no están disponibles a menos que se permita copiar.

**Complementos** No se puede agregar ni eliminar durante una sesión protegida.

**Colaboración en línea** No disponible durante una sesión protegida.

**Documentos principales y secundarios** Los documentos secundarios se rigen por la directiva de documentos principales cuando se abren en el documento principal. Si se abren por separado, los documentos secundarios no se pueden imprimir, copiar ni modificar.

**Volver a resumir** No disponible durante una sesión protegida.

**Marcos (y todos los comandos relacionados)** No disponibles durante una sesión protegida.

**Panel documento** No disponible durante una sesión protegida.

**Programador > Plantilla de documento** No disponible durante una sesión protegida. Para acceder a este comando, seleccione Archivo > Opciones > Personalizar > pestaña Programador > Plantillas > Plantilla de documento.

**Esquema > Documento principal > Crear documento secundario
Insertar documento secundario** No disponible durante una sesión protegida.

#### Restricciones de Excel 2010 y Excel 2013 {#excel-2010-and-excel-2013-restrictions}

Las siguientes funciones están restringidas en las situaciones descritas:

**Archivo > Nuevo > Nuevo a partir de archivo** Disponible, pero los archivos creados con este comando durante una sesión protegida no se pueden guardar. El contenido del nuevo archivo no se puede copiar en otro archivo.

**Archivo > Guardar, Guardar como** Restringido por el permiso de modificación.

**Archivo > Guardar como > PDF** No disponible durante una sesión protegida.

**Archivo > Imprimir** Restringido por el permiso de impresión. No disponible a menos que la directiva permita la impresión de alta resolución.

**Archivo > Información > Proteger documento** No disponible durante una sesión protegida.

**Archivo > Información > Proteger libro** No disponible durante una sesión protegida.

**Archivo > Guardar y enviar** No disponible durante una sesión protegida.

**Archivo > Opciones > Complementos** No se puede agregar ni eliminar durante una sesión protegida.

**Archivo > Flujos de trabajo** No disponible durante una sesión protegida.

***Nota **: La capacidad de inicio de un flujo de trabajo de las versiones de Microsoft® Office 2010 de Word, Excel y PowerPoint solo está disponible en los grupos de Office Professional Plus 2010, Office Enterprise 2010 y Office Ultimate 2010, así como en las versiones independientes de estos programas de Office 2010.*

**Archivo > Servidor > Menú tareas del servidor de archivos** No disponible durante una sesión protegida.

**Inicio > Portapapeles > Copiar** Restringido con el permiso Copiar. Si no se permite copiar, el contenido copiado no se puede pegar en ningún otro archivo ni en el portapapeles de Microsoft® Office. El contenido se puede copiar dentro del archivo protegido si el usuario tiene el permiso de cambio.

**Inicio > Portapapeles > Pegar** Restringido con el permiso Cambiar.

**Inicio > Portapapeles > Pegado especial** Restringido por el permiso de modificación.

**Inicio > Celdas > Formato > Mover o copiar hoja** No disponible durante una sesión protegida.

**Inicio > Celdas > Insertar > Insertar hoja** No disponible durante una sesión protegida.

**Inicio > Celdas > Eliminar > Eliminar hoja** No disponible durante una sesión protegida.

**Inicio > Edición > Rellenar > En toda la hoja** Restringido por el permiso de modificación.

**Insertar > Tablas > Tabla** Restringido por el permiso Cambiar.

**Insertar > Tablas > Tabla dinámica** Los archivos protegidos por directivas no se pueden seleccionar en el asistente de creación.

**Insertar > Texto > Objeto** No disponible durante una sesión protegida. Los archivos protegidos por directivas no se pueden insertar en ningún momento.

**Insertar > Texto > Encabezado y pie de página** Restringido por el permiso Cambiar. No disponible para un documento protegido por una directiva.

**Datos > Obtener datos externos** Los datos de archivos protegidos por directivas no se pueden importar.

**Datos > Esquema > Subtotal** Restringido por el permiso Cambiar.

**Datos > Herramientas de datos > Validación de datos** Restringido por el permiso Cambiar.

**Revisar > Revisión > Referencia** Restringido por el permiso Copiar.

**Revisar > Revisión > Thesaurus** Restringido por el permiso de copia.

**Revisar > Idioma > Traducir** Restringido con el permiso Copiar.

**Revisar > Cambios > Proteger hoja** No disponible durante una sesión protegida.

**Revisar > Cambios > Proteger libro** No disponible durante una sesión protegida.

**Revisar > Cambios > Compartir libro** No disponible durante una sesión protegida.

**Revisar > Cambios > Proteger y compartir libro** No disponible durante una sesión protegida.

**Revisar > Cambios > Permitir que los usuarios modifiquen intervalos** No disponible durante una sesión protegida.

**Revisar > Cambios > Control de cambios > Resaltar
cambios** No disponible para un archivo protegido por una directiva que contenga una marca de agua dinámica.

**Ver > Macros** Restringido por el permiso de modificación.

**Ver > Guardar espacio de trabajo** El comando no funciona.

**Desarrollador > XML > Paquetes de expansión** Algunas macros están restringidas por el permiso de copia y no están disponibles a menos que se permita copiar.

**Fórmulas > Auditoría de fórmulas > Comprobación de errores** Restringido por el permiso Cambiar. No disponible a menos que se permita el cambio.

**Colaboración en línea** No disponible durante una sesión protegida.

**Guardar información de recuperación automática** No disponible durante una sesión protegida.

***Nota **: Si intenta cambiar una celda en un archivo protegido por una directiva en el que no tiene permisos para realizar cambios, Excel muestra un mensaje de advertencia incorrecto que indica que debe quitar la protección del archivo mediante el comando Desproteger hoja. El uso del comando Desproteger hoja no elimina la protección de directivas del archivo.*

#### Restricciones de PowerPoint 2010 y PowerPoint 2013 {#powerpoint-2010-and-powerpoint-2013-restrictions}

Las siguientes funciones están restringidas en las situaciones descritas:

**Archivo > Nuevo > Nuevo a partir de archivo** Disponible, pero los archivos creados con este comando durante una sesión protegida no se pueden guardar. El contenido del nuevo archivo no se puede copiar en otro archivo.

**Archivo > Guardar** Restringido con el permiso de modificación.

**Archivo > Guardar como** Todas las opciones restringidas por el permiso de modificación.

**Archivo > Imprimir** Todas las opciones restringidas por el permiso de impresión. No disponible a menos que la directiva permita la impresión de alta resolución.

**Archivo > Guardar y enviar** No disponible durante una sesión protegida.

**Archivo > Información > Proteger presentación > Cifrar
con contraseña, Añadir una firma digital, Marcar como final, Restringir permisos por personas** No disponibles durante una sesión protegida.

**Archivo > Opciones de PowerPoint > Guardar información de recuperación automática** No disponible durante una sesión protegida.

**Archivo > Servidor > Menú tareas del servidor de archivos** No disponible durante una sesión protegida.

**Inicio > Portapapeles > Copiar** Restringido con el permiso Copiar. Si no se permite copiar, el contenido copiado no se puede pegar dentro del documento, en ningún otro archivo o en el portapapeles de Office. El contenido se puede copiar dentro del archivo protegido si el usuario tiene el permiso de cambio.

**Inicio > Portapapeles > Pegar** Restringido con el permiso Cambiar. Si no se permite copiar, el contenido copiado no se puede pegar dentro del documento.

**Inicio > Portapapeles > Pegado especial** Restringido por el permiso de modificación.

**Inicio > Diapositivas > Nuevas diapositivas > Diapositivas del esquema,
Reutilizar diapositivas** No disponible durante una sesión protegida.

**Insertar > Texto > Objeto** No disponible durante una sesión protegida. Los archivos protegidos por directivas no se pueden insertar en ningún momento.

**Diseño > Fondo > Estilos de fondo, Ocultar gráficos de fondo, Formato de fondo** No disponible para un archivo protegido por una directiva que contenga una marca de agua dinámica.

**Presentación con diapositivas > Configurar > Grabar presentación** Restringido por el permiso de cambio.

**Revisar > Revisión > Thesaurus** Restringido por el permiso de copia.

**Revisar > Idioma > Traducir** Restringido con el permiso Copiar.

**Revisar > Idioma > Traducir > Minitraductor** Habilitado con el permiso de copia.

**Ver > Vista de presentación > Presentación** Restringido por el permiso de modificación. Si no se permiten cambios, no se podrán ver presentaciones de diapositivas si se ha modificado el archivo.

**Ver > Macros** Algunas macros están restringidas por el permiso de copia y no están disponibles a menos que se permita copiar.

**Complementos** No se puede agregar ni eliminar durante una sesión protegida.

**Colaboración en línea** No disponible durante una sesión protegida.

## Usar proveedores de autenticación de terceros {#use-third-party-authentication-providers}

Puede utilizar proveedores de autenticación de terceros con AEM Forms Document Security. Estos proveedores de autenticación le ayudan a agregar una capa de acceso adicional a los documentos protegidos. AEM Forms Document Security admite los siguientes flujos de trabajo de autenticación extendida:

* Autenticación extendida mediante la URL de AEM Forms predeterminada
* Autenticación extendida mediante una dirección URL personalizada
* Flujo de trabajo de autenticación extendida predeterminado con proveedores de identidad de terceros configurados en AEM Forms en el servidor JEE
* Flujo de trabajo de autenticación extendida personalizado con proveedores de identidad de terceros configurados en AEM Forms en el servidor JEE
* Autenticación extendida mediante una página personalizada para enumerar autenticaciones SAML

## Glosario {#glossary}

Para obtener información sobre LiveCycle y AEM Forms en la terminología JEE, consulte el [Capítulo 19: Glosario](https://www.adobe.com/go/learn_aemforms_designer_65_es).
