# Tema 5

#### Ejercicio 1

##### Instalar los paquetes necesarios para usar KVM. Se pueden seguir estas instrucciones. Ya lo hicimos en el primer tema, pero volver a comprobar si nuestro sistema está preparado para ejecutarlo o hay que conformarse con la paravirtualización.

Volvemos a comprobarlo:

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-12-23%2016-40-50_zpsf3fjxaae.png)

Procedemos a instalar KVM

      sudo apt-get install qemu-kvm libvirt-bin ubuntu-vm-builder bridge-utils

Me añado a libvirtd y kvm

```bash

sudo adduser 'id -un' libvirtd
sudo adduser 'id -un' kvm

```

Verificamos la instalación

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-12-24%2015-38-57_zpsg1pqzfpv.png)

#### Ejercicio 2

##### Crear varias máquinas virtuales con algún sistema operativo libre tal como Linux o BSD. Si se quieren distribuciones que ocupen poco espacio con el objetivo principalmente de hacer pruebas se puede usar CoreOS (que sirve como soporte para Docker) GALPon Minino, hecha en Galicia para el mundo, Damn Small Linux, SliTaz (que cabe en 35 megas) y ttylinux (basado en línea de órdenes solo).

###### SliTaz

Creamos un disco duro y instalamos una imagen de SliTaz

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-12-23%2017-21-05_zpshkm2zpy8.png)

###### CoreOS

Creamos un disco duro y instalamos una imagen de CoreOS

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-12-24%2016-29-59_zpsf1kbxg4f.png)

##### Hacer un ejercicio equivalente usando otro hipervisor como Xen, VirtualBox o Parallels.

He utilizado VirtualBox y he instalado SliTaz

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-12-24%2019-02-58_zps5xj3jrj0.png)

#### Ejercicio 3

##### Crear un benchmark de velocidad de entrada salida y comprobar la diferencia entre usar paravirtualización y arrancar la máquina virtual simplemente con qemu-system-x86_64 -hda /media/Backup/Isos/discovirtual.img

#### Ejercicio 4

##### Crear una máquina virtual Linux con 512 megas de RAM y entorno gráfico LXDE a la que se pueda acceder mediante VNC y ssh.

Creamos disco

      qemu-img create -f qcow2 lubuntu.qcow2 6G

Instalamos

      qemu-system-x86_64 -machine accel=kvm -hda lubuntu.qcow2 -cdrom lubuntu-16.10-desktop-i386.iso -m 512M -boot d

###### VNC

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-12-25%2019-12-27_zpssdk8f4c0.png)

###### SSH

Instalamos ssh dentro de lubuntu

      sudo apt-get install openssh-server

En la maquina local:

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-12-25%2019-18-38_zpsknpzt4vl.png)

#### Ejercicio 5

##### Crear una máquina virtual ubuntu e instalar en ella alguno de los servicios que estamos usando en el proyecto de la asignatura.

#### Ejercicio 6

##### Instalar una máquina virtual con Linux Mint para el hipervisor que tengas instalado.

![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202017-01-03%2023-29-49_zpsfdwa0g0k.png)
