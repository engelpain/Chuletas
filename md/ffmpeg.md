# Convertir videos con FFmpeg
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

## Instalar / Desinstalar FFmpeg
* Instalar proxychains  `# apt-get install ffmpeg`
* Desinstalar proxychains  `# apt-get remove ffmpeg`

## Convertir video
* De formato un formato a otro: `$ ffmpeg -i input.mp4 output.avi`
* Para configurar el bitrate: `$ ffmpeg -i input.avi -b:v 64k -bufsize 64k output.avi`
* Para configurar el frame rate: `$ ffmpeg -r 1 -i input.m2v -r 24 output.avi`