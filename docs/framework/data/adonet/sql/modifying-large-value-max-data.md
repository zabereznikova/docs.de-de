---
title: Ändern von Daten mit umfangreichen Werten (max)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8aca5f00-d80e-4320-81b3-016d0466f7ee
ms.openlocfilehash: cb37fdb85d323d4f0816a3667a4624da8ec75e65
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "76979845"
---
# <a name="modifying-large-value-max-data-in-adonet"></a><span data-ttu-id="1526a-102">Ändern von Daten mit umfangreichen Werten (max) in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1526a-102">Modifying Large-Value (max) Data in ADO.NET</span></span>
<span data-ttu-id="1526a-103">Bei LOB-Datentypen übersteigt die Zeilengröße die maximal zulässige Zeilengröße von 8 KB.</span><span class="sxs-lookup"><span data-stu-id="1526a-103">Large object (LOB) data types are those that exceed the maximum row size of 8 kilobytes (KB).</span></span> <span data-ttu-id="1526a-104">SQL Server umfasst einen `max`-Spezifizierer für die Datentypen `varchar`, `nvarchar` und `varbinary`, der das Speichern Werten mit einer Größe bis zu 2^32 Bytes ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="1526a-104">SQL Server provides a `max` specifier for `varchar`, `nvarchar`, and `varbinary` data types to allow storage of values as large as 2^32 bytes.</span></span> <span data-ttu-id="1526a-105">Tabellenspalten und Transact-SQL-Variablen können die Datentypen `varchar(max)`, `nvarchar(max)` oder `varbinary(max)` angeben.</span><span class="sxs-lookup"><span data-stu-id="1526a-105">Table columns and Transact-SQL variables may specify `varchar(max)`, `nvarchar(max)`, or `varbinary(max)` data types.</span></span> <span data-ttu-id="1526a-106">In ADO.NET können die `max`-Datentypen durch einen `DataReader` abgerufen werden. Außerdem können sie ohne spezielle Behandlung sowohl als Eingabe- als auch als Ausgabeparameterwerte angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1526a-106">In ADO.NET, the `max` data types can be fetched by a `DataReader`, and can also be specified as both input and output parameter values without any special handling.</span></span> <span data-ttu-id="1526a-107">Bei großen `varchar`-Datentypen können Daten inkrementell abgerufen und aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="1526a-107">For large `varchar` data types, data can be retrieved and updated incrementally.</span></span>  
  
 <span data-ttu-id="1526a-108">Die `max`-Datentypen können für Vergleiche, als Transact-SQL-Variablen und zum Verketten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1526a-108">The `max` data types can be used for comparisons, as Transact-SQL variables, and for concatenation.</span></span> <span data-ttu-id="1526a-109">Auch der Einsatz in den Klauseln DISTINCT, ORDER BY und GROUP BY einer SELECT-Anweisung sowie in Aggregaten, Joins und Unterabfragen ist möglich.</span><span class="sxs-lookup"><span data-stu-id="1526a-109">They can also be used in the DISTINCT, ORDER BY, GROUP BY clauses of a SELECT statement as well as in aggregates, joins, and subqueries.</span></span>  
  
 <span data-ttu-id="1526a-110">Die folgende Tabelle enthält Links zur Dokumentation in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="1526a-110">The following table provides links to the documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="1526a-111">**SQL Server Books Online (SQL Server-Onlinedokumentation)**</span><span class="sxs-lookup"><span data-stu-id="1526a-111">**SQL Server Books Online**</span></span>  
  
1. [<span data-ttu-id="1526a-112">Verwenden von Datentypen mit umfangreichen Werten</span><span class="sxs-lookup"><span data-stu-id="1526a-112">Using Large-Value Data Types</span></span>](https://go.microsoft.com/fwlink/?LinkId=120498)  
  
## <a name="large-value-type-restrictions"></a><span data-ttu-id="1526a-113">Einschränkungen für große Werttypen</span><span class="sxs-lookup"><span data-stu-id="1526a-113">Large-Value Type Restrictions</span></span>  
 <span data-ttu-id="1526a-114">Für die `max`-Datentypen gelten die folgenden Einschränkungen, die für kleinere Datentypen nicht vorhanden sind:</span><span class="sxs-lookup"><span data-stu-id="1526a-114">The following restrictions apply to the `max` data types, which do not exist for smaller data types:</span></span>  
  
- <span data-ttu-id="1526a-115">Ein `sql_variant` kann keinen großen `varchar`-Datentyp enthalten.</span><span class="sxs-lookup"><span data-stu-id="1526a-115">A `sql_variant` cannot contain a large `varchar` data type.</span></span>  
  
- <span data-ttu-id="1526a-116">Große `varchar`-Spalten können nicht als Schlüsselspalte in einem Index angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1526a-116">Large `varchar` columns cannot be specified as a key column in an index.</span></span> <span data-ttu-id="1526a-117">In einer eingeschlossenen Spalte in einem nicht gruppierten Index sind sie jedoch zulässig.</span><span class="sxs-lookup"><span data-stu-id="1526a-117">They are allowed in an included column in a non-clustered index.</span></span>  
  
- <span data-ttu-id="1526a-118">Große `varchar`-Spalten können nicht zum Partitionieren von Schlüsselspalten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1526a-118">Large `varchar` columns cannot be used as partitioning key columns.</span></span>  
  
## <a name="working-with-large-value-types-in-transact-sql"></a><span data-ttu-id="1526a-119">Arbeiten mit großen Werttypen in Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1526a-119">Working with Large-Value Types in Transact-SQL</span></span>  
 <span data-ttu-id="1526a-120">Die Transact-SQL-`OPENROWSET`-Funktion ist eine für den Einmalgebrauch bestimmte Methode zum Herstellen einer Verbindung mit Remotedaten und den Zugriff auf diese Daten.</span><span class="sxs-lookup"><span data-stu-id="1526a-120">The Transact-SQL `OPENROWSET` function is a one-time method of connecting and accessing remote data.</span></span> <span data-ttu-id="1526a-121">Sie enthält alle erforderlichen Verbindungsinformationen für den Zugriff auf Remotedaten von einer OLE DB-Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="1526a-121">It includes all of the connection information necessary to access remote data from an OLE DB data source.</span></span> <span data-ttu-id="1526a-122">Auf `OPENROWSET` kann in der FROM-Klausel einer Abfrage so verwiesen werden, als ob es ein Tabellenname wäre.</span><span class="sxs-lookup"><span data-stu-id="1526a-122">`OPENROWSET` can be referenced in the FROM clause of a query as though it were a table name.</span></span> <span data-ttu-id="1526a-123">Abhängig von den Funktionen des OLE DB-Anbieters kann OPENROWSET auch als Zieltabelle einer INSERT-, UPDATE- oder DELETE-Anweisung dienen.</span><span class="sxs-lookup"><span data-stu-id="1526a-123">It can also be referenced as the target table of an INSERT, UPDATE, or DELETE statement, subject to the capabilities of the OLE DB provider.</span></span>  
  
 <span data-ttu-id="1526a-124">Die `OPENROWSET`-Funktion umfasst den `BULK`-Rowsetanbieter, mit dem Sie Daten direkt aus einer Datei lesen können, ohne sie in eine Zieltabelle zu laden.</span><span class="sxs-lookup"><span data-stu-id="1526a-124">The `OPENROWSET` function includes the `BULK` rowset provider, which allows you to read data directly from a file without loading the data into a target table.</span></span> <span data-ttu-id="1526a-125">Auf diese Weise können Sie `OPENROWSET` in einer einfachen INSERT SELECT-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="1526a-125">This enables you to use `OPENROWSET` in a simple INSERT SELECT statement.</span></span>  
  
 <span data-ttu-id="1526a-126">Die Argumente für die `OPENROWSET BULK` Option bieten eine bedeutende Kontrolle darüber, wo das Lesen von Daten begonnen und beendet werden soll, wie mit Fehlern umzugehen ist und wie Daten interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="1526a-126">The `OPENROWSET BULK` option arguments provide significant control over where to begin and end reading data, how to deal with errors, and how data is interpreted.</span></span> <span data-ttu-id="1526a-127">So können Sie z. B. angeben, dass die Datendatei als Rowset mit einer einzelnen Zeile und einer einzelnen Spalte vom Typ `varbinary`, `varchar` oder `nvarchar` gelesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="1526a-127">For example, you can specify that the data file be read as a single-row, single-column rowset of type `varbinary`, `varchar`, or `nvarchar`.</span></span> <span data-ttu-id="1526a-128">Die vollständige Syntax und alle Optionen finden Sie in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="1526a-128">For the complete syntax and options, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="1526a-129">Im folgenden Beispiel wird ein Foto in die ProductPhoto-Tabelle der AdventureWorks-Beispieldatenbank eingefügt.</span><span class="sxs-lookup"><span data-stu-id="1526a-129">The following example inserts a photo into the ProductPhoto table in the AdventureWorks sample database.</span></span> <span data-ttu-id="1526a-130">Wenn Sie den `BULK OPENROWSET`-Anbieter verwenden, müssen Sie die benannte Liste der Spalten angeben, auch wenn Sie keine Werte in jede Spalte einfügen.</span><span class="sxs-lookup"><span data-stu-id="1526a-130">When using the `BULK OPENROWSET` provider, you must supply the named list of columns even if you aren't inserting values into every column.</span></span> <span data-ttu-id="1526a-131">Der Primärschlüssel ist in diesem Fall als Identitätsspalte definiert und kann in der Liste der Spalten weggelassen werden.</span><span class="sxs-lookup"><span data-stu-id="1526a-131">The primary key in this case is defined as an identity column, and may be omitted from the column list.</span></span> <span data-ttu-id="1526a-132">Beachten Sie, dass Sie am Ende der `OPENROWSET`-Anweisung auch einen Korrelationsnamen angeben müssen. In diesem Fall lautet er "ThumbnailPhoto".</span><span class="sxs-lookup"><span data-stu-id="1526a-132">Note that you must also supply a correlation name at the end of the `OPENROWSET` statement, which in this case is ThumbnailPhoto.</span></span> <span data-ttu-id="1526a-133">Dies korreliert mit der Spalte in der `ProductPhoto`-Tabelle, in die die Datei geladen wird.</span><span class="sxs-lookup"><span data-stu-id="1526a-133">This correlates with the column in the `ProductPhoto` table into which the file is being loaded.</span></span>  
  
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
  
## <a name="updating-data-using-update-write"></a><span data-ttu-id="1526a-134">Aktualisieren von Daten mithilfe von UPDATE .WRITE</span><span class="sxs-lookup"><span data-stu-id="1526a-134">Updating Data Using UPDATE .WRITE</span></span>  
 <span data-ttu-id="1526a-135">Die Transact-SQL-Anweisung UPDATE weist eine neue WRITE-Syntax zum Ändern des Inhalts in den Spalten `varchar(max)`, `nvarchar(max)` oder `varbinary(max)` auf.</span><span class="sxs-lookup"><span data-stu-id="1526a-135">The Transact-SQL UPDATE statement has new WRITE syntax for modifying the contents of `varchar(max)`, `nvarchar(max)`, or `varbinary(max)` columns.</span></span> <span data-ttu-id="1526a-136">Dies ermöglicht es Ihnen, teilweise Updates der Daten durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="1526a-136">This allows you to perform partial updates of the data.</span></span> <span data-ttu-id="1526a-137">Die UPDATE .WRITE-Syntax wird hier in gekürzter Form dargestellt:</span><span class="sxs-lookup"><span data-stu-id="1526a-137">The UPDATE .WRITE syntax is shown here in abbreviated form:</span></span>  
  
 <span data-ttu-id="1526a-138">AKTUALISIEREN</span><span class="sxs-lookup"><span data-stu-id="1526a-138">UPDATE</span></span>  
  
 <span data-ttu-id="1526a-139">{ *\<Objekt >* }</span><span class="sxs-lookup"><span data-stu-id="1526a-139">{ *\<object>* }</span></span>  
  
 <span data-ttu-id="1526a-140">SET</span><span class="sxs-lookup"><span data-stu-id="1526a-140">SET</span></span>  
  
 <span data-ttu-id="1526a-141">{ *column_name* = {. Write ( *Ausdruck* , @Offset @Length)}</span><span class="sxs-lookup"><span data-stu-id="1526a-141">{ *column_name* = { .WRITE ( *expression* , @Offset , @Length ) }</span></span>  
  
 <span data-ttu-id="1526a-142">Die Write-Methode gibt an, dass ein Abschnitt des Werts des *column_name* geändert wird.</span><span class="sxs-lookup"><span data-stu-id="1526a-142">The WRITE method specifies that a section of the value of the *column_name* will be modified.</span></span> <span data-ttu-id="1526a-143">Der Ausdruck ist der Wert, der in den *column_name*kopiert wird, der `@Offset` ist der Anfangspunkt, an dem der Ausdruck geschrieben wird, und das `@Length`-Argument ist die Länge des Abschnitts in der Spalte.</span><span class="sxs-lookup"><span data-stu-id="1526a-143">The expression is the value that will be copied to the *column_name*, the `@Offset` is the beginning point at which the expression will be written, and the `@Length` argument is the length of the section in the column.</span></span>  
  
|<span data-ttu-id="1526a-144">Wenn virtuelle Maschinen mit</span><span class="sxs-lookup"><span data-stu-id="1526a-144">If</span></span>|<span data-ttu-id="1526a-145">Then</span><span class="sxs-lookup"><span data-stu-id="1526a-145">Then</span></span>|  
|--------|----------|  
|<span data-ttu-id="1526a-146">Der Ausdruck ist auf NULL festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1526a-146">The expression is set to NULL</span></span>|<span data-ttu-id="1526a-147">`@Length` wird ignoriert, und der Wert in *column_name* wird am angegebenen `@Offset`abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="1526a-147">`@Length` is ignored and the value in *column_name* is truncated at the specified `@Offset`.</span></span>|  
|<span data-ttu-id="1526a-148">`@Offset` ist NULL</span><span class="sxs-lookup"><span data-stu-id="1526a-148">`@Offset` is NULL</span></span>|<span data-ttu-id="1526a-149">Der Aktualisierungs Vorgang fügt den Ausdruck am Ende des vorhandenen *column_name* Werts an, und `@Length` wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1526a-149">The update operation appends the expression at the end of the existing *column_name* value and `@Length` is ignored.</span></span>|  
|<span data-ttu-id="1526a-150">`@Offset` ist größer als die Länge des &lt;legacyItalic&gt;column_name&lt;/legacyItalic&gt;-Werts</span><span class="sxs-lookup"><span data-stu-id="1526a-150">`@Offset` is greater than the length of the column_name value</span></span>|<span data-ttu-id="1526a-151">SQL Server gibt einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="1526a-151">SQL Server returns an error.</span></span>|  
|<span data-ttu-id="1526a-152">`@Length` ist NULL</span><span class="sxs-lookup"><span data-stu-id="1526a-152">`@Length` is NULL</span></span>|<span data-ttu-id="1526a-153">Beim Updatevorgang werden alle Daten ab `@Offset` bis zum Ende des `column_name`-Werts entfernt.</span><span class="sxs-lookup"><span data-stu-id="1526a-153">The update operation removes all data from `@Offset` to the end of the `column_name` value.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="1526a-154">Weder `@Offset` noch `@Length` darf eine negative Zahl sein.</span><span class="sxs-lookup"><span data-stu-id="1526a-154">Neither `@Offset` nor `@Length` can be a negative number.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1526a-155">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1526a-155">Example</span></span>  
 <span data-ttu-id="1526a-156">In diesem Transact-SQL-Beispiel wird ein Teil eines Werts in &lt;legacyBold&gt;DocumentSummary&lt;/legacyBold&gt; aktualisiert. Dabei handelt es sich um eine `nvarchar(max)`-Spalte in der &lt;legacyBold&gt;Document&lt;/legacyBold&gt;-Tabelle in der &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="1526a-156">This Transact-SQL example updates a partial value in DocumentSummary, an `nvarchar(max)` column in the Document table in the AdventureWorks database.</span></span> <span data-ttu-id="1526a-157">Das Wort "components" wird ersetzt durch "features". Dazu wird das Ersatzwort, die Anfangsposition (Offset) des zu ersetzenden Worts in den vorhandenen Daten und die Anzahl der zu ersetzenden Zeichen (Length) angegeben.</span><span class="sxs-lookup"><span data-stu-id="1526a-157">The word 'components' is replaced by the word 'features' by specifying the replacement word, the beginning location (offset) of the word to be replaced in the existing data, and the number of characters to be replaced (length).</span></span> <span data-ttu-id="1526a-158">Das Beispiel enthält SELECT-Anweisungen vor und nach der UPDATE-Anweisung, damit die Ergebnisse verglichen werden können.</span><span class="sxs-lookup"><span data-stu-id="1526a-158">The example includes SELECT statements before and after the UPDATE statement to compare results.</span></span>  
  
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
  
## <a name="working-with-large-value-types-in-adonet"></a><span data-ttu-id="1526a-159">Arbeiten mit großen Werttypen in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1526a-159">Working with Large-Value Types in ADO.NET</span></span>  
 <span data-ttu-id="1526a-160">Sie können mit großen Werttypen in ADO.NET arbeiten, indem Sie große Werttypen als <xref:System.Data.SqlClient.SqlParameter> Objekte in einem <xref:System.Data.SqlClient.SqlDataReader> angeben, um ein Resultset zurückzugeben, oder indem Sie einen <xref:System.Data.SqlClient.SqlDataAdapter> zum Ausfüllen eines `DataSet`/`DataTable`verwenden.</span><span class="sxs-lookup"><span data-stu-id="1526a-160">You can work with large value types in ADO.NET by specifying large value types as <xref:System.Data.SqlClient.SqlParameter> objects in a <xref:System.Data.SqlClient.SqlDataReader> to return a result set, or by using a <xref:System.Data.SqlClient.SqlDataAdapter> to fill a `DataSet`/`DataTable`.</span></span> <span data-ttu-id="1526a-161">Sie können mit großen Datentypen genauso arbeiten wie mit den entsprechenden kleineren Datentypen.</span><span class="sxs-lookup"><span data-stu-id="1526a-161">There is no difference between the way you work with a large value type and its related, smaller value data type.</span></span>  
  
### <a name="using-getsqlbytes-to-retrieve-data"></a><span data-ttu-id="1526a-162">Abrufen von Daten mit "GetSqlBytes"</span><span class="sxs-lookup"><span data-stu-id="1526a-162">Using GetSqlBytes to Retrieve Data</span></span>  
 <span data-ttu-id="1526a-163">Mit der `GetSqlBytes`-Methode von <xref:System.Data.SqlClient.SqlDataReader> können Sie den Inhalt einer `varbinary(max)`-Spalte abrufen.</span><span class="sxs-lookup"><span data-stu-id="1526a-163">The `GetSqlBytes` method of the <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varbinary(max)` column.</span></span> <span data-ttu-id="1526a-164">Im folgenden Codefragment wird von einem <xref:System.Data.SqlClient.SqlCommand>-Objekt mit dem Namen `cmd` ausgegangen, das `varbinary(max)`-Daten aus einer Tabelle auswählt. Außerdem gibt es ein <xref:System.Data.SqlClient.SqlDataReader>-Objekt mit dem Namen `reader`, das die Daten als <xref:System.Data.SqlTypes.SqlBytes> abruft.</span><span class="sxs-lookup"><span data-stu-id="1526a-164">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `varbinary(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data as <xref:System.Data.SqlTypes.SqlBytes>.</span></span>  
  
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
  
### <a name="using-getsqlchars-to-retrieve-data"></a><span data-ttu-id="1526a-165">Abrufen von Daten mit "GetSqlChars"</span><span class="sxs-lookup"><span data-stu-id="1526a-165">Using GetSqlChars to Retrieve Data</span></span>  
 <span data-ttu-id="1526a-166">Mit der `GetSqlChars`-Methode von <xref:System.Data.SqlClient.SqlDataReader> können Sie den Inhalt einer `varchar(max)`-Spalte oder einer `nvarchar(max)`-Spalte abrufen.</span><span class="sxs-lookup"><span data-stu-id="1526a-166">The `GetSqlChars` method of the <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varchar(max)` or `nvarchar(max)` column.</span></span> <span data-ttu-id="1526a-167">Im folgenden Codefragment wird von einem <xref:System.Data.SqlClient.SqlCommand>-Objekt mit dem Namen `cmd` ausgegangen, das `nvarchar(max)`-Daten aus einer Tabelle auswählt. Außerdem gibt es ein <xref:System.Data.SqlClient.SqlDataReader>-Objekt mit dem Namen `reader`, das die Daten abruft.</span><span class="sxs-lookup"><span data-stu-id="1526a-167">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `nvarchar(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data.</span></span>  
  
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
  
### <a name="using-getsqlbinary-to-retrieve-data"></a><span data-ttu-id="1526a-168">Abrufen von Daten mit "GetSqlBinary"</span><span class="sxs-lookup"><span data-stu-id="1526a-168">Using GetSqlBinary to Retrieve Data</span></span>  
 <span data-ttu-id="1526a-169">Mit der `GetSqlBinary`-Methode eines <xref:System.Data.SqlClient.SqlDataReader> können Sie den Inhalt einer `varbinary(max)`-Spalte abrufen.</span><span class="sxs-lookup"><span data-stu-id="1526a-169">The `GetSqlBinary` method of a <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varbinary(max)` column.</span></span> <span data-ttu-id="1526a-170">Im folgenden Codefragment wird von einem <xref:System.Data.SqlClient.SqlCommand>-Objekt mit dem Namen `cmd` ausgegangen, das `varbinary(max)`-Daten aus einer Tabelle auswählt. Außerdem gibt es ein <xref:System.Data.SqlClient.SqlDataReader>-Objekt mit dem Namen `reader`, das die Daten als <xref:System.Data.SqlTypes.SqlBinary>-Stream abruft.</span><span class="sxs-lookup"><span data-stu-id="1526a-170">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `varbinary(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data as a <xref:System.Data.SqlTypes.SqlBinary> stream.</span></span>  
  
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
  
### <a name="using-getbytes-to-retrieve-data"></a><span data-ttu-id="1526a-171">Abrufen von Daten mit "GetBytes"</span><span class="sxs-lookup"><span data-stu-id="1526a-171">Using GetBytes to Retrieve Data</span></span>  
 <span data-ttu-id="1526a-172">Die `GetBytes`-Methode eines <xref:System.Data.SqlClient.SqlDataReader> liest einen Bytestream, beginnend am angegebenen Spaltenoffset, in ein Bytearray, beginnend am angegebenen Arrayoffset.</span><span class="sxs-lookup"><span data-stu-id="1526a-172">The `GetBytes` method of a <xref:System.Data.SqlClient.SqlDataReader> reads a stream of bytes from the specified column offset into a byte array starting at the specified array offset.</span></span> <span data-ttu-id="1526a-173">Im folgenden Codefragment wird von einem <xref:System.Data.SqlClient.SqlDataReader>-Objekt mit dem Namen `reader` ausgegangen, das Bytes in ein Bytearray abruft.</span><span class="sxs-lookup"><span data-stu-id="1526a-173">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves bytes into a byte array.</span></span> <span data-ttu-id="1526a-174">Beachten Sie, dass `GetSqlBytes` im Unterschied zu `GetBytes` eine Größe für den Arraypuffer benötigt.</span><span class="sxs-lookup"><span data-stu-id="1526a-174">Note that, unlike `GetSqlBytes`, `GetBytes` requires a size for the array buffer.</span></span>  
  
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
  
### <a name="using-getvalue-to-retrieve-data"></a><span data-ttu-id="1526a-175">Abrufen von Daten mit "GetValue"</span><span class="sxs-lookup"><span data-stu-id="1526a-175">Using GetValue to Retrieve Data</span></span>  
 <span data-ttu-id="1526a-176">Die `GetValue`-Methode eines <xref:System.Data.SqlClient.SqlDataReader> liest den Wert, beginnend am angegebenen Spaltenoffset, in ein Array.</span><span class="sxs-lookup"><span data-stu-id="1526a-176">The `GetValue` method of a <xref:System.Data.SqlClient.SqlDataReader> reads the value from the specified column offset into an array.</span></span> <span data-ttu-id="1526a-177">Im folgenden Codefragment wird von einem <xref:System.Data.SqlClient.SqlDataReader>-Objekt mit dem Namen `reader` ausgegangen, das zuerst binäre Daten abruft und damit am ersten Spaltenoffset beginnt. Anschließend werden Zeichenfolgendaten abgerufen, wobei am zweiten Spaltenoffset begonnen wird.</span><span class="sxs-lookup"><span data-stu-id="1526a-177">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves binary data from the first column offset, and then string data from the second column offset.</span></span>  
  
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
  
## <a name="converting-from-large-value-types-to-clr-types"></a><span data-ttu-id="1526a-178">Konvertieren von großen Werttypen in CLR-Typen</span><span class="sxs-lookup"><span data-stu-id="1526a-178">Converting from Large Value Types to CLR Types</span></span>  
 <span data-ttu-id="1526a-179">Sie können den Inhalt einer `varchar(max)`-Spalte oder einer `nvarchar(max)`-Spalte mit einer beliebigen Methode zur Zeichenfolgenkonvertierung konvertieren, z. B. mit `ToString`.</span><span class="sxs-lookup"><span data-stu-id="1526a-179">You can convert the contents of a `varchar(max)` or `nvarchar(max)` column using any of the string conversion methods, such as `ToString`.</span></span> <span data-ttu-id="1526a-180">Im folgenden Codefragment wird von einem <xref:System.Data.SqlClient.SqlDataReader>-Objekt mit dem Namen `reader` ausgegangen, das die Daten abruft.</span><span class="sxs-lookup"><span data-stu-id="1526a-180">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data.</span></span>  
  
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
  
### <a name="example"></a><span data-ttu-id="1526a-181">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1526a-181">Example</span></span>  
 <span data-ttu-id="1526a-182">Der folgende Code ruft den Namen und das `LargePhoto`-Objekt aus der `ProductPhoto`-Tabelle in der `AdventureWorks`-Datenbank ab und speichert das Objekt in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="1526a-182">The following code retrieves the name and the `LargePhoto` object from the `ProductPhoto` table in the `AdventureWorks` database and saves it to a file.</span></span> <span data-ttu-id="1526a-183">Die Assembly muss mit einem Verweis auf den <xref:System.Drawing>-Namespace kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="1526a-183">The assembly needs to be compiled with a reference to the <xref:System.Drawing> namespace.</span></span>  <span data-ttu-id="1526a-184">Die <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A>-Methode des <xref:System.Data.SqlClient.SqlDataReader> gibt ein <xref:System.Data.SqlTypes.SqlBytes>-Objekt zurück, das eine `Stream`-Eigenschaft verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="1526a-184">The <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A> method of the <xref:System.Data.SqlClient.SqlDataReader> returns a <xref:System.Data.SqlTypes.SqlBytes> object that exposes a `Stream` property.</span></span> <span data-ttu-id="1526a-185">Der Code verwendet diese, um ein neues `Bitmap` Objekt zu erstellen, und speichert es dann in der GIF-`ImageFormat`.</span><span class="sxs-lookup"><span data-stu-id="1526a-185">The code uses this to create a new `Bitmap` object, and then saves it in the Gif `ImageFormat`.</span></span>  
  
 [!code-csharp[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/VB/source.vb#1)]  
  
## <a name="using-large-value-type-parameters"></a><span data-ttu-id="1526a-186">Verwenden großer Werttypparameter</span><span class="sxs-lookup"><span data-stu-id="1526a-186">Using Large Value Type Parameters</span></span>  
 <span data-ttu-id="1526a-187">Große Werttypen können in <xref:System.Data.SqlClient.SqlParameter>-Objekten auf dieselbe Weise verwendet werden wie kleinere Werttypen in <xref:System.Data.SqlClient.SqlParameter>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="1526a-187">Large value types can be used in <xref:System.Data.SqlClient.SqlParameter> objects the same way you use smaller value types in <xref:System.Data.SqlClient.SqlParameter> objects.</span></span> <span data-ttu-id="1526a-188">Sie können große Werttypen als <xref:System.Data.SqlClient.SqlParameter> Werte abrufen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1526a-188">You can retrieve large value types as <xref:System.Data.SqlClient.SqlParameter> values, as shown in the following example.</span></span> <span data-ttu-id="1526a-189">Im Code wird davon ausgegangen, dass in der AdventureWorks-Beispieldatenbank die folgende gespeicherte GetDocumentSummary-Prozedur vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1526a-189">The code assumes that the following GetDocumentSummary stored procedure exists in the AdventureWorks sample database.</span></span> <span data-ttu-id="1526a-190">Die gespeicherte Prozedur nimmt einen Eingabeparameter mit dem Namen @DocumentID und gibt den Inhalt der DocumentSummary-Spalte im @DocumentSummary Output-Parameter zurück.</span><span class="sxs-lookup"><span data-stu-id="1526a-190">The stored procedure takes an input parameter named @DocumentID and returns the contents of the DocumentSummary column in the @DocumentSummary output parameter.</span></span>  
  
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
  
### <a name="example"></a><span data-ttu-id="1526a-191">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1526a-191">Example</span></span>  
 <span data-ttu-id="1526a-192">Der ADO.NET-Code erstellt ein <xref:System.Data.SqlClient.SqlConnection>-Objekt und ein <xref:System.Data.SqlClient.SqlCommand>-Objekt, um die gespeicherte GetDocumentSummary-Prozedur auszuführen und die Dokumentübersicht abzurufen, die als großer Werttyp gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="1526a-192">The ADO.NET code creates <xref:System.Data.SqlClient.SqlConnection> and <xref:System.Data.SqlClient.SqlCommand> objects to execute the GetDocumentSummary stored procedure and retrieve the document summary, which is stored as a large value type.</span></span> <span data-ttu-id="1526a-193">Der Code übergibt einen Wert für den @DocumentID Eingabeparameter und zeigt die Ergebnisse an, die im @DocumentSummary Output-Parameter im Konsolenfenster zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="1526a-193">The code passes a value for the @DocumentID input parameter, and displays the results passed back in the @DocumentSummary output parameter in the Console window.</span></span>  
  
 [!code-csharp[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1526a-194">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1526a-194">See also</span></span>

- [<span data-ttu-id="1526a-195">SQL Server Binary and Large-Value Data (Binäre Daten und Daten mit umfangreichen Werten in SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1526a-195">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="1526a-196">SQL Server-Datentypzuordnungen</span><span class="sxs-lookup"><span data-stu-id="1526a-196">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="1526a-197">SQL Server Data Operations in ADO.NET (SQL Server-Datenvorgänge in ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="1526a-197">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="1526a-198">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1526a-198">ADO.NET Overview</span></span>](../ado-net-overview.md)
