# Que es Express.js

Express es un framework web transigente, escrito en JavaScript y alojado dentro del entorno de ejecución NodeJS. El modulo explica algunos de los beneficios clave de este framework, como configurar tu entorno de desarrollo y como realizar tareas comunes en desarrollo y publicación web.

### Primeros pasos para crear una aplicacion del lado del backend con Express.js

primeramente debemos tener bien definido nuestro entorno de desarrollo con npm, ya sabes inicializar el git, las dependencias de npm, prettier, nodemon, los archivos como eslint, editorConfig, gitignore, etc. lo siguente es comenzar a declara las princiaples constantes de nuestro servidor de manea que podamos comprobar si este se encuentera operativo. asi:

``` Js
console.log('Starting ...');

const express = require('express');

const app = express();

const port = 3000;


app.get('/', (req, res) => {

res.send('hola este es mi server en express');

})

  

app.listen(port,() => {

console.log('Server Port: ' + port);

})
```

Podemos observar que en primera intancia importamos a express que es la dependencia misma de expres que nos crea un constructor sobre la constante app. luego hacemos otra constante con el puerto en que se estara ejecutando nuestro sevidor.

para eso debemos crear un router en este caso app.get(); envia el contenido a nuestro usuario. pero para que nuestro usuario pueda acceder a nuestro servidor debemos tener el servidor en escucha ya que si no escucha ninguna peticion no podra interactuar con el usuario, y para eso llamamos a app.listen(). como dije esta pone en escucha a nuestro servido en base el puerto que le pasamos previamente. que en nuestro caso era el puerto 3000.

## Routing con express.js

los primero pasos para hacer routing que es basicamente que en el la url de nuestro servidor luego de la / podamos crear diferentes rutas como platzi.com/cursos o platzi.com/estudiantes.

en node com expres el routing se lleva a cabo de la siguente manera:

```js
app.get('/', (req, res) => {

res.send('hola este es mi server en express');

})

app.get('/products', (req, res) => {

res.json({

name: 'Producto 1',

price: '1000'

});

} )


app.get('/nueva-ruta', (req, res) => {

res.send('Esta es Una nueva ruta');

})
```

como ves en esta caso estamos creando 3 rutas difentes:

- /
- /products
- /nueva-ruta

## Api Restfull


# Get: Recibir parametros:

cuando nos referimos a get dentro de una api que en **Ingles** seria obtener, le estamos obteniendo parametros gracias a los endpoints que definimos previamente, gracias a esto podemos obtener las ids objetos o contenido en general. para luego procesarlos y hacer lo querramos.

> Los endpoints son las URLs de un API o un backend que responden a una petición. Los mismos entrypoints tienen que calzar con un endpoint para existir. Algo debe responder para que se renderice un sitio con sentido para el visitante.


## Get: Parametros en Query:


http://localhost:3000/users?limit=10&offset=200


## Como crear nuestro primer servicio:

#### The Clean Architecture

![[Pasted image 20220822113622.png]]

![[Pasted image 20220822113650.png]]
  

Creamos nuestra estructura

### products.services.js

```jsx
const faker = require('faker');

class ProductsService {
  constructor() {
    this.products = [];

    this.generate(); // Iniciamos nuestros servicios de usuarios
  }

  generate() {}

  // Funciones para los servicios
  create() {}

  find() {}

  findOne(id) { // Devolvemos un solo dato}

  update() {}

  delete() {}
}

module.exports = ProductsService;
```

Nuestro metodo generate se va a encargar de hacer el llamado a faker y setear los datos

```jsx
generate() {
    const limit = 10;

    // Push de productos
    for (let i = 0; i < limit; i++) {
      this.products.push({
        id: faker.datatype.uuid(),
        nombre: faker.commerce.productName(),
        precio: parseInt(faker.commerce.price(), 10), // Numero en base 10
        descripcion: faker.lorem.sentence(),
        imagen: faker.image.imageUrl(),
      });
    }
  }
```

El metodo find se encarga de retornar todo los datos y findOne se encarga de retornar un solo dato

```jsx
find() {
    // Devolvemos los datos
    return this.products;
  }

  findOne(id) { // Devolvemos un solo dato
    return this.products.find((item) => item.id == id);
  }
```

Para usar los servicios en nuestros router se importa y setea en los lugares requeridos

```jsx
const ProductsService = require('../services/products.services');

//...

// Servicio de productos
const service = new ProductsService();
```

```jsx
router.get('/', (req, res) => {
  // Traemos los datos desde nuestros servicios
  const products = service.find();

  res.json(products); // Respuesta
});

//...

router.get('/:id', (req, res) => {
  const { id } = req.params; // Destructuracion del parametro
  const product = service.findOne(id); // Lo trae del servicio

  res.json(product); // Respuesta con el parametro
});
```


## Que es un middleware?
Middleware es software que permite uno o más tipos de comunicación o conectividad entre dos o más aplicaciones o componentes de aplicaciones en una red distribuida. Al facilitar la conexión de aplicaciones que no fueron diseñadas para conectarse entre sí, y al brindar funcionalidad para conectarlas de manera inteligente, el middleware agiliza el desarrollo de aplicaciones y acelera el tiempo de comercialización.

#### Casos De Usos:
- Funcionar como pipes.
- validar Datos.
- Capturar errores.
- Validar permisos.
- Controlar accesos.


***

**Control de errores con la libreria: BoomJs**
**Validacion de datos con la api: Joi**

Middlewares polulares con expres:

## CORS

_Middleware_ para habilitar CORS (Cross-origin resource sharing) en nuestras rutas o aplicación. [http://expressjs.com/en/resources/middleware/cors.html](https://expressjs.com/en/resources/middleware/cors.html)

## Morgan

Un _logger_ de solicitudes HTTP para Node.js. [http://expressjs.com/en/resources/middleware/morgan.html](https://expressjs.com/en/resources/middleware/morgan.html)

## Helmet

Helmet nos ayuda a proteger nuestras aplicaciones Express configurando varios encabezados HTTP. ¡No es a prueba de balas de plata, pero puede ayudar! [https://github.com/helmetjs/helmet](https://github.com/helmetjs/helmet)

## Express Debug

Nos permite hacer _debugging_ de nuestras aplicaciones en Express mediante el uso de un _toolbar_ en la pagina cuando las estamos desarrollando. [https://github.com/devoidfury/express-debug](https://github.com/devoidfury/express-debug)

## Express Slash

Este _middleware_ nos permite evitar preocuparnos por escribir las rutas con o sin _slash_ al final de ellas. [https://github.com/ericf/express-slash](https://github.com/ericf/express-slash)

## Passport

Passport es un _middleware_ que nos permite establecer diferentes estrategias de autenticación a nuestras aplicaciones. [https://github.com/jaredhanson/passport](https://github.com/jaredhanson/passport)

> Puedes encontrar más _middlewares_ populares en el siguiente enlace: [http://expressjs.com/en/resources/middleware.html](https://expressjs.com/en/resources/middleware.html)


### Recomendaciones antes de pasar a produccion:

- Cors
- Https
- Procesos de build
- Remover logs
- Seguridad(Helmet)
- Testing

---

## Manejando un pool de conexiones:


las conexiones a la base de datos las estamos haciendo con una libreria de node: node-posgres ya que la base de datos que estamos empleando es una de posgres con docker lo cual facilita su uso y escalabildad.

### Poll de conexiones:
para hacer una conexion con nuestra base de datos nuestra api estaba creando una instancia nueva de esta cada ves que le haciamos una peticion, de tal manera que no es lo suficientemente eficiente de manera que vamos a general un pool de conexiones que es: Un pool de conexiones es un conjunto limitado de conexiones a una base de datos, que es manejado por un servidor de aplicaciones de forma tal, que dichas conexiones pueden ser reutilizadas por los diferentes usuarios.

![[Pasted image 20220827083453.png]]

## variables de ambiente:

hasta este momento hemos estado comentiendo una mala practica, estamos situando los datos de conexion a la base de datos directamente en el codigo de la mima api, la manera en la que se debaria realizar es pasarle a la api las variables de entorno requeridas para realizar la conexion y de esta manera no llevar las llaves de conexion a cualquier lugar donde clonemos nuestro repositorio.


### Que es un ORM?

> 💡Un ORM es un modelo de programación que permite mapear las estructuras de una base de datos relacionales.

.  
Al abstraer este tipo de programación, delegamos su implementación al backend, es decir, le añadimos una de responsabilidad a la capa transaccional del servidor:  
.  
✨Los beneficios son los siguientes:

-   Acciones como **_CRUD_** (Create, Read, Update, Delete) son administradas mediante ORM.
-   La implementación de **_seeds_** o semillas, nos permiten recuperar, mediante código, la estructura de una BD.

.  
Una de las bases teóricas para entender este modelo es mediante el conocimiento de **_DAO_** (Data Access Object) y **_DTO_** (Data Transfer Object), los cuales nos permiten desestructurar un ORM en módulos de abstracción para acceder a la DB y transferir datos desde la misma DB, respectivamente hablando.  
.  
🙃Los contras sería:

-   Delegación de responsabilidades al server
-   Descentralización de trabajo, directa, de una BD.


# Modelos


# Manejando el CRUD;
### Crear, actualizar y eliminar:

