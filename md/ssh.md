# SSH
Centro Nacional de Desarrollo e Investigación de Tecnologías Libres (CENDITEL) <br>
[CENDITEL](https://www.cenditel.gob.ve/), Mérida - Venezuela<br>
Dirección de Desarrollo<br>
Autor: [Ing. Angelo Osorio](https://twitter.com/Engel_PAIN)<br>
Fecha de Elaboración: 24-09-2018 (dd,mm,aaaa)


## Notas del autor
El símbolo al principio de una línea de comandos indica:
```
   $ = hacer la sentencia como usuario
   # = hacer la sentencia como administrador
```


## Instalar SSH
* Para instalar SSH se utiliza el comando:
   * `# apt-get install ssh`


## Configurar SSH
1. Configurar el archivo del cliente ssh:
   * `# nano /etc/ssh/ssh_config`
   1. Y descomentar la `Protocol` y asignar el número de protocolo, si no existe se agrega:
      * `Protocol 2`
2. Configurar el archivo del cliente servidor ssh:
   * `# nano /etc/ssh/sshd_config`
   1. Descomentar y cambiar el puerto:
      * `Port 1234`
   2. En la línea siguiente agregar el protocolo asignado en el archivo anterior:
      * `Protocol 2`
3. Reiniciar ssh
   * `# systemctl restart sshd`


## Utilizar con SSH
* Conectar a una máquina o servidor remoto
   * `$ ssh -p puerto username@ipdedestino`
* Apagar la máquina virtual
   * `$ poweroff`