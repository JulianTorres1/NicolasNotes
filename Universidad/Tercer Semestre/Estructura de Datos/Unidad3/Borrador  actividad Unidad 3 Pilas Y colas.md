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


#### 7. Explique textual y gráficamente cual es el algoritmo o proceso para contar contar los elementos de una Cola, desde el primero que entra (la Cabeza) hasta el último que entra (el final). Hacer el ejemplo en Java.

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

#### 8. Explique textual y gráficamente cual es el algoritmo o proceso para saber si una Cola  está vacía o no. Hacer un ejemplo en Java.

hay muchas maneras de hacer lo pero una de las mas sensillas es utilizando el metodo .size, este nos devuelve el numero de elementos que tengamos dentro de nuestra cola. por lo que haciendo una comparacion booleana en un if podemos determinar si este se encuentra vacio o no: como podemos ver en el siguente ejemplo:

```Java
if (cola.size() == 0) {  
    System.out.println("La cola esta vacia");  
} else {  
    nuemeroDeElementos = cola.size();  
    System.out.println("La cola No! esta vacia con un " + nuemeroDeElementos + " elementos");  
}
```

de esta manera si la cantidad de elementos es 0 el arreglo esta vacio pero por otro lado si no es 0 este no esta vacio.

#### 9. Explique textual y gráficamente cual es el algoritmo o proceso para buscar un elemento en una Cola. Hacer un ejemplo en Java.

para buscar un elemento dentro dentro de nuestra cola empleamos el el metodo predefinido .contains() este metodo recore todos los nodos de nuestra cola comparando si el elemeto que le pasamos por parametro coninside con el que esta buscando. si lo que estamos buscando coincide este devuelve la ubicacion del mismo en la coleccion y si no nos devuelve un numero negativo. asi como podemos ver en este ejemplo que nos devuelve un mensaje indicandonos si encontro lo que estabamos buscando:

```
System.out.println("dijite el elemento a buscar: ");  
String busqueda = sc.next();  
if (cola.contains(busqueda)) {  
    System.out.println("Objeto " + busqueda + " encontrado");  
}else {  
    System.out.println("Objeto No encontrado :C");  
}
```


#### 10.  Explique textual y gráficamente cual es el algoritmo o proceso para agregar un elemento a una Cola. Hacer un ejemplo en Java.

para agregar elementos a una cola en java de tipo Queue emplemos el metodo que el jdk de java nos ofrece, el metodo .add() este metodo ingresa el valor que le pasemos a nuestra pila o cola. como vermos en el siguente ejemplo:

```
// Primero Creamos nuestro objeto cola que a su ves es una cola tipo Queue  
Queue<String> cola = new LinkedList<String>();  

// añadimos nuestros elemetos haciendo uso de .add(); 
cola.add("Nicolas");  
cola.add("jonny");  
cola.add("Edwin");
```
   
#### 11. Explique textual y gráficamente cual es el algoritmo o proceso para sacar el próximo  elemento en una Cola. Hacer un ejemplo en Java.

para poder sacar un elemento de una cola en java, primero hay que en tener el principio FiFO de primero en entrar, primero en salir, esto es impresindible ya que de otro modo no lograriamos saber que elemento sacariamos, con esto claro para sacar un elemento de una cola en java empleamos el metodo .remove() que sacara como ya dijimos antes el ultimo elemento en la cola. como podemos ver en este ejemplo:

```

Queue<String> cola = new LinkedList<String>();  

// añadimos nuestro elemetos a eliminar:

cola.add("Nicolas");  

cola.remove(); // x3
```

#### 12. Explique textual y gráficamente cual es el algoritmo o proceso para obtener la posición de un elemento en una Cola. Hacer un ejemplo en Java.

Esta parte del algoritmo primero le pedimos al usuario que ingrese el contenido del elemento a buscar su indice. luego de esto hacemos un ciclo for que en cada ciclo ejecute un if  que recorra elemento por elemento y compare si el contenido que le brindo el usuario se coresponde por el que esta recorriendo en ese momento, y si no se corresponde expresarselo al usuario. como podemos ver en el siguente ejemplo:

```
System.out.println("ingrese el Contenido a encontrar su indice");  
String content = sc.next();  
  
for (int i = 0; i < cola.size(); i++) {  
    if (((LinkedList<String>) cola).get(i).contains(content)) {  
        System.out.println("El elemento " + content + " equivale al indice " + i);  
    }else {  
        System.out.println("el elemento no exite dentro de la cola");  
    }
```


#### 13. Explique textual y gráficamente cual es el algoritmo o proceso para obtener un elemento en la posición X  de  una Cola. Hacer un ejemplo en Java.

para buscar un elemento en espesifico en nuestra cola divimos el proceso en dos partes dentro de nuestro codigo:
	1. Parte #1: primero tenemos la parte de la recolecion del indice del elemento que queremos buscar para esto es bastante conveniente de cara al usuario mostrarle que indices estan disponibles dentro de nuestra cola, para eso hicimos uso de un ciclo for que recorre todos lo elementos de nuestra cola y les asigna un indice para que el usuario vea los indices que estan disponibles. luego mediante de el metodo Scaner el usuario indica un indice, el cual es el que nuestro progrma va a buscar.
	2. La Busqueda: Luego de obtener el indice obtenemos el contenido de nuestra cola mediante el metodo  .get(); que nos ofrece la clase del jdk LinkedList ya este nos devuelve el contenido de el indice al que apuntamos. y por ultimo se lo mostramos al usuario.

como podemos ver en el siguente ejemplo:

```
System.out.printf("Dijite  la posicion de elemento a Buscar\n");  
for (int i = 0; i < cola.size(); i++) {  
    System.out.println("Indices disponibles " + i);  
}  
  
int index = sc.nextInt();  
String elementoIndex = ((LinkedList<String>) cola).get(index);  
System.out.println("el elemento en el indice "+ index + " es " + elementoIndex);
```

#### 14. Explique textual y gráficamente cual es el algoritmo o proceso para eliminar un elemento cualquiera de una Cola. Hacer un ejemplo en Java.

para llevar a cabo al eliminacion de un componente que no se el de la cabeza de la cola, que normalmente seria lo mas comun, pero si nececitamos remover un elemento que no esta proximo a su salida podemos hacer uso del metodo .remove() pasandole el indice o el el contenido de nuestro elemento a eliminar: tal y como veremos en el siguente ejemplo:

```
System.out.println("dispone de los siguientes elementos: " + cola);  
System.out.println("Ingrese el Contenido del elemento a eliminar:");  
  
String Contenido = sc.next();  
cola.remove(Contenido);  
System.out.println("Resultado: " + cola);
```

#### 15. Explique textual y gráficamente cual es el algoritmo o proceso para agregar varios elementos a una Cola, es decir, agregar una subCola en otra Cola. Hacer un ejemplo en Java.

System.out.println(pila.pop());

#### 16. Explique textual y gráficamente cual es el algoritmo o proceso para eliminar varios elementos consecutivos o secuenciales de cualquier parte de la Cola, es decir, eliminar una subCola en otra Cola, per que no sea del final de la cola. Hacer un ejemplo en Java.

para esta parte del algoritmo vamos a dividirlo en dos caminos, uno es la de eliminar elementos segun cuantos querramos eliminar y eliminar elementos segun el contenido. para la primera parte solo nececitamos pedirle a usuario cuantos elementos va a eliminar con la clase scaner, luego de esto debemos hacer un ciclo for que tome en cuenta la cantidad de elementos a eliminar luego eliminar el siguente elemento en la cola gracias al metodo cola.remove();.
para la proxima opcion es eliminar elementos en base al contenido, para esto le solicitamos al usuario cuantos elementos va a eliminar y luego hacemos un for que por cada elemento a eliminar pregunte el contenido del elemento a eliminar luego hacer un try que pruebe si es posible eliminar dicho elemento. aqui un ejemplo:

```
System.out.println("""  
        Seleccione una opcion:            1. eliminar los siguientes elementos en la cola.            2. eliminar por contenido.        """);  
int opcionEliminar = sc.nextInt();  
  
if (opcionEliminar == 1){  
    System.out.println("Ingrese el nuemro de elementos que desea eliminar: ");  
    int cuantosEliminar = sc.nextInt();  
    for (int i = 0; i < cuantosEliminar; i++) {  
        cola.remove();  
    }  
    System.out.println("Elementos eliminados!, Cola: " + cola );  
} else if (opcionEliminar == 2) {  
    System.out.println("Cuantos elementos eliminara? ");  
    int cuantosIndex = sc.nextInt();  
    for (int i = 0; i < cuantosIndex; i++) {  
        System.out.println("ingrese el contenido del elemento " + i +" a eliminar: ");  
        String deleteElemento = sc.next();  
        try {  
            cola.remove(deleteElemento);  
        }catch (Exception e) {  
            System.out.println("No se encontro el elemento a eliminar: " + deleteElemento + "\n" + e.getMessage());  
        }  
    }  
    System.out.println("Elementos eliminados, Cola: " + cola);  
}
```



#### 17.  Explique textual y gráficamente cual es el algoritmo o proceso para borrar todos los elementos de una Cola, es decir, vaciar una Cola. Hacer un ejemplo en Java.

para vaciar nuestra cola haremos uso de la clase Iterator para poder iterar sobre nuestra cola para luego hacer un while que mientras que la cola contenga algun elemento haremos un cola.remove(); para vaciar nuestra cola. como vemos en este ejemplo:

```
System.out.println("Borrando ....");  
Iterator<String> itr = cola.iterator();  
  
while (itr.hasNext())  
{  
    cola.remove();  
    System.out.println("Borrando");  
}  
System.out.println("Todos los elementos han sido eliminados!, elementos: " + cola.size());  
System.out.println(cola);
```




# Pilas:

1.  Explique textual y gráficamente que es un una Pila, y cuales son las clases ofrece el SDK de Java para trabajar con Pilas:

una pila es un tipo de estructura de dato que principalmente tiene  dos tipos de operaciones la de apilar o desapilar o tambien conocidos como push and pop, las pilas son un tipo de estructura de dato que se basa en el principio de LIFO o del inglés Last In First Out, último en entrar, primero en salir. debido a este principio se diferencia de las colas. un ejemplo practico que se usa al momento de explicar las colas es el de la pila de platos y es que en si una pila de platos trabaja de la misma forma que una pila, de manera que para poner un plato seria un push y para sacar un plato un pop.
el JDK de java nos ofrece una serie herramientas para trabajar con las pilas, principalmente la clase Stack que nos permite crear diferentes objetos de esta, ofreciendonos tambien algunos metodos para trabajar con las colas como:

- Push
- Pop
- Peak
- Empty

![[Pasted image 20220715122245.png]]


    
2.  Explique por qué las pilas se consideran elementos fundamentales en las estructuras de datos.

Las pilas en la programacion en java son una herramienta fundamental ya que estas nos permiten los siguentes beneficios: una optimizacion mucho mayor con difererentes tipos de datos, organizar de una manera estandar y mucho mas consistente colecciones de datos, una cantidad inmenza de herramientas con la que trabajar las mismas.

    
3.  Explique textual y gráficamente  cual es el algoritmo o proceso para contar los elementos de una Pila, desde el primero hasta el último. Hacer un ejemplo en Java

Una de las diversas masneras que existen para contar los elementos de una pila, una de ellas es la siguente: primero cramos una variable donde guardemos la cantidad total de elementos que nuestro algoritmo va a contar, luego de eso creamos un ciclo for que se ejecute dependiendo el tamaño de elementos que conteng nuestra pila, y dentro del ciclo for solo nos queda imprimir que elementos se estan contando (por simple decoracion) y ir guardando los elementos dentro de la variable cantidad, para luego mostrarselos al usuario. tal y como podemos ver en el siguente ejemplo: 

```
int cantidad = 0;  
for (int i = 0; i < pila.size(); i++) {  
    System.out.println("Contando Elemento: " + i);  
    cantidad++;  
}  
System.out.println("cantidad total de elementos: " + cantidad);
```

4.  Explique textual y gráficamente  cual es el algoritmo o proceso para saber si una Pila está vacía o no. Hacer un ejemplo en Java:

para esta parte del algorimo simplemente nececitamos hacar una comprobacion con un If de manera que si pila.size() nos devuelve un valor superior a 0 significa que la pila no esta vacia pero por otro lado si la condicion no se cumple significa que la pila esta vacia tan simple como el siguente ejemplo:

```
if (pila.size() != 0) {  
    System.out.println("la Pila NO! esta vacia.");  
}else {  
    System.out.println("Pila esta vacia");  
}
```

    
5.  Explique textual y gráficamente cual es el algoritmo o proceso para recordar o mostrar los elementos de una Pila, desde el primero hasta el último. Hacer un ejemplo en Java:

para mostrar los elemento de una solo nececitamos imprimirla por pantalla:

```
System.out.println("Contenido de la Pila: " + pila);
```
    
6.  Explique textual y gráficamente cual es el algoritmo o proceso para recorrer o mostrar los elementos de una Pila, desde el último hasta el primero. Hacer un ejemplo en Java
    
7.  Explique textual y gráficamente cual es el algoritmo o proceso para agregar un elemento a una Pila. Hacer un ejemplo en Java

para agregar un elemento en la pila debemos llamar al metodo que nos ofrece la clase stack, el metodo .push() este metod recibe un valor Item que es cualquier tipo de datos que le querramos pasara la pila y esta lo agrege. como en el siguente ejemplo:

```
System.out.println("Ingrese texto a ingresar en la pila: ");  
pila.push(sc.next());  
// o individualmente  
pila.push("cadena de texto a ingresar en la pila");  
pila.push(10);
```

    
8.  Explique textual y gráficamente cual es el algoritmo o proceso para insertar un elemento a una Pila. Hacer un ejemplo en Java



9.  Explique textual y gráficamente cual es el algoritmo o proceso para eliminar el primer elemento de una pila. Hacer un ejemplo en Java:

para esta ocacion vamos a hacer uso de los indices de nuestra pila y que queremos eliminar el primer elemento de esta por lo que, lo primero que vamos a hacer es comprobar que la pila esta vacia ya que de lo contrario esta nos generaria un error devido a que no tiene elementos que eliminar lo cuan se podriva evitar con una excepcion on en java un try. luego de comprobar que nuestra pila no esta vacia vamos a eliminar el primer elemento de esta que siempre seria el elemento con index #0 y para eso hacemos uso las herramientas de la clase Stacks que en este caso para eliminar un elemento seria el metodo .remove(); al cual le pasamos el indice de nuestro elemento, luego lo eliminamos y se lo mostramos al usuario de una manera sensilla. como podemos ver en este ejemplo:

```
if (pila.isEmpty()  == false) {  
    System.out.println("Eliminado Primer elemento: " + pila.get(0));  
    pila.remove(0);  
    System.out.println("Estado de la pila: " + pila);  
}else {  
    System.out.println("pila true");  
}
```

    
10.  Explique textual y gráficamente cual es el algoritmo o proceso para eliminar el último elemento de una pila. Hacer un ejemplo en Java:

para eliminar el ultimo elemento en la pila debemos hacer lo que se conoce comunmente como pop cuando trabajamos con pilas. para eso debemos llamar al metodo que nos brinda la clase Stack. .pop()

```
System.out.println(pila.pop());
```
    
11.  Explique textual y gráficamente cual es el algoritmo o proceso para buscar un elemento de una pila. Hacer un ejemplo en Java

para buscar un elemento en la pila lo primero que debemos hacer es obtener el elemento que vamos a buscar para esto hacemos uso del objeto scaner o sc que creamos al principio de nuestro codigo, una vez tenemos el objeto a buscar lo siguiente es determinar si se trata de un entero o una cadena de texto, para eso hacememos un condicional que nos divida el flujo del algoritmo en dos, ahora bien para comprobar si el elemento a buscar esta en la pila hacemos uso de el metodo .contains() que comprueba si el elemento que le pasamos es esta en la linked list, de manera que devuelve true o false dependiendo si lo encontro: aqui tenemos un ejemplo:

```Java
System.out.println("Dijite su elemento a buscar: ");  
BusquedaString = sc.next();  
System.out.println("El elemento ingresado es numero ( y / n ): ");  
String str = sc.next();  
if (Objects.equals(str, "y")) {  
    int entero = Integer.parseInt(String.valueOf(BusquedaString));  
  
    if (pila.contains(entero)) {  
        System.out.println("Se encontro el elemento " + entero + " en la pila!");  
    }else {  
        System.out.println("No se encontro el elemento " + entero + " en la pila!");  
    }  
}else if (Objects.equals(str, "n")){  
    if (pila.contains(BusquedaString)) {  
        System.out.println("Se encontro el elemento: " + BusquedaString + " en la Pila!");  
    }else {  
        System.out.println("No! Se encontro el elemento: " + BusquedaString + " en la Pila.");  
    }}
```

    
12.  Explique textual y gráficamente cual es el algoritmo o proceso para agregar varios elementos consecutivos o secuenciales en cualquier posición de la Pila. Hacer un ejemplo en Java:

para este algoritmo lo primero es determinar cuantos elementos vamos a agregar a nuestra pila para eso le preguntamos a nuestro usuario por medio de la clase scaner y guardamos el numero de elemento que este determino de manera que hagamos un ciclo for que se ejecute el numero de veces que nuestro usuario determina: para agregar varios elemento creamos una nueva pila momentanea y en cada ciclo de nuestro for le preguntamos a nuestro usuario que va a añadir y añadirlo a nuestra pila temporal, luego de esto añadimos la pila temporal a la momentanea por medio del metodo addAll(); luego limpiamos la pila temporal para que la proxima ves que querramos añadir algo no esten los demas elementos. aqui un pequeño ejemplo de lo hablado:

```
System.out.println("Cuanto elementos va a agregar (ingresar cantidad en nuemeros): ");  
int cantidad = sc.nextInt();  
Stack<String> pilaadd = new Stack<>();  
for (int i = 0; i < cantidad; i++){  
    System.out.println("ingrese ele lemento #" + i);  
    pilaadd.push(sc.next());  
}  
System.out.println("agregando los elementos ...");  
try {  
    pila.addAll(pilaadd);  
}catch (Exception e){  
    System.out.println("no Se pudo agregar " + e);  
}
```
    
13.  Explique textual y gráficamente cual es el algoritmo o proceso para eliminar varios elementos consecutivos o secuenciales en cualquier posición de la Pila. Hacer un ejemplo en Java:


para punto hemos dessarrollado tres maneras de eliminar elementos de forma consecutiva deferentes elementos dentro de nuestra pila. la primera forma es mediante el metodo pop de nuestra clase Stack como ya sabemos este metodo nos prermite sacar el ultimo elemento en nuestra pila como en un principio esta esta pensada que funcione, para esto llamos al metodo scaner para perguntarle al usuario cuantos elementos desea sacar de la pila, para luego con ese dato hacer un for que se ejecute el numero de veses establesidas. la siguente manera que de desarrollamos fue la de eliminar desde un indice hasta otro, para esta parte desarrollamos un algorimo que primero pregunta desde que elemento a que elemento va a eliminar de manera que hacemos un for que valla preguntando cuales son los indices a eliminar. luego la tercera manera es la de eliminar por contenido. para esta parte creamos un array donde nuestro algoritmo le pregunta al usuario que ingrese el contenido de los elementos que desea eliminar. para siguente en base a ese array hacer un for que en base a cada elemento del array compare si este elemento se encuentra dentro de nuestra pila y si se encuentra eliminarlo, pero en caso de que no este mostrara un mensaje de error indicando que no se pudo eliminar: aqui el algoritmo desarrollado: 

```
System.out.println("""  
        Seleccione una opcion:            1. (pop) eleminar varios elementos al final de la pila.            2. eliminar varios indices de la pila.            3. eliminar por contenido.        """);  
int opcionBorrar = sc.nextInt();  
  
if (opcionBorrar == 1) {  
    System.out.println("cuantos Pop de la pila desea realizar: ");  
    int pops = sc.nextInt();  
    for (int i = 0; i < pops; i++) {  
        pila.pop();  
    }}else if (opcionBorrar == 2) {  
    System.out.println("Cuantos elementos va a eliminar: ");  
    int cuantos = sc.nextInt();  
    for (int i = 0; i < cuantos; i++) {  
        try {  
            System.out.println("Ingrese el elemento # " + i + " a eliminar:");  
            int eliminar = sc.nextInt();  
            pila.remove(eliminar);  
            if (pila.contains(eliminar)) {  
                System.out.println("No se elimino el elemento deseado!");  
            }else {  
                System.out.println("se elemento el elemento deseado!");  
            }            eliminar = 0;  
        }catch (Exception e) {  
            System.out.println("no se elimino el elemento deseado Error: " + e.getMessage());  
        }    }    System.out.println("Elementos eliminados: " + cuantos);  
    System.out.println("Estado De la pila: " + pila);  
} else if (opcionBorrar == 3) {  
    System.out.println("Cuandos elementos eliminara: ");  
    int cuantos = sc.nextInt();  
    String [] elementos = new String[cuantos];  
  
    for (int i = 0; i < cuantos; i++) {  
        System.out.println("ingrese el contenido del elemento a eliminar:");  
        elementos[i] = sc.next();  
    }    System.out.println(Arrays.toString(elementos));  
  
    try {  
        for (int i = 0; i < elementos.length; i++) {  
            if (pila.contains(elementos[i])) {  
                pila.remove(elementos[i]);  
            }        }    }catch (Exception e) {  
        System.out.println("Error: " + e.getMessage());  
    }    System.out.println("elementos: " + Arrays.toString(elementos) + " eliminados correctamente.");  
}
```

    
14.  Explique textual y gráficamente cual es el algoritmo o proceso para obtener la posición de un elemento  de la Pila. Hacer un ejemplo en Java

para esta parde el algorimo le preguntamos al usuario cual es el elemento que va buscar para hacer un for que recorra la pila buscando dicho elemento, y si lo encuentra nos devuelve el indice de dicho elemento, y en caso de que no nos devuelve un mensaje indicando que no pudo ser encontrado.

```
boolean found = false;  
System.out.println("ingrese el contenido del elemento a buscar su posicion: ");  
String busquedaE = sc.next();  
for (int i = 0; i < pila.size(); i++) {  
    if (pila.get(i).equals(busquedaE)) {  
        System.out.println("el elemento " + busquedaE + " se encontro ne la posicion " + i);  
        found = true;  
    }else if (!found) {  
        System.out.println("No se encontro el elemento " + busquedaE);  
    }
```

    
15.  Explique textual y gráficamente cual es el algoritmo o proceso para obtener un elemento a partir de una posición específica de la Pila. Hacer un ejemplo en Java


para poder encontrar el contenido en un indice espesifico primero debermos solicitar el indice al usuario luego de eso gracias a el metodo que nos ofrece la clase Stack. pila.elementAt(index); podemos obtener el dato que estamos buscando, de  asi como se muestra en el siguente ejemplo:

```
System.out.println("Ingrese el Indice del elemento a buscar:");  
int index = sc.nextInt();  
  
try {  
    System.out.println("Elemento en el indice " + index + " es: " + pila.elementAt(index));  
}catch (Exception e) {  
    System.out.println(Arrays.toString(new String[]{"No se encontro el elemento en el indice: error: " + e.getMessage()}));  
}
```
    
16.  Explique textual y gráficamente cual es el algoritmo o proceso para Eliminar todos los elementos (vaciar) de una Pila. Hacer un ejemplo en Java

para eliminar todos los elemento primero hay que guardar el tamaño inicial de la pila ya que para que cuando hagamos el ciclo for los elementos no se eliminaran del todo ya que el tamaño de la pila cambio mietras el for se ejecutava. ahora bien en el ciclo for se ejecuta el dependiendo el tamaño de nuestra pila eleiminado simpre el elemento del indice 0. como podemos ver en este ejemplo: 

```
int tamagno = pila.size();  
for (int i = 0; i < tamagno; i++) {  
    pila.remove(0);  
}  
System.out.println(pila);
```