# Guía de utilización de GIT
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



## Gestión de Usuario
* Asignar el nombre de usuario para cada commit:
   * `$ git config --global user.name "username"`
* Asignar el correo para cada commit:
   * `$ git config --global user.email sample@example.com`
* Mostrar los datos de usuario que están configurados
   * `$ git config -l`



## Crear un repositorio
1. Crear un directorio
   * `$ mkdir prueba`
2. Entrar al directorio
   * `$ cd prueba`
3. Dentro del directorio ejecutar el comando para iniciar un repositorio:
  * `$ git init`
4. Añada la ruta del repositorio remoto
   * `git remote git://sub.domain.com/repo.git`



## Clonar un repositorio
1. Ir a la dirección donde se clonará el repositorio
   * `$ cd directorio/destino`
2. Buscar el repositorio a clonar:
   * `$ git clone git://sub.domain.com/repo.git`

### Clonar solo una rama específica del repositorio
* `$ git clone -b mybranch --single-branch git://sub.domain.com/repo.git`



## Subir archivos a un repositorio
1. Añadir cambios:
   1. Añadir todos los archivos del directorio:
      * Forma 1: `$ git add --all`
      * Forma 2: `$ git add *`
   2. Añadir archivos específicos:
      * `$ git add archivo.extension`
   3. Añadir todos los archivos con una extensión específica:
      * `$ git add *.extensión`
2. Describir el commit de los cambios realizados:
   * `$ git commmit -m "Descripción del commit"`
3. Subir los archivos al repositorio
   * `$ git push origin master`



## Sincronización
* Revisar si hay cambios en el repositorio:
   * `$ git pull`
* Revisar el estado de una rama:
   * `$ git status`
* Revisar el estado de una rama (simplificado):
   * `$ git status -s`

### Descargar cambios con conflictos en la rama
* Guardar los cambios que se tienen pendientes:
   * `$ git stash`
* Solicitar los cambios de la rama:
   * `$ git pull`
* Incorporar los cambios pendientes sobre los recién descargados:
   * `$ git stash pop`


## Ramas
* Crear una rama:
   * `$ git checkout -b nuevarama`
* Cambiar de rama:
   * `$ git checkout rama`