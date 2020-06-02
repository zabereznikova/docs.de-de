---
title: Tabellenwertparameter
description: Erfahren Sie, wie Sie mithilfe von Tabellenwert Parametern mehrere Daten Zeilen aus einer Client Anwendung in SQL Server Mars Hallen.
ms.date: 10/12/2018
dev_langs:
- csharp
- vb
ms.assetid: 370c16d5-db7b-43e3-945b-ccaab35b739b
ms.openlocfilehash: 7b1f0a6c416f660f06cea099197ba136f84407f9
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286196"
---
# <a name="table-valued-parameters"></a><span data-ttu-id="a5319-103">Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="a5319-103">Table-Valued Parameters</span></span>
<span data-ttu-id="a5319-104">Tabellenwertparameter bieten eine einfache Möglichkeit zum Marshallen mehrerer Datenzeilen aus einer Clientanwendung nach SQL Server, ohne dass mehrere Roundtrips oder eine spezielle serverseitige Logik für die Verarbeitung der Daten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a5319-104">Table-valued parameters provide an easy way to marshal multiple rows of data from a client application to SQL Server without requiring multiple round trips or special server-side logic for processing the data.</span></span> <span data-ttu-id="a5319-105">Sie können Tabellenwertparameter verwenden, um Datenzeilen in einer Clientanwendung zu kapseln und die Daten in einem einzigen parametrisierten Befehl an den Server zu senden.</span><span class="sxs-lookup"><span data-stu-id="a5319-105">You can use table-valued parameters to encapsulate rows of data in a client application and send the data to the server in a single parameterized command.</span></span> <span data-ttu-id="a5319-106">Die eingehenden Datenzeilen werden in einer Tabellenvariablen gespeichert, die Sie dann mithilfe von Transact-SQL bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="a5319-106">The incoming data rows are stored in a table variable that can then be operated on by using Transact-SQL.</span></span>  
  
 <span data-ttu-id="a5319-107">Für den Zugriff auf Spaltenwerte in Tabellenwertparametern können Standard-SELECT-Anweisungen in Transact-SQL verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a5319-107">Column values in table-valued parameters can be accessed using standard Transact-SQL SELECT statements.</span></span> <span data-ttu-id="a5319-108">Tabellenwertparameter sind stark typisiert, und ihre Struktur wird automatisch validiert.</span><span class="sxs-lookup"><span data-stu-id="a5319-108">Table-valued parameters are strongly typed and their structure is automatically validated.</span></span> <span data-ttu-id="a5319-109">Die Größe von Tabellenwertparametern ist lediglich durch den Arbeitsspeicher des Servers beschränkt.</span><span class="sxs-lookup"><span data-stu-id="a5319-109">The size of table-valued parameters is limited only by server memory.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5319-110">In Tabellenwertparametern können keine Daten zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a5319-110">You cannot return data in a table-valued parameter.</span></span> <span data-ttu-id="a5319-111">Tabellenwertparameter sind reine Eingabeparameter. Das Schlüsselwort OUTPUT wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a5319-111">Table-valued parameters are input-only; the OUTPUT keyword is not supported.</span></span>  
  
 <span data-ttu-id="a5319-112">Weitere Informationen zu Tabellenwertparametern finden Sie in den folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="a5319-112">For more information about table-valued parameters, see the following resources.</span></span>  
  
|<span data-ttu-id="a5319-113">Resource</span><span class="sxs-lookup"><span data-stu-id="a5319-113">Resource</span></span>|<span data-ttu-id="a5319-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a5319-114">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="a5319-115">Verwenden von Tabellenwertparameter (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="a5319-115">Use Table-Valued Parameters (Database Engine)</span></span>](/sql/relational-databases/tables/use-table-valued-parameters-database-engine)|<span data-ttu-id="a5319-116">Beschreibt, wie Sie Tabellenwertparameter erstellen und verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5319-116">Describes how to create and use table-valued parameters.</span></span>|  
|<span data-ttu-id="a5319-117">[Benutzerdefinierte Tabellentypen](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="a5319-117">[User-Defined Table Types](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100))</span></span>|<span data-ttu-id="a5319-118">Beschreibt die benutzerdefinierten Tabellentypen, die zum Deklarieren von Tabellenwertparametern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a5319-118">Describes user-defined table types that are used to declare table-valued parameters.</span></span>|  
  
## <a name="passing-multiple-rows-in-previous-versions-of-sql-server"></a><span data-ttu-id="a5319-119">Übergeben von mehreren Zeilen in älteren Versionen von SQL Server</span><span class="sxs-lookup"><span data-stu-id="a5319-119">Passing Multiple Rows in Previous Versions of SQL Server</span></span>  
 <span data-ttu-id="a5319-120">Vor der Einführung von Tabellenwertparametern in SQL Server 2008 bestanden nur eingeschränkte Möglichkeiten zum Übergeben mehrerer Datenzeilen an eine gespeicherte Prozedur oder einen parametrisierten SQL-Befehl.</span><span class="sxs-lookup"><span data-stu-id="a5319-120">Before table-valued parameters were introduced to SQL Server 2008, the options for passing multiple rows of data to a stored procedure or a parameterized SQL command were limited.</span></span> <span data-ttu-id="a5319-121">Entwickler hatten folgende Möglichkeiten, um mehrere Zeilen an den Server zu übergeben:</span><span class="sxs-lookup"><span data-stu-id="a5319-121">A developer could choose from the following options for passing multiple rows to the server:</span></span>  
  
- <span data-ttu-id="a5319-122">Verwenden von mehreren Einzelparametern zur Darstellung der Werte in mehreren Datenspalten und -zeilen.</span><span class="sxs-lookup"><span data-stu-id="a5319-122">Use a series of individual parameters to represent the values in multiple columns and rows of data.</span></span> <span data-ttu-id="a5319-123">Die Menge der Daten, die mit dieser Methode übergeben werden können, ist aufgrund der maximal zulässigen Anzahl von Parametern beschränkt.</span><span class="sxs-lookup"><span data-stu-id="a5319-123">The amount of data that can be passed by using this method is limited by the number of parameters allowed.</span></span> <span data-ttu-id="a5319-124">SQL Server-Prozeduren können höchstens über 2100 Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="a5319-124">SQL Server procedures can have, at most, 2100 parameters.</span></span> <span data-ttu-id="a5319-125">Um diese Einzelwerte zur Verarbeitung in einer Tabellenvariable oder einer temporären Tabelle zusammenzusetzen, ist serverseitige Logik erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a5319-125">Server-side logic is required to assemble these individual values into a table variable or a temporary table for processing.</span></span>  
  
- <span data-ttu-id="a5319-126">Bündeln mehrerer Datenwerte in Zeichenfolgen mit Trennzeichen oder XML-Dokumenten und Übergeben dieser Textwerte an eine Prozedur oder Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a5319-126">Bundle multiple data values into delimited strings or XML documents and then pass those text values to a procedure or statement.</span></span> <span data-ttu-id="a5319-127">Bei dieser Vorgehensweise muss die Prozedur oder Anweisung die erforderliche Logik zum Überprüfen der Datenstrukturen und Entbündeln der Werte enthalten.</span><span class="sxs-lookup"><span data-stu-id="a5319-127">This requires the procedure or statement to include the logic necessary for validating the data structures and unbundling the values.</span></span>  
  
- <span data-ttu-id="a5319-128">Erstellen einer Reihe von SQL-Einzelanweisungen für Datenänderungen, die sich auf mehrere Zeilen auswirken (z.B. durch den Aufruf der `Update`-Methode einer <xref:System.Data.SqlClient.SqlDataAdapter>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="a5319-128">Create a series of individual SQL statements for data modifications that affect multiple rows, such as those created by calling the `Update` method of a <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span> <span data-ttu-id="a5319-129">Änderungen können einzeln an den Server übermittelt oder in Gruppen zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="a5319-129">Changes can be submitted to the server individually or batched into groups.</span></span> <span data-ttu-id="a5319-130">Auch wenn sie in Batches übermittelt werden, die mehrere Anweisungen enthalten, wird jede Anweisung einzeln auf dem Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a5319-130">However, even when submitted in batches that contain multiple statements, each statement is executed separately on the server.</span></span>  
  
- <span data-ttu-id="a5319-131">Verwenden des `bcp`-Hilfsprogramms oder des <xref:System.Data.SqlClient.SqlBulkCopy>-Objekts, um eine Vielzahl von Datenzeilen in eine Tabelle zu laden.</span><span class="sxs-lookup"><span data-stu-id="a5319-131">Use the `bcp` utility program or the <xref:System.Data.SqlClient.SqlBulkCopy> object to load many rows of data into a table.</span></span> <span data-ttu-id="a5319-132">Wenngleich dieses Verfahren sehr effizient ist, wird die serverseitige Verarbeitung nur dann unterstützt, wenn die Daten in eine temporäre Tabelle oder Tabellenvariable geladen werden.</span><span class="sxs-lookup"><span data-stu-id="a5319-132">Although this technique is very efficient, it does not support server-side processing unless the data is loaded into a temporary table or table variable.</span></span>  
  
## <a name="creating-table-valued-parameter-types"></a><span data-ttu-id="a5319-133">Erstellen von Tabellenwertparameter-Typen</span><span class="sxs-lookup"><span data-stu-id="a5319-133">Creating Table-Valued Parameter Types</span></span>  
 <span data-ttu-id="a5319-134">Tabellenwert Parameter basieren auf stark typisierten Tabellenstrukturen, die mithilfe von Transact-SQL-Anweisungen zum Erstellen von Typen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="a5319-134">Table-valued parameters are based on strongly typed table structures that are defined by using Transact-SQL CREATE TYPE statements.</span></span> <span data-ttu-id="a5319-135">Sie müssen einen Tabellentyp erstellen und die Struktur in SQL Server definieren, bevor Sie Tabellenwertparameter in Ihren Clientanwendungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a5319-135">You have to create a table type and define the structure in SQL Server before you can use table-valued parameters in your client applications.</span></span> <span data-ttu-id="a5319-136">Weitere Informationen zum Erstellen von Tabellentypen finden Sie unter [Benutzerdefinierte Tabellentypen](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100)).</span><span class="sxs-lookup"><span data-stu-id="a5319-136">For more information about creating table types, see [User-Defined Table Types](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100)).</span></span>  
  
 <span data-ttu-id="a5319-137">Mit der folgenden Anweisung wird ein Tabellentyp namens „CategoryTableType“ erstellt, der aus den Spalten „CategoryID“ und „CategoryName“ besteht:</span><span class="sxs-lookup"><span data-stu-id="a5319-137">The following statement creates a table type named CategoryTableType that consists of CategoryID and CategoryName columns:</span></span>  
  
```sql
CREATE TYPE dbo.CategoryTableType AS TABLE  
    ( CategoryID int, CategoryName nvarchar(50) )  
```  
  
 <span data-ttu-id="a5319-138">Nachdem Sie einen Tabellentyp erstellt haben, können Sie Tabellenwertparameter basierend auf diesem Typ deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a5319-138">After you create a table type, you can declare table-valued parameters based on that type.</span></span> <span data-ttu-id="a5319-139">Das folgende Transact-SQL-Fragment veranschaulicht, wie ein Tabellenwertparameter in der Definition einer gespeicherten Prozedur deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="a5319-139">The following Transact-SQL fragment demonstrates how to declare a table-valued parameter in a stored procedure definition.</span></span> <span data-ttu-id="a5319-140">Beachten Sie, dass das Schlüsselwort READONLY erforderlich ist, um einen Tabellenwertparameter zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a5319-140">Note that the READONLY keyword is required for declaring a table-valued parameter.</span></span>  
  
```sql
CREATE PROCEDURE usp_UpdateCategories
    (@tvpNewCategories dbo.CategoryTableType READONLY)  
```  
  
## <a name="modifying-data-with-table-valued-parameters-transact-sql"></a><span data-ttu-id="a5319-141">Ändern von Daten mit Tabellenwertparametern (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a5319-141">Modifying Data with Table-Valued Parameters (Transact-SQL)</span></span>  
 <span data-ttu-id="a5319-142">Um Tabellenwertparameter bei Datenänderungen zu verwenden, die auf Sätzen basieren und sich auf mehrere Zeilen auswirken, kann eine einzelne Anweisung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a5319-142">Table-valued parameters can be used in set-based data modifications that affect multiple rows by executing a single statement.</span></span> <span data-ttu-id="a5319-143">Beispielsweise können Sie alle Zeilen in einem Tabellenwertparameter auswählen und in eine Datenbanktabelle einfügen, oder Sie können eine update-Anweisung erstellen, indem Sie einen Tabellenwertparameter mit der Tabelle verbinden, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a5319-143">For example, you can select all the rows in a table-valued parameter and insert them into a database table, or you can create an update statement by joining a table-valued parameter to the table you want to update.</span></span>  
  
 <span data-ttu-id="a5319-144">Mit der folgenden UPDATE-Anweisung in Transact-SQL wird veranschaulicht, wie ein Tabellenwertparameter durch einen Join mit der Categories-Tabelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a5319-144">The following Transact-SQL UPDATE statement demonstrates how to use a table-valued parameter by joining it to the Categories table.</span></span> <span data-ttu-id="a5319-145">Wenn Sie einen Tabellenwertparameter mit einem JOIN in einer FROM-Klausel verwenden, müssen Sie auch einen Alias angeben, wie in diesem Beispiel gezeigt (der Alias des Tabellenwertparameters lautet „ec“):</span><span class="sxs-lookup"><span data-stu-id="a5319-145">When you use a table-valued parameter with a JOIN in a FROM clause, you must also alias it, as shown here, where the table-valued parameter is aliased as "ec":</span></span>  
  
```sql
UPDATE dbo.Categories  
    SET Categories.CategoryName = ec.CategoryName  
    FROM dbo.Categories INNER JOIN @tvpEditedCategories AS ec  
    ON dbo.Categories.CategoryID = ec.CategoryID;  
```  
  
 <span data-ttu-id="a5319-146">Dieses Transact-SQL-Beispiel veranschaulicht, wie Zeilen aus einem Tabellenwertparameter ausgewählt werden, um einen INSERT-Vorgang in einem einzelnen mengenbasierten Vorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a5319-146">This Transact-SQL example demonstrates how to select rows from a table-valued parameter to perform an INSERT in a single set-based operation.</span></span>  
  
```sql
INSERT INTO dbo.Categories (CategoryID, CategoryName)  
    SELECT nc.CategoryID, nc.CategoryName FROM @tvpNewCategories AS nc;  
```  
  
## <a name="limitations-of-table-valued-parameters"></a><span data-ttu-id="a5319-147">Einschränkungen von Tabellenwertparametern</span><span class="sxs-lookup"><span data-stu-id="a5319-147">Limitations of Table-Valued Parameters</span></span>  
 <span data-ttu-id="a5319-148">Bei Verwendung von Tabellenwertparametern müssen eine Reihe von Einschränkungen berücksichtigt werden:</span><span class="sxs-lookup"><span data-stu-id="a5319-148">There are several limitations to table-valued parameters:</span></span>  
  
- <span data-ttu-id="a5319-149">Tabellenwertparameter können nicht an [benutzerdefinierte CLR-Funktionen](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions) übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="a5319-149">You cannot pass table-valued parameters to [CLR user-defined functions](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions).</span></span>  
  
- <span data-ttu-id="a5319-150">Tabellenwertparameter können nur für die Unterstützung der UNIQUE- oder PRIMARY KEY-Einschränkungen indiziert werden.</span><span class="sxs-lookup"><span data-stu-id="a5319-150">Table-valued parameters can only be indexed to support UNIQUE or PRIMARY KEY constraints.</span></span> <span data-ttu-id="a5319-151">SQL Server verwaltet keine Statistiken für Tabellenwertparameter.</span><span class="sxs-lookup"><span data-stu-id="a5319-151">SQL Server does not maintain statistics on table-valued parameters.</span></span>  
  
- <span data-ttu-id="a5319-152">Tabellenwertparameter sind in Transact-SQL-Code schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="a5319-152">Table-valued parameters are read-only in Transact-SQL code.</span></span> <span data-ttu-id="a5319-153">Sie können die Spaltenwerte in den Zeilen eines Tabellenwertparameters nicht aktualisieren, und Sie können keine Zeilen einfügen oder löschen.</span><span class="sxs-lookup"><span data-stu-id="a5319-153">You cannot update the column values in the rows of a table-valued parameter and you cannot insert or delete rows.</span></span> <span data-ttu-id="a5319-154">Um die Daten zu ändern, die an eine gespeicherte Prozedur oder eine parametrisierte Anweisung in einem Tabellenwertparameter übergeben werden, müssen Sie die Daten in eine temporäre Tabelle oder in eine Tabellenvariable einfügen.</span><span class="sxs-lookup"><span data-stu-id="a5319-154">To modify the data that is passed to a stored procedure or parameterized statement in table-valued parameter, you must insert the data into a temporary table or into a table variable.</span></span>  
  
- <span data-ttu-id="a5319-155">Der Aufbau von Tabellenwertparametern kann nicht mithilfe von ALTER TABLE-Anweisungen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a5319-155">You cannot use ALTER TABLE statements to modify the design of table-valued parameters.</span></span>  
  
## <a name="configuring-a-sqlparameter-example"></a><span data-ttu-id="a5319-156">Konfigurieren eines SqlParameter-Beispiels</span><span class="sxs-lookup"><span data-stu-id="a5319-156">Configuring a SqlParameter Example</span></span>  
 <span data-ttu-id="a5319-157"><xref:System.Data.SqlClient> unterstützt das Auffüllen von Tabellenwertparametern aus <xref:System.Data.DataTable>-, <xref:System.Data.Common.DbDataReader>- und <xref:System.Collections.Generic.IEnumerable%601> \ <xref:Microsoft.SqlServer.Server.SqlDataRecord>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="a5319-157"><xref:System.Data.SqlClient> supports populating table-valued parameters from <xref:System.Data.DataTable>, <xref:System.Data.Common.DbDataReader> or <xref:System.Collections.Generic.IEnumerable%601> \ <xref:Microsoft.SqlServer.Server.SqlDataRecord> objects.</span></span> <span data-ttu-id="a5319-158">Sie müssen mit der <xref:System.Data.SqlClient.SqlParameter.TypeName%2A>-Eigenschaft eines <xref:System.Data.SqlClient.SqlParameter> einen Typnamen für den Tabellenwertparameter angeben.</span><span class="sxs-lookup"><span data-stu-id="a5319-158">You must specify a type name for the table-valued parameter by using the <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="a5319-159">`TypeName` muss dem Namen eines kompatiblen Typs entsprechen, der zuvor auf dem Server erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a5319-159">The `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="a5319-160">Das folgende Codefragment zeigt, wie <xref:System.Data.SqlClient.SqlParameter> für das Einfügen von Daten konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="a5319-160">The following code fragment demonstrates how to configure <xref:System.Data.SqlClient.SqlParameter> to insert data.</span></span>  

<span data-ttu-id="a5319-161">Im folgenden Beispiel enthält die Variable `addedCategories` eine <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="a5319-161">In the following example, the `addedCategories` variable contains a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="a5319-162">Weitere Informationen zum Füllen der Variable finden Sie in den Beispielen im nächsten Abschnitt [Übergeben eines Tabellenwertparameters an eine gespeicherte Prozedur](#passing).</span><span class="sxs-lookup"><span data-stu-id="a5319-162">To see how the variable is populated, see the examples in the next section, [Passing a Table-Valued Parameter to a Stored Procedure](#passing).</span></span>

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
  
 <span data-ttu-id="a5319-163">Sie können auch jedes von <xref:System.Data.Common.DbDataReader> abgeleitete Objekt verwenden, um Datenzeilen per Streaming in einen Tabellenwertparameter zu übertragen, wie im folgenden Fragment dargestellt:</span><span class="sxs-lookup"><span data-stu-id="a5319-163">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter, as shown in this fragment:</span></span>  
  
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
  
## <a name="passing-a-table-valued-parameter-to-a-stored-procedure"></a><a name="passing"></a><span data-ttu-id="a5319-164">Übergeben eines Tabellenwert Parameters an eine gespeicherte Prozedur</span><span class="sxs-lookup"><span data-stu-id="a5319-164">Passing a Table-Valued Parameter to a Stored Procedure</span></span>  
 <span data-ttu-id="a5319-165">In diesem Beispiel wird veranschaulicht, wie Daten aus Tabellenwertparametern an eine gespeicherte Prozedur übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="a5319-165">This example demonstrates how to pass table-valued parameter data to a stored procedure.</span></span> <span data-ttu-id="a5319-166">Der Code extrahiert hinzugefügte Zeilen mithilfe der <xref:System.Data.DataTable>-Methode in eine neue <xref:System.Data.DataTable.GetChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5319-166">The code extracts added rows into a new <xref:System.Data.DataTable> by using the <xref:System.Data.DataTable.GetChanges%2A> method.</span></span> <span data-ttu-id="a5319-167">Im Code wird dann ein <xref:System.Data.SqlClient.SqlCommand> definiert, wobei für die Eigenschaft <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> der Wert <xref:System.Data.CommandType.StoredProcedure> festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="a5319-167">The code then defines a <xref:System.Data.SqlClient.SqlCommand>, setting the <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> property to <xref:System.Data.CommandType.StoredProcedure>.</span></span> <span data-ttu-id="a5319-168">Der <xref:System.Data.SqlClient.SqlParameter> wird mit der <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A>-Methode aufgefüllt und für <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> wird `Structured` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a5319-168">The <xref:System.Data.SqlClient.SqlParameter> is populated by using the <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> method and the <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> is set to `Structured`.</span></span> <span data-ttu-id="a5319-169">Anschließend wird der <xref:System.Data.SqlClient.SqlCommand> mit der Methode <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a5319-169">The <xref:System.Data.SqlClient.SqlCommand> is then executed by using the <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> method.</span></span>  
  
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
  
### <a name="passing-a-table-valued-parameter-to-a-parameterized-sql-statement"></a><span data-ttu-id="a5319-170">Übergeben eines Tabellenwertparameters an eine parametrisierte SQL-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a5319-170">Passing a Table-Valued Parameter to a Parameterized SQL Statement</span></span>  
 <span data-ttu-id="a5319-171">Im folgenden Beispiel wird veranschaulicht, wie Daten in die Tabelle „dbo.Categories“ eingefügt werden. Dazu wird eine INSERT-Anweisung mit einer SELECT-Unterabfrage verwendet, die einen Tabellenwertparameter als Datenquelle nutzt.</span><span class="sxs-lookup"><span data-stu-id="a5319-171">The following example demonstrates how to insert data into the dbo.Categories table by using an INSERT statement with a SELECT subquery that has a table-valued parameter as the data source.</span></span> <span data-ttu-id="a5319-172">Wenn Sie einen Tabellenwertparameter an eine parametrisierte SQL-Anweisung übergeben, müssen Sie mithilfe der neuen Eigenschaft <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> eines <xref:System.Data.SqlClient.SqlParameter> einen Typnamen für den Tabellenwertparameter angeben.</span><span class="sxs-lookup"><span data-stu-id="a5319-172">When passing a table-valued parameter to a parameterized SQL statement, you must specify a type name for the table-valued parameter by using the new <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="a5319-173">`TypeName` muss dem Namen eines kompatiblen Typs entsprechen, der zuvor auf dem Server erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a5319-173">This `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="a5319-174">Der Code in diesem Beispiel verwendet die Eigenschaft `TypeName`, um auf die in „dbo.CategoryTableType“ definierte Typstruktur zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="a5319-174">The code in this example uses the `TypeName` property to reference the type structure defined in dbo.CategoryTableType.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5319-175">Wenn Sie einen Wert für eine Identitätsspalte in einem Tabellenwertparameter angeben, muss die SET IDENTITY_INSERT-Anweisung für die Sitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a5319-175">If you supply a value for an identity column in a table-valued parameter, you must issue the SET IDENTITY_INSERT statement for the session.</span></span>  
  
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
  
## <a name="streaming-rows-with-a-datareader"></a><span data-ttu-id="a5319-176">Streaming von Zeilen mit einem DataReader</span><span class="sxs-lookup"><span data-stu-id="a5319-176">Streaming Rows with a DataReader</span></span>  
 <span data-ttu-id="a5319-177">Sie können auch jedes von <xref:System.Data.Common.DbDataReader> abgeleitete Objekt verwenden, um Datenzeilen per Streaming in einen Tabellenwertparameter zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="a5319-177">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter.</span></span> <span data-ttu-id="a5319-178">Das folgende Codefragment zeigt, wie Daten mithilfe von <xref:System.Data.OracleClient.OracleCommand> und <xref:System.Data.OracleClient.OracleDataReader> aus einer Oracle-Datenbank abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a5319-178">The following code fragment demonstrates retrieving data from an Oracle database by using an <xref:System.Data.OracleClient.OracleCommand> and an <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="a5319-179">Anschließend wird mit dem Code ein <xref:System.Data.SqlClient.SqlCommand> konfiguriert, um eine gespeicherte Prozedur mit einem einzigen Eingabeparameter aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="a5319-179">The code then configures a <xref:System.Data.SqlClient.SqlCommand> to invoke a stored procedure with a single input parameter.</span></span> <span data-ttu-id="a5319-180">Für die Eigenschaft <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> des <xref:System.Data.SqlClient.SqlParameter> wird der Wert `Structured` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a5319-180">The <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> property of the <xref:System.Data.SqlClient.SqlParameter> is set to `Structured`.</span></span> <span data-ttu-id="a5319-181">Mithilfe von <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> wird das Resultset `OracleDataReader` als Tabellenwertparameter an die gespeicherte Prozedur übergeben.</span><span class="sxs-lookup"><span data-stu-id="a5319-181">The <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> passes the `OracleDataReader` result set to the stored procedure as a table-valued parameter.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a5319-182">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5319-182">See also</span></span>

- [<span data-ttu-id="a5319-183">Konfigurieren von Parametern und Parameterdatentypen</span><span class="sxs-lookup"><span data-stu-id="a5319-183">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="a5319-184">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="a5319-184">Commands and Parameters</span></span>](../commands-and-parameters.md)
- [<span data-ttu-id="a5319-185">DataAdapter-Parameter</span><span class="sxs-lookup"><span data-stu-id="a5319-185">DataAdapter Parameters</span></span>](../dataadapter-parameters.md)
- [<span data-ttu-id="a5319-186">SQL Server von Daten Vorgängen in ADO.net</span><span class="sxs-lookup"><span data-stu-id="a5319-186">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="a5319-187">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a5319-187">ADO.NET Overview</span></span>](../ado-net-overview.md)
