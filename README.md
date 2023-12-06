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
```
class SessionsController < ApplicationController
 	   def create
    	         @user = User.find_or_create_from_auth_hash(auth_hash)
    	         self.current_user = @user
    	         redirect_to '/'
                   end
          	  protected
          	  def auth_hash
            		request.env['omniauth.auth']
                 end
              end
```


## Pregunta:   Utilizando historias de usuario y Cucumber 

Utilizaremos el archivo dado en el examen para esta pregunta , comenzaremos ejecutando el servidor :  

![imagen](https://github.com/peg1163/PC5_CC3S2/assets/92898224/445bb7ab-62fa-4622-8fa0-50092c18630b)

vemos que se ejecuta correctamente , tambien podemos ver algunas peliculas en la tabla , pasaremos al siguiente paso , ejecutar bundle exec cucumber :

![imagen](https://github.com/peg1163/PC5_CC3S2/assets/92898224/f8b84a63-08c4-406b-bd77-81118161a5f6)

Vemos que los escenarios no logran pasar la "prueba"
Comenzaremos quitando los pendientes en el codigo , cosa que al ejecutarlo  nos da lo siguiente :

![imagen](https://github.com/peg1163/PC5_CC3S2/assets/92898224/da60c3ad-fca7-4944-a575-942166f7e4e2)

Ya quitados los pendientes , vemos que hay algunos errores , por ejemplo el primer error que nos encontramos es que no detecta las tablas que ingresamos , esto es porque no hemos definido una tabla al comenzar la prueba , cambiamos un poco el cosigo : 

![imagen](https://github.com/peg1163/PC5_CC3S2/assets/92898224/42312630-bf4e-4562-82d4-4fde4b270c48)

Y ejecutamos nuevamente el  codigo :

![imagen](https://github.com/peg1163/PC5_CC3S2/assets/92898224/fc76f43e-05a1-40fe-b83f-87341fd75331)

Observamos que los errores con el numero de filas ha desaparecido , pero uno nuevo empieza ,el cual nos impide pasar todas las pruebas .




