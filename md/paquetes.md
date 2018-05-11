# Paquetes varios útiles
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

## Cambiar repositorios en Debian
* Para agregar o remover repositorios se debe modificar el archivo `source.list` ubicado en la ruta
`/etc/apt/source.list`
* Así se modificaría desde la consola utilizando el editor nano:
   * `# nano /etc/apt/sources.list`


## Aptitude
* Aptitude es un manejador de interfaz de alto nivel para la gestión de paquetes, es la versión
mejorada de apt-get, por tanto es mejor para buscar resultados en los repositorios. Se debe instalar
aptitude si se quiere utilizar la búsqueda que explica el siguiente punto.
* Para verificar los paquetes disponibles en el repositorio se utiliza:
```
   # aptitude search nombreDelPaquete
```
* La búsqueda arrojará todos los paquetes disponibles en el repositorio con una letra antepuesta, ésta
tiene los siguientes significados:
```
p   Paquete disponible en el repositorio
i   Paquete instalado en la máquina
i A Paquete instalado por solicitud de otro paquete que se intaló o se instalará
v   Paquete virtual
c   Paquete corrupto
```
* Utilizando aptitude search y ~x (donde x es la letra que determina la disponibilidad del paquete,
que se mostró en el paso anterior)
* Ejemplos:
   * Mostrar todos los paquetes corruptos del sistema:
      * `# aptitude search ~c`
   * Mostrar todos los paquetes instalados del sistema:
      * `# aptitude search ~i`
   * Utilizando el comando grep se puede reducir la búsqueda aún más:
      * `# aptitude search ~c | grep ejemplo`
      * mostrarán todos los paquetes corruptos del sistema que tengan como nombre ejemplo



## Instalación de paquetes
* Para instalar un paquete se utiliza:
   * Forma 1: `# apt-get install nombreDelPaquete`
   * Forma 2: `# apt install nombreDelPaquete`
   * Forma 3: `# aptitude install nombreDelPaquete`

>Es conveniente realizar primero la búsqueda del paquete para saber si está disponible en el
repositorio antes de instalarlo, dado que no se puede instalar lo que no está disponible.

* Para instalar un paquete descargado y que sea de extensión .deb (paquete debian) se utiliza el 
paquete dpkg, que es el instalador de debian, con la siguiente sentencia:
   * `# dpkg -i nombreDelPaquete.deb`

* El -i es de instalar, también se puede utilizar -install en lugar de -i
* dpkg también sirve para desinstalar usando -r o -remove
* Y para verificar si ya está instalado el paquete usando -l | grep 'nombreDelPaquete'

* Instalar un paquete con dpkg:
   * `# dpkg -i paquete.deb`

* Desinstalar un paquete con dpkg:
   * `# dpkg -r paquete.deb`

* Verificar un paquete con dpkg:
   * `# dpkg -l | grep 'Chrome'`

## Desinstalar de paquetes
* Para desinstalar un programa instalado a través de la consola se usa el comando:
   * `# aptitude remove nombreDelPaquete`
   * `# apt-get remove nombreDelPaquete `

* Luego de ello siempre es bueno utilizar el comando para liberar el espacio del disco:
   * `# aptitude autoclean`
   * `# apt-get autoremove`


## Paquetes Útiles
* aptitude: Gestor de archivos mejor a apt y apt-get
* sudo: Utilizado para darle permisos de superusuario al usuario que inició sesión
* screenfetch: Imprime en consola el logo del sistema operativo y las caracteristicas del equipo
* terminator: Terminal con buenas características para codificación ágil
* vim: Editor de texto en consola
* youtube-dl: Descarga videos de YouTube en una variedad de formatos


## Screenfetch
Crea una imagen en la consola con una descripción de los requerimientos del sistema.

* Instalar el paquete:
   * `# aptitude install screenfetch`
* Utilizar screenfetch
   * `$ screenfetch`
* Mostrar el logo de screenfetch omitiendo errores
   * `$ screenfetch -E`
* Simular que se está utilizando una distro distinta:
   * `$ screenfetch -D 'Nombre Distro linux'`
   * Por ejemplo: `$ screenfetch -D 'fedora'` mostraría un gráfico de Fedora.