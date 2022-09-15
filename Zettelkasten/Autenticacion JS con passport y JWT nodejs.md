[[Autenticacion vs autorizacion]]


## Passport Js

passport es un modulo de node js que nos facilita la autenticacion de credenciales dentro de nuestra api, agregando cosas como login con google, o diferentes servicios. por medio de la implementacion de [[Strategies]] o estrategias

[[Node js]]

para implementar una strategia de autenticacion con passport tenemos que:
1. crear una carpeta "strategies" donde guardaremos las diferentes forma que tendremos de autenticarnos en nuestro servicio ya sea con google, github, facebook, con una estrategia local o con cualquierta de las diferente formas que nos brinda passport.
2. en el archivo index.js dentro de la carpeta de authentication que allamos definido. le indicaremos a passport todas las estrategias que vamos autilizar
3. y finalmente agregamos las estrategias a nuestro routing que comunmente es `/login` .


