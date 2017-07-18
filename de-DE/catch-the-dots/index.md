---
title: Fange die Punkte
description: Lerne, wie man ein Fang-die-Punkte-Spiel herstellt.
layout: project
notes: "Catch the Dots - notes.md"
---

# Einf�hrung { .intro }

In diesem Projekt lernst du, wie man ein Spiel herstellt, in welchem du die bunten Punkte dem dazu geh�rigen, richtigen Teil des Controllers zuordnen musst.

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="https://scratch.mit.edu/projects/embed/44942820/?autostart=false" frameborder="0"></iframe>
  <img src="images/dots-final.png">
</div>

# Schritt 1: Einen Controller herstellen { .activity }

Lass uns damit beginnen, einen Controller herzustellen, der dazu benutzt wird, um die Punkte einzufangen.

## Aktivit�ts-Checkliste { .check }

+ �ffne das 'Catch the Dots' (Fang die Punkte) Scratch Projekt online unter <a href="http://jumpto.cc/dots-go" target="_blank">jumpto.cc/dots-go</a> oder lade es von <a href="http://jumpto.cc/dots-get" target="_blank">jumpto.cc/dots-get</a> herunter udn �ffnes es dann, wenn du den offline Editor benutzt.

	Du solltest ein Controller Sprite sehen k�nnen:

	![screenshot](images/dots-controller.png)
	
	
+ Drehe deinen Controller nach rechts, wenn die rechte Pfeiltaste gedr�ckt wird:

	```Bl�cke
		wenn Flagge geklickt wurde
		f�r immer
			wenn <Schl�ssel [rechter Pfeil V] gedr�ckt?> dann
				um (3) Grad nach rechts drehen 
			beenden
		beenden
	```
+ Teste deinen Controller: Er sollte sich nach rechts drehen.

## Projekt speichern { .save }

## Aufgabe: Nach links drehen {.challenge}
Kannst du versuchen, dass dein Controller sich nach links dreht, wenn die linke Pfeiltaste gedr�ckt wird?

## Projekt speichern { .save }

# Schritt 2: Punkte einsammeln { .activity }

Lass uns ein paar Punkte hinzuf�gen, die der Spieler mit dem Controller einsammeln kann.

## Aktivit�ts-Checkliste { .check }

+ Erstelle ein neues Sprite namens 'red' (rot). Dieses Sprite sollte ein kleiner roter Punkt sein.

	![screenshot](images/dots-red.png)

+ F�ge dieses Script zu deinem 'red' roten Punkt Sprite hinzu, um alle paar Sekunden einen neuen Punkt-Klon zu erstellen:

	```Bl�cke
		wenn Flagge geklickt wurde
		verstecken
		(2) Sek. warten
		f�r immer
			erstelle einen Klon von [mir selbst V]
			(zuf�llig ausw�hlen(5) bis (10)) Sek. warten
		beenden
	```

+ Wenn jeder Klon erstellt wurde, willst du, dass er in einer der 4 Ecken des Stadiums erscheint.

	![screenshot](images/dots-start.png)

	Damit dies geschieht, musst du als erstes eine neue __Liste__ namens `start positions` {.blockdata} (Startpositionen) erstellen und auf das `(+)` klicken, um die Werte `-180` und `180` hinzuzuf�gen.

	![screenshot](images/dots-list.png)

+ Du kannst diese 2 Listen-Artikel benutzen, um eine zuf�llige Ecke des Stadiums auszuw�hlen. F�ge diesen Code zum 'dot' (Punkt) Sprite hinzu, sodass jeder neue Klon sich in eine zuf�llig ausgew�hlte Ecke bewegt und sich dann langsam auf den Controller zubewegt.

	```Bl�cke
		wenn ich als Klon starte
		gehe zu x: (Artikel (zuf�llig ausgew�hlte V) der [Startpositionen V]) y: (Artikel (zuf�llig ausgew�hlte V) der [Startpositionen V]) 
		zeigt zum [Controller V]
		zeigen
		wiederholen bis <Ber�hrung von [Controller V]?>
			um (1) Schritt bewegen
		beenden
	```

	Der o.g. Code w�hlt entweder `-180` oder `180` f�r die x _und_ y Positionen, was bedeutet, dass jeder Klon in einer Ecke des Stadiums beginnt.

+ Teste dein Projekt. Du solltest jetzt sehen k�nnen, dass ganz viele rote Punkte in jeder Ecke des Bildschirms erscheinen und sich langsam auf den Controller hinzubewegen.

	![screenshot](images/dots-red-test.png)

+ Erstelle 2 neue Variable namens `lives` {.blockdata} (Leben) und `score` {.blockdata} (Punktzahl).

+ F�ge den Code zu deinem Stadium hinzu, um die `lives` {.blockdata} Leben-Blockdaten auf 3 und die `score` {.blockdata} Punktzahl-Blockdaten auf 0 zu Beginn des Spiels einzustellen.

+ Du musst den Code zum Ende deines roten `when I start as a clone` {.blockcontrol} (wenn ich als Klon beginne) Punkt-Codes hinzuf�gen, damit entweder 1 zur `score` {.blockdata} (Punktzahl) des Spielers hinzugef�gt wird, wenn die Farben zueinander passen oder 1 vom `lives` {.blockdata} Leben des Spielers abgezogen wird, wenn die Farben nicht zueinander passen.

	```Bl�cke
		um (5) Schritt bewegen
		wenn <Farbe ber�hren [#FF0000]?> dann
			[Punktzahl V] um (1) �ndern
			Sound [Pop V] spielen
		oder
			[Leben V] um (-1) �ndern
			Sound [Laser1 V] spielen
		beenden
		diesen Klon l�schen
	```

+ F�ge diesen Code zum Ende deines Stadion-Scripts hinzu, damit das Spiel beendet wird, wenn der Spieler alle seine Leben verloren hat:

	```Bl�cke
		warten bis <(Leben) < [1]>
		[alle V] stoppen
	```

+ Teste dein Spiel, um zu gew�hrleisten, dass dieser Code wie erwartet funktioniert.

## Projekt speichern { .save }

## Aufgabe: Noch mehr Punkte {.challenge}	
Kopiere dein 'red' (rotes) Punkt-Sprite zweimal und nenne die beiden neuen Sprites 'yellow' (gelb) und 'blue' (blau).

![screenshot](images/dots-more-dots.png)

Bearbeite diese Sprites (f�ge deren Code hinzu), sodass jeder bunte Punkt zur richtigen Farbe auf dem Controller passt. Denk daran, dein Projekt zu testen und achte darauf, dass du jeweils zum richtigen Zeitpunkt entweder Punkte sammelst oder Leben verlierst und dass dein Spiel weder zu leicht noch zu schwer ist!

![screenshot](images/dots-all-test.png)

## Projekt speichern { .save }

# Schritt 3: Den Schwierigkeitsgrad steigern { .activity .new-page}

Lass uns das Spiel noch schwieriger gestalten, je l�nger der Spieler am Leben bleibt, indem wir langsam die Verz�gerung zwischen dem Erscheinen der Punkte drosseln.

## Aktivit�ts-Checkliste { .check }

+ Erstelle eine neue Variable namens`delay` {.blockdata} (Verz�gerung).

+ Erstelle nun in deinem Stadium ein neues Script, welches die Verz�gerung auf eine hohe Zahl einstellt und dann langsam diese Verz�gerungszeit drosselt.

	```Bl�cke
		wenn Flagge geklickt wurde
		[Verz�gerung V] auf (8) einstellen
		wiederholen bis < (Verz�gerung) = (2)>
			(10) Sek. warten
			[Verz�gerung V] um (-0.5) �ndern
		beenden
	```

	Merkst du, dass dies sehr �hnlich wie eine Spielzeituhr funktioniert?

+ Abschlie�end kannst du diese `delay` {.blockdata} (Verz�gerung) Variable in deinen roten, gelben und blauen Punkten Scripts benutzen. Entferne den Code, der eine zuf�llig ausgew�hlte Zahl an Sekunden zwischen dem Erstellen von Klonen wartet und ersetze ihn mit deiner neuen `delay` {.blockdata} (Verz�gerung) Variable:

	```Bl�cke
		(Verz�gerung) Sek. warten
	```

+ Teste deine neue `delay` {.blockdata} (Verz�gerung) Variable und schau, ob die Verz�gerung zwischen den einzelnen Punkten langsam gesenkt wird. Funktioniert dies bei allen 3 der bunten Punkte? Kannst du den Wert der `delay` {.blockdata} (Verz�gerung) Variable sehen, wie er sich senkt?

## Projekt speichern { .save }

## Aufgabe: Sich schneller bewegende Punkte {.challenge}
Kannst du dein Spiel verbessern, indem du eine `speed` {.blockdata} (Geschwindigkeit) Variable hinzuf�gst, sodass die Punkte damit beginnen, sich je einen Schritt zur Zeit zu bewegen und dann langsam aber sicher schneller und schneller werden? Das funktioniert sehr �hnlich wie die `delay` {.blockdata} (Verz�grung) Variable, die du, wie o.g., benutzt hast und du kannst diesen Code benutzen, um dir hierbei zu helfen.

## Projekt speichern { .save }

# Schritt 4: Hohe Punktzahl { .activity }

Lass uns die hohe Punktzahl speichern, damit der Spieler sehen kann, wie gut sein Fortschritt ist.

## Aktivit�ts-Checkliste { .check }

+ Erstelle eine neue Variable namens `high score` {.blockdata} (hohe Punktzahl).

+ Klicke auf dein Stadium und erstelle einen neuen, speziell angefertigten Block namens `check high score` {.blockmoreblocks} (hohe Punktzahl pr�fen).

	![screenshot](images/dots-custom-1.png)

+ F�ge deinen neuen, speziell angefertigten Block kurz vor Spielende hinzu.

	![screenshot](images/dots-custom-2.png)

+ F�ge den Code zu deinem speziell angefertigten Block hinzu, um die aktuelle `score` {.blockdata}  (Punktzahl) als `high score` {.blockdata} (hohe Punktzahl) zu speichern`if` {.blockcontrol} (wenn) sie bis dahin die h�chste Punktzahl ist:

	```Bl�cke
		[hohe Punktzahl pr�fen] definieren
		wenn <(Punktzahl) > (hohe Punktzahl)> dann
			[hohe Punktzahl V] auf (Punktzahl) einstellen
		beenden
	```

+ Teste den Code, den du hinzugef�gt hast. Spiele dein Spiel, um zu pr�fen, ob die `high score` {.blockdata} (hohe Punktzahl) korrekt aktualisiert wurde.

## Projekt speichern { .save }

## Aufgabe: Verbessere dein Spiel! {.challenge}
Kannst du an Wege denken, wie du dein Spiel verbessern k�nntest? Du k�nntest z. B. spezielle Punkte kreieren, die:

+ deine Punktzahl verdoppeln;
+ die Punkte verlangsamen;
+ alle anderen, sichtbaren Punkte auf dem Bildschirm verstecken!

## Projekt speichern { .save }

## Aufgabe: Spielmen� {.challenge}
Kannst du ein Men� (mit Tasten) zu deinem Spiel hinzuf�gen? Du k�nntest einen Spielanleitungsbildschirm hinzuf�gen oder einen separaten Bildschirm, um dort die hohe Punktzahl anzuzeigen. Falls du hierbei Hilfestellung ben�tigst, dann wird dir das 'Brain Game' Projekt hierbei n�tzlich sein.

