# PostgreSQL
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


## Instalar / Desinstalar PostgreSQL
* Instalar PostgreSQL  `# apt-get install postgresql`
* Desinstalar PostgreSQL  `# apt-get remove postgresql`


## Manipular PostgreSQL Server
* Iniciar Postgres Server:
   * `# /etc/init.d/postgresql start`
   * `# service postgresql start`
   * `# systemctl start postgresql`
* Detener Postgres Server:
   * `# /etc/init.d/postgresql stop`
   * `# service postgresql stop`
   * `# systemctl stop postgresql`
* Reiniciar Postgres Server:
   * `# /etc/init.d/postgresql restart`
   * `# service postgresql restart`
   * `# systemctl restart postgresql`
* Verificar el estado de Postgres Server:
   * `# /etc/init.d/postgresql status`
   * `# service postgresql status`
   * `# systemctl status postgresql`


## Cambiar la contraseña por defecto
1. Entrar a postgreSQL:
   * `# su postgres -c psql postgres`
2. El prompt cambiará al prefijo `postgres=#`, ahora se debe ingresar el comando:
   * `postgres=# ALTER USER postgres WITH PASSWORD 'nuevacontraseña';`
3. Cerrar PostgreSQL
   * `postgres=# \q`
4. Reiniciar PostgreSQL Server
   * `# /etc/init.d/postgresql restart`


## Entrar en PostgreSQL por consola
1. Cambiar al usuario *postgres* usando el comando `su postgres` como superusuario:
   * `# su postgres`
2. Ingresar el comando `psql`:
   * `postgres@user:/home/user$ psql`
3. El prefijo del prompt cambiará a `postgres=#`, significando que se entró con éxito a PostgreSQL.


## Comandos de PostgreSQL
* Listar las base de datos
   * `\l`
* Cambiar a la base de datos *nombre_base_de_datos*
   * `\c nombre_base_de_datos`
* Listar las tablas
   * `\d`
* Describir los campos de la tabla *nombre_tabla*
   * `\d+ nombre_tabla`
* Salir de PostgreSQL
   * `\q`


## Gestión de base de datos

### Gestionar bases de datos
* Crear una base de datos:
   * `CREATE DATABASE nombre_base_de_datos;`
* Cambiar a una base de datos:
   * `\c nombre_base_de_datos`
* Eliminar una base de datos:
   * `DROP DATABASE nombre_base_de_datos;`

### Gestionar tablas de bases de datos
>**Nota importante**: Las bases de datos, tablas y datos deben ir en minúsculas siempre.

* Crear una tabla vacía:
   * `CREATE TABLE nombre_tabla;`
* Crear una tabla con atributos:
   * `CREATE TABLE nombre_tabla (campo1 VARCHAR(30) NOT NULL UNIQUE, campo2 SERIAL NOT NULL UNIQUE PRIMARY KEY);`
* Modificar el nombre de una tabla:
   * `ALTER TABLE nombre_tabla RENAME TO nombre_nuevo_tabla;`
* Vaciar una tabla;
   * `TRUNCATE TABLE nombre_tabla;`
* Eliminar una tabla:
   * `DROP TABLE nombre_tabla;`

## Gestionar campos de una tabla
* Agregar un campo:
   * `ALTER TABLE nombre_tabla ADD nombre_campo tipo_atributo restricción_atributo;`
* Modificar un campo:
   * `ALTER TABLE nombre_tabla ALTER COLUMN nombre_campo TYPE tipo_atributo;`
* Eliminar un campo:
   * `ALTER TABLE nombre_tabla DROP COLUMN nombre_campo;`
* Campos *No nulos*:
   * Agregar la restricción *no nulo* al campo:
      * `ALTER TABLE nombre_tabla ALTER COLUMN nombre_campo SET NOT NULL;`
   * Eliminar la restricción *no nulo* al campo:
      * `ALTER TABLE nombre_tabla ALTER COLUMN nombre_campo SET NOT NULL;`
* Campos *Únicos*:
   * Agregar la restricción *único* al campo (o campos):
      * `ALTER TABLE nombre_tabla ADD CONSTRAINT MyUniqueConstraint UNIQUE(column1, column2...);`
   * Eliminar la restricción *único* al campo(s):
      * `ALTER TABLE nombre_tabla DROP CONSTRAINT MyUniqueConstraint;`
* *Llaves primarias*:
   * Agregar una llave primaria:
      * `ALTER TABLE nombre_tabla ADD PRIMARY KEY (MyPrimaryKey);`
   * Eliminar una llave primaria:
      * `ALTER TABLE nombre_tabla DROP CONSTRAINT MyPrimaryKey;`}
* *Llaves foráneas*:
   * Agregar una llave primaria:
      * `ALTER TABLE nombre_tabla ADD CONSTRAINT FK_nombre_tabla_nombreforaneo FOREIGN KEY (nombreforaneo) REFERENCES nombre_tabla_enlazada(nombre_campo_referenciado);`

### Usuarios
* Crear usuario:
   * `CREATE USER usuario WITH PASSWORD 'contraseña';`
* Eliminar usuario:
   * `DROP USER usuario;`
* Asignarle rol de superusuario a un usuario:
   * `ALTER ROLE usuario WITH SUPERUSER;`


## CRUD
* Agregar un registro:
   * `INSERT INTO nombre_tabla (campo1, campo2, campo3, campo4) VALUES ('Valor 1', 2, NULL, 'Valor 4');`
* Consultar todos los registros de una tabla:
   * `SELECT * FROM nombre_tabla`;
* Consultar solo registros de campos específicos:
   * `SELECT campo1, campo2 FROM nombre_tabla`;
* Consultar todos los registros de una tabla donde:
   * `SELECT * FROM nombre_tabla WHERE campo='Restricción'`;
* Consultar solo registros de campos específicos donde:
   * `SELECT campo1, campo2 FROM nombre_tabla WHERE campo='Restricción'`;
* Consultar datos ordenados por un campo:
   * `SELECT * FROM nombre_tabla ORDER BY campo`;
* Modificar un registro:
   * `UPDATE nombre_tabla SET campo1='Valor1', campo2=2 WHERE campo2='Dato';`
* Eliminar un registro:
   * `DELETE FROM nombre_tabla WHERE campo1='Dato';`

## Exportar una base de datos
Para exportar una base de datos desde PostgreSQL se utiliza el comando:
   * `$ pg_dump -U username -W -h host basename > basename.sql`

Detalles de los argumentos del comando: 
* $ pg_dump       Declara que se exportará una base de datos de PostgreSQL
* -U username     Se refiere al usuario propietario de la base de datos o el usuario postgres
* -W              Parámetro para solicitar el password del usuario antes especificado
* -h 127.0.0.1    Indica la dirección IP del host a donde se conectará
* basename        Nombre de la base de datos que se va a exportar
* basename.sql  Indica dónde se va a guardar el archivo exportado

### Ejemplo:
* La base de datos que se quiere respaldar se llama *entidades*
* La base de datos está en un servidor local
* El usuario propietario de la base de datos es antares
* Se quiere guardar el archivo en la carpeta del servidor con el nombre respaldo
Por lo tanto, el comando a utilizar será:
```shell
   $ pg_dump -U antares -W -h localhost entidades > /var/www/html/respaldo.sql
```


## Importar una base de datos
1. Para importar una base de datos en PostgreSQL, primero hay que crear una vacía para llenarla con las tablas:
   * `postgres=# CREATE DATABASE nombre_base;`
2. Importar el archivo sql:
   * `$ psql -U username -W -h host nombre_base < dump_base.sql`

Explicando paso a paso: 
* $ psql          Declara que se importará una base de datos usando PostgreSQL
* -U username     Se refiere al usuario propietario de la base de datos o el usuario postgres
* -W              Parámetro para solicitar el password del usuario antes especificado
* -h 127.0.0.1    Indica la dirección IP del host a donde se conectará
* nombre_base     Nombre de la base de datos que se va a exportar
* < dump_base.sql  Indica desde dónde se va a obtener el archivo a importar

### Ejemplo:
Si se quisiera importar la base de datos que se exportó en el punto anterior, se usaría el siguiente
comando:
```shell
  $ psql -U postgres -W -h localhost nombre_base < dump_base.sql
```