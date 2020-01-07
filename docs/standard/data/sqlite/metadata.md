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
# <a name="metadata"></a><span data-ttu-id="10b1f-103">Metadaten</span><span class="sxs-lookup"><span data-stu-id="10b1f-103">Metadata</span></span>

<span data-ttu-id="10b1f-104">Es gibt zwei APIs zum Abrufen von Metadaten in ADO.net.</span><span class="sxs-lookup"><span data-stu-id="10b1f-104">There are two APIs for retrieving metadata in ADO.NET.</span></span> <span data-ttu-id="10b1f-105">Eine Ruft Metadaten zu Abfrage Ergebnissen ab.</span><span class="sxs-lookup"><span data-stu-id="10b1f-105">One retrieves metadata about query results.</span></span> <span data-ttu-id="10b1f-106">Der andere Ruft Metadaten über das Datenbankschema ab.</span><span class="sxs-lookup"><span data-stu-id="10b1f-106">The other retrieves metadata about the database schema.</span></span>

## <a name="query-result-metadata"></a><span data-ttu-id="10b1f-107">Abfrageergebnis Metadaten</span><span class="sxs-lookup"><span data-stu-id="10b1f-107">Query result metadata</span></span>

<span data-ttu-id="10b1f-108">Mithilfe der <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A>-Methode auf `SqliteDataReader`können Sie Metadaten zu den Ergebnissen einer Abfrage abrufen.</span><span class="sxs-lookup"><span data-stu-id="10b1f-108">You can retrieve metadata about the results of a query using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method on `SqliteDataReader`.</span></span> <span data-ttu-id="10b1f-109">Der zurückgegebene <xref:System.Data.DataTable> enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="10b1f-109">The returned <xref:System.Data.DataTable> contains the following columns:</span></span>

| <span data-ttu-id="10b1f-110">Spalte</span><span class="sxs-lookup"><span data-stu-id="10b1f-110">Column</span></span>             | <span data-ttu-id="10b1f-111">Typ</span><span class="sxs-lookup"><span data-stu-id="10b1f-111">Type</span></span>    | <span data-ttu-id="10b1f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10b1f-112">Description</span></span>                                                               |
| ------------------ | ------- | ------------------------------------------------------------------------- |
| `AllowDBNull`      | <span data-ttu-id="10b1f-113">Boolean</span><span class="sxs-lookup"><span data-stu-id="10b1f-113">Boolean</span></span> | <span data-ttu-id="10b1f-114">True, wenn die Ursprungs Spalte möglicherweise NULL ist.</span><span class="sxs-lookup"><span data-stu-id="10b1f-114">True if the origin column may be NULL.</span></span>                                    |
| `BaseCatalogName`  | <span data-ttu-id="10b1f-115">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="10b1f-115">String</span></span>  | <span data-ttu-id="10b1f-116">Der Name der Datenbank der Ursprungs Spalte.</span><span class="sxs-lookup"><span data-stu-id="10b1f-116">The name of the origin column's database.</span></span> <span data-ttu-id="10b1f-117">Für Ausdrücke immer NULL.</span><span class="sxs-lookup"><span data-stu-id="10b1f-117">Always NULL for expressions.</span></span>    |
| `BaseColumnName`   | <span data-ttu-id="10b1f-118">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="10b1f-118">String</span></span>  | <span data-ttu-id="10b1f-119">Der Name der Ursprungs Spalte ohne Alias.</span><span class="sxs-lookup"><span data-stu-id="10b1f-119">The unaliased name of the origin column.</span></span> <span data-ttu-id="10b1f-120">Für Ausdrücke immer NULL.</span><span class="sxs-lookup"><span data-stu-id="10b1f-120">Always NULL for expressions.</span></span>    |
| `BaseSchemaName`   | <span data-ttu-id="10b1f-121">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="10b1f-121">String</span></span>  | <span data-ttu-id="10b1f-122">Immer NULL.</span><span class="sxs-lookup"><span data-stu-id="10b1f-122">Always NULL.</span></span> <span data-ttu-id="10b1f-123">SQLite unterstützt keine Schemas.</span><span class="sxs-lookup"><span data-stu-id="10b1f-123">SQLite doesn't support schemas.</span></span>                              |
| `BaseServerName`   | <span data-ttu-id="10b1f-124">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="10b1f-124">String</span></span>  | <span data-ttu-id="10b1f-125">Der Pfad zur Datenbankdatei, die in der Verbindungs Zeichenfolge angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="10b1f-125">The path to the database file specified in the connection string.</span></span>         |
| `BaseTableName`    | <span data-ttu-id="10b1f-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="10b1f-126">String</span></span>  | <span data-ttu-id="10b1f-127">Der Name der Tabelle der Ursprungs Spalte.</span><span class="sxs-lookup"><span data-stu-id="10b1f-127">The name of the origin column's table.</span></span> <span data-ttu-id="10b1f-128">Für Ausdrücke immer NULL.</span><span class="sxs-lookup"><span data-stu-id="10b1f-128">Always NULL for expressions.</span></span>       |
| `ColumnName`       | <span data-ttu-id="10b1f-129">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="10b1f-129">String</span></span>  | <span data-ttu-id="10b1f-130">Der Name oder Alias der Spalte im Resultset.</span><span class="sxs-lookup"><span data-stu-id="10b1f-130">The name or alias of the column in the result set.</span></span>                        |
| `ColumnOrdinal`    | <span data-ttu-id="10b1f-131">Int32</span><span class="sxs-lookup"><span data-stu-id="10b1f-131">Int32</span></span>   | <span data-ttu-id="10b1f-132">Die Ordnungszahl der Spalte im Resultset.</span><span class="sxs-lookup"><span data-stu-id="10b1f-132">The ordinal of the column in the result set.</span></span>                              |
| `ColumnSize`       | <span data-ttu-id="10b1f-133">Int32</span><span class="sxs-lookup"><span data-stu-id="10b1f-133">Int32</span></span>   | <span data-ttu-id="10b1f-134">Immer-1.</span><span class="sxs-lookup"><span data-stu-id="10b1f-134">Always -1.</span></span> <span data-ttu-id="10b1f-135">Dies kann sich in zukünftigen Versionen von `Microsoft.Data.Sqlite`ändern.</span><span class="sxs-lookup"><span data-stu-id="10b1f-135">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span>   |
| `DataType`         | <span data-ttu-id="10b1f-136">Typ</span><span class="sxs-lookup"><span data-stu-id="10b1f-136">Type</span></span>    | <span data-ttu-id="10b1f-137">Der .NET-Standard Datentyp der Spalte.</span><span class="sxs-lookup"><span data-stu-id="10b1f-137">The default .NET data type of the column.</span></span>                                 |
| `DataTypeName`     | <span data-ttu-id="10b1f-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="10b1f-138">String</span></span>  | <span data-ttu-id="10b1f-139">Der SQLite-Datentyp der Spalte.</span><span class="sxs-lookup"><span data-stu-id="10b1f-139">The SQLite data type of the column.</span></span>                                       |
| `IsAliased`        | <span data-ttu-id="10b1f-140">Boolean</span><span class="sxs-lookup"><span data-stu-id="10b1f-140">Boolean</span></span> | <span data-ttu-id="10b1f-141">True, wenn der Name der Spalte im Resultset ein Alias ist.</span><span class="sxs-lookup"><span data-stu-id="10b1f-141">True if the column name is aliased in the result set.</span></span>                     |
| `IsAutoIncrement`  | <span data-ttu-id="10b1f-142">Boolean</span><span class="sxs-lookup"><span data-stu-id="10b1f-142">Boolean</span></span> | <span data-ttu-id="10b1f-143">True, wenn die Ursprungs Spalte mit dem AUTOINCREMENT-Schlüsselwort erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="10b1f-143">True if the origin column was created with the AUTOINCREMENT keyword.</span></span>     |
| `IsExpression`     | <span data-ttu-id="10b1f-144">Boolean</span><span class="sxs-lookup"><span data-stu-id="10b1f-144">Boolean</span></span> | <span data-ttu-id="10b1f-145">True, wenn die Spalte aus einem Ausdruck in der Abfrage stammt.</span><span class="sxs-lookup"><span data-stu-id="10b1f-145">True if the column originates from an expression in the query.</span></span>            |
| `IsKey`            | <span data-ttu-id="10b1f-146">Boolean</span><span class="sxs-lookup"><span data-stu-id="10b1f-146">Boolean</span></span> | <span data-ttu-id="10b1f-147">True, wenn die Ursprungs Spalte Teil des Primärschlüssels ist.</span><span class="sxs-lookup"><span data-stu-id="10b1f-147">True if the origin column is part of the PRIMARY KEY.</span></span>                     |
| `IsUnique`         | <span data-ttu-id="10b1f-148">Boolean</span><span class="sxs-lookup"><span data-stu-id="10b1f-148">Boolean</span></span> | <span data-ttu-id="10b1f-149">True, wenn die Ursprungs Spalte eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="10b1f-149">True if the origin column is UNIQUE.</span></span>                                      |
| `NumericPrecision` | <span data-ttu-id="10b1f-150">Int16</span><span class="sxs-lookup"><span data-stu-id="10b1f-150">Int16</span></span>   | <span data-ttu-id="10b1f-151">Immer NULL.</span><span class="sxs-lookup"><span data-stu-id="10b1f-151">Always NULL.</span></span> <span data-ttu-id="10b1f-152">Dies kann sich in zukünftigen Versionen von `Microsoft.Data.Sqlite`ändern.</span><span class="sxs-lookup"><span data-stu-id="10b1f-152">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |
| `NumericScale`     | <span data-ttu-id="10b1f-153">Int16</span><span class="sxs-lookup"><span data-stu-id="10b1f-153">Int16</span></span>   | <span data-ttu-id="10b1f-154">Immer NULL.</span><span class="sxs-lookup"><span data-stu-id="10b1f-154">Always NULL.</span></span> <span data-ttu-id="10b1f-155">Dies kann sich in zukünftigen Versionen von `Microsoft.Data.Sqlite`ändern.</span><span class="sxs-lookup"><span data-stu-id="10b1f-155">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |

<span data-ttu-id="10b1f-156">Im folgenden Beispiel wird gezeigt, wie `GetSchemaTable` verwendet wird, um eine debugzeichenfolge zu erstellen, die Metadaten zu einem Ergebnis anzeigt:</span><span class="sxs-lookup"><span data-stu-id="10b1f-156">The following example shows how to use `GetSchemaTable` to create a debug string that shows metadata about a result:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ResultMetadataSample/Program.cs?name=snippet_ResultMetadata)]

<span data-ttu-id="10b1f-157">Diese Abfrage erzeugt z. b. die folgende debugzeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="10b1f-157">For example, this query would produce the following debug string:</span></span>

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

## <a name="schema-metadata"></a><span data-ttu-id="10b1f-158">Schema Metadaten</span><span class="sxs-lookup"><span data-stu-id="10b1f-158">Schema metadata</span></span>

<span data-ttu-id="10b1f-159">Microsoft. Data. sqlite implementiert die GetSchema-Methode nicht in DbConnection.</span><span class="sxs-lookup"><span data-stu-id="10b1f-159">Microsoft.Data.Sqlite doesn't implement the GetSchema method on DbConnection.</span></span> <span data-ttu-id="10b1f-160">Stattdessen können Sie die Schema Informationen mithilfe der [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) Tabelle und der pragma-Anweisungen wie [TABLE_INFO](https://www.sqlite.org/pragma.html#pragma_table_info) und [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list)direkt abfragen.</span><span class="sxs-lookup"><span data-stu-id="10b1f-160">Instead, you can query directly for schema information using the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and PRAGMA statements like [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) and [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).</span></span>

<span data-ttu-id="10b1f-161">Diese Abfrage ruft z. b. Metadaten zu allen Spalten in der Datenbank ab.</span><span class="sxs-lookup"><span data-stu-id="10b1f-161">For example, this query will retrieve metadata about all the columns in the database.</span></span>

```sql
SELECT t.name AS tbl_name, c.name, c.type, c.notnull, c.dflt_value, c.pk
FROM sqlite_master AS t,
     pragma_table_info(t.name) AS c
WHERE t.type = 'table';
```

## <a name="see-also"></a><span data-ttu-id="10b1f-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10b1f-162">See also</span></span>

* [<span data-ttu-id="10b1f-163">Speicherung des SQL-Datenbankschemas</span><span class="sxs-lookup"><span data-stu-id="10b1f-163">Storage of the SQL Database Schema</span></span>](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)
* [<span data-ttu-id="10b1f-164">Pragma-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="10b1f-164">PRAGMA Statements</span></span>](https://www.sqlite.org/pragma.html)
* [<span data-ttu-id="10b1f-165">Datentypen</span><span class="sxs-lookup"><span data-stu-id="10b1f-165">Data types</span></span>](types.md)
