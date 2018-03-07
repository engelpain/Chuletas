# Guía para aprender comandos de Debian
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

## Gestionar Servicios
* Iniciar un servicio:
   * Forma 1: `# systemctl start servicio`
   * Forma 2: `# /etc/init.d/servicio start`
   * Forma 3: `# service servicio start`

* Reiniciar un servicio:
   * Forma 1: `# systemctl restart servicio`
   * Forma 2: `# /etc/init.d/servicio restart`
   * Forma 3: `# service servicio restart`

* Detener un servicio:
   * Forma 1: `# systemctl stop servicio`
   * Forma 2: `# /etc/init.d/servicio stop`
   * Forma 3: `# service servicio stop`

* Revisar el estado de un servicio:
   * Forma 1: `# systemctl status servicio`
   * Forma 2: `# /etc/init.d/servicio status`
   * Forma 3: `# service servicio status`

* Revisar si está activo un servicio:
   * `# systemctl is-active servicio`


### Gestionar unidades externas
Para montar una unidad externa o directorio, por ejemplo un pendrive, se utiliza el comando:
```
  $ mount /media/usuario/nombreunidad
```
El comando *mount* también sirve para montar directorios dentro de sistemas enjaulados.

Para expulsar una unidad externa, por ejemplo un pendrive, se utiliza el comando:
```
  $ umount /media/usuario/nombreunidad
```
De igual forma a *mount*, *umount* sirve para desmontar directorios de jaulas.


### Crear comandos personalizados en Debian
> Nota Importante:
Debian posee dos archivos .bashrc
Uno del usuario y otro de root, dependiendo del usuario con el que se quiera ejecutar ese alias se debe modificar el .bashrc como usuario o como root.
Se utiliza la expresión ~/ para referirse al bashrc del usuario activo, si está activo el usuario root, se modificará el bashrc que se encuentra en /root, si en cambio es un usuario común, entonces se modificará el que se encuentra en /home/usuario

Para personalizar un comando en Debian se debe modificar el archivo ~/.bashrc con un editor de texto, por ejemplo: nano, vi o vim, en este caso se usará nano:
```
  $ nano ~/.bashrc
```
Dentro del archivo al final hay que agregar:
```
  alias palabra_corta='comando palabras o ruta a ejecutar'
```

### Recursos del sistema
Para mostrar los recursos que ese están utilizando en el sistema se utiliza el comando:
```
  $ top
```

**Top mejorado**
```
  # aptitude install htop
  $ htop
```

**Liberar espacio en la memoria RAM**
```
  # sysctl -w vm.drop_caches=3
```

## Listar usuarios y grupos

* Listar usuarios del sistema: `$ cat /etc/passwd`
* Listar grupos del sistema: `$ cat /etc/group`