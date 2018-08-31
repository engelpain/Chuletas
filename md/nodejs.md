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

### Requisitos
* Tener *curl* instalado, caso contrario:
   * `# aptitude install curl`

### Instalar NodeJS en Debian (o distribuciones basadas en Debian)
1. `$ curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -`
2. `# apt-get install -y nodejs`

### Comandos en NodeJS
* Ver la versión de Node
   * $ nodejs -v
* Ver la versión de npm
   * $ npm -v