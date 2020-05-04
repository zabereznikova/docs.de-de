---
title: Metadaten
ms.date: 12/13/2019
description: Informationen zum Abrufen von Metadaten über eine Datenbank
ms.openlocfilehash: b2f2704a748627d9943943fa2fa7b1b7e9f3007f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450429"
---
# <a name="metadata"></a>Metadaten

Es gibt zwei APIs zum Abrufen von Metadaten in ADO.NET. Die eine RUFT Metadaten zu Abfrageergebnissen ab, die andere ruft Metadaten über das Datenbankschema ab.

## <a name="query-result-metadata"></a>Metadaten für Abfrageergebnisse

Mithilfe der <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A>-Methode in `SqliteDataReader` können Sie Metadaten zu den Ergebnissen einer Abfrage abrufen. Die zurückgegebene <xref:System.Data.DataTable>-Klasse enthält die folgenden Spalten:

| Spalte             | Typ    | Beschreibung                                                               |
| ------------------ | ------- | ------------------------------------------------------------------------- |
| `AllowDBNull`      | Boolesch | true, wenn die Ursprungsspalte möglicherweise NULL ist                                    |
| `BaseCatalogName`  | Zeichenfolge  | Der Datenbankname der Ursprungsspalte, für Ausdrücke immer NULL    |
| `BaseColumnName`   | Zeichenfolge  | Der Name der Ursprungsspalte ohne Alias, für Ausdrücke immer NULL    |
| `BaseSchemaName`   | Zeichenfolge  | Immer NULL, SQLite unterstützt keine Schemas.                              |
| `BaseServerName`   | Zeichenfolge  | Der Pfad zur Datenbankdatei, der in der Verbindungszeichenfolge angegeben ist         |
| `BaseTableName`    | Zeichenfolge  | Der Tabellenname der Ursprungsspalte, für Ausdrücke immer NULL       |
| `ColumnName`       | Zeichenfolge  | Der Name oder Alias der Spalte im Resultset                        |
| `ColumnOrdinal`    | Int32   | Die Ordnungszahl der Spalte im Resultset                              |
| `ColumnSize`       | Int32   | Immer -1, kann sich in zukünftigen Versionen von `Microsoft.Data.Sqlite` ändern   |
| `DataType`         | Typ    | Der .NET-Standard-Datentyp der Spalte                                 |
| `DataTypeName`     | Zeichenfolge  | Der SQLite-Datentyp der Spalte                                       |
| `IsAliased`        | Boolesch | true, wenn der Spaltenname im Resultset ein Alias ist.                     |
| `IsAutoIncrement`  | Boolesch | true, wenn die Ursprungsspalte mit dem AUTOINCREMENT-Schlüsselwort erstellt wurde     |
| `IsExpression`     | Boolesch | true, wenn die Spalte aus einem Ausdruck in der Abfrage stammt            |
| `IsKey`            | Boolesch | true, wenn die Ursprungsspalte Teil von PRIMARY KEY ist                     |
| `IsUnique`         | Boolesch | true, wenn die Ursprungsspalte UNIQUE ist                                      |
| `NumericPrecision` | Int16   | Immer NULL, kann sich in zukünftigen Versionen von `Microsoft.Data.Sqlite` ändern |
| `NumericScale`     | Int16   | Immer NULL, kann sich in zukünftigen Versionen von `Microsoft.Data.Sqlite` ändern |

Im folgenden Beispiel wird veranschaulicht, wie `GetSchemaTable` verwendet wird, um eine Debugzeichenfolge zu erstellen, die Metadaten zu einem Ergebnis anzeigt:

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ResultMetadataSample/Program.cs?name=snippet_ResultMetadata)]

Diese Abfrage erzeugt z. B. die folgende Debugzeichenfolge:

```sql
SELECT id AS post_id,
       title,
       body,
       random() AS random
FROM post
```

```output
post.id AS post_id INTEGER PRIMARY KEY AUTOINCREMENT
post.title TEXT NOT NULL UNIQUE
post.body TEXT
(expression) AS random BLOB
```

## <a name="schema-metadata"></a>Metadaten für Schemas

Microsoft.Data.Sqlite implementiert die GetSchema-Methode nicht in DbConnection. Stattdessen können Sie mithilfe der Tabelle [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) und Pragmaanweisungen wie [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) und [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list) direkte Abfragen für Schemainformationen ausführen.

Diese Abfrage ruft z. B. Metadaten zu allen Spalten in der Datenbank ab.

```sql
SELECT t.name AS tbl_name, c.name, c.type, c.notnull, c.dflt_value, c.pk
FROM sqlite_master AS t,
     pragma_table_info(t.name) AS c
WHERE t.type = 'table';
```

## <a name="see-also"></a>Siehe auch

* [Speicherung des SQL-Datenbankschemas](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)
* [Pragmaanweisungen](https://www.sqlite.org/pragma.html)
* [Datentypen](types.md)
