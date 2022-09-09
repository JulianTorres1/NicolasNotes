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