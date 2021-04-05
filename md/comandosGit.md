# Guía de utilización de GIT
Centro Nacional de Desarrollo e Investigación de Tecnologías Libres (CENDITEL) <br>
[CENDITEL](https://www.cenditel.gob.ve/), Mérida - Venezuela<br>
Dirección de Desarrollo<br>
Autor: [Ing. Angelo Osorio](https://twitter.com/Engel_PAIN)<br>
Fecha de Elaboración: 05-09-2017 (dd,mm,aaaa)


## Notas del autor
>El símbolo al principio de una línea de comandos indica:
```
   $ = hacer la sentencia como usuario
   # = hacer la sentencia como administrador
```


## Índice
1. [Guía rápida](#forma-corta-de-commitear-y-subir-cambios)
1. [Gestión de Usuario](#gestión-de-usuario)
1. [Crear un repositorio](#crear-un-repositorio)
1. [Clonar un repositorio](#clonar-un-repositorio)
1. [Sincronización](#sincronización)
1. [Añadir cambios](#añadir-cambios)
1. [Desechar cambios](#desechar-cambios)
1. [Commit](#commit)
1. [Ramas](#ramas)
1. [Repositorios remotos alternativos](#repositorios-remotos-alternativos)


## Guía rápida
1. Añadir cambios: `$ git add .` (En referencia al directorio actual)
2. Nota descriptiva de los cambios realizados: `$ git commit -m "Descripción del commit"`
3. Subir los archivos al repositorio: `$ git push`


## Gestión de Usuario
* Configurar **username**:
   * Global: `$ git config --global user.name "Angelo Osorio"`
   * Solo en el repositorio: `$ git config user.name "Angelo Osorio"`
* Configurar **correo**:
   * Global: `$ git config --global user.email sample@example.com`
   * Solo en el repositorio: `$ git config user.email sample@example.com`
* Configurar **editos**:
   * Global: `$ git config --global core.editor "nombreeditor"`
   * Solo en el repositorio: `$ git config core.editor "nombreeditor"`
* Almacenar sus credenciales de inicio de sesión en Git:
   * Modo **caché** (almacena las credenciales por 15 minutos):
      * `$ git config --global credential.helper cache`
   * Modo **store** (almacena las credenciales en un archivo, sin límite de tiempo):
      * `$ git config --global credential.helper store --file ~/.mis-credenciales`
* Mostrar configuración actual: `$ git config -l`


## Crear un repositorio local
1. Crear un directorio: `$ mkdir prueba`
2. Entrar al directorio: `$ cd prueba`
3. Dentro del directorio ejecutar el comando para iniciar un repositorio: `$ git init`
4. Añada la ruta del repositorio remoto: `$ git remote git://sub.dominio.com/repo.git`


## Clonar un repositorio
* Clonar un repositorio: `$ git clone git://sub.dominio.com/repo.git`
* Clonar solo una rama específica del repositorio: `$ git clone -b mybranch git://sub.dominio.com/repo.git`
* Clonar un repositorio en un directorio: `$ git clone git://sub.dominio.com/repo.git nombredeldirectorio`


## Sincronización
* Revisar si hay cambios en el repositorio: `$ git pull`
* Revisar el estado de una rama:
   * Forma normal: `$ git status`
   * Forma simplificado: `$ git status -s`
* Descargar cambios con conflictos en la rama
   1. Guardar los cambios que se tienen pendientes: `$ git stash`
   2. Solicitar los cambios de la rama: `$ git pull`
   3. Incorporar los cambios pendientes sobre los recién descargados: `$ git stash pop`


## Añadir cambios
* Añadir todos los archivos del directorio:
   * Forma 1: `$ git add --all`
   * Forma 2: `$ git add *`
   * Forma 3: `$ git add .` (En referencia al directorio actual)
* Añadir archivos específicos:  `$ git add rutarelativa/archivo.extension`
* Añadir todos los archivos con una extensión específica: `$ git add *.extensión`
* Añadir todos los archivos que comiencen con 'fil': `$ git add fil*`


## Desechar cambios
* De un archivo: `$ git checkout -- <file>`
* Todos los archivos: `$ git reset --hard`


## Commit
* Commitear cambios
   * Forma normal: `$ git commit`
   * Forma simplificada: `$ git commit -m "mensaje"`
* Arreglar el mensaje del último commit: `$ git commit --amend`
* Deshacer el último commit (pushed): `$ git reset --soft HEAD~1`


## Ramas
* Cambiar de rama: `$ git checkout rama`
* Crear una rama: `$ git checkout -b nuevarama`
* Cambiar de rama: `$ git checkout rama`
* Volver a un commit anterior: `$ git checkout commit-id`


## Repositorios remotos alternativos
* Agregar repositorio alternativo: `$ git remote add backup git://sub.dominio.com/repo.git`
* Bajar cambios del repositorio alternativo: `$ git pull backup rama`
* Subir cambios al repositorio alternativo: `$ git push backup rama`