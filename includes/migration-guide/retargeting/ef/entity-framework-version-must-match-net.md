### <a name="entity-framework-version-must-match-the-net-framework-version"></a>Die Version von Entity Framework muss mit der Version von .NET Framework übereinstimmen

|   |   |
|---|---|
|Details|Die Version von Entity Framework muss mit der Version von .NET Framework übereinstimmen. Für .NET 4.5 wird Entity Framework 5 empfohlen. Bei EF 4.x in einem .NET 4.5-Projekt sind im Zusammenhang mit <xref:System.ComponentModel.DataAnnotations> mehrere Probleme bekannt. In .NET 4.5 wurden diese in eine andere Assembly verschoben, daher gibt es Probleme mit der Bestimmung der zu verwendenden Anmerkungen.|
|Vorschlag|Führen Sie bei Verwendung von .NET Framework 4.5 ein Upgrade auf Entity Framework 5 durch.|
|Bereich|Hauptversion|
|Version|4.5|
|Typ|Neuzuweisung|

