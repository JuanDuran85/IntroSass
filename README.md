   # Introducción a Sass
Ejemplos básicos usando Sass desde cero.
## CSS
### Desventajas de CSS
* No es un lenguaje de programación como tal.
* Problemas con especificidad, cascadas y herencia cuando los proyectos son muy grandes.
* Modularización.
* Las varibales de CSS vienen con limitaciones.

## SASS
### Ventajas de SASS
* Es una super extensión de CSS que lo convierte en un lenguaje de programación, por lo tanto, amplia las capacidades de CSS puro.
* SASS pasa a ser un preprocesador de CSS. Es decir, procesa previamente el código y lo convierte en CSS mediante la compilación. Ya sea por terminal o con otro software, framework o librería.
* Para compilar por el terminar, actualemente es necesario utilizar NodeJS y NPM. Mientras que se pueden usar Prepos o GulpJS para compilar los archivos de SASS en CSS.
* SASS es 100% compatible con CSS. No existirá problema alguno. Incluso, se puede renombrar un archivo de CSS en SASS.
* SASS Permite la modularización del código en distintos archivos y/o carpetas que permitan trabajar de una manera ordenada y fácil de entender.
* Se puede importar a un archivo principal todos los módulos mediante la instrucción import.

### Instalación de SASS
* Primeramente se debe instalar NodeJS, disponible en: [node.js]
* Luego verificar la instalación de NodeJS y NPM utilizando los comandos:

```sh
$ node --version
$ npm --version
```

* Posteriormente, se debe instalar SASS desde el terminal, utilizando las siguientes instrucciones:

```sh
$ npm install -g sass
```

* Una vez tengas todo instalado, puedes crear una carpeta con el archivos index.html (donde escribirás todo el documento al cual deseas agregar estilos), *otra carpeta denominada sass con el archivos style.scss*, y dentro de la carpeta de sass *otra carpeta denominada components, con los archivos modulares del proyecto*. Estos deben iniciar el nombre con el _ para que no sean compilados, debido a que serán importados al style.scss. Ejemplo: _colores.scss. Finalmente, otra carpeta con el nombre de css a la altura del index.html, donde estará nuestro archivo de salida final con los estilos en css puto, denominado style.css **(este archivo será el que debe estar incluido en el index.html)**.
* Para compilar un archivo SASS, se debe utilizar la siguiente instrucción en el terminal:

```sh
$ sass --watch style.scss ../css/style.css
```

* Se debe tener cuidado con la ubicación de los archivos, por lo tanto, se puede entrar a la carpeta de SASS y ejecutar la instrucción anterior desde esa carpeta e indicar la ubicación exacta del archivo de salida. 

### Características importantes de SASS
* SASS posee distintos tipos de datos, como números, cadenas de texto, colores, boléanos, listas.
* Las variables se inician con el símbolo de “$” más el nombre de la variable, posteriormente se escribe “:” para poder asignar el valor a la variable, no se debe usar el signo "="
* Se puede usar @debug mas el nombre de la varibale para ver el valor de dicha variable.
* En SASS las funciones son con “-” y no con “_”.
* Se puede utilizar la instrucción type-of para saber el tipo de datos que posee una variable.
* Los mapas son como un objeto en JavaScript, tienen clave y valor.
* Se pueden anidar selectores facilmente mediante la tecnica nesting.
* También se pueden usar mixins, los cuales, son trozos de códigos que se pueden reutilizar.






