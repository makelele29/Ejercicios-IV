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
##### Como ejercicio, algo ligeramente diferente: una web para calificar las empresas en las que hacen prácticas los alumnos. Las acciones serían

- Crear empresa
- Listar calificaciones para cada empresa
- Crear calificación y añadirla (comprobando que la persona no la haya añadido ya)
- Borrar calificación (si se arrepiente o te denuncia la empresa o algo)
- Hacer un ránking de empresas por calificación
- Crear un repositorio en GitHub para la librería y crear un pequeño programa que use algunas de sus funcionalidades.

Para este ejercicios he utilizado express, jade y MySQL para la realización de la web.
He creado un repositorio y he añadido un script para la instalación y funcionamiento de la web en cualquier sistema Ubuntu.

[Repositorio del ejercicio 2](https://github.com/makelele29/Ranking-Empresas)

#### Ejercicio 3
##### Ejecutar el programa en diferentes versiones del lenguaje. ¿Funciona en todas ellas?
Funciona en todas ellas a la perfección.

![prueba de que va bien](http://i1356.photobucket.com/albums/q726/Makelele_Junior/Captura%20de%20pantalla%20de%202016-10-22%2017-15-24_zpskdqq2onq.png?t=1477063318)

#### Ejercicio 4
##### Crear una descripción del módulo usando package.json. En caso de que se trate de otro lenguaje, usar el método correspondiente.

    {
      "name": "application-name",
      "version": "0.0.1",
      "private": true,
      "scripts": {
        "start": "nodejs ./bin/www"
      },
      "dependencies": {
        "express": "~4.0.0",
        "static-favicon": "~1.0.0",
        "morgan": "~1.0.0",
        "cookie-parser": "~1.0.1",
        "body-parser": "~1.0.0",
        "debug": "~0.7.4",
        "jade": "~1.3.0",
        "mysql": "~2.9.0",
        "express-session": "^1.14.1"
      }
    }

#### Ejercicio 5
##### Automatizar con grunt y docco (o algún otro sistema) la generación de documentación de la librería que se cree. Previamente, por supuesto, habrá que documentar tal librería.

Nos creamos en la raiz de nuestro proyecto un archivo __gruntfile.js__

    'use strict';

    module.exports = function(grunt) {

      // Configuración del proyecto
      grunt.initConfig({
      pkg: grunt.file.readJSON('package.json'),
      docco: {
          debug: {
          src: ['*.js'],
          options: {
              output: 'docs/'
          }
          }
      }
      });

      // Carga el plugin de grunt para hacer esto
      grunt.loadNpmTasks('grunt-docco');

      // Tarea por omisión: generar la documentación
      grunt.registerTask('default', ['docco']);
    };

Instalamos el grunt-docco y creamos documentación

![Ejercicio 5](http://i1356.photobucket.com/albums/q726/Makelele_Junior/ejer5_zpsoldwwlbq.png)

Tendremos una carpeta __docs/__ con toda la documentación.


#### Ejercicio 6
##### Para la aplicación que se está haciendo, escribir una serie de aserciones y probar que efectivamente no fallan. Añadir tests para una nueva funcionalidad, probar que falla y escribir el código para que no lo haga (vamos, lo que viene siendo TDD).
    app.post('/iniciar',function(req, res){
        var bd=BD();
        bd.query("SELECT DNI,nombre FROM USUARIOS WHERE DNI="+req.body.dni+" AND clave="+req.body.clave,function(error,resultado,fila){
          assert.ok(!error,"Error en el select de usuarios");
          assert.notEqual(resultado.length,0,"No hay ningun resultado");
          session.dni=resultado[0].DNI;
          session.nombre=resultado[0].nombre;
          res.redirect(session.pagina);
        });

    });


#### Ejercicio 7
##### IConvertir los tests unitarios anteriores con assert a programas de test y ejecutarlos desde mocha, usando descripciones del test y del grupo de test de forma correcta. Si hasta ahora no has subido el código que has venido realizando a GitHub, es el momento de hacerlo, porque lo vas a necesitar un poco más adelante.

    var assert = require('assert');
    var mysql = require('mysql');
    //Funcion para conectar a la base de datos
    function BD(){
      var conexion = mysql.createConnection({
        host: 'localhost',
        user: 'root',
        password: '1',
        port: 3306,
        database: 'ranking'
      });
      return conexion;
    }
    describe("Prueba de test",function(){
      it("Login",function(done){

        var bd=BD();

        bd.query("SELECT DNI,nombre FROM USUARIOS WHERE DNI=111 AND clave=111",function(error,resultado,fila){
          console.log(resultado.length);
          assert.ok(!error,"Error en el select de usuarios");
          assert.notEqual(resultado.length,0,"El usuario introducido no es correcto");
          bd.end(done);
        });

      });
    });

He probado el test con un usuario que estaba y con otro que no.

![ejer7](http://i1356.photobucket.com/albums/q726/Makelele_Junior/ejer6_zpsvrfjdkqd.png)


#### Ejercicio 8
##### Haced los dos primeros pasos antes de pasar al tercero.
![](http://i1356.photobucket.com/albums/q726/Makelele_Junior/ejer8_zpsxgc7iruo.png)
