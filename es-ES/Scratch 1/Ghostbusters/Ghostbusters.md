---
title: Caza fantasmas
level: Scratch 1
language: es-ES
stylesheet: scratch
embeds: "*.png"
materials: ["Recursos para el l�der del club/*.*"]
...

## Nota: { .challenge .pdf-hidden }
El Proyecto �Globos� se ha movido a la secci�n [Proyectos Scratch Adicionales](http://projects.codeclub.org.uk/en-GB/03_scratch_bonus/index.html.

# Introducci�n { .intro }

�Vas a crear un juego para cazar fantasmas!

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/60787262/?autostart=false" frameborder="0"></iframe>
  <img src="ghost-final.png">
</div>

# Primer paso: C�mo animar un fantasma { .activity }

## Lista de verificaci�n de actividades { .check }

+ Comienza un nuevo proyecto Scratch, y borra el objeto gato para que tu proyecto est� vac�o. Puedes encontrar el editor en l�nea de Scratch en <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.

+ Agrega un nuevo objeto fantasma, y un escenario acorde.

	![screenshot](ghost-ghost.png)

+ Agrega este c�digo a tu fantasma, para que continuamente aparezca y desaparezca:

	```blocks
		al presionar la bandera verde
		por siempre
			esconder
			esperar (1) segundos
			mostrar
			esperar (1) segundos
		fin
	```

+ Prueba el c�digo de tu fantasma haciendo clic en la bandera verde.

## Guarda tu proyecto { .save }

# Segundo paso: Fantasmas aleatorios { .activity }

�Tu fantasma es muy f�cil de atrapar porque no se mueve!

## Lista de verificaci�n de actividades { .check }

+ En lugar de estar en la misma posici�n, puedes hacer que Scratch elija coordinadas x e y al azar. Agregar un bloque `ir a` {.blockmotion} al c�digo de tu fantasma, para que se vea as�:

	```blocks
		al presionar bandera verde
		por siempre
			esconder
			esperar (1) segundos
			ir a x:(n�mero al azar entre (-150) y (150)) y:(n�mero al azar entre (-150) y (150))
			mostrar
			esperar (1) segundos
		fin
	```

+ Prueba tu fantasma una vez m�s. Deber�as notar que cada vez aparece en un lugar distinto.

## Guarda tu proyecto { .save }

## Desaf�o: M�s aleatoriedad {.challenge}
�Puedes hacer que tu fantasma `espere` {.blockcontrol} una cantidad de tiempo al azar antes de aparecer? �Puedes usar el bloque `fijar tama�o ` {.blocklooks} para hacer que tu fantasma tenga un tama�o al azar cada vez que aparece?

## Guarda tu proyecto { .save }

# Tercer paso: C�mo atrapar fantasmas { .activity }

�Dejemos que el jugador pueda atrapar fantasmas!

## Lista de verificaci�n de actividades { .check }

+ Para permitirle al jugador que atrape un fantasma, agrega este c�digo:

	```blocks
		al hacer clic en este objeto
		esconder
	```

+ Prueba tu proyecto. �Puedes atrapar fantasmas cuando aparecen? Si te parece dif�cil atrapar fantasmas, puedes jugar el juego en el modo pantalla completa haciendo clic en este bot�n:

	![screenshot](ghost-fullscreen.png)

## Desaf�o: Agregar un sonido { .challenge }
�Puedes hacer un sonido cada vez que se atrapa un fantasma?

## Guarda tu proyecto { .save }

# Cuarto paso: Agregar un puntaje { .activity .new-page }

Hagamos que las cosas sean m�s interesantes con un contador de puntos.

## Lista de verificaci�n de actividades { .check }

+ Para llevar un conteo de los puntos del jugador, necesitas un lugar para ubicarlo. Una __variable__ es un lugar para almacenar informaci�n que cambia, como un puntaje.

	Para crear una nueva variable, haz clic en la leng�eta de �Secuencia de comandos�, selecciona `Informaci�n` {.blockdata} y luego haz clic en �Crear una Variable�.

	![screenshot](ghost-score.png)

	Ingresa �puntaje� como el nombre de la variable. Aseg�rate de que est� disponible para todos los objetos, y haz clic en �OK� para crearla. Ver�s much�simos bloques de c�digo que pueden usarse con tu variable `puntaje` {.blockdata}.

	![screenshot](ghost-variable.png)

	Tambi�n ver�s el puntaje en la esquina superior izquierda del escenario.

	![screenshot](ghost-stage-score.png)

+ Cuando se inicia un nuevo juego (haciendo clic en la bandera), deber�as hacer que el puntaje del jugador sea 0:

	```blocks
	al presionar bandera verde
	fijar [score v] a [0]
	```

+ Siempre que se atrapa un fantasma, necesitas agregar 1 al puntaje del jugador:

	![screenshot](ghost-change-score.png)

+ Ejecuta tu programa une vez m�s y atrapa algunos fantasmas. �Cambia tu puntaje?

## Guarda tu proyecto { .save }

# Quinto paso: C�mo agregar un cron�metro { .activity }

Puedes hacer tu juego m�s interesante, d�ndole al jugador solo 10 segundos para atrapar tantos fantasmas como le sea posible.

## Lista de verificaci�n de actividades { .check }

+ Puedes usar otra variable para almacenar el tiempo que queda. Haz clic en el escenario y crea una nueva variable denominada �tiempo�:

	![screenshot](ghost-time.png)

+ As� es como deber�a funcionar el cron�metro:

	+ El cron�metro deber�a comenzar a 10 segundos;
	+ El cron�metro deber�a contar cada segundo descendiente;
	+ El juego deber�a detenerse cuando el cron�metro llega a 0.

	Este es el c�digo para hacerlo, que puedes agregar a tu __escenario__:

	```blocks
		al presionar bandera verde
		fijar [time v] a [10]
		repetir hasta que <(time) = [0]>
			esperar (1) segundos
			cambiar [time v] por (-1)
		fin
		detener [todos v]
	```

	As� es como agregas el c�digo `repetir hasta`{.blockcontrol}`tiempo`{.blockdata}`= 0`{.blockoperators}:

	![screenshot](ghost-timer-help.png)

+ Arrastra el visor de la variable �tiempo� al lado derecho del scenario. Tambi�n puedes hacer clic con el bot�n derecho en el visor de la variable y elegir �lector grande� para cambiar c�mo se muestra el tiempo.

	![screenshot](ghost-readout.png)

+ P�dele a un amigo que pruebe tu juego. �Cu�ntos puntos pueden sumar? Si tu juego es demasiado f�cil, puedes:

	+ Darle menos tiempo al jugador;
	+ Hacer que los fantasmas no aparezcan tan seguido;
	+ Hacer que los fantasmas sean m�s peque�os.

	Prueba tu juego algunas veces hasta que est�s conforme con que tiene el nivel adecuado de dificultad.

## Guarda tu proyecto { .save }

## Desaf�o: M�s objetos {.challenge}
�Puedes agregar otros objetos a tu juego?

![screenshot](ghost-final.png)

Necesitas pensar sobre los objetos que agregas. Piensa acerca de:

+ �Qu� tan grande es?
+ �Aparecer� m�s o menos seguido que los fantasmas?
+ �C�mo se ver�/sonar� cuando sea atrapado?
+ �Cu�ntos puntos te dar� (o quitar�) si lo atrapas?

�Si necesitas ayuda para agregar otro objeto, puedes volver a usar los pasos anteriores!

## Guarda tu proyecto { .save }
