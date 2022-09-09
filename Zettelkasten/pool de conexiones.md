## Manejando un [[pool de conexiones]]:




las conexiones a la base de datos las estamos haciendo con una libreria de node: node-posgres ya que la base de datos que estamos empleando es una de posgres con docker lo cual facilita su uso y escalabildad.

### Poll de conexiones:
para hacer una conexion con nuestra base de datos nuestra api estaba creando una instancia nueva de esta cada ves que le haciamos una peticion, de tal manera que no es lo suficientemente eficiente de manera que vamos a general un pool de conexiones que es: Un pool de conexiones es un conjunto limitado de conexiones a una base de datos, que es manejado por un servidor de aplicaciones de forma tal, que dichas conexiones pueden ser reutilizadas por los diferentes usuarios.

![[Pasted image 20220827083453.png]]
