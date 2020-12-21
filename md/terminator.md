## Guía sobre comandos de Terminator
Centro Nacional de Desarrollo e Investigación de Tecnologías Libres (CENDITEL) <br>
[CENDITEL](https://www.cenditel.gob.ve/), Mérida - Venezuela<br>
Dirección de Desarrollo<br>
Autor: [Ing. Angelo Osorio](https://twitter.com/Engel_PAIN)<br>
Fecha de Elaboración: 05-12-2017 (dd,mm,aaaa)
Modificada: 09-12-2020 (dd,mm,aaaa)

### Notas del autor
El símbolo al principio de una línea de comandos indica:
```
   $ = hacer la sentencia como usuario
   # = hacer la sentencia como administrador
```

### Descripción
Terminator es una terminal que permite manipular su layout para abrir terminales adicionales en la
misma ventana.


### Instalar Terminator
- Basta con el comando: `# apt install terminator`
- De poseer aptitude: `# aptitude install terminator`

### Comandos de Terminator

#### Texto
|         Comando         |               Descripción               |
| ----------------------- | --------------------------------------- |
| Ctrl + Shift + C        | Copiar lo seleccionado al portapapeles  |
| Ctrl + Shift + V        | Pegar texto del portapapeles            |
| Ctrl + Shift + F        | Buscar con el scrollback de la terminal |

#### Layout
|         Comando         |               Descripción               |
| ----------------------- | --------------------------------------- |
| Ctrl + Shift + O        | Dividir terminal horizontalmente        |
| Ctrl + Shift + E        | Dividir terminal verticalmente          |
| Ctrl + Shift + Up       | Mover borde principal Arriba            |
| Ctrl + Shift + Down     | Mover borde principal Abajo             |
| Ctrl + Shift + Right    | Mover borde principal a la Derecha      |
| Ctrl + Shift + Left     | Mover borde principal a la Izquierda    |
| Ctrl + Shift + S        | Mostrar/Ocultar barra Scroll            |
| Ctrl + Plus (+)         | Aumentar tamaño de la fuente            |
| Ctrl + Minus (-)        | Disminuir tamaño de la fuente           |
| Ctrl + Zero (0)         | Restaurar tamaño original de la fuente  |
| Ctrl + Shift + Z        | Ampliar la terminal actual              |
| F11                     | Pantalla completa                       |
| Ctrl + Shift + W        | Cerrar la terminal actual               |
| Ctrl + Shift + X        | Mostrar sólo la terminal actual         |
| Ctrl + Shift + Q        | Cerrar Terminator                       |

#### Pestañas
|         Comando         |                        Descripción                       |
| ----------------------- | -------------------------------------------------------- |
| Ctrl + Shift + T        | Abrir nueva pestaña                                      |
| Ctrl + PageDown         | Mover a la siguiente pestaña                             |
| Ctrl + PageUp           | Mover a la anterior pestaña                              |
| Ctrl + Shift + N        | Mover a la siguiente terminal dentro de la misma pestaña |
| Ctrl + Shift + P        | Mover a la anterior terminal dentro de la misma pestaña  |
| Ctrl + Shift + PageDown | Intercambiar posición con la siguiente pestaña           |
| Ctrl + Shift + PageUp   | Intercambiar posición con la anterior pestaña            |
| Shift + Super + R       | Rotar terminales (Inverso a las agujas del reloj)        |