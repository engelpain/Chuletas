## Comandos nuevos en Windows
Centro Nacional de Desarrollo e Investigación de Tecnologías Libres (CENDITEL) <br>
[CENDITEL](https://www.cenditel.gob.ve/), Mérida - Venezuela<br>
Dirección de Desarrollo<br>
Autor: [Ing. Angelo Osorio](https://twitter.com/Engel_PAIN)<br>
Fecha de Elaboración: 28-03-2018 (dd,mm,aaaa)


### Cambiar color del tema (Windows 7, 8 y 10):
1. WIN + R (Ejecutar)
2. Control Color

### Crear comandos personalizados
1. WIN + R (Ejecutar)
1. regedit
1. Buscar el directorio: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\AppPaths
1. Nuevo > clave > nombre.exe
1. Dentro de la carpeta:
   1. Nuevo > valor de cadena múltiple > como nombre hay que ponerle "Path"
1. Doble click al Path
1. En información del valor ingresar la ruta de "Iniciar en" del acceso directo
1. Aceptar
1. Doble click en (Predeterminado)
1. En información del valor ingresar la ruta de "Destino" del acceso directo
1. Aceptar

#### Enjoy!