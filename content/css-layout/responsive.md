---
title: Responsive Design 
order: 15
---

Responsive Design 
--------------------

Große Unterschiede im Platz kann man mit Mediaqueries in CSS behandeln. Die Verwendung von Mediaqueries wurde 2010 in einem Artikel von Ethan Marcotte in "A List Apart" unter dem Begriff "Responsive Webdesign" popularisiert [&rarr;](http://www.alistapart.com/articles/responsive-web-design/). 

![Das erste Beispiel für "Responsive Webdesign": Darstellung der Seite auf verschiedenen Breiten](/images/responsive.png)

### Mobile First

Luke Wroblewski schlug schon 2009 unter dem Slogan "Mobile First" vor, zuerst die mobile Version der Website zu gestalten, und davon dann die "größeren" Versionen abzuleiten [&rarr;](http://www.lukew.com/ff/entry.asp?933).


### Mediaqueries

Die technische Umsetzung des verschiedenen Layouts ist relativ einfach: Mediaqueries erlauben eine "Verzweigung" in CSS.

<css caption="CSS mit Mediaqueries: Nur wenn Darstellung am Screen, und Breite kleiner gleich 480 Pixel">
@media screen and (max-width: 480px) {
  .column {
    float: none;
  }
  /* weitere Regeln für kleine Screens */
}
/* allgemein gültige Regeln */
</css>

Bilder und Responsive Design
----------

Bilder waren lange Zeit ein Grund, warum das Layout von Webseiten nicht flexibel war: weil die Bilder nur für die Darstellung bei einer bestimmten Größe geeigenet waren. Das ist aber seit ca. 2010 anders.

### Pixel
Als Bildformate für `<img>` Tags in Webseiten wurden lange nur Pixel-Formate unterstützt. Diese Formate (jpg, png, gif) sind eigentlich für die Darstellung bei einer bestimmten Größe gedacht. Die Vergrößerte Darstellung von Pixel-Bildern liefert keine guten Ergebnisse:


![Abbildung 29: Ausschnitte aus einem Pixel Bild, vom Browser (Firefox) in 3 Stufen vergrößert dargestellt](/images/image117.png)

Aktuelle Browser sind aber sehr gut bei der verkleinerten Darstellung von Pixel-Bildern, man kann also
dasselbe Pixel-Bild für verschiedene Darstellungen verwenden.


![Abbildung 30: Pixel Bild wird vom Browser (Firefox) in 3 Stufen verkleinert dargestellt](/images/image119.png)


# Responsive Images

Mobile Geräte mit sehr hoher Pixeldichte stellen das Web Design vor ein
Dilemma: soll ich - wegen der Pixeldichte - riesige Bilder ausliefern?  
Oder - weil es ein mobiles Gerät ist, und die Datenübertragung über
das Handy-Netz so langsam und teuer ist - doch kleine Bilder ausliefern?

Um dieses Dilemma zu umgehen wurde das neue Attribute "srcset" für den **img**-Tag entwickelt.
Ausser vom Internet Explorer wird das Attribut 2016 von 
allen Browsern unterstützt [caniuse srcset](http://caniuse.com/#feat=srcset).

Mit diesem Attribut kann man mehrere Varianten eines Bildes hinterlegen,
der Browser entscheidet welche Version er lädt und darstellt.


<htmlcode>
  <img src="salzburg.jpg" style="width: 1353px; height: 461px;"
       srcset="salzburg.jpg, salzburg@2x.jpg 2x, salzburg@4x.jpg 4x">
</htmlcode>

Das Bild wird immer mit der gleichen Größe an virtuellen Pixel dargestellt.
Es stehen aber noch Versionen mit doppelter und vierfacher Höhe und Breite
zur Verfügung, die der Browser laden und darstellen kann.

Der folgende Screenshot wurde auf einem Macbook mit Retinadisplay erstellt,
in der oberen Variante wird das "normale" Bild dargestellt, darunter das in
der **2x** Version.

![Ausschnitt aus der Demo-Seite](/images/vergleich.jpg)

Die Demo-Seite zeigt drei Abstufungen:

[Demo-Seite für "Responsive Images"](/images/responsive-images.html)

Das kann man auch mit Hintergrundbilder machen:

[Demo-Seite für "Responsive Background Images"](/images/responsive-background-images.html)


### Vektor

Mit dem Format SVG steht auch ein vektor-basiertes Bildformat für das Web zur Verfügung. SVG-Bilder können in beliebiger Größe verwendet werden. Die Einbindung erfolgt mit dem img-Tag: 

    <img src="circle.svg">

![Abbildung: Kreis in SVG-Darstelllung](/images/circle.svg)

Schriftgröße
---------------
Die Schriftgröße im Browser unterliegt nur bedingte der Kontrolle durch HTML und CSS Code. Das „letzte Wort“ hat hier die LeserIn, die die Schrift größer oder kleiner stellen kann. z.B. in MSIE unter Ansicht → Schriftgrad, in Firefox mit der Tastenkombination STRG + oder STRG – 

Je nach Schriftgröße und zur Verfügung stehendem Platz im Browser-Fenster wird der Browser die Absätze geeignet in Zeilen umbrechen, wie in Abbildung 31 gezeigt. 


![Abbildung 31: Darstellung von Text bei verschiedenen Fensterbreiten und Schriftgrößen](/images/zeilenumbruch.png)

Skalieren
----------

Beim Vergrößern und Verkleinern der Schriftgröße verwenden die Browser zwei
verschiedene Methoden: entweder die Bilder werden mit der Schrift vergrößert und
verkleinert (heute default), oder nur der Text wird verändern, die Bilder aber bleiben gleich. 
Hier das entsprechende Menü in Firefox. 

![Abbildung 32: Zoom Menü in Firefox](/images/zoom.png)

Vertiefung
----------

* [Responsive Tables](http://blog.cloudfour.com/picking-responsive-tables-solution/)
