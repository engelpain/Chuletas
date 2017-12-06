<h1> Ubicación de puertos de programas </h1>
<p> Centro Nacional de Desarrollo e Investigación de Tecnologías Libres (CENDITEL)</p>
<p> CENDITEL, Mérida - Venezuela </p>
<p> Dirección de Desarrollo </p>
<p> Autor: <a href="https://twitter.com/Engel_PAIN">Ing. Angelo Osorio</a> </p>
<p> Fecha de Elaboración: 05-12-2017 (dd,mm,aaaa)</p><br>

<h2>Notas del autor</h2>
<p>El símbolo al principio de una línea de comandos indica: <br>
  <code> $ = hacer la sentencia como usuario </code> <br>
  <code> # = hacer la sentencia como administrador</code>
</p>
<p>Nano es el editor de texto de consolas que instalar Debian por defecto, por ello se utiliza nano,
sin embargo, se puede usar cualquier otro editor.</p>

<h2>Apache</h2>
<ol>
  <li>El archivo de los puertos de apache <br>
    <code> # nano /etc/apache2/ports.conf</code>
  </li>
  <li>
    <img src="../img/puertos1.png" alt="puertos1">
    <p>Entre las primeras líneas se encuentra una sentencia que dice <strong>Listen 80</strong>, ese es el puerto</p>
    <p>El puerto por defecto de apache es el 80</p>
  </li>
</ol>