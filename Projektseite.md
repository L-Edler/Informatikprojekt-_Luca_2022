# Informatik Projekt Nr.1 : Cat-Jump&Run


## Inhaltsverzeichnis

[Programm](#Programm)

[Spielprinzip](#Spielprinzip)

[Code](#Code)
   
   [Weltklassen](#Weltklassen)
     
     [Laser](#Laser)
     
     [Sender](#Sender)
   
   [Actorklassen](#Actorklassen)
     
     [Hindernisse](#Hindernisse)

[Endprodukt](#Endprodukt) 

[Stundenprotokoll](https://github.com/L-Edler/Blog-2022/blob/main/Stundentagebuch.md)
 

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

In meinem Spiel geht es in der Klasse "World" um die Spielwelt. Hier ist die subclass "CatWorld" am wichtigsten, da diese subclass die Spielwelt ist.





