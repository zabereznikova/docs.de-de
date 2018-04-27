### <a name="xml-schema-validation-is-stricter"></a>Die XML-Schemaüberprüfung ist genauer

|   |   |
|---|---|
|Details|In .NET Framework 4.5 ist die XML-Schemaüberprüfung genauer. Wenn Sie xsd:anyURI verwenden, um einen URI wie ein mailto-Protokoll zu überprüfen, tritt bei der Validierung ein Fehler auf, wenn der URI Leerzeichen enthält. In früheren Versionen von .NET Framework war die Validierung erfolgreich. Die Änderung betrifft nur Anwendungen, die auf .NET Framework 4.5 ausgerichtet sind.|
|Vorschlag|Wenn eine weniger genaue Überprüfung für .NET Framework 4.0 erforderlich ist, kann die überprüfende Anwendung auf Version 4.0 von .NET Framework ausgerichtet werden. Bei einer Neuausrichtung auf .NET 4.5 sollte jedoch ein Code Review durchgeführt werden, um sicherzustellen, dass ungültige URIs (mit Leerzeichen) nicht als Attributwerte mit dem Datentyp anyURI erwartet werden.|
|Bereich|Gering|
|Version|4.5|
|Typ|Neuzuweisung|

