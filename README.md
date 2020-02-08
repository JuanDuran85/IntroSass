# Introducción a Sass
Ejemplos básicos usando Sass desde cero.

## CSS
### Desventajas de CSS
* No es un lenguaje de programación como tal.
* Problemas con especificidad, cascadas y herencia cuando los proyectos son muy grandes.
* Modularización.
* Las varibales de CSS vienen con limitaciones.

# SASS
## Ventajas de SASS
* Es una super extensión de CSS que lo convierte en un lenguaje de programación, por lo tanto, amplia las capacidades de CSS puro.
* SASS pasa a ser un preprocesador de CSS. Es decir, procesa previamente el código y lo convierte en CSS mediante la compilación. Ya sea por terminal o con otro software, framework o librería.
* Para compilar por el terminar, actualemente es necesario utilizar NodeJS y NPM. Mientras que se pueden usar Prepos o GulpJS para compilar los archivos de SASS en CSS.
* SASS es 100% compatible con CSS. No existirá problema alguno. Incluso, se puede renombrar un archivo de CSS en SASS.
* SASS Permite la modularización del código en distintos archivos y/o carpetas que permitan trabajar de una manera ordenada y fácil de entender.
* Se puede importar a un archivo principal todos los módulos mediante la instrucción import.

## Instalación de SASS
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

## Características importantes de SASS
* SASS posee distintos tipos de datos, como números, cadenas de texto, colores, boléanos, listas.
* Las variables se inician con el símbolo de “$” más el nombre de la variable, posteriormente se escribe “:” para poder asignar el valor a la variable, no se debe usar el signo "="
* Se puede usar @debug mas el nombre de la varibale para ver el valor de dicha variable.
* La regla @warn muestra el valor de una expresió SaasScript en forma de mensaje de error.
* En SASS las funciones son con “-” y no con “_”.
* Se puede utilizar la instrucción type-of para saber el tipo de datos que posee una variable.
* Los mapas son como un objeto en JavaScript, tienen clave y valor.
* Se pueden anidar selectores facilmente mediante la tecnica nesting. 
* Los Nesting o Inheritance, son los anidamientos que se pueden usar entre las etiquetas para ir agregando los estilos al HTML. Por lo tanto, en SASS, se debe seguir una secuencia del llamado de las etiquetas una dentro de la otra para lograr el anidamiento y la posterior herencia de las etiquetas.
* Se puede anidar selectores sin importar el tipo, es decir, pueden ser clases o id. Igualmente, se pueden modificar las clases predefinidas por bootstrap.
* & se utiliza para nombrar y activar las Pseudo-clases de CSS.
* Las extensiones seran partes del código que no serán compiladas directamente sobre la salida en CSS. Para indicar que una parte del código será una extensión, se debe utilizar el simbolo %"nombre_extension", y al utilizar la instruccion de @extend %nombre_extension, estas seran llamadas e incorporadas como parte del código en CSS al selector seleccionado
* Para instalar Bootstrap. la mejor manera es posicionarse en la carpeta donde se desea utilizar la libreria, posteriormente utilizar los comandos en el terminar:

```sh
npm install bootstrap
```

* Posteriormente se importa el documento en el principal de SASS, utiliando la ruta (ejemplo):

```sass
@import "bootstrap/node_modules/bootstrap/scss/bootstrap.scss";
```

* Cuando se trabaja con el Bootstrap mediante SASS, se debe importar primero la libreria completa de Bootstrap antes que los otros archivos de SASS.
Ahora, para utilizar cualquiera de las clases de Bootstrap tradicionales, solo se agrega la clase dentro de las etiquetas HTML como siempre se hace.
* Las extensiones seran partes del codigo que no seran compiladas directamente sobre la salida en CSS. Para indicar que una parte del codigo sera una extension, se debe utilizar el sombolo %+nombre_extension, pero al utilizar la instruccion de @extend %nombre_extension, estas seran llamadas e incorporadas como parte del codigo en CSS al selector seleccionado
* También se pueden usar mixin, los cuales, son trozos de códigos que se pueden reutilizar.
* Los Mixin sos bloques de códigos que pueden ser utilizados tantas veces sea necesario. Por si solo, no generan estilos sobre el CSS.
* Para llamar un mixin se utiliza el @include. 
* Igualmente se puede agregar dentro de un mixin el "&" para repetir el selector padre y aplicar las Pseudo-clases, igualmente se pueden agregar @media para trabajar con los distintos tamaños.
* Al utilizar los maxin, se pueden enviar parametros como si se trabajara con una funcion culaquiera en JavaScript, por lo que se pueden usar uno o mas parametros e incluso la notacion de ES6 de los "..." tres puntos seguidos.
* Otra importante caracteristica que tiene SASS es que se pueden usar *ciclos repetitivos, como: (for), (each), (while)* o *ciclos condicionales (if-else)*.
* Para usar el ciclo de repetición for, se debe trabajar con la instrucción:

```sass
@for <variable> from <expression> to <expression> { ... }
```
o

```sass
@for <variable> from <expression> through <expression> { ... }
```
* se debe utilizar la instrucción "map-get" para tomar los valores de una variable tipo mapa.
* Existen diversas funciones predefinidas en SASS, como el caso de:
    1. *length*: que se utiliza para ver la cantidad de valores disponibles en una lista.
    2. Con list-separator podemos ver el tipo de separación que existe en una variable del tipo lista.
    3. La función *nth* permite seleccionar un valor en especifico de una lista.
    4. Con la función *set-nth* se puede modificar un valor en especifico de una lista de valores o estilos.
    5. Con la función *join* se pueden unir mas de una lista e indicar el tipo de separador en el caso de ser necesario.
    6. Con la funcion *append* se puede agregar valores a una lista yadefinida directamente sobre el estilo.
    7. El index se utiliza para indicar la posicion de un elemento o valor dentro de una lista. El elemento a buscar debe ser exactamente igual al almacenado en la lista. Por lo que regresarà el valor de la posicion donde se encuentre ese valor.
    8. la funcion *zip* permite concatener distintas listas de variables o valores en una sola linea.

* Tambien se pueden usar funciones predefinidas con las variables del tipo MAP, como lo son:
    1. map-keys: muestra los nombres de las llaves de una variable tipo map.
    2. map-values: muestra los valores de las llaves de una varibale tipo map.
    3. map-has-key: permite determinar si una llave existe en ua varibale del tipo map.
    4. map-get: se obtiene el valor de una llave en especifica.
    5. inspect(map-merge): son dos funciones que permiten mostrar las llaves y los valores de varibales del tipo mp.
    6. inspect(map-remove): se utiliza para remover una llave de la varible del tipo map.

* En SASS tambien se pueden realizar operaciones matematicas básicas. Como suma, resta, multiplicacion y división. Igualmente utilizar funciones predeterminadas como:
    1. round: redondea el valor para llegar al siguiente superior.
    2. floor: redondea el valor dependiendo del valor de los decimales.
    3. percentage: convierte en porcentaje el valor ingresado. 0.1 para 10%. 1 para 100%.
    4. ceil: redondea el valor dependiendo del valor de los decimales.
    5. abs: retorna el valor de forma positiva. 

* Otras de las caracteristicas importantes de SASS, es la utilizacion de funciones con argumentos o parametros definidos por el programador. Estas trabajan igual que en distintos lenguajes de programacion, como JavaScript. Ejemplo:

```sass
@function nombre_funcion ($parametro1, $parametro2) { ... }
```




