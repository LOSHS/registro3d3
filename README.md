# Registro3d3<br/>
Código para RETOS Jalisco del prototipo construido en el reto 3 de 3<br/>
<br/>
Esta aplicación utiliza JAVA, Alfresco (CMIS API), Bootstrap, JavaScript, JQuery, KnockoutJS, CSS, HTML5 & PostgreSQL.<br/>
Para correr esto, primero hay que instalar los siguientes requrimientos del lado del servidor.<br/>
<br/>
Para efectos del prototipo creamos 5 módulos:<br/>
<br/>
/login/index.html<br/>
Este módulo sirve para autenticarse con el servidor, se crea una sesión con un Id, que es guardado como cookie y se envía en cada request, sirve para validar las credenciales del usuario, aquí se puede ver un ejemplo de cómo se puede utilizar knockout para hacer binding de la información enviada (en JSON) y los campos de texto.<br/>
/usuarios/index.html<br/>
Este módulo muestra un listado de los usuarios que están activos para cada uno. Además despliega un modal que permite agregar un usuario a la tabla. Aquí mismo se puede ver otro ejemplo (en Contralor.js y Common.js) de cómo se usaría el knockout para bindear información de los usuarios.<br/>
/usuario/index.html<br/>
En esta pantalla se pueden observar más detalles de los usuarios, así como las declaraciones correspondientes a cada uno y toda la actividad relacionada con los datos del mismo.<br/>
/declaraciones/index.html<br/>
Aquí se listan las declaraciones, mismas que pueden ser filtradas, exportadas a Word, Excel o Pdf y descargadas.<br/>
/reporte/index.html<br/>
Este es uno de los tantos reportes, para ejemplo del prototipo, pusimos del de incumplimiento de declaraciones patrimoniales, se puede filtrar por año, por entidad y por tipo de declaración.<br/>
/obligado/index.html<br/>
Esta sería la pantalla que vera el servidor público / obligado, misma en la que puede generar sus declaraciones ( patrimoniales, fiscales y de conflicto de intereses), cambiar su contraseña, solicitar acuses de recibo, solicitar cambios, etc.<br/>
<br/>
Existe además una funcionalidad en el prototipo para que la interfaz muestre diferentes aspecos o elementos, dependiendo del rol del usuario (Ver Como)<br/>
Algunas funciones como la de Enviar Aviso (envío de correos masivos) se pueden acceder desde distintos módulos para la facilidad de uso<br/>
<br/>
#JAVA, #JEE3, #Jersey, #JAX-RS, #REST, #Alfresco (CMIS API), #Bootstrap, #JavaScript, #JQuery, #KnockoutJS, #CSS, #HTML5 & #PostgreSQL, #ApacheTika<br/>
<br/>
El modulo de sesión controla el acceso seguro y validación de los usuarios<br/>
<br/>
<a href="#">/registro3de3/webapi/login</a> POST "application/json, application/x-www-form-urlencoded" Módulo de authenticación con contraseña encriptada en la base de datos, crea una sesión para el usuario en el container (WebLogic, Tomcat, Apache, Glassfish, JBoss, etc) <br/>
<a href="#">/registro3de3/webapi/logout</a> destruye la sesión de manera segura<br/>
<br/>
REST Endpoint<br/>
Con servicios REST se puede validar, consultar, capturar información y generar reportes, ya sea de los usuarios, de las declaraciónes o del mismo sistema para administrarlo<br/>
<br/>
<br/>
<a href="#">/registro3de3/webapi/users/</a> GET obtener datos de todos los usuarios activos <br/>
<a href="#">/registro3de3/webapi/users/{id}</a> GET obtener datos de un usuarios activo<br/>
<a href="#">/registro3de3/webapi/users/</a> POST crear un usuario<br/>
<a href="#">/registro3de3/webapi/users/{id}/toggleActiveStatus</a> cambiar estatus de usuario<br/>
<a href="#">/registro3de3/webapi/users/{id}</a> DELETE borrar (borrado lógico) un usuario<br/>
<br/>
<a href="#">/registro3de3/webapi/statements/fromUser/{id}</a> obtener datos de las declaraciones de un usuario específico<br/>
<a href="#">/registro3de3/webapi/statements/</a> GET obtener datos de todas los declaraciones<br/>
<a href="#">/registro3de3/webapi/statements/{id}</a> GET obtener datos de una declaración<br/>
<a href="#">/registro3de3/webapi/statements/</a> POST crear una declaración en la base de datos<br/>
<a href="#">/registro3de3/webapi/statements/{id}/toggleActiveStatus</a> cambiar estatus de declaración<br/>
<a href="#">/registro3de3/webapi/statements/{id}</a> DELETE borrar (borrado lógico) una declaracion<br/>
<br/>
<a href="#">/registro3de3/webapi/file/download/</a> POST "application/json, application/x-www-form-urlencoded" usando CMIS con Alfresco server descarga el archivo de Alfresco como Stream y envía ese stream al usuario por el navegador web, por lo que el navegador descargará el archivo<br/>
<a href="#">/registro3de3/webapi/file/upload/</a> POST "multipart/form-data" usando CMIS con Alfresco server carga el archivo al servidor de Alfresco (se puede cargar cualquier tipo de archivo, cualquier declaración puede ser guardada en Alfresco y sus metadatos en postgres), hay un modulo con Apache Tika que válida el contenido del stream del archivo más allá de que tenga una extensión incorrecta, o carezca de ella (.pdf, .doc, .xls, .jpg, etc)<br/>
