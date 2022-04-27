# Protokoll 13.04.2022 - Meeting mit Puzzle

## Anwesend 
Assistent: Dominik Fischli

PSE Team: Dario Marti, Renato Oester, Julien Gaumez, Ramona Christen _(Protokoll)_
## Entschuldigt
Raphael Fehr
# Traktanden

[Feedback](#feedback-assistent) 

[Status](#status)

[Varia](#varia)

[Beschluss](#beschluss)

# Feedback Assistent

## Protokoll Kundenmeeting
* Schreibfehler z.B. in Anwesenheitsliste und Retro.
* Layout nicht wie im 1. Protokoll
* Name und Titel anpassen (Datum)
* Start, Stop, Continue ist nicht überall verständlich (z.B. was ist Techtalk?)
* Planning nächste Iteration hat keine Angabe der Einheit der Schätzungen.
* Taskbeschreibungen sind nicht verständlich. Sollten besser beschrieben werden oder Issue verlinken.


-> Verbesserung durch Raphael 
## Allgemein
Frage zu Risikoanalyse letzte Woche
* Wurde die Gewichtung der Abhängigkeiten zu tief gewichtet? 
  * Team meint ja. Sollte in Zukunft bedenkt werden.


Aktuelle Risikoanalyse: 
* Wie bemerkt man, dass ein Missverständnis vorliegt?
  * Kann erst retrospektiv bewertet werden. Deshalb sollten vortlaufend Fragen gestellt werden um diese frühzeitig zu erkennen.
* Risikoanalyse zu Missverständnissen ist nicht klar formuliert.


Anlyse 2. Iteration muss noch mit Stunden aller Teammitglieder ergänzt werden.

# Status
//Status der Person und untendran die Erklärung 

![Status](https://img.shields.io/badge/Ramona_Christen-green-green)
Arbeitet weiter an Issue _[#564](https://github.com/puzzle/cryptopus/issues/564) LOG: Encryptable read access_. Meeting mit Puzzle hat einige neue Ideen gegeben. Das Issue sollte nun bald fertiggestellt werden können.

![Status](https://img.shields.io/badge/Dario_Marti-green-green)
Weiterarbeit ebenfalls an Issue _[#564](https://github.com/puzzle/cryptopus/issues/564) LOG: Encryptable read access_. Es gibt noch ein paar Probleme mit Ember, vor allem darin zu verstehen wie Ember in unserem Projekt verwendet wird.

![Status](https://img.shields.io/badge/Renat_Oester-green-green)
Arbeitet an Issue _[#572](https://github.com/puzzle/cryptopus/issues/572) LOG: Recent credentials on dashboard_ , fand eine Lösung dies unabhänig von Issue /#564 zu lösen indem vorübergehend Testdaten simuliert werden.

![Status](https://img.shields.io/badge/Julien_Gaumez-green-green)

Arbeitet weiter an Issue _[#568](https://github.com/puzzle/cryptopus/issues/568) LOG: Personal activity Log_, kann nun auch unabhängig von read access log gelöst werden indem ein separater Rails Controller erstellt wird anstatt auf die Fertigstellung von /#564 zu warten.
# Varia 
Diskussion wie die Abhängigkeit zwischen Tasks reduziert werden kann. Es wurde beschlossen, dass für den Personal Log einen separaten Controller erstellt wird, damit unabhängig vom Read Access Log gearbeitet werden kann


# Beschluss 
* Verbesserung des Kundenprotokolls durch Raphael
* In Zukunft Abhängigkeiten zwischen Tasks nicht unterschätzen
  * Abhängigkeiten so weit wie möglich reduzieren z.B. durch erstellen von separaten Controllern für verschieden Tasks oder simulieren von Testdaten. 
* Nächstes Team Meeting: Freitag 29.04.2022 um 14:00

