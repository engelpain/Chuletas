## Números de respuesta de servidores
Centro Nacional de Desarrollo e Investigación de Tecnologías Libres (CENDITEL) <br>
[CENDITEL](https://www.cenditel.gob.ve/), Mérida - Venezuela<br>
Dirección de Desarrollo<br>
Autor: [Ing. Angelo Osorio](https://twitter.com/Engel_PAIN)<br>
Fecha de Elaboración: 05-09-2017 (dd,mm,aaaa)

### Respuestas informativas
* 100 - El navegador puede continuar realizando su petición (se utiliza para indicar que la primera parte de la petición del navegador se ha recibido correctamente.

### Peticiones correctas
* 200 - Respuesta estándar para peticiones correctas.
* 201 - La petición ha sido completada y ha resultado en la creación de un nuevo recurso.
* 204 - La petición se ha completado con éxito pero su respuesta no tiene ningún contenido.

### Redirecciones
* 301 - Esta y todas las peticiones futuras deberían ser dirigidas a la URI dada.
* 304 - Indica que la petición a la URL no ha sido modificada desde que fue requerida por última vez.

### Errores del cliente
* 400 - (**Bad Request**) La solicitud contiene sintaxis errónea y no debería repetirse.
* 401 - (**Unauthorized**). Fallo de autentificación.
* 403 - (**Forbidden**) Autentificada pero el servidor rehúsa responderla dado que el cliente no tiene
los privilegios para hacerla.
* 404 - (**Not Found**) Recurso no encontrado.

### Errores de servidor
* 500 - (**Internal Server Error**) Error interno del servidor.
* 502 - (**Bad Gateway**) El servidor está actuando de proxy o gateway y ha recibido una respuesta
inválida del otro servidor, por lo que no puede responder adecuadamente a la petición del navegador.
* 503 - (**Service Unavailable**) El servidor no puede responder a la petición del navegador porque
está congestionado o está realizando tareas de mantenimiento.
* 504 - (**Gateway Timeout**) El servidor está actuando de proxy o gateway y no ha recibido a tiempo
una respuesta del otro servidor, por lo que no puede responder adecuadamente a la petición del
navegador.

### Referencia en la Wikipedia
[Códigos de estado HTTP](https://es.wikipedia.org/wiki/Anexo:C%C3%B3digos_de_estado_HTTP)