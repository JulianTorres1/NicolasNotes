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



# Que son las Promesas?

Las promesas son una sintaxis mas elegante y legible de realizar callbacks, creando así un código mucho más escalable y entendible para todas las personas.  
Una promesa al final no deja de ser un callback, solo que, con la novedad de tener estados, las promesas cuentan con 3 estados, resuelta, en progreso y en fallo.  
Para utilizar una promesa solo debemos de instanciar una nueva, una promesa en si es una función que recibe dos parámetros, resolve y reject, que son los dos estados de una promesa.  
Utilizamos resolve para retornar el valor deseado cuando una función se ejecute y utilizamos reject para cuando una función retorna un valor no deseado.

```JavaScript
New Promise( (resolve, reject) => {  
	…code  
	If(code === true){  
	resolve(correctValue);  
}else {  
	Reject(wrongValue);  
	}  
});  
```

Para poder obtener los valores que retorna una función debemos utilizar su propiedad .then, esta propiedad es una función que recibe un callback el cual tendrá como parámetro el valor retornado con resolve o reject.  
Siempre que usemos una promesa además de realizar la propiedad .then debemos invocar la propiedad .catch, la cual es un callback que recibe como parámetro el error ocurrido en caso de haber sucedió uno.

```JavaScript
myPromise(‘Parameter’)  
.then( data => console.log(data) )  
.catch( err => console.log(err) );
```



# Async | Await

Para evitar que todo se vea asíncrono, y que la sintáxis sea más legible las operaciones secuenciales como hacer un archivo que se procese, subirlo para tener una URL y de ahí mandarla a una base de datos.  
Async y Await nos permite definir una función de forma explícita como asíncrona y esperar a que la función termine. No estará bloqueando el hilo principal, pues estará esperando a que se resuelva con el event loop

```JavaScript
// La palabra async  la convierte inmediatamente en asíncrona.
async function hola(nombre) {
    return new Promise(function (resolve, reject) {
        setTimeout(function () {
            console.log('Hola, '+ nombre);
            resolve(nombre);
        }, 1500);
    });
}

async function hablar(nombre) {
    return new Promise( (resolve, reject) => {
        setTimeout(function() {
            console.log('Bla bla bla bla...');
            resolve('Hay un error');
        }, 1000);
    });
}

async function adios(nombre) {
    return new Promise( (resolve, reject) => {
        setTimeout(function() {
            console.log('Adios', nombre);
            resolve();
        }, 1000);
    });
}


// Await solo es válido dentro de una función asíncrona.
async function main() {
    let nombre = await hola('Nicolas');
    await hablar();
    hablar(); // Para hacer que se ejecute en segundo plano no debe existir el await
    await hablar();
    await adios(nombre);
    console.log('Termina el proceso');
}

// Esto nos permitirá saber si nuestra función se está ejecutanod de forma asíncrona.
console.log('Empezamos el proceso');
main();
console.log('Va a ser la segunda instrucción')

```


# Globals:

**RESUMEN**:

---

Los modulos globales son módulos del core.  
Una de las funciones muy usadas en Node es setInterval, clearInterval, para evaluar en n tiempo si el servidor está caído o no.

**TIP**: Si no tengo que usar variables globales no usarlas, pues son un foco de problemas

```JavaScript
console.log(global)

// Salida:

/*Object [global] {
    global: [Circular], ---> Dependencias ciruculares.
    clearInterval: [Function: clearInterval],
    clearTimeout: [Function: clearTimeout],
    setInterval: [Function: setInterval],
    setTimeout: [Function: setTimeout] {
      [Symbol(nodejs.util.promisify.custom)]: [Function]
    },
    queueMicrotask: [Function: queueMicrotask],
    clearImmediate: [Function: clearImmediate],
    setImmediate: [Function: setImmediate] {
      [Symbol(nodejs.util.promisify.custom)]: [Function]
    }
  }
*/


require(); // nos va a permitir acceder a caulqueir módulo.

let i =0; //  Inicializo contador en cero
let intervalo = setInterval(() => {  // Asigno el setInterval a una variable intervalo para poder operarla luego.
    console.log(" Alejandro "); // Imprimo mi nombre
    if (i === 3){ // Con i ===3 imprima mi nombre hasat que de cero llega a 3 y luego haga clearInterval.
        clearInterval(intervalo); 
    }
    i ++;
}, 1000);


setImmediate(()=>{
    console.log("Ya mismo")
})

```

---
## Console
  
Con console podemos imprimir todo tipo de valores por  
nuestra terminal.

-   **console.log**: recibe cualquier tipo y lo muestra en el consola.
-   **[console.info](http://console.info)**: es equivalente a log pero es usado para informar.
-   **console.error**: es equivalente a log pero es usado para errores.
-   **console.warn**: es equivalente a log pero es usado para warning.
-   **console.table**: muestra una tabla a partir de un objeto.
-   **console.count**: inicia un contador autoincremental.
-   **console.countReset**: reinicia el contador a 0.
-   **console.time**: inicia un cronometro en ms.
-   **console.timeEnd**: Finaliza el cronometro.
-   **console.group**: permite agrupar errores mediante identación.
-   **console.groupEnd**: finaliza la agrupación.
-   **console.clear**: Limpia la consola.


## Errores (Try/Catch)

Cuando se genera un error, node propaga el error hacia arriba, hasta que esta es caputado. si el error no se captura node se detiene.

> Siempre que sea posible debemos capturar todos los errores que se puedan generar en nuestros hilos.

Non permite caputar los errores:

```JavaScript
function seRompe(a) {
	return a + z;
}

try {
	seRompe(10);
} catch (error) {
	console.error('Algo Se ha roto!')
}
```


# Child_Process | Procesos Hijos

El módulo de procesos secundarios de Node.js (**child_process**) tiene dos funciones **spawn** y **exec**, mediante las cuales podemos iniciar un proceso secundario para ejecutar otros programas en el sistema.

La diferencia más significativa entre child_process.spawn y child_process.exec está en lo que spawn devuelve un stream y exec devuelve un buffer.

-   Usa **spawn** cuando quieras que el proceso hijo devuelva datos binarios enormes a Node.
-   Usa **exec** cuando quieras que el proceso hijo devuelva mensajes de estado simples.
-   Usa **spawn** cuando quieras recibir datos desde que el proceso arranca.
-   Usa **exec** cuando solo quieras recibir datos al final de la ejecución.

Un buen blog para revisar mas del tema:

[Diferencia entre spawn y exec de child_process de NodeJS - michelletorres](https://blog.michelletorres.mx/diferencia-entre-spawn-y-exec-de-child_process-de-nodejs/)

##### Ejemplo:

```JavaScript
const { exec } = require('child_process');
const { stdout } = require('nodemon/lib/config/defaults');

exec('neofetch', (err, stdout, sterr) => {
    if (err) {
        console.error(err)
        return false;
    } else {
        console.log(stdout);
    }
})
function seRompe(a) {
    return a + z;
}

```

# OS:

El modulo de Node para OS me permite acceder a elementos de muy bajo nivel, y es útil en diferentes contextos.

---

```JavaScript
const os = require('os');

console.log(os.hostname());//  Voy a saber el hostname de la máquina
console.log(os.networkInterfaces());// Puedo acceder a mi interfaz de red activas en mi máquina, puedo saber  IPVX
console.log(os.tmpdir())//-->Me muestra los directorios temporales, temproales una imagen que voy a procesar
console.log(os.homedir()) // Me permite saber cual es el directorio raíz
console.log(os.arch()); //----> Me devuelve la arquitecura de mi OS
console.log(os.platform());//---> Me dice en qué plataforma estoy
console.log(os.cpus());//--->podemos acceder a la información de las cpus de mi pc.
console.log(os.constants);//--->  Me muestran todos los errores de sistema.


//Acceder a espacios de memoria es muy útil para saber si tengo a memoria suficiente para realizar esta operación.
console.log(os.freemem());// ---> Me dice en bytes la memoria libre que tenemos
// console.log(kb(os.freemem()));
// console.log(mb(os.freemem()));
// console.log(gb(os.freemem()));
console.log(gb(os.totalmem())); // ---> Me muestra la memoria disponible del pc.

const SIZE = 1024;
function kb(bytes) { return bytes / SIZE }
function mb(bytes) { return kb(bytes) / SIZE }
function gb(bytes) { return mb(bytes) / SIZE }


```

## Process

El objecto process es una instancia de `EventEmitter`; podemos suscribirnos a el para escuchar eventos de node.

-   **UncaughtException**: Permite capturar cualquier error que no fue caputurado previamente. Esto evita que Node cierre todos los hijos al encontrar un error no manejado.
    
    ```js
    process.on('uncaughtException', (error, origen) => console.log(error, origen));
    ```
    
-   **exit**: Se ejecuta cuando node detiene el `eventloop` y cierra su proceso principal.
    
    ```js
    process.on('exit', () => console.log('Adios'));
    ``` 

# 📦 Gestion de paquetes de node por NPM:

 En node tenemos a nuestra dispocicion una herramienta d e gestion de paquetes increible, esta es npm este gestor nos provee de una gran variedad de paquetes que podremos implementar a nuestros proyectos de manera muy dinamica aparte de que la mayoria de paquertes son de codigo abierto.

npm puede ser una gran ayuda a la hora de desarrollar codigo, pero no entodos los casos de uso ya que si no tenemos en cuenta el costo de rendimiento de lo paquetes que importamos, podriamos estar ante una mala practica de desarrollo. 

##### 👉Aclaracion👈:

>🔥 El **import** de ES+6 todavía no viene incluido en Node.js, solo viene de forma experimental, en 2021 ya este no es experimental.

### formato de importacion de ES6 en 2022:
File: myOwnModule.js

```JavaScript
function sayHello() {
    console.log('Hello from inside a function of myOwnModule.js');
}

const property1 = 'Property 1 String value';
const property2 = 2;

module.exports = {sayHello, property1, property2}
};
```

File: index.js

```js
const myOwnModule = require('./myOwnModule');

console.log(myOwnModule.property1);
console.log('Property 2 value (number): ', myOwnModule.property2);
myOwnModule.sayHello();
```

**FORMATO ECMASCRIPT 6:**  
File: myOwnES6Module.mjs

```js
function sayHello() {
    console.log('Hello from inside a function of myOwnES6Module.mjs');
}

const property1 = 'Property 1 String value';
const property2 = 2;

export default {sayHello,property1,property2};
```

File: index.mjs

```js
import myOwnES6Module from './myOwnES6ModuleES6.mjs';

console.log(myOwnES6Module.property1);
console.log('Property 2 value (number): ', myOwnES6Module.property2);
myOwnES6Module.sayHello();
```

También se podría utilizar el operador de desestructuración para obtener las funciones y propiedades del módulo importado directamente en variables independientes, por ejemplo utiizando el primer ejemplo:

```js
const { sayHello, property1, property 2 } = require('./myOwnModule.js');
```


## Módulos útiles

Módulos que utilizaremos frecuentemente en nuestras aplicaciones como:

**_bycript_** : Permite encriptar un string generando un hash.

**_bycript.hash_** : Genera el hash del string, este método recibe por parámetros el string a encriptar, las veces que debe ejecutarse el script para generar un hash aleatorio y por ultimo una función que se encarga de capturar hash o el error que se presente.

**_bycript.compare_** : Permite comprar el hash con el string a encriptado y nos devuelve un true o false. `bycript.compare` recibe por parámetros el string a encriptado, luego el hash y por ultimo una función que captura la información o el error que se presente.

```js
//importamos el modulo
const bcrypt = require('bcrypt');
//declaramos el pass o palabra a encriptar
const passworld = '1234Segura';
//bcrypt.hash no permite generar un hash
bcrypt.hash(passworld, 10, function(error, hash) {
  console.log(hash);
//bcrypt.compare nos devuelve un boleano si hash y contraseña son iguales
  bcrypt.compare(passworld, hash, function(err, res) {
    console.log(res)
  });
});
```

**_moment_** : Logramos manipular fechas de manera eficiente.  
**_moment.format_** : Podemos darle un formato adecuado a nuestra fecha.

```js
//importamos el modulo
const moment = require('moment');

let ahora = moment();
//establecemos el formato a usar
let ahoraFormat = ahora.format('HH:mm:ss');


console.log(ahoraFormat);
```

**_sharp_** : Permite trabajar con imágenes

```js
//importamos el modulo
const sharp = require('sharp');
//ruta de la imagen a modificar
sharp('fondo-carro.jpg')
//scalamos la imagen a 500 de alto
  .resize(500)
//otorgamos una escala de grises
  .grayscale()
//generamos el archivo modificado
  .toFile('fondo-carro-small.jpg');
```

# Buffer

---

Un buffer es un espacio de memoria (en la memoria ram), en el que se almacenan datos de manera temporal.

Es la forma mas cruda en la que se pueden almacenar los datos. (Se guardan en **bytes** y no se especifica el tipo de dato)

En la consola, **los datos se muestran en formato hexadecimal**.

---

<h3>Creacion de un bufer básico</h3>

Para crear un buffer, con 4 espacios por ejemplo, podemos hacerlo con la siguiente sintaxis.

```javascript
let buffer = Buffer.alloc(4);
console.log(buffer); 
// Output:
//<Buffer 00 00 00 00>
```

### Otras formas de crear un buffer

Datos en un arreglo

```javascript
let buffer2 = Buffer.from([1,2,3]);
console.log(buffer2);
```

Datos de tipo string

```javascript
let buffer3 = Buffer.from('Hola');
console.log(buffer3);
console.log(buffer3.toString());
```

Guardar el abecedario en un buffer

```javascript
let abc =  Buffer.alloc(26);
console.log(abc);

for (let i = 0; i< abc.length; i++){
  abc[i] = i + 97;
}

console.log(abc);
console.log(abc.toString())
```


 