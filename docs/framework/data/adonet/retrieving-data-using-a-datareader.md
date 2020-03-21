---
title: Abrufen von Daten mit "DataReader"
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 88cd85ce343aaab08b944f81c9659918014da0a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149023"
---
# <a name="retrieve-data-using-a-datareader"></a><span data-ttu-id="11167-102">Abrufen von Daten mithilfe eines DataReaders</span><span class="sxs-lookup"><span data-stu-id="11167-102">Retrieve data using a DataReader</span></span>
<span data-ttu-id="11167-103">Um Daten mit einem **DataReader**abzurufen, erstellen Sie eine Instanz des Command-Objekts, und erstellen Sie dann einen **DataReader,** indem Sie **Command.ExecuteReader** aufrufen, um Zeilen aus einer Datenquelle abzurufen. **Command**</span><span class="sxs-lookup"><span data-stu-id="11167-103">To retrieve data using a **DataReader**, create an instance of the **Command** object, and then create a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="11167-104">Der **DataReader** stellt einen ungepufferten Datenstrom bereit, mit dem die Prozedurlogik Ergebnisse aus einer Datenquelle sequenziell effizient verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="11167-104">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="11167-105">Der **DataReader** ist eine gute Wahl, wenn Sie große Datenmengen abrufen, da die Daten nicht im Arbeitsspeicher zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="11167-105">The **DataReader** is a good choice when you're retrieving large amounts of data because the data is not cached in memory.</span></span>

<span data-ttu-id="11167-106">Das folgende Beispiel veranschaulicht die Verwendung `reader` eines **DataReader** `command` , wobei ein gültiger DataReader und ein gültiges Command-Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="11167-106">The following example illustrates using a **DataReader**, where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

<span data-ttu-id="11167-107">Verwenden Sie die **DataReader.Read-Methode,** um eine Zeile aus den Abfrageergebnissen abzufragen.</span><span class="sxs-lookup"><span data-stu-id="11167-107">Use the **DataReader.Read** method to obtain a row from the query results.</span></span> <span data-ttu-id="11167-108">Sie können auf jede Spalte der zurückgegebenen Zeile zugreifen, indem Sie den Namen oder die Ordinalnummer der Spalte an den **DataReader**übergeben.</span><span class="sxs-lookup"><span data-stu-id="11167-108">You can access each column of the returned row by passing the name or ordinal number of the column to the **DataReader**.</span></span> <span data-ttu-id="11167-109">Für eine optimale Leistung bietet **dataReader** jedoch eine Reihe von Methoden, mit denen Sie auf Spaltenwerte in ihren systemeigenen Datentypen zugreifen können (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**usw.).</span><span class="sxs-lookup"><span data-stu-id="11167-109">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="11167-110">Eine Liste der typisierten Accessormethoden für datenanbieterspezifische <xref:System.Data.OleDb.OleDbDataReader> <xref:System.Data.SqlClient.SqlDataReader> **DataReader**finden Sie unter und .</span><span class="sxs-lookup"><span data-stu-id="11167-110">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="11167-111">Wenn Sie die typisierten Accessormethoden verwenden, wenn Sie wissen, dass der zugrunde liegende Datentyp den Beim Abrufen des Spaltenwerts erforderlichen Typkonvertierungstyps verwendet.</span><span class="sxs-lookup"><span data-stu-id="11167-111">Using the typed accessor methods when you know the underlying data type reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
 <span data-ttu-id="11167-112">Im folgenden Beispiel wird ein **DataReader-Objekt** durchlaufen und zwei Spalten aus jeder Zeile zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="11167-112">The following example iterates through a **DataReader** object and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="11167-113">Schließen des "DataReader"</span><span class="sxs-lookup"><span data-stu-id="11167-113">Closing the DataReader</span></span>  
 <span data-ttu-id="11167-114">Rufen Sie immer die **Close-Methode** auf, wenn Sie die Verwendung des **DataReader-Objekts** abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="11167-114">Always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="11167-115">Wenn Ihr **Befehl** Ausgabeparameter oder Rückgabewerte enthält, sind diese Werte erst verfügbar, wenn der **DataReader** geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="11167-115">If your **Command** contains output parameters or return values, those values are not available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="11167-116">Während ein **DataReader** geöffnet ist, wird die **Verbindung** ausschließlich von **diesem DataReader**verwendet.</span><span class="sxs-lookup"><span data-stu-id="11167-116">While a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="11167-117">Sie können keine Befehle für die **Verbindung**ausführen, einschließlich des Erstellens eines anderen **DataReader**, bis der ursprüngliche **DataReader** geschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="11167-117">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="11167-118">Rufen Sie **Close** oder **Dispose** nicht für eine **Verbindung**, einen **DataReader**oder ein anderes verwaltetes Objekt in der **Finalize-Methode** Ihrer Klasse auf.</span><span class="sxs-lookup"><span data-stu-id="11167-118">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="11167-119">Geben Sie in einer Finalize-Methode nur nicht verwaltete Ressourcen frei, die der Klasse direkt gehören.</span><span class="sxs-lookup"><span data-stu-id="11167-119">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="11167-120">Wenn Ihre Klasse keine nicht verwalteten Ressourcen besitzt, schließen Sie keine **Finalize-Methode** in ihre Klassendefinition ein.</span><span class="sxs-lookup"><span data-stu-id="11167-120">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="11167-121">Weitere Informationen finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="11167-121">For more information, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="11167-122">Abrufen mehrerer Resultsets mit NextResult</span><span class="sxs-lookup"><span data-stu-id="11167-122">Retrieving multiple result sets using NextResult</span></span>  
 <span data-ttu-id="11167-123">Wenn der **DataReader** mehrere Resultsets zurückgibt, rufen Sie die **NextResult-Methode** auf, um die Resultsets sequenziell zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="11167-123">If the **DataReader** returns multiple result sets, call the **NextResult** method to iterate through the result sets sequentially.</span></span> <span data-ttu-id="11167-124">Im folgenden Beispiel werden die Ergebnisse von zwei SELECT-Anweisungen mit der <xref:System.Data.SqlClient.SqlDataReader>-Methode von <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="11167-124">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="11167-125">Abrufen von Schemainformationen aus dem DataReader</span><span class="sxs-lookup"><span data-stu-id="11167-125">Getting schema information from the DataReader</span></span>  
 <span data-ttu-id="11167-126">Während ein **DataReader** geöffnet ist, können Sie mithilfe der **GetSchemaTable-Methode** Schemainformationen über das aktuelle Resultset abrufen.</span><span class="sxs-lookup"><span data-stu-id="11167-126">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="11167-127">**GetSchemaTable** gibt <xref:System.Data.DataTable> ein Objekt zurück, das mit Zeilen und Spalten gefüllt ist, die die Schemainformationen für das aktuelle Resultset enthalten.</span><span class="sxs-lookup"><span data-stu-id="11167-127">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="11167-128">Die **DataTable** enthält eine Zeile für jede Spalte des Resultsets.</span><span class="sxs-lookup"><span data-stu-id="11167-128">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="11167-129">Jede Spalte der Schematabelle wird einer Eigenschaft der Spalten zugeordnet, die in den Zeilen des Resultsets zurückgegeben werden, wobei der **ColumnName** der Name der Eigenschaft und der Wert der Spalte der Wert der Eigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="11167-129">Each column of the schema table maps to a property of the columns returned in the rows of the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="11167-130">Im folgenden Beispiel werden die Schemainformationen für **DataReader**ausgeschreiben.</span><span class="sxs-lookup"><span data-stu-id="11167-130">The following example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="11167-131">Arbeiten mit OLE DB-Kapiteln</span><span class="sxs-lookup"><span data-stu-id="11167-131">Working with OLE DB chapters</span></span>  
 <span data-ttu-id="11167-132">Hierarchische Rowsets oder Kapitel (OLE DB Typ **DBTYPE_HCHAPTER**, ADO-Typ <xref:System.Data.OleDb.OleDbDataReader> **adChapter**) können mit dem abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="11167-132">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**), can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="11167-133">Wenn eine Abfrage, die ein Kapitel enthält, als **DataReader**zurückgegeben wird, wird das Kapitel als Spalte in **diesem DataReader** zurückgegeben und als **DataReader-Objekt** verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="11167-133">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="11167-134">Das ADO.NET **DataSet** kann auch verwendet werden, um hierarchische Rowsets darzustellen, indem Parent-Child-Beziehungen zwischen Tabellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="11167-134">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets by using parent-child relationships between tables.</span></span> <span data-ttu-id="11167-135">Weitere Informationen finden Sie unter [DataSets, DataTables und DataViews](./dataset-datatable-dataview/index.md).</span><span class="sxs-lookup"><span data-stu-id="11167-135">For more information, see [DataSets, DataTables, and DataViews](./dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="11167-136">Im folgenden Codebeispiel wird mit dem MSDataShape-Anbieter eine Kapitelspalte mit Bestellungen für jeden Kunden in einer Kundenliste generiert.</span><span class="sxs-lookup"><span data-stu-id="11167-136">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="11167-137">Ergebnisse mit Oracle REF CURSORs zurücksenden</span><span class="sxs-lookup"><span data-stu-id="11167-137">Returning results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="11167-138">Der .NET Framework-Datenanbieter für Oracle unterstützt die Verwendung von Oracle-REF CURSORs zur Rückgabe eines Abfrageergebnisses.</span><span class="sxs-lookup"><span data-stu-id="11167-138">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="11167-139">Ein Oracle-REF CURSOR wird als <xref:System.Data.OracleClient.OracleDataReader> zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="11167-139">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="11167-140">Sie können <xref:System.Data.OracleClient.OracleDataReader> ein Objekt abrufen, das einen <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> Oracle REF CURSOR darstellt, indem Sie die Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="11167-140">You can retrieve an <xref:System.Data.OracleClient.OracleDataReader> object that represents an Oracle REF CURSOR by using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method.</span></span> <span data-ttu-id="11167-141">Sie können auch <xref:System.Data.OracleClient.OracleCommand> eine angeben, die einen oder mehrere Oracle <xref:System.Data.OracleClient.OracleDataAdapter> REF CURSORs als **SelectCommand** für eine zum Ausfüllen einer <xref:System.Data.DataSet>verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="11167-141">You can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="11167-142">Um auf einen REF CURSOR zuzugreifen, der <xref:System.Data.OracleClient.OracleCommand> von einer Oracle-Datenquelle zurückgegeben wird, erstellen <xref:System.Data.OracleClient.OracleCommand.Parameters> Sie <xref:System.Data.OracleClient.OracleCommand>eine für Ihre Abfrage, und fügen Sie einen Ausgabeparameter hinzu, der auf den REF CURSOR zur Auflistung Ihrer verweist.</span><span class="sxs-lookup"><span data-stu-id="11167-142">To access a REF CURSOR returned from an Oracle data source, create an <xref:System.Data.OracleClient.OracleCommand> for your query and add an output parameter that references the REF CURSOR to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection of your <xref:System.Data.OracleClient.OracleCommand>.</span></span> <span data-ttu-id="11167-143">Der Name des Parameters muss mit dem Namen des REF CURSOR-Parameters in der Abfrage übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="11167-143">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="11167-144">Legen Sie den Typ <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>des Parameters auf .</span><span class="sxs-lookup"><span data-stu-id="11167-144">Set the type of the parameter to <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>.</span></span> <span data-ttu-id="11167-145">Die <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> Methode <xref:System.Data.OracleClient.OracleCommand> von <xref:System.Data.OracleClient.OracleDataReader> Ihnen gibt eine für den REF CURSOR zurück.</span><span class="sxs-lookup"><span data-stu-id="11167-145">The <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method of your <xref:System.Data.OracleClient.OracleCommand> returns an <xref:System.Data.OracleClient.OracleDataReader> for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="11167-146">Wenn <xref:System.Data.OracleClient.OracleCommand> Sie mehrere REF CURSORS zurückgibt, fügen Sie mehrere Ausgabeparameter hinzu.</span><span class="sxs-lookup"><span data-stu-id="11167-146">If your <xref:System.Data.OracleClient.OracleCommand> returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="11167-147">Sie können auf die verschiedenen REF <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> CURSORs zugreifen, indem Sie die Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="11167-147">You can access the different REF CURSORs by calling the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="11167-148">Der Aufruf, <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> <xref:System.Data.OracleClient.OracleDataReader> einen Verweis auf den ersten REF CURSOR zurückzurufen.</span><span class="sxs-lookup"><span data-stu-id="11167-148">The call to <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> returns an <xref:System.Data.OracleClient.OracleDataReader> referencing the first REF CURSOR.</span></span> <span data-ttu-id="11167-149">Sie können dann <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> die Methode aufrufen, um auf nachfolgende REF CURSORs zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="11167-149">You can then call the <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="11167-150">Obwohl die Parameter <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> in Ihrer Auflistung mit den <xref:System.Data.OracleClient.OracleDataReader> REF CURSOR-Ausgabeparametern übereinstimmen, greift <xref:System.Data.OracleClient.OracleCommand.Parameters> der Zugriff auf sie in der Reihenfolge zu, in der sie der Auflistung hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="11167-150">Although the parameters in your <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection match the REF CURSOR output parameters by name, the <xref:System.Data.OracleClient.OracleDataReader> accesses them in the order in which they were added to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection.</span></span>  
  
 <span data-ttu-id="11167-151">	Betrachten Sie z. B. das folgende Oracle-Paket und den Paketkörper.</span><span class="sxs-lookup"><span data-stu-id="11167-151">For example, consider the following Oracle package and package body.</span></span>  
  
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
  
 <span data-ttu-id="11167-152">Der folgende Code <xref:System.Data.OracleClient.OracleCommand> erstellt eine, die die REF CURSORs aus <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> dem <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> vorherigen Oracle-Paket zurückgibt, indem der Auflistung zwei Parameter vom Typ hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="11167-152">The following code creates an <xref:System.Data.OracleClient.OracleCommand> that returns the REF CURSORs from the previous Oracle package by adding two parameters of type <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> to the <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection.</span></span>  
  
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
  
 <span data-ttu-id="11167-153">Der folgende Code gibt die Ergebnisse <xref:System.Data.OracleClient.OracleDataReader.Read> des <xref:System.Data.OracleClient.OracleDataReader.NextResult> vorherigen <xref:System.Data.OracleClient.OracleDataReader>Befehls mithilfe der und-Methoden der zurück.</span><span class="sxs-lookup"><span data-stu-id="11167-153">The following code returns the results of the previous command using the <xref:System.Data.OracleClient.OracleDataReader.Read> and <xref:System.Data.OracleClient.OracleDataReader.NextResult> methods of the <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="11167-154">Die REF CURSOR-Parameter werden der Reihe nach zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="11167-154">The REF CURSOR parameters are returned in order.</span></span>  
  
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
  
 <span data-ttu-id="11167-155">Im folgenden Beispiel wird der vorherige <xref:System.Data.DataSet> Befehl verwendet, um eine mit den Ergebnissen des Oracle-Pakets aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="11167-155">The following example uses the previous command to populate a <xref:System.Data.DataSet> with the results of the Oracle package.</span></span>  
  
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
> <span data-ttu-id="11167-156">Um eine **OverflowException**zu vermeiden, wird empfohlen, dass Sie auch jede Konvertierung vom Oracle NUMBER-Typ in einen gültigen .NET Framework-Typ behandeln, bevor Sie den Wert in einer <xref:System.Data.DataRow>speichern.</span><span class="sxs-lookup"><span data-stu-id="11167-156">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="11167-157">Sie können <xref:System.Data.Common.DataAdapter.FillError> das Ereignis verwenden, um zu bestimmen, ob eine **OverflowException** aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="11167-157">You can use the <xref:System.Data.Common.DataAdapter.FillError> event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="11167-158">Weitere Informationen zum <xref:System.Data.Common.DataAdapter.FillError> Ereignis finden Sie [unter Behandeln von DataAdapter-Ereignissen](handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="11167-158">For more information on the <xref:System.Data.Common.DataAdapter.FillError> event, see [Handling DataAdapter Events](handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11167-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="11167-159">See also</span></span>

- [<span data-ttu-id="11167-160">DataAdapters und DataReaders</span><span class="sxs-lookup"><span data-stu-id="11167-160">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="11167-161">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="11167-161">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="11167-162">Abrufen von Datenbankschemainformationen</span><span class="sxs-lookup"><span data-stu-id="11167-162">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)
- [<span data-ttu-id="11167-163">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="11167-163">ADO.NET Overview</span></span>](ado-net-overview.md)
