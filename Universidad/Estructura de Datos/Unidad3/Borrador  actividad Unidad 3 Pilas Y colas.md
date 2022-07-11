####  1.Explique textual y gráficamente que es un una Cola, y cuales son las clases ofrece el SDK de Java para trabajar con Colas

Respuesta:

Una cola es un tipo de estructura de dato que nos ayuda a trabajar con un flujo de datos muy en particulas, asi como su nombre lo dice las colas como en la vida misma son una secuencia de elementos que en lo principal se caracteriza por una logia first in fist out o primero en entrar primero en salir, de manera que si nosotros incertamos un elemento este se acumulara de manera ordenada con los demas y cuando queremos realizar la extraccion de un elemento, no se saldra cualquiera, saldra el primero que entro a la cola, exactamente como en la cola de un supermercado.


en java tenemos dos maneras generales de trabajar con las colas, la primera es utilizando la clase que nos ofrece la interfaz: queue con la que trabajaremos mediante la clase linkedlist dentro de java.util. algunos de los elementos que nos ofrece el queue son: add, offer, element, peek, poll, remove.
java no nos provee de clases predefinidas con las que se pueda dar el nombre a la cola y sola mente tener que operar con los metodos que esta trae devido a esto es presiso que definamos en comportamiento de la cola cada ves que tengamos pensado trabajar con una. de manera que  cada cola funciona  con una estructura de nodos de manera que cada elemento sabe a cual es el nodo que tiene atrar y nodo que tiene de frente de manera que sabremos en todo momento cual es el orden de la cola y cual es el ultimo y primero.

![[Pasted image 20220709094052.png]]
#### 3. Explique por qué las colas y pilas se consideran elementos fundamentales en las estructuras de datos.

Respuesta:

Las colas en java tienen una infidad de aplicaciones de las hace bastante requeridad, las colas no pueden servir para organizar datos de manera que querramos que se autogestionen, trabajos de forma ordenada de manera que alla un flujo constante y ordenado evitando congestiones.

#### 4. Explique gráfica y textualmente que es una cola con prioridades

Respuesta:

a diferencia de las colas normales la colas con prioridades son un tipo de cola que al momento de extraer su ultimo elemento esta ofrecera el elemento que disponga de una prioridad mayor en ese momento de manera que siempre tendremos a dispocision el elemento de mas prioridad.
![[Pasted image 20220711110719.png]]
#### 5.Explique gráfica y textualmente que es una Cola con comportamiento LIFO

Respuesta:

Cuando hacemos una cola basada en el comportamiento LIFO, en realidad estamos haciendo una pila ya que el comportamiento de Last Input First Output, por lo que no tendria mucho sentido.