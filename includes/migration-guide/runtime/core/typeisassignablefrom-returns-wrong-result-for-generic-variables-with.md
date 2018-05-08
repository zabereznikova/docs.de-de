### <a name="typeisassignablefrom-returns-wrong-result-for-generic-variables-with-constraints"></a>Type.IsAssignableFrom gibt ein falsches Ergebnis für generische Variablen mit Einschränkungen zurück.

|   |   |
|---|---|
|Details|In .NET Framework 4.5 gibt <xref:System.Type.IsAssignableFrom(System.Type)> für alle generischen Typen mit Einschränkungen fälschlicherweise <code>false</code> zurück.|
|Vorschlag|Dieses Problem wurde in einem Wartungsupdate behoben. Aktualisieren Sie .NET Framework 4.5 oder führen Sie ein Upgrade auf .NET Framework 4.5.1 oder höher aus, um dieses Problem zu beheben. Vermeiden Sie alternativ die Verwendung von „IsAssignableFrom“ mit generischen Typen, die bei generischen Parametern Einschränkungen aufweisen. Reflection-APIs können zur Problemumgehung verwendet werden.|
|Bereich|Gering|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Type.IsAssignableFrom(System.Type)?displayProperty=nameWithType></li></ul>|
|Analyzer|<ul><li>CD0089</li></ul>|

