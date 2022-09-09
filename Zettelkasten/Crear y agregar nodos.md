basicamente cuando creamos nodos solo podemos crear de dos tipos:
- nodos elementos
	```JSX
	document.createElement(" el elemento a crear");
	```

- nodos texto
	```JSX
	document.createTextNode("El texto en si")
	```

> cuando creamos un elemento solo lo creamos en memoria, a la variable que lo asignemos. pero en **Ningun momento creamos un elemento en el DOM**

https://developer.mozilla.org/es/docs/Web/API/ParentNode/append

Como solo creamos, necesitamos formas de agregarlos al DOM, para ello, JavaScript nos provee de estas formas:  
.

-   `parentElement.appendChild()`: Agrega un hijo **al final** algún elemento

```
// Obtengo el elemento padre
const parentElement = document.querySelector("selector")
// Creo el nodo a insertar
const h3 = document.createElement("h3")
// Creo el texto del nodo
const texto = document.createTextNode("Hola!")
// Inserto el texto al nodo
h3.appendChild(h3)
// Inserto el nodo al padre
parentElement.appendChild(h3)
```

-   `parentElement.append()`: Es la evolución de `appendChild`, podemos agregar más de un nodo, puedes agregar texto y… no es soportado por Internet Explorer ¬¬!  
    .  
    Un polyfill es una adaptación del código para dar soporte a navegadores que no lo soportan, aquí está el polyfill de append:  
    [https://developer.mozilla.org/es/docs/Web/API/ParentNode/append#polyfill](https://developer.mozilla.org/es/docs/Web/API/ParentNode/append#polyfill)

```
// Obtengo el elemento padre
const parentElement = document.querySelector("selector")
// Agrego al elemento padre
parentElement.append("agrego un texto", document.createElement("div"))
```

-   `parentElement.insertBefore()`: Inserta nodos antes del elemento que le pasemos como referencia, este nodo de referencia **tiene que ser un hijo DIRECTO del padre**

```
// Obtengo el elemento padre
const parentElement = document.querySelector("selector")
// Creo un elemento
const titulo = document.createElement("h1")
// Obtengo la referencia del elemento del que quiero insertar antes:
const referencia = document.querySelector("selector")
// ¡Lo insertamos!
parentElement.insertBefore(titulo, referencia)
```

-   `parentElement.insertAdjacentElement()`: Inserta nodos según las opciones que le pasemos:
    1.  **beforebegin:** Lo inserta antes del nodo
    2.  **afterbegin:** Lo inserta despues del nodo
    3.  **beforeend:** Lo inserta antes de donde finaliza el nodo
    4.  **afterend:** Lo inserta después de donde finaliza el nodo

```
// Obtengo el elemento padre
const parentElement = document.querySelector("selector")
// Creo un elemento
const nodo = document.createElement("span")
parentElement.insertAdjacentElement("beforebegin", nodo)
```

