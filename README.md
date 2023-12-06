# Practica Calificada 5
## Preguntas iniciales 

* En las actividades relacionados a la Introducción de Rails los métodos actuales del controlador no son muy robustos: si el usuario introduce de manera manual un URI para ver (Show) una película que no existe (por ejemplo /movies/99999), verás un mensaje de excepción horrible. Modifica el método show del controlador para que, si se pide una película que no existe, el usuario sea redirigido a la vista Index con un mensaje más amigable explicando que no existe ninguna película con ese.
  
 Utilizaremos el archivo BDD-cucumber para este inciso ,si ejecutamos la aplicacion a un servidor local e intentamos entrar en alguna pelicula inexistente , esta nos mostrara lo siguiente :

 ![imagen](https://github.com/peg1163/PC5_CC3S2/assets/92898224/df18300d-1d8b-4a19-a473-0133a13a7755)

Se ve una respuesta un poco tosca de parte de nuestro servidor , modificaremos esta excepcion para que nos de un mensaje un poco mas amigable 
Para esto modificaremos ,en movie_controller, el metodo show , para que si ingresamos algun id que no sea aceptado entonces nos mostrara la tabla y un mensaje dicendonos que "No existe dicha pelicula"  

![imagen](https://github.com/peg1163/PC5_CC3S2/assets/92898224/89110721-f51c-4afb-87bd-5c50688637a4)

Ejecutaremos el servidor y provaremos las modificaciones hechas :

![imagen](https://github.com/peg1163/PC5_CC3S2/assets/92898224/2ef61665-d0cd-4288-b9a5-e6b9e00ac0d4)

Como vemos nos muestra el mensaje y las tablas de las peliculas para seleccionar otra


* En las actividades relacionados a Rails Avanzado, si tenemos el siguiente ejemplo de código que muestra cómo se integra OmniAuth en una aplicación Rails:
