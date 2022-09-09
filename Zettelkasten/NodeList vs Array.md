la principal diferencia entre los NodeList y los arrays es que los nodelist no dispones de varios metodos que los arrys si. algunos ejemplos de metodos que no se pueden ejecutar con los nodelist:
- .map
- .some
- .filter
- .reduce

> [[Buenas Practicas]]:

sin enbargo hay una forma de pasar un nodelist a un array: asi:

``` jsx
const nodeListAsArray =  [...nodeList];
```

de  manera que ahora que ya nuestro nodeList ya tendria todos los metodos de nuestros arrays. 