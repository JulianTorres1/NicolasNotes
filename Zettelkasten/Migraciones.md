# Migraciones:

Las migraciones son:

> Las migraciones son la forma en que Django **propaga** cambios en los modelos y los refleja en el esquema de bases de datos. **- Django.**

> Las migraciones son como un sistema de **control** de versiones para la base de datos. **- Laravel.**

> Es como un sistema de control de versiones para manejar los cambios desde el código y trackear los cambios en la base de datos. **- Sequelize.**

Básicamente, las migraciones **mantienen el historial** del esquema que se lleva en la base de datos. Es un sistema muy usado en ambientes de producción para **trackear** los **cambios** sin tener que replicar todo nuevamente _(creación de tablas, llaves foráneas, etc)_. Es decir, permite saber en qué punto estaba para saber qué es lo que se tiene que modificar.

–

**`sequelize.sync()`** empieza a leer los modelos, crea tablas y hace relist _(se sobrescribe información)_, no se aconseja que se corra en producción. Es mejor sincronizar con un sistema de migraciones.

Para correr migraciones se utiliza la librería **`sequelize-cli`** y se instala como dependencia de desarrollo con el comando **`npm i sequelize-cli -D`**.

Posteriormente, se crea un archivo de configuración **`.sequelizerc`** en la carpeta principal.

–

**`.sequelizerc`**:

```jsx
module.exports = {
  'config': './db/config.js',
  'models-paths: './db/models',
  'migrations-paths: './db/migrations',
  'seeders-path': './db/seeders',
}
```

-   **`config`** → Dónde se encuentra la configuración, esta configuración se encuentra la conexión hacia la BD. El cli tiene su propia conexión, independientemente de la conexión de la aplicación porque esas conexiones corren a nivel de terminal.
    
-   **`models-paths`** → Dónde se encuentran los modelos.
    
-   **`migrations-paths`** → Dónde se encuentran las migraciones.
    
-   **`seeders-path`** → Dónde se encuentran las semillas de información, sirve mucho para pruebas unitarias, end to end, donde se necesitan semillas de información que es como cargar varios datos de información a la BD.
    

–  
Se crean las carpetas **`migrations`**, **`models`**, **`seeders`** y el archivo **`config.js`** dentro de la carpeta **`db`**.