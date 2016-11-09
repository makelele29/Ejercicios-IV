# Tema 3

#### Ejercicio 1

##### Darse de alta en algún servicio PaaS tal como Heroku, Nodejitsu, BlueMix u OpenShift.

Yo ya tenia cuenta tanto en Openshift, como en Heroku.

#### Ejercicio 2

##### Crear una aplicación en OpenShift o en algún otro PaaS en el que se haya dado uno de alta. Realizar un despliegue de prueba usando alguno de los ejemplos.

Creare una aplicación WordPress utilizando la web de OpenShift.
Lo primero es iniciar sesión y una vez dentro de tu perfil, se le da al botón __Add Aplication...__

Aparecera una serie de cartuchos y inicios rapidos que seran las aplicaciones que dispone OpenShift, en nuestro caso buscamos WordPress y le damos a añadir.

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura_zpsh1hmp5xi.png)

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura_zpswaixf6gp.png)

Una vez rellenado los campos dependiendo nuestras preferencias le daremos a __Create Application__ y en un rato ya tendremos nuestro wordpress en nuestro OpenShift.

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura_zps81xqfuk0.png)

Solo nos falta registrarnos y tendremos nuestra web en WordPress.

#### Ejercicio 3

##### Realizar una app en express (o el lenguaje y marco elegido) que incluya variables como en el caso anterior.

He creado una aplicación como la del ejemplo sobre las apuestas y guardo los resultados en mongodb.

[Repositorio del ejercicio 3](https://github.com/makelele29/heroku-porras)

Aquí un ejemplo en la consola:

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-11-09%2017-53-25_zpsqrmvmlxx.png)

#### Ejercicio 4

##### Crear pruebas para las diferentes rutas de la aplicación.

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-11-09%2018-22-19_zpsxicndeop.png)

#### Ejercicio 5

##### Instalar y echar a andar tu primera aplicación en Heroku.

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-11-09%2018-44-02_zps8xgn8ryj.png)

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-11-09%2019-33-19_zpsi6mzagmq.png)

#### Ejercicio 6

He añadido el archivo  travis y le he puesto a heroku que hasta que no pase el CI no se suban los archivos.

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-11-09%2020-00-40_zpsisc2fmsn.png)

##### Usar como base la aplicación de ejemplo de heroku y combinarla con la aplicación en node que se ha creado anteriormente. Probarla de forma local con foreman. Al final de cada modificación, los tests tendrán que funcionar correctamente; cuando se pasen los tests, se puede volver a desplegar en heroku.

#### Ejercicio 7

##### Haz alguna modificación a tu aplicación en node.js para Heroku, sin olvidar añadir los tests para la nueva funcionalidad, y configura el despliegue automático a Heroku usando Snap CI o alguno de los otros servicios, como Codeship, mencionados en StackOverflow

#### Ejercicio 8

##### Preparar la aplicación con la que se ha venido trabajando hasta este momento para ejecutarse en un PaaS, el que se haya elegido.
