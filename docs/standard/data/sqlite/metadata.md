---
title: Metadaten
ms.date: 12/13/2019
description: Erfahren Sie, wie Metadaten über die Datenbank abgerufen werden.
ms.openlocfilehash: b2f2704a748627d9943943fa2fa7b1b7e9f3007f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450429"
---
# <a name="metadata"></a>Metadaten

Es gibt zwei APIs zum Abrufen von Metadaten in ADO.net. Eine Ruft Metadaten zu Abfrage Ergebnissen ab. Der andere Ruft Metadaten über das Datenbankschema ab.

## <a name="query-result-metadata"></a>Abfrageergebnis Metadaten

Mithilfe der <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A>-Methode auf `SqliteDataReader`können Sie Metadaten zu den Ergebnissen einer Abfrage abrufen. Der zurückgegebene <xref:System.Data.DataTable> enthält die folgenden Spalten:

| Spalte             | Typ    | Beschreibung                                                               |
| ------------------ | ------- | ------------------------------------------------------------------------- |
| `AllowDBNull`      | Boolean | True, wenn die Ursprungs Spalte möglicherweise NULL ist.                                    |
| `BaseCatalogName`  | Zeichenfolge  | Der Name der Datenbank der Ursprungs Spalte. Für Ausdrücke immer NULL.    |
| `BaseColumnName`   | Zeichenfolge  | Der Name der Ursprungs Spalte ohne Alias. Für Ausdrücke immer NULL.    |
| `BaseSchemaName`   | Zeichenfolge  | Immer NULL. SQLite unterstützt keine Schemas.                              |
| `BaseServerName`   | Zeichenfolge  | Der Pfad zur Datenbankdatei, die in der Verbindungs Zeichenfolge angegeben ist.         |
| `BaseTableName`    | Zeichenfolge  | Der Name der Tabelle der Ursprungs Spalte. Für Ausdrücke immer NULL.       |
| `ColumnName`       | Zeichenfolge  | Der Name oder Alias der Spalte im Resultset.                        |
| `ColumnOrdinal`    | Int32   | Die Ordnungszahl der Spalte im Resultset.                              |
| `ColumnSize`       | Int32   | Immer-1. Dies kann sich in zukünftigen Versionen von `Microsoft.Data.Sqlite`ändern.   |
| `DataType`         | Typ    | Der .NET-Standard Datentyp der Spalte.                                 |
| `DataTypeName`     | Zeichenfolge  | Der SQLite-Datentyp der Spalte.                                       |
| `IsAliased`        | Boolean | True, wenn der Name der Spalte im Resultset ein Alias ist.                     |
| `IsAutoIncrement`  | Boolean | True, wenn die Ursprungs Spalte mit dem AUTOINCREMENT-Schlüsselwort erstellt wurde.     |
| `IsExpression`     | Boolean | True, wenn die Spalte aus einem Ausdruck in der Abfrage stammt.            |
| `IsKey`            | Boolean | True, wenn die Ursprungs Spalte Teil des Primärschlüssels ist.                     |
| `IsUnique`         | Boolean | True, wenn die Ursprungs Spalte eindeutig ist.                                      |
| `NumericPrecision` | Int16   | Immer NULL. Dies kann sich in zukünftigen Versionen von `Microsoft.Data.Sqlite`ändern. |
| `NumericScale`     | Int16   | Immer NULL. Dies kann sich in zukünftigen Versionen von `Microsoft.Data.Sqlite`ändern. |

Im folgenden Beispiel wird gezeigt, wie `GetSchemaTable` verwendet wird, um eine debugzeichenfolge zu erstellen, die Metadaten zu einem Ergebnis anzeigt:

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ResultMetadataSample/Program.cs?name=snippet_ResultMetadata)]

Diese Abfrage erzeugt z. b. die folgende debugzeichenfolge:

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

## <a name="schema-metadata"></a>Schema Metadaten

Microsoft. Data. sqlite implementiert die GetSchema-Methode nicht in DbConnection. Stattdessen können Sie die Schema Informationen mithilfe der [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) Tabelle und der pragma-Anweisungen wie [TABLE_INFO](https://www.sqlite.org/pragma.html#pragma_table_info) und [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list)direkt abfragen.

Diese Abfrage ruft z. b. Metadaten zu allen Spalten in der Datenbank ab.

```sql
SELECT t.name AS tbl_name, c.name, c.type, c.notnull, c.dflt_value, c.pk
FROM sqlite_master AS t,
     pragma_table_info(t.name) AS c
WHERE t.type = 'table';
```

## <a name="see-also"></a>Siehe auch

* [Speicherung des SQL-Datenbankschemas](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)
* [Pragma-Anweisungen](https://www.sqlite.org/pragma.html)
* [Datentypen](types.md)
