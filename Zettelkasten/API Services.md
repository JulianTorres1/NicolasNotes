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
