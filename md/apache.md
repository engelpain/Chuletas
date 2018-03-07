# Guía para instalar y manipular Apache2 en Debian
Centro Nacional de Desarrollo e Investigación de Tecnologías Libres (CENDITEL) <br>
[CENDITEL](https://www.cenditel.gob.ve/), Mérida - Venezuela<br>
Dirección de Desarrollo<br>
Autor: [Ing. Angelo Osorio](https://twitter.com/Engel_PAIN)<br>
Fecha de Elaboración: 05-09-2017 (dd,mm,aaaa)

## Notas del autor
El símbolo al principio de una línea de comandos indica:
```
   $ = hacer la sentencia como usuario
   # = hacer la sentencia como administrador
```

## Instalar Apache
Para instalar apache se utiliza el comando:
```
   # apt-get install apache2
```

## Controlar Apache
* Iniciar proceso:
   * Forma 1: `# service apache2 start`
   * Forma 2: `# systemctl start apache2`
   * Forma 3: `# /etc/init.d/apache2 start`
* Reiniciar proceso:
   * Forma 1: `# service apache2 restart`
   * Forma 2: `# systemctl restart apache2`
   * Forma 3: `# /etc/init.d/apache2 restart`
* Detener proceso:
   * Forma 1: `# service apache2 stop`
   * Forma 2: `# systemctl stop apache2`
   * Forma 3: `# /etc/init.d/apache2 stop`
* Estado del proceso
   * Forma 1: `# service apache2 status`
   * Forma 2: `# systemctl status apache2`
   * Forma 3: `# /etc/init.d/apache2 status`


## mod_rewrite en Apache
1. Para activar el módulo Rewrite de apache se utiliza el siguiente comando: `# a2enmod rewrite`
2. Modificar el archivo `apache2.conf`. Se puede modificar tanto desde la consola como desde un editor de texto, siempre y cuando se tenga permiso de superusuario, en este caso se usará nano, editor de texto desde la consola: `# nano /etc/apache2/apache2.conf`
3. Ahora se debe buscar la línea dentro del archivo que dice *AllowOverride None*. En caso de encontrar más de una, buscar la que tiene el directorio donde se alojan los archivos del servidor local, *www* en mi caso:
```
<Directory /var/www/>
   Options Indexes FollowSymLinks
   AllowOverride None <-- Esta línea es la que se debe cambiar
   Require all granted
</Directory>
```
4. Ahora se cambia *None* por *All*
```
<Directory /var/www/>
   Options Indexes FollowSymLinks
   AllowOverride All <-- Así
   Require all granted
</Directory>
```
5. Se guarda el archivo
6. Luego se debe reiniciar el apache: `# service apache2 restart`
7. Ya se pueden usar las urls limpias