

## [Programm](#Programm)

## [Spielprinzip](#Spielprinzip)

## [Code](#Code)

### [Weltklassen](#Weltklassen)
     
### [Actorklassen](#Actorklasssen)

## [Endprodukt](#Endprodukt)

## [Stundenprotokoll](https://github.com/L-Edler/Blog-2022/blob/main/Stundentagebuch.md)
 

## Das Programm <a name="Programm"></a>

![image](https://user-images.githubusercontent.com/111414185/208302437-4ef429f7-3aab-4fd0-9d5a-947c677f55bd.png)

Ich habe mich für die Arbeit mit Greenfoot entschieden. In Greenfoot können auch unerfahrene Programnmierer sich einmal an der Erstellung eines Spiels versuchen. Es handelt sich dabei um 2D Spiele. Die Arbeitsoberfläche bei Greenfoot ist einfach aufgebaut, sodass sich auch Anfänger gut zurecht finden. Bei Greenfoot arbeitet man mit sog. Szenarien. Diese Szenarien füllt man mit Klassen, die ganz verschiedene Rollen übernehmen können. Von diesen kann man beliebig viele erstellen um z.B eine Spielwelt zu erstellen oder einen Charakter zu schaffen, der bestimmte Befehle ausführen soll.
Die Befehle, die ein Obkelt einer bestimmten Klasse ausführen soll, werden im Editor eingefügt. Die Programmiersprache ist Java. Als Anfänger muss man sich also ersteinmal mit verschiednen Befehlen vertraut machen und lernen, wie man sie richtig anwendet.

## Das Spielprinzip <a name="Spielprinzip"></a>

Das Prinzip meines Spiels ist recht sympel. Von einem Jump&Run hat fast jeder schoneinmal gehört. Falls nicht, auch nichts schlimm, der Name erklärt das Prinzip perfekt. Es gibt einen Spieler, der sich in einer zweidimensionalen Welt fortbewegen muss. Er kann springen und laufen. Außerdem muss der Spieler Hindernisse überwinden und auch Gegnern ausweichen um zu einer Art Ziel zukommen. Alles in allem ein Simples Prinzip. In meinem Spiel, ist der Spieler eine Katze. Die Katze kann mittels der Tasten "a" und "d" hin und her bewegt werden. Es besteht ebenfalls die Möglichkeit zu springen, was mittels drücken der "Leertaste/Space" geschieht. Der Spieler muss die Katze durch einer Welt steuern und Gegnern wie einem Hund, der am boden patrolliert oder auch umherfliegedem Ufos ausweichen, deren Flugbahn unberechenbar ist. Auch am Boden muss er sich vor Bomben in achtnehmen, die auf keinen Fall berührt werden sollten. Ziel ist es, einerseits so viele Mäuse wie möglich zu fressen, andererseist gilt es eine Pizza zu fressen, um das Spiel zu gewinnenn.

## Der Code <a name="Code"></a>

Nun möchte ich mit der Erklärung meines Codes, dem Herzstück des Spiels, beginnen. Wie Eingangs bereits erwähnt kann man bei Greenfoot versch. Szenarien erstellen und diese dann mit Klassen füllen. 

![Screenshot (19)](https://user-images.githubusercontent.com/111414185/208303576-6b1481fb-2f3d-4d99-80af-3e59a2062ab0.png)

Mein Szenario heißt:Cat_Jump&Run

In diese Szenarios lassen sich jetzt ganz verschieden Klassen einfügen. 

![Screenshot (21)](https://user-images.githubusercontent.com/111414185/208303715-c5c5850e-b055-4f68-8590-ba95f91b1056.png)

Wie im Bild zusehen ist, habe ich zwei "Oberklassen" erstellt, nämlich die "World" und "Actor" Klassen. In diesen "Oberklassen" gibt es dann mehere "Unterklassen", die sog. "subclasses". Diese erstellt man mit einem Rechtsklick auf die "Oberklassen".

In meinem Spiel geht es in der Klasse "World" unteranderem um die Spielwelt. Hier ist die subclass "CatWorld" am wichtigsten, da diese subclass die Spielwelt ist.

Um einer subclass dann Leben einzuhauchen muss im Editor der Code geschrieben werden. Dieser kann in verschiedene Methoden unterteilt werden, die der subclass Befehle geben. Jede Klasse hat außerdem ihren eigenen Editor. 

![Screenshot (23)](https://user-images.githubusercontent.com/111414185/208304659-5df9ba55-85c0-4ef6-a544-23b56f2c085f.png)

Im Editor gibt es dann verschiedne Methoden, die in den gelben Kästen gezeigt sind (siehe Bild unten). Die einzelnen Methoden sind entweder mit private oder public betitelt. "public" Methoden können von allen Mitgliedern einer Klasse und abgeleiteten unterklassen eingesehen werden. Bei "private" Methoden, bleibt abgeleiteten Klassen der Zugriff auf die Methoden verwehrt. 

![Screenshot (25)](https://user-images.githubusercontent.com/111414185/208304667-c7346830-2a38-46f8-bd5a-e741a5b28d71.png)

### Die Weltklassen <a name="Weltklassen"></a>

#### Die CatWorld <a name=Catworld></a>

In der "public CatWorld" Methode werden u.a. die Parameter der Welt fest gelegt.

![Screenshot (26)](https://user-images.githubusercontent.com/111414185/208305363-154fbf59-8db1-4597-84ac-a1a62fb5d8e1.png)

background = new GreenfootImage("background_endless_01.png"), mit diesem Befehl wird das Hintergrundbild festgelegt.

super(x, y, z) legt z.B die größe der Welt fest, die der Spieler sehen kann. 

Das Spiel soll in meinem Fall aber größer sein als 1000px in X-Richtung.
Die Hindernisse kann man auch außerhalb des Sichbaren bereiches setzen. Das stell also kein Problem dar. Jedoch würde der Spieler sich nur innerhalb der 1000px des Sichtfeldes bewegen können und am Rand nicht weiter laufen können. Hintergrund und Sichtfeld müssen sich also mit dem Spieler mitbewegen, sodass dieser immer im Zentrum des Spielfelds bleibt, also nicht mit dem Rand kollidiert. 

Um also dafür zusorgen, dass der Hintergrund sich simultan mit dem Spieler bewegt/verändert muss ich die X-Koordinate des Hintergrundes verändern. 
Dafür wird im Editor der CatWorld eine Methode erstellt, das verhalten bei einer veränderung der X-Koordinate beschreibt. (siehe Bild unten)

![Screenshot (27)](https://user-images.githubusercontent.com/111414185/208306451-b26d4137-d6f3-4a87-ad7a-c7d37b3c557e.png)


Nun braucht es aber auch noch den Spieler, der diese Methode aufruft und somit den Hintergrund bewegt.
Im Code der "Player" class wird in der Methode "public void checkKeys()" dies getan. 
In dieser Methode wird einerseits festgelegt wie sich der Spieler bewegt durch das drücken der Tasten "a" oder "d" wird die X-Koordinate des Spielers jeweils um 5 Pixel nach links oder rechts verschoben. Außerdem wird ein Bild für die jeweilige Bewegung eingefügt, damit es so aussieht, als würde der Spieler in beide Richtugen vorwärts laufen. 

![Screenshot (30)](https://user-images.githubusercontent.com/111414185/208306887-27011b75-6b37-4a32-bc14-8c8aea2844a3.png)

Außerdem wird über das drücken der Tasten festgelegt, wie die X-Koordinate des Hintergrundbildes verändert wird, sodass dieser sich mit dem Spieler bewegt und der Spieler augenscheinlich weiter läuft. Die Änderung geschieht hier, weil wieder die public void changeBackgroundX(int changeX) Methode aufgerufen wird. 
Wichtig ist hier die Belegung der Tasten umgekehrt zum Spieler zumachen, denn der Hintergund muss sich nach links bewegen, wenn der Spieler nach rehcts läuft und umgekehrt. 



Funktionieren wird die Bewegung nach links und rechts jedoch noch nicht. Mit den oben gezeigten Methoden werden lediglich Variablen verändert. Der Hintergrund an sich tut also noch nichts. Es muss also dafür gesorgt werden, das sich der Hintergund auf Basis der durch den Druck der Taste "a" oder  "d" veränderten Variablen, neu erstellt, bzw. er neu geladen wird.

![Screenshot (34)](https://user-images.githubusercontent.com/111414185/208307482-5129af49-a491-496c-b07c-43e0fb3e2b88.png)

Auf dem Bild sieht man die entsprechende Methode. Diese besagt eben genau das, dass das Hintergrundbild mit den veränderten Parametern, neu geladen/gezeichnet(draw) werden soll.
Da die CatWorld Klasse nun selber etwas tun muss einer "Act Methode" eingefügt werden. Diese sorgt einfach nur dafür, dass die Methode zum Neuladen der Welt ständig ausgeführt wird. 

![Screenshot (36)](https://user-images.githubusercontent.com/111414185/208307780-02c6c517-6544-4fba-a213-2c76a76f9334.png)

Mit diesem Code gibt es jetzt jedoch noch ein Problem. Nämlich wird nur der Hintergrund des Spielers bewegt, sodass es so aussieht, als würde er sich bewegen. In Wahrheit steht er auf der Stelle. Platziert man nun einen anderen Actor im Spiel wird sich dieser auch mitbewegen, und nicht am Spieler vorbei ziehen, wie es die Welt tut. Es gilt also dafür zu sorgen, dass Objekte sich nicht mehr mit dem Spieler bewegen, also ähnlich wie das Hintergrundbild wegscrollen.
Dafür werden alle Actors in einer Liste gespeichert

Für diese Liste wird wieder eine Methode erstellt.

public List<Actor> giveMeAllActors() 

Im Gegensatz zu anderen Methoden, haben wir hier kein void mehr. Das bedeutet, die Methode hat einen Rückgabewert, nämlich eine Liste mit allen Actors
Wer also diese Methode aufruft, erhält eine Liste mit allen Actors.
   
In dieser Methode wird dann mittels des Greenfoot Befehls "getObjects(Actor.class)" festgelegt, was die Liste enthalten soll.
Um dann dafür zu sorgen, dass die Informationen der Liste auch an den zurückgehen, der die Methode aufruft, wird der "return" befehl genutzt.
   
Nun wird einer Zählerschleife generiert, die die bereits generierte Liste immerwieder durch geht. 
Diese Schleife zählt von 0 (dem ersten Objekt der Liste), solange der Zähler kleiner ist als die größe der Liste. 
   
Bsp. Würde die Liste 10 Actors enthalten, würde die Zählerschleife von 0 bis 9 zählen. 
   
Gezählt wird in einser Schritten (zaehler++)
   
Nun kann man mit dem SetLocation Befehl die Position aller Actors verschieben.
   
![Screenshot (40)](https://user-images.githubusercontent.com/111414185/208309133-59d07353-c171-4049-b1c0-ae54929628ed.png)
     
Neben diesen recht Komplexen Methoden, die dafür sorgen, dass sich unser Spieler mit dem Hintergrund in der Welt bewegt, gibt es für die CatWorld noch andere ebenso wichtige Methoden, die aber deutlich einfacher sind. So z.B die "prepare Methode" sie fügt lediglich alle Objekte vor Start des Spiels in die Welt ein. 

![Screenshot (42)](https://user-images.githubusercontent.com/111414185/208310147-fccce7e6-317a-4d78-854c-39de471ae135.png)

Im Bild zusehen: Ein Teil der Methode u.a die spawn Koordinaten für Player und Maus etc.
     

#### Die EndGame/Finish Klasse <a name="Die EndGame/Finish Klasse"></a>
   
Die beiden Weltklassen EndGame und Finish sind als eine Art Mitteilung für den Spieler gedacht. 
Beide erzeugen eine Meldung, entweder hat der Spieler gewonnen -> Finish oder er hat verloren -> EndGame.
Der Code ist, bis auf den Text der Meldung und die Farbe, der selbe, weswegen ich nur ein Beispiel erläutern werde. 
     
![Screenshot (44)](https://user-images.githubusercontent.com/111414185/208310356-60f07344-0a0d-4ff8-9c8d-f416b1456bee.png)

Im obrigen Bild ist der gesamte Code zusehen. Es handelt sich nur um eine einzige Methode.
Der Sinn hinter der Klasse besteht darin, ein schwarzes Bild im Sichtfeld des Spielers zu erzeugen, was die Nachricht "GameOver" beinhaltet. Es wird also zuerst eine neue Welt erstellt. Diese ist in den Maßen sogroß wie die Sichtbare Spielwelt. 
In diese Welt wird dann ein Bild eingefügt, was an Höhe und Breite die gesamte Welt ausfüllt. "GreenfootImage bg = new GreenfootImage(getWidth(), getHeight());"
Weiter wird festgelegt, dass der Hintergrund Schwarz sein soll, und das ganze Bild schwarz ausgefüllt wird. "bg.setColor(Color.BLACK); bg.fillRect(0, 0, getWidth(), getHeight()); setBackground(bg);"
     
Das Bild wird als Hintergrund festgelegt.
UM Schrift einzufügen muss unteranderem die Schriftart angepasst werden: "Font f = new Font ("SansSerif", 60);". Font bedeutet Schriftart.
Es wird also Eine Schriftart (Font) ausgewähltl, diese ist hier SansSerif, hierbei handelt es sich um eine normale Schriftart, genauso wie man z.B Arial oder Times New Roman kennt.
     
Die Frabe wird mittels "setcolor" Rot. 
Und mit dem Befehl "draw String Message" kann dann die vorher festgelegte Stringmessage eingefügt werden. 

Das Endergebniss sieht wie folgt aus:
     
![Screenshot (46)](https://user-images.githubusercontent.com/111414185/208310965-851dc515-6756-495d-81c2-8264eb0fdc20.png)

Oder für den Victory Screen so: 
     
![Screenshot (48)](https://user-images.githubusercontent.com/111414185/208311095-0729a225-24f7-4cf4-8d4f-72555e15c905.png)
     
### Die Actorklassen <a name="Actorklassen"></a>
     
Ein Spiel besteht natürlich nicht nur aus der Welt. Erst die Objekte in der Welt hauchen dem Spiel Leben ein. Bei mir heißen alle diese Objekte "Actor". 
Der wichtigste Actor ist wohl die Spiel Figur, der "Player". Über die BEwegung des Players in der Spielwelt wurde bereits vieles gesagt. Jedoch kann sich die Spielfigur in einem klassischen JUmp&Run Spiel nicht nur nach links und rechts bewegen, sie kann natürlich auch springen. Das Springen wird also wie folgt umgesetzt.
     
Ein Sprung besteht bekannter weise aus zwei Phasen. Dem Sprung in die Höhe, also eine Steigphase und dem wieder herunterfallen, also eine Fallphase.

Das fallen an sich zu erstellen ist nicht besonders schwierig. Man muss sich ledglich über den Aufbau der Welt in Greenfoot anhand eines Koordinatensystems bewusst sein. 
Das folgende Bild soll dies einmal verdeutlichen.
     
![Screenshot (52)](https://user-images.githubusercontent.com/111414185/208311486-8c6478ab-d08e-4c12-ac09-06c439c20684.png)
     
Weiß man also wie das Koordinatensystem verläuft kann man eine einfache Methode schreiben, die die Y koordinate des Spielers um einen gewünschten Wert erhöht. Geschieht das dauert haft, fällt der Spieler

     
   

     


        
     












