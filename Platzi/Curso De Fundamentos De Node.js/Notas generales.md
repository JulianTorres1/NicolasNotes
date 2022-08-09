# Que es Node.js

nodejs es simplemente un entorno de ejecucion de JavaScrip fuera del navegador. nos sirve para llevar js a diferentes implementaciones, como utilizar js como el lenguaje de nuestro Backend,api's, apps de escritorio, etc.

Caracteristicas:
 - es concurrente.
 - motor V8. es un entorno de ejecucion creado por google, que basicamente conviente nuestro codigo de js a codigo maquina, de manera que es increiblemente rapido.
 - Todo funciona en base a modulos.
 - esta orientado a eventos. lo que nos permite programar de formas reactiva.

#### Origen: 
se crea en 2009 orientado a servidores por google.

## Que es el EventLoop:

es simple mente un bucle que esta todo el rato ejecutandoce de manera que todo lo que le mandemos funcione de forma asincrona de manera que es altamente concurrente. lo cual es espcialmente bueno para projectos que neccecitan bastante entrada y salida.

**Event Loop:** Se encarga de resolver los eventos ultra rápidos que llegan desde el Event Queue. En caso de no poder resolverse rápido, enviá el evento al Thread Pool.

**Thread Pool:** Se encarga de gestionar los eventos de forma asíncrona. Una vez terminado lo devuelve al Event Loop. El Event Loop vera si lo pasa a Event Queue o no.

![[Pasted image 20220806182603.png]]




#### Para que nos sirven las variables de entorno??

por lo general cuando nececitamos que nuestro codigo funcione con datos externos al codigo utilizamos variables de entorno ya que guardar dentro de nuestro codigo informacion delicada como claves de acceso, key de apis, usuarios, etc. es mejor que estos sean ingresados desde afuera de manera que no habra que cambiar el codigo cada ves que nececitemos cambiar alguna variable. aqui un ejemplo:

Codigo:
```
let nombre = process.env.NOMBRE || 'Sin Nombre';

console.log("Hola " + nombre);
```

ejecucion pasando parametros:

`` $ NOMBRE=Nicolas node Variables-De-Entorno.js  

salida:

`Hola Nicolas`

ejecucion sin pasar variables de entorno:

` $ node Variables-De-Entorno.js `

salida:

`Hola Sin Nombre`

**RESUMEN**:

---

**Desarrollo**  
**Nodemon.** Demons en linux, puedes tener procesos que ves ejecutandose  
nodemon + archivo al que quiero acceder detecta cambios, y ejecuta automaticamente el código.

sudo npm install -g nodemon

-   [Nodemon](https://nodemon.io/)

**Producción**

sudo npm install -g pm2

**PM2** Es un demonio administrador de procesos que me puede ayudar a administrar y mantener mi aplicación 24/7.

-   Voy a poner monitorizar el código para saber si algo se rompe.
-   Me permite ver dashboards de mi código, puedo ver que está corriendo.
-   Puedo ver el rendimiento de mi cpu
-   Con: pm2 stop + id —> me detiene el proceso que está en ejecución con ese ID.



# callbacks:
**Funciones Callback**  
Una funcion callback es una funcion que es pasada como argumento a otra funcion, para ser llamada(`called back`) en otro momento.  
La funcion que recibe como argumento otras funciones es denominada funcion de orden superior (higher-order function), esta contiene la logica correspondiente para ejecutar adecuadamente la funcion callback.

En el siguiente codigo

```javascript
setTimeout(console.log('Hello'), 1000)
```

`setTimeout` es una higher-order function y `console.log` es una callback function

ejemplo:
```JavaScript
function hola(nombre, miCallback) {

console.log("no soy asincrono");

setTimeout(function() {

console.log("hola " + nombre);

miCallback();

},1000)

}

  

hola('Nicolas',function () {

console.log("Proceso Terminado");

});
```

  ## callbacks Hell !!!!
  