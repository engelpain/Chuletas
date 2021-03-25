# Ubicación de puertos de programas
Centro Nacional de Desarrollo e Investigación de Tecnologías Libres (CENDITEL)<br>
CENDITEL, Mérida - Venezuela <br>
Dirección de Desarrollo <br>
Autor: [Ing. Angelo Osorio](https://twitter.com/Engel_PAIN)<br>
Fecha de Elaboración: 05-12-2017 (dd,mm,aaaa)<br>


## Notas del autor
- El símbolo al principio de una línea de comandos indica:
```
   $ = hacer la sentencia como usuario
   # = hacer la sentencia como administrador
```
- Nano es el editor de texto de consolas que instala Debian por defecto, por
ello se utiliza nano, sin embargo, se puede usar cualquier otro editor.


## Apache
- El puerto de salida por defecto de Apache es el **80**

### Configurar un puerto distinto
- El archivo de configuración del puerto de Apache se encuentra en:
   - `# nano /etc/apache2/ports.conf`
- Entre las primeras líneas se encuentra una sentencia que dice **Listen 80**:
   ```
   # If you just change the port or add more ports here, you will likely also
   # have to change the VirtualHost statement in
   # /etc/apache2/sites-enabled/000-default.conf

   Listen 80
   ```
- Cambiar el 80 por el puerto de salida que se necesite.
- Reiniciar el servicio
   - `service apache2 restart`


## PostgreSQL
- El puerto de salida por defecto de Apache es el **5432**

### Configurar un puerto distinto
- El archivo de configuración del puerto de PostgreSQL se encuentra en:
   - `# nano /etc/postgresql/version/main/postgresql.conf`
   - Donde **version** es la versión del PostgreSQL, si es la 11, el directorio
   se llamará 11.
- En la línea 63 se encuentra una sentencia que dice **port = 5432**:
   ```
   #------------------------------------------------------------------------------
   # CONNECTIONS AND AUTHENTICATION
   #------------------------------------------------------------------------------

   # - Connection Settings -

   #listen_addresses = 'localhost'     # what IP address(es) to listen on;
                  # comma-separated list of addresses;
                  # defaults to 'localhost'; use '*' for all
                  # (change requires restart)
   port = 5432    # (change requires restart)
   ```
- Cambiar el 5432 por el puerto de salida que se necesite.
- Reiniciar el servicio
   - `service postgresql restart`

### Cambiar el puerto de PostgreSQL en Phppgadmin
- El archivo de configuración del puerto de Phppgadmin se encuentra en:
   - `# nano /etc/phppgadmin/config.inc.php`
- Bajo el comentario _"Database port on server (5432 is the PostgreSQL default)"_
está el puerto:
   <img src="../img/puertos3.png" alt="puerto Phppgadmin">
- Cambiar el 5432 por el puerto de salida que se haya configurado para PostgreSQL.


## MySQL
- El puerto de salida por defecto de MySQL es el **3306**

### Configurar un puerto distinto
- El archivo de configuración del puerto de MySQL se encuentra en:
   - `# nano /etc/mysql/mariadb.conf.d/50-server.cnf`
- En la línea 19 se encuentra una sentencia que dice **port = 3306**:
- Entre las primeras líneas se encuentra una sentencia que dice ****:
   ```
   # this is only for the mysqld standalone daemon
   [mysqld]

   #
   # * Basic Settings
   #
   user                    = mysql
   pid-file                = /run/mysqld/mysqld.pid
   socket                  = /run/mysqld/mysqld.sock
   port                    = 3306
   ```
- Cambiar el 80 por el puerto de salida que se necesite.
- Reiniciar el servicio
   - `service mysqld restart`