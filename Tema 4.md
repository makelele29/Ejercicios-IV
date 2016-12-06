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

##### Comparar las prestaciones de un servidor web en una jaula y el mismo servidor en un contenedor. Usar nginx.




#### Ejercicio 6

##### Instalar docker.

Instalamos docker en nuestro sistema

    sudo apt-get install docker.io

![prueba](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-12-06%2001-09-20_zpsu761b5mp.png)

#### Ejercicio 7

##### Instalar a partir de docker una imagen alternativa de Ubuntu y alguna adicional, por ejemplo de CentOS.

Yo he instalado y ejecutado la imagen al mismo tiempo.

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-12-06%2011-53-31_zpsqnwlkzcv.png)

##### Buscar e instalar una imagen que incluya MongoDB.

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-12-06%2012-09-12_zpscsjj9i6m.png)
#### Ejercicio 8

##### Crear un usuario propio e instalar nginx en el contenedor creado de esta forma.

Procedemos a crearnos un usuario en ubuntu, darle permisos de administrador y hacer login.

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-12-06%2012-22-59_zpsnpto7vz3.png)

Para instalar nginx:

    sudo apt-get install nginx

Una vez instalado lo echamos a andar y listo.

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-12-06%2013-03-38_zpsmoeto8tg.png)


#### Ejercicio 9

##### Crear a partir del contenedor anterior una imagen persistente con commit.

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-12-06%2013-08-28_zpswkvxrwlz.png)

#### Ejercicio 10

##### Crear una imagen con las herramientas necesarias para el proyecto de la asignatura sobre un sistema operativo de tu elección.

Ejecutamos los siguientes comandos:

```shell

sudo docker run -i -t ubuntu /bin/bash

apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10
echo "deb http://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.0 multiverse" | tee /etc/apt/sources.list.d/mongodb-org-3.0.list

apt update

apt install -y mongodb-org

apt install -y build-essential curl

curl -sL https://deb.nodesource.com/setup_7.x

apt install -y nodejs

```

Luego guardamos la imagen

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-12-06%2013-51-31_zpsjyqhmw4q.png)
