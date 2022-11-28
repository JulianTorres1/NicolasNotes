Data Definition lenguage:

-   DML  
    o Data Manipulation Language o Lenguaje de Manipulación de Datos  
    o Lenguaje procedimental y declarativo  conjunto de instrucciones que apoyarán al proceso de construcción de la BD  
    o Las sentencias DML afectan los registros en una tabla. Estas son operaciones básicas que realizamos sobre datos tales como seleccionar algunos registros de una tabla, insertar nuevos registros, eliminar registros innecesarios y actualizar / modificar registros existentes.  
    o Opciones DML  
     SELECT: para seleccionar registros de tablas  
     INSERT: para insertar nuevos registros  
     UPDATE: para actualizar y modificar registros  
     DELETE: para eliminar registros existentes.
    
-   DDL  
    o Data Definition Language o Lenguaje de Definición de Datos  
    o Aquí ya se especifica el esquema de la BD, generando un diccionario de datos, las restricciones de integridad y las autorizaciones para que ciertos usuarios no vean cierto contenido.  
    o Sentencias DDL son las necesarias para poder modificar la BD, esquema y ESTRUCTURA de las tablas. Son las útiles para el diseño y control de objetos que se encuentran dentro de las BD.  
    o Opciones DDL  
     CREATE: Crear una nueva base de datos, una tabla o esquema.  
     ALTER: Alterar tabla existente, descripción de columnas, etc.  
     DROP: Eliminar objetos existentes de la BD.  
    o 3 objetos que manipularemos con el lenguaje DDL  
     Database  
     Tables  traducción a SQL de las entidades  
     View  se ofrece la proyección de los datos de la BD de forma entendible
    
-   DCL  
    o Lenguaje de Control de Datos  
    o Las declaraciones DLC son las encargadas de controlar el acceso de los usuarios a las BD.  
    o Opciones DDL  
     GRANT:  
    • Declaración que permite a los usuarios leer / escribir en objetos que digamos de la BD.  
     REVOKE:  
    • Es la que ofrece a los usuarios estar sin permiso de lectura / escritura en objetos de la BD.
    
-   TLC  
    o Lenguaje de Control de Transacciones  
    o Instrucciones que permiten administrar transacciones y tener integridad de datos dentro de las declaraciones SQL. Se gestiona a través de las siguientes declaraciones  
     BEGIN Transaction  
    • Nos permite abrir una transacción  
     COMMIT Transaction  
    • Ofrece confirmar una transacción  
     ROLLBACK Transaction  
    • Devuelve una transacción en caso de error cometido.