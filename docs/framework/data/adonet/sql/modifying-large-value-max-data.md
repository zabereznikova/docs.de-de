---
title: Ändern von Daten mit umfangreichen Werten (max)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8aca5f00-d80e-4320-81b3-016d0466f7ee
ms.openlocfilehash: 8a077c56f4de5a88e9c2a6f932c9a8b5ffc6b974
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556966"
---
# <a name="modifying-large-value-max-data-in-adonet"></a><span data-ttu-id="7789d-102">Ändern von Daten mit umfangreichen Werten (max) in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7789d-102">Modifying Large-Value (max) Data in ADO.NET</span></span>
<span data-ttu-id="7789d-103">Bei Large Object-Datentypen (LOB) übersteigt die Zeilengröße die maximal zulässige Zeilengröße von 8 KB.</span><span class="sxs-lookup"><span data-stu-id="7789d-103">Large object (LOB) data types are those that exceed the maximum row size of 8 kilobytes (KB).</span></span> <span data-ttu-id="7789d-104">SQL Server  bietet einen `max`-Spezifizierer für die Datentypen `varchar`, `nvarchar` und `varbinary`, der das Speichern von 2^32 Bytes großen Werten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="7789d-104">SQL Server provides a `max` specifier for `varchar`, `nvarchar`, and `varbinary` data types to allow storage of values as large as 2^32 bytes.</span></span> <span data-ttu-id="7789d-105">Tabellenspalten und Transact-SQL-Variablen können die Datentypen `varchar(max)`, `nvarchar(max)` oder `varbinary(max)` angeben.</span><span class="sxs-lookup"><span data-stu-id="7789d-105">Table columns and Transact-SQL variables may specify `varchar(max)`, `nvarchar(max)`, or `varbinary(max)` data types.</span></span> <span data-ttu-id="7789d-106">In ADO.NET können die `max`-Datentypen durch einen `DataReader` abgerufen werden. Außerdem können sie ohne spezielle Behandlung sowohl als Eingabe- als auch als Ausgabeparameterwerte angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7789d-106">In ADO.NET, the `max` data types can be fetched by a `DataReader`, and can also be specified as both input and output parameter values without any special handling.</span></span> <span data-ttu-id="7789d-107">Für große `varchar`-Datentypen können Daten inkrementell abgerufen und aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7789d-107">For large `varchar` data types, data can be retrieved and updated incrementally.</span></span>  
  
 <span data-ttu-id="7789d-108">Die `max`-Datentypen können für Vergleiche, als Transact-SQL-Variablen und zum Verketten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7789d-108">The `max` data types can be used for comparisons, as Transact-SQL variables, and for concatenation.</span></span> <span data-ttu-id="7789d-109">Sie können auch in den Klauseln DISTINCT, ORDER BY und GROUP BY einer SELECT-Anweisung sowie in Aggregaten, Joins und Unterabfragen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7789d-109">They can also be used in the DISTINCT, ORDER BY, GROUP BY clauses of a SELECT statement as well as in aggregates, joins, and subqueries.</span></span>  
  
 <span data-ttu-id="7789d-110">Die folgende Tabelle enthält Links zur Dokumentation in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="7789d-110">The following table provides links to the documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="7789d-111">**SQL Server-Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="7789d-111">**SQL Server documentation**</span></span>  
  
1. <span data-ttu-id="7789d-112">[Verwenden von Datentypen mit umfangreichen Werten](/previous-versions/sql/sql-server-2008/ms178158(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="7789d-112">[Using Large-Value Data Types](/previous-versions/sql/sql-server-2008/ms178158(v=sql.100))</span></span>  
  
## <a name="large-value-type-restrictions"></a><span data-ttu-id="7789d-113">Einschränkungen für große Werttypen</span><span class="sxs-lookup"><span data-stu-id="7789d-113">Large-Value Type Restrictions</span></span>  
 <span data-ttu-id="7789d-114">Die folgenden Einschränkungen gelten für die `max`-Datentypen, die es für kleinere Datentypen nicht gibt:</span><span class="sxs-lookup"><span data-stu-id="7789d-114">The following restrictions apply to the `max` data types, which do not exist for smaller data types:</span></span>  
  
- <span data-ttu-id="7789d-115">Ein `sql_variant` kann nicht den großen Datentyp `varchar` enthalten.</span><span class="sxs-lookup"><span data-stu-id="7789d-115">A `sql_variant` cannot contain a large `varchar` data type.</span></span>  
  
- <span data-ttu-id="7789d-116">Große `varchar`-Spalten können nicht als Schlüsselspalte in einem Index angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7789d-116">Large `varchar` columns cannot be specified as a key column in an index.</span></span> <span data-ttu-id="7789d-117">Sie sind in einem nicht gruppierten Index in einer eingeschlossenen Spalte zulässig.</span><span class="sxs-lookup"><span data-stu-id="7789d-117">They are allowed in an included column in a non-clustered index.</span></span>  
  
- <span data-ttu-id="7789d-118">Große `varchar`-Spalten können nicht als Partitionierungsschlüsselspalten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7789d-118">Large `varchar` columns cannot be used as partitioning key columns.</span></span>  
  
## <a name="working-with-large-value-types-in-transact-sql"></a><span data-ttu-id="7789d-119">Arbeiten mit großen Werttypen in Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7789d-119">Working with Large-Value Types in Transact-SQL</span></span>  
 <span data-ttu-id="7789d-120">Die Transact-SQL-Funktion `OPENROWSET` bietet eine Einmalmethode zum Herstellen einer Verbindung mit und Zugreifen auf Remotedaten.</span><span class="sxs-lookup"><span data-stu-id="7789d-120">The Transact-SQL `OPENROWSET` function is a one-time method of connecting and accessing remote data.</span></span> <span data-ttu-id="7789d-121">Sie enthält alle erforderlichen Verbindungsinformationen für den Zugriff auf Remotedaten von einer OLE DB-Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="7789d-121">It includes all of the connection information necessary to access remote data from an OLE DB data source.</span></span> <span data-ttu-id="7789d-122">Auf `OPENROWSET` kann in der FROM-Klausel einer Abfrage so verwiesen werden, als ob es ein Tabellenname wäre.</span><span class="sxs-lookup"><span data-stu-id="7789d-122">`OPENROWSET` can be referenced in the FROM clause of a query as though it were a table name.</span></span> <span data-ttu-id="7789d-123">Abhängig von den Funktionen des OLE DB-Anbieters kann OPENROWSET auch als Zieltabelle einer INSERT-, UPDATE- oder DELETE-Anweisung dienen.</span><span class="sxs-lookup"><span data-stu-id="7789d-123">It can also be referenced as the target table of an INSERT, UPDATE, or DELETE statement, subject to the capabilities of the OLE DB provider.</span></span>  
  
 <span data-ttu-id="7789d-124">Die `OPENROWSET`-Funktion bietet den Rowsetanbieter `BULK`, mit dem Sie Daten direkt aus einer Datei lesen können, ohne sie in eine Zieltabelle zu laden.</span><span class="sxs-lookup"><span data-stu-id="7789d-124">The `OPENROWSET` function includes the `BULK` rowset provider, which allows you to read data directly from a file without loading the data into a target table.</span></span> <span data-ttu-id="7789d-125">Auf diese Weise können Sie `OPENROWSET` in einer einfachen INSERT SELECT-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="7789d-125">This enables you to use `OPENROWSET` in a simple INSERT SELECT statement.</span></span>  
  
 <span data-ttu-id="7789d-126">Die Optionsargumente von `OPENROWSET BULK` ermöglichen die flexible Festlegung, wo mit dem Lesen von Daten angefangen und aufgehört werden soll, wie mit Fehlern umzugehen ist und wie Daten interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="7789d-126">The `OPENROWSET BULK` option arguments provide significant control over where to begin and end reading data, how to deal with errors, and how data is interpreted.</span></span> <span data-ttu-id="7789d-127">Beispielsweise können Sie angeben, dass die Datendatei als einzeiliges, einspaltiges Rowset vom Datentyp `varbinary`, `varchar` oder `nvarchar` gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="7789d-127">For example, you can specify that the data file be read as a single-row, single-column rowset of type `varbinary`, `varchar`, or `nvarchar`.</span></span> <span data-ttu-id="7789d-128">Die gesamte Syntax und Optionen finden Sie in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="7789d-128">For the complete syntax and options, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="7789d-129">Im folgenden Beispiel wird ein Foto in die Tabelle ProductPhoto in der Beispieldatenbank AdventureWorks eingefügt.</span><span class="sxs-lookup"><span data-stu-id="7789d-129">The following example inserts a photo into the ProductPhoto table in the AdventureWorks sample database.</span></span> <span data-ttu-id="7789d-130">Wenn Sie den `BULK OPENROWSET`-Anbieter verwenden, müssen Sie die benannte Liste der Spalten auch dann angeben, wenn Sie nicht in jeder Spalte Werte einfügen.</span><span class="sxs-lookup"><span data-stu-id="7789d-130">When using the `BULK OPENROWSET` provider, you must supply the named list of columns even if you aren't inserting values into every column.</span></span> <span data-ttu-id="7789d-131">Der Primärschlüssel ist in diesem Fall als Identitätsspalte definiert und kann in der Spaltenliste weggelassen werden.</span><span class="sxs-lookup"><span data-stu-id="7789d-131">The primary key in this case is defined as an identity column, and may be omitted from the column list.</span></span> <span data-ttu-id="7789d-132">Beachten Sie, dass Sie auch einen Korrelationsnamen am Ende der `OPENROWSET`-Anweisung angeben müssen, der in diesem Fall ThumbnailPhoto lautet.</span><span class="sxs-lookup"><span data-stu-id="7789d-132">Note that you must also supply a correlation name at the end of the `OPENROWSET` statement, which in this case is ThumbnailPhoto.</span></span> <span data-ttu-id="7789d-133">Dies korreliert mit der Spalte in der Tabelle `ProductPhoto`, in die die Datei geladen wird.</span><span class="sxs-lookup"><span data-stu-id="7789d-133">This correlates with the column in the `ProductPhoto` table into which the file is being loaded.</span></span>  
  
```sql  
INSERT Production.ProductPhoto (  
    ThumbnailPhoto,
    ThumbnailPhotoFilePath,
    LargePhoto,
    LargePhotoFilePath)  
SELECT ThumbnailPhoto.*, null, null, N'tricycle_pink.gif'  
FROM OPENROWSET
    (BULK 'c:\images\tricycle.jpg', SINGLE_BLOB) ThumbnailPhoto  
```  
  
## <a name="updating-data-using-update-write"></a><span data-ttu-id="7789d-134">Aktualisieren von Daten mithilfe von UPDATE .WRITE</span><span class="sxs-lookup"><span data-stu-id="7789d-134">Updating Data Using UPDATE .WRITE</span></span>  
 <span data-ttu-id="7789d-135">Die Transact-SQL-Anweisung UPDATE hat eine neue WRITE-Syntax zum Ändern des Inhalts der Spalten `varchar(max)`, `nvarchar(max)` oder `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="7789d-135">The Transact-SQL UPDATE statement has new WRITE syntax for modifying the contents of `varchar(max)`, `nvarchar(max)`, or `varbinary(max)` columns.</span></span> <span data-ttu-id="7789d-136">Dies ermöglicht Ihnen, Teilaktualisierungen an den Daten vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="7789d-136">This allows you to perform partial updates of the data.</span></span> <span data-ttu-id="7789d-137">Die .WRITE-Syntax von UPDATE wird hier in gekürzter Form gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7789d-137">The UPDATE .WRITE syntax is shown here in abbreviated form:</span></span>  
  
 <span data-ttu-id="7789d-138">UPDATE</span><span class="sxs-lookup"><span data-stu-id="7789d-138">UPDATE</span></span>  
  
 <span data-ttu-id="7789d-139">{ *\<object>* }</span><span class="sxs-lookup"><span data-stu-id="7789d-139">{ *\<object>* }</span></span>  
  
 <span data-ttu-id="7789d-140">SET</span><span class="sxs-lookup"><span data-stu-id="7789d-140">SET</span></span>  
  
 <span data-ttu-id="7789d-141">{ *column_name* = {. Write ( *Ausdruck* , @Offset , @Length )}</span><span class="sxs-lookup"><span data-stu-id="7789d-141">{ *column_name* = { .WRITE ( *expression* , @Offset , @Length ) }</span></span>  
  
 <span data-ttu-id="7789d-142">Die WRITE-Methode gibt an, dass ein Abschnitt des Werts von *colum_name* geändert wird.</span><span class="sxs-lookup"><span data-stu-id="7789d-142">The WRITE method specifies that a section of the value of the *column_name* will be modified.</span></span> <span data-ttu-id="7789d-143">Der Ausdruck ist der Wert, der in *column_name* kopiert wird, `@Offset` ist der Anfangspunkt, ab dem der Ausdruck geschrieben wird, und das `@Length`-Argument gibt die Länge des Abschnitts in der Spalte an.</span><span class="sxs-lookup"><span data-stu-id="7789d-143">The expression is the value that will be copied to the *column_name*, the `@Offset` is the beginning point at which the expression will be written, and the `@Length` argument is the length of the section in the column.</span></span>  
  
|<span data-ttu-id="7789d-144">Wenn</span><span class="sxs-lookup"><span data-stu-id="7789d-144">If</span></span>|<span data-ttu-id="7789d-145">Then</span><span class="sxs-lookup"><span data-stu-id="7789d-145">Then</span></span>|  
|--------|----------|  
|<span data-ttu-id="7789d-146">Der Ausdruck ist auf NULL festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7789d-146">The expression is set to NULL</span></span>|<span data-ttu-id="7789d-147">`@Length` wird ignoriert, und der Wert in *column_name* wird am angegebenen `@Offset` abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="7789d-147">`@Length` is ignored and the value in *column_name* is truncated at the specified `@Offset`.</span></span>|  
|<span data-ttu-id="7789d-148">`@Offset` ist NULL</span><span class="sxs-lookup"><span data-stu-id="7789d-148">`@Offset` is NULL</span></span>|<span data-ttu-id="7789d-149">Beim Updatevorgang wird der Ausdruck am Ende des vorhandenen Werts *column_name* angefügt, und `@Length` wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="7789d-149">The update operation appends the expression at the end of the existing *column_name* value and `@Length` is ignored.</span></span>|  
|<span data-ttu-id="7789d-150">`@Offset` ist größer als die Länge des Werts von column_name.</span><span class="sxs-lookup"><span data-stu-id="7789d-150">`@Offset` is greater than the length of the column_name value</span></span>|<span data-ttu-id="7789d-151">SQL Server gibt einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="7789d-151">SQL Server returns an error.</span></span>|  
|<span data-ttu-id="7789d-152">`@Length` ist NULL</span><span class="sxs-lookup"><span data-stu-id="7789d-152">`@Length` is NULL</span></span>|<span data-ttu-id="7789d-153">Der Updatevorgang entfernt alle Daten aus `@Offset` bis zum Ende des `column_name`-Werts.</span><span class="sxs-lookup"><span data-stu-id="7789d-153">The update operation removes all data from `@Offset` to the end of the `column_name` value.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="7789d-154">Weder `@Offset` noch `@Length` darf eine negative Zahl sein.</span><span class="sxs-lookup"><span data-stu-id="7789d-154">Neither `@Offset` nor `@Length` can be a negative number.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7789d-155">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7789d-155">Example</span></span>  
 <span data-ttu-id="7789d-156">Dieses Transact-SQL-Beispiel aktualisiert einen Teilwert in DocumentSummary, einer `nvarchar(max)`-Spalte in der Tabelle „Document“ in der Datenbank AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="7789d-156">This Transact-SQL example updates a partial value in DocumentSummary, an `nvarchar(max)` column in the Document table in the AdventureWorks database.</span></span> <span data-ttu-id="7789d-157">Der Begriff „components“ wird durch den Begriff „features“ ersetzt, indem der Ersatzbegriff, die Anfangsposition (offset) des zu ersetzenden Begriffs in den vorhandenen Daten und die Anzahl der zu ersetzenden Zeichen (length) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7789d-157">The word 'components' is replaced by the word 'features' by specifying the replacement word, the beginning location (offset) of the word to be replaced in the existing data, and the number of characters to be replaced (length).</span></span> <span data-ttu-id="7789d-158">Das Beispiel enthält SELECT-Anweisungen vor und nach der UPDATE-Anweisung, um Ergebnisse zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="7789d-158">The example includes SELECT statements before and after the UPDATE statement to compare results.</span></span>  
  
```sql
USE AdventureWorks;  
GO  
--View the existing value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety components of your bicycle.  
  
--Modify a single word in the DocumentSummary column  
UPDATE Production.Document  
SET DocumentSummary .WRITE (N'features',28,10)  
WHERE DocumentID = 3 ;  
GO
--View the modified value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety features of your bicycle.  
```  
  
## <a name="working-with-large-value-types-in-adonet"></a><span data-ttu-id="7789d-159">Arbeiten mit großen Werttypen in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7789d-159">Working with Large-Value Types in ADO.NET</span></span>  
 <span data-ttu-id="7789d-160">Sie können in ADO.NET mit großen Werttypen arbeiten, indem Sie große Werttypen als <xref:System.Data.SqlClient.SqlParameter>-Objekte in einem <xref:System.Data.SqlClient.SqlDataReader> angeben, damit ein Resultset zurückgegeben wird, oder indem Sie mithilfe eines <xref:System.Data.SqlClient.SqlDataAdapter> ein `DataSet`/ oder eine `DataTable` füllen.</span><span class="sxs-lookup"><span data-stu-id="7789d-160">You can work with large value types in ADO.NET by specifying large value types as <xref:System.Data.SqlClient.SqlParameter> objects in a <xref:System.Data.SqlClient.SqlDataReader> to return a result set, or by using a <xref:System.Data.SqlClient.SqlDataAdapter> to fill a `DataSet`/`DataTable`.</span></span> <span data-ttu-id="7789d-161">Es gibt keinen Unterschied zwischen der Art und Weise, wie Sie mit einem großen Werttyp und dem zugehörigen Datentyp mit kleinerem Wert arbeiten.</span><span class="sxs-lookup"><span data-stu-id="7789d-161">There is no difference between the way you work with a large value type and its related, smaller value data type.</span></span>  
  
### <a name="using-getsqlbytes-to-retrieve-data"></a><span data-ttu-id="7789d-162">Verwenden von GetSqlBytes zum Abrufen von Daten</span><span class="sxs-lookup"><span data-stu-id="7789d-162">Using GetSqlBytes to Retrieve Data</span></span>  
 <span data-ttu-id="7789d-163">Die `GetSqlBytes`-Methode von <xref:System.Data.SqlClient.SqlDataReader> kann verwendet werden, um den Inhalt einer `varbinary(max)`-Spalte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7789d-163">The `GetSqlBytes` method of the <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varbinary(max)` column.</span></span> <span data-ttu-id="7789d-164">Das folgende Codefragment geht von einem <xref:System.Data.SqlClient.SqlCommand>-Objekt namens `cmd` aus, das `varbinary(max)`-Daten in einer Tabelle auswählt, und von einem <xref:System.Data.SqlClient.SqlDataReader>-Objekt namens `reader`, das die Daten als <xref:System.Data.SqlTypes.SqlBytes> abruft.</span><span class="sxs-lookup"><span data-stu-id="7789d-164">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `varbinary(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data as <xref:System.Data.SqlTypes.SqlBytes>.</span></span>  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim bytes As SqlBytes = reader.GetSqlBytes(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBytes bytes = reader.GetSqlBytes(0);  
    }  
```  
  
### <a name="using-getsqlchars-to-retrieve-data"></a><span data-ttu-id="7789d-165">Abrufen von Daten mit "GetSqlChars"</span><span class="sxs-lookup"><span data-stu-id="7789d-165">Using GetSqlChars to Retrieve Data</span></span>  
 <span data-ttu-id="7789d-166">Die `GetSqlChars`-Methode von <xref:System.Data.SqlClient.SqlDataReader> kann verwendet werden, um den Inhalt einer `varchar(max)`- oder `nvarchar(max)`-Spalte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7789d-166">The `GetSqlChars` method of the <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varchar(max)` or `nvarchar(max)` column.</span></span> <span data-ttu-id="7789d-167">Das folgende Codefragment geht von einem <xref:System.Data.SqlClient.SqlCommand>-Objekt namens `cmd` aus, das `nvarchar(max)`-Daten in einer Tabelle auswählt, und von einem <xref:System.Data.SqlClient.SqlDataReader>-Objekt namens `reader`, das die Daten abruft.</span><span class="sxs-lookup"><span data-stu-id="7789d-167">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `nvarchar(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data.</span></span>  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim buffer As SqlChars = reader.GetSqlChars(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
{  
    SqlChars buffer = reader.GetSqlChars(0);  
}  
```  
  
### <a name="using-getsqlbinary-to-retrieve-data"></a><span data-ttu-id="7789d-168">Abrufen von Daten mit "GetSqlBinary"</span><span class="sxs-lookup"><span data-stu-id="7789d-168">Using GetSqlBinary to Retrieve Data</span></span>  
 <span data-ttu-id="7789d-169">Die `GetSqlBinary`-Methode von <xref:System.Data.SqlClient.SqlDataReader> kann verwendet werden, um den Inhalt einer `varbinary(max)`-Spalte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7789d-169">The `GetSqlBinary` method of a <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varbinary(max)` column.</span></span> <span data-ttu-id="7789d-170">Das folgende Codefragment geht von einem <xref:System.Data.SqlClient.SqlCommand>-Objekt namens `cmd` aus, das `varbinary(max)`-Daten in einer Tabelle auswählt, und von einem <xref:System.Data.SqlClient.SqlDataReader>-Objekt namens `reader`, das die Daten als <xref:System.Data.SqlTypes.SqlBinary>-Datenstrom abruft.</span><span class="sxs-lookup"><span data-stu-id="7789d-170">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `varbinary(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data as a <xref:System.Data.SqlTypes.SqlBinary> stream.</span></span>  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim binaryStream As SqlBinary = reader.GetSqlBinary(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBinary binaryStream = reader.GetSqlBinary(0);  
    }  
```  
  
### <a name="using-getbytes-to-retrieve-data"></a><span data-ttu-id="7789d-171">Abrufen von Daten mit "GetBytes"</span><span class="sxs-lookup"><span data-stu-id="7789d-171">Using GetBytes to Retrieve Data</span></span>  
 <span data-ttu-id="7789d-172">Die `GetBytes`-Methode von <xref:System.Data.SqlClient.SqlDataReader> liest einen Strom von Bytes aus dem angegebenen Spaltenoffset in ein Bytearray, das am angegebenen Arrayoffset beginnt.</span><span class="sxs-lookup"><span data-stu-id="7789d-172">The `GetBytes` method of a <xref:System.Data.SqlClient.SqlDataReader> reads a stream of bytes from the specified column offset into a byte array starting at the specified array offset.</span></span> <span data-ttu-id="7789d-173">Das folgende Codefragment geht von einem <xref:System.Data.SqlClient.SqlDataReader>-Objekt namens `reader` aus, das Bytes in ein Bytearray abruft.</span><span class="sxs-lookup"><span data-stu-id="7789d-173">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves bytes into a byte array.</span></span> <span data-ttu-id="7789d-174">Beachten Sie, dass `GetBytes` im Gegensatz zu `GetSqlBytes` eine Größe für den Arraypuffer fordert.</span><span class="sxs-lookup"><span data-stu-id="7789d-174">Note that, unlike `GetSqlBytes`, `GetBytes` requires a size for the array buffer.</span></span>  
  
```vb  
While reader.Read()  
    Dim buffer(4000) As Byte  
    Dim byteCount As Integer = _  
    CInt(reader.GetBytes(1, 0, buffer, 0, 4000))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    byte[] buffer = new byte[4000];  
    long byteCount = reader.GetBytes(1, 0, buffer, 0, 4000);  
}  
```  
  
### <a name="using-getvalue-to-retrieve-data"></a><span data-ttu-id="7789d-175">Abrufen von Daten mit "GetValue"</span><span class="sxs-lookup"><span data-stu-id="7789d-175">Using GetValue to Retrieve Data</span></span>  
 <span data-ttu-id="7789d-176">Die `GetValue`-Methode von <xref:System.Data.SqlClient.SqlDataReader> liest den Wert aus dem angegebenen Spaltenoffset in ein Array ein.</span><span class="sxs-lookup"><span data-stu-id="7789d-176">The `GetValue` method of a <xref:System.Data.SqlClient.SqlDataReader> reads the value from the specified column offset into an array.</span></span> <span data-ttu-id="7789d-177">Das folgende Codefragment geht von einem <xref:System.Data.SqlClient.SqlDataReader>-Objekt namens `reader` aus, das Binärdaten aus dem Offset der ersten Spalte und dann Zeichenfolgendaten aus dem Offset der zweiten Spalte abruft.</span><span class="sxs-lookup"><span data-stu-id="7789d-177">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves binary data from the first column offset, and then string data from the second column offset.</span></span>  
  
```vb  
While reader.Read()  
    ' Read the data from varbinary(max) column  
    Dim binaryData() As Byte = CByte(reader.GetValue(0))  
  
    ' Read the data from varchar(max) or nvarchar(max) column  
    Dim stringData() As String = Cstr((reader.GetValue(1))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    // Read the data from varbinary(max) column  
    byte[] binaryData = (byte[])reader.GetValue(0);  
  
    // Read the data from varchar(max) or nvarchar(max) column  
    String stringData = (String)reader.GetValue(1);  
}  
```  
  
## <a name="converting-from-large-value-types-to-clr-types"></a><span data-ttu-id="7789d-178">Konvertieren von großen Werttypen in CLR-Typen</span><span class="sxs-lookup"><span data-stu-id="7789d-178">Converting from Large Value Types to CLR Types</span></span>  
 <span data-ttu-id="7789d-179">Sie können den Inhalt einer `varchar(max)`- oder `nvarchar(max)`-Spalte mit einer der Methoden zur Zeichenfolgenkonvertierung, wie z. B. `ToString`, konvertieren.</span><span class="sxs-lookup"><span data-stu-id="7789d-179">You can convert the contents of a `varchar(max)` or `nvarchar(max)` column using any of the string conversion methods, such as `ToString`.</span></span> <span data-ttu-id="7789d-180">Das folgende Codefragment geht von einem <xref:System.Data.SqlClient.SqlDataReader>-Objekt namens `reader` aus, das die Daten abruft.</span><span class="sxs-lookup"><span data-stu-id="7789d-180">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data.</span></span>  
  
```vb  
While reader.Read()  
    Dim str as String = reader(0).ToString()  
    Console.WriteLine(str)  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
     string str = reader[0].ToString();  
     Console.WriteLine(str);  
}  
```  
  
### <a name="example"></a><span data-ttu-id="7789d-181">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7789d-181">Example</span></span>  
 <span data-ttu-id="7789d-182">Der folgende Code ruft den Namen und das `LargePhoto`-Objekt aus der Tabelle `ProductPhoto` in der Datenbank `AdventureWorks` ab und speichert es in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="7789d-182">The following code retrieves the name and the `LargePhoto` object from the `ProductPhoto` table in the `AdventureWorks` database and saves it to a file.</span></span> <span data-ttu-id="7789d-183">Die Assembly muss mit einem Verweis auf den Namespace <xref:System.Drawing> kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="7789d-183">The assembly needs to be compiled with a reference to the <xref:System.Drawing> namespace.</span></span>  <span data-ttu-id="7789d-184">Die <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A>-Methode von <xref:System.Data.SqlClient.SqlDataReader> gibt ein <xref:System.Data.SqlTypes.SqlBytes>-Objekt zurück, das eine `Stream`-Eigenschaft verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="7789d-184">The <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A> method of the <xref:System.Data.SqlClient.SqlDataReader> returns a <xref:System.Data.SqlTypes.SqlBytes> object that exposes a `Stream` property.</span></span> <span data-ttu-id="7789d-185">Der Code verwendet diese, um ein neues `Bitmap`-Objekt zu erstellen, das dann im `ImageFormat` GIF gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="7789d-185">The code uses this to create a new `Bitmap` object, and then saves it in the Gif `ImageFormat`.</span></span>  
  
 [!code-csharp[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/VB/source.vb#1)]  
  
## <a name="using-large-value-type-parameters"></a><span data-ttu-id="7789d-186">Verwenden großer Werttypparameter</span><span class="sxs-lookup"><span data-stu-id="7789d-186">Using Large Value Type Parameters</span></span>  
 <span data-ttu-id="7789d-187">Große Werttypen können in <xref:System.Data.SqlClient.SqlParameter>-Objekten auf dieselbe Weise verwendet werden wie kleinere Werttypen in <xref:System.Data.SqlClient.SqlParameter>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="7789d-187">Large value types can be used in <xref:System.Data.SqlClient.SqlParameter> objects the same way you use smaller value types in <xref:System.Data.SqlClient.SqlParameter> objects.</span></span> <span data-ttu-id="7789d-188">Sie können große Werttypen als <xref:System.Data.SqlClient.SqlParameter>-Werte abrufen, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7789d-188">You can retrieve large value types as <xref:System.Data.SqlClient.SqlParameter> values, as shown in the following example.</span></span> <span data-ttu-id="7789d-189">Der Code geht davon aus, dass die folgende gespeicherte Prozedur GetDocumentSummary in der Beispieldatenbank AdventureWorks vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7789d-189">The code assumes that the following GetDocumentSummary stored procedure exists in the AdventureWorks sample database.</span></span> <span data-ttu-id="7789d-190">Die gespeicherte Prozedur verwendet einen Eingabeparameter mit dem Namen „@DocumentID“ und gibt den Inhalt der Spalte „DocumentSummary“ im @DocumentSummary-Ausgabeparameter zurück.</span><span class="sxs-lookup"><span data-stu-id="7789d-190">The stored procedure takes an input parameter named @DocumentID and returns the contents of the DocumentSummary column in the @DocumentSummary output parameter.</span></span>  
  
```sql
CREATE PROCEDURE GetDocumentSummary
(  
    @DocumentID int,  
    @DocumentSummary nvarchar(MAX) OUTPUT  
)  
AS  
SET NOCOUNT ON  
SELECT  @DocumentSummary=Convert(nvarchar(MAX), DocumentSummary)  
FROM    Production.Document  
WHERE   DocumentID=@DocumentID  
```  
  
### <a name="example"></a><span data-ttu-id="7789d-191">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7789d-191">Example</span></span>  
 <span data-ttu-id="7789d-192">Der ADO.NET-Code erstellt <xref:System.Data.SqlClient.SqlConnection>- und <xref:System.Data.SqlClient.SqlCommand>-Objekte, um die gespeicherte Prozedur GetDocumentSummary auszuführen und die Dokumentzusammenfassung abzurufen, die als großer Werttyp gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="7789d-192">The ADO.NET code creates <xref:System.Data.SqlClient.SqlConnection> and <xref:System.Data.SqlClient.SqlCommand> objects to execute the GetDocumentSummary stored procedure and retrieve the document summary, which is stored as a large value type.</span></span> <span data-ttu-id="7789d-193">Der Code übergibt einen Wert für den @DocumentID-Eingabeparameter, und die im @DocumentSummary-Ausgabeparameter zurückgegebenen Ergebnisse werden im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7789d-193">The code passes a value for the @DocumentID input parameter, and displays the results passed back in the @DocumentSummary output parameter in the Console window.</span></span>  
  
 [!code-csharp[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7789d-194">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7789d-194">See also</span></span>

- [<span data-ttu-id="7789d-195">SQL Server von Binärdaten und Daten mit umfangreichen Werten</span><span class="sxs-lookup"><span data-stu-id="7789d-195">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="7789d-196">SQL Server-Datentypzuordnungen</span><span class="sxs-lookup"><span data-stu-id="7789d-196">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="7789d-197">SQL Server von Daten Vorgängen in ADO.net</span><span class="sxs-lookup"><span data-stu-id="7789d-197">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="7789d-198">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7789d-198">ADO.NET Overview</span></span>](../ado-net-overview.md)
