---
title: Robot parlanch�n
level: Scratch 1
language: es-ES
stylesheet: scratch
embeds: "*.png"
materials: ["Recursos para el L�der del Club /*.*"]
...

# Introducci�n { .intro }

�Vas a aprender c�mo programar tu propio robot que habla!

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/26762091/?autostart=false" frameborder="0"></iframe>
  <img src="chatbot-final.png">
</div>

# Primer paso: Tu robot parlanch�n { .activity }

## Lista de verifiaci�n de actividades { .check }

+ Antes de comenzar a hacer tu robot parlanch�n, necesitas decidir sobre su personalidad.
	+ �C�mo se llama?
	+ �D�nde vive?
	+ �Es feliz? �serio? �gracioso? �t�mido? �amigable?

+ Comienza un nuevo proyecto Scratch, y borra el objeto gato para que tu proyecto est� vac�o. Puedes encontrar el editor en l�nea de Scratch en <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.

+ Elige uno de estos caracteres objetos, y agr�galos a tu proyecto:

	![screenshot](chatbot-characters.png)

+ Crea un escenario que haga juego con la personalidad de tu robot parlanch�n. Aqu� te  damos un ejemplo, aunque no necesariamente tiene que  verse as�:

	![screenshot](chatbot-sprite.png)

## Guarda tu proyecto { .save }

# Segundo paso: Un robot parlanch�n que puede hablar { .activity }

Ahora que tienes un robot parlanch�n con personalidad, creemos un programa para que te hable.

## Lista de verificaci�n de actividades { .check }

+ Haz clic en el caracter de tu robot parlanch�n, y agrega este c�digo:

	```blocks
		al hacer clic en este objeto
		preguntar [Hey! C�mo te llamas?] y esperar
		decir [Qu� lindo nombre!] por (2) segundos
	```

+ Haz clic en tu robot parlanch�n para probarlo. Luego de que te pregunta tu nombre, escr�belo en la caja abajo del escenario.

	![screenshot](chatbot-text.png)

+ Tu robot parlanch�n simplemente responde `Qu� lindo nombre!` cada vez. Puedes personalizar la respuesta de tu robot parlanch�n, haciendo uso de la respuesta del usuario. Cambia el c�digo del robot parlanch�n, para que se vea as�:

	```blocks
		al hacer clic en este objeto
		preguntar [Hey! C�mo te llamas?] y esperar
		decir <unir [Hola] (respuesta)> por (2) segundos
	```

	Para crear este �ltimo bloque, primero tendr�s que arrastrar un bloque verde `unir` {.blockoperators} , y arrastrarlo sobre el bloque `decir` {.blocklooks} .

	![screenshot](chatbot-join.png)

	Puedes cambiar el texto `hola` para decir `Hey`, y arrastrar el bloque azul `respuesta` {.blocksensing}  (de la secci�n 'Percepci�n' ) sobre el texto `mundo`.

	![screenshot](chatbot-answer.png)

+ Prueba este nuevo programa. �Funciona como esperabas? �Puedes solucionar los problemas que ves? (Pista: �puedes intentar agregar un espacio en cualquier parte!)

+ Puede que quieras almacenar el nombre del usuario en una variable, para poder usarlo de nuevo en el futuro. Crea una nueva variable que se llame `nombre` {.blockdata}. Si olvidaste como hacerlo, el proyecto "Globos" puede ayudarte.

+ La informaci�n que ingresaste ya est� almacenada en una variable especial llamada `respuesta` {.blocksensing}. Ve al grupo de bloques de Percepci�n y haz clic en el bloque de respuesta para que aparezca una palomita. El valor actual en `respuesta` {.blocksensing} deber�a mostrarse en la parte superior izquierda del escenario.

+ Una vez que creaste tu nueva variable, aseg�rate de que el c�digo de tu robot parlanch�n se vea as�:

	```blocks
		al hacer clic en este objeto
		preguntar [Hey! C�mo te llamas?] y esperar
		fijar [name v] a (answer)
		decir <unir [Hola ] (name)> por (2) segundos
	```

+ Si pruebas el programa una vez m�s, ver�s que la respuesta se almacena en la variable `nombre` {.blockdata} , y se muestra en la parte superior izquierda del escenario. La variable `nombre` {.blockdata} deber�a ahora contener el mismo valor que la variable `respuesta` {.blocksensing} .

	![screenshot](chatbot-variable.png)

	Si prefieres no ver las variables en tu escenario, puedes hacer clic en la palomita junto al nombre de la variable en la leng �eta "Secuencia de comandos" para esconderlas.

## Guarda tu proyecto { .save }

## Desaf�o: M�s preguntas { .challenge }

Programa tu robot parlanch�n para que haga otra pregunta. �Puedes almacenar su respuesta en una variable?

![screenshot](chatbot-question.png)

## Guarda tu proyecto { .save }

# Tercer paso: La toma de decisiones { .activity }

Puedes programar tu robot parlanch�n para que decida qu� hacer, bas�ndose en las respuestas del usuario.

## Lista de verificaci�n de actividades { .check }

+ Hagamos que tu robot parlanch�n pregunte al usuario una pregunta con una respuesta `s�` o `no` . Aqu� te damos un ejemplo, pero puedes cambiar la pregunta si as� lo deseas:

	```blocks
		al hacer clic en este objeto
		preguntar [Hey! C�mo te llamas?] y esperar
		fijar [name v] a (answer)
		decir <unir [Hola ] (name)> por (2) segundos
		preguntar <unir [Est�s bien ] (name)> y esperar
		si ((respuesta)=[s�]) entonces
			decir [Me da gusto saber que est�s bien!] por (2) segundos
		fin
	```

	F�jate que ahora que has guardado el nombre del usuario en una variable, puedes usarlo cuantas veces quieras.

+ Para probar el programa adecuadamente, tendr�s que probarlo dos veces, una escribiendo `no` como tu respuesta, y otra escribiendo `s�`. Solo deber�as obtener una respuesta de tu robot parlanch�n `si` {.blockcontrol} tu respuesta es `s�`.

+ El problema con tu robot parlanch�n es que no te da una respuesta si el usuario contesta `no`. Puedes solucionar esto cambiando el bloque `si` {.blockcontrol} por un bloque `si/si no` {.blockcontrol} , para que tu nuevo c�digo se vea as�:

	```blocks
		al hacer clic en este objeto
		preguntar [Hey! C�mo te llamas?] y esperar
		fijar [name v] a (answer)
		decir <unir [Hola ] (name)> por (2) segundos
		preguntar <unir [Est�s bien ] (name)> y esperar
		si ((respuesta)=[s�]) entonces
			decir [Me da gusto saber que est�s bien!] por (2) segundos
		si no
			decir [Oh no!] por (2) segundos
		fin
	```

+ Si pruebas tu c�digo, ver�s ahora que obtienes una respuesta si contestas `s�` o `no`. Tu robot parlanch�n deber�a responder con `Me da gusto saber que est�s bien!` cuando contestas `s�`, pero responder� `Oh no!` si escribes otra cosa que no sea `s�` (`si no` {.blockcontrol} significa "de lo contrario").

	![screenshot](chatbot-else.png)

+ Puedes poner cualquier c�digo dentro de un bloque `si` {.blockcontrol} o `si no` {.blockcontrol} , no solo el c�digo para hacer que tu robot parlanch�n hable. Por ejemplo, puedes cambiar el disfraz de tu robot parlanch�n para que coincida con la respuesta.

	Si miras los disfraces de tu robot parlanch�n, ver�s que hay m�s de uno. (Si no los hay, �siempre puedes agregar m�s tu mismo!)

	![screenshot](chatbot-costumes.png)

	Puedes usar estos disfraces como parte de la respuesta de tu robot parlanch�n, agregando este c�digo:

	![screenshot](chatbot-costumes-code.png)

+ Prueba tu programa, y deber�as ver c�mo la cara de tu robot parlanch�n cambia dependiendo de la respuesta que le das.

	![screenshot](chatbot-face.png)

## Guarda tu proyecto { .save }

## Desaf�o: M�s decisiones { .challenge }

Programa tu robot parlanch�n para hacer otra pregunta, algo que tenga una respuesta `s�` o `no` . Puedes hacer que tu robot parlanch�n responda a la respuesta?

![screenshot](chatbot-joke.png)

## Guarda tu proyecto { .save }

# Cuarto paso: C�mo cambiar la ubicaci�n { .activity }

Tambi�n puedes programar a tu robot parlanch�n para que cambie su ubicaci�n.

## Lista de verificaci�n de actividades { .check }

+ Agrega otro fondo a tu escenario, por ejemplo el fondo "luna".

	![screenshot](chatbot-moon.png)

+ Ahora puedes programar a tu robot parlanch�n para que cambie de ubicaci�n agregando este c�digo a tu robot parlanch�n:

	```blocks
		preguntar [Me voy a la luna. �Quieres venir conmigo?] y esperar
		si ((respuesta) = [s�]) entonces
			cambiar fondo a [moon v]
		fin
	```

+ Tambi�n debes asegurarte de que tu robot parlanch�n est� afuera cuando comienzas a hablarle. Agrega este bloque al principio del c�digo de tu robot parlanch�n:

	![screenshot](chatbot-outside.png)

+ Prueba tu programa, y contesta `s�` cuando te pregunta si quieres ir a la luna. Deber�as ver que la ubicaci�n del robot parlanch�n cambi�.

	![screenshot](chatbot-backdrop.png)

+ �Cambia de ubicaci�n tu robot parlanch�n si escribes `no`? �Y qu� pasa si escribes `No estoy seguro`?

+ Tambi�n puedes agregar este c�digo dentro de tu bloque `si` {.blockcontrol} , para hacer que tu robot parlanch�n salte 4 veces si la respuesta es `s�`:

	```scratch
	repetir (4)
		cambiar y por (10)
		esperar (0.1) segundos
		cambiar y por (-10)
		esperar (0.1) segundos
	fin
	```

	![screenshot](chatbot-loop.png)

+ Prueba tu c�digo una vez m�s. �Salta tu robot parlanch�n si contestas que `s�`?

## Guarda tu proyecto { .save }

## Desaf�o: Crea tu propio robot parlanch�n {.challenge}
Utiliza lo que has aprendido para terminar de crear tu robot parlanch�n interactivo. Aqu� te damos algunas ideas:

![screenshot](chatbot-ideas.png)

Una vez que termines de crear tu robot parlanch�n, �haz que tus amigos hablen con �l! �Les gusta tu personaje? �Encontraron alg�n problema?

## Guarda tu proyecto { .save }
