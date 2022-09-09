# Routing en express

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

