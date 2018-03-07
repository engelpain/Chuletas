# Cómo crear una página en GitHub
Centro Nacional de Desarrollo e Investigación de Tecnologías Libres (CENDITEL) <br>
[CENDITEL](https://www.cenditel.gob.ve/), Mérida - Venezuela<br>
Dirección de Desarrollo<br>
Autor: [Ing. Angelo Osorio](https://twitter.com/Engel_PAIN)<br>
Fecha de Elaboración: 05-09-2017 (dd,mm,aaaa)

1. Crea un repositorio en GitHub llamado *username.github.io* cambiando *username* por el nombre de usuario que se posee en GitHub
2. Clonar el repositorio que se creó: `$ git clone https://github.com/username/username`
3. Entrar en el directorio que se clonó: `$ cd username.github.io`
4. Crear un archivo index.html: `$ echo "Hello World" > index.html`
5. Agregue, comente y haga push de los cambios:
```shell
   $ git add --all
   $ git commit -m "Commit Inicial"
   $ git push -u origin master
```
6. El sitio está terminado, ahora accesa a *username.github.io*