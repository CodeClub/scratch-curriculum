---
t�tulo: Perdidos en el espacio
nivel: Scratch 1
idioma: es-ES
stylesheet: scratch
embeds: "*.png"
materiales: ["Recursos para el l�der del Club /*.*"]
...

# Introducci�n { .intro }

�Vas a aprender a programar tu propia animaci�n!

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/26818098/?autostart=false" frameborder="0"></iframe>
  <img src="space-final.png">
</div>

# Primer paso: Animaci�n de una nave espacial { .activity .new-page}

�Hagamos una nave espacial que vuele hacia la Tierra!

## Lista de verificaci�n de actividades { .check }

+ Comienza un nuevo proyecto Scratch, y elimina el objeto gato para que tu proyecto est� vac�o. Puedes encontrar el editor de Scratch en l�nea en <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.

+ Agrega los objetos �Nave especial� y �Tierra� al escenario. Tambi�n deber�as agregar las �Estrellas� en el fondo de tu escenario. Tu escenario deber�a verse as�:

	![screenshot](space-sprites.png)

+ Haz clic en tu nuevo objeto nave especial, y haz clic en la leng�eta �Disfraces�.

	![screenshot](space-costume.png)

+ Usa la herramienta de flechas para seleccionar la imagen. Luego haz clic en la manija rotatoria circular, y haz rotar la imagen hasta que est� de costado.

	![screenshot](space-rotate.png)

+ Agrega este c�digo a tu objeto nave espacial:

	![screenshot](space-animate.png)

	Cambia los n�meros en los bloques de c�digo, para que el c�digo sea exactamente igual que en la imagen anterior.

+ Si haces clic en los bloques de c�digo para ejecutar el c�digo, deber�as ver que la nave especial habla, dobla y se mueve hacia el centro del escenario.

	![screenshot](space-animate-stage.png)

	La posici�n de la pantalla `x:(0) y:(0)` {.blockmotion} es el centro del escenario. Una posici�n como `x:(-150) y:(-150)` {.blockmotion} est� hacia la parte inferior izquierda del esenario, y una posici�n como `x:(150) y:(150)` {.blockmotion} est� cerca de la parte superior derecha.

	![screenshot](space-xy.png)

	Si necesitas saber las coordinadas de una posici�n en el scenario, mueve el rat�n a la posici�n para la cual deseas saber las coordinadas, que se despliegan abajo del escenario.

	![screenshot](space-coordinates.png)

+ Prueba tu animaci�n haciendo clic en la bandera verde justo arriba del escenario.

	![screenshot](space-flag.png)

## Desaf�o: Mejora tu animaci�n {.challenge}
Puedes cambiar los n�meros en el c�digo de tu animaci�n, para que:
+ �La nave especial se mueva hasta tocar la Tierra?
+ �La nave espacial se mueva m�s lentamente hacia la Tierra?

Necesitar�s cambiar los n�meros en este bloque:

```blocks
	deslizar en (1) segs a x:(0) y:(0)
```

## Guarda tu proyecto { .save }

# Segundo paso: Animaci�n mediante el uso de loops { .activity .new-page }

Otra manera de animar la nave espacial es decirle que se mueva distancias peque�as, muchas veces.

## Lista de verificaci�n de actividades { .check }

+ Elimina el bloque `deslizar` {.blockmotion} de tu c�digo haciendo clic con el bot�n derecho y haciendo clic en �eliminar�. Tambi�n puedes eliminar c�digo arrastr�ndolo del �rea de secuencia de comandos, de nuevo al �rea de los bloques de c�digo.

	![screenshot](space-delete-glide.png)

+ Una vez que hayas eliminado tu c�digo, agrega este c�digo en su lugar:

	![screenshot](space-loop.png)

	El bloque `repetir` {.blockcontrol} se usa para repetir algo muchas veces, y tambi�n se conoce como un __loop__.

+ Si haces clic en la bandera para probar este nuevo c�digo, ver�s que hace casi lo mismo que antes.

+ Puedes agregar m�s c�digo a tu loop, para hacer cosas interesantes. Agrega el bloque `cambiar efecto de color por 25` {.blocklooks} en el loop (de la secci�n �Vistas�), para cambiar el color de la nave espacial repetidamente a medida que se mueve:

	![screenshot](space-colour.png)

+ Haz clic en la bandera para ver tu nueva animaci�n.

	![screenshot](space-colour-test.png)

+ Tambi�n puedes hacer que tu nave especial se haga m�s peque�a a medida que se mueve hacia la Tierra.

	![screenshot](space-size.png)

+ Prueba tu animaci�n. �Qu� sucede si haces clic en la bandera una segunda vez? �Tu nave espacial empieza con el tama�o correcto? Puedes usar este bloque para fijar tu animaci�n:

	```scratch
	fijar tama�o a (100) %
	```

## Guarda tu proyecto { .save }

# Tercer paso: Mono que flota { .activity .new-page }

Agreguemos un mono a tu animaci�n, que est� �perdido en el espacio!! 

## Lista de verificaci�n de actividades { .check }

+ Comienza agregando un objeto mono de la biblioteca.

	![screenshot](space-monkey.png)

+ Si haces clic en tu nuevo objeto mono y luego en �Disfraces�, puedes editar c�mo se ve el mono. Haz clic en la herramienta �Elipse� y dibuja un casco espacial blanco alrededor de la cabeza del mono.

	![screenshot](space-monkey-edit.png)

+ Ahora haz clic en �Secuancia de comandos�, y agrega este c�digo a tu mono, para que gire lentamente en un c�rculo por siempre:

	```blocks
		al presionar bandera verde
		por siempre
		    girar (1) grados a la derecha
		fin
		end
	```

	El bloque `por siempre` {.blockcontrol} es otro loop, pero esta vez uno que nunca termina.

+ Haz clic en la bandera para probar tu mono. Tendr�s que hacer clic en el bot�n parar (al lado de la bandera) para terminar esta animaci�n.

	![screenshot](space-monkey-loop.png)

# Cuarto paso: Asteroides que rebotan { .activity .new-page }

Agreguemos a tu animaci�n algunas rocas espaciales que flotan.

## Lista de verificaci�n de actividades { .check }

+ Agrega un objeto �roca� a tu animaci�n.

	![screenshot](space-rock-sprite.png)

+ Agrega este c�digo a tu roca, para hacer que rebote por todo el escenario:

	```scratch
	al presionar bandera verde
	apuntar hacia [Earth v]
	por siempre
		mover (2) pasos
		rebotar si toca un borde
		if on edge, bounce
	```

+ Haz clic en la bandera para probar tu roca. �Rebota por todo el escenario?

# Quinto paso: Estrellas que brillan { .activity .new-page }

Combinemos loops para hacer una estrella que brilla.

## Lista de verificaci�n de actividades { .check }

+ Agrega un objeto �Estrella� a tu animaci�n

	![screenshot](space-star-sprite.png)

+ Agrega este c�digo a tu estrella:

	![screenshot](space-star.png)

+ Haz clic en la bandera para probar esta animaci�n de la estrella. �Qu� hace este c�digo? Bien, la estrella se hace un poquito m�s grande 20 veces, y luego se hace un poquito m�s peque�a 20 veces, hasta llegar a su tama�o original. Estos 2 loops est�n dentro de un loop `por siempre` {.blockcontrol}, para que la animaci�n se contin�e repitiendo.

## Guarda tu proyecto { .save }

## Desaf�o: Crea tu propia animaci�n {.challenge}
Det�n tu animaci�n especial, haz clic en �Archivo� y luego en �Nuevo�, para comenzar un nuevo proyecto.

Usa lo que aprendiste en este proyecto para crear tu propia animaci�n. Puede ser cualquier cosa que quieras, pero trata de que la animaci�n concuerde con el escenario. Aqu� te damos algunos ejemplos:

![screenshot](space-egs.png)

## Guarda tu proyecto { .save }