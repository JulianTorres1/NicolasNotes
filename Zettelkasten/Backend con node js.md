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

[[Routing con express.js]]

[[Api]]


[[Get]]

[[API Services]]

[[Recomendaciones antes de pasar a produccion]]:

[[pool de conexiones]]:
 
[[variables de ambiente]]:

[[ORM]]

[[Migraciones]]

[[Empaquetadores]]

[[Compiladores o Trasnpiladores]]

[[Consulta de Datos]]