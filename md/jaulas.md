<h1> Guía de elaboración de sistemas enjaulados en Debian</h1>
<p> Centro Nacional de Desarrollo e Investigación de Tecnologías Libres (CENDITEL)</p>
<p> CENDITEL, Mérida - Venezuela </p>
<p> Dirección de Desarrollo </p>
<p> Autor: <a href="https://twitter.com/Engel_PAIN">Ing. Angelo Osorio</a> </p>
<p> Fecha de Elaboración: 05-12-2017 (dd,mm,aaaa)</p>

<h2>Notas del autor</h2>
<p>El símbolo al principio de una línea de comandos indica: <br>
  <code> $ = hacer la sentencia como usuario </code> <br>
  <code> # = hacer la sentencia como administrador</code>
</p>

<h2>¿Qué es un sistema enjaulado?</h2>
<p>También denominado <strong>Bootstraping</strong>, consiste en correr un sistema operativo invitado dentro de un anfitrión, a través de la consola.</p>
<p>Sirven para hacer pruebas en distintas distribuciones sin la necesidad de utilizar una máquina virtual, ni interfaz gráfica, además que utiliza los requerimientos de la máquina anfitriona, en lugar de seccionar éstos como pasa al momento de instalar una máquina virtual. La única desventaja es que toda operación dentro de la jaula se realizará bajo permiso root exclusivamente.</p>
<p> Son útiles cuando se requiere probar versiones de programas que tienen dependencias específicas. </p>

<h2> Crear una jaula de Debian 8 (jessie) en Debian 9 (stretch) </h2>
<ol>
  <li>
    <p> Instalar debootstrap: </p>
    <p> <code> # apt install debootstrap </code> </p>
  </li>
  <li>
    <p> Crear un directorio para el sistema enjaulado</p>
    <p> <code> # mkdir -p /jaulas/jessie </code> </p>
    <p> <b> Nota: </b> En este caso se creó un directorio que se llama <b> jaulas </b> antes de crear el directorio <b> jessie </b> que será el que alojará la jaula, dado que es más práctico tener todas las jaulas en el mismo sitio.
    </p>
    <p> <b> Nota 2: </b> Es indiferente dónde se cree el directorio. En este ejemplo, el directorio está directamente en la raíz. </p>
    <p> <b> Nota 3: </b> Se utiliza el argumento <code> -p </code> para que no arroje un error si el directorio padre ya existe y crea el directorio padre si es necesario.
    </p>
  </li>
  <li>
    <p> Descargar el sistema desde los repositorios Debian </p>
    <p> <code> # debootstrap jessie /jaulas/jessie ​http://ftp.us.debian.org/debian/ </code> </p>
  </li>
  <li>
    <p> Una vez descargado se debe importar el <b>proc</b> de la máquina anfitrión a la jaula. </p>
    <p> Cada vez que se reinicia el equipo hay que montar el <b>proc</b>, entonces, para
automatizar esa directiva se puede modificar el fichero <code>/etc/fstab</code> con la siguiente instrucción:
    </p>
    <p> 
      <code> # echo "/proc /jaulas/jessie/proc/ auto bind 0 0 " >> /etc/fstab </code>
    </p>
  </li>
  <li>
    <p> Iniciar el sistema enjaulado: </p>
    <p> Montar el proc: </p>
    <p> # mount -a </p>
    <p> Entrar en la jaula </p>
    <p> <code> # chroot /jaulas/jessie </code> </p>
  </li>
</ol>

<p> Ahora la jaula está lista para utilizar </p>
<p><img src="../img/jaulas1.png" alt="Jaula jessie"></p>


<h3>Enlaces de referencia:</h3>
<ul>
  <li> <a href="https://cumaco.cenditel.gob.ve/desarrollo/wiki/openwrt">Guía de referencia para Jaula de Debian</a>
  </li>
</ul>