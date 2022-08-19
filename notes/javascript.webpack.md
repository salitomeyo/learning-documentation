---
id: fqmgm6nkjwxsgwkfbjc3zmr
title: Webpack
desc: ''
updated: 1660861323617
created: 1660850196290
---

# NodeJs

Permite correr codigo Javascript en el lado del servidor, tambien permite convertir nuestro pc en un servidor de desarrollo. Es decir permite crear un entorno de desarrollo local.

## NPM

Es un gestor de paquetes de node

# BABEL

Es un paquete de npm que permite convertir el codigo de js en las nuevas versiones a codigo antiguo

# Webpack

Es un enpaquetador de modulos, es decir permite realizar varias funciones de manera automatica

* Gestion de dependencias
* Montar servidores de desarrollo y pruebas
* Cargar modulos
* Convertir a diferentes formatos
* Minimizar codigo
* Compilar SASS a CSS
* Compilar TS a JS
* Permite trabajar con JS moderno

## Problematicas de webpack

* La configuracion inicial es realmente engorroza
* Puede ser complicado detectar problemas con algun paquete

## Como instalar webpack

[Webpack guide](https://webpack.js.org/guides/getting-started/)

Webpack se instala en las devDependencies ya que no es necesario para produccion, y a la hora de enviar a produccion se puede eliminar usando un tree-shaking

Al utilizar

```cmd
webpack
```

Esto creara un build de nuestra aplicacion, en el cual **todos los archivos de javascript son centralizados y minimizados** en la carpeta dist, los archivos creados en esta carpeta pueden ser lanzados directamente a produccion

### Build archivos html

Pero normalmente una aplicacion web no solo necesita los archivos js sino que a su vez necesita archivos css y html, por esto es importante instalar las siguientes librerias que nos ayudaran a buildear los archivos html en modo produccion

* [html-loader](https://webpack.js.org/loaders/html-loader/)
* [html-webpack-plugin](https://webpack.js.org/plugins/html-webpack-plugin/)

Una vez se instalan estos archivos y se configuran en **webpack.config.js** la carpeta dist tendra el js y el html, pero como el archivo html y js buildeados con webpack usan modulos es necesario probar estos archivos en un servidor http, ya que simplemente abrir el archivo html en el navegador no permitira usar el js configurado

Por esto es necesario descargar e implementear un servidor locar, para ayudarnos a hacer esto existe otra libreria soportada por webpack

* [dev-server](https://webpack.js.org/configuration/dev-server/)

### Build archivos CSS

Del mismo modo que realizamos las importaciones para poder buildear archivos html, ahora importaremos las librerias necesarias para poder buildear archivos de css

* [css-loader](https://webpack.js.org/loaders/css-loader/)
* [style-loader](https://webpack.js.org/loaders/style-loader/)

Al hacer un build usando estas 2 librerias no se creara un archivo externo css sino que los estilos quedaran embeidos en el html, si no queremos esto sino que buscamos crear un archivo css en el build es necesario instalar esta libreria adicional 

* [mini-css-extract-plugin](https://webpack.js.org/plugins/mini-css-extract-plugin/)

### Cargando imagenes

Para poder usar imagenes y otros archivos en el webpack dev-server es necesario importar una libreria adicional

* [file-loader](https://v4.webpack.js.org/loaders/file-loader/)

### Build archivos estaticos

Para que la carpeta de assets, imagenes, o cualquier otro recurso estatico se copie en el dist al buildear requerimos la siguiente libreria

* [copy-webpack-plugin](https://webpack.js.org/plugins/copy-webpack-plugin/)


## Enviando a produccion

El archivo que creamos en produccion de css tambien debe ser minimizado para ahorrar espacio, por esto debemos instalar los siguientes plugins

* [css-minimazer-webpack-plugin](https://webpack.js.org/plugins/css-minimizer-webpack-plugin/)
* [teser-webpack-plugin](https://webpack.js.org/plugins/terser-webpack-plugin/)

## Usando Babel

Usamos Babel para traducir el codigo de ultimas versiones de js a versiones mejor soportadas por todos los navegadores, toda la documentacion acerca de babel se encuentra en su pagina oficional

[babel](https://babeljs.io/)


