### <a name="change-in-behavior-in-data-definition-language-ddl-apis"></a>Änderung des Verhaltens in DDL-APIs (Data Definition Language, Datendefinitionssprachen)

|   |   |
|---|---|
|Details|Das Verhalten von DDL-APIs beim Angeben von „AttachDBFilename“ hat sich wie folgt geändert:<ul><li>Verbindungszeichenfolgen müssen keinen „Initial Catalog“-Wert angeben. Zuvor waren „AttatchDBFilename“ und „Initial Catalog“ erforderlich.</li><li>Wenn „AttatchDBFilename“ und „Initial Catalog“ angegeben sind und die angegebene MDF-Datei vorhanden ist, gibt die ObjectContext.DatabaseExists-Methode den Wert TRUE zurück. Bislang hat sie „false“ zurückgegeben.</li><li>Wenn „AttatchDBFilename“ und „Initial Catalog“ angegeben sind und die angegebene MDF-Datei vorhanden ist, löscht der Aufruf der ObjectContext.DeleteDatabase-Methode die Dateien.</li><li>Wenn „ObjectContext.DeleteDatabase“ aufgerufen wird, wenn die Verbindungszeichenfolge einen AttachDBFilename-Wert mit einer nicht vorhandenen MDF-Datei und einem nicht vorhandenen „Initial Catalog“ angibt, löst die Methode eine InvalidOperationException-Ausnahme aus. Zuvor hat sie eine SqlException-Ausnahme ausgelöst.</li></ul>|
|Vorschlag|Diese Änderungen erleichtern das Erstellen von Tools und Anwendungen, die die DDL-APIs verwenden. Diese Änderungen können sich in den folgenden Szenarien auf die Anwendungskompatibilität auswirken:<ul><li>Der Benutzer schreibt Code, der einen DROP DATABASE-Befehl direkt ausführt, anstatt „ObjectContext.DeleteDatabase“ aufzurufen, wenn „ObjectContext.DatabaseExists“ den Wert „true“ zurückgibt. Ist die Datenbank nicht angefügt, die MDF-Datei jedoch vorhanden, wird vorhandener Code hierdurch unbrauchbar.</li><li>Der Benutzer schreibt Code, der erwartet, dass die ObjectContext.DeleteDatabase-Methode anstelle einer InvalidOperationException-Ausnahme eine SqlException-Ausnahme auslöst, wenn „Initial Catalog“ und die MDF-Datei nicht vorhanden sind.</li></ul>|
|Bereich|Gering|
|Version|4.5|
|Typ|Laufzeit|

