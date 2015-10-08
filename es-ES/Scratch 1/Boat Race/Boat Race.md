---
title: Carrera de botes
level: Scratch 1
language: es-ES
stylesheet: scratch
embeds: "*.png"
materials: ["Recursos para el l�der del Club /*.*","Recursos del Proyecto /*.*"]
...

# Introducci�n { .intro }

Vas a aprender c�mo crear un juego en el cual usar�s el rat�n para navegar tu bote a una isla desierta.

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/63957956/?autostart=false" frameborder="0"></iframe>
  <img src="boat-final.png">
</div>

# Primer paso: C�mo planificar el juego { .activity }

## Lista de verificaci�n de actividades { .check }

+ Comienza un nuevo proyecto Scratch, y borra el objeto gato para que tu proyecto est� vac�o. Puedes encontrar el editor en l�nea de Scratch en <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.

+ Haz clic en el fondo de tu escenario y planifica tu nivel. Deber�as agregar:
	+ Madera que tu bote tiene que evitar;
	+ Una isla desierta a la que tu bote tiene que llegar.

	Tu juego podr�a verse algo as�:

	![screenshot](boat-bg.png) 

# Segundo paso: C�mo controlar el bote { .activity }

## Lista de verificaci�n de actividades { .check }

+ Si el l�der de tu club te dio una carpeta de 'Recursos', haz clic en 'Cargar objeto del expediente' y agrega la imagen 'boat.png'. Deber�as achicar el objeto y ubicarlo en la posici�n de comienzo.

	![screenshot](boat-boat.png)

	Si no tienes la imagen boat.png, �puedes dibujar tu propio bote!

+ Vas a controlar el bote con tu rat�n. Agrega este c�digo a tu bote:

	```blocks
		al presionar la bandera verde
		apuntar en direcci�n (0 v)
		ir a x: (-190) y: (-150)
		por siempre
			apuntar hacia [puntero del mouse v]
			mover (1) pasos
		fin
	```

+ Prueba tu bote haciendo clic en la bandera y moviendo el rat�n. �Navega el bote hacia el rat�n?

	![screenshot](boat-mouse.png)

+ �Qu� sucede si el bote llega al apuntador del rat�n?

	Para que esto no suceda, necesitar�s agregar un bloque 'si'{.blockcontrol} a tu c�digo, para que el bote solo se mueva si est� a m�s de 5 p�xeles del rat�n.

	![screenshot](boat-pointer.png)	

+ Prueba tu bote una vez m�s para ver si el problema ha sido resuelto.

## Guarda tu proyecto { .save }

# Tercer paso: �Choques! { .activity .new-page }

�Tu bote puede navegar a trav�s de barreras de madera! Arreglemos eso.

## Lista de verificaci�n de actividades { .check }

+ Necesitar�s 2 disfraces para tu bote, uno normal y otro para cuando el bote choca. Duplica el disfraz de tu bote y n�mbralos 'normal' y 'chocado'.

+ Haz clic en tu disfraz 'chocado', y elige la herramienta 'Seleccionar' para tomar partecitas del bote y moverlas y rotarlas por todos lados. Haz que parezca que tu bote ha chocado.

	![screenshot](boat-hit-costume.png)

+ Agrega este c�digo a tu bote, dentro del loop `por siempre` {.blockcontrol}, para que choque cuando toca cualquier trocito de madera marr�n:

	```blocks
		si <tocando el color [#603C15]?> entonces
			cambiar disfraz a [hit v]
			decir [Noooooo!] por (1) segundos
			cambiar disfraz a [normal v]
			apuntar en direcci�n (0 v)
			ir a x: (-215) y: (-160)
		fin
	```

	Este c�digo est� dentro del loop `por siempre` {.blockcontrol}, para que tu c�digo constantemente verifique si tu bote ha chocado.

+ Tambi�n deber�as asegurarte de que al comienzo tu bote siempre se vea 'normal'.

+ Ahora si tratas de navegar a trav�s de una barrera de madera, deber�as ver que tu bote choca y vuelve al inicio.

	![screenshot](boat-crash.png)

## Guarda tu proyecto { .save }

## Desaf�o: �Ganar! {.challenge}
�Puedes agregar otra declaraci�n `si` {.blockcontrol} al c�digo de tu bote, para que el jugador gane cuando llegue a la isla desierta?

Cuando el bote llega a la isla desierta amarilla, deber�a decir 'YEAH!' y el juego deber�a terminar. Tendr�s que usar este c�digo:

```bloques
	decir [YEAH!] por (1) segundos
	terminar [all v]
```

![screenshot](boat-win.png)

## Guarda tu proyecto { .save }

## Desaf�o: Efectos de sonido {.challenge}
Puedes agregar efectos de sonido a tu juego para cuando el bote choca y para cuando llega a la isla al final del juego. Incluso puedes agregar m�sica de fondo (si necesitas ayuda con esto mira el proyecto 'Banda de Rock' anterior).

## Guarda tu proyecto { .save }

# Cuarto paso: Prueba del cron�metro { .activity }

Agreguemos a tu juego un crn�metro, para que el jugador tenga que llegar a la isla lo m�s r�pido posible.

## Lista de verificaci�n de actividades { .check }

+ Agrega a tu escenario una nueva variable que se llame `tiempo` {.blockdata}. Tambi�n puedes cambiar c�mo se ve tu nueva variable. Si necesitas ayuda, mira el proyecto "Globos".

	![screenshot](boat-variable.png)

+ Agrega este c�digo a tu __escenario__, para que el cron�metro cuente hasta que el bote llega a la isla desierta:

	```blocks
		al presionar la bandera verde
		fijar [time v] a [0]
		por siempre
			esperar (0.1) segundos
			cambiar [time v] por (0.1)
		fin
	```

+ �Ya est�! �Prueba tu juego para ver qu� tan r�pido puedes llegar a la isla desierta!

	![screenshot](boat-variable-test.png)

## Guarda tu proyecto { .save }

# Quinto paso: Obst�culos y fuentes de energ�a { .activity }

Este juego es _demasiado_ f�cil � agreguemos cosas para hacerlo m�s interesante.

## Lista de verificaci�n de actividades { .check }

+ Primero agreguemos algunos "est�mulos" a tu juego, que har�n que el bote navegue m�s r�pido. Edita el fondo de tu scenario y agrega algunas flechas blancas de energ�a.

	![screenshot](boat-boost.png)

+ Ahora puedes agregar c�digo al loop `por siempre` {.blockcontrol} de tu bote, para que se mueva 2 _pasos extra_ cada vez que toca una fuente de energ�a blanca.

	```blocks
		si <tocando el color [#FFFFFF]?> entonces
			mover (3) pasos
		fin
	```

+ Tambi�n puedes agregar una puerta giratoria, que tu bote tiene que evitar. Agrega un nuevo objeto que se llame 'puerta', y que se vea as�:

	![screenshot](boat-gate.png)

	Aseg�rate de que el color de la puerta sea igual al color de las otras barreras de madera.

+ Fija el centro del objeto puerta.

	![screenshot](boat-center.png)

+ Agrega c�digo a tu puerta para hacerla que lentamente gire `por siempre` {.blockcontrol}.

+ Prueba tu juego. Ahora deber�as tener una puerta giratoria que tienes que evitar.

	![screenshot](boat-gate-test.png)

## Guarda tu proyecto { .save }

## Desaf�o: �M�s obst�culos! {.challenge .new-page}
�Puedes agregar m�s obst�culos a tu juego? Aqu� te damos algunas ideas:

+ Podr�as agregar cieno verde a tu scenario, lo que frena al jugador cuando lo toca. Para hacerlo puedes usar un bloque `espera` {.blockcontrol}:

```blocks
	esperar (0.01) segundos
````

![screenshot](boat-algae.png)

+ �Podr�as agregar un objeto en movimiento, como un tronco o un tibur�n!

![screenshot](boat-obstacles.png)

Estos bloques pueden ayudarte:

```blocks
	mover (1) pasos
	rebotar si toca un borde
````

Si tu nuevo objeto no es marr�n, tendr�s que agregar esto al c�digo de tu bote:

```blocks
	si <  <tocando el color [#603C15]?> o <tocando [shark v]?> > entonces
	fin
```

## Guarda tu proyecto { .save }

## Desaf�o: �M�s botes! {.challenge .new-page}
�Puedes convertir tu juego en una carrera entre 2 jugadores?

+ Duplica el bote, ren�mbralo 'Jugador 2' y c�mbiale el color.

![screenshot](boat-p2.png)

+ Cambia este c�digo para cambiar la posici�n de comienzo del Jugador 2:

```blocks
	ir a x: (-190) y: (-150)
```

+ Borra el c�digo que usa el rat�n para controlar el bote:

```blocks
	si < (distancia a [puntero del mouse v]) > [5] > entonces
		apuntar hacia [apuntador del rat�n v]
		mover (1) pasos
	fin
```

...y reempl�zalo con c�digo para controlar el bote usando las teclas de flechas.

Este es el c�digo que necesitas para mover el bote hacia adelante:

```blocks
	si < tecla [flecha arriba v] presionada? > entonces
		mover (1) pasos
	fin
```

Tambi�n necesitar�s un c�digo para `doblar` {.blockmotion} el bote cuando se presionan las teclas de flechas izquierda y derecha.

## Guarda tu proyecto { .save }

## Desaf�o: �M�s niveles! {.challenge .new-page}
�Puedes crear escenarios adicionales y permitirle al jugador que elija entre niveles?

```blocks
	al presionar la tecla [espacio v]
	siguiente fondo
```

## Guarda tu proyecto { .save }
