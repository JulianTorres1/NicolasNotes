el renderizado es el proceso en el cual nuestro codigo html pasa a al [[DOM]] de nuestro navegador para de esta manera ser mostrado al usuario

[[Virtual DOM]]

estrategias del render: 
- Dirty:
	- esta se utiliza cuando nececitamos hacer cambios en nuestro dom. pero simpre y cuando estos cambios sean pocos ya que hacer muchos cambios directos al dom es bastante costo.
- Re-Renderef:
	- es hacer una copia del DOM actual con javascrpit y hacer los cambios pertinentes y luego mandar a renderizar el dom de nuevo.

![[Pasted image 20220909182935.png]]

