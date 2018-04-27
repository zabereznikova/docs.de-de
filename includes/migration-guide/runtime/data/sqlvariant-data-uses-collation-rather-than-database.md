### <a name="sqlvariant-data-uses-sqlvariant-collation-rather-than-database-collation"></a>Sql_variant-Daten verwenden sql_variant-Sortierreihenfolgen anstatt Datenbanksortierreihenfolgen

|   |   |
|---|---|
|Details|<code>sql_variant</code>-Daten verwenden <code>sql_variant</code>-Sortierreihenfolgen anstatt Datenbanksortierreihenfolgen.|
|Vorschlag|Diese Änderung behandelt potenzielle Datenbeschädigungen, die verursacht werden, wenn sich die Datenbanksortierreihenfolge von der <code>sql_variant</code>-Sortierreihenfolge unterscheidet. Bei Anwendungen, die auf den beschädigten Daten basieren, treten möglicherweise Fehler auf.|
|Bereich|Transparent|
|Version|4.5|
|Typ|Laufzeit|

