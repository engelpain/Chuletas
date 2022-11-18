# Guía de NodeJS
Centro Nacional de Desarrollo e Investigación de Tecnologías Libres (CENDITEL) <br>
[CENDITEL](https://www.cenditel.gob.ve/), Mérida - Venezuela<br>
Dirección de Desarrollo<br>
Autor: [Ing. Angelo Osorio](https://twitter.com/Engel_PAIN)<br>
Fecha de Elaboración: 31-08-2018 (dd,mm,aaaa)


## Notas del autor
El símbolo al principio de una línea de comandos indica:
```
   $ = hacer la sentencia como usuario
   # = hacer la sentencia como administrador
```

## Instalación:
### Forma 1: Descargar e instalar desde su página web
* Se puede instalar NodeJS descargándolo e instalando el archivo desde este [enlace](https://nodejs.org/es/download/current/).

### Forma 2: Instalar NodeJS en Debian (o distribuciones basadas en Debian)
#### Requisitos para este tipo de instalación:
* Tener *curl* instalado, caso contrario instalarlo:
   * `# apt install curl`
#### Pasos para instalarlo
1. `$ curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -`
2. `# apt install -y nodejs`

### Forma 3: Instalar NodeJS con NVM
> Nota: NVM Es un gestor de instalación que permite instalar más de un NodeJS. Para ver el repositorio original puede seguir este [enlace](https://github.com/nvm-sh/nvm).

#### Instalación única
1. `$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.2/install.sh | bash`
2. `$ nvm install node`

#### Instalación múltiple
Para instalar más de una versión solamente hace falta especificar qué versión se requiere.
Usando `$ nvm install 8.0.0` se instalaría la versión 8.0.0 de NodeJS, y esta convivirá sin problemas con la instalación
del paso anterior.

#### Selección
* `$ nvm use número`: Cambia a la versión **número** de Node.

#### Listar versiones instaladas
*  `$ nvm ls`

### Comandos en NodeJS
* Ver la versión de Node
   * $ nodejs -v
* Ver la versión de npm
   * $ npm -v
