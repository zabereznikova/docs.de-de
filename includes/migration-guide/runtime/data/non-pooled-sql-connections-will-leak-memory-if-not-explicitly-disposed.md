### <a name="non-pooled-sql-connections-will-leak-memory-if-not-explicitly-disposed"></a>SQL-Verbindungen ohne Pooling verlieren Arbeitsspeicher, wenn sie nicht explizit gelöscht werden.

|   |   |
|---|---|
|Details|In .NET Framework 4.5 verlieren SQL-Verbindungen ohne Pooling, die nicht explizit (über „Löschen“, „Schließen“ oder „Verwenden“) geschlossen wurden, Arbeitsspeicher|
|Vorschlag|Dieses Problem wurde in einem Wartungsupdate von .NET Framework 4.5 behoben. Aktualisieren Sie .NET Framework 4.5 oder führen Sie ein Upgrade auf .NET Framework 4.5.1 oder höher aus, um dieses Problem zu beheben. Alternativ kann dieses Problem vermieden werden, indem Sie <xref:System.Data.SqlClient.SqlConnection?displayProperty=name> in einem &#39;using&#39-Muster verwenden (dies ist eine bewährte Methode), oder durch explizites Aufrufen von „Löschen“ oder „Schließen“, wenn die Verbindung nicht mehr benötigt wird.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String%2CSystem.Data.SqlClient.SqlCredential)?displayProperty=nameWithType></li></ul>|

