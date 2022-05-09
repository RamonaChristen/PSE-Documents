# Testkonzept von Cryptopus

Das Cryptopus hat ein umfangreiches Testkonzept welches Unit-Tests, System-Tests, End-to-End Tests, Frontend-Tests, Actions und einen mehrstufigen Review-Prozess beinhaltet.
Wird ein neues Feature implementiert (z.B. logs), dann muss dieses vollständig mit den oben genannten Tests abgedeckt werden. Das Feature wird auf einem separaten branch implementiert
und wird bei einem Pull-Request zuerst von einem Mitarbeiter und dann vom verantwortlichen für das Projekt reviewt. Falls noch änderungen vorgenommen werden müssen, werden diese gemacht, gepusht und dann wieder reviewt.
Dieser Prozess wird so lange wiederholt, bis der Branch den Anforderungen der Reviewer entspricht. Ist das der Fall, so wird der Branch in den Master Branch gemerged.

## Unit-Tests
Diese werden im Cryptopus im Rails-Backend implementiert. Mit den Unit-Tests wird sichergestellt, dass die einzelnen Komponenten/Funktionen unabhängig voneinander Funktionieren. Unit-Tests
sind im Cryptopus Whitebox-Tests, d.h. es wird nicht nur geschaut, ob sie den gewünschten output liefern, sondern auch wie dieser Zustande kommt. Wird z.B. eine Methode in der Methode aufgerufen,
welche getestet wird, wird auch getestet, ob diese Methode tatsächlich aufgerufen wurde. Im Cryptopus existieren separate Test Ordner für Controller-Tests, Migration-Tests, Authorisierungs-Tests
und Integration-Tests. Integration-Tests testen die von Controllern unabhängige Funktionalität, wie z.B. Models.

## System-Tests/End-to-End Tests
Diese werden zwar im Backend implementiert, beziehen sich aber auf die gesamte Codebase. D.h. es wird ein Firefox-Browser gestartet, welcher sich durch das gewünschte Feature hindurch klickt.
System-Tests/End-to-End Tests sind Blackbox-Tests, d.h. es wird nur geprüft, ob die gewünschte Funktionalität existiert aber nicht, was genau in den einzelnen Methoden passiert. Ein Beispiel wäre
zu Prüfen, ob ein Knopf eine geordnete Liste anzeigt, wenn dieser geklickt wird. Mit Rake werden alle Tests ausgeführt. Ein einzelnes Test-File kann mit rspec 'path/filename.spec' ausgeführt werden.

## Frontend-Tests
Diese testen lediglich die Funktionalität im Ember-Frontend. D.h. es wird z.B. geprüft ob ein Component den richtigen Request an das Backend schickt. Auch hier wird ein Firefox-Browser gestartet
und die Tests werden ausgeführt, indem auf die URL http://localhost:3000/tests navigiert wird. Es handelt sich um Whitebox-Tests, da auch die interne funktionalität der Methoden überprüft wird.

## Rubocop
Um eine standartisierte Formattierung sicherzustellen, wird Rubocop im gesamten Rails-Projekt verwendet. Die Regeln sind bei Spezialfällen angepasst, entsprechen aber generell den Standard Regeln welche von Rubocop gegeben sind.

## Actions
GitHub gibt einem die Möglichkeit, Tests auch auf einem Server laufen zu lassen. Im Cryptopus wird bei jedem commit der auf das Repository gepushed wird, eine GitHub Action gestartet,
welche alle Tests (auch Rubocop) ausführt.
