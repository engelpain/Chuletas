## Sass
Centro Nacional de Desarrollo e Investigación de Tecnologías Libres (CENDITEL) <br>
[CENDITEL](https://www.cenditel.gob.ve/), Mérida - Venezuela<br>
Dirección de Desarrollo<br>
Autor: [Ing. Angelo Osorio](https://twitter.com/Engel_PAIN)<br>
Fecha de Elaboración: 26-12-2017 (dd,mm,aaaa)


### Compilar un archivo en Sass desde la consola
> Para sistemas Windows con instalación de Ruby mínima primero se debe correr primero el bat de las
variables de Ruby

```  
C:\Ruby\bin\setrbvars.bat
```  

* Compilar un archivo
   * `sass origen.scss:destino.css`
* Compilar un archivo cada vez que tenga un cambio
   * Se agrega la directiva *--watch* al comando:
      * `sass --watch origen.scss:destino.css`
* Compilar un archivo en formato específico
   * Se agrega la directiva *--style* y tipo de formato (compressed, nested, expanded) al comando:
   * Para forma formatos minificados:
      * `sass --style compressed origen.scss:destino.css`
   * Para forma formatos anidados:
      * `sass --style nested origen.scss:destino.css`
   * Para forma formatos expandidos:
      * `sass --style expanded origen.scss:destino.css`
* Compilación recomendada para archivos en producción:
   * `sass --watch origen.scss:destino.min.css --style compressed`