# Guía de configuración y uso de proxychains
Centro Nacional de Desarrollo e Investigación de Tecnologías Libres (CENDITEL) <br>
[CENDITEL](https://www.cenditel.gob.ve/), Mérida - Venezuela<br>
Dirección de Desarrollo<br>
Autor: [Ing. Angelo Osorio](https://twitter.com/Engel_PAIN)<br>
Fecha de Elaboración: 13-11-2017 (dd,mm,aaaa)

## Notas del autor
El símbolo al principio de una línea de comandos indica:
```
  $ = hacer la sentencia como usuario
  # = hacer la sentencia como administrador
```

## Proxychains
Un proxy es un intermediario entre el cliente que realiza una petición a un servidor que la recibe,
utilizado comúnmente para ocultar la dirección del cliente y evadir restricciones por paises.
Proxychains es una aplicación que permite hacer conexión a través de cadenas de proxies.

## Instalar / Desinstalar Proxychains
* Instalar proxychains  `# apt-get install proxychains`
* Desinstalar proxychains  `# apt-get remove proxychains`

## Configurar Proxychains
Para configurar proxychains hay que entrar en su archivo de configuración ubicado en `/etc/proxychains.conf`
con un editor de texto (nano, vim, vi, gedit, sublime text, etc...) con permisos de superusuario,
en este caso se usará el editor de texto de consola nano:
```
  # nano /etc/proxychains.conf
```
Ahora mostrará el archivo de configuración, que contiene la versión de la aplicación e información.
Proxychains tiene tres configuraciones seleccionables para encadenar los proxies:
* Strict_chain: Recorre la lista de proxies por orden y si uno está caído se detiene.
* Dynamic_chain: Recorre la lista de proxies por orden y si uno está caído continúa con el siguiente.
* Random_chain: Encadenará un proxy tras otro aleatoriamente.

Para activar la opción que se quiera utilizar hay que descomentarla y comentar la que esté activada
por defecto, agregando un numeral (#) al principio de la opción que se quiere desactivar y eliminado
el numeral de la línea que se quiere activar.

Por ejemplo, se si se quiere activar la configuración de cadena dinámica:
Comentar la opción que está activada por defecto:
```
#random_chain
```
Por defecto Dynamic_chain está comentada, hay que remover el comentario:
```
dynamic_chain
```

Ahora hay que ir a la parte inferior del archivo, en un apartado que dice `[ProxyList]`
Ahí hay que escribir los proxies que se van a utilizar. [Hidemy](https://hidemy.name/es/proxy-list/)
ofrece listas de proxies gratuitos, hay que ingresar en la página y tomar algunos.

Luego de elegir los proxies que se utilizarán hay que escribir en el final del archivo los proxies:
```
[ProxyList]
# add proxy here ...
# meanwile
# defaults set to "tor"
socks4 127.0.0.1 9050
<---------------------- A partir de aquí se escribiran los proxies
Tipo Host Puerto usuario contraseña (usuario y contraseña son opcionales)
```

Por ejemplo:
```
[ProxyList]
# add proxy here ...
# meanwile
# defaults set to "tor"
socks4 127.0.0.1 9050
# Proxy 1
http 192.168.0.1 80
socks5 192.168.0.1 8080
```

## Utilizar Proxychains
Ya configurado solo hay que escribir desde la consola el comando proxychains más el nombre del
navegador, por ejemplo firefox:
  $ proxychains firefox