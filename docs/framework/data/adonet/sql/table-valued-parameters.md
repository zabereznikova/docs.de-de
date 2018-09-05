---
title: Tabellenwertparameter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 370c16d5-db7b-43e3-945b-ccaab35b739b
ms.openlocfilehash: 333154f26a575886f19a914ce2f91beebd6be49e
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43742518"
---
# <a name="table-valued-parameters"></a><span data-ttu-id="4bcda-102">Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="4bcda-102">Table-Valued Parameters</span></span>
<span data-ttu-id="4bcda-103">Tabellenwertparameter bieten eine gute Möglichkeit, mehrere Datenzeilen aus einer Clientanwendung nach SQL Server zu marshallen, ohne dass mehrere Roundtrips oder eine besondere serverseitige Logik für die Verarbeitung der Daten notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="4bcda-103">Table-valued parameters provide an easy way to marshal multiple rows of data from a client application to SQL Server without requiring multiple round trips or special server-side logic for processing the data.</span></span> <span data-ttu-id="4bcda-104">Sie können Tabellenwertparameter verwenden, um Datenzeilen in einer Clientanwendung zu kapseln und diese Daten in einem einzelnen parametrisierten Befehl an den Server zu senden.</span><span class="sxs-lookup"><span data-stu-id="4bcda-104">You can use table-valued parameters to encapsulate rows of data in a client application and send the data to the server in a single parameterized command.</span></span> <span data-ttu-id="4bcda-105">Die eingehenden Datenzeilen werden in einer Tabellenvariablen gespeichert, die anschließend mit [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] bearbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4bcda-105">The incoming data rows are stored in a table variable that can then be operated on by using [!INCLUDE[tsql](../../../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4bcda-106">Auf Spaltenwerte in Tabellenwertparametern kann mit SELECT-Standardanweisungen in [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="4bcda-106">Column values in table-valued parameters can be accessed using standard [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] SELECT statements.</span></span> <span data-ttu-id="4bcda-107">Tabellenwertparameter sind stark typisiert, und die Überprüfung ihrer Struktur erfolgt automatisch.</span><span class="sxs-lookup"><span data-stu-id="4bcda-107">Table-valued parameters are strongly typed and their structure is automatically validated.</span></span> <span data-ttu-id="4bcda-108">Die Größe der Tabellenwertparameter wird nur vom Serverarbeitsspeicher beschränkt.</span><span class="sxs-lookup"><span data-stu-id="4bcda-108">The size of table-valued parameters is limited only by server memory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4bcda-109">Daten in einem Tabellenwertparameter können nicht zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4bcda-109">You cannot return data in a table-valued parameter.</span></span> <span data-ttu-id="4bcda-110">Tabellenwertparameter sind reine Eingabeparameter; das OUTPUT-Schlüsselwort wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4bcda-110">Table-valued parameters are input-only; the OUTPUT keyword is not supported.</span></span>  
  
 <span data-ttu-id="4bcda-111">Weitere Informationen über Tabellenwertparameter finden Sie in den folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="4bcda-111">For more information about table-valued parameters, see the following resources.</span></span>  
  
|<span data-ttu-id="4bcda-112">Ressource</span><span class="sxs-lookup"><span data-stu-id="4bcda-112">Resource</span></span>|<span data-ttu-id="4bcda-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4bcda-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="4bcda-114">[Tabellenwertparameter (Datenbankmodul)](https://go.microsoft.com/fwlink/?LinkId=98363) in SQL Server-Onlinedokumentation</span><span class="sxs-lookup"><span data-stu-id="4bcda-114">[Table-Valued Parameters (Database Engine)](https://go.microsoft.com/fwlink/?LinkId=98363) in SQL Server Books Online</span></span>|<span data-ttu-id="4bcda-115">Beschreibt das Erstellen und Verwenden von Tabellenwertparametern.</span><span class="sxs-lookup"><span data-stu-id="4bcda-115">Describes how to create and use table-valued parameters.</span></span>|  
|<span data-ttu-id="4bcda-116">[Benutzerdefinierte Tabellentypen](https://go.microsoft.com/fwlink/?LinkId=98364) in SQL Server-Onlinedokumentation</span><span class="sxs-lookup"><span data-stu-id="4bcda-116">[User-Defined Table Types](https://go.microsoft.com/fwlink/?LinkId=98364) in SQL Server Books Online</span></span>|<span data-ttu-id="4bcda-117">Beschreibt benutzerdefinierte Tabellentypen, die zum Deklarieren von Tabellenwertparametern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4bcda-117">Describes user-defined table types that are used to declare table-valued parameters.</span></span>|  
  
## <a name="passing-multiple-rows-in-previous-versions-of-sql-server"></a><span data-ttu-id="4bcda-118">Übergeben von mehreren Zeilen in älteren Versionen von SQL Server</span><span class="sxs-lookup"><span data-stu-id="4bcda-118">Passing Multiple Rows in Previous Versions of SQL Server</span></span>  
 <span data-ttu-id="4bcda-119">Bevor Sie Tabellenwertparameter in SQL Server 2008 eingeführt wurden, konnten die Optionen zum Übergeben mehrerer Datenzeilen an eine gespeicherte Prozedur oder einen parametrisierten SQL‑Befehl.</span><span class="sxs-lookup"><span data-stu-id="4bcda-119">Before table-valued parameters were introduced to SQL Server 2008, the options for passing multiple rows of data to a stored procedure or a parameterized SQL command were limited.</span></span> <span data-ttu-id="4bcda-120">Ein Entwickler konnte aus den folgenden Optionen zum Übergeben mehrerer Zeilen an den Server auswählen:</span><span class="sxs-lookup"><span data-stu-id="4bcda-120">A developer could choose from the following options for passing multiple rows to the server:</span></span>  
  
-   <span data-ttu-id="4bcda-121">Er hatte die Möglichkeit, eine Reihe einzelner Parameter zu verwenden, um die Werte in mehreren Spalten und Zeilen von Daten darzustellen.</span><span class="sxs-lookup"><span data-stu-id="4bcda-121">Use a series of individual parameters to represent the values in multiple columns and rows of data.</span></span> <span data-ttu-id="4bcda-122">Die Datenmenge, die mithilfe dieser Methode übergeben werden kann, ist durch die Anzahl der zulässigen Parameter beschränkt.</span><span class="sxs-lookup"><span data-stu-id="4bcda-122">The amount of data that can be passed by using this method is limited by the number of parameters allowed.</span></span> <span data-ttu-id="4bcda-123">SQL Server-Prozeduren können höchstens über 2100 Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="4bcda-123">SQL Server procedures can have, at most, 2100 parameters.</span></span> <span data-ttu-id="4bcda-124">Eine Zusammenstellung zur Verarbeitung dieser einzelnen Werte in einer Tabellenvariablen oder einer temporären Tabelle erfordert serverseitige Logik.</span><span class="sxs-lookup"><span data-stu-id="4bcda-124">Server-side logic is required to assemble these individual values into a table variable or a temporary table for processing.</span></span>  
  
-   <span data-ttu-id="4bcda-125">Ein Entwickler hatte weiterhin die Möglichkeit, mehrere Datenwerte in voneinander getrennten Zeichenfolgen oder in XML-Dokumenten zu bündeln und diese Textwerte anschließend an eine Prozedur oder Anweisung zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="4bcda-125">Bundle multiple data values into delimited strings or XML documents and then pass those text values to a procedure or statement.</span></span> <span data-ttu-id="4bcda-126">Bei dieser Methode muss die Prozedur oder Anweisung die erforderliche Logik zum Überprüfen der Datenstrukturen sowie zum Entbündeln der Werte beinhalten.</span><span class="sxs-lookup"><span data-stu-id="4bcda-126">This requires the procedure or statement to include the logic necessary for validating the data structures and unbundling the values.</span></span>  
  
-   <span data-ttu-id="4bcda-127">Ein Entwickler konnte weiterhin eine Reihe einzelner SQL-Datenänderungsanweisungen erstellen, die mehrere Zeilen betreffen, wie beispielsweise Anweisungen, die durch den Aufruf der `Update`-Methode eines <xref:System.Data.SqlClient.SqlDataAdapter> erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="4bcda-127">Create a series of individual SQL statements for data modifications that affect multiple rows, such as those created by calling the `Update` method of a <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span> <span data-ttu-id="4bcda-128">Die Änderungen können dabei einzeln oder in Gruppen gestapelt an den Server gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="4bcda-128">Changes can be submitted to the server individually or batched into groups.</span></span> <span data-ttu-id="4bcda-129">Jede Anweisung wird jedoch auf dem Server einzeln ausgeführt, auch wenn die Anweisungen in Stapeln übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="4bcda-129">However, even when submitted in batches that contain multiple statements, each statement is executed separately on the server.</span></span>  
  
-   <span data-ttu-id="4bcda-130">Das `bcp`-Hilfsprogramm und das <xref:System.Data.SqlClient.SqlBulkCopy>-Objekt bieten ebenfalls die Möglichkeit, mehrere Datenzeilen in eine Tabelle zu laden.</span><span class="sxs-lookup"><span data-stu-id="4bcda-130">Use the `bcp` utility program or the <xref:System.Data.SqlClient.SqlBulkCopy> object to load many rows of data into a table.</span></span> <span data-ttu-id="4bcda-131">Obwohl diese Technik sehr effizient ist, bietet sie keine Unterstützung für serverseitige Verarbeitung, wenn die Daten nicht in eine temporäre Tabelle oder Tabellenvariable geladen werden.</span><span class="sxs-lookup"><span data-stu-id="4bcda-131">Although this technique is very efficient, it does not support server-side processing unless the data is loaded into a temporary table or table variable.</span></span>  
  
## <a name="creating-table-valued-parameter-types"></a><span data-ttu-id="4bcda-132">Erstellen von Tabellenwertparameter-Typen</span><span class="sxs-lookup"><span data-stu-id="4bcda-132">Creating Table-Valued Parameter Types</span></span>  
 <span data-ttu-id="4bcda-133">Tabellenwertparameter basieren auf stark typisierten Tabellenstrukturen, die mit CREATE TYPE-Anweisungen in [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] definiert werden.</span><span class="sxs-lookup"><span data-stu-id="4bcda-133">Table-valued parameters are based on strongly-typed table structures that are defined by using [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] CREATE TYPE statements.</span></span> <span data-ttu-id="4bcda-134">Sie müssen einen Tabellentyp erstellen und die Struktur in SQL Server definieren, bevor Sie Tabellenwertparameter in Ihren Clientanwendungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4bcda-134">You have to create a table type and define the structure in SQL Server before you can use table-valued parameters in your client applications.</span></span> <span data-ttu-id="4bcda-135">Weitere Informationen zum Erstellen von Tabellentypen finden Sie unter [benutzerdefinierte Tabellentypen](https://go.microsoft.com/fwlink/?LinkID=98364) in SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="4bcda-135">For more information about creating table types, see [User-Defined Table Types](https://go.microsoft.com/fwlink/?LinkID=98364) in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="4bcda-136">Die folgende Anweisung erstellt einen Tabellentyp mit dem Namen <legacyBold>CategoryTableType</legacyBold>, der aus den Spalten <legacyBold>CategoryID</legacyBold> und <legacyBold>CategoryName</legacyBold> besteht:</span><span class="sxs-lookup"><span data-stu-id="4bcda-136">The following statement creates a table type named CategoryTableType that consists of CategoryID and CategoryName columns:</span></span>  
  
```  
CREATE TYPE dbo.CategoryTableType AS TABLE  
    ( CategoryID int, CategoryName nvarchar(50) )  
```  
  
 <span data-ttu-id="4bcda-137">Nach der Erstellung eines Tabellentyps können Tabellenwertparameter auf Grundlage dieses Typs deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="4bcda-137">After you create a table type, you can declare table-valued parameters based on that type.</span></span> <span data-ttu-id="4bcda-138">Das folgende [!INCLUDE[tsql](../../../../../includes/tsql-md.md)]-Fragment veranschaulicht, wie ein Tabellenwertparameter in der Definition einer gespeicherten Prozedur deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="4bcda-138">The following [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] fragment demonstrates how to declare a table-valued parameter in a stored procedure definition.</span></span> <span data-ttu-id="4bcda-139">Beachten Sie, dass das READONLY-Schlüsselwort zum Deklarieren eines Tabellenwertparameters erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="4bcda-139">Note that the READONLY keyword is required for declaring a table-valued parameter.</span></span>  
  
```  
CREATE PROCEDURE usp_UpdateCategories   
    (@tvpNewCategories dbo.CategoryTableType READONLY)  
```  
  
## <a name="modifying-data-with-table-valued-parameters-transact-sql"></a><span data-ttu-id="4bcda-140">Ändern von Daten mit Tabellenwertparametern (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4bcda-140">Modifying Data with Table-Valued Parameters (Transact-SQL)</span></span>  
 <span data-ttu-id="4bcda-141">Tabellenwertparameter können in mengenbasierten Datenänderungen verwendet werden, die mehrere Zeilen mit der Ausführung einer einzelnen Anweisung beeinflussen können.</span><span class="sxs-lookup"><span data-stu-id="4bcda-141">Table-valued parameters can be used in set-based data modifications that affect multiple rows by executing a single statement.</span></span> <span data-ttu-id="4bcda-142">So können Sie z. B. alle Zeilen in einem Tabellenwertparameter auswählen und diese in eine Datenbanktabelle einfügen, oder Sie können eine Updateanweisung erstellen, indem Sie einen Tabellenwertparameter mit der zu aktualisierenden Tabelle verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="4bcda-142">For example, you can select all the rows in a table-valued parameter and insert them into a database table, or you can create an update statement by joining a table-valued parameter to the table you want to update.</span></span>  
  
 <span data-ttu-id="4bcda-143">Mit der folgenden UPDATE-Anweisung in [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] wird veranschaulicht, wie ein Tabellenwertparameter durch einen Join mit der Categories-Tabelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4bcda-143">The following [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] UPDATE statement demonstrates how to use a table-valued parameter by joining it to the Categories table.</span></span> <span data-ttu-id="4bcda-144">Wenn Sie einen Tabellenwertparameter mit einem JOIN in einer FROM-Klausel verwenden, müssen Sie diesen ebenfalls mit einem Alias versehen. Dies ist im folgenden Beispiel dargestellt, in dem der Tabellenwertparameter mit dem Alias "ec" versehen ist:</span><span class="sxs-lookup"><span data-stu-id="4bcda-144">When you use a table-valued parameter with a JOIN in a FROM clause, you must also alias it, as shown here, where the table-valued parameter is aliased as "ec":</span></span>  
  
```  
UPDATE dbo.Categories  
    SET Categories.CategoryName = ec.CategoryName  
    FROM dbo.Categories INNER JOIN @tvpEditedCategories AS ec  
    ON dbo.Categories.CategoryID = ec.CategoryID;  
```  
  
 <span data-ttu-id="4bcda-145">Dieses [!INCLUDE[tsql](../../../../../includes/tsql-md.md)]-Beispiel veranschaulicht, wie Zeilen aus einem Tabellenwertparameter ausgewählt werden, um einen INSERT-Vorgang in einem einzelnen mengenbasierten Vorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4bcda-145">This [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] example demonstrates how to select rows from a table-valued parameter to perform an INSERT in a single set-based operation.</span></span>  
  
```  
INSERT INTO dbo.Categories (CategoryID, CategoryName)  
    SELECT nc.CategoryID, nc.CategoryName FROM @tvpNewCategories AS nc;  
```  
  
## <a name="limitations-of-table-valued-parameters"></a><span data-ttu-id="4bcda-146">Einschränkungen von Tabellenwertparametern</span><span class="sxs-lookup"><span data-stu-id="4bcda-146">Limitations of Table-Valued Parameters</span></span>  
 <span data-ttu-id="4bcda-147">Es gibt mehrere Einschränkungen bei Tabellenwertparametern:</span><span class="sxs-lookup"><span data-stu-id="4bcda-147">There are several limitations to table-valued parameters:</span></span>  
  
-   <span data-ttu-id="4bcda-148">Sie können keine Tabellenwertparameter zu übergeben [CLR-benutzerdefinierten Funktionen](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions).</span><span class="sxs-lookup"><span data-stu-id="4bcda-148">You cannot pass table-valued parameters to [CLR user-defined functions](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions).</span></span>  
  
-   <span data-ttu-id="4bcda-149">Tabellenwertparameter können nur zur Unterstützung von UNIQUE- und PRIMARY KEY-Einschränkungen indiziert werden.</span><span class="sxs-lookup"><span data-stu-id="4bcda-149">Table-valued parameters can only be indexed to support UNIQUE or PRIMARY KEY constraints.</span></span> <span data-ttu-id="4bcda-150">SQL Server führt keine Statistik zu Tabellenwertparametern.</span><span class="sxs-lookup"><span data-stu-id="4bcda-150">SQL Server does not maintain statistics on table-valued parameters.</span></span>  
  
-   <span data-ttu-id="4bcda-151">Tabellenwertparameter sind in [!INCLUDE[tsql](../../../../../includes/tsql-md.md)]-Code schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="4bcda-151">Table-valued parameters are read-only in [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] code.</span></span> <span data-ttu-id="4bcda-152">Die Spaltenwerte in den Zeilen eines Tabellenwertparameters können nicht aktualisiert werden, und Zeilen können nicht eingefügt oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="4bcda-152">You cannot update the column values in the rows of a table-valued parameter and you cannot insert or delete rows.</span></span> <span data-ttu-id="4bcda-153">Um die Daten zu ändern, die in einem Tabellenwertparameter an eine gespeicherte Prozedur oder eine parametrisierte Anweisung übergeben werden, müssen die Daten in eine temporäre Tabelle oder eine Tabellenvariable eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="4bcda-153">To modify the data that is passed to a stored procedure or parameterized statement in table-valued parameter, you must insert the data into a temporary table or into a table variable.</span></span>  
  
-   <span data-ttu-id="4bcda-154">Es können keine ALTER TABLE-Anweisungen zum Ändern des Entwurfs von Tabellenwertparametern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4bcda-154">You cannot use ALTER TABLE statements to modify the design of table-valued parameters.</span></span>  
  
## <a name="configuring-a-sqlparameter-example"></a><span data-ttu-id="4bcda-155">Konfigurieren eines SqlParameter-Beispiels</span><span class="sxs-lookup"><span data-stu-id="4bcda-155">Configuring a SqlParameter Example</span></span>  
 <span data-ttu-id="4bcda-156"><xref:System.Data.SqlClient> unterstützt das Auffüllen von Tabellenwertparametern aus <xref:System.Data.DataTable>, <xref:System.Data.Common.DbDataReader> oder <xref:System.Collections.Generic.IEnumerable%601>  \  <xref:Microsoft.SqlServer.Server.SqlDataRecord> Objekte.</span><span class="sxs-lookup"><span data-stu-id="4bcda-156"><xref:System.Data.SqlClient> supports populating table-valued parameters from <xref:System.Data.DataTable>, <xref:System.Data.Common.DbDataReader> or <xref:System.Collections.Generic.IEnumerable%601> \ <xref:Microsoft.SqlServer.Server.SqlDataRecord> objects.</span></span> <span data-ttu-id="4bcda-157">Mithilfe der <xref:System.Data.SqlClient.SqlParameter.TypeName%2A>-Eigenschaft eines <xref:System.Data.SqlClient.SqlParameter> muss ein Typname für den Tabellenwertparameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4bcda-157">You must specify a type name for the table-valued parameter by using the <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="4bcda-158">Der `TypeName` muss dem Namen eines kompatiblen Typs entsprechen, der zuvor auf dem Server erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4bcda-158">The `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="4bcda-159">Das folgende Codefragment zeigt, wie <xref:System.Data.SqlClient.SqlParameter> konfiguriert werden kann, um Daten einzufügen:</span><span class="sxs-lookup"><span data-stu-id="4bcda-159">The following code fragment demonstrates how to configure <xref:System.Data.SqlClient.SqlParameter> to insert data.</span></span>  
  
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
  
 <span data-ttu-id="4bcda-160">Sie können auch ein von <xref:System.Data.Common.DbDataReader> abgeleitetes Objekt verwenden, um Datenzeilen als Stream in einen Tabellenwertparameter zu übertragen. Dies ist im folgenden Fragment dargestellt:</span><span class="sxs-lookup"><span data-stu-id="4bcda-160">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter, as shown in this fragment:</span></span>  
  
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
  
## <a name="passing-a-table-valued-parameter-to-a-stored-procedure"></a><span data-ttu-id="4bcda-161">Übergeben eines Tabellenwertparameters an eine gespeicherte Prozedur</span><span class="sxs-lookup"><span data-stu-id="4bcda-161">Passing a Table-Valued Parameter to a Stored Procedure</span></span>  
 <span data-ttu-id="4bcda-162">In diesem Beispiel wird veranschaulicht, wie Daten eines Tabellenwertparameters an eine gespeicherte Prozedur übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="4bcda-162">This example demonstrates how to pass table-valued parameter data to a stored procedure.</span></span> <span data-ttu-id="4bcda-163">Der Code ruft hinzugefügte Zeilen mithilfe der <xref:System.Data.DataTable>-Methode in eine neue <xref:System.Data.DataTable.GetChanges%2A> ab.</span><span class="sxs-lookup"><span data-stu-id="4bcda-163">The code extracts added rows into a new <xref:System.Data.DataTable> by using the <xref:System.Data.DataTable.GetChanges%2A> method.</span></span> <span data-ttu-id="4bcda-164">Anschließend definiert der Code einen <xref:System.Data.SqlClient.SqlCommand>, mit dem die <xref:System.Data.SqlClient.SqlCommand.CommandType%2A>-Eigenschaft auf <xref:System.Data.CommandType.StoredProcedure> festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="4bcda-164">The code then defines a <xref:System.Data.SqlClient.SqlCommand>, setting the <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> property to <xref:System.Data.CommandType.StoredProcedure>.</span></span> <span data-ttu-id="4bcda-165">Der <xref:System.Data.SqlClient.SqlParameter> wird mit der <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A>-Methode aufgefüllt, und der <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> wird auf `Structured` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4bcda-165">The <xref:System.Data.SqlClient.SqlParameter> is populated by using the <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> method and the <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> is set to `Structured`.</span></span> <span data-ttu-id="4bcda-166">Der <xref:System.Data.SqlClient.SqlCommand> wird dann mithilfe der <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>-Methode ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4bcda-166">The <xref:System.Data.SqlClient.SqlCommand> is then executed by using the <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> method.</span></span>  
  
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
  
### <a name="passing-a-table-valued-parameter-to-a-parameterized-sql-statement"></a><span data-ttu-id="4bcda-167">Übergeben eines Tabellenwertparameters an eine parametrisierte SQL-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4bcda-167">Passing a Table-Valued Parameter to a Parameterized SQL Statement</span></span>  
 <span data-ttu-id="4bcda-168">Im folgenden Beispiel wird veranschaulicht, wie Daten unter Verwendung einer INSERT-Anweisung mit einer SELECT-Unterabfrage, die über einen Tabellenwertparameter als Datenquelle verfügt, in die <legacyBold>dbo.Categories</legacyBold>-Tabelle eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="4bcda-168">The following example demonstrates how to insert data into the dbo.Categories table by using an INSERT statement with a SELECT subquery that has a table-valued parameter as the data source.</span></span> <span data-ttu-id="4bcda-169">Beim Übergeben eines Tabellenwertparameters an eine parametrisierte SQL-Anweisung muss ein Typname für den Tabellenwertparameter angegeben werden, indem die neue <xref:System.Data.SqlClient.SqlParameter.TypeName%2A>-Eigenschaft eines <xref:System.Data.SqlClient.SqlParameter> verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4bcda-169">When passing a table-valued parameter to a parameterized SQL statement, you must specify a type name for the table-valued parameter by using the new <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="4bcda-170">Dieser `TypeName` muss dem Namen eines kompatiblen Typs entsprechen, der zuvor auf dem Server erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4bcda-170">This `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="4bcda-171">Im Code in diesem Beispiel wird die `TypeName`-Eigenschaft verwendet, um auf die in <legacyBold>dbo.CategoryTableType</legacyBold> definierte Typstruktur zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="4bcda-171">The code in this example uses the `TypeName` property to reference the type structure defined in dbo.CategoryTableType.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4bcda-172">Wenn ein Wert für eine Identitätsspalte in einem Tabellenwertparameter angegeben wird, muss die SET IDENTITY_INSERT-Anweisung für die Sitzung ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4bcda-172">If you supply a value for an identity column in a table-valued parameter, you must issue the SET IDENTITY_INSERT statement for the session.</span></span>  
  
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
  
## <a name="streaming-rows-with-a-datareader"></a><span data-ttu-id="4bcda-173">Streaming von Zeilen mit einem DataReader</span><span class="sxs-lookup"><span data-stu-id="4bcda-173">Streaming Rows with a DataReader</span></span>  
 <span data-ttu-id="4bcda-174">Sie können auch ein von <xref:System.Data.Common.DbDataReader> abgeleitetes Objekt verwenden, um Datenzeilen als Stream in einen Tabellenwertparameter zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="4bcda-174">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter.</span></span> <span data-ttu-id="4bcda-175">Im folgenden Codefragment wird veranschaulicht, wie Daten mithilfe eines <xref:System.Data.OracleClient.OracleCommand> und eines <xref:System.Data.OracleClient.OracleDataReader> aus einer Oracle-Datenbank abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4bcda-175">The following code fragment demonstrates retrieving data from an Oracle database by using an <xref:System.Data.OracleClient.OracleCommand> and an <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="4bcda-176">Im Code wird dann ein <xref:System.Data.SqlClient.SqlCommand> konfiguriert, um eine gespeicherte Prozedur mit einem einzelnen Eingabeparameter aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="4bcda-176">The code then configures a <xref:System.Data.SqlClient.SqlCommand> to invoke a stored procedure with a single input parameter.</span></span> <span data-ttu-id="4bcda-177">Die <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A>-Eigenschaft von <xref:System.Data.SqlClient.SqlParameter> wird auf `Structured` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4bcda-177">The <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> property of the <xref:System.Data.SqlClient.SqlParameter> is set to `Structured`.</span></span> <span data-ttu-id="4bcda-178">Die <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A>-Methode übergibt das `OracleDataReader`-Resultset als Tabellenwertparameter an die gespeicherte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="4bcda-178">The <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> passes the `OracleDataReader` result set to the stored procedure as a table-valued parameter.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4bcda-179">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4bcda-179">See Also</span></span>  
 [<span data-ttu-id="4bcda-180">Konfigurieren von Parametern und Parameterdatentypen</span><span class="sxs-lookup"><span data-stu-id="4bcda-180">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [<span data-ttu-id="4bcda-181">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="4bcda-181">Commands and Parameters</span></span>](../../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="4bcda-182">DataAdapter-Parameter</span><span class="sxs-lookup"><span data-stu-id="4bcda-182">DataAdapter Parameters</span></span>](../../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 [<span data-ttu-id="4bcda-183">SQL Server Data Operations in ADO.NET (SQL Server-Datenvorgänge in ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="4bcda-183">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [<span data-ttu-id="4bcda-184">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="4bcda-184">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
