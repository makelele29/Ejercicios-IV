# Tema 6

#### Ejercicio 1

##### Instalar chef en la máquina virtual que vayamos a usar.

Lo instalamos con el siguiente comando:

    curl -L https://www.opscode.com/chef/install.sh | sudo bash



#### Ejercicio 2

##### Crear una receta para instalar la aplicación que se viene creando en la asignatura en alguna máquina virtual o servidor en la nube.

#### Ejercicio 3

##### Desplegar la aplicación de DAI con todos los módulos necesarios usando un playbook de Ansible.

El despliegue lo he realizado con la aplicación de IV y esta explicado [aqui](https://makelele29.github.io/Geoke-Web/#ansible)

#### Ejercicio 4

##### Instalar una máquina virtual Debian usando Vagrant y conectar con ella.

Instalamos vagrant

      sudo apt-get install vagrant

Ahora descargo la imagen de Debian tal y como se explica en los apuntes:

    vagrant box add debian https://github.com/holms/vagrant-jessie-box/releases/download/Jessie-v0.1/Debian-jessie-amd64-netboot.box

Lo siguiente es crear el fichero Vagranfile:

    vagrant init debian

y con vagrant up inicilizamos la máquina:

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202017-01-24%2020-07-37_zpsszvqsxtk.png)

por último para conectarnos vagrant ssh:

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202017-01-24%2020-13-30_zpsfskkwrjd.png)


#### Ejercicio 5

##### Crear un script para provisionar `nginx` o cualquier otro servidor web que pueda ser útil para alguna otra práctica

Configuramos el Vagrantfile

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202017-01-24%2020-18-11_zpspjwr2wwj.png)

luego ejecutamos vagrant up y luego vagrant provision para añadir lo que hemos puesto en el Vagrantfile.

Comprobamos que efectivamente esta instalado y funcionando.

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202017-01-24%2020-27-32_zpswzoshfbz.png)

#### Ejercicio 6

##### Configurar tu máquina virtual usando vagrant con el provisionador chef.

Primero vamos a instalar el plugin de chef en vagrant

      vagrant plugin install vagrant-berkshelf
