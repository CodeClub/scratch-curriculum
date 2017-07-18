---
title: Lost in Space — Volunteer Notes
---

#Einf�hrung:
In diesem Projekt lernen die Kinder, wie man Codebl�cke miteinander kombiniert, um eine einfache Animation zu erzeugen.

#Ressourcen
F�r dieses Projekt sollte Scratch 2 benutzt werden. Scratch 2 kann entweder online benutzt werden unter [jumpto.cc/scratch-on](http://jumpto.cc/scratch-on) oder es kann von [jumpto.cc/scratch-off](http://jumpto.cc/scratch-off) heruntergeladen und offline benutzt werden.

Sie finden eine fertig gestellte Version dieses Projekts unter <a href="http://scratch.mit.edu/projects/26818098/#editor">online</a> oder es kann heruntergeladen werden, indem Sie auf den 'Project Materials' (Projektmaterialien) Link f�r dieses Projekt klicken, der u.a. Folgendes enth�lt:

+ LostInSpace.sb2

#Lernziele
+ Schleifen:
	+ `Repeat` {.blockcontrol} (Wiederholung) Schleifen;
	+ `Forever` {.blockcontrol} (F�r immer) Schleifen.

Dieses Projekt deckt Elemente aus den folgenden Bereichen des [Raspberry Pi Lehrplans zur digitalen Produktion](http://rpf.io/curriculum):

+ [Einfach Programmierkonstrukte benutzen, um einfache Programme zu erstellen.](https://www.raspberrypi.org/curriculum/programming/creator)

#Aufgaben
+ �Verbessere deine Animation�: �ndern von Zahlen in einem kurzen Programm;
+ �Erstelle deine eigene Animation�: Wende das Gelernte an, um eine neue Animation herzustellen.

#H�ufig gestellte Fragen (FAQ)
+ Die Kinder m�ssen evtl. daran erinnert werden, die Position, die Gr��e sowie andere Effekte eines Sprites beim Start der Animation wieder 'reset' (auf Null zu stellen). Dies kann einfach erzielt werden, indem manche der folgenden Bl�cke zum Start der Animationen hinzugef�gt werden:

```Bl�cke
	gehe zu x:(0) y:(0)
```

```Bl�cke
	Gr��e auf (100) % einstellen
```

```Bl�cke
	Grafik-Effekte l�schen
```

+ Das 'spaceship' (Raumschiff) Sprite wird sich seitw�rts bewegen, es sei denn, es wird um 90 Grad im Uhrzeigersinn gedreht. Das Drehen des Raumschiffs ist Teil der Projektanweisungen. Falls dies Probleme bereiten sollte, kann jedoch ein anderes Sprite als Ersatz f�r das Raumschiff benutzt werden.

	![screenshot](images/space-rotate.png)