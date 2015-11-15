---
title: Selektieren und Manipulieren mit jQuery
order: 30
---
jQuery verwendet die Schreibweise der CSS-Selektoren um Nodes des DOM auszuwählen:

<javascript>
$("a")        /* alle a-Tags ... als jQuery Objekte */
$("h1")       /* alle Überschriften h1 ... als jQuery Objekte */
$("p.extra")  /* alle p-tags mit klasse extra ... als jQuery Objekte  */
</javascript>
    
jQuery definiert noch ein paar zusätzliche Selektoren, die es in CSS so nicht gibt:

<javascript>
$("tr:even")                 /* Alle geraden Zeilen der Tabelle */
$("p:contains('Warnung')")   /* Absätze die die Zeichenkette Warnung enthalten */
$(":checkbox")               /* Alle input-Tags vom typ checkbox */
</javascript>

und weitere Methoden, um noch besser zu selektieren:

<javascript>
$('h1').next()               /* nächster Tag nach der h1 */
$('h2').nextUntil('h2')      /* Alle Tags zwischen einem h2 und dem nächsten */
</javascript>

Das Ergebnis ist jeweils ein jQuery Objekt.

Manipulation
----------

Die Selektion allein verändert die Webseite noch nicht. Dafür bietet jQuery 
eine Reihe von Manipulations-Funktionen an. 

<javascript>
$("a").addClass("wichtig"); /* alle A-Tags erhalten die Klasse wichtig */
$("h1").append(":");        /* in Überschriften h1 wird ein Doppelpunkt angefügt */
$("h1").prepend("Titel:");  /*  --||-- wird vorne ‚titel:’ eingefügt */
$("p.extra").hide();        /* alle p-tags mit klasse extra werden versteckt */
</javascript>

Hinweis: hier versteckt sich eine Schleife: der Selektor liefert ein Liste von
Tags, die Manipulations-Funktion wird für jedes Element der Liste aufgerufen.

