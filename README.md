# ExamenParcial-CC3S2
## Parte 2 :
Comenzamos ejecutando el comando rails new todo_app , para que rails nos genere una aplicacion y todas las dependencias necesarias para esta :

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/150dc246-1f6c-4714-8ae0-c0ca9ddfde17)

Ahora necesitamos generar la clase To Do , con ayuda de generate crearemos los directorios necesarios :

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/b28b034a-14fc-45a8-9978-3e848c859105)

¿Qué está pasando aquí ? 

* Respuesta : el comando rails generate nos genera los archivos para un modelo de ruby on rails , estos archivos son el modelo , los controladores,vistas y migraciones , esaa migracion tiene la caracteristica de tener un atributo llamado description de tipo string

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/c038e983-ef44-4d84-b33e-e93104752169)

Ahora que tenemos definida la forma que tendra la base de datos generada por la migracion , entonces ejecutaremos la migracion con el comando " bundle exec rake db:migrate "

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/92982080-f818-4735-b46b-919fbf3c3c1f)

Ahora si queremos ingresar datos a esta tabla , los ingresaremos en el archivo seeds.rb de esta forma :

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/8df5a874-5a4d-422f-a6d6-961c5870e9db)

Pero estos aun no han sido ingresados en la tabla , para esto ejecutamos el comando " 
rails db:seed ", para ver si han sido ingresados primero ejecutaremos la consola de rails y con ayuda del comando Todo.all el cual nos devolvera todos los datos de la tabla  :   
![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/9e9c6a20-cfe2-4768-a285-1dce8d10cc03)

Ahora ejecutaremos el servidor : 

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/4f671997-4a2c-4c7f-aea5-949ad8d28bf1)

Veremos que se ejecuta con normalidad el servidor y si ingresamos a al puerto donde se ejecuta veremos :

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/1db36f37-98ed-434b-97c0-f2a7e79dc7ae)

Vemos esto porque no hemos ingresado a la ruta correcta , el comando sccafold ya genero una ruta donde se muestran los datos de la tabla ingresada , pero en donde ? .Revisemos los controladores de esta aplicacion 

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/5e8cb823-71ce-4104-a9ef-6e1ca183fe3c)

vemos que en /todos se mostraran los datos de la tabla , no solo eso sino que tambien podremos crear nuevos datos , editarlos y eliminarlos 

ingresemos a /todos :

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/86592430-ede9-4685-91e4-56da9da84629)

Que pasa si ahora queremos ingresar algun dato :

Ingresemos a todos/new

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/81a19674-6430-46ff-bfec-a02594a7935f)

si ingresamos un nuevo dato  y regresamos a /todos :

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/1a8ca3a3-dace-4896-9016-09ea1babc3a0)

vemos que ha sido actualizado un nuevo elemento :

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/bdbcccd8-7b50-4f92-8ec2-fa3cef1e7825)

Editandolo :

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/271e8d58-d415-4b66-9e23-8aaae260d0c1)

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/764bdf9b-36ad-4109-9aad-957a08ce7e74)

ahora eliminandolo :

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/f1a5c33b-78ee-455e-a293-d6af598b5fb5)


### Más migraciones
La primera migración nos permitió crear la base de datos. Digamos que el cliente quiere que cada "tareas pendientes" tenga una fecha de vencimiento asociada. ¿Cómo hacemos que eso suceda? 
¿Qué  archivos nuevos o cambios en los archivos existentes han ocurrido? .

Agregaremos una nueva migracion , en donde especifiquemos que se agrege una columna a la tabla todo , esta columna se llamara time_limit y sea tipo datetime :

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/81b6007d-7f9a-4dc2-852f-fc8599355baa)

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/1a986db3-7133-4efc-9898-d34f023d570f)

Ahora rellenaremos los datos en seed 

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/effe709c-33ef-4752-a0e2-79856e6fc4f8)

y lo pondremos en la base de datos , revisemos :

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/9a67bfff-2702-4ddd-b32c-52ff052bc9d9)

ha sido creado con exito 

### Redireccionando :
 
 Rediccionaremos una pagina que crearemos , para esto primero crearemos la ruta a donde queramos que se muestre :

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/d02fb5d9-4d80-4233-bf35-67e8132d2ce8)

ahora crearemos que queremos mostrar en esta direccion :

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/0b51fc10-fba4-45b0-8a54-38a38367e6d0)

finalmente modificaremos esta ruta en el controlador :

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/17bfca11-e850-49ba-a70c-a818e35936b5)

ahora si ejecutamos el servidor y entramos en la direccion veremos :

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/03f92424-2891-4711-a61b-343608b5178e)

## Parte 3 :
Para esto usaremos la aplicacion wordguesser que teniamos ya hecha de la pc1 , ahora ejecutaremos de manera local 

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/d076a0ea-d651-4bd7-960c-1100906dbdd4)


vemos que funciona correctamente :

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/b5b1f05e-1ab7-46f9-96ad-b8a4ae91482b)

Preguntas (1 punto):
•	¿Cuál es el objetivo de ejecutar bundle install?
•	¿Por qué es una buena práctica especificar –without production al ejecutarlo en su computadora de desarrollo?
•	(Para la mayoría de las aplicaciones Rails, también tendrías que crear y inicializar la base de datos de desarrollo, pero al igual que la aplicación Sinatra, esta aplicación no utiliza ninguna base de datos).


Respuesta : 
- el objetivo de ejecutar bunlde install es para que pueda instalar las gemas que pusimos en el archivo gemfile , no solo instalar las gemas sino tambien las dependencias de estas gemas .
- Para poder evitar problemas con versiones 
- esto es porque las palabras que usamos las sacamos de una pagina web , que nos da palabras aleatorias .

  
•	¿En qué parte de la estructura del directorio de la aplicación Rails está el código correspondiente al modelo WordGuesserGame?

Respuesta :  

-Este se encuentra dentro del directorio models :

![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/5c9f2c7e-2fdc-4d8e-9ade-acbf91e7eef5)

•	¿En qué archivo está el código que más se corresponde con la lógica del archivo app.rb de las aplicaciones Sinatra que maneja las acciones entrantes del usuario?  

Respuesta : 

-Lo mas parecido a app.rb de sinatra a la aplicacion en rails serian 2 partes , la de controlador y la de routes , ya que app.rb cuenta con estas dos logicas .

•	¿Qué clase contiene ese código?

-Respuesta:
   Esta solo contiene una clase , esta es GameController la hereda a AplicationControleer esta contiene la logica atravez de la cual nos dara respuestas a lo que nosotros juguemos 
   :
   ![image](https://github.com/peg1163/ExamenParcial-CC3S2/assets/92898224/b3f9acb8-72af-4c28-9757-c83ade94c9b4)


   
•	¿De qué otra clase (que es parte del framework Rails) hereda esa clase?

Respuesta:
  Este hereda de AplicationController
  
•	¿En qué directorio está el código correspondiente a las vistas de la aplicación Sinatra (new.erb, show.erb, etc.)?

  Esta se encuentra en la parte de view/game donde existen 4 vistas : lose.html.erb,new.html.erb,show.html.erb,win.html.erb
  
•	Los sufijos de nombre de archivo para estas vistas son diferentes en Rails que en la aplicación Sinatra. ¿Qué información proporciona el sufijo situado más a la derecha del nombre del archivo (por ejemplo: en foobar.abc.xyz, el sufijo .xyz) sobre el contenido del archivo?  

Respuesta :
    Por ejemplo en los archivo mencionados anteriormente ,.erb hace que se haga codigo dinamico , es decir que se puede agregar codigo ruby en el primer sufijo , en este caso html
    
•	¿Qué información te brinda el otro sufijo sobre lo que se le pide a Rails que haga con el archivo?
Respuesta :
  mencionado anteriormente se puede agregar codigo ruby para poder facilitar la llamada de objetos y metodos a los archivos html o a los demas tipos de archivos 
  
•	¿En qué archivo está la información de la aplicación Rails que asigna rutas (por ejemplo, GET/new) a las acciones del controlador?

  Este se encuentra en el archivo config/routes.rb
  
•	¿Cuál es el papel de la opción :as => 'name' en las declaraciones de ruta de config/routes.rb? .

al igual que algunas librerias en python :as => name permite poder asignarle un nombre a la ruta , para poder tener un codigo mas legible .
























