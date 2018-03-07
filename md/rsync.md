# Rsync
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

Paquete utilizado para realizar copias de respaldo de archivos y/o carpetas a través de la consola mostrando en tiempo real el estado de la operación, el porcentaje de la carga y el archivo que está respaldando. También es utilizado simplemente para copiar carpetas.

### Copiar un directorio
```
  $ rsync -P -r nombrecarpeta /ruta/donde/copiará/
```
* El argumento -P es para que muestre el estado del copiado
* El argumento -r es para que sea recursivo el copiado