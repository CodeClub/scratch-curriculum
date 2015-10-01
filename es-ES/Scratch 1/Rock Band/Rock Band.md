---
title: Banda de Rock
level: Scratch 1
language: es-ES
stylesheet: scratch
embeds: "*.png"
materials: ["Recursos para el l�der del Club/*.*"]
...

# Introducci�n { .intro }

�En este Proyecto aprender�s c�mo codificar tus propios instrumentos musicales!

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/26741186/?autostart=false" frameborder="0"></iframe>
  <img src="band-final.png">
</div>

# Primer paso: Objetos { .activity }

Antes de poder comenzar a animar, necesitas agregar �algo� que animar. En Scratch, estas �cosas� se llaman__objetos__. 

## Lista de verificaci�n de actividades { .check }

+ Primero, abre el editor de Scratch. Puedes encontrar el editor en l�nea de Scratch editor en <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>. Se ve as�:

	![screenshot](band-scratch.png)

+ El objeto gato que puedes ver es la mascota de Scratch. Deshag�mosnos de �l haciendo clic en el bot�n derecho y luego haciendo clic en �eliminar�.

	![screenshot](band-delete.png)

+ Luego, haz clic en �Elegir objeto de la biblioteca� para abrir una lista de todos los objetos de Scratch.

	![screenshot](band-sprite-library.png)

+ Baja hasta encontrar un objeto de un tambor. Haz clic en un tambor, y haz clic en �OK� para agregarlo a tu proyecto.

	![screenshot](band-sprite-drum.png)

+ Haz clic en el �cono �encoger�, y luego haz clic en el tambor unas cuantas veces para hacerlo m�s peque�o.

	![screenshot](band-shrink.png)

## Guarda tu proyecto { .save }

Asigna un nombre a tu proyecto ingres�ndolo en la casilla de texto arriba del escenario.

Despu�s puedes hacer clic en �Archivo� y luego �Guardar ahora� para guardar tu proyecto.

![screenshot](band-save.png)

# Segundo paso: El Escenario { .activity }

El __escenario__ es el �rea a la izquierda, y es donde tu proyecto cobra vida. Imag�nate que es el �rea donde se hace la presentaci�n, �como en un escenario real!

## Lista de verificaci�n de actividades { .check }

+ �En estos momentos, el escenario es de color blanco y se ve bastante aburrido! Agreguemos un fondo al escenario haciendo clic en �Elegir fondo de la biblioteca�.

	![screenshot](band-stage-choose.png)

+ Haz clic en �Interiores� en la izquierda y luego haz clic en un fondo de escenario y luego clic en �OK�.

	![screenshot](band-backdrop.png)

+ Ahora tu escenario deber�a verse as�:

	![screenshot](band-stage.png)

# Tercer paso: C�mo crear un tambor { .activity }

Codifiquemos tu tambor para que pueda sonar cuando se lo toca.

## Lista de verificaci�n de actividades { .check }

+ Puedes encontrar los bloques de c�digo en la leng�eta �Secuencias de comandos� �y todas tienen c�digos de color! 

	Haz clic en el objeto tambor y luego arrastra estos 2 bloques al �rea de c�digo a la derecha, asegur�ndote de que est�n conectados juntos (como los bloques de lego):

	![screenshot](band-code.png)

+ �Haz clic en el tambor para probar tu nuevo instrumento!

+ Tambi�n puedes cambiar c�mo se ve tu tambor cuando le hacen clic, creando un nuevo disfraz. Haz clic en la leng�eta �Disfraces�, y ver�s la imagen del tambor.

	![screenshot](band-drum-costume.png)

+ Haz clic con el bot�n derecho en el disfraz y haz clic en �duplicar� para crear una copia del disfraz.

	![screenshot](band-drum-duplicate.png)

+ Haz clic en el nuevo disfraz (que se llama �tambor 2�) y luego selecciona la herramienta de l�nea y dibuja l�neas para que se vea como que el tambor est� produciendo sonidos.

	![screenshot](band-drum-hit.png)

+ En este momento los nombres de los disfraces no son muy �tiles. Renombra los 2 disfraces a �sin tocar� y �tocado� ingresando el nuevo nombre para cada disfraz en la caja de texto.

	![screenshot](band-drum-name.png)

+ �Ahora que ya tienes 2 disfraces diferentes para tu tambor, puedes elegir qu� disfraz desplegar! Agrega estos 2 bloques a tu tambor:

	![screenshot](band-looks.png)

	El bloque de c�digo para cambiar el disfraz est� en la secci�n �Vistas� {.blocklooks}.

+ Prueba tu tambor. �Cuando haces clic en el tambor, deber�a verse como que est� siendo tocado!

## Guarda tu proyecto { .save }

##Desaf�o: Mejora tu tambor { .challenge }

+ �Puedes cambiar el sonido que hace tu tambor cuando se le hace clic? 

![screenshot](band-drum-sound.png)

+ �Puedes tambi�n hacer que el tambor haga un sonido cuando se presiona la barra espaciadora? Necesitar�s utilizar este bloque �evento� {.blockevents}:

```blocks
	al presionar tecla [espacio v] 
```

Puedes copiar tu c�digo existente haciendo clic en el c�digo con el bot�n derecho y haciendo clic en �duplicar�.

![screenshot](band-duplicate-code.png)

## Guarda tu proyecto { .save }

# Cuarto paso: Crear un cantante { .activity .new-page }

�Agreguemos un cantante a tu banda!

## Lista de verificaci�n de actividades { .check }

+ Agrega otros 2 objetos a tu escenario; un cantante y un micr�fono.

	![screenshot](band-singer-mic.png)

+ Antes de que puedas hacer que tu cantante cante, necesitar�s agregar un sonido a tu objeto. Aseg�rate de haber seleccionado tu cantante, y luego haz clic en la leng�eta �Sonidos� y haz clic en �Elegir sonido de la biblioteca�:

	![screenshot](band-import-sound.png)

+ Si haces clic en �Voces� en el lado izquierdo, podr�s elegir sonidos apropiados para agregar a tu objeto.

	![screenshot](band-choose-sound.png)

+ Ahora que has agregado el sonido, puedes agregar este c�digo a tu cantante:

	```blocks
		al hacer clic en este objeto
		Tocar sonido [singer1 v] y esperar
	```

+ Haz clic en tu cantante, para asegurarte de que cante cuando le haces clic.

## Guarda tu proyecto { .save }

##Desaf�o: C�mo cambiar el disfraz de tu cantante { .challenge }
�Puedes hacer que tu cantante se vea como que est� cantando cuando le haces clic? Si necesitas ayuda, puedes usar las instrucciones anteriores para crear un tambor.

![screenshot](band-singer-final.png)

�No olvides probar que tu nuevo c�digo funciona!

## Guarda tu proyecto { .save }

##Desaf�o: Crea tu propia banda { .challenge }
�Usa lo que aprendiste en este proyecto para crear tu propia banda! Puedes crear cualquier instrumento que desees, pero f�jate en los sonidos disponibles y en los instrumentos para tener algunas ideas.

![screenshot](band-ideas.png)

Sin embargo, tus instrumentos no tienen que ser sensibles. Puedes, por ejemplo, crear un piano hecho de muffins!

![screenshot](band-piano.png)

Puedes usar los objetos existentes y al mismo tiempo dibujar los tuyos propios.

![screenshot](band-draw.png)

�Si tienes un micr�fono puedes grabar tus propios sonidos, o incluso usar una c�mara web para tocar los instrumentos! 

![screenshot](band-io.png)

## Guarda tu proyecto { .save }
