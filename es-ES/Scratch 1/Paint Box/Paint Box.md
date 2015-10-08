---
t�tulo: Caja de l�pices
nivel: Scratch 1
idioma: es-ES
tipo de planilla: scratch
embeds: "*.png"
materiales: ["Recursos para el l�der del Club /*.*","Recursos del Proyecto /*.*"]
...

# Introducci�n { .intro }

�En este Proyecto, vas a crear tu propio programa para pintar!

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/63473366/?autostart=false" frameborder="0"></iframe>
  <img src="paint-final.png">
</div>

# Primer paso: Crear un l�piz { .activity }

Comencemos por crear un l�piz, que puedes usar para dibujar en el escenario.

## Lista de verificaci�n de actividades { .check }

+ Comienza un nuevo proyecto Scratch, y elimina el objeto gato para que tu proyecto est� vac�o. Puedes encontrar el editor de Scratch en l�nea en <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.

+ Agrega el objeto l�piz a tu proyecto.

	![screenshot](paint-pencil.png) 

+ Haz clic en �Disfraces�, y elimina el disfraz �pencil-b�.

	![screenshot](paint-pencil-delete.png) 

+ Renombra tu disfraz �l�piz-azul�, y usa la herramienta �Colorear una forma� para hacer que el l�piz sea azul. 

	![screenshot](paint-pencil-blue.png) 

+ Como vas a estar usando tu rat�n para dibujar, querr�s que tu l�piz siga al rat�n �por siempre� {.blockcontrol}. Agrega este c�digo a tu objeto l�piz:

	```blocks
		al presionar bandera verde
		por siempre
		  ir a [mouse pointer v]
		fin
	```

+ Prueba el c�digo haciendo clic en la bandera y luego moviendo el rat�n en el escenario. �Hace lo que esperabas que hiciera? 

+ �Te has dado cuenta de que es el centro del l�piz y no la punta, lo que sigue al apuntador del rat�n?

	![screenshot](paint-center.png)

	Para solucionarlo, haz clic en el disfraz �l�piz-azul� de tu objeto l�piz, y haz clic en �Establecer centro del disfraz�.

	![screenshot](paint-center-icon.png)

+ Deber�as ver que aparece una cruz en el disfraz. Ahora puedes hacer clic justo debajo de la punta del l�piz, y establecerla esta punta como el centro del disfraz.

	![screenshot](paint-pencil-center.png)

+ Haz clic en la leng�eta �Secuencias de comandos�, y luego prueba tu l�piz una vez m�s. �Funciona mejor que antes?

+ Ahora hagamos que tu l�piz dibuje `si` {.blockcontrol} se ha hecho clic en el rat�n. Agrega este c�digo a tu objeto l�piz:

	![screenshot](paint-pencil-draw-code.png)	

+ Prueba tu c�digo una vez m�s. Esta vez, mueve el l�piz por el escenario y mant�n apretado el bot�n del rat�n. �Puedes dibujar con el l�piz?

	![screenshot](paint-draw.png)

## Guarda tu proyecto { .save }

# Segundo paso: L�pices de colores { .activity }

�Agreguemos distintos l�pices de colores a tu proyecto, y permit�mosle al usuario que pueda elegir entre ellos!

## Lista de verificaci�n de actividades { .check }

+ Haz clic en tu objeto l�piz, haz clic en �disfraces� y duplica tu disfraz �l�piz-azul�.

	![screenshot](paint-blue-duplicate.png)

+ Renombra tu nuevo disfraz �l�piz-verde�, y pinta el l�piz de color verde.

	![screenshot](paint-pencil-green.png)

+ Crea dos objetos nuevos, que usar�s para seleccionar el l�piz azul o verde.

	![screenshot](paint-selectors.png)

+ Cuando se hace clic en el selector verde, necesitas `enviar` {.blockevents} un mensaje al objeto l�piz, dici�ndole que tiene que cambiar su disfraz y color de l�piz.

	Para hacerlo, primero agrega este c�digo a tu �cono selector verde:

	```blocks
		al hacer clic en este objeto
		enviar [green v]
	```

	Para crear el bloque `enviar` {.blockevents}, haz clic en la flecha hacia abajo y selecciona �nuevo mensaje��.

	![screenshot](paint-broadcast.png)

	Luego puedes escribir �verde� para crear to nuevo mensaje.

	![screenshot](paint-green-message.png)

+ Ahora necesitas decirle a tu objeto l�piz qu� tiene que hacer cuando recibe el mensaje. Agrega este c�digo a tu objeto l�piz:

	```blocks
		al recibir [green v]
		cambiar disfraz a [pencil-green v]
		fijar color de l�piz a [#00ff00]
	```

	Para fijar el color de l�piz a verde, haz clic en la caja con colores en el bloque `fijar color` {.blockpen}, y haz clic en el �cono selector verde para elegir verde como el color para tu l�piz.

+ Ahora puedes hacer lo mismo para el l�piz azul, agregando este c�digo al objeto selector azul:

	```blocks
		al hacer clic en este objeto
		enviar [blue v]
	```

	...y agrega este c�digo al objeto l�piz:

	```blocks
		al recibir [blue v]
		cambiar disfraz a [pencil-blue v]
		fijar color de l�piz a [#0000ff]
	```

+ Por �ltimo, necesitas decirle a tu objeto l�piz qu� disfraz y color de l�piz elegir, y limpiar la pantalla cuando comienza tu proyecto. Agrega este c�digo al comienzo del c�digo de tu l�piz {.blockevents} `cuando se hace clic en la bandera `  (antes de `por siempre` {.blockcontrol} loop):

	```blocks
		borrar
		cambiar disfraz a [blue-pencil v]
		fijar color de l�piz a [#0000ff]
	```

	�Si lo prefieres, puedes comenzar con un color de l�piz diferente!

+ Prueba tu proyecto. �Puedes cambiar entre los l�pices azul y verde?

	![screenshot](paint-pens-test.png)

## Guarda tu proyecto { .save }

# Tercer paso: Cuando se cometen errores { .activity .new-page }

�A veces se comenten errores, entonces agreguemos un bot�n �limpiar� y una goma a nuestro proyecto!

## Lista de verificaci�n de actividades { .check }

+ Agreguemos un bot�n para limpiar el escenario. Para hacerlo, agrega el objeto letra 'X-block' al escenario, y p�ntalo de rojo.

	![screenshot](paint-x.png)

+ Agrega c�digo a tu nuevo bot�n cancelar para limpiar el escenario cuando se le hace clic.

	```blocks
		al hacer clic en este objeto
		borrar
	```

	�F�jate que no necesitas enviar un mensaje para limpiar el escenario, ya que cualquier objeto puede hacerlo!

+ Tambi�n puedes crear una goma. Si tu l�der del club te dio una carpeta de �Recursos�, haz clic en �Cargar disfraz desde archivo� y agrega la imagen �eraser.svg�.

	![screenshot](paint-eraser-costume.png)
	
	�Si no tienes la imagen eraser.svg, crea en su lugar un nuevo l�piz blanco!

+ Tambi�n deber�as agregar la imagen goma como un nuevo objeto selector. As� es como deber�a verse:

	![screenshot](paint-eraser-stage.png)

+ Luego puedes agregar c�digo al objeto selector goma, para decirle al l�piz que cambie a goma.

	```blocks
		al hacer clic en este objeto
		enviar [eraser v]
	```

+ �Cuando el l�piz recibe este mensaje, puedes crear una goma cambiando el disfraz del l�piz al de goma, y cambiando el color del l�piz al mismo color del escenario!

	```blocks
		al recibir [eraser v]
		cambiar disfraz a [eraser v]
		fijar color de l�piz a [#FFFFFF]
	```

+ Prueba tu proyecto para ver si puedes limpiar y borrar en el escenario.

	![screenshot](paint-erase-test.png)

+ Hay otro problema m�s con el l�piz � puedes dibujar en cualquier parte del escenario, �incluso cerca de los �conos selectores!

	![screenshot](paint-draw-problem.png)

	Para arreglar esto, tienes que decirle al l�piz que solo dibuje si se hace clic en el rat�n _y_ si la posici�n y del rat�n es mayor a -110 (`mouse y`{.blocksensing}`> -120` {.blockoperators}). Cambia la declaraci�n `si` {.blockcontrol} de tu l�piz para que se vea as�:

	![screenshot](pencil-gt-code.png)

+ Prueba tu proyecto. Ahora no deber�as poder dibujar cerca de los bloques selectores.

	![screenshot](paint-fixed.png)

## Guarda tu proyecto { .save }

# Cuarto paso: Cambiar el ancho del l�piz { .activity .new-page }

Permit�mosle al usuario que pueda dibujar eligiendo distintos tama�os de l�pices.

## Lista de verificaci�n de actividades { .check }

+ Primero, agrega una nueva variable que se llame �ancho�. Si no est�s seguro sobre como hacerlo, el Proyecto �Globos� puede ayudarte.

+ Agrega esta l�nea_dentro_del loop del c�digo `por siempre` {.blockcontrol} de tu l�piz:

	```blocks
		fijar tama�o de l�piz a (width)
	```

	El ancho de tu l�piz ahora se fijar� repetidamente al valor de tu variable �ancho�.

+ Puedes cambiar el n�mero almacenado en esta variable haciendo clic en el bot�n derecho sobre tu variable (en el escenario) y haciendo clic en la �barra deslizable�.

	![screenshot](paint-slider.png)

	Ahora puedes arrastrar la barra deslizadora por debajo de la variable para cambiar su valor.

	![screenshot](paint-slider-change.png)

+ Prueba tu proyecto, y f�jate si puedes modificar el ancho de tu l�piz.

	![screenshot](paint-width-test.png)

	Si lo deseas, puedes fijar el valor m�nimo y m�ximo del �ancho� permitido. Para hacerlo, haz clic con el bot�n derecho sobre tu variable y luego haz clic de nuevo en �fijar min y max para la barra deslizable�. Fija los valores m�nimos y m�ximos para tu variable a algo un poco m�s coherente, como 1 y 20.

	![screenshot](paint-slider-max.png)

	Contin�a probando tu variable �ancho� hasta que est�s conforme.

## Guarda tu proyecto { .save }

## Desaf�o: Accesos directos { .challenge }
�Puedes crear accesos directos en el teclado para tus comandos? Por ejemplo:

+ a = Cambiar al l�piz azul
+ v = cambiar al l�piz verde
+ g = cambiar a la goma
+ l = limpiar pantalla

�Incluso podr�as permitirle al usuario cambiar el ancho del l�piz con las teclas de flechas!

## Guarda tu proyecto { .save }

## Desaf�o: M�s l�pices { .challenge }
�Puedes agregar l�pices de color rojo, amarillo y negro a tu programa para pintar? Encontrar�s todas las im�genes que necesitas en la carpeta �Recursos�. �Recuerda agregar los accesos r�pidos en el teclado para estos nuevos l�pices!

�Puedes usar tus l�pices para hacer un dibujo?

![screenshot](paint-final.png)