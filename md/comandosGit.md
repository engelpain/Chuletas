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
1. [Guía rápida](#guía-rápida)
1. [Gestión de Usuario](#gestión-de-usuario)
1. [Crear un repositorio local](#crear-un-repositorio-local)
1. [Clonar un repositorio](#clonar-un-repositorio)
1. [Sincronización](#sincronización)
1. [Añadir cambios](#añadir-cambios)
1. [Ver cambios](#ver-cambios)
1. [Desechar cambios](#desechar-cambios)
1. [Commit](#commit)
1. [Logs](#logs)
1. [Ramas](#ramas)
1. [Fusión de ramas](#fusi%C3%B3n-de-ramas)
1. [Etiquetas](#etiquetas)
1. [Repositorios remotos alternativos](#repositorios-remotos-alternativos)


## Guía rápida
1. Siempre hacer pull antes de subir cualquier cambio (nadie quiere borrar el trabajo de otros): `$ git pull"`
2. Añadir cambios: `$ git add .` (En referencia al directorio actual)
3. Nota descriptiva de los cambios realizados: `$ git commit -m "Descripción del commit"`
4. Subir los archivos al repositorio: `$ git push`


## Gestión de Usuario
* Configurar **Nombre del usuario**: `$ git config user.name "Angelo Osorio"`
* Configurar **correo electrónico**: `$ git config user.email sample@example.com`
* Configurar **editos**: `$ git config core.editor "nombreeditor"`
* Almacenar sus credenciales de inicio de sesión en Git:
   * Modo **caché** (almacena las credenciales por 15 minutos):
      * `$ git config credential.helper cache`
   * Modo **store** (almacena las credenciales en un archivo, sin límite de tiempo):
      * `$ git config credential.helper store --file ~/.mis-credenciales`
   * Modo **store** (almacena las credenciales en el gestor interno del sistema operativo, sin límite de tiempo):
      * `$ git config credential.helper store
* Mostrar configuración actual: `$ git config -l`
> Nota: para que los cambios surjan efecto global se debe usar el _flag_ **--global**).


## Crear un repositorio local
1. Crear un directorio: `$ mkdir prueba`
2. Entrar al directorio: `$ cd prueba`
3. Dentro del directorio ejecutar el comando para iniciar un repositorio: `$ git init`
4. Añada la ruta del repositorio remoto: `$ git remote git://sub.dominio.com/repo.git`


## Clonar un repositorio
* Clonar un repositorio: `$ git clone git://sub.dominio.com/repo.git`
* Clonar solo una rama específica del repositorio: `$ git clone -b mybranch git://sub.dominio.com/repo.git`
* Clonar un repositorio en un directorio: `$ git clone git://sub.dominio.com/repo.git nombredeldirectorio`
* Clonar un repositorio con x cantidad de commits tras el último: `$ git clone --depth=50 git://sub.dominio.com/repo.git`
> En este ejemplo el repositorio será clonado con los últimos 50 commits.


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
* Añadir archivos específicos:  `$ git add ruta-relativa/archivo.extension`
* Añadir todos los archivos con una extensión específica: `$ git add *.extensión`
* Añadir todos los archivos que comiencen con 'fil': `$ git add fil*`


## Ver cambios
* Cambios hechos en archivos existentes: `$ git diff`
* Comparar commits: `$ git diff commit-id-1 commit-id-2`


## Desechar cambios
* De un archivo: `$ git checkout -- <file>`
* Todos los archivos: `$ git reset --hard`


## Commit
* Commitear cambios
   * Forma normal: `$ git commit`
   * Forma simplificada: `$ git commit -m "mensaje"`
* Arreglar el mensaje del último commit: `$ git commit --amend`
* Deshacer el último commit (pushed): `$ git reset --soft HEAD~1`


## Logs
* Ver log del repositorio: `$ git log`
* Detallado (cambios en cada archivo): `$ git log -p`
* Detallado por commit específico (cambios en cada archivo): `$ git log -p hash-del-commit`

### Flags útiles
* Simplificado: `$ git log --oneline`
* Detallado (nombres de los archivos modificados): `$ git log --name-only`
* Detallado (nombres de los archivos y de cambios): `$ git log --stat`
* Todos los cambios en todas la ramas: `git log --all`
* Crear un gráfico de las ramas: `git log --graph`

### Uniones de flags útiles
* Una corta de ver el árbol de commits: `git log --oneline --all --graph`
* Forma estilizada y levemente más detallada: `git log --all --graph --pretty=short`


## Ramas
* Listar las ramas del repositorio: `$ git branch`
* Crear una rama: `$ git checkout -b nueva-rama`
* Cambiar de rama: `$ git checkout rama`
* Cambiar nombre a una rama: `$ git branch -m nombre-rama nuevo-nombre`
* Eliminar una rama: `$ git branch -d nombre-rama`

### Otros usos de git-branch y git-checkout
* Cambiar a un commit anterior: `$ git checkout commit-id`
* Configurar un repositorio remoto y rama predeterminado para su local actual: `$ git branch --set-upstream-to=origin/master master`


## Fusión de ramas
* Fusionar una rama con otra: `git merge nombre-rama`


## Etiquetas
* Crear una etiqueta: `git tag nombre-etiqueta id-commit`
* Eliminar una etiqueta: `git tag -d nombre-etiqueta`
* Listar etiquetas: `git tag`
* * Listar etiquetas específicas: ` -l "title-like*"`


## Repositorios remotos alternativos
* Agregar repositorio alternativo: `$ git remote add backup git://sub.dominio.com/repo.git`
* Bajar cambios del repositorio alternativo: `$ git pull backup rama`
* Subir cambios al repositorio alternativo: `$ git push backup rama`


## Alias
Luego de aprender todo lo que tiene git para ofrecer respecto a funcionalidades, a veces se pueden crear comandos muy largos para acciones específicas,
pero el objetivo de git es facilitar nuestra vida, no complicarla, por tanto ofrece la creación de alias para usar comandos largos sin necesidad de escribir todas las flags requeridas.

* Para crear un alias: `git config alias.nombre-alias 'comando flags'`
* Para eliminar un alias: `git config --unset alias.nombre-alias`
> Nota: para que los cambios surjan efecto global se debe usar el _flag_ **--global**).

* Un ejemplo de creación de alias: `git config alias.graph 'log --all --graph --pretty=short'`
> Nota importante: Se debe escribir los comandos siempre entre comillas simples.

Cabe destacar que cuando se invoca este alias en la consola, también se pueden agregar más flags al final. Siguiendo el ejemplo anterior se podría usar `git graph` y agregarle un flag, por ejemplo `--decorate`, para invocar al final a `git graph --decorate`, y este comando haría la suma de todos las flags del alias más la agregada después.

