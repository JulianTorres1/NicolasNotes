# Notas Generales De Estructura De Datos

Primero que todo el mapa general de la asigniatura con las cosas que debo saber al terminar cada unidad:

## Unidad # 1
#### Objetivos:
 - diferenciar las estructuras de datos mas utilizadas.
 - Entender los coseptos de **Apuntadores** para crear estructuras de datos.
 - Comprender la **Asignacion De Memoria** usando apuntadores.
 - **Operaciones** ( Buscar, Adicionar o eliminar, pegar, romper listas, ordenar, copias nodos) de una lista.
 - **Implementar** estructuras de datos en lenguajes java.
 - Conocer las distintas **aplicaciones** computacionales de cada estructura de datos.
 - **Desarrollar aplicaciones** usando algunas de las estructuras definidas.

### Que es una estructura de datos??
Consepto Personal:
Para mi la estructura de datos es la forma en que organizamos los datos. esto en base a un modelo matematica o logico de manera que se cree una forma optima de trabajar con estos datos.

definicion formal:
En programación, una estructura de datos es una forma de  organizar un conjunto de datos elementales (Un dato elemental es la mínima  información que se tiene en un sistema) con el objetivo de facilitar su manipulación.

***Una estructura de datos es simplemento "una forma organizada e intenciaonal de datos".***

Su proposito es permitir un eficiente almacenamiento y recuperacion de los datos.

existen las estructuras de datos estaticas y dinamicas. la diferenciaa entre esta es que las estaticas predefinen su tamano antes de la ejecucion de codigo por lo tanto siempre ocupan el mismo espacio en dicos mientras que las dinamicas van variando su tamagno mediante se ejecuta el codigo sobre estas.

##### Tipos De Datos - Clasificacion:


- Datos Estaticos:
	- arrays( Vectores / Matrices)

- Datos Dinamicos:
	- Lineales
	- Listas Enlazadas
	- Listas ( Pilas / Colas )
		- No Lineales:
			- Arboles
			- Grafos

### Estructuras De datos Impresindibles:

- Arrays o Vectores
- Lista Enlazada
- Tablas De Hash
- Pilas y las Colas (en Grafos)
- Grafos


#### Estructura De Datos Dinamicas:

Creaccion De nodos:

en java la creacion de nodos se basa en la siguiente sistaxsis:

```
tipo variable = new tipo; para crear un nodo
	// esto quedaria de la siguente forma:
char [] puntoVector = new char[100];
```

	 
El 100 es donde determinamos la cantidad de caracteres que almacenara nuestro vector cuando se cree.
 
**Asignacion:** puntero1 = puntero2 
esta operacion nos permite cambiar a donde esta apuntando el puntero1 a hacer que apunte al puntero2

**Comparacion:** puntero1 == puntero2 
esta operacion que nos devuelve un boleano nos permite determinar si las dos referencias de los punteros un iguales devolviendo true o false.

para que un puntero no apunte a ningun la lado le asignamosel valor de ` null `

#### Estructuras Lineales
	
![[Pasted image 20220421175943.png]]
	
#### Estructuras No Lineales:

![[Pasted image 20220421180028.png]]

#### Estructuras De Datos Estaticas:

Estas Estructuras se caracterizan por varios factores. primero porque su tamano es conocido antes de la ejecucion de comodigo y por concecuentes los tipos de datos que esta almacena son de tipo estatico por lo que no se pueden cambiar. Segundo se almacenan en memoria de forma secuencial ya sea como Una Pila o una cola:

![[Pasted image 20220421181652.png]]



# Arrays o Arreglos:
Un Array es un grupo de elementos de un mismo tipo al que se le adicionan dos valores por espacio, la clave y el valor la clave nos indica el espacio en el array al que nos estamos refieriendo y el valor es el contenido que guarda el array con referencia a la clave. su sintaxis en java es esta:

``` 
Clase nombreArreglo[] = new clase [numeroElementos];
	
// ambas son declaraciones válidas
int intArray[]; 
int[] intArray;

//Tipo de datos primitivos

byte byteArray[];
short shortArray[];
boolean booleanArray[];
long longArray[];
float floatArray[];
double doubleArray[];
char charArray[];

//Tipos de datos definidos por el usuario

// una serie de referencias a objetos de
// la clase MyClass (una clase creada por
// el usuario)

MyClass myClassArray[]; 
```


#### Estructuras de datos homogeneas:
En las estructuras de datos homogéneas todos los datos son del mismo tipo. Como ejemplo veremos los vectores, las tablas y, en general, las matrices n-dimensionales.