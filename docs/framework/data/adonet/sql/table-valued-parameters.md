---
title: Tabellenwertparameter
ms.date: 10/12/2018
dev_langs:
- csharp
- vb
ms.assetid: 370c16d5-db7b-43e3-945b-ccaab35b739b
ms.openlocfilehash: d99cea1641dc61c1cae6d6b1634359211ce788ae
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452304"
---
# <a name="table-valued-parameters"></a><span data-ttu-id="1cd5f-102">Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="1cd5f-102">Table-Valued Parameters</span></span>
<span data-ttu-id="1cd5f-103">Tabellenwertparameter bieten eine einfache Möglichkeit zum Marshallen mehrerer Datenzeilen aus einer Clientanwendung nach SQL Server, ohne dass mehrere Roundtrips oder eine spezielle serverseitige Logik für die Verarbeitung der Daten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-103">Table-valued parameters provide an easy way to marshal multiple rows of data from a client application to SQL Server without requiring multiple round trips or special server-side logic for processing the data.</span></span> <span data-ttu-id="1cd5f-104">Sie können Tabellenwertparameter verwenden, um Datenzeilen in einer Clientanwendung zu kapseln und die Daten in einem einzigen parametrisierten Befehl an den Server zu senden.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-104">You can use table-valued parameters to encapsulate rows of data in a client application and send the data to the server in a single parameterized command.</span></span> <span data-ttu-id="1cd5f-105">Die eingehenden Datenzeilen werden in einer Tabellenvariablen gespeichert, die anschließend mit Transact-SQL verarbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-105">The incoming data rows are stored in a table variable that can then be operated on by using Transact-SQL.</span></span>  
  
 <span data-ttu-id="1cd5f-106">Für den Zugriff auf Spaltenwerte in Tabellenwertparametern können Standard-SELECT-Anweisungen in Transact-SQL verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-106">Column values in table-valued parameters can be accessed using standard Transact-SQL SELECT statements.</span></span> <span data-ttu-id="1cd5f-107">Tabellenwertparameter sind stark typisiert, und ihre Struktur wird automatisch validiert.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-107">Table-valued parameters are strongly typed and their structure is automatically validated.</span></span> <span data-ttu-id="1cd5f-108">Die Größe der Tabellenwertparameter wird nur vom Serverarbeitsspeicher beschränkt.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-108">The size of table-valued parameters is limited only by server memory.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1cd5f-109">Daten in einem Tabellenwertparameter können nicht zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-109">You cannot return data in a table-valued parameter.</span></span> <span data-ttu-id="1cd5f-110">Tabellenwertparameter sind reine Eingabeparameter; das OUTPUT-Schlüsselwort wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-110">Table-valued parameters are input-only; the OUTPUT keyword is not supported.</span></span>  
  
 <span data-ttu-id="1cd5f-111">Weitere Informationen über Tabellenwertparameter finden Sie in den folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-111">For more information about table-valued parameters, see the following resources.</span></span>  
  
|<span data-ttu-id="1cd5f-112">Ressource</span><span class="sxs-lookup"><span data-stu-id="1cd5f-112">Resource</span></span>|<span data-ttu-id="1cd5f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1cd5f-113">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="1cd5f-114">Verwenden von Tabellenwertparameter (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="1cd5f-114">Use Table-Valued Parameters (Database Engine)</span></span>](/sql/relational-databases/tables/use-table-valued-parameters-database-engine)|<span data-ttu-id="1cd5f-115">Beschreibt das Erstellen und Verwenden von Tabellenwertparametern.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-115">Describes how to create and use table-valued parameters.</span></span>|  
|<span data-ttu-id="1cd5f-116">[Benutzerdefinierte Tabellentypen](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="1cd5f-116">[User-Defined Table Types](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100))</span></span>|<span data-ttu-id="1cd5f-117">Beschreibt die benutzerdefinierten Tabellentypen, die zum Deklarieren von Tabellenwertparametern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-117">Describes user-defined table types that are used to declare table-valued parameters.</span></span>|  
  
## <a name="passing-multiple-rows-in-previous-versions-of-sql-server"></a><span data-ttu-id="1cd5f-118">Übergeben von mehreren Zeilen in älteren Versionen von SQL Server</span><span class="sxs-lookup"><span data-stu-id="1cd5f-118">Passing Multiple Rows in Previous Versions of SQL Server</span></span>  
 <span data-ttu-id="1cd5f-119">Vor der Einführung von Tabellenwertparametern in SQL Server 2008 bestanden nur eingeschränkte Möglichkeiten zum Übergeben mehrerer Datenzeilen an eine gespeicherte Prozedur oder einen parametrisierten SQL-Befehl.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-119">Before table-valued parameters were introduced to SQL Server 2008, the options for passing multiple rows of data to a stored procedure or a parameterized SQL command were limited.</span></span> <span data-ttu-id="1cd5f-120">Ein Entwickler konnte aus den folgenden Optionen zum Übergeben mehrerer Zeilen an den Server auswählen:</span><span class="sxs-lookup"><span data-stu-id="1cd5f-120">A developer could choose from the following options for passing multiple rows to the server:</span></span>  
  
- <span data-ttu-id="1cd5f-121">Er hatte die Möglichkeit, eine Reihe einzelner Parameter zu verwenden, um die Werte in mehreren Spalten und Zeilen von Daten darzustellen.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-121">Use a series of individual parameters to represent the values in multiple columns and rows of data.</span></span> <span data-ttu-id="1cd5f-122">Die Datenmenge, die mithilfe dieser Methode übergeben werden kann, ist durch die Anzahl der zulässigen Parameter beschränkt.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-122">The amount of data that can be passed by using this method is limited by the number of parameters allowed.</span></span> <span data-ttu-id="1cd5f-123">SQL Server-Prozeduren können höchstens über 2100 Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-123">SQL Server procedures can have, at most, 2100 parameters.</span></span> <span data-ttu-id="1cd5f-124">Eine Zusammenstellung zur Verarbeitung dieser einzelnen Werte in einer Tabellenvariablen oder einer temporären Tabelle erfordert serverseitige Logik.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-124">Server-side logic is required to assemble these individual values into a table variable or a temporary table for processing.</span></span>  
  
- <span data-ttu-id="1cd5f-125">Ein Entwickler hatte weiterhin die Möglichkeit, mehrere Datenwerte in voneinander getrennten Zeichenfolgen oder in XML-Dokumenten zu bündeln und diese Textwerte anschließend an eine Prozedur oder Anweisung zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-125">Bundle multiple data values into delimited strings or XML documents and then pass those text values to a procedure or statement.</span></span> <span data-ttu-id="1cd5f-126">Bei dieser Methode muss die Prozedur oder Anweisung die erforderliche Logik zum Überprüfen der Datenstrukturen sowie zum Entbündeln der Werte beinhalten.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-126">This requires the procedure or statement to include the logic necessary for validating the data structures and unbundling the values.</span></span>  
  
- <span data-ttu-id="1cd5f-127">Ein Entwickler konnte weiterhin eine Reihe einzelner SQL-Datenänderungsanweisungen erstellen, die mehrere Zeilen betreffen, wie beispielsweise Anweisungen, die durch den Aufruf der `Update`-Methode eines <xref:System.Data.SqlClient.SqlDataAdapter> erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-127">Create a series of individual SQL statements for data modifications that affect multiple rows, such as those created by calling the `Update` method of a <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span> <span data-ttu-id="1cd5f-128">Die Änderungen können dabei einzeln oder in Gruppen gestapelt an den Server gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-128">Changes can be submitted to the server individually or batched into groups.</span></span> <span data-ttu-id="1cd5f-129">Jede Anweisung wird jedoch auf dem Server einzeln ausgeführt, auch wenn die Anweisungen in Stapeln übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-129">However, even when submitted in batches that contain multiple statements, each statement is executed separately on the server.</span></span>  
  
- <span data-ttu-id="1cd5f-130">Das `bcp`-Hilfsprogramm und das <xref:System.Data.SqlClient.SqlBulkCopy>-Objekt bieten ebenfalls die Möglichkeit, mehrere Datenzeilen in eine Tabelle zu laden.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-130">Use the `bcp` utility program or the <xref:System.Data.SqlClient.SqlBulkCopy> object to load many rows of data into a table.</span></span> <span data-ttu-id="1cd5f-131">Obwohl diese Technik sehr effizient ist, bietet sie keine Unterstützung für serverseitige Verarbeitung, wenn die Daten nicht in eine temporäre Tabelle oder Tabellenvariable geladen werden.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-131">Although this technique is very efficient, it does not support server-side processing unless the data is loaded into a temporary table or table variable.</span></span>  
  
## <a name="creating-table-valued-parameter-types"></a><span data-ttu-id="1cd5f-132">Erstellen von Tabellenwertparameter-Typen</span><span class="sxs-lookup"><span data-stu-id="1cd5f-132">Creating Table-Valued Parameter Types</span></span>  
 <span data-ttu-id="1cd5f-133">Tabellenwertparameter basieren auf stark typisierten Tabellenstrukturen, die mit CREATE TYPE-Anweisungen in Transact-SQL definiert werden.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-133">Table-valued parameters are based on strongly-typed table structures that are defined by using Transact-SQL CREATE TYPE statements.</span></span> <span data-ttu-id="1cd5f-134">Sie müssen einen Tabellentyp erstellen und die Struktur in SQL Server definieren, bevor Sie Tabellenwertparameter in Ihren Clientanwendungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-134">You have to create a table type and define the structure in SQL Server before you can use table-valued parameters in your client applications.</span></span> <span data-ttu-id="1cd5f-135">Weitere Informationen zum Erstellen von Tabellentypen finden Sie unter [Benutzerdefinierte Tabellentypen](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100)).</span><span class="sxs-lookup"><span data-stu-id="1cd5f-135">For more information about creating table types, see [User-Defined Table Types](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100)).</span></span>  
  
 <span data-ttu-id="1cd5f-136">Die folgende Anweisung erstellt einen Tabellentyp mit dem Namen &lt;legacyBold&gt;CategoryTableType&lt;/legacyBold&gt;, der aus den Spalten &lt;legacyBold&gt;CategoryID&lt;/legacyBold&gt; und &lt;legacyBold&gt;CategoryName&lt;/legacyBold&gt; besteht:</span><span class="sxs-lookup"><span data-stu-id="1cd5f-136">The following statement creates a table type named CategoryTableType that consists of CategoryID and CategoryName columns:</span></span>  
  
```sql
CREATE TYPE dbo.CategoryTableType AS TABLE  
    ( CategoryID int, CategoryName nvarchar(50) )  
```  
  
 <span data-ttu-id="1cd5f-137">Nach der Erstellung eines Tabellentyps können Tabellenwertparameter auf Grundlage dieses Typs deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-137">After you create a table type, you can declare table-valued parameters based on that type.</span></span> <span data-ttu-id="1cd5f-138">Das folgende Transact-SQL-Fragment veranschaulicht, wie ein Tabellenwertparameter in der Definition einer gespeicherten Prozedur deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-138">The following Transact-SQL fragment demonstrates how to declare a table-valued parameter in a stored procedure definition.</span></span> <span data-ttu-id="1cd5f-139">Beachten Sie, dass das READONLY-Schlüsselwort zum Deklarieren eines Tabellenwertparameters erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-139">Note that the READONLY keyword is required for declaring a table-valued parameter.</span></span>  
  
```sql
CREATE PROCEDURE usp_UpdateCategories   
    (@tvpNewCategories dbo.CategoryTableType READONLY)  
```  
  
## <a name="modifying-data-with-table-valued-parameters-transact-sql"></a><span data-ttu-id="1cd5f-140">Ändern von Daten mit Tabellenwertparametern (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1cd5f-140">Modifying Data with Table-Valued Parameters (Transact-SQL)</span></span>  
 <span data-ttu-id="1cd5f-141">Tabellenwertparameter können in mengenbasierten Datenänderungen verwendet werden, die mehrere Zeilen mit der Ausführung einer einzelnen Anweisung beeinflussen können.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-141">Table-valued parameters can be used in set-based data modifications that affect multiple rows by executing a single statement.</span></span> <span data-ttu-id="1cd5f-142">So können Sie z. B. alle Zeilen in einem Tabellenwertparameter auswählen und diese in eine Datenbanktabelle einfügen, oder Sie können eine Updateanweisung erstellen, indem Sie einen Tabellenwertparameter mit der zu aktualisierenden Tabelle verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-142">For example, you can select all the rows in a table-valued parameter and insert them into a database table, or you can create an update statement by joining a table-valued parameter to the table you want to update.</span></span>  
  
 <span data-ttu-id="1cd5f-143">Mit der folgenden UPDATE-Anweisung in Transact-SQL wird veranschaulicht, wie ein Tabellenwertparameter durch einen Join mit der Categories-Tabelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-143">The following Transact-SQL UPDATE statement demonstrates how to use a table-valued parameter by joining it to the Categories table.</span></span> <span data-ttu-id="1cd5f-144">Wenn Sie einen Tabellenwertparameter mit einem JOIN in einer FROM-Klausel verwenden, müssen Sie diesen ebenfalls mit einem Alias versehen. Dies ist im folgenden Beispiel dargestellt, in dem der Tabellenwertparameter mit dem Alias "ec" versehen ist:</span><span class="sxs-lookup"><span data-stu-id="1cd5f-144">When you use a table-valued parameter with a JOIN in a FROM clause, you must also alias it, as shown here, where the table-valued parameter is aliased as "ec":</span></span>  
  
```sql
UPDATE dbo.Categories  
    SET Categories.CategoryName = ec.CategoryName  
    FROM dbo.Categories INNER JOIN @tvpEditedCategories AS ec  
    ON dbo.Categories.CategoryID = ec.CategoryID;  
```  
  
 <span data-ttu-id="1cd5f-145">Dieses Transact-SQL-Beispiel veranschaulicht, wie Zeilen aus einem Tabellenwertparameter ausgewählt werden, um einen INSERT-Vorgang in einem einzelnen mengenbasierten Vorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-145">This Transact-SQL example demonstrates how to select rows from a table-valued parameter to perform an INSERT in a single set-based operation.</span></span>  
  
```sql
INSERT INTO dbo.Categories (CategoryID, CategoryName)  
    SELECT nc.CategoryID, nc.CategoryName FROM @tvpNewCategories AS nc;  
```  
  
## <a name="limitations-of-table-valued-parameters"></a><span data-ttu-id="1cd5f-146">Einschränkungen von Tabellenwertparametern</span><span class="sxs-lookup"><span data-stu-id="1cd5f-146">Limitations of Table-Valued Parameters</span></span>  
 <span data-ttu-id="1cd5f-147">Es gibt mehrere Einschränkungen bei Tabellenwertparametern:</span><span class="sxs-lookup"><span data-stu-id="1cd5f-147">There are several limitations to table-valued parameters:</span></span>  
  
- <span data-ttu-id="1cd5f-148">Tabellenwertparameter können nicht an [benutzerdefinierte CLR-Funktionen](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions) übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-148">You cannot pass table-valued parameters to [CLR user-defined functions](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions).</span></span>  
  
- <span data-ttu-id="1cd5f-149">Tabellenwertparameter können nur zur Unterstützung von UNIQUE- und PRIMARY KEY-Einschränkungen indiziert werden.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-149">Table-valued parameters can only be indexed to support UNIQUE or PRIMARY KEY constraints.</span></span> <span data-ttu-id="1cd5f-150">SQL Server verwaltet keine Statistiken für Tabellenwertparameter.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-150">SQL Server does not maintain statistics on table-valued parameters.</span></span>  
  
- <span data-ttu-id="1cd5f-151">Tabellenwertparameter sind in Transact-SQL-Code schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-151">Table-valued parameters are read-only in Transact-SQL code.</span></span> <span data-ttu-id="1cd5f-152">Die Spaltenwerte in den Zeilen eines Tabellenwertparameters können nicht aktualisiert werden, und Zeilen können nicht eingefügt oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-152">You cannot update the column values in the rows of a table-valued parameter and you cannot insert or delete rows.</span></span> <span data-ttu-id="1cd5f-153">Um die Daten zu ändern, die in einem Tabellenwertparameter an eine gespeicherte Prozedur oder eine parametrisierte Anweisung übergeben werden, müssen die Daten in eine temporäre Tabelle oder eine Tabellenvariable eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-153">To modify the data that is passed to a stored procedure or parameterized statement in table-valued parameter, you must insert the data into a temporary table or into a table variable.</span></span>  
  
- <span data-ttu-id="1cd5f-154">Es können keine ALTER TABLE-Anweisungen zum Ändern des Entwurfs von Tabellenwertparametern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-154">You cannot use ALTER TABLE statements to modify the design of table-valued parameters.</span></span>  
  
## <a name="configuring-a-sqlparameter-example"></a><span data-ttu-id="1cd5f-155">Konfigurieren eines SqlParameter-Beispiels</span><span class="sxs-lookup"><span data-stu-id="1cd5f-155">Configuring a SqlParameter Example</span></span>  
 <span data-ttu-id="1cd5f-156"><xref:System.Data.SqlClient> unterstützt das Auffüllen von Tabellenwertparametern aus <xref:System.Data.DataTable>-, <xref:System.Data.Common.DbDataReader>- und <xref:System.Collections.Generic.IEnumerable%601> \ <xref:Microsoft.SqlServer.Server.SqlDataRecord>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-156"><xref:System.Data.SqlClient> supports populating table-valued parameters from <xref:System.Data.DataTable>, <xref:System.Data.Common.DbDataReader> or <xref:System.Collections.Generic.IEnumerable%601> \ <xref:Microsoft.SqlServer.Server.SqlDataRecord> objects.</span></span> <span data-ttu-id="1cd5f-157">Sie müssen mit der <xref:System.Data.SqlClient.SqlParameter.TypeName%2A>-Eigenschaft eines <xref:System.Data.SqlClient.SqlParameter> einen Typnamen für den Tabellenwertparameter angeben.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-157">You must specify a type name for the table-valued parameter by using the <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="1cd5f-158">Der `TypeName` muss dem Namen eines kompatiblen Typs entsprechen, der zuvor auf dem Server erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-158">The `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="1cd5f-159">Das folgende Codefragment zeigt, wie <xref:System.Data.SqlClient.SqlParameter> konfiguriert werden kann, um Daten einzufügen:</span><span class="sxs-lookup"><span data-stu-id="1cd5f-159">The following code fragment demonstrates how to configure <xref:System.Data.SqlClient.SqlParameter> to insert data.</span></span>  
 
<span data-ttu-id="1cd5f-160">Im folgenden Beispiel enthält die Variable `addedCategories` eine <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-160">In the following example, the `addedCategories` variable contains a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="1cd5f-161">Informationen zum Füllen der Variablen finden Sie in den Beispielen im nächsten Abschnitt [übergeben eines Tabellenwert Parameters an eine gespeicherte Prozedur](#passing).</span><span class="sxs-lookup"><span data-stu-id="1cd5f-161">To see how the variable is populated, see the examples in the next section, [Passing a Table-Valued Parameter to a Stored Procedure](#passing).</span></span>

```csharp  
// Configure the command and parameter.  
SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
tvpParam.SqlDbType = SqlDbType.Structured;  
tvpParam.TypeName = "dbo.CategoryTableType";  
```  
  
```vb  
' Configure the command and parameter.  
Dim insertCommand As New SqlCommand(sqlInsert, connection)  
Dim tvpParam As SqlParameter = _  
   insertCommand.Parameters.AddWithValue( _  
  "@tvpNewCategories", addedCategories)  
tvpParam.SqlDbType = SqlDbType.Structured  
tvpParam.TypeName = "dbo.CategoryTableType"  
```  
  
 <span data-ttu-id="1cd5f-162">Sie können auch jedes von <xref:System.Data.Common.DbDataReader> abgeleitete Objekt verwenden, um Datenzeilen per Streaming in einen Tabellenwertparameter zu übertragen, wie im folgenden Fragment dargestellt:</span><span class="sxs-lookup"><span data-stu-id="1cd5f-162">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter, as shown in this fragment:</span></span>  
  
```csharp  
// Configure the SqlCommand and table-valued parameter.  
SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
insertCommand.CommandType = CommandType.StoredProcedure;  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", dataReader);  
tvpParam.SqlDbType = SqlDbType.Structured;  
```  
  
```vb  
' Configure the SqlCommand and table-valued parameter.  
Dim insertCommand As New SqlCommand("usp_InsertCategories", connection)  
insertCommand.CommandType = CommandType.StoredProcedure  
Dim tvpParam As SqlParameter = _  
  insertCommand.Parameters.AddWithValue("@tvpNewCategories", _  
  dataReader)  
tvpParam.SqlDbType = SqlDbType.Structured  
```  
  
## <a name="passing"></a><span data-ttu-id="1cd5f-163">Übergeben eines Tabellenwert Parameters an eine gespeicherte Prozedur</span><span class="sxs-lookup"><span data-stu-id="1cd5f-163">Passing a Table-Valued Parameter to a Stored Procedure</span></span>  
 <span data-ttu-id="1cd5f-164">In diesem Beispiel wird veranschaulicht, wie Daten eines Tabellenwertparameters an eine gespeicherte Prozedur übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-164">This example demonstrates how to pass table-valued parameter data to a stored procedure.</span></span> <span data-ttu-id="1cd5f-165">Der Code ruft hinzugefügte Zeilen mithilfe der <xref:System.Data.DataTable>-Methode in eine neue <xref:System.Data.DataTable.GetChanges%2A> ab.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-165">The code extracts added rows into a new <xref:System.Data.DataTable> by using the <xref:System.Data.DataTable.GetChanges%2A> method.</span></span> <span data-ttu-id="1cd5f-166">Anschließend definiert der Code einen <xref:System.Data.SqlClient.SqlCommand>, mit dem die <xref:System.Data.SqlClient.SqlCommand.CommandType%2A>-Eigenschaft auf <xref:System.Data.CommandType.StoredProcedure> festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-166">The code then defines a <xref:System.Data.SqlClient.SqlCommand>, setting the <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> property to <xref:System.Data.CommandType.StoredProcedure>.</span></span> <span data-ttu-id="1cd5f-167">Der <xref:System.Data.SqlClient.SqlParameter> wird mit der <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A>-Methode aufgefüllt, und der <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> wird auf `Structured` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-167">The <xref:System.Data.SqlClient.SqlParameter> is populated by using the <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> method and the <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> is set to `Structured`.</span></span> <span data-ttu-id="1cd5f-168">Der <xref:System.Data.SqlClient.SqlCommand> wird dann mithilfe der <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>-Methode ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-168">The <xref:System.Data.SqlClient.SqlCommand> is then executed by using the <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> method.</span></span>  
  
```csharp  
// Assumes connection is an open SqlConnection object.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Configure the SqlCommand and SqlParameter.  
  SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
  insertCommand.CommandType = CommandType.StoredProcedure;  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
```vb  
' Assumes connection is an open SqlConnection object.  
Using connection  
   '  Create a DataTable with the modified rows.  
   Dim addedCategories As DataTable = _  
     CategoriesDataTable.GetChanges(DataRowState.Added)  
  
  ' Configure the SqlCommand and SqlParameter.  
   Dim insertCommand As New SqlCommand( _  
     "usp_InsertCategories", connection)  
   insertCommand.CommandType = CommandType.StoredProcedure  
   Dim tvpParam As SqlParameter = _  
     insertCommand.Parameters.AddWithValue( _  
     "@tvpNewCategories", addedCategories)  
   tvpParam.SqlDbType = SqlDbType.Structured  
  
   '  Execute the command.  
   insertCommand.ExecuteNonQuery()  
End Using  
```  
  
### <a name="passing-a-table-valued-parameter-to-a-parameterized-sql-statement"></a><span data-ttu-id="1cd5f-169">Übergeben eines Tabellenwertparameters an eine parametrisierte SQL-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1cd5f-169">Passing a Table-Valued Parameter to a Parameterized SQL Statement</span></span>  
 <span data-ttu-id="1cd5f-170">Im folgenden Beispiel wird veranschaulicht, wie Daten unter Verwendung einer INSERT-Anweisung mit einer SELECT-Unterabfrage, die über einen Tabellenwertparameter als Datenquelle verfügt, in die {1}dbo.Categories{2}-Tabelle eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-170">The following example demonstrates how to insert data into the dbo.Categories table by using an INSERT statement with a SELECT subquery that has a table-valued parameter as the data source.</span></span> <span data-ttu-id="1cd5f-171">Beim Übergeben eines Tabellenwertparameters an eine parametrisierte SQL-Anweisung muss ein Typname für den Tabellenwertparameter angegeben werden, indem die neue <xref:System.Data.SqlClient.SqlParameter.TypeName%2A>-Eigenschaft eines <xref:System.Data.SqlClient.SqlParameter> verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-171">When passing a table-valued parameter to a parameterized SQL statement, you must specify a type name for the table-valued parameter by using the new <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="1cd5f-172">Dieser `TypeName` muss dem Namen eines kompatiblen Typs entsprechen, der zuvor auf dem Server erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-172">This `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="1cd5f-173">Im Code in diesem Beispiel wird die `TypeName`-Eigenschaft verwendet, um auf die in &lt;legacyBold&gt;dbo.CategoryTableType&lt;/legacyBold&gt; definierte Typstruktur zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-173">The code in this example uses the `TypeName` property to reference the type structure defined in dbo.CategoryTableType.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1cd5f-174">Wenn ein Wert für eine Identitätsspalte in einem Tabellenwertparameter angegeben wird, muss die SET IDENTITY_INSERT-Anweisung für die Sitzung ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-174">If you supply a value for an identity column in a table-valued parameter, you must issue the SET IDENTITY_INSERT statement for the session.</span></span>  
  
```csharp  
// Assumes connection is an open SqlConnection.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Define the INSERT-SELECT statement.  
  string sqlInsert =   
      "INSERT INTO dbo.Categories (CategoryID, CategoryName)"  
      + " SELECT nc.CategoryID, nc.CategoryName"  
      + " FROM @tvpNewCategories AS nc;"  

  // Configure the command and parameter.  
  SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  
  tvpParam.TypeName = "dbo.CategoryTableType";  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
```vb  
' Assumes connection is an open SqlConnection.  
Using connection  
  ' Create a DataTable with the modified rows.  
  Dim addedCategories As DataTable = _  
    CategoriesDataTable.GetChanges(DataRowState.Added)  
  
  ' Define the INSERT-SELECT statement.  
  Dim sqlInsert As String = _  
  "INSERT INTO dbo.Categories (CategoryID, CategoryName)" _  
  & " SELECT nc.CategoryID, nc.CategoryName" _  
  & " FROM @tvpNewCategories AS nc;"  
  
  ' Configure the command and parameter.  
  Dim insertCommand As New SqlCommand(sqlInsert, connection)  
  Dim tvpParam As SqlParameter = _  
     insertCommand.Parameters.AddWithValue( _  
    "@tvpNewCategories", addedCategories)  
  tvpParam.SqlDbType = SqlDbType.Structured  
  tvpParam.TypeName = "dbo.CategoryTableType"  
  
  ' Execute the query  
  insertCommand.ExecuteNonQuery()  
End Using  
```  
  
## <a name="streaming-rows-with-a-datareader"></a><span data-ttu-id="1cd5f-175">Streaming von Zeilen mit einem DataReader</span><span class="sxs-lookup"><span data-stu-id="1cd5f-175">Streaming Rows with a DataReader</span></span>  
 <span data-ttu-id="1cd5f-176">Sie können auch jedes von <xref:System.Data.Common.DbDataReader> abgeleitete Objekt verwenden, um Datenzeilen per Streaming in einen Tabellenwertparameter zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-176">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter.</span></span> <span data-ttu-id="1cd5f-177">Im folgenden Codefragment wird veranschaulicht, wie Daten mithilfe eines <xref:System.Data.OracleClient.OracleCommand> und eines <xref:System.Data.OracleClient.OracleDataReader> aus einer Oracle-Datenbank abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-177">The following code fragment demonstrates retrieving data from an Oracle database by using an <xref:System.Data.OracleClient.OracleCommand> and an <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="1cd5f-178">Im Code wird dann ein <xref:System.Data.SqlClient.SqlCommand> konfiguriert, um eine gespeicherte Prozedur mit einem einzelnen Eingabeparameter aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-178">The code then configures a <xref:System.Data.SqlClient.SqlCommand> to invoke a stored procedure with a single input parameter.</span></span> <span data-ttu-id="1cd5f-179">Die <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A>-Eigenschaft von <xref:System.Data.SqlClient.SqlParameter> wird auf `Structured` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-179">The <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> property of the <xref:System.Data.SqlClient.SqlParameter> is set to `Structured`.</span></span> <span data-ttu-id="1cd5f-180">Die <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A>-Methode übergibt das `OracleDataReader`-Resultset als Tabellenwertparameter an die gespeicherte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="1cd5f-180">The <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> passes the `OracleDataReader` result set to the stored procedure as a table-valued parameter.</span></span>  
  
```csharp  
// Assumes connection is an open SqlConnection.  
// Retrieve data from Oracle.  
OracleCommand selectCommand = new OracleCommand(  
   "Select CategoryID, CategoryName FROM Categories;",  
   oracleConnection);  
OracleDataReader oracleReader = selectCommand.ExecuteReader(  
   CommandBehavior.CloseConnection);  
  
 // Configure the SqlCommand and table-valued parameter.  
 SqlCommand insertCommand = new SqlCommand(  
   "usp_InsertCategories", connection);  
 insertCommand.CommandType = CommandType.StoredProcedure;  
 SqlParameter tvpParam =  
    insertCommand.Parameters.AddWithValue(  
    "@tvpNewCategories", oracleReader);  
 tvpParam.SqlDbType = SqlDbType.Structured;  
  
 // Execute the command.  
 insertCommand.ExecuteNonQuery();  
```  
  
```vb  
' Assumes connection is an open SqlConnection.  
' Retrieve data from Oracle.  
Dim selectCommand As New OracleCommand( _  
  "Select CategoryID, CategoryName FROM Categories;", _  
  oracleConnection)  
Dim oracleReader As OracleDataReader = _  
  selectCommand.ExecuteReader(CommandBehavior.CloseConnection)  
  
' Configure SqlCommand and table-valued parameter.  
Dim insertCommand As New SqlCommand("usp_InsertCategories", connection)  
insertCommand.CommandType = CommandType.StoredProcedure  
Dim tvpParam As SqlParameter = _  
  insertCommand.Parameters.AddWithValue("@tvpNewCategories", _  
  oracleReader)  
tvpParam.SqlDbType = SqlDbType.Structured  
  
' Execute the command.  
insertCommand.ExecuteNonQuery()  
```  
  
## <a name="see-also"></a><span data-ttu-id="1cd5f-181">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1cd5f-181">See also</span></span>

- [<span data-ttu-id="1cd5f-182">Konfigurieren von Parametern und Parameterdatentypen</span><span class="sxs-lookup"><span data-stu-id="1cd5f-182">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="1cd5f-183">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="1cd5f-183">Commands and Parameters</span></span>](../commands-and-parameters.md)
- [<span data-ttu-id="1cd5f-184">DataAdapter-Parameter</span><span class="sxs-lookup"><span data-stu-id="1cd5f-184">DataAdapter Parameters</span></span>](../dataadapter-parameters.md)
- [<span data-ttu-id="1cd5f-185">SQL Server Data Operations in ADO.NET (SQL Server-Datenvorgänge in ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="1cd5f-185">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="1cd5f-186">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1cd5f-186">ADO.NET Overview</span></span>](../ado-net-overview.md)
