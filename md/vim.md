# Guía de utilización de VIM
Centro Nacional de Desarrollo e Investigación de Tecnologías Libres (CENDITEL) <br>
[CENDITEL](https://www.cenditel.gob.ve/), Mérida - Venezuela<br>
Dirección de Desarrollo<br>
Autor: [Ing. Angelo Osorio](https://twitter.com/Engel_PAIN)<br>
Fecha de Elaboración: 20-11-2017 (dd,mm,aaaa)

## Notas del autor
El símbolo al principio de una línea de comandos indica:
```
  $ = hacer la sentencia como usuario
  # = hacer la sentencia como administrador
```

## Instalar / Desinstalar VIM
* Instalar VIM  `# apt-get install vim`
* Desinstalar VIM  `# apt-get remove vim`

## Ejecutar VIM
* Ejecutar vim: `$ vim`
* Abrir un archivo con vim: `$ vim /ruta/archivo.extensión`

## Comando VIM
VIM posee dos modos de operación, *modo comandos* y *modo de inseción de texto*, por defecto se entra en *modo de comandos*.

### Comandos en modo de inseción de texto:
* Entrar en modo de inserción de texto:
   * Presionar la tecla **i**
* Salir del modo del modo de edición (Entrar en modo de comandos):
   * Presionar la tecla **Esc**

### Comandos en modo comandos:
* Guarda los cambios sin salir del editor: **:w**
* Salir del editor, sólo si no hubieron cambios en el mismo: **:q**
* Salir sin guardar cambios: **:q!**
* Guardar y salir
   * Forma 1: **:wq**
   * Forma 2: **:x**
   * Forma 2: **ZZ** <- (Shift + z) dos veces

* Moverse por el documento:
   * Mueve el cursor hacia arriba: **k** o **flecha arriba**
   * Mueve el cursor hacia abajo: **j** o flecha abajo
   * Mueve el cursor a la izquierda: **h** o flecha izquierda
   * Mueve el cursor a la derecha: **l** o flecha a la derecha
   * Lleva el cursor al final de la palabra actual: **e**
   * Al final de una palabra delimitada por espacios: **E** <- (Shift + e)
   * Al inicio de una palabra: **b**
   * Al inicio de una palabra delimitada por espacios: **B** <- (Shift + b)
   * Al inicio de la línea: **O** <- (Shift + o)
   * Al primer caracter de una línea que no sea un espacio: **^**
   * Al final de la línea: **$**
   * A la primer línea de la pantalla: **H** <- (Shift + h)
   * A la línea al medio de la pantalla: **M** <- (Shift + m)
   * A la última línea de la pantalla: **L** <- (Shift + l)
   * Salta a la línea n, donde n, es un número entero: **:n**
      * Por ejemplo, para saltar a la línea 13: **:13**