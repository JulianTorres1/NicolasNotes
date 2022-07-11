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

en estructurtura de datos cuando empleamos una cola pero mas concretamente una cola que emplea la estructura de LIFO o el primero en entrar es el primero en salir, pero para ejemplificar este tipo de estructura de datos el ejemplo mas eficas es el de la pila de los platos, cuando tenemos una pila de platos y le agregamos otro mas lo logico es poner el plato a integrar en la parte de arriba por lo que cuando tengamos que sacar nuestro plato siempre sacaremos el ultimo que allamos puesto, y esto es igual en java por lo que cuando sacamos un elemento de nuestra cola tipo LIFO siempre sacaremos el ultimo que ingresamos.

![[Pasted image 20220711150542.png]]

#### 6. Explique gráfica y textualmente  que es una cola con comportamiento FIFO

en las colas tipo FIFO pasa lo contrario a las colas tipo LIFO como era de esperar. en las colas tipo FIFO su conportamiento se basa en que el primero en entrar es el primero en salir porlo que en java cuando tenemos una cola con varios elemento y ingresamos uno tendremos que sacar a todos los elemento que esten por delante de este para que el que ingresamos pueda salir. otro ejemplo muy acertado es el de la cola de un banco. cuando llegamos al banco hay dos posibles situaciones: la primera y la menos habitual y es que la cola del banco este vacia y en ese caso seriamos la primera persona en entrar asi que seriamos la primera en salir, o la segunda situacion y que ya alla una cola de personas previas a nuestra llegada por lo que para ser atendido debemos espera a que las demas personas salgan de la cola

![[Pasted image 20220711151606.png]]


#### 7.  1.  Explique textual y gráficamente cual es el algoritmo o proceso para contar contar los elementos de una Cola, desde el primero que entra (la Cabeza) hasta el último que entra (el final). Hacer el ejemplo en Java.

Respuesta:

para poder obtener el tamaño de una cola en java es tan simple como tener un objeto tipo cola instanciado previamente ya se sea que este tenga cero o varios elementos, para poder obtener el tamaño recurimos a un metodo de java.util este es: .size(); este metodo nos devuelve cuantos elemento tiene nuestra cola. tan simple como el siguente ejemplo:

```
package com.mycompany.trabajo3unidad3;  
  
import java.util.LinkedList;  
import java.util.Queue;  
  
public class queuelist {  
    public static void main(String[] args) {  
        System.out.println("ok ok");  
  
        Queue<String> cola = new LinkedList<>();  
  
        cola.add("Nicolas");  
        cola.add("Edwin");  
        cola.add("jonny");  
  
        System.out.println("Contenido De la Cola: " +cola);  
  
        int colaSize = cola.size();  
  
        System.out.printf("Tamaño de la cola: " + colaSize);  
    }  
}

```

