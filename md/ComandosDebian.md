# Guía de comandos útiles en Debian y algunas distros linux en general

## Notas del autor
El símbolo al principio de una línea de comandos indica:
```
$ = usar el comando como usuario
# = usar el comando como administrador
```

## Comandos básicos de consola
* `$ pwd`: Muestra la ruta actual
* `$ ls`: Listar archivos
* `$ ls -l`: Listar directorios y archivos detallado
* `$ ls -a`: Listar directorios y archivos incluyendo ocultos
* `$ ls -la`: Listar directorios y archivos detallado incluyendo ocultos
* `$ cd nombredirectorio`: Cambiar al directorio "nombredirectorio"
* `$ du -sh *`: Muestra el peso de los archivos del directorio

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

## Gestionar unidades externas
1. Para montar una unidad externa o directorio, por ejemplo un pendrive, se utiliza el comando:
- `$ mount /media/usuario/nombreunidad`
> El comando *mount* también sirve para montar directorios dentro de sistemas enjaulados.

2. Para expulsar una unidad externa, por ejemplo un pendrive, se utiliza el comando:
- `$ umount /media/usuario/nombreunidad`
> De igual forma a *mount*, *umount* sirve para desmontar directorios de jaulas.


### Crear comandos personalizados en Debian
> **Nota Importante:**
Debian posee dos archivos .bashrc, uno del usuario y otro de root, dependiendo del usuario con el que se quiera ejecutar ese alias se debe modificar el .bashrc como usuario o como root. Se utiliza la expresión *~/* para referirse al bashrc del usuario activo, si está activo el usuario root, se modificará el bashrc que se encuentra en /root, si en cambio es un usuario común, entonces se modificará el que se encuentra en /home/usuario

1. Para personalizar un comando en Debian se debe modificar el archivo *~/.bashrc* con un editor de texto, por ejemplo: nano, vi o vim, en este caso se usará nano:
- `$ nano ~/.bashrc`

2. Dentro del archivo (por lo general al final) se debe agregar el comando/acción que se desea crear:
- `alias palabra_corta='comando palabras o ruta a ejecutar'`

### Recursos del sistema
Para mostrar los recursos que ese están utilizando en el sistema se utiliza el comando:
`$ top`

**Top pero en tiempo real**
```
# aptitude install htop
$ htop
```

**Otra versión en tiempo real de top**
```
# aptitude install gotop
$ gotop
```

**Liberar espacio en la memoria RAM**
- `# sysctl -w vm.drop_caches=3`

## Listar usuarios y grupos
* Listar usuarios del sistema: `$ cat /etc/passwd`
* Listar grupos del sistema: `$ cat /etc/group`

## Listar paquetes instalados
- `grep " install " /var/log/dpkg.log`

## Trucos en terminal
Para repetir la última sentencia de un comando en específico utilizada anteriormente, basta con
typear: Signo de exclamación + las primeras dos letras del comando.

* Ejemplo 1: digamos que el último comando de un paquete como *python* fue:
`$ python manage.py runserver 0.0.0.0:8080`.
   - Si luego se paró el comando para realizar otros comandos que no tienen que ver con python, y se
   requiere reutilizar el comando de python, no hay que reescribirlo, bastará con: `$ !py`. La
   consola automáticamente lo interpreterá como el último comando con los parámetros incluidos.
* Ejemplo 2: Un comando de aptitude como: `$ aptitude search ~c` bastaría con `$ !ap`.
* Ejemplo 3: Un comando de screenfetch como: `$ screenfetch -D 'Fedora'` bastaría con `$ !sc`.
* Ejemplo 4: Habiendo usado el comando para apagar el equipo: `# shutdown -h now` bastaría con `# !sh`.
> Nota: No es necesario que sean solamente dos letras, se puede escribir el nombre completo en caso que
> se hayan usado comandos que comiencen con las mismas letras, un ejemplo sería *aptitude* y *apt-get*.
* Para repetir el último comando que se ha usado en la terminar basta con usar `!!`.

## Find: Encontrar archivos
Find es el comando por antonomasia para encontrar archivos, su nomenclatura más sencilla es la siguiente:
- `find [ruta] [criterio] [acción]`
   - Ruta: La ruta específica donde se buscará.
   - Criterio: nombre, cadena, extensión, peso, entre otros, que se desean buscar. Se puede introducir el nombre del archivo específico o también agregar * como comodines:
      - "*.txt": Busca cualquier archivo que termine en .txt, sin importar cómo se llame al principio.
      - "informe*": Busca cualquier archivo que comience con la palabra "informe", sin importar su extensión.
      - "*2026*": Busca cualquier archivo que contenga "2026" en cualquier parte de su nombre.
   - Acción: Que acción realizar con los archivos que coincidan con el criterio.

Ejemplo práctico:
- `find /ruta/ -name "*cadena*"`
> Protección con comillas: Si escribes find . -name *cadena* sin comillas, la terminal intentará resolver el comodín localmente primero. Si usas "*cadena*" entre comillas, el comodín se envía directamente al comando find para que busque en las subcarpetas.

## Determinar la pantalla de login del entorno de escritorio
* `# dpkg-reconfigure gdm` en caso que **gdm** sea su entorno predeterminado.
* `# dpkg-reconfigure lightdm` en caso que **lightdm** sea su entorno predeterminado

## Administrar una red
* Apagar una conexión: `# ip link set nombredelared down`.
* Encender una conexión: `# ip link set nombredelared up`.
> Normalmente las redes de tipo cableadas usan un nombre parecido a **eth0**, y las redes inalámbricas uno similar a **wlan0**, donde 0 significa que es la primera.
