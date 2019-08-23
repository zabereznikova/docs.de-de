---
title: Abrufen von Daten mit "DataReader"
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 561ebd7ac6948fa42f73ebb4f1eb97c574e6d7e7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963188"
---
# <a name="retrieve-data-using-a-datareader"></a><span data-ttu-id="96c65-102">Abrufen von Daten mit einem DataReader</span><span class="sxs-lookup"><span data-stu-id="96c65-102">Retrieve data using a DataReader</span></span>
<span data-ttu-id="96c65-103">Erstellen Sie zum Abrufen von Daten mithilfe eines **DataReader**-Objekts eine Instanz des **Befehls** Objekts, und erstellen Sie dann einen **DataReader** , indem Sie **Command. ExecuteReader** aufrufen, um Zeilen aus einer Datenquelle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="96c65-103">To retrieve data using a **DataReader**, create an instance of the **Command** object, and then create a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="96c65-104">Das **DataReader** -Objekt stellt einen nicht gepufferten Datenstrom bereit, der prozeduralen Logik die effiziente Verarbeitung von Ergebnissen aus einer Datenquelle in sequenziell ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="96c65-104">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="96c65-105">Der **DataReader** ist eine gute Wahl, wenn Sie große Datenmengen abrufen, da die Daten nicht im Arbeitsspeicher zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="96c65-105">The **DataReader** is a good choice when you're retrieving large amounts of data because the data is not cached in memory.</span></span>

<span data-ttu-id="96c65-106">Das folgende Beispiel veranschaulicht die Verwendung eines **DataReader**, `reader` wobei einen gültigen DataReader darstellt `command` und ein gültiges Befehls Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="96c65-106">The following example illustrates using a **DataReader**, where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

<span data-ttu-id="96c65-107">Verwenden Sie die **DataReader. Read** -Methode, um eine Zeile aus den Abfrage Ergebnissen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="96c65-107">Use the **DataReader.Read** method to obtain a row from the query results.</span></span> <span data-ttu-id="96c65-108">Sie können auf jede Spalte der zurückgegebenen Zeile zugreifen, indem Sie den Namen oder die Ordinalzahl der Spalte an den **DataReader**übergeben.</span><span class="sxs-lookup"><span data-stu-id="96c65-108">You can access each column of the returned row by passing the name or ordinal number of the column to the **DataReader**.</span></span> <span data-ttu-id="96c65-109">Um die bestmögliche Leistung zu erzielen, stellt der **DataReader** eine Reihe von Methoden bereit, mit denen Sie auf Spaltenwerte in ihren systemeigenen Datentypen (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**usw.) zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="96c65-109">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="96c65-110">Eine Liste der typisierten Accessormethoden für Datenanbieter spezifische **DataReaders**finden <xref:System.Data.OleDb.OleDbDataReader> Sie unter und <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="96c65-110">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="96c65-111">Wenn Sie die typisierten Accessormethoden verwenden, wenn Sie wissen, dass der zugrunde liegende Datentyp beim Abrufen des Spaltenwerts die erforderliche Typkonvertierung reduziert.</span><span class="sxs-lookup"><span data-stu-id="96c65-111">Using the typed accessor methods when you know the underlying data type reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
 <span data-ttu-id="96c65-112">Im folgenden Beispiel wird ein **DataReader** -Objekt durchlaufen, und es werden zwei Spalten aus jeder Zeile zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="96c65-112">The following example iterates through a **DataReader** object and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="96c65-113">Schließen des "DataReader"</span><span class="sxs-lookup"><span data-stu-id="96c65-113">Closing the DataReader</span></span>  
 <span data-ttu-id="96c65-114">Verwenden Sie immer die **Close** -Methode, wenn Sie das **DataReader** -Objekt nicht mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="96c65-114">Always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="96c65-115">Wenn der **Befehl** Ausgabeparameter oder Rückgabewerte enthält, sind diese Werte erst nach dem Schließen des **DataReader** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="96c65-115">If your **Command** contains output parameters or return values, those values are not available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="96c65-116">Während ein **DataReader** geöffnet ist, wird die **Verbindung** exklusiv von diesem **DataReader**verwendet.</span><span class="sxs-lookup"><span data-stu-id="96c65-116">While a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="96c65-117">Sie können keine Befehle für die **Verbindung**ausführen, einschließlich der Erstellung eines anderen **DataReader**, bis der ursprüngliche **DataReader** geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="96c65-117">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="96c65-118">Führen Sie in der **Finalize** -Methode der Klasse nicht **Close** oder verwerfen für eine **Verbindung**, einen **DataReader**oder ein anderes verwaltetes Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="96c65-118">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="96c65-119">Geben Sie in einer Finalize-Methode nur nicht verwaltete Ressourcen frei, die der Klasse direkt gehören.</span><span class="sxs-lookup"><span data-stu-id="96c65-119">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="96c65-120">Wenn Ihre Klasse keine nicht verwalteten Ressourcen besitzt, schließen Sie keine **Finalize** -Methode in die Klassendefinition ein.</span><span class="sxs-lookup"><span data-stu-id="96c65-120">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="96c65-121">Weitere Informationen finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="96c65-121">For more information, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="96c65-122">Abrufen mehrerer Resultsets mithilfe von NextResult</span><span class="sxs-lookup"><span data-stu-id="96c65-122">Retrieving multiple result sets using NextResult</span></span>  
 <span data-ttu-id="96c65-123">Wenn das **DataReader** -Objekt mehrere Resultsets zurückgibt, wird die **NextResult** -Methode aufgerufen, um die Resultsets sequenziell zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="96c65-123">If the **DataReader** returns multiple result sets, call the **NextResult** method to iterate through the result sets sequentially.</span></span> <span data-ttu-id="96c65-124">Im folgenden Beispiel werden die Ergebnisse von zwei SELECT-Anweisungen mit der <xref:System.Data.SqlClient.SqlDataReader>-Methode von <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="96c65-124">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="96c65-125">Erhalten von Schema Informationen aus dem DataReader</span><span class="sxs-lookup"><span data-stu-id="96c65-125">Getting schema information from the DataReader</span></span>  
 <span data-ttu-id="96c65-126">Während ein **DataReader** geöffnet ist, können Sie Schema Informationen über das aktuelle Resultset mithilfe der **getschembare** -Methode abrufen.</span><span class="sxs-lookup"><span data-stu-id="96c65-126">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="96c65-127">**Getschemabel** gibt ein <xref:System.Data.DataTable> -Objekt zurück, das mit Zeilen und Spalten aufgefüllt ist, die die Schema Informationen für das aktuelle Resultset enthalten.</span><span class="sxs-lookup"><span data-stu-id="96c65-127">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="96c65-128">Die **Daten** Tabelle enthält eine Zeile für jede Spalte des Resultsets.</span><span class="sxs-lookup"><span data-stu-id="96c65-128">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="96c65-129">Jede Spalte der Schema Tabelle ist einer Eigenschaft der Spalten zugeordnet, die in den Zeilen des Resultsets zurückgegeben werden, wobei **ColumnName** der Name der Eigenschaft und der Wert der Spalte der Wert der Eigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="96c65-129">Each column of the schema table maps to a property of the columns returned in the rows of the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="96c65-130">Im folgenden Beispiel werden die Schema Informationen für **DataReader**geschrieben.</span><span class="sxs-lookup"><span data-stu-id="96c65-130">The following example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="96c65-131">Arbeiten mit OLE DB Kapiteln</span><span class="sxs-lookup"><span data-stu-id="96c65-131">Working with OLE DB chapters</span></span>  
 <span data-ttu-id="96c65-132">Hierarchische Rowsets oder Kapitel (OLE DB Type **DBTYPE_HCHAPTER**, ADO Type **adChapter**) können mithilfe von <xref:System.Data.OleDb.OleDbDataReader>abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="96c65-132">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**), can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="96c65-133">Wenn eine Abfrage, die ein Kapitel enthält, als **DataReader**zurückgegeben wird, wird das Kapitel als Spalte in diesem **DataReader** zurückgegeben und als **DataReader** -Objekt verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="96c65-133">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="96c65-134">Das ADO.net- **DataSet** kann auch verwendet werden, um hierarchische Rowsets mithilfe von über-und untergeordneten Beziehungen zwischen Tabellen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="96c65-134">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets by using parent-child relationships between tables.</span></span> <span data-ttu-id="96c65-135">Weitere Informationen finden Sie unter [Datasets, DataTables und DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span><span class="sxs-lookup"><span data-stu-id="96c65-135">For more information, see [DataSets, DataTables, and DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="96c65-136">Im folgenden Codebeispiel wird mit dem MSDataShape-Anbieter eine Kapitelspalte mit Bestellungen für jeden Kunden in einer Kundenliste generiert.</span><span class="sxs-lookup"><span data-stu-id="96c65-136">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" &
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind")

    Using custCMD As OleDbCommand = New OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " &
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " &
        "RELATE CustomerID TO CustomerID)", connection)

        connection.Open()

        Using custReader As OleDbDataReader = custCMD.ExecuteReader()

            Do While custReader.Read()
                Console.WriteLine("Orders for " & custReader.GetString(1))
                ' custReader.GetString(1) = CompanyName  

                Using orderReader As OleDbDataReader = custReader.GetValue(2)
                    ' custReader.GetValue(2) = Orders chapter as DataReader  

                    Do While orderReader.Read()
                        Console.WriteLine(vbTab & orderReader.GetInt32(1))
                        ' orderReader.GetInt32(1) = OrderID  
                    Loop
                    orderReader.Close()
                End Using
            Loop
            ' Make sure to always close readers and connections.  
            custReader.Close()
        End Using
    End Using
End Using
```  
  
```csharp  
using (OleDbConnection connection = new OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" +
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind"))
{
    using (OleDbCommand custCMD = new OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " +
        "RELATE CustomerID TO CustomerID)", connection))
    {
        connection.Open();

        using (OleDbDataReader custReader = custCMD.ExecuteReader())
        {

            while (custReader.Read())
            {
                Console.WriteLine("Orders for " + custReader.GetString(1));
                // custReader.GetString(1) = CompanyName  

                using (OleDbDataReader orderReader = (OleDbDataReader)custReader.GetValue(2))
                {
                    // custReader.GetValue(2) = Orders chapter as DataReader  

                    while (orderReader.Read())
                        Console.WriteLine("\t" + orderReader.GetInt32(1));
                    // orderReader.GetInt32(1) = OrderID  
                    orderReader.Close();
                }
            }
            // Make sure to always close readers and connections.  
            custReader.Close();
        }
    }
}
```  
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="96c65-137">Zurückgeben von Ergebnissen mit Oracle-REF Cursors</span><span class="sxs-lookup"><span data-stu-id="96c65-137">Returning results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="96c65-138">Der .NET Framework-Datenanbieter für Oracle unterstützt die Verwendung von Oracle-REF CURSORs zur Rückgabe eines Abfrageergebnisses.</span><span class="sxs-lookup"><span data-stu-id="96c65-138">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="96c65-139">Ein Oracle-REF CURSOR wird als <xref:System.Data.OracleClient.OracleDataReader> zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="96c65-139">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="96c65-140">Sie können ein <xref:System.Data.OracleClient.OracleDataReader> Objekt, das einen Oracle-REF-Cursor darstellt, <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> mithilfe der-Methode abrufen.</span><span class="sxs-lookup"><span data-stu-id="96c65-140">You can retrieve an <xref:System.Data.OracleClient.OracleDataReader> object that represents an Oracle REF CURSOR by using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method.</span></span> <span data-ttu-id="96c65-141">Sie <xref:System.Data.OracleClient.OracleCommand> können auch einen angeben, der einen oder mehrere Oracle-REF Cursors als **SelectCommand** für einen <xref:System.Data.OracleClient.OracleDataAdapter> zurückgibt, der zum Ausfüllen eines <xref:System.Data.DataSet>verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="96c65-141">You can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="96c65-142">Um auf einen von einer Oracle-Datenquelle zurückgegebenen Verweis Cursor zuzugreifen <xref:System.Data.OracleClient.OracleCommand> , erstellen Sie einen für die Abfrage, und fügen Sie einen Output-Parameter <xref:System.Data.OracleClient.OracleCommand.Parameters> hinzu, der <xref:System.Data.OracleClient.OracleCommand>auf den Verweis Cursor auf die-Auflistung Ihres verweist.</span><span class="sxs-lookup"><span data-stu-id="96c65-142">To access a REF CURSOR returned from an Oracle data source, create an <xref:System.Data.OracleClient.OracleCommand> for your query and add an output parameter that references the REF CURSOR to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection of your <xref:System.Data.OracleClient.OracleCommand>.</span></span> <span data-ttu-id="96c65-143">Der Name des Parameters muss mit dem Namen des REF CURSOR-Parameters in der Abfrage übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="96c65-143">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="96c65-144">Legen Sie den Typ des Parameters <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>auf fest.</span><span class="sxs-lookup"><span data-stu-id="96c65-144">Set the type of the parameter to <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>.</span></span> <span data-ttu-id="96c65-145">Die <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> -Methode <xref:System.Data.OracleClient.OracleCommand> des gibt einen <xref:System.Data.OracleClient.OracleDataReader> für den ref Cursor zurück.</span><span class="sxs-lookup"><span data-stu-id="96c65-145">The <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method of your <xref:System.Data.OracleClient.OracleCommand> returns an <xref:System.Data.OracleClient.OracleDataReader> for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="96c65-146">Wenn Sie <xref:System.Data.OracleClient.OracleCommand> mehrere Ref Cursors zurückgibt, fügen Sie mehrere Ausgabeparameter hinzu.</span><span class="sxs-lookup"><span data-stu-id="96c65-146">If your <xref:System.Data.OracleClient.OracleCommand> returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="96c65-147">Sie können auf die verschiedenen REF CURSORs zugreifen, indem <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> Sie die-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="96c65-147">You can access the different REF CURSORs by calling the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="96c65-148">Der-Rückruf <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> gibt einen <xref:System.Data.OracleClient.OracleDataReader> zurück, der auf den ersten Verweis Cursor verweist.</span><span class="sxs-lookup"><span data-stu-id="96c65-148">The call to <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> returns an <xref:System.Data.OracleClient.OracleDataReader> referencing the first REF CURSOR.</span></span> <span data-ttu-id="96c65-149">Sie können dann die <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> -Methode aufrufen, um auf nachfolgende Ref Cursors zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="96c65-149">You can then call the <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="96c65-150">Obwohl die Parameter in <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> der Auflistung den REF CURSOR-Ausgabeparametern nach Namen entsprechen, greift der <xref:System.Data.OracleClient.OracleDataReader> in der Reihenfolge, in der <xref:System.Data.OracleClient.OracleCommand.Parameters> Sie der Auflistung hinzugefügt wurden, auf Sie zu.</span><span class="sxs-lookup"><span data-stu-id="96c65-150">Although the parameters in your <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection match the REF CURSOR output parameters by name, the <xref:System.Data.OracleClient.OracleDataReader> accesses them in the order in which they were added to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection.</span></span>  
  
 <span data-ttu-id="96c65-151">Betrachten Sie z. B. das folgende Oracle-Paket und den Paketkörper.</span><span class="sxs-lookup"><span data-stu-id="96c65-151">For example, consider the following Oracle package and package body.</span></span>  
  
```sql
CREATE OR REPLACE PACKAGE CURSPKG AS   
  TYPE T_CURSOR IS REF CURSOR;   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR);   
END CURSPKG;  
  
CREATE OR REPLACE PACKAGE BODY CURSPKG AS   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR)   
  IS   
  BEGIN   
    OPEN EMPCURSOR FOR SELECT * FROM DEMO.EMPLOYEE;   
    OPEN DEPTCURSOR FOR SELECT * FROM DEMO.DEPARTMENT;   
  END OPEN_TWO_CURSORS;   
END CURSPKG;   
```  
  
 <span data-ttu-id="96c65-152">Der folgende Code erstellt eine <xref:System.Data.OracleClient.OracleCommand> , die die Ref Cursors aus dem vorherigen Oracle-Paket zurückgibt, indem der <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> -Auflistung zwei Parameter des Typs hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="96c65-152">The following code creates an <xref:System.Data.OracleClient.OracleCommand> that returns the REF CURSORs from the previous Oracle package by adding two parameters of type <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> to the <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection.</span></span>  
  
```vb  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
```  
  
```csharp  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
```  
  
 <span data-ttu-id="96c65-153">Der folgende Code gibt die Ergebnisse des vorherigen Befehls mithilfe der <xref:System.Data.OracleClient.OracleDataReader.Read> -Methode und der- <xref:System.Data.OracleClient.OracleDataReader> <xref:System.Data.OracleClient.OracleDataReader.NextResult> Methode von zurück.</span><span class="sxs-lookup"><span data-stu-id="96c65-153">The following code returns the results of the previous command using the <xref:System.Data.OracleClient.OracleDataReader.Read> and <xref:System.Data.OracleClient.OracleDataReader.NextResult> methods of the <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="96c65-154">Die REF CURSOR-Parameter werden der Reihe nach zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="96c65-154">The REF CURSOR parameters are returned in order.</span></span>  
  
```vb  
oraConn.Open()  
  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.CommandType = CommandType.StoredProcedure  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
  
Dim reader As OracleDataReader = cursCmd.ExecuteReader()  
  
Console.WriteLine(vbCrLf & "Emp ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2))  
Loop  
  
reader.NextResult()  
  
Console.WriteLine(vbCrLf & "Dept ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}", reader.GetOracleNumber(0), reader.GetString(1))  
Loop  
' Make sure to always close readers and connections.  
reader.Close()  
oraConn.Close()  
```  
  
```csharp  
oraConn.Open();  
  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.CommandType = CommandType.StoredProcedure;  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
  
OracleDataReader reader = cursCmd.ExecuteReader();  
  
Console.WriteLine("\nEmp ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2));  
  
reader.NextResult();  
  
Console.WriteLine("\nDept ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}", reader.GetOracleNumber(0), reader.GetString(1));  
// Make sure to always close readers and connections.  
reader.Close();  
oraConn.Close();  
```  
  
 <span data-ttu-id="96c65-155">Im folgenden Beispiel wird der vorherige Befehl verwendet, um eine <xref:System.Data.DataSet> mit den Ergebnissen des Oracle-Pakets aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="96c65-155">The following example uses the previous command to populate a <xref:System.Data.DataSet> with the results of the Oracle package.</span></span>  
  
```vb  
Dim ds As DataSet = New DataSet()  
  
Dim adapter As OracleDataAdapter = New OracleDataAdapter(cursCmd)  
adapter.TableMappings.Add("Table", "Employees")  
adapter.TableMappings.Add("Table1", "Departments")  
  
adapter.Fill(ds)  
```  
  
```csharp  
DataSet ds = new DataSet();  
  
OracleDataAdapter adapter = new OracleDataAdapter(cursCmd);  
adapter.TableMappings.Add("Table", "Employees");  
adapter.TableMappings.Add("Table1", "Departments");  
  
adapter.Fill(ds);  
```

> [!NOTE]
> <span data-ttu-id="96c65-156">Um eine **OverflowException**zu vermeiden, empfiehlt es sich, jede beliebige Konvertierung vom Oracle-Nummertyp in einen gültigen .NET Framework Typ zu verarbeiten, bevor der <xref:System.Data.DataRow>Wert in einer gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="96c65-156">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="96c65-157">Sie können das <xref:System.Data.Common.DataAdapter.FillError> -Ereignis verwenden, um zu bestimmen, ob eine **OverflowException** aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="96c65-157">You can use the <xref:System.Data.Common.DataAdapter.FillError> event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="96c65-158">Weitere Informationen <xref:System.Data.Common.DataAdapter.FillError> zum-Ereignis finden Sie unter [Handling DataAdapter-Ereignisse](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="96c65-158">For more information on the <xref:System.Data.Common.DataAdapter.FillError> event, see [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c65-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96c65-159">See also</span></span>

- [<span data-ttu-id="96c65-160">DataAdapters und DataReaders</span><span class="sxs-lookup"><span data-stu-id="96c65-160">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="96c65-161">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="96c65-161">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="96c65-162">Abrufen von Datenbankschemainformationen</span><span class="sxs-lookup"><span data-stu-id="96c65-162">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [<span data-ttu-id="96c65-163">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="96c65-163">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
