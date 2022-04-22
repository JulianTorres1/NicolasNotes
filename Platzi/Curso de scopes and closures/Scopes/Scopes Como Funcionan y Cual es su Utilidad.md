# Scopes Como Funcionan y Cual es su Utilidad En La Programacion Con Javascript:

Primero que todo y para sentar las bases un scope es a lo que le llamamos en castellano el alcance. el alcance en la programacion es una propiedad que adquieren las variables constantes etc. y en general los tipos de datos en nuestro algoritmo el scope es una propiedad que permite o deniega el acceso a una campo en funcion de como este sea declarado o ubicado dentro  del codigo, diferentes metodos de acceso a este seran o no posibles.

#### Scope Global:
El Scope Global como su nombre lo indica. funciona de tal manera que el campo que pose esta propiedad sea accesible desde cualquier parte del codigo porque lo que podemos acceder a este dato desde funciones, fat arrows functions, etc. por lo general se ven asi:

```
let variableGlobal = 'im Global lol';
```

#### Local Scope
En diferencia con las variales globales las variables con el scope de tipo local solo pueden ser acedidad desde la funcion o metodo en que fueron declaradas. de manera que fuera del el son inacecibles: ejemplo

```
let variableGlobal = 'hey im global';

const funcionConVariableLocal = () => {
	let variableLocal = 'hey im a local bro;
};

funcionConVarialeLocal(); 
variableLocal = 'trying to change it! ' // error ya que la variable no es global por lo tanto no se puede acceder desde afuera.

```

#### Block Scope:
Este tipo de scope es similar al Scope local pero con la diferencia este solo aplica para los tipos de datos let y const y mas espesificamente cuando estos se encuentran dentro de un bloque de codigo como este **{Bloque de codigo}** aqui un ejemplo:

```
const frutas = () => {
	if (true){
	var fruta1 = 'apple';
	let fruta2 = 'banana';
	const fruta3 = 'kiwi';
	console.log(fruta1, fruta2, fruta3); // se ejecutaran todas los console.log
	// ya que estan dentro del bloque
	}
	console.log(fruta1, fruta2, fruta3); // solo se ejecutara fruta ya que
	//su acceso es local en todo el bloque pero no para banana ni kiwi	
}

frutas();
```

