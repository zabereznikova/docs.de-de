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
# <a name="metadata"></a><span data-ttu-id="04987-103">Metadaten</span><span class="sxs-lookup"><span data-stu-id="04987-103">Metadata</span></span>

<span data-ttu-id="04987-104">Es gibt zwei APIs zum Abrufen von Metadaten in ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="04987-104">There are two APIs for retrieving metadata in ADO.NET.</span></span> <span data-ttu-id="04987-105">Die eine RUFT Metadaten zu Abfrageergebnissen ab,</span><span class="sxs-lookup"><span data-stu-id="04987-105">One retrieves metadata about query results.</span></span> <span data-ttu-id="04987-106">die andere ruft Metadaten über das Datenbankschema ab.</span><span class="sxs-lookup"><span data-stu-id="04987-106">The other retrieves metadata about the database schema.</span></span>

## <a name="query-result-metadata"></a><span data-ttu-id="04987-107">Metadaten für Abfrageergebnisse</span><span class="sxs-lookup"><span data-stu-id="04987-107">Query result metadata</span></span>

<span data-ttu-id="04987-108">Mithilfe der <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A>-Methode in `SqliteDataReader` können Sie Metadaten zu den Ergebnissen einer Abfrage abrufen.</span><span class="sxs-lookup"><span data-stu-id="04987-108">You can retrieve metadata about the results of a query using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method on `SqliteDataReader`.</span></span> <span data-ttu-id="04987-109">Die zurückgegebene <xref:System.Data.DataTable>-Klasse enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="04987-109">The returned <xref:System.Data.DataTable> contains the following columns:</span></span>

| <span data-ttu-id="04987-110">Spalte</span><span class="sxs-lookup"><span data-stu-id="04987-110">Column</span></span>             | <span data-ttu-id="04987-111">Typ</span><span class="sxs-lookup"><span data-stu-id="04987-111">Type</span></span>    | <span data-ttu-id="04987-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04987-112">Description</span></span>                                                               |
| ------------------ | ------- | ------------------------------------------------------------------------- |
| `AllowDBNull`      | <span data-ttu-id="04987-113">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04987-113">Boolean</span></span> | <span data-ttu-id="04987-114">true, wenn die Ursprungsspalte möglicherweise NULL ist</span><span class="sxs-lookup"><span data-stu-id="04987-114">True if the origin column may be NULL.</span></span>                                    |
| `BaseCatalogName`  | <span data-ttu-id="04987-115">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04987-115">String</span></span>  | <span data-ttu-id="04987-116">Der Datenbankname der Ursprungsspalte,</span><span class="sxs-lookup"><span data-stu-id="04987-116">The name of the origin column's database.</span></span> <span data-ttu-id="04987-117">für Ausdrücke immer NULL</span><span class="sxs-lookup"><span data-stu-id="04987-117">Always NULL for expressions.</span></span>    |
| `BaseColumnName`   | <span data-ttu-id="04987-118">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04987-118">String</span></span>  | <span data-ttu-id="04987-119">Der Name der Ursprungsspalte ohne Alias,</span><span class="sxs-lookup"><span data-stu-id="04987-119">The unaliased name of the origin column.</span></span> <span data-ttu-id="04987-120">für Ausdrücke immer NULL</span><span class="sxs-lookup"><span data-stu-id="04987-120">Always NULL for expressions.</span></span>    |
| `BaseSchemaName`   | <span data-ttu-id="04987-121">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04987-121">String</span></span>  | <span data-ttu-id="04987-122">Immer NULL,</span><span class="sxs-lookup"><span data-stu-id="04987-122">Always NULL.</span></span> <span data-ttu-id="04987-123">SQLite unterstützt keine Schemas.</span><span class="sxs-lookup"><span data-stu-id="04987-123">SQLite doesn't support schemas.</span></span>                              |
| `BaseServerName`   | <span data-ttu-id="04987-124">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04987-124">String</span></span>  | <span data-ttu-id="04987-125">Der Pfad zur Datenbankdatei, der in der Verbindungszeichenfolge angegeben ist</span><span class="sxs-lookup"><span data-stu-id="04987-125">The path to the database file specified in the connection string.</span></span>         |
| `BaseTableName`    | <span data-ttu-id="04987-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04987-126">String</span></span>  | <span data-ttu-id="04987-127">Der Tabellenname der Ursprungsspalte,</span><span class="sxs-lookup"><span data-stu-id="04987-127">The name of the origin column's table.</span></span> <span data-ttu-id="04987-128">für Ausdrücke immer NULL</span><span class="sxs-lookup"><span data-stu-id="04987-128">Always NULL for expressions.</span></span>       |
| `ColumnName`       | <span data-ttu-id="04987-129">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04987-129">String</span></span>  | <span data-ttu-id="04987-130">Der Name oder Alias der Spalte im Resultset</span><span class="sxs-lookup"><span data-stu-id="04987-130">The name or alias of the column in the result set.</span></span>                        |
| `ColumnOrdinal`    | <span data-ttu-id="04987-131">Int32</span><span class="sxs-lookup"><span data-stu-id="04987-131">Int32</span></span>   | <span data-ttu-id="04987-132">Die Ordnungszahl der Spalte im Resultset</span><span class="sxs-lookup"><span data-stu-id="04987-132">The ordinal of the column in the result set.</span></span>                              |
| `ColumnSize`       | <span data-ttu-id="04987-133">Int32</span><span class="sxs-lookup"><span data-stu-id="04987-133">Int32</span></span>   | <span data-ttu-id="04987-134">Immer -1,</span><span class="sxs-lookup"><span data-stu-id="04987-134">Always -1.</span></span> <span data-ttu-id="04987-135">kann sich in zukünftigen Versionen von `Microsoft.Data.Sqlite` ändern</span><span class="sxs-lookup"><span data-stu-id="04987-135">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span>   |
| `DataType`         | <span data-ttu-id="04987-136">Typ</span><span class="sxs-lookup"><span data-stu-id="04987-136">Type</span></span>    | <span data-ttu-id="04987-137">Der .NET-Standard-Datentyp der Spalte</span><span class="sxs-lookup"><span data-stu-id="04987-137">The default .NET data type of the column.</span></span>                                 |
| `DataTypeName`     | <span data-ttu-id="04987-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04987-138">String</span></span>  | <span data-ttu-id="04987-139">Der SQLite-Datentyp der Spalte</span><span class="sxs-lookup"><span data-stu-id="04987-139">The SQLite data type of the column.</span></span>                                       |
| `IsAliased`        | <span data-ttu-id="04987-140">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04987-140">Boolean</span></span> | <span data-ttu-id="04987-141">true, wenn der Spaltenname im Resultset ein Alias ist.</span><span class="sxs-lookup"><span data-stu-id="04987-141">True if the column name is aliased in the result set.</span></span>                     |
| `IsAutoIncrement`  | <span data-ttu-id="04987-142">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04987-142">Boolean</span></span> | <span data-ttu-id="04987-143">true, wenn die Ursprungsspalte mit dem AUTOINCREMENT-Schlüsselwort erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="04987-143">True if the origin column was created with the AUTOINCREMENT keyword.</span></span>     |
| `IsExpression`     | <span data-ttu-id="04987-144">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04987-144">Boolean</span></span> | <span data-ttu-id="04987-145">true, wenn die Spalte aus einem Ausdruck in der Abfrage stammt</span><span class="sxs-lookup"><span data-stu-id="04987-145">True if the column originates from an expression in the query.</span></span>            |
| `IsKey`            | <span data-ttu-id="04987-146">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04987-146">Boolean</span></span> | <span data-ttu-id="04987-147">true, wenn die Ursprungsspalte Teil von PRIMARY KEY ist</span><span class="sxs-lookup"><span data-stu-id="04987-147">True if the origin column is part of the PRIMARY KEY.</span></span>                     |
| `IsUnique`         | <span data-ttu-id="04987-148">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04987-148">Boolean</span></span> | <span data-ttu-id="04987-149">true, wenn die Ursprungsspalte UNIQUE ist</span><span class="sxs-lookup"><span data-stu-id="04987-149">True if the origin column is UNIQUE.</span></span>                                      |
| `NumericPrecision` | <span data-ttu-id="04987-150">Int16</span><span class="sxs-lookup"><span data-stu-id="04987-150">Int16</span></span>   | <span data-ttu-id="04987-151">Immer NULL,</span><span class="sxs-lookup"><span data-stu-id="04987-151">Always NULL.</span></span> <span data-ttu-id="04987-152">kann sich in zukünftigen Versionen von `Microsoft.Data.Sqlite` ändern</span><span class="sxs-lookup"><span data-stu-id="04987-152">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |
| `NumericScale`     | <span data-ttu-id="04987-153">Int16</span><span class="sxs-lookup"><span data-stu-id="04987-153">Int16</span></span>   | <span data-ttu-id="04987-154">Immer NULL,</span><span class="sxs-lookup"><span data-stu-id="04987-154">Always NULL.</span></span> <span data-ttu-id="04987-155">kann sich in zukünftigen Versionen von `Microsoft.Data.Sqlite` ändern</span><span class="sxs-lookup"><span data-stu-id="04987-155">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |

<span data-ttu-id="04987-156">Im folgenden Beispiel wird veranschaulicht, wie `GetSchemaTable` verwendet wird, um eine Debugzeichenfolge zu erstellen, die Metadaten zu einem Ergebnis anzeigt:</span><span class="sxs-lookup"><span data-stu-id="04987-156">The following example shows how to use `GetSchemaTable` to create a debug string that shows metadata about a result:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ResultMetadataSample/Program.cs?name=snippet_ResultMetadata)]

<span data-ttu-id="04987-157">Diese Abfrage erzeugt z. B. die folgende Debugzeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="04987-157">For example, this query would produce the following debug string:</span></span>

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

## <a name="schema-metadata"></a><span data-ttu-id="04987-158">Metadaten für Schemas</span><span class="sxs-lookup"><span data-stu-id="04987-158">Schema metadata</span></span>

<span data-ttu-id="04987-159">Microsoft.Data.Sqlite implementiert die GetSchema-Methode nicht in DbConnection.</span><span class="sxs-lookup"><span data-stu-id="04987-159">Microsoft.Data.Sqlite doesn't implement the GetSchema method on DbConnection.</span></span> <span data-ttu-id="04987-160">Stattdessen können Sie mithilfe der Tabelle [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) und Pragmaanweisungen wie [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) und [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list) direkte Abfragen für Schemainformationen ausführen.</span><span class="sxs-lookup"><span data-stu-id="04987-160">Instead, you can query directly for schema information using the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and PRAGMA statements like [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) and [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).</span></span>

<span data-ttu-id="04987-161">Diese Abfrage ruft z. B. Metadaten zu allen Spalten in der Datenbank ab.</span><span class="sxs-lookup"><span data-stu-id="04987-161">For example, this query will retrieve metadata about all the columns in the database.</span></span>

```sql
SELECT t.name AS tbl_name, c.name, c.type, c.notnull, c.dflt_value, c.pk
FROM sqlite_master AS t,
     pragma_table_info(t.name) AS c
WHERE t.type = 'table';
```

## <a name="see-also"></a><span data-ttu-id="04987-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04987-162">See also</span></span>

* [<span data-ttu-id="04987-163">Speicherung des SQL-Datenbankschemas</span><span class="sxs-lookup"><span data-stu-id="04987-163">Storage of the SQL Database Schema</span></span>](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)
* [<span data-ttu-id="04987-164">Pragmaanweisungen</span><span class="sxs-lookup"><span data-stu-id="04987-164">PRAGMA Statements</span></span>](https://www.sqlite.org/pragma.html)
* [<span data-ttu-id="04987-165">Datentypen</span><span class="sxs-lookup"><span data-stu-id="04987-165">Data types</span></span>](types.md)
