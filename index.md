---
layout: index
---


# Tema 1


#### Ejercicio  1:

##### Consultar en el catálogo de alguna tienda de informática el precio de un ordenador tipo servidor y calcular su coste de amortización a cuatro y siete años. Consultar este artículo en Infoautónomos sobre el tema.



[HP ProLiant ML110 G9 E5 v4/8GB](https://www.pccomponentes.com/hp-proliant-ml110-g9-e5-v4-8gb)

![HP ProLiant ML110 G9 E5 v4/8GB](https://thumb.pccomponentes.com/w-85-85/articles/10/102676/hp-proliant-ml110-g9-e5-v4-8gb-1.jpg)

** Precio: ** 999 €


- ** Amortización a los 4 años **:  Si consideramos que cada año tiene una amortización máxima (un 25%) el servidor nos costaria 999 * 0.25 = 249.75 € cada año.
-  ** Amortización a los 7 años **: Si consideramos que el servidor se amortiza más los primeros años y menos los últimos años, por cada año tendriamos:
 -  Primer año :  999 * 0.25 = 249,75
 -  Segundo año : 999 * 0.25 = 249,75
 -  Tercer año :  999 * 0.15 = 149,85
 -  Cuarto año :  999 * 0.15 = 149,85
 -  Quinto año :  999 * 0.10 = 99,9
 -  Sexto año :   999 * 0.05 = 49,95
 -  Séptimo año : 999 * 0.05 = 49,95


_ _ _ 


#### Ejercicio  2: 

##### Usando las tablas de precios de servicios de alojamiento en Internet y de proveedores de servicios en la nube, Comparar el coste durante un año de un ordenador con un procesador estándar (escogerlo de forma que sea el mismo tipo de procesador en los dos vendedores) y con el resto de las características similares (tamaño de disco duro equivalente a transferencia de disco duro) en el caso de que la infraestructura comprada se usa sólo el 1% o el 10% del tiempo.


| Maquina virtual de la web Microsoft Azure | Maquina dedicada de la web Arsys |
|--------|--------|
| ![F4](http://i1356.photobucket.com/albums/q726/Makelele_Junior/F4_zpsmngnbkzl.png?t=1475617759)       | ![pro4](http://i1356.photobucket.com/albums/q726/Makelele_Junior/pro4_zpstegdgw2q.png?t=1475617756)       |



Si se usa el 1% del tiempo:

Azure:  125.48 €/mes `*` 12 Meses `*` 0.01= 15,0576 €

Arsys: 125.00 €/mes `*` 12 meses = 1500 €



Se usa el 10% del tiempo:

Azure:  125.48 €/mes `*` 12 Meses `*` 0.1 = 150,576 €

Arsys: 125.00€/mes `*`12 meses = 1500 €

No he conseguido encontrar dos maquinas con almacenamiento parecido.

Es preferible la maquina virtual ya que el precio depende del tiempo de uso en este caso era 0.169 €/h, por tanto es más económico.

_ _ _ 


#### Ejercicio  3:

##### ¿Qué tipo de virtualización usarías en cada caso? [Comentar en el foro](https://github.com/JJ/IV16-17/issues/1)

- Virtualización plena : Para usar diferentes sistemas operativos o maquinas recurriría a una virtualización completa o plena (VMware,VirtualBox,etc).
- Virtualización de aplicaciones: En el caso de querer usar un ejecutable .exe o aplicaciones de Windows ( u otro sistema operativo) en un sistema UNIX/Linux usaría una virtualización de aplicaciones como por ejemplo Wine.
- Virtualización en entornos de desarrollo: cuando queremos trabajar con una determinada version sin modificar la versión que tenemos, un claro ejemplo es python con la version 2.7 y la 3.


##### Crear un programa simple en cualquier lenguaje interpretado para Linux, empaquetarlo con CDE y probarlo en diferentes distribuciones.

He creado un programa para ver si en una cadena de llaves estan todas bien cerradas.

```

#!/usr/bin/env python
import random
def comprobarllaves(H):
	total=0
	i=0
	tam=len(H)
	if tam%2==0:
		while total>-1 and i<tam:
			if H[i]=='[':
				total=total+1
			else:
				total=total-1
			i=i+1
		if total==0:
			return True
		else :
			return False
	else:
		return False
tam=random.randint(1,10)
M=list()
for i in range(tam):
	M.append(random.choice("[]"))
cadena=""
for i in range (tam):
	cadena=cadena+ M[i]
print cadena
print comprobarllaves(cadena)

```

Instalamos cde

> sudo apt-get install cde

Empaquetamos el script

> cde python ejer5.py

Buscamos el archivo python.cde

> cd /cde-package/cde-root/Ejercicios

Y lo ejecutamos

> python.cde ejer5.py
> [][]
> True


_ _ _ 


#### Ejercicio 4:

##### Comprobar si el procesador o procesadores instalados tienen estos flags. ¿Qué modelo de procesador es? ¿Qué aparece como salida de esa orden?

Usamos :

> cat /proc/cpuinfo

Para saber el tipo de procesador que usamos, en mi caso es:

Intel(R) Core(TM) i5-2450M CPU @ 2.50GHz

Al ejecutar

> egrep '^flags.*(vmx|svm)' /proc/cpuinfo

Aparece repetido 8 veces esta sentencia

![egrep '^flags.*(vmx|svm)' /proc/cpuinfo](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura1_zpsvek4hpvu.png)



#### Ejercicio 5:


##### Comprobar si el núcleo instalado en tu ordenador contiene este módulo del kernel usando la orden kvm-ok.
![kvm-ok](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura_zpskjre6xpq.png)

##### Instalar un hipervisor para gestionar máquinas virtuales, que más adelante se podrá usar en pruebas y ejercicios.

Tengo instalado virtualbox y vagrant 