# Tema 4

#### Ejercicio 1

##### Instala LXC en tu versión de Linux favorita. Normalmente la versión en desarrollo, disponible tanto en GitHub como en el sitio web está bastante más avanzada; para evitar problemas sobre todo con las herramientas que vamos a ver más adelante, conviene que te instales la última versión y si es posible una igual o mayor a la 1.0.
He utilizado el siguiente comando para instalarme LXC

```bash

sudo apt-get install lxc

```

#### Ejercicio 2

##### Comprobar qué interfaces puente se han creado y explicarlos.

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-12-05%2022-07-55_zpsuldtn7z9.png)


- __lxcbr0__ que sirve para que el contenedor tenga acceso a internet.
- __vethVUI42Y__ para que el contenedor se pueda comunicar con otros contenedores.


#### Ejercicio 3

##### Crear y ejecutar un contenedor basado en Debian.

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-12-05%2022-15-58_zpsexxgpdyf.png)

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-12-05%2022-24-26_zpsqjdgfatn.png)

##### Crear y ejecutar un contenedor basado en otra distribución, tal como Fedora. Nota En general, crear un contenedor basado en tu distribución y otro basado en otra que no sea la tuya. Fedora, al parecer, tiene problemas si estás en Ubuntu 13.04 o superior, así que en tal caso usa cualquier otra distro. Por ejemplo, Óscar Zafra ha logrado instalar Gentoo usando un script descargado desde su sitio, como indica en este comentario en el issue.

Yo he instalado Fedora sin ningún problema

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-12-05%2022-35-00_zps09ymmsjw.png)

#### Ejercicio 4

##### Instalar lxc-webpanel y usarlo para arrancar, parar y visualizar las máquinas virtuales que se tengan instaladas.

Ejecutamos el siguiente comando siendo root, para que se instale.

```bash

wget https://lxc-webpanel.github.io/tools/install.sh -O - | bash

```
Para visualizalo : http://localhost:5000/home

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-12-05%2022-44-34_zpslfcqewki.png)

##### Desde el panel restringir los recursos que pueden usar: CPU shares, CPUs que se pueden usar (en sistemas multinúcleo) o cantidad de memoria.

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-12-05%2022-58-26_zpsifqrnlme.png)

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
