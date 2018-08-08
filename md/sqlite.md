## SQLite3
Centro Nacional de Desarrollo e Investigación de Tecnologías Libres (CENDITEL) <br>
[CENDITEL](https://www.cenditel.gob.ve/), Mérida - Venezuela<br>
Dirección de Desarrollo<br>
Autor: [Ing. Argenis Osorio](https://twitter.com/argenisosorio)<br>
Editor: [Ing. Angelo Osorio](https://twitter.com/Engel_PAIN)<br>
Fecha de Elaboración: 08-08-2018 (dd,mm,aaaa)


### Notas del autor
El símbolo al principio de una línea de comandos indica:
```
   $ = hacer la sentencia como usuario
   # = hacer la sentencia como administrador
```

### Instalar / Desinstalar SQLite3
* Instalar SQLite3
   * ` # apt-get install sqlite3`
* Desinstalar SQLite3
   * `# apt-get remove sqlite3`


### Entrar a SQLite3
* Forma 1: Usando el comando del programa
   * `$ sqlite3`
   * El prefijo del prompt cambiará a `sqlite>` significando que se entró con éxito a SQLite3.
* Forma 2: Abrir un archivo sqlite3 desde SQLite3
   * `$ sqlite3 nombredelarchivo.sqlite3`


### Gestion de base de datos
* Abrir una base datos desde SQLite3
   * `sqlite> .open nombre.sqlite3`
* Listar las tablas de la base de datos:
   * `sqlite> .tables`
* Ver esquema de creación de la tabla.
   * `sqlite> .schema nombretabla`
* Para salir del prompt de sqlite3
   * `sqlite> .exit`


### CRUD en SQLite3
* Agregar un registro:
   * `INSERT INTO nombre_tabla (campo1, campo2, campo3, campo4) VALUES ('Valor 1', 2, NULL, 'Valor 4');`
* Consultar todos los registros de una tabla:
   * `SELECT * FROM nombre_tabla;`
* Consultar solo registros de campos específicos:
   * `SELECT campo1, campo2 FROM nombre_tabla;`
* Consultar todos los registros de una tabla donde:
   * `SELECT * FROM nombre_tabla WHERE campo='Restricción';`
* Consultar solo registros de campos específicos donde:
   * `SELECT campo1, campo2 FROM nombre_tabla WHERE campo='Restricción';`
* Consultar datos ordenados por un campo:
   * `SELECT * FROM nombre_tabla ORDER BY campo;`
* Modificar un registro:
   * `UPDATE nombre_tabla SET campo1='Valor1', campo2=2 WHERE campo2='Dato';`
* Eliminar un registro:
   * `DELETE FROM nombre_tabla WHERE campo1='Dato';`


### Insertar datos desde un csv
* Acceder al modo csv, para poder ejecutar operaciones con estos ficheros.
   * `sqlite> .mode csv`
   * `sqlite> .import test.csv yourtable`

>Nota: Importamos los datos de el fichero .csv a la tabla especifica.
Los datos deben coincidir los campos en el .csv y en la tabla.