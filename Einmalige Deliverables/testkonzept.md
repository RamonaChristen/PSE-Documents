# Testkonzept von Cryptopus
Das Cryptopus hat ein umfangreiches Testkonzept, welches Unit-Tests, System-Tests, End-to-End Tests, Frontend-Tests, Actions und einen mehrstufigen Review-Prozess beinhaltet.
Wird ein neues Feature implementiert (z. B. Logs), dann muss dieses vollständig mit den oben genannten Tests abgedeckt werden.
Das Feature wird auf einem separaten Branch implementiert und wird bei einem Pull-Request zuerst von einem Mitarbeiter und dann vom verantwortlichen für das Projekt reviewt.
Falls noch Änderungen vorgenommen werden müssen, werden diese gemacht, gepusht und dann wieder reviewt.
Dieser Prozess wird so lange wiederholt, bis der Branch den Anforderungen der Reviewer entspricht. Ist das der Fall, so wird der Branch in den Master Branch gemerged.

## Unit-Tests
Diese werden im Cryptopus im Rails-Backend implementiert. Mit den Unit-Tests wird sichergestellt, dass die einzelnen Komponenten/Funktionen unabhängig voneinander Funktionieren. Unit-Tests
sind im Cryptopus Whitebox-Tests, d.h. es wird nicht nur geschaut, ob sie den gewünschten Output liefern, sondern auch wie dieser zustande kommt. Wird z. B. eine Methode in der Methode aufgerufen,
welche getestet wird, wird auch getestet, ob diese Methode tatsächlich aufgerufen wurde. Beispiele für Unit-Tests bzgl. eines Serializers befinden sich [hier](https://github.com/puzzle/cryptopus/blob/master/spec/unit/serializers/team_serializer_spec.rb).
Die Unit-Tests befinden sich im Cryptopus im Ordner 'Unit' und umfassen die Authentifizierung, die Serializer, die Libraries und die Utilities. Getestet werden die einzelnen Methoden, welche sich
in den Klassen befinden. Also z. B. die Authentication Klasse, die OidcClient Klasse und die EncryptableSerializer Klasse. Der Ordner befindet sich [hier](https://github.com/puzzle/cryptopus/tree/master/spec/unit)

## Integration-Tests
Im Cryptopus existieren separate Test Ordner für Controller-Tests, Migration-Tests, Autorisierungstests
und Integration-Tests. Integration-Tests testen das Zusammenspiel mehrerer Funktionen. Wird eine neue Funktion implementiert, muss also auch überprüft werden, wie diese sich im Zusammenhang mit anderen
Funktionen verhält. Ein Integration-Test für das User Modell sieht dann so aus https://github.com/puzzle/cryptopus/blob/master/spec/integration/user_login_spec.rb .

## Migration-Tests
Diese werden im Rails-Backend implementiert und testen, ob die Datenbank-Migrationen richtig ausgeführt werden.
Dieses [Beispiel](https://github.com/puzzle/cryptopus/blob/master/spec/migrations/move_file_entries_to_encryptable_files_spec.rb
) zeigt einen Migration-Test.

## Controller-Tests
Diese werden auch im Rails-Backend implementiert und testen ausschließlich die Controller. Tests für den Session Controller sehen z.B. [so](https://github.com/puzzle/cryptopus/blob/master/spec/controllers/session_controller_spec.rb) aus.

## Policy-Tests
Das Cryptopus verfügt über Policies welche definiere, auf welche Models ein User zugreifen darf. Diese Policies werden ebenfalls separat getestet.
In [diesem](https://github.com/puzzle/cryptopus/blob/master/spec/policies/encryptable_policy_spec.rb) Policy-Test werden die Policies bzgl. eines Encryptables getestet.

## System-Tests/End-to-End Tests
Diese werden zwar im Backend implementiert, beziehen sich aber auf die gesamte Codebase. D. h. Es wird ein Firefox-Browser gestartet, welcher sich durch das gewünschte Feature hindurch klickt.
System-Tests/End-to-End Tests sind Blackbox-Tests, d.h. es wird nur geprüft, ob die gewünschte Funktionalität existiert aber nicht, was genau in den einzelnen Methoden passiert. Ein Beispiel wäre
zu Prüfen, ob ein Knopf eine geordnete Liste anzeigt, wenn dieser geklickt wird. Mit Rake werden alle Tests ausgeführt. Ein einzelnes Test-File kann mit rspec 'path/filename.spec' ausgeführt werden.
[Dieser](https://github.com/puzzle/cryptopus/blob/master/spec/system/create_user_system_spec.rb
) System-Test überprüft, ob ein User mit dem UI erstellt werden kann.

## Frontend-Tests
Diese testen lediglich die Funktionalität im Ember-Frontend. D. h. es wird z. B. geprüft, ob ein Component den richtigen Request an das Backend schickt. Auch hier wird ein Firefox-Browser gestartet
und die Tests werden ausgeführt, indem auf die URL http://localhost:3000/tests navigiert wird. Es handelt sich um Whitebox-Tests, da auch die interne Funktionalität der Methoden überprüft wird.
[Dieses](https://github.com/puzzle/cryptopus/blob/master/frontend/tests/integration/components/admin/users-test.js
) Beispiel zeigt einen Integration-Test im Frontend.

## Rubocop
Um eine standardisierte Formatierung sicherzustellen, wird Rubocop im gesamten Rails-Projekt verwendet. Die Regeln sind bei Spezialfällen angepasst, entsprechen aber generell den Standard Regeln, welche von Rubocop gegeben sind.

## Actions
GitHub gibt einem die Möglichkeit, Tests auch auf einem Server laufen zu lassen. Im Cryptopus wird bei jedem commit, der auf das Repository gepusht wird, eine GitHub-Action gestartet,
welche alle Tests (auch Rubocop) ausführt.

## Usability-Test
Das Cryptopus wird als Passwortmanager von allen Angestellten von Puzzle verwendet. Da das Cryptopus intern entwickelt wird, verfügen die Entwickler über ein grosses
Vorwissen der Software. Für die anderen Angestellten, wie z. B. diese im HR, beschränken sich die Vorkenntnisse auf die Bedienung der Software. Das Umfasst vorallem
das Anmelden, das Finden von Passwörtern und das Kopieren/Einfügen von Passwörtern bei Login in eine andere Software. Die Bedienbarkeit wird von den Entwicklern
getestet, welche daran Arbeiten. Wird z. B. im Frontend ein neuer Knopf implementiert, welcher eine Liste aller User anzeigt, überprüft der Entwickler, 
ob der Knopf richtig angezeigt wird. Danach überprüft er, ob die Liste richtig dargestellt wird und ob die User in der gewünschten Reihenfolge angezeigt werden.
Er erstellt dann einen System-Spec, welcher diesem Ablauf entspricht.
Zusätzlich bekommt jeder Entwickler von Cryptopus, vor einem neuen Release, 30 Minuten Zeit um sich durch die Seite zu klicken. Dabei versuchen sie mithilfe von Edge-Cases Fehler zu erzeugen. Alle gefundenen Fehler oder sonstige Kritikpunkte der Entwickler werden dann noch vor dem Release behoben.
