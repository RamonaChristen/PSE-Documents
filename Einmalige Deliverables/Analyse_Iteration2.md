# Analyse der 2. Iteration
## War der Inhalt der Stories nach dem Planning Game klar?
Die Stories waren sehr ausführlich dokumentiert. Vor allem bei den verschiedenen [LOG](https://github.com/puzzle-bbt/kon-cryptopus-access-log-history/blob/main/README.md#log-page-minimal-example) Tasks gab es genaue TODO's die genau so abgearbeitet werden konnten.
## War der Umfang der Stories zu gross/zu klein?
Das Ticket _[#564](https://github.com/puzzle/cryptopus/issues/564) LOG: Encryptable read access_ war zu gross. Bereits nach dem Planning war klar, dass es sich dabei um einen eher grossen Task handelt, da dieser mit 13 SP (26 Arbeitstunden) geschätzt wurden. Es stellte sich zudem heraus, dass sogar noch mehr Aufwand benötigt wird um den Task fertig zu stellen.
Die restlichen Stories wurden auf 3 bis 8 SP (6-16 Stunden) geschätzt und konnten auch in diesem Zeitrahmen erfüllt werden. Somit war die Grösse dieser Tasks angemessen.
## War die Aufwandschätzung der Stories realistisch?
Das Ticket _[#538](https://github.com/puzzle/cryptopus/issues/538) Arrow in Folder Navigation wrong direction_ wurde auf 3 SP (6 Arbeitstunden) geschätzt. Die Umsetzung dauerte allerdings nur knapp eine Arbeitsstunde, da es sich um eine sehr triviale Änderung handelte.
Dafür wurde das Ticket _[#564](https://github.com/puzzle/cryptopus/issues/564) LOG: Encryptable read access_ mit 13 SP (26 Arbeitsstunden)  immernoch zu klein geschätzt. Die Umsetzung konnte auch mit einem Arbeitsaufwand von circa 40 Stunden noch nicht fertiggestellt werden und muss in die nächste Iteration mitgenommen werden.
Für die restlichen Tickets war die Aufwandschätzung ziemlich genau.
## Wurde der Aufwand, sich in neue Programmiersprachen/Technologien einzuarbeiten, realistisch eingeschätzt?
In dieser Iteration wurde keine Zeit eingeplant um sich in neue Technologien einzuarbeiten. Nachträglich stellte sich heraus, dass wir doch noch nicht alle verwendeten Technologien komplett verstehen und es brauchte noch etwas Zeit um sich in die genauen Abläufe von EmberJS einzuarbeiten.
## Wurde das Entwicklungstempo realistisch eingeschätzt? Gab es Engpässe?
Das Entwicklungstempo wurde etwas zu optimistisch eingeschätzt. Vor allem die Arbeit am _[#564](https://github.com/puzzle/cryptopus/issues/564) LOG: Encryptable read access_ ging nicht so schnell voran wie geplant, was weitere Tickets beeinflusste, die auf dieses aufbauen.
## Kann die gruppeninterne Kommunikation verbessert werden?
Die Kommunikation im Team verläuft weiterhin reibungslos und es besteht kein Bedarf zur Verbesserung.
## War die Arbeitsbelastung aller Teammitglieder ähnlich? Sind alle zufrieden?
Die verschieden Tickets wurden fair aufgeteilt. Da Ticket _[#564](https://github.com/puzzle/cryptopus/issues/564) LOG: Encryptable read access_ allerdings mehr Zeit beanspruchte als ursprünglich geplant erhöhte sich der Aufwand der beiden Teammitglieder, die diesem Ticket zugewiesen waren (DM,RC). Die anderen Teammitglieder konnten nur begrenzt aushelfen, da sie nach dem Erledigen ihrer eigenen Tickets nicht so stark mit den Aufgaben und bisherigen Implementationen dieses Tasks vertraut waren wie 
DM und RC. Im allgemeinen sind aber alle Temmitglieder mit der Arbeitsaverteilung zufrieden.
## Gab es ”Leerläufe“ oder Wartezeiten aufgrund der Abhängigkeiten zwischen den Tasks?
Es gab 4 verschieden Tickets zur Implementation eines LOGs, die alle mehr oder weniger vom _[#564](https://github.com/puzzle/cryptopus/issues/564) LOG: Encryptable read access_ Ticket abhingen. Dadurch kam es zu Wartezeiten in der Implementation von Ticket _[#568](https://github.com/puzzle/cryptopus/issues/568) LOG: Personal activity log_ 
und Ticket _[#572](https://github.com/puzzle/cryptopus/issues/572) LOG: Recent credentials on dashboard_ , da diese auf einem Model aufbauen, dass im ersten Ticket implementiert werden soll. Dadurch konnen diese Tickets nur teilweise implementiert werden und müssen auch in den nächsten Sprint mitgenommen werden. Das Ticket _[#565](https://github.com/puzzle/cryptopus/issues/565) LOG: Encryptable log write access/previous values_ 
baut vollständig auf Ticket /#564 auf und konnte garnicht implementiert werden. Nach Rücksprache mit dem Kunden wurde dieses aus dem Sprint entfernt und die Implementation auf unbestimmte Zeit aufgeschoben.
## Wieviel Zeit hat jedes Teammitglied investiert für

Teammitglied| Implementation von Stories | Implementation von Testfällen | Einarbeiten in neue Technologien  | Systemadministration (Setup Cryptopus) |
|-----------|----------------------------|-------------------------------|-----------------------------------|----------------------|
|Ramona     | 18 Stunden                  | 2 Stunden                    |  1 Stunde                         | 1 Stunde           |
|Raphael    |                             |                              |                                   |           |
|Julien     |                             |                              |                                   |           |
|Renato     |                             |                              |                                   |           |
|Dario      |                             |                              |                                   |           |

  * Wo ist für die nächste Iteration diesbezüglich der grösste Aufwand zu erwarten? 
    * Der grösste aufwand ist in der Implementation von Stories und Testfällen zu erwarten. Zeit zum Einarbeiten in neue Technologien und Systemadministration sollten nicht vergessen werden aber es ist nicht mehr Aufwand zu erwarten als in dieser Iteration beansprucht wurde.
