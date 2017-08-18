---
title: Gehirntraining
description: Lerne, wie man ein Quiz produziert.
layout: project
notes: "Brain Game - notes.md"
---

# Einf�hrung { .intro }

In diesem Projekt lernst du, wie man ein Multiplikations-Quiz produziert, in dem man so viele Fragen wie m�glich innerhalb von 30 Sekunden richtig beantworten musss.

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="https://scratch.mit.edu/projects/embed/42225768/?autostart=false" frameborder="0"></iframe>
  <img src="images/brain-final.png">
</div>

# Schritt 1: Fragen zusammenstellen { .activity }

Lass uns damit beginnen, ein paar beliebig ausgew�hlte Fragen zusammenzustellen, die der Spieler beantworten muss.

## Aktivit�ts-Checkliste { .check }

+ Starte ein neues Scratch Projekt und l�sche das Katzen-Sprite, damit dein Projekt leer ist. Du findest den online Scratch Editor unter <a href="http://jumpto.cc/scratch-new" target="_blank">jumpto.cc/scratch-new</a>.

+ W�hle eine Spielfigur und einen Hintergrund f�r dein Spiel aus. Du kannst dir aussuchen, was du m�chtest! Hier ist ein Beispiel:

	![screenshot](images/brain-setting.png)

+ Erstelle 2 neue Variablen namens `number 1` {.blockdata} (Zahl 1) und `number 2` {.blockdata} (Zahl 2). Diese Variablen speichern die beiden Zahlen, die miteinander multipliziert werden sollen.

	![screenshot](images/brain-variables.png)

+ F�ge den Code zu deiner Spielfigur hinzu, um beide diese Variablen auf eine Zufallszahl `random` {.blockoperators} zwischen 2 und 12 einzustellen.

	```blocks
		Wenn die gr�ne Flagge angeklickt
		setze [number 1 v] auf (Zufallszahl von (2) bis (12))
		setze [number 2 v] auf (Zufallszahl von (2) bis (12))
	```

+ Du kannst dann den Spieler nach der Antwort fragen und ihn wissen lassen, ob er richtig oder falsch geantwortet hat.

	```blocks
		Wenn die gr�ne Flagge angeklickt
		setze [number 1 v] auf (Zufallszahl von (2) bis (12))
		setze [number 2 v] auf (Zufallszahl von (2) bis (12))
		frage (verbinde (number 1) (verbinde [x] (number 2))) und warte
		falls <(Antwort) = ((number 1) * (number 2))> dann
  			sage [Ja! :)] f�r (2) Sek.
		sonst
   			sage [Nein :(] f�r (2) Sek.
		Ende
	```

+ Teste dein Projekt vollst�ndig, indem du eine Frage richtig und eine Frage falsch beantwortest.

+ F�ge eine `forever` {.blockcontrol} (f�r immer) Schleife um diesen Code herum hinzu, damit dem Spieler viele Fragen gestellt werden.

+ Erstelle einen Countdown-Z�hler in diesem Stadium, der eine Variable namens `time` {.blockdata} (Zeit) benutzt. Das 'Ghostbusters' Projekt beinhaltet Anweisungen dar�ber, wie man einen Z�hler herstellt (in Schritt 5), falls du Hilfestellung ben�tigst!

+ Teste dein Projekt erneut: Du solltest jetzt in der Lage sein, weitere Fragen zu stellen, bis die Zeit abgelaufen ist.

## Projekt speichern { .save }

## Aufgabe: Kost�m �ndern {.challenge}
Kannst du das Kost�m deiner Spielfigur �ndern, sodass sie auf die Antwort des Spielers reagiert?

![screenshot](images/brain-costume.png)

## Aufgabe: Eine Punktzahl hinzuf�gen {.challenge}
Kannst du deinem Spiel eine Punktzahl hinzuf�gen? Du kannst einen Punkt f�r jede korrekt beantwortete Frage hinzuf�gen. Wenn du gemein bist, k�nntest du auch die Punktzahl des Spielers wieder zur�ck auf 0 stellen, falls er eine Frage falsch beantwortet hat!

## Projekt speichern { .save }

# Schritt 2: Mehrfache Spiele { .activity .new-page}

Lass uns eine 'play' (spielen) Taste zu deinem Spiel hinzuf�gen, damit du es mehrmals spielen kannst.

## Aktivit�ts-Checkliste { .check }

+ Erstelle ein neues 'Play' Sprite als Taste, welche dein Spieler klicken muss, um ein neues Spiel zu beginnen. Du kannst es entweder selbst zeichnen oder ein Sprite aus der Scratch Bibliothek bearbeiten.

	![screenshot](images/brain-play.png)

+ F�ge diesen Code zu deiner neuen Taste hinzu.

	```blocks
		wenn die Flagge geklickt wird
		zeigen

		wenn dieses Sprite geklickt wird
		verstecken
		[Start V] senden
	```

	Dieser Code zeigt die �Spiel� Taste, wenn dein Projekt gestartet wird. Wenn die Taste geklickt wird, wird sie versteckt und sendet dann eine Meldung, die das Spiel starten wird.

+ Du musst den Code deiner Spielfigur bearbeiten, damit das Spiel beginnt, wenn die Figur die `start` {.blockevents} Startmeldung erh�lt und nicht erst wenn die Flagge geklickt wird.

	Ersetze den Code `when flag clicked` {.blockevents} (wenn Flagge geklickt wird) mit `when I receive start` {.blockevents} (wenn ich den Start erhalte).

	![screenshot](images/brain-start.png)

+ Klicke die gr�ne Flagge und klicke auf deine neue Spieltaste, um es zu testen. Du solltest sehen k�nnen, dass das Spiel nicht startet, bis die Taste geklickt wird.

+ Hast du gemerkt, dass die Zeituhr erst startet, wenn die gr�ne Flagge geklickt wird und nicht, wenn das Spiel beginnt?

	![screenshot](images/brain-timer-bug.png)

	Kannst du dieses Problem beheben?

+ Klicke auf das Stadium und ersetze den `stop all` {.blockcontrol} (alles stoppen) Block mit einer `end` {.blockevents} (beenden) Meldung.

	![screenshot](images/brain-end.png)

+ Du kannst jetzt den Code zu deiner Taste hinzuf�gen, um sie bei Spielende erneut zu zeigen.

	```blocks
		Wenn ich [Ende v] empfange
		zeige dich
	```

+ Du musst auch deine Spielfigur beenden, damit sie keine weiteren Fragen bei Spielende stellt:

	```blocks
		Wenn ich [Ende v] empfange
		stoppe [andere Skripte der Figur v]
	```

+ Teste deine Spieltaste, indem du ein paar Spiele spielst. Du solltest jetzt merken k�nnen, dass die Spieltaste nach jedem Spiel angezeigt wird. Um das Testen leichter zu machen, kannst du jedes Spiel abk�rzen, damit es nur ein paar Sekunden dauert.

	```blocks
		setze [time v] auf [10]
	```

+ Du kannst auch �ndern, wie die Taste aussieht, wenn die Maus dar�ber gleitet.

	```blocks
		Wenn die gr�ne Flagge angeklickt
		zeige dich
		wiederhole fortlaufend
   		falls <wird [Mauszeiger v] ber�hrt?> dann
      		setze [Fischauge v]-Effekt auf (30)
   		sonst
      		setze [Fischauge v]-Effekt auf (0)
   		Ende
	Ende
	```

	![screenshot](images/brain-fisheye.png)

## Projekt speichern { .save }

## Aufgabe: Start-Bildschirm {.challenge}
Kannst du einen weiteren Hintergrund zu deinem Stadium hinzuf�gen, welcher der Start-Bildschirm deines Spiels sein wird? Du kannst die `when I receive start` {.blockevents} (wenn ich den Start-Block erhalte) und `when I receive end` {.blockevents} (wenn ich den Beenden-Block erhalte) benutzen, um zwischen dem Hintergund hin- und herzuschalten.

Mit Hilfe dieser Bl�cke kannst du deine Spielfigur entweder zeigen oder auch verstecken und sogar die Zeituhr entweder zeigen oder auch verstecken:

```blocks
zeige Variable [time v]
```
```blocks
verstecke Variable [time v]
```

![screenshot](images/brain-startscreen.png)

## Projekt speichern { .save }

# Schritt 3: Grafik hinzuf�gen { .activity .new-page}

Anstatt, dass deine Spielfigur nur `yes! :)` (Ja!) oder `nope :(` (Nein) zum Spieler sagt, k�nnen wir jetzt Grafik hinzuf�gen, damit der Spieler wei�, wie es um ihn bestellt ist.

+ Erstelle ein neues Sprite namens 'Result' (Ergebnis), das Kost�me mit entweder einem 'tick' (H�kchen) oder einem 'cross' (Kreuz) enth�lt.

	![screenshot](images/brain-result.png)

+ �ndere den Code deiner Spielfigur, damit du, statt nur dem Spieler mitzuteilen, welchen Punktestand er erreicht hat, ihm statt dessen auch die entsprechenden `correct` {.blockevents} (richtig) und `wrong` {.blockevents} (falsch) Meldungen senden kannst.

	![screenshot](images/brain-broadcast-answer.png)

+ Du kannst jetzt diese Meldungen dazu benutzen, um entweder das 'tick' (H�kchen) oder das 'cross' (Kreuz) Kost�m anzuzeigen. F�ge diesen Code zu deinem neuen 'Result' (Ergebnis) Sprite hinzu:

	![screenshot](images/brain-show-answer.png)

+ Teste dein Spiel erneut. Du solltest ein H�kchen sehen k�nnen, wannimmer du eine Frage richtig beantwortet hast und ein Kreuz, wannimer du eine Frage falsch beantwortet hast.

	![screenshot](images/brain-test-answer.png)

+ Hast du gemerkt, dass der Code f�r die `when I receive correct` {.blockevents} (wenn ich richtig geantwortet habe) und `when I receive wrong` {.blockevents} (wenn ich falsch geantwortet habe) Bl�cke nahezu identisch ist? Lass uns eine Funktion erstellen, damit es leichter f�r dich ist, �nderungen an deinem Code vorzunehmen.

	Klicke `More Blocks` {.blockmoreblocks} (weitere Bl�cke) auf deinem 'Result' (Ergebnis) Sprite und 'Make a Block' (Block herstellen), stelle dann einen weiteren Block her. Erstelle eine neue Funktion namens `animate` {.blockmoreblocks} (animieren).

	![screenshot](images/brain-animate-function.png)

+ Du kannst dann den Animationscode zu deiner neuen Animationsfunktion hinzuf�gen und dann die Funktion zweimal benutzen:

	![screenshot](images/brain-use-function.png)

+ Jetzt brauchst du dann nur eine Ver�nderung an deinem Code vorzunehmen, wenn du das H�kchen oder das Kreuz f�r l�ngere, bzw. k�rzere Zeit anzeigen m�chtest. Probier es mal!

+ Anstatt das H�kchen und das Kreuz entweder nur zu zeigen oder zu verstecken, kannst du auch die Animationsfunktion �ndern, damit die Grafik eingeblendet wird.

	```blocks
		Definiere [object Object]
		setze [Durchsichtigkeit v]-Effekt auf (100)
		zeige dich
		wiederhole (25) mal
  		�ndere [Durchsichtigkeit v]-Effekt um (-4)
		Ende
		verstecke dich
	```

## Projekt speichern { .save }

## Aufgabe: Verbesserte Animation {.challenge}
Kannst du die Animation deiner Grafik verbessern? Du k�nntest das H�kchen und das Kreuz so programmieren, dass sie ein- oder ausblenden. Oder du k�nntest andere coole Effekte benutzen:

![screenshot](images/brain-effects.png)

## Projekt speichern { .save }

## Aufgabe: Sound und Musik {.challenge}
Kannst du Sound-Effekte und Musik zu deinem Spiel hinzuf�gen? Zum Beispiel:

+ Du k�nntest einen Sound spielen, wenn der Spieler eine Frage entweder richtig oder falsch beantwortet;
+ Du k�nntest einen tickenden-Uhr-Sound zu deinem Countdown-Z�hler hinzuf�gen;
+ Du k�nntest einen Sound spielen, wenn die Zeit abgelaufen ist;

	```blocks
		spiele Schlaginstrument (10 v) f�r (0.1) Schl�ge
	```

+ Du kannst auch konstant Musik in einer Schleife spielen (wenn du nicht mehr genau wei�t, wie das geht, wird dir Schritt 4 des 'Rock Band' Projekts hierbei als Erinnerungshilfe dienen).

## Projekt speichern { .save }

## Aufgabe: Wettrennen zu 10 Punkten {.challenge}
Kannst du dein Spiel �ndern, damit (statt so viele Fragen wie m�glich innerhalb von 30 Sekunden richtig zu beantworten) der Spieler sehen kann, wie schnell er 10 Fragen richtig beantworten kann?

Um dies zu tun brauchst du nur den Code deiner Zeituhr zu �ndern. Kannst du sehen, was ge�ndert werden muss?

```blocks
	Wenn ich [start v] empfange
	setze [time v] auf (30)
	wiederhole bis <(time) = [0]>
   		warte (1) Sek.
   		�ndere [time v] um (-1)
	Ende
	sende [Ende v] an alle
```

## Projekt speichern { .save }

## Aufgabe: Anweisungsbildschirm {.challenge}
Kannst du einen Anweisungsbildschirm zu deinem Spiel hinzuf�gen und deinem Spieler mitteilen, wie das Spiel gespielt wird? Du brauchst eine 'Instructions' (Anweisungen) Taste und einen weiteren Stadium Hintergrund.

![screenshot](images/brain-instructions.png)

Du wirst eventuell auch eine 'Back' (Zur�ck) Taste ben�tigen, um wieder zum Hauptmen� zur�ckzugelangen.

```blocks
	sende [main menu v] an alle
```

## Projekt speichern { .save }
