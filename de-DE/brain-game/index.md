---
title: Create Your Own World 
description: Lerne, wie du dein eigenes Open-World Abenteuerspiel erstellen kannst.
layout: project
notes: "Create Your Own World - notes.md"
---

# Einf�hrung { .intro }

In diesem Projekt lernst du, wie du dein eigenes Open-World Abenteuerspiel anfertigen kannst.

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="https://scratch.mit.edu/projects/embed/34248822/?autostart=false" frameborder="0"></iframe>
  <img src="images/world-final.png">
</div>

# Schritt 1: Programmiere deinen Spieler { .activity }

Lass uns damit beginnen, einen Spieler zu erstellen, der sich rund um deine Welt bewegen kann.

## Aktivit�ts-Checkliste { .check }

+ �ffne das 'Create Your Own World' (Erstelle deine eigene Welt) Scratch Projekt online unter <a href="http://jumpto.cc/world-go" target="_blank">jumpto.cc/world-go</a> oder lade es von <a href="http://jumpto.cc/world-get" target="_blank">jumpto.cc/world-get</a> herunter und �ffne es dann, wenn du den offline Editor benutzt.

	![screenshot](images/world-starter.png)

+ Lass uns die Pfeiltasten benutzen, um den Spieler rund ums Spielfeld zu bewegen. Wenn der Spieler die Pfeil-hoch-Taste dr�ckt, dann willst du, dass der Spieler nach oben geht, indem wir dessen y-Koordinaten �ndern. F�ge diesen Code zum `player` (Spieler) Sprite hinzu:

	```Bl�cke
		wenn Flagge geklickt wurde
		f�r immer
			wenn <Schl�ssel [Pfeil hoch V] gedr�ckt wurde? > dann
				y um (2) �ndern
			beenden
		beenden
	```

+ Teste deinen Spieler, indem du auf die Flagge klickst und dann die Pfeil-hoch-Taste gedr�ckt h�ltst. Bewegt sich dein Spieler nach oben?

	![screenshot](images/world-up.png)

+ Um den Spieler nach links zu bewegen, musst du einen weiteren `if` {.blockcontrol} (wenn) Block zu deinem Spieler hinzuf�gen, welcher dann die x-Koordinaten �ndert:

	```Bl�cke
		wenn Flagge geklickt wurde
		f�r immer
			wenn <Schl�ssel [Pfeil hoch V] gedr�ckt wurde? > dann
				y um (2) �ndern
			beenden
			wenn <Schl�ssel [linker Pfeil V] gedr�ckt wurde? > dann
				x um (-2) �ndern
			beenden
		beenden
	```

## Aufgabe: Sich in alle vier Richtungen bewegen {.challenge}
Kannst du noch mehr Code zu deinem Spieler hinzuf�gen, damit er sich nach oben, nach unten, nach links oder nach rechts bewegen kann. Benutze den Code, den du bereits hast, um dir hierbei zu helfen!

## Projekt speichern { .save }

+ Teste deinen Spieler erneut und du wirst sehen, dass er die F�higkeit hat, durch die hellgrauen W�nde durchzugehen.

	![screenshot](images/world-walls.png)

+ Um dieses Problem zu beheben, musst du den Spieler bewegen, aber ihn dann zur�ck bewegen, wenn er eine hellgraue Wand ber�hrt. Hier ist der Code den du brauchst:

	```Bl�cke
		wenn Flagge geklickt wurde
		f�r immer
			wenn <Schl�ssel [Pfeil hoch V] gedr�ckt wurde? > dann
				y um (2) �ndern
				wenn < Farbe ber�hrt [#BABABA]? > dann
					y um (-2) �ndern
				beenden
			beenden
		beenden
	```

	Hast du gemerkt, dass der neue `if`{.blockcontrol} (wenn) `touching color`{.blocksensing} (Farbe ber�hrt) Block sich _innerhalb_ des `if`{.blockcontrol} (wenn) `key [up arrow]`{.blocksensing} (Schl�ssel [Pfeil hoch]) Blocks befindet?

+ Teste diesen neuen Code, indem du unter die Wand gehst (du solltest nicht in der Lage sein, in die Wand hoch zu gehen).

	![screenshot](images/world-walls-test.png)

+ Lass uns das Gleiche f�r die linke Pfeiltaste tun, gehe zur�ck, wenn der Spieler eine Wand ber�hrt. Hier ist, wie der Code f�r deinen Spieler bislang aussehen sollte:

	![screenshot](images/world-wall-code.png)

## Aufgabe: Repariere die Bewegung deines Spielers {.challenge}
F�ge Code zu deinem Spieler hinzu, damit er nicht in jede Richtung durch die Wand laufen kann. Benutze den Code, den du bereits hast, um dir hierbei zu helfen!

## Projekt speichern { .save }

# Schritt 2: Programmiere deine Welt { .activity }

Lass uns jetzt erm�glichen, dass der Spieler durch die T�ren in ein anderes Zimmer gelangen kann!

## Aktivit�ts-Checkliste { .check }

+ Dein Projekt enth�lt bereits den Hintergrund f�r weitere Zimmer:

	![screenshot](images/world-backdrops.png)

+ Du brauchst eine neue 'for all sprites' (f�r alle Sprites) Variable namens `room` {.blockdata} (Zimmer), um mitverfolgen zu k�nnen, in welchem Zimmer sich der Spieler gerade aufh�lt. 

	![screenshot](images/world-room.png)

+ Wenn der Spieler die orange-farbene T�r im ersten Zimmer ber�hrt, sollte der n�chste Hintergrund angezeigt werden und der Spieler sollte sich zur�ck zur linken Seite des Stadiums bewegen. Hier ist der Code, den du hierf�r brauchst: Er sollte innerhalb der `forever` {.blockcontrol} (f�r immer) Schleife des Spielers eingef�gt werden:

	```Bl�cke
		wenn < Farbe ber�hrt [#F2A24A] > dann
			Hintergrund zu [n�chster Hintergrund V] ver�ndern
			gehe zu x: (-200) y: (0)
			[Zimmer V] um (1) �ndern
		beenden
	```

+ F�ge diesen Code zum _Start_ deines Spieler-Codes hinzu, (vor der `forever` {.blockcontrol} (f�r immer) Schleife), um zu gew�hrleisten, dass alles wieder auf Null gestellt wird, wenn die Flagge angeklickt wird:

	```Bl�cke
		[Zimmer V] zu (1) einstellen
		gehe zu x: (-200) y: (0)
		Hintergrund zu [Zimmer1 V] �ndern
	```

+ Klicke die Flagge und bewege deinen Spieler �ber die orange-farbene T�r. Geht dein Spieler zum n�chsten Bildschirm hin�ber? �ndert sich die `room` {.blockdata} Zimmer-Variable zu 2?

	![screenshot](images/world-room-test.png)

## Aufgabe: Ins vorherige Zimmer gehen {.challenge}
Kannst du deinen Spieler ins vorherige Zimmer bewegen, wenn er eine gelbe T�r ber�hrt? Denke daran, dass dieser Code _sehr_ �hnlich sein wird wie der Code, den du bereits hinzugef�gt hast, um ins n�chste Zimmer zu gelangen.

## Projekt speichern { .save }

# Schritt 3: Schilder { .activity }

Lass uns Schilder zu deiner Welt hinzuf�gen, um eine Wegweisung f�r deinen Spieler auf seiner Reise zu bereiten.

## Aktivit�ts-Checkliste { .check }

+ Dein Projekt beinhaltet ein Willkommens- Schild Sprite:

	![screenshot](images/world-sign.png)

+ Dieses Schild ist nur in Zimmer 1 sichtbar, lass uns jetzt noch weiteren Code zum Schild hinzuf�gen, um zu gew�hrleisten, dass dies passiert:

	```Bl�cke
		wenn Flagge geklickt wurde
		f�r immer
			wenn < (Zimmer) = [1] > dann
				zeigen
			oder
				verstecken
			beenden
		beenden
	```

+ Teste dein Schild, indem du zwischen den Zimmern hin- und hergehst. Dein Schild sollte nur in Zimmer 1 sichtbar sein.

	![screenshot](images/world-sign-test.png)

+ Ein Schild n�tzt aber nicht viel, wenn nichts darauf steht! Lass uns weiteren Code (in einem separaten Block) hinzuf�gen, um eine Meldung anzuzeigen, wenn das Schild den Spieler ber�hrt:

	```Bl�cke
		wenn Flagge geklickt wurde
		f�r immer
			wenn < [Spieler V] ber�hrt? > dann
				[Willkommen! Kannst du den Schatz finden?] sagen
			oder
				[] sagen
			beenden
		beenden
	```
+ Teste dein Schild und du solltest eine Meldung sehen k�nnen, wenn der Spieler es ber�hrt.

	![screenshot](images/world-sign-test2.png)

## Projekt speichern { .save }

## Aufgabe: Schatz gefunden! {.challenge}
Klicke mit der rechten Maustaste auf das Schatzkisten-Sprite und w�hle 'show' (zeigen). 

Kannst du es veranlassen, dass das Schatzkisten-Sprite nur in Zimmer 3 erscheint und dann 'Well done!' (Gut gemacht!) sagen, wenn der Spieler die Kiste ber�hrt?


![screenshot](images/world-treasure.png)

## Projekt speichern { .save }

# Schritt 4: Leute { .activity }

Lass uns weitere Leute zu deiner Welt hinzuf�gen zu denen dein Spieler Umgang hat.

## Aktivit�ts-Checkliste { .check }

+ F�ge diesen Code zum Personen-Sprite hinzu, sodass diese Person mit deinem Spieler spricht. Dieser Code ist sehr �hnlich zu dem Code, den du bereits zu deinem Schild hinzugef�gt hast:

	```Bl�cke
		wenn Flagge geklickt wurde
		gehe zu x: (0) y: (-150)
		f�r immer
			wenn < [Spieler V] ber�hrt? > dann
				[Wusstest du, dass du durch orange-farbene und gelb-farbene T�ren gehen kannst?] sagen
			oder
				[] sagen
			beenden
		beenden
	```

+ Du k�nntest deiner Person auch erlauben, sich zu bewegen, indem du diese beiden Bl�cke benutzt:

	```Bl�cke
		(1) Schritt gehen
		wenn an der Kante, abprallen
	```

	Deine Person wird anders handeln, je nachdem, ob du diesen Code in der `forever` {.blockcontrol} (f�r immer)Schleife oder in dem `if` {.blockcontrol} (wenn) Block platzierst. Probier beides mal aus, um zu sehen, welches davon dir besser gef�llt.

	![screenshot](images/world-person-test.png)

+ Hast du bemerkt, dass deine Person sich kopf�ber dreht? Um dies zu stoppen, klicke auf das Informationssymbol (`i`{.blockmotion}) des Sprites und klicke auf den Punkt, um den Drehungsstil zu reparieren.

	![screenshot](images/world-person-rotate.png)

## Aufgabe: Verbessere deine Person {.challenge}
Kannst du weiteren Code zu deiner neuen Person hinzuf�gen, sodass sie nur in Zimmer 1 erscheint? Achte darauf, dass du deinen neuen Code testest!

## Projekt speichern { .save }

+ Du kannst auch ein paar patroullierende Feinde hinzuf�gen, die das Spiel automatisch beenden, wenn der Spieler sie ber�hrt. F�ge ein neues Feind-Sprite hinzu und �ndere den Drehungsstil, genau so, wie du es mit dem 'person' Sprite getan hast.

+ F�ge den Code zu deinem Feind hinzu, damit er nur in Zimmer 2 erscheint.

+ Du wirst auch Code hinzuf�gen m�ssen, um den Feind bewegen zu k�nnen und um das Spiel zu beenden, wenn der Feind den Spieler ber�hrt. Es ist leichter, dies in separaten Code-Bl�cken zu tun. Hier ist, wie dein Feind-Code aussehen sollte:

	![screenshot](images/world-enemy-code.png)

+ Teste deinen Feind, um sicher zu stellen, dass:
	+ er nur in Zimmer 2 sichtbar ist;
	+ er das Zimmer patroulliert;
	+ das Spiel endet, wenn der Spieler ber�hrt wurde.

## Projekt speichern { .save }

## Aufgabe: Noch mehr Feinde {.challenge}
Kannst du einen weiteren Feind in Zimmer 3 hinzuf�gen, der durch die Spalte in der Wand auf- und ab marschiert?

![screenshot](images/world-enemy2.png)

## Projekt speichern { .save }

# Schritt 5: M�nzen sammeln { .activity }

## Aktivit�ts-Checkliste { .check }

+ F�ge eine neue Variable namens `coins` {.blockdata} (M�nzen) zu deinem Projekt hinzu.

+ Klicke mit der rechten Maustaste auf das 'coin' (M�nzen) Sprite und w�hle 'show' (zeigen). 

![screenshot](images/world-coins.png)

+ F�ge den Code zu deiner M�nze hinzu, sodass sie nur in Zimmer 1 erscheint.

+ F�ge Code zu deinem M�nzen-Sprite hinzu, um 1 zu deinen `coins` {.blockdata} (M�nzen) hinzuzuf�gen, nachdem eine M�nze eingesammelt wurde:

	```Bl�cke
		wenn Flagge geklickt wurde
		warten bis < [Spieler V] ber�hrt?>
		[M�nzen V] um (1) �ndern
		[andere Scripts in Sprite V] stoppen
		verstecken
	```

	Der Code `stop other scripts in Sprite` {.blockcontrol} (andere Scripts in Sprite stoppen) wird ben�tigt, damit die M�nze nicht l�nger in Zimmer 1 angezeigt wird, nachdem sie eingesammelt worden ist.

+ Du musst auch Code hinzuf�gen, um deine `coins` {.blockdata} (M�nzen) Variable bei Spielbeginn auf 0 einzustellen.

+ Teste dein Projekt: Das Sammeln deiner M�nzen sollte deine Punktzahl zu 1 �ndern.

## Aufgabe: Weitere M�nzen {.challenge}
Kannst du noch mehr M�nzen zu deinem Spiel hinzuf�gen? Sie k�nnen in einem anderen Zimmer platziert werden und manche M�nzen k�nnten sogar von den patroullierenden Feinden bewacht werden.

# Schritt 6: T�ren und Schl�ssel { .activity }

## Aktivit�ts-Checkliste { .check }

+ Bearbeite das Kost�m des Schl�ssel-Sprites, damit es blau ist. Klicke mit der rechten Maustaste auf das Schl�ssel-Sprite und w�hle 'show' (zeigen), damit es im Stadium erscheint. Schalte dein Stadium zu Hintergrund 3 und platziere den Schl�ssel irgendwo hin, wo er schwierig zu erreichen ist!

 	![screenshot](images/world-key.png)

+ Achte darauf, dass dein Schl�ssel nur in Zimmer 3 sichtbar ist.

+ Erstelle eine neue Listenvariable namens `inventory` {.blockdata} (Inventar). Dies wird der Ort sein, an dem du all die Gegenst�nde, die dein Spieler einsammelt, aufbewahrst, bzw. speicherst.

+ Der Code zum Einsammeln des Schl�ssels ist sehr �hnlich wie der Code zum Einsammeln der M�nzen. Der Unterschied ist, dass du den Schl�ssel zu deinem Inventar hinzuf�gst.

	```Bl�cke
		wenn Flagge geklickt wurde
		warten bis < [Spieler V] ber�hrt?>
		[blauen Schl�ssel] zu [Inventar V] hinzuf�gen
		[andere Scripts in Sprite V] stoppen
		verstecken
	```

+ Teste deinen Schl�ssel, um zu sehen, ob du ihn einsammeln kannst und ob du ihn zu deinem Inventar hinzuf�gen kannst. Denke daran, den Code zu deinem Stadium hinzuzuf�gen und dein Inventar bei Spielbeginn zu leeren.

	```Bl�cke
		(alle V) von [Inventar V] l�schen
	```

+ Platziere dein blaues T�r-Sprite quer �ber der Spalte in den beiden W�nden.

	![screenshot](images/world-door.png)

+ F�ge Code zu deiner T�r hinzu, damit sie nur in Zimmer 3 sichtbar ist.

+ Du wirst auch deine blaue T�r verstecken m�ssen, damit dein Spieler daran vorbei gehen kann, nachdem du den blauen Schl�ssel in deinem Inventar hast.

	```Bl�cke
		wenn Flagge geklickt wurde
		warten bis <[Inventar V] [blauen Schl�ssel] enth�lt>
		[andere Scripts in Sprite V] stoppen
		verstecken
	```

+ Teste dein Projekt und schau, ob du den blauen Schl�ssel einsammeln kannst, um die T�r zu �ffnen!

## Projekt speichern { .save }

## Aufgabe: Erstelle deine eigene Welt {.challenge}
Du kannst jetzt fortfahren, deine eigene Welt zu erstellen. Hier sind ein paar Vorschl�ge:

+ �ndere dein Spielumfeld und deine Spielgrafik;
+ F�ge Sound und Musik zu deinem Spiel hinzu;
+ F�ge weitere Leute, sowie Feinde, Schilder und M�nzen hinzu;
+ F�ge rote und gelbe T�ren hinzu, die ihre eigenen Schl�ssel zum �ffnen ben�tigen;
+ F�ge weitere Zimmer zu deiner Welt hinzu;
+ F�ge andere, n�tzliche Gegenst�nde zu deinem Spiel hinzu;

+ Benutze M�nzen, um Informationen von anderen Leuten zu erhalten;

	![screenshot](images/world-bribe.png)

+ Du k�nntest auch T�ren im Norden und S�den hinzuf�gen, damit der Spieler in allen 4 Richtungen zwischen den Zimmern hin- und hergehen kann. Zum Beispiel: Wenn du 9 Zimmer h�ttest, k�nntest du sie als ein 3 x 3 Raster betrachten. Du kannst dann die Nummer 3 zur Zimmerzahl hinzuf�gen, um dich 1 Stufe herunter zu bewegen.

	![screenshot](images/world-north-south.png)

## Projekt speichern { .save }

