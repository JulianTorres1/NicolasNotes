## 🙅 Eliminar Nodos

<h4>Apuntes</h4>

-   Existen 3 formas de eliminar nodos en el DOM

1.  **Remove Child**
    
    -   Podemos eliminar un nodo según a un método que proviene del padre y pasamos la referencia a eliminar
    
    ```jsx
    padre.removeChild(nodoAEliminar)
    ```
    
2.  **Remove**
    
    -   Es la evolución de remove child
    -   No esta soportado en internet explorer
    
    ```jsx
    nodoAEliminar.remove()
    ```
    
3.  **Replace Child**
    
    -   Nos permite remplazar un nodo
    
    ```jsx
    padre.replaceChild(nuevoNodo, aRemplazar)
    ```