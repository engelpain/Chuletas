# Angular 6
Centro Nacional de Desarrollo e Investigación de Tecnologías Libres (CENDITEL) <br>
[CENDITEL](https://www.cenditel.gob.ve/), Mérida - Venezuela<br>
Dirección de Desarrollo<br>
Autor: [Ing. Angelo Osorio](https://twitter.com/Engel_PAIN)<br>
Fecha de Elaboración: 31-08-2018 (dd,mm,aaaa)



## Notas del autor
El símbolo al principio de una línea de comandos indica:
```
   $ = hacer la sentencia como usuario
   # = hacer la sentencia como administrador
```


### Requisitos
* Tener instalado [NodeJS](https://nodejs.org/es/)
   * Opción 1: [Instalación para sistemas basados en Debian](https://github.com/engelpain/Chuletas/blob/master/md/nodejs.md)
   * Opción 2: [Instalación usando un gestor de paquetes](https://github.com/engelpain/Chuletas/blob/master/md/nodejs.md)
   * Opción 3: [Descarga del instalador](https://nodejs.org/es/download/current/)


### Instalar Angular CLI en NodeJS, para proyectos con Angular 6
* **Nota**: En caso de tener una instalación anterior de Angular CLI, desinstalar para evitar conflictos:
   * `# npm unistall -g angular-cli`
   * `# npm unistall -g @angular/cli`
   * `# npm cache clean`
* Instalar la última versión de Angular CLI
   * `# npm install -g @angular/cli`

### Mi primer proyecto en Angular 6
#### 1. Crear un proyecto
1. Generar el nuevo proyecto
   * `$ ng new my-app`
2. Entrar al directorio recién generado
   * `$ cd my-app`
3. Servir la aplicación
   * Forma 1: `$ ng serve -o`
   * Forma 2: `$ npm start`

#### 2. Editar el título de la aplicación
1. Editar el primer componente de Angular: `./src/app/app.component.ts`
```script
export class AppComponent {
  title = 'Mi primer proyecto en Angular 6';
}
```

#### 3. Componentes en Angular 6
En Angular todo trata de componentes, dentro de estos es donde "ocurre la magia", donde se cargan los
datos, de realizan los filtrados, donde se muestran las consultas. En `./src/app/app.component.ts` es
donde se agregan los componentes de las aplicaciones.

Por ejemplo:
```script
/*
 * @Component es una palabra reservada en Angular y se refiere al componente. Este tiene atributos
 * como:
 * selector: señala el selector donde se cargará el componente.
 * Por ejemplo, si se quiere cargar en una etiqueta llamada app-root, se debe especificar 'app-root'.
 * Ejemplo 2: Si se quisiera cargar en un div con un id, solamente se debe especificar '#nombredeid'.
 * Ejemplo 3: Si se quisiera cargar en un div con una clase, solo se debe especificar '.nombreclase'.
 */
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  // Título de la aplicación
  title = 'Mi primer proyecto en Angular 6';
}
```
