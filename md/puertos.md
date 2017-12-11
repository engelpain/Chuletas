<h1> Ubicación de puertos de programas </h1>
<p> Centro Nacional de Desarrollo e Investigación de Tecnologías Libres (CENDITEL)</p>
<p> CENDITEL, Mérida - Venezuela </p>
<p> Dirección de Desarrollo </p>
<p> Autor: <a href="https://twitter.com/Engel_PAIN">Ing. Angelo Osorio</a> </p>
<p> Fecha de Elaboración: 05-12-2017 (dd,mm,aaaa)</p>

<h2>Notas del autor</h2>
<p>El símbolo al principio de una línea de comandos indica: <br>
  <code>  $ = hacer la sentencia como usuario </code> <br>
  <code>  # = hacer la sentencia como administrador</code>
</p>
<p>Nano es el editor de texto de consolas que instalar Debian por defecto, por ello se utiliza nano, sin embargo, se puede usar cualquier otro editor.</p>

<h2>Apache</h2>
<ol>
  <li>El archivo de los puertos de apache <br>
    <code>  # nano /etc/apache2/ports.conf</code>
  </li>
  <li>
    <p>Entre las primeras líneas se encuentra una sentencia que dice <b>Listen 80</b></p>
    <p><img src="../img/puertos1.png" alt="puerto Apache"></p>
    <p>Ese es el puerto (Por defecto es el 80)</p>
  </li>
</ol>


<h2>PostgreSQL</h2>
<ol>
  <li>Abrir el archivo de configuración de PostgreSQL <br>
    <code>  $ nano /etc/postgresql/version/main/postgresql.conf</code>
    <i>Nota</i>: en <b>version</b> hay que reemplazarlo por la versión de PostgreSQL que posea, por ejemplo: <br>
    <code>  $ nano /etc/postgresql/9.4/main/postgresql.conf</code>
  </li>
  <li>
    <p>En el apartado CONNECTIONS AND AUTHENTICATION se encuentra el puerto (Por defecto es el 5432):</p>
    <p><img src="../img/puertos2.png" alt="puerto PostgresSQL"></p>
  </li>
</ol>


<h2>Phppgadmin</h2>
<ol>
  <li>
    <p>Abrir el archivo de configuración de Phppgadmin</p>
    <p><code>  # nano /etc/phppgadmin/config.inc.php</code></p>
  </li>
  <li>
    <p>Bajo el comentario "Database port on server (5432 is the PostgreSQL default)" está el puerto:</p>
    <p><img src="../img/puertos3.png" alt="puerto Phppgadmin"></p>
  </li>
</ol>