---
title: Abrufen von Daten mit "DataReader"
description: Erfahren Sie, wie Sie Daten mit einem DataReader in ADO.net mit diesem Beispielcode abrufen. DataReader bietet einen nicht gepufferten Datenstrom.
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 6e5161cc325bf0379bb9241b99c473c539ad1081
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286597"
---
# <a name="retrieve-data-using-a-datareader"></a><span data-ttu-id="9570e-104">Abrufen von Daten mithilfe eines DataReader-Objekts</span><span class="sxs-lookup"><span data-stu-id="9570e-104">Retrieve data using a DataReader</span></span>
<span data-ttu-id="9570e-105">Erstellen Sie zum Abrufen von Daten mithilfe eines **DataReader**-Objekts eine Instanz des **Befehls** Objekts, und erstellen Sie dann einen **DataReader** , indem Sie **Command. ExecuteReader** aufrufen, um Zeilen aus einer Datenquelle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9570e-105">To retrieve data using a **DataReader**, create an instance of the **Command** object, and then create a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="9570e-106">Das **DataReader** -Objekt stellt einen nicht gepufferten Datenstrom bereit, der prozeduralen Logik die effiziente Verarbeitung von Ergebnissen aus einer Datenquelle in sequenziell ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="9570e-106">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="9570e-107">Der **DataReader** ist eine gute Wahl, wenn Sie große Datenmengen abrufen, da die Daten nicht im Arbeitsspeicher zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="9570e-107">The **DataReader** is a good choice when you're retrieving large amounts of data because the data is not cached in memory.</span></span>

<span data-ttu-id="9570e-108">Das folgende Beispiel veranschaulicht die Verwendung eines **DataReader**, wobei `reader` einen gültigen DataReader darstellt und `command` ein gültiges Befehls Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="9570e-108">The following example illustrates using a **DataReader**, where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

<span data-ttu-id="9570e-109">Verwenden Sie die **DataReader. Read** -Methode, um eine Zeile aus den Abfrage Ergebnissen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9570e-109">Use the **DataReader.Read** method to obtain a row from the query results.</span></span> <span data-ttu-id="9570e-110">Sie können auf jede Spalte der zurückgegebenen Zeile zugreifen, indem Sie den Namen oder die Ordinalzahl der Spalte an den **DataReader**übergeben.</span><span class="sxs-lookup"><span data-stu-id="9570e-110">You can access each column of the returned row by passing the name or ordinal number of the column to the **DataReader**.</span></span> <span data-ttu-id="9570e-111">Um die bestmögliche Leistung zu erzielen, stellt der **DataReader** eine Reihe von Methoden bereit, mit denen Sie auf Spaltenwerte in ihren systemeigenen Datentypen (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**usw.) zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="9570e-111">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="9570e-112">Eine Liste der typisierten Accessormethoden für Datenanbieter spezifische **DataReaders**finden Sie unter <xref:System.Data.OleDb.OleDbDataReader> und <xref:System.Data.SqlClient.SqlDataReader> .</span><span class="sxs-lookup"><span data-stu-id="9570e-112">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="9570e-113">Wenn Sie die typisierten Accessormethoden verwenden, wenn Sie wissen, dass der zugrunde liegende Datentyp beim Abrufen des Spaltenwerts die erforderliche Typkonvertierung reduziert.</span><span class="sxs-lookup"><span data-stu-id="9570e-113">Using the typed accessor methods when you know the underlying data type reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
 <span data-ttu-id="9570e-114">Im folgenden Beispiel wird ein **DataReader** -Objekt durchlaufen, und es werden zwei Spalten aus jeder Zeile zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9570e-114">The following example iterates through a **DataReader** object and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="9570e-115">Schließen des "DataReader"</span><span class="sxs-lookup"><span data-stu-id="9570e-115">Closing the DataReader</span></span>  
 <span data-ttu-id="9570e-116">Verwenden Sie immer die **Close** -Methode, wenn Sie das **DataReader** -Objekt nicht mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="9570e-116">Always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="9570e-117">Wenn der **Befehl** Ausgabeparameter oder Rückgabewerte enthält, sind diese Werte erst nach dem Schließen des **DataReader** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9570e-117">If your **Command** contains output parameters or return values, those values are not available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="9570e-118">Während ein **DataReader** geöffnet ist, wird die **Verbindung** exklusiv von diesem **DataReader**verwendet.</span><span class="sxs-lookup"><span data-stu-id="9570e-118">While a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="9570e-119">Sie können keine Befehle für die **Verbindung**ausführen, einschließlich der Erstellung eines anderen **DataReader**, bis der ursprüngliche **DataReader** geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="9570e-119">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9570e-120">Führen Sie in der **Finalize** -Methode der Klasse nicht **Close** oder verwerfen für eine **Verbindung**, einen **DataReader** **oder ein** anderes verwaltetes Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="9570e-120">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="9570e-121">Geben Sie in einer Finalize-Methode nur nicht verwaltete Ressourcen frei, die der Klasse direkt gehören.</span><span class="sxs-lookup"><span data-stu-id="9570e-121">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="9570e-122">Wenn Ihre Klasse keine nicht verwalteten Ressourcen besitzt, schließen Sie keine **Finalize** -Methode in die Klassendefinition ein.</span><span class="sxs-lookup"><span data-stu-id="9570e-122">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="9570e-123">Weitere Informationen finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="9570e-123">For more information, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="9570e-124">Abrufen mehrerer Resultsets mithilfe von NextResult</span><span class="sxs-lookup"><span data-stu-id="9570e-124">Retrieving multiple result sets using NextResult</span></span>  
 <span data-ttu-id="9570e-125">Wenn das **DataReader** -Objekt mehrere Resultsets zurückgibt, wird die **NextResult** -Methode aufgerufen, um die Resultsets sequenziell zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="9570e-125">If the **DataReader** returns multiple result sets, call the **NextResult** method to iterate through the result sets sequentially.</span></span> <span data-ttu-id="9570e-126">Im folgenden Beispiel werden die Ergebnisse von zwei SELECT-Anweisungen mit der <xref:System.Data.SqlClient.SqlDataReader>-Methode von <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="9570e-126">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="9570e-127">Erhalten von Schema Informationen aus dem DataReader</span><span class="sxs-lookup"><span data-stu-id="9570e-127">Getting schema information from the DataReader</span></span>  
 <span data-ttu-id="9570e-128">Während ein **DataReader** geöffnet ist, können Sie Schema Informationen über das aktuelle Resultset mithilfe der **getschembare** -Methode abrufen.</span><span class="sxs-lookup"><span data-stu-id="9570e-128">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="9570e-129">**Getschemabel** gibt ein <xref:System.Data.DataTable> -Objekt zurück, das mit Zeilen und Spalten aufgefüllt ist, die die Schema Informationen für das aktuelle Resultset enthalten.</span><span class="sxs-lookup"><span data-stu-id="9570e-129">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="9570e-130">Die **Daten** Tabelle enthält eine Zeile für jede Spalte des Resultsets.</span><span class="sxs-lookup"><span data-stu-id="9570e-130">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="9570e-131">Jede Spalte der Schema Tabelle ist einer Eigenschaft der Spalten zugeordnet, die in den Zeilen des Resultsets zurückgegeben werden, wobei **ColumnName** der Name der Eigenschaft und der Wert der Spalte der Wert der Eigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="9570e-131">Each column of the schema table maps to a property of the columns returned in the rows of the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="9570e-132">Im folgenden Beispiel werden die Schema Informationen für **DataReader**geschrieben.</span><span class="sxs-lookup"><span data-stu-id="9570e-132">The following example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="9570e-133">Arbeiten mit OLE DB Kapiteln</span><span class="sxs-lookup"><span data-stu-id="9570e-133">Working with OLE DB chapters</span></span>  
 <span data-ttu-id="9570e-134">Hierarchische Rowsets oder Kapitel (OLE DB Type **DBTYPE_HCHAPTER**, ADO Type **adChapter**) können mithilfe von abgerufen werden <xref:System.Data.OleDb.OleDbDataReader> .</span><span class="sxs-lookup"><span data-stu-id="9570e-134">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**), can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="9570e-135">Wenn eine Abfrage, die ein Kapitel enthält, als **DataReader**zurückgegeben wird, wird das Kapitel als Spalte in diesem **DataReader** zurückgegeben und als **DataReader** -Objekt verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="9570e-135">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="9570e-136">Das ADO.net- **DataSet** kann auch verwendet werden, um hierarchische Rowsets mithilfe von über-und untergeordneten Beziehungen zwischen Tabellen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="9570e-136">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets by using parent-child relationships between tables.</span></span> <span data-ttu-id="9570e-137">Weitere Informationen finden Sie unter [Datasets, DataTables und DataViews](./dataset-datatable-dataview/index.md).</span><span class="sxs-lookup"><span data-stu-id="9570e-137">For more information, see [DataSets, DataTables, and DataViews](./dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="9570e-138">Im folgenden Codebeispiel wird mit dem MSDataShape-Anbieter eine Kapitelspalte mit Bestellungen für jeden Kunden in einer Kundenliste generiert.</span><span class="sxs-lookup"><span data-stu-id="9570e-138">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="9570e-139">Zurückgeben von Ergebnissen mit Oracle-REF Cursors</span><span class="sxs-lookup"><span data-stu-id="9570e-139">Returning results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="9570e-140">Der .NET Framework-Datenanbieter für Oracle unterstützt die Verwendung von Oracle-REF CURSORs zur Rückgabe eines Abfrageergebnisses.</span><span class="sxs-lookup"><span data-stu-id="9570e-140">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="9570e-141">Ein Oracle-REF CURSOR wird als <xref:System.Data.OracleClient.OracleDataReader> zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9570e-141">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="9570e-142">Sie können ein <xref:System.Data.OracleClient.OracleDataReader> Objekt, das einen Oracle-REF-Cursor darstellt, mithilfe der- <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> Methode abrufen.</span><span class="sxs-lookup"><span data-stu-id="9570e-142">You can retrieve an <xref:System.Data.OracleClient.OracleDataReader> object that represents an Oracle REF CURSOR by using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method.</span></span> <span data-ttu-id="9570e-143">Sie können auch einen angeben <xref:System.Data.OracleClient.OracleCommand> , der einen oder mehrere Oracle-REF Cursors als **SelectCommand** für einen zurückgibt, der <xref:System.Data.OracleClient.OracleDataAdapter> zum Ausfüllen eines verwendet wird <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="9570e-143">You can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="9570e-144">Um auf einen von einer Oracle-Datenquelle zurückgegebenen Verweis Cursor zuzugreifen, erstellen Sie einen <xref:System.Data.OracleClient.OracleCommand> für die Abfrage, und fügen Sie einen Output-Parameter hinzu, der auf den Verweis Cursor auf die-Auflistung <xref:System.Data.OracleClient.OracleCommand.Parameters> Ihres verweist <xref:System.Data.OracleClient.OracleCommand> .</span><span class="sxs-lookup"><span data-stu-id="9570e-144">To access a REF CURSOR returned from an Oracle data source, create an <xref:System.Data.OracleClient.OracleCommand> for your query and add an output parameter that references the REF CURSOR to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection of your <xref:System.Data.OracleClient.OracleCommand>.</span></span> <span data-ttu-id="9570e-145">Der Name des Parameters muss mit dem Namen des REF CURSOR-Parameters in der Abfrage übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="9570e-145">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="9570e-146">Legen Sie den Typ des Parameters auf fest <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9570e-146">Set the type of the parameter to <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9570e-147">Die- <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> Methode des <xref:System.Data.OracleClient.OracleCommand> gibt einen <xref:System.Data.OracleClient.OracleDataReader> für den ref Cursor zurück.</span><span class="sxs-lookup"><span data-stu-id="9570e-147">The <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method of your <xref:System.Data.OracleClient.OracleCommand> returns an <xref:System.Data.OracleClient.OracleDataReader> for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="9570e-148">Wenn Sie <xref:System.Data.OracleClient.OracleCommand> mehrere Ref Cursors zurückgibt, fügen Sie mehrere Ausgabeparameter hinzu.</span><span class="sxs-lookup"><span data-stu-id="9570e-148">If your <xref:System.Data.OracleClient.OracleCommand> returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="9570e-149">Sie können auf die verschiedenen REF CURSORs zugreifen, indem Sie die- <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9570e-149">You can access the different REF CURSORs by calling the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9570e-150">Der-Rückruf <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> gibt einen zurück, <xref:System.Data.OracleClient.OracleDataReader> der auf den ersten Verweis Cursor verweist.</span><span class="sxs-lookup"><span data-stu-id="9570e-150">The call to <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> returns an <xref:System.Data.OracleClient.OracleDataReader> referencing the first REF CURSOR.</span></span> <span data-ttu-id="9570e-151">Sie können dann die- <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> Methode aufrufen, um auf nachfolgende Ref Cursors zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="9570e-151">You can then call the <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="9570e-152">Obwohl die Parameter in der Auflistung <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> den REF CURSOR-Ausgabeparametern nach Namen entsprechen, <xref:System.Data.OracleClient.OracleDataReader> greift der in der Reihenfolge, in der Sie der Auflistung hinzugefügt wurden, auf Sie zu <xref:System.Data.OracleClient.OracleCommand.Parameters> .</span><span class="sxs-lookup"><span data-stu-id="9570e-152">Although the parameters in your <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection match the REF CURSOR output parameters by name, the <xref:System.Data.OracleClient.OracleDataReader> accesses them in the order in which they were added to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection.</span></span>  
  
 <span data-ttu-id="9570e-153">	Betrachten Sie z. B. das folgende Oracle-Paket und den Paketkörper.</span><span class="sxs-lookup"><span data-stu-id="9570e-153">For example, consider the following Oracle package and package body.</span></span>  
  
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
  
 <span data-ttu-id="9570e-154">Der folgende Code erstellt eine <xref:System.Data.OracleClient.OracleCommand> , die die Ref Cursors aus dem vorherigen Oracle-Paket zurückgibt, indem der-Auflistung zwei Parameter des Typs hinzugefügt werden <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9570e-154">The following code creates an <xref:System.Data.OracleClient.OracleCommand> that returns the REF CURSORs from the previous Oracle package by adding two parameters of type <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> to the <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection.</span></span>  
  
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
  
 <span data-ttu-id="9570e-155">Der folgende Code gibt die Ergebnisse des vorherigen Befehls mithilfe der <xref:System.Data.OracleClient.OracleDataReader.Read> -Methode und der- <xref:System.Data.OracleClient.OracleDataReader.NextResult> Methode von zurück <xref:System.Data.OracleClient.OracleDataReader> .</span><span class="sxs-lookup"><span data-stu-id="9570e-155">The following code returns the results of the previous command using the <xref:System.Data.OracleClient.OracleDataReader.Read> and <xref:System.Data.OracleClient.OracleDataReader.NextResult> methods of the <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="9570e-156">Die REF CURSOR-Parameter werden der Reihe nach zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9570e-156">The REF CURSOR parameters are returned in order.</span></span>  
  
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
  
 <span data-ttu-id="9570e-157">Im folgenden Beispiel wird der vorherige Befehl verwendet, um eine <xref:System.Data.DataSet> mit den Ergebnissen des Oracle-Pakets aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="9570e-157">The following example uses the previous command to populate a <xref:System.Data.DataSet> with the results of the Oracle package.</span></span>  
  
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
> <span data-ttu-id="9570e-158">Um eine **OverflowException**zu vermeiden, empfiehlt es sich, jede beliebige Konvertierung vom Oracle-Nummertyp in einen gültigen .NET Framework Typ zu verarbeiten, bevor der Wert in einer gespeichert wird <xref:System.Data.DataRow> .</span><span class="sxs-lookup"><span data-stu-id="9570e-158">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="9570e-159">Sie können das- <xref:System.Data.Common.DataAdapter.FillError> Ereignis verwenden, um zu bestimmen, ob eine **OverflowException** aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="9570e-159">You can use the <xref:System.Data.Common.DataAdapter.FillError> event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="9570e-160">Weitere Informationen zum- <xref:System.Data.Common.DataAdapter.FillError> Ereignis finden Sie unter [Handling DataAdapter-Ereignisse](handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="9570e-160">For more information on the <xref:System.Data.Common.DataAdapter.FillError> event, see [Handling DataAdapter Events](handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9570e-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9570e-161">See also</span></span>

- [<span data-ttu-id="9570e-162">"DataAdapters" und "DataReaders"</span><span class="sxs-lookup"><span data-stu-id="9570e-162">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="9570e-163">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="9570e-163">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="9570e-164">Abrufen von Datenbankschemainformationen</span><span class="sxs-lookup"><span data-stu-id="9570e-164">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)
- [<span data-ttu-id="9570e-165">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9570e-165">ADO.NET Overview</span></span>](ado-net-overview.md)
