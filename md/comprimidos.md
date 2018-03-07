# Archivos Comprimidos
Centro Nacional de Desarrollo e Investigación de Tecnologías Libres (CENDITEL) <br>
[CENDITEL](https://www.cenditel.gob.ve/), Mérida - Venezuela<br>
Dirección de Desarrollo<br>
Autor: [Ing. Angelo Osorio](https://twitter.com/Engel_PAIN)<br>
Fecha de Elaboración: 05-09-2017 (dd,mm,aaaa)

## Operaciones con Archivos comprimidos

**Formato** ||          **Comprimir**         ||   **Descomprimir**  || **Ver contenido sin descomprimir**
     TAR    || $ tar cvf archivo.tar archivo/ || tar xvf archivo.tar || $ tar tvf archivo.tar

## Formato TAR:
* Comprimir un directorio o archivo: `$ tar cvf archivo.tar archivo/`
* Descomprimir: `$ tar xvf archivo.tar`
* Ver contenido, sin descomprimir: `$ tar tvf archivo.tar`

## Formato TAR.GZ:
* Comprimir un directorio o archivo: `$ tar czvf archivo.tar.gz archivo/`
* Descomprimir: `$ tar xzvf archivo.tar.gz`
* Ver contenido, sin descomprimir: `$ tar tzvf archivo.tar.gz`

## Formato TAR.Z:
* Comprimir un directorio o archivo: `$ tar czvf archivo.tar.z archivo/`
* Descomprimir: `$ tar xzvf archivo.tar.z`
* Ver contenido, sin descomprimir: `$ tar tzvf archivo.tar.z`


## Formato TGZ:
* Comprimir un directorio o archivo: `$ tar czvf archivo.tgz archivo/`
* Descomprimir: `$ tar xzvf archivo.tgz`
* Ver contenido, sin descomprimir: `$ tar tzvf archivo.tgz`


## Formato TGZ:
* Comprimir un directorio o archivo: `$ tar czvf archivo.tgz archivo/`
* Descomprimir: `$ tar xzvf archivo.tgz`
* Ver contenido, sin descomprimir: `$ tar tzvf archivo.tgz`


## Formato TAR.BZ2:
Comprimir un directorio o archivo:
  $ tar -c archivos | bzip2 > archivo.tar.bz2
Descomprimir:
  $ bzip2 -dc archivo.tar.bz2 | tar -xv
- Versiones recientes de tar
  $ tar jvxf archivo.tar.bz2

Ver contenido, sin descomprimir:
  $ bzip2 -dc archivo.tar.bz2 | tar -tv


## Formato ZIP:
Comprimir un directorio o archivo
  $ zip archivo.zip archivo/*
Descomprimir
  $ unzip archivo.zip
Ver contenido, sin descomprimir
  $ unzip -v archivo.zip


## Formato RAR:
Comprimir un directorio o archivo
  $ rar a archivo.rar /mayo/archivos
Descomprimir
  $ rar x archivo.rar
Ver contenido, sin descomprimir
Forma 1: $ rar v archivo.rar
Forma 2: $ rar l archivo.rar