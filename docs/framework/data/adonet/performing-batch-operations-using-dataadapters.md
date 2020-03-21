---
title: Ausführen von Batchvorgängen mit "DataAdapters"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e72ed5af-b24f-486c-8429-c8fd2208f844
ms.openlocfilehash: 62a61051e5b9d896f8a89ed3d2745859fc07a7ec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149257"
---
# <a name="performing-batch-operations-using-dataadapters"></a><span data-ttu-id="907e7-102">Ausführen von Batchvorgängen mit "DataAdapters"</span><span class="sxs-lookup"><span data-stu-id="907e7-102">Performing Batch Operations Using DataAdapters</span></span>
<span data-ttu-id="907e7-103">Durch Batch-Unterstützung in ADO.NET kann ein <xref:System.Data.Common.DataAdapter> die Operationen INSERT, UPDATE und DELETE aus einem <xref:System.Data.DataSet> oder einer <xref:System.Data.DataTable> an einen Server zusammenfassen, anstatt nur jeweils eine Operation senden zu können.</span><span class="sxs-lookup"><span data-stu-id="907e7-103">Batch support in ADO.NET allows a <xref:System.Data.Common.DataAdapter> to group INSERT, UPDATE, and DELETE operations from a <xref:System.Data.DataSet> or <xref:System.Data.DataTable> to the server, instead of sending one operation at a time.</span></span> <span data-ttu-id="907e7-104">Durch das Reduzieren der Anzahl von Roundtrips zum Server kann im Allgemeinen die Leistung beträchtlich gesteigert werden.</span><span class="sxs-lookup"><span data-stu-id="907e7-104">The reduction in the number of round trips to the server typically results in significant performance gains.</span></span> <span data-ttu-id="907e7-105">Batchupdates werden für die .NET-Datenanbieter für SQL Server (<xref:System.Data.SqlClient>) und Oracle (<xref:System.Data.OracleClient>) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="907e7-105">Batch updates are supported for the .NET data providers for SQL Server (<xref:System.Data.SqlClient>) and Oracle (<xref:System.Data.OracleClient>).</span></span>  
  
 <span data-ttu-id="907e7-106">Beim Aktualisieren einer Datenbank mit Änderungen aus einem <xref:System.Data.DataSet> wurde die Datenbank in früheren Versionen von ADO.NET mit der `Update`-Methode eines `DataAdapter` zeilenweise aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="907e7-106">When updating a database with changes from a <xref:System.Data.DataSet> in previous versions of ADO.NET, the `Update` method of a `DataAdapter` performed updates to the database one row at a time.</span></span> <span data-ttu-id="907e7-107">Dabei wurden die Zeilen in der angegebenen <xref:System.Data.DataTable> durchlaufen, wobei jede <xref:System.Data.DataRow> auf Änderungen geprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="907e7-107">As it iterated through the rows in the specified <xref:System.Data.DataTable>, it examined each <xref:System.Data.DataRow> to see if it had been modified.</span></span> <span data-ttu-id="907e7-108">Wenn die Zeile geändert worden war, wurde, abhängig vom Wert der `UpdateCommand`-Eigenschaft für die Zeile, der entsprechende `InsertCommand`, `DeleteCommand` oder <xref:System.Data.DataRow.RowState%2A> aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="907e7-108">If the row had been modified, it called the appropriate `UpdateCommand`, `InsertCommand`, or `DeleteCommand`, depending on the value of the <xref:System.Data.DataRow.RowState%2A> property for that row.</span></span> <span data-ttu-id="907e7-109">Für jede Zeilenaktualisierung war ein Netzwerkroundtrip zur Datenbank erforderlich.</span><span class="sxs-lookup"><span data-stu-id="907e7-109">Every row update involved a network round-trip to the database.</span></span>  
  
 <span data-ttu-id="907e7-110">Beginnend mit ADO.NET 2.0 wird vom <xref:System.Data.Common.DbDataAdapter>-Objekt eine <xref:System.Data.Common.DbDataAdapter.UpdateBatchSize%2A>-Eigenschaft verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="907e7-110">Starting with ADO.NET 2.0, the <xref:System.Data.Common.DbDataAdapter> exposes an <xref:System.Data.Common.DbDataAdapter.UpdateBatchSize%2A> property.</span></span> <span data-ttu-id="907e7-111">Wenn die `UpdateBatchSize`-Eigenschaft auf einen positiven ganzzahligen Wert festgelegt wird, werden Updates der Datenbank als Batches mit der angegebenen Größe gesendet.</span><span class="sxs-lookup"><span data-stu-id="907e7-111">Setting the `UpdateBatchSize` to a positive integer value causes updates to the database to be sent as batches of the specified size.</span></span> <span data-ttu-id="907e7-112">Wenn z. B. für `UpdateBatchSize` der Wert 10 festgelegt wird, bedeutet dies, dass jeweils 10 Anweisungen in einer Gruppe zusammengefasst und zusammen als Batch gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="907e7-112">For example, setting the `UpdateBatchSize` to 10 will group 10 separate statements and submit them as single batch.</span></span> <span data-ttu-id="907e7-113">Wird dagegen für `UpdateBatchSize` 0 festgelegt, verwendet der <xref:System.Data.Common.DataAdapter> die größtmöglichen Batches, die der Server unterstützt.</span><span class="sxs-lookup"><span data-stu-id="907e7-113">Setting the `UpdateBatchSize` to 0 will cause the <xref:System.Data.Common.DataAdapter> to use the largest batch size that the server can handle.</span></span> <span data-ttu-id="907e7-114">Bei einem Wert von 1 werden Batchupdates deaktiviert, weil die Zeilen einzeln nacheinander gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="907e7-114">Setting it to 1 disables batch updates, as rows are sent one at a time.</span></span>  
  
 <span data-ttu-id="907e7-115">Die Ausführung eines extrem großen Batches könnte die Leistung verringern.</span><span class="sxs-lookup"><span data-stu-id="907e7-115">Executing an extremely large batch could decrease performance.</span></span> <span data-ttu-id="907e7-116">Daher sollten Sie die Einstellung für eine optimale Batchgröße vor der Implementierung Ihrer Anwendung austesten.</span><span class="sxs-lookup"><span data-stu-id="907e7-116">Therefore, you should test for the optimum batch size setting before implementing your application.</span></span>  
  
## <a name="using-the-updatebatchsize-property"></a><span data-ttu-id="907e7-117">Verwenden der "UpdateBatchSize"-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="907e7-117">Using the UpdateBatchSize Property</span></span>  
 <span data-ttu-id="907e7-118">Wenn Batchupdates aktiviert sind, sollte der <xref:System.Data.IDbCommand.UpdatedRowSource%2A>-Eigenschaftswert von `UpdateCommand`, `InsertCommand` und `DeleteCommand` des DataAdapter auf <xref:System.Data.UpdateRowSource.None> oder <xref:System.Data.UpdateRowSource.OutputParameters> festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="907e7-118">When batch updates are enabled, the <xref:System.Data.IDbCommand.UpdatedRowSource%2A> property value of the DataAdapter's `UpdateCommand`, `InsertCommand`, and `DeleteCommand` should be set to <xref:System.Data.UpdateRowSource.None> or <xref:System.Data.UpdateRowSource.OutputParameters>.</span></span> <span data-ttu-id="907e7-119">Beim Update eines Batches sind der <xref:System.Data.IDbCommand.UpdatedRowSource%2A>-Wert und der <xref:System.Data.UpdateRowSource.FirstReturnedRecord>-Wert der <xref:System.Data.UpdateRowSource.Both>-Eigenschaft des Befehls ungültig.</span><span class="sxs-lookup"><span data-stu-id="907e7-119">When performing a batch update, the command's <xref:System.Data.IDbCommand.UpdatedRowSource%2A> property value of <xref:System.Data.UpdateRowSource.FirstReturnedRecord> or <xref:System.Data.UpdateRowSource.Both> is invalid.</span></span>  
  
 <span data-ttu-id="907e7-120">In der folgenden Prozedur wird die Verwendung der `UpdateBatchSize`-Eigenschaft veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="907e7-120">The following procedure demonstrates the use of the `UpdateBatchSize` property.</span></span> <span data-ttu-id="907e7-121">Die Prozedur verwendet zwei <xref:System.Data.DataSet> Argumente, ein Objekt mit Spalten, die die Felder **ProductCategoryID** und **Name** in der Tabelle **Production.ProductCategory** darstellen, und eine ganze Zahl, die die Batchgröße darstellt (die Anzahl der Zeilen im Batch).</span><span class="sxs-lookup"><span data-stu-id="907e7-121">The procedure takes two arguments, a <xref:System.Data.DataSet> object that has columns representing the **ProductCategoryID** and **Name** fields in the **Production.ProductCategory** table, and an integer representing the batch size (the number of rows in the batch).</span></span> <span data-ttu-id="907e7-122">Der Code erstellt ein neues <xref:System.Data.SqlClient.SqlDataAdapter>-Objekt und legt dessen Eigenschaften <xref:System.Data.SqlClient.SqlDataAdapter.UpdateCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> und <xref:System.Data.SqlClient.SqlDataAdapter.DeleteCommand%2A> fest.</span><span class="sxs-lookup"><span data-stu-id="907e7-122">The code creates a new <xref:System.Data.SqlClient.SqlDataAdapter> object, setting its <xref:System.Data.SqlClient.SqlDataAdapter.UpdateCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A>, and <xref:System.Data.SqlClient.SqlDataAdapter.DeleteCommand%2A> properties.</span></span> <span data-ttu-id="907e7-123">Der Code geht davon aus, dass das <xref:System.Data.DataSet>-Objekt geänderte Zeilen aufweist.</span><span class="sxs-lookup"><span data-stu-id="907e7-123">The code assumes that the <xref:System.Data.DataSet> object has modified rows.</span></span> <span data-ttu-id="907e7-124">Er legt einen Wert für die `UpdateBatchSize`-Eigenschaft fest und führt das Update aus.</span><span class="sxs-lookup"><span data-stu-id="907e7-124">It sets the `UpdateBatchSize` property and executes the update.</span></span>  
  
```vb  
Public Sub BatchUpdate( _  
  ByVal dataTable As DataTable, ByVal batchSize As Int32)  
    ' Assumes GetConnectionString() returns a valid connection string.  
    Dim connectionString As String = GetConnectionString()  
  
    ' Connect to the AdventureWorks database.  
    Using connection As New SqlConnection(connectionString)  
        ' Create a SqlDataAdapter.  
        Dim adapter As New SqlDataAdapter()  
  
        'Set the UPDATE command and parameters.  
        adapter.UpdateCommand = New SqlCommand( _  
          "UPDATE Production.ProductCategory SET " _  
          & "Name=@Name WHERE ProductCategoryID=@ProdCatID;", _  
          connection)  
        adapter.UpdateCommand.Parameters.Add("@Name", _  
          SqlDbType.NVarChar, 50, "Name")  
        adapter.UpdateCommand.Parameters.Add("@ProdCatID",  _  
          SqlDbType.Int, 4, " ProductCategoryID ")  
        adapter.UpdateCommand.UpdatedRowSource = _  
          UpdateRowSource.None  
  
        'Set the INSERT command and parameter.  
        adapter.InsertCommand = New SqlCommand( _  
          "INSERT INTO Production.ProductCategory (Name) VALUES (@Name);", _  
  connection)  
        adapter.InsertCommand.Parameters.Add("@Name", _  
          SqlDbType.NVarChar, 50, "Name")  
        adapter.InsertCommand.UpdatedRowSource = _  
          UpdateRowSource.None  
  
        'Set the DELETE command and parameter.  
        adapter.DeleteCommand = New SqlCommand( _  
          "DELETE FROM Production.ProductCategory " _  
          & "WHERE ProductCategoryID=@ProdCatID;", connection)  
        adapter.DeleteCommand.Parameters.Add("@ProdCatID", _  
           SqlDbType.Int, 4, " ProductCategoryID ")  
        adapter.DeleteCommand.UpdatedRowSource = UpdateRowSource.None  
  
        ' Set the batch size.  
        adapter.UpdateBatchSize = batchSize  
  
        ' Execute the update.  
        adapter.Update(dataTable)  
    End Using  
End Sub  
```  
  
```csharp  
public static void BatchUpdate(DataTable dataTable,Int32 batchSize)  
{  
    // Assumes GetConnectionString() returns a valid connection string.  
    string connectionString = GetConnectionString();  
  
    // Connect to the AdventureWorks database.  
    using (SqlConnection connection = new
      SqlConnection(connectionString))  
    {  
  
        // Create a SqlDataAdapter.  
        SqlDataAdapter adapter = new SqlDataAdapter();  
  
        // Set the UPDATE command and parameters.  
        adapter.UpdateCommand = new SqlCommand(  
            "UPDATE Production.ProductCategory SET "  
            + "Name=@Name WHERE ProductCategoryID=@ProdCatID;",
            connection);  
        adapter.UpdateCommand.Parameters.Add("@Name",
           SqlDbType.NVarChar, 50, "Name");  
        adapter.UpdateCommand.Parameters.Add("@ProdCatID",
           SqlDbType.Int, 4, "ProductCategoryID");  
         adapter.UpdateCommand.UpdatedRowSource = UpdateRowSource.None;  
  
        // Set the INSERT command and parameter.  
        adapter.InsertCommand = new SqlCommand(  
            "INSERT INTO Production.ProductCategory (Name) VALUES (@Name);",
            connection);  
        adapter.InsertCommand.Parameters.Add("@Name",
          SqlDbType.NVarChar, 50, "Name");  
        adapter.InsertCommand.UpdatedRowSource = UpdateRowSource.None;  
  
        // Set the DELETE command and parameter.  
        adapter.DeleteCommand = new SqlCommand(  
            "DELETE FROM Production.ProductCategory "  
            + "WHERE ProductCategoryID=@ProdCatID;", connection);  
        adapter.DeleteCommand.Parameters.Add("@ProdCatID",
          SqlDbType.Int, 4, "ProductCategoryID");  
        adapter.DeleteCommand.UpdatedRowSource = UpdateRowSource.None;  
  
        // Set the batch size.  
        adapter.UpdateBatchSize = batchSize;  
  
        // Execute the update.  
        adapter.Update(dataTable);  
    }  
}  
```  
  
## <a name="handling-batch-update-related-events-and-errors"></a><span data-ttu-id="907e7-125">Behandeln von Ereignissen und Fehlern im Zusammenhang mit dem Batchupdate</span><span class="sxs-lookup"><span data-stu-id="907e7-125">Handling Batch Update-Related Events and Errors</span></span>  
 <span data-ttu-id="907e7-126">**Der DataAdapter** hat zwei updatebezogene Ereignisse: **RowUpdating** und **RowUpdated**.</span><span class="sxs-lookup"><span data-stu-id="907e7-126">The **DataAdapter** has two update-related events: **RowUpdating** and **RowUpdated**.</span></span> <span data-ttu-id="907e7-127">In älteren Versionen von ADO.NET werden diese Ereignisse jeweils einmal für jede verarbeitete Zeile generiert, wenn die Batchverarbeitung deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="907e7-127">In previous versions of ADO.NET, when batch processing is disabled, each of these events is generated once for each row processed.</span></span> <span data-ttu-id="907e7-128">**RowUpdating** wird generiert, bevor die Aktualisierung erfolgt, und **RowUpdated** wird generiert, nachdem die Datenbankaktualisierung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="907e7-128">**RowUpdating** is generated before the update occurs, and **RowUpdated** is generated after the database update has been completed.</span></span>  
  
### <a name="event-behavior-changes-with-batch-updates"></a><span data-ttu-id="907e7-129">Änderungen im Ereignisverhalten durch Batchupdates</span><span class="sxs-lookup"><span data-stu-id="907e7-129">Event Behavior Changes with Batch Updates</span></span>  
 <span data-ttu-id="907e7-130">Bei aktivierter Batchverarbeitung werden mehrere Zeilen in einer einzigen Datenbankoperation aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="907e7-130">When batch processing is enabled, multiple rows are updated in a single database operation.</span></span> <span data-ttu-id="907e7-131">Deshalb findet pro Batch nur ein `RowUpdated`-Ereignis statt, wohingegen das `RowUpdating`-Ereignis für jede verarbeitete Zeile auftritt.</span><span class="sxs-lookup"><span data-stu-id="907e7-131">Therefore, only one `RowUpdated` event occurs for each batch, whereas the `RowUpdating` event occurs for each row processed.</span></span> <span data-ttu-id="907e7-132">Bei deaktivierter Batchverarbeitung werden die beiden Ereignisse mit Einzelverschachtelung ausgelöst, wobei für jede Zeile zunächst ein `RowUpdating`-Ereignis und dann ein `RowUpdated`-Ereignis ausgelöst wird. Diese Abfolge der Auslösung von `RowUpdating`-Ereignissen und `RowUpdated`-Ereignissen setzt sich so lange fort, bis alle Zeilen verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="907e7-132">When batch processing is disabled, the two events are fired with one-to-one interleaving, where one `RowUpdating` event and one `RowUpdated` event fire for a row, and then one `RowUpdating` and one `RowUpdated` event fire for the next row, until all of the rows are processed.</span></span>  
  
### <a name="accessing-updated-rows"></a><span data-ttu-id="907e7-133">Zugreifen auf aktualisierte Zeilen</span><span class="sxs-lookup"><span data-stu-id="907e7-133">Accessing Updated Rows</span></span>  
 <span data-ttu-id="907e7-134">Bei deaktivierter Batchverarbeitung kann auf die zu aktualisierende Zeile mit der <xref:System.Data.Common.RowUpdatedEventArgs.Row%2A>-Eigenschaft der <xref:System.Data.Common.RowUpdatedEventArgs>-Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="907e7-134">When batch processing is disabled, the row being updated can be accessed using the <xref:System.Data.Common.RowUpdatedEventArgs.Row%2A> property of the <xref:System.Data.Common.RowUpdatedEventArgs> class.</span></span>  
  
 <span data-ttu-id="907e7-135">Bei aktivierter Batchverarbeitung wird für mehrere Zeilen ein einziges `RowUpdated`-Ereignis generiert.</span><span class="sxs-lookup"><span data-stu-id="907e7-135">When batch processing is enabled, a single `RowUpdated` event is generated for multiple rows.</span></span> <span data-ttu-id="907e7-136">Daher ist der Wert der `Row`-Eigenschaft  in jeder Zeile NULL.</span><span class="sxs-lookup"><span data-stu-id="907e7-136">Therefore, the value of the `Row` property for each row is null.</span></span> <span data-ttu-id="907e7-137">Es werden weiterhin `RowUpdating`-Ereignisse für jede Zeile generiert.</span><span class="sxs-lookup"><span data-stu-id="907e7-137">`RowUpdating` events are still generated for each row.</span></span> <span data-ttu-id="907e7-138">Mit der <xref:System.Data.Common.RowUpdatedEventArgs.CopyToRows%2A>-Methode der <xref:System.Data.Common.RowUpdatedEventArgs>-Klasse können Sie auf die verarbeiteten Zeilen zugreifen, indem Sie Verweise auf die Zeilen in ein Array kopieren.</span><span class="sxs-lookup"><span data-stu-id="907e7-138">The <xref:System.Data.Common.RowUpdatedEventArgs.CopyToRows%2A> method of the <xref:System.Data.Common.RowUpdatedEventArgs> class allows you to access the processed rows by copying references to the rows into an array.</span></span> <span data-ttu-id="907e7-139">Wenn keine Zeilen verarbeitet werden, löst `CopyToRows` eine <xref:System.ArgumentNullException> aus.</span><span class="sxs-lookup"><span data-stu-id="907e7-139">If no rows are being processed, `CopyToRows` throws an <xref:System.ArgumentNullException>.</span></span> <span data-ttu-id="907e7-140">Verwenden Sie die <xref:System.Data.Common.RowUpdatedEventArgs.RowCount%2A>-Eigenschaft, um vor dem Aufruf der <xref:System.Data.Common.RowUpdatedEventArgs.CopyToRows%2A>-Methode die Anzahl der verarbeiteten Zeilen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="907e7-140">Use the <xref:System.Data.Common.RowUpdatedEventArgs.RowCount%2A> property to return the number of rows processed before calling the <xref:System.Data.Common.RowUpdatedEventArgs.CopyToRows%2A> method.</span></span>  
  
### <a name="handling-data-errors"></a><span data-ttu-id="907e7-141">Behandeln von Datenfehlern</span><span class="sxs-lookup"><span data-stu-id="907e7-141">Handling Data Errors</span></span>  
 <span data-ttu-id="907e7-142">Eine Batchausführung hat dieselben Auswirkungen wie die Ausführung einzelner Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="907e7-142">Batch execution has the same effect as the execution of each individual statement.</span></span> <span data-ttu-id="907e7-143">Anweisungen werden in der Reihenfolge ausgeführt, in der sie dem Batch hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="907e7-143">Statements are executed in the order that the statements were added to the batch.</span></span> <span data-ttu-id="907e7-144">Fehler werden im Batchmodus in derselben Weise behandelt wie bei deaktiviertem Batchmodus.</span><span class="sxs-lookup"><span data-stu-id="907e7-144">Errors are handled the same way in batch mode as they are when batch mode is disabled.</span></span> <span data-ttu-id="907e7-145">Jede Zeile wird einzeln verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="907e7-145">Each row is processed separately.</span></span> <span data-ttu-id="907e7-146">Nur Zeilen, die erfolgreich in der Datenbank verarbeitet wurden, werden in der entsprechenden <xref:System.Data.DataRow> innerhalb der <xref:System.Data.DataTable> aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="907e7-146">Only rows that have been successfully processed in the database will be updated in the corresponding <xref:System.Data.DataRow> within the <xref:System.Data.DataTable>.</span></span>  
  
 <span data-ttu-id="907e7-147">Der Datenanbieter und der Back-End-Datenbankserver bestimmen, welche SQL-Konstrukte für die Batchausführung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="907e7-147">The data provider and the back-end database server determine which SQL constructs are supported for batch execution.</span></span> <span data-ttu-id="907e7-148">Wenn eine nicht unterstützte Anweisung ausgeführt werden soll, wird möglicherweise eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="907e7-148">An exception may be thrown if a non-supported statement is submitted for execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="907e7-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="907e7-149">See also</span></span>

- [<span data-ttu-id="907e7-150">DataAdapters und DataReaders</span><span class="sxs-lookup"><span data-stu-id="907e7-150">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="907e7-151">Updating Data Sources with DataAdapters (Aktualisieren von Datenquellen mit DataAdapters)</span><span class="sxs-lookup"><span data-stu-id="907e7-151">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="907e7-152">Behandeln von DataAdapter-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="907e7-152">Handling DataAdapter Events</span></span>](handling-dataadapter-events.md)
- [<span data-ttu-id="907e7-153">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="907e7-153">ADO.NET Overview</span></span>](ado-net-overview.md)
