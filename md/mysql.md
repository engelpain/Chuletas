## MySQL
Centro Nacional de Desarrollo e Investigación de Tecnologías Libres (CENDITEL) <br>
[CENDITEL](https://www.cenditel.gob.ve/), Mérida - Venezuela<br>
Dirección de Desarrollo<br>
Autor: [Ing. Angelo Osorio](https://twitter.com/Engel_PAIN)<br>
Fecha de Elaboración: 28-03-2018 (dd,mm,aaaa)

* Crear una base de datos
   * `CREATE DATABASE nombreBasedeDatos;`
* Cambiar a una base de datos
   * `USE nombreBasedeDatos`
* Crear una tabla
   * `CREATE TABLE nombreTabla(dato1 INT PRIMARY KEY AUTO_INCREMENT, dato2 VARCHAR(20), dato3 CHAR(1), dato4 DATE);`
* Ver los campos de una tabla
   * `DESCRIBE nombreTabla;`
* Insertar datos en una tabla (CREATE)
   * `INSERT INTO nombreTabla VALUES(NULL, 'Pelusa', 'Diana', 'Hamster', 'f', '2000-03-30',NULL);`
* Recuperar datos de una tabla (READ)
   * `SELECT LaInformaciónQueDeseamos FROM DeQueTabla WHERE CondiciónASatisfacer;`
* Eliminar todos los datos de una tabla (DELETE)
   * `TRUNCATE TABLE nombreTabla;`
* Eliminar datos específicos de una tabla (DELETE)
   * `DELETE FROM nombreTabla WHERE condicion;`
* Importar el archivo
   * `mysql –u usuario_mysql -p nombre_bbdd < ruta_fichero_importación.sql`
* Exportar el archivo
   * `mysqldump –u usuario_mysql -p nombre_bbdd > fichero_exportación.sql`
