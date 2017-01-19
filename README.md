# registro3d3
Código para RETOS Jalisco del prototipo construido en el reto 3 de 3

Esta aplicación utiliza JAVA, Alfresco (CMIS API), Bootstrap, JavaScript, JQuery, KnockoutJS, CSS, HTML5 & PostgreSQL.
Para correr esto, primero hay que instalar los siguientes requrimientos del lado del servidor.

Para efectos del prototipo creamos 5 módulos:

/login/index.html
Este módulo sirve para autenticarse con el servidor, se crea una sesión con un Id, que es guardado como cookie y se envía en cada request, sirve para validar las credenciales del usuario, aquí se puede ver un ejemplo de cómo se puede utilizar knockout para hacer binding de la información enviada (en JSON) y los campos de texto.
/usuarios/index.html
Este módulo muestra un listado de los usuarios que están activos para cada uno. Además despliega un modal que permite agregar un usuario a la tabla. Aquí mismo se puede ver otro ejemplo (en Contralor.js y Common.js) de cómo se usaría el knockout para bindear información de los usuarios.
/usuario/index.html
En esta pantalla se pueden observar más detalles de los usuarios, así como las declaraciones correspondientes a cada uno y toda la actividad relacionada con los datos del mismo.
/declaraciones/index.html
Aquí se listan las declaraciones, mismas que pueden ser filtradas, exportadas y descargadas.
/reporte/index.html
Este es uno de los tantos reportes, para ejemplo del prototipo, pusimos del de incumplimiento de declaraciones patrimoniales, se puede filtrar por año, por entidad y por tipo de declaración.
/obligado/index.html
Esta sería la pantalla que vera el servidor público / obligado, misma en la que puede generar sus declaraciones ( patrimoniales, fiscales y de conflicto de intereses), cambiar su contraseña, solicitar acuses de recibo, solicitar cambios, etc.

#JAVA, #Alfresco (CMIS API), #Bootstrap, #JavaScript, #JQuery, #KnockoutJS, #CSS, #HTML5 & #PostgreSQL
