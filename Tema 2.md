# Tema 2
#### Ejercicio 1
##### Instalar alguno de los entornos virtuales de node.js (o de cualquier otro lenguaje con el que se esté familiarizado) y, con ellos, instalar la última versión existente, la versión minor más actual de la 4.x y lo mismo para la 0.11 o alguna impar (de desarrollo).
Para este ejercicio he instalado NVM para node.js, con el siguiente comando:

    curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.32.1/install.sh | bash

Las versiones que voy a instalar son la 6.9.0, 4.6.1 y la 0.11.16.
- v6.9.0
      nvm install v6.9.0
- v4.6.1
      nvm install v4.6.1

- v0.11.16
      nvm install v0.11.16

Para ver las versiones instaladas en el ordenador utilizamos NVM ls:

    ->     v0.11.16
    v4.6.1
    v6.9.0
    default -> v4.6.1
    node -> stable (-> v6.9.0) (default)
    stable -> 6.9 (-> v6.9.0) (default)
    unstable -> 0.11 (-> v0.11.16) (default)
    iojs -> N/A (default)
    lts/* -> lts/boron (-> v6.9.0)
    lts/argon -> v4.6.1
    lts/boron -> v6.9.0



##### Ejercicio 2
###### Como ejercicio, algo ligeramente diferente: una web para calificar las empresas en las que hacen prácticas los alumnos. Las acciones serían

- Crear empresa
- Listar calificaciones para cada empresa
- Crear calificación y añadirla (comprobando que la persona no la haya añadido ya)
- Borrar calificación (si se arrepiente o te denuncia la empresa o algo)
- Hacer un ránking de empresas por calificación, por ejemplo
- Crear un repositorio en GitHub para la librería y crear un pequeño programa que use algunas de sus funcionalidades.

#### Ejercicio 3
##### Ejecutar el programa en diferentes versiones del lenguaje. ¿Funciona en todas ellas?


#### Ejercicio 4
##### Crear una descripción del módulo usando package.json. En caso de que se trate de otro lenguaje, usar el método correspondiente.

#### Ejercicio 5
##### Automatizar con grunt y docco (o algún otro sistema) la generación de documentación de la librería que se cree. Previamente, por supuesto, habrá que documentar tal librería.


#### Ejercicio 6
##### Para la aplicación que se está haciendo, escribir una serie de aserciones y probar que efectivamente no fallan. Añadir tests para una nueva funcionalidad, probar que falla y escribir el código para que no lo haga (vamos, lo que viene siendo TDD).


#### Ejercicio 7
##### IConvertir los tests unitarios anteriores con assert a programas de test y ejecutarlos desde mocha, usando descripciones del test y del grupo de test de forma correcta. Si hasta ahora no has subido el código que has venido realizando a GitHub, es el momento de hacerlo, porque lo vas a necesitar un poco más adelante.


#### Ejercicio 8
##### Haced los dos primeros pasos antes de pasar al tercero.
