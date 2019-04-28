---
title: Abrufen von Daten mit "DataReader"
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 8063f239123ec1a2f2650adf9d76f7ceaaa50673
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61664258"
---
# <a name="retrieve-data-using-a-datareader"></a><span data-ttu-id="11755-102">Abrufen von Daten, die mit "DataReader"</span><span class="sxs-lookup"><span data-stu-id="11755-102">Retrieve data using a DataReader</span></span>
<span data-ttu-id="11755-103">Zum Abrufen von Daten mithilfe einer **DataReader**, erstellen Sie eine Instanz von der **Befehl** Objekt aus, und erstellen Sie eine **DataReader** durch Aufrufen von **Command.ExecuteReader**  um Zeilen aus einer Datenquelle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="11755-103">To retrieve data using a **DataReader**, create an instance of the **Command** object, and then create a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="11755-104">Die **DataReader** enthält einen nicht gepufferten Datenstream, mit der prozeduralen Logik, die Ergebnisse aus einer Datenquelle effizient sequenziell zu verarbeiten zu können.</span><span class="sxs-lookup"><span data-stu-id="11755-104">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="11755-105">Die **DataReader** ist eine gute Wahl, wenn Sie große Mengen von Daten abgerufen werden, da die Daten nicht im Arbeitsspeicher zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="11755-105">The **DataReader** is a good choice when you're retrieving large amounts of data because the data is not cached in memory.</span></span>

<span data-ttu-id="11755-106">Das folgende Beispiel veranschaulicht die Verwendung einer **DataReader**, wobei `reader` stellt ein gültiger DataReader-Ziel und `command` ein gültiges Command-Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="11755-106">The following example illustrates using a **DataReader**, where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

<span data-ttu-id="11755-107">Verwenden der **DataReader.Read** Methode, um eine Zeile aus die Ergebnisse der Abfrage abzurufen.</span><span class="sxs-lookup"><span data-stu-id="11755-107">Use the **DataReader.Read** method to obtain a row from the query results.</span></span> <span data-ttu-id="11755-108">Sie können jede Spalte der zurückgegebenen Zeile zugreifen, indem Sie übergeben den Namen oder die Ordnungszahl der Spalte, die die **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="11755-108">You can access each column of the returned row by passing the name or ordinal number of the column to the **DataReader**.</span></span> <span data-ttu-id="11755-109">Allerdings für eine optimale Leistung die **DataReader** enthält eine Reihe von Methoden, die Sie auf Spaltenwerte in deren systemeigenen Datentypen zugreifen können (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**und so weiter).</span><span class="sxs-lookup"><span data-stu-id="11755-109">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="11755-110">Eine Liste der typisierten Zugriffsmethoden für anbieterspezifische **"DataReaders"**, finden Sie unter <xref:System.Data.OleDb.OleDbDataReader> und <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="11755-110">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="11755-111">Verwenden die typisierten Accessormethoden bereit, wenn Sie wissen, dass die zugrunde liegenden Daten verringert Typ die Typumwandlung erforderlich, wenn der Wert der Spalte abrufen.</span><span class="sxs-lookup"><span data-stu-id="11755-111">Using the typed accessor methods when you know the underlying data type reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
 <span data-ttu-id="11755-112">Das folgende Beispiel durchläuft einen **DataReader** -Objekt und zwei Spalten aus jeder Zeile zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="11755-112">The following example iterates through a **DataReader** object and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="11755-113">Schließen des "DataReader"</span><span class="sxs-lookup"><span data-stu-id="11755-113">Closing the DataReader</span></span>  
 <span data-ttu-id="11755-114">Rufen Sie immer die **schließen** Methode, wenn Sie aufgehört haben die **DataReader** Objekt.</span><span class="sxs-lookup"><span data-stu-id="11755-114">Always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="11755-115">Wenn Ihre **Befehl** enthält die Ausgabe Parameter oder Rückgabewerte, sind diese Werte nicht verfügbar, bis die **DataReader** geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="11755-115">If your **Command** contains output parameters or return values, those values are not available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="11755-116">Während einer **DataReader** geöffnet ist, die **Verbindung** wird ausschließlich von diesem **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="11755-116">While a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="11755-117">Sie können nicht ausgeführt werden Befehle für die **Verbindung**, einschließlich der Erstellung eines weiteren **DataReader**, bis die ursprüngliche **DataReader** geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="11755-117">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11755-118">Rufen Sie nicht **schließen** oder **Dispose** auf eine **Verbindung**, **DataReader**, oder andere verwaltete Objekte in der **abschließen**  Methode der Klasse.</span><span class="sxs-lookup"><span data-stu-id="11755-118">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="11755-119">Geben Sie in einer Finalize-Methode nur nicht verwaltete Ressourcen frei, die der Klasse direkt gehören.</span><span class="sxs-lookup"><span data-stu-id="11755-119">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="11755-120">Wenn Ihre Klasse keine nicht verwalteten Ressourcen besitzt, ist nicht enthalten. ein **Finalize** Methode in der Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="11755-120">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="11755-121">Weitere Informationen finden Sie unter [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="11755-121">For more information, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="11755-122">Abrufen von mehreren Resultsets legt fest, die mit "NextResult"</span><span class="sxs-lookup"><span data-stu-id="11755-122">Retrieving multiple result sets using NextResult</span></span>  
 <span data-ttu-id="11755-123">Wenn die **DataReader** mehrere Resultsets Aufruf gibt die **NextResult** Methode zum iterieren durch das Ergebnis wird sequenziell.</span><span class="sxs-lookup"><span data-stu-id="11755-123">If the **DataReader** returns multiple result sets, call the **NextResult** method to iterate through the result sets sequentially.</span></span> <span data-ttu-id="11755-124">Im folgenden Beispiel werden die Ergebnisse von zwei SELECT-Anweisungen mit der <xref:System.Data.SqlClient.SqlDataReader>-Methode von <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="11755-124">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="11755-125">Abrufen von Schemainformationen vom DataReader</span><span class="sxs-lookup"><span data-stu-id="11755-125">Getting schema information from the DataReader</span></span>  
 <span data-ttu-id="11755-126">Während einer **DataReader** ist geöffnet ist, können die Schemainformationen über das aktuelle Resultset mit Abrufen der **GetSchemaTable** Methode.</span><span class="sxs-lookup"><span data-stu-id="11755-126">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="11755-127">**GetSchemaTable** gibt eine <xref:System.Data.DataTable> -Objekt mit den Zeilen und Spalten, die die Schemainformationen für das aktuelle Resultset enthalten.</span><span class="sxs-lookup"><span data-stu-id="11755-127">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="11755-128">Die **DataTable** enthält eine Zeile für jede Spalte des Resultsets.</span><span class="sxs-lookup"><span data-stu-id="11755-128">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="11755-129">Jede Spalte der Schematabelle ordnet eine Eigenschaft, die Spalten, die Zeilen des Resultsets festgelegt, wobei die **ColumnName** ist der Name der Eigenschaft und der Wert der Spalte den Wert der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="11755-129">Each column of the schema table maps to a property of the columns returned in the rows of the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="11755-130">Im folgende Beispiel schreibt die Schemainformationen für **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="11755-130">The following example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="11755-131">Arbeiten mit OLE DB-Kapitel</span><span class="sxs-lookup"><span data-stu-id="11755-131">Working with OLE DB chapters</span></span>  
 <span data-ttu-id="11755-132">Hierarchische Rowsets oder Kapitel (OLE DB-Typ **DBTYPE_HCHAPTER**, ADO-Typ **AdChapter**), können abgerufen werden, mithilfe der <xref:System.Data.OleDb.OleDbDataReader>.</span><span class="sxs-lookup"><span data-stu-id="11755-132">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**), can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="11755-133">Wenn eine Abfrage, die einem Kapitel zurückgegeben wird, als eine **DataReader**, das Kapitel als Spalte in diesem zurückgegeben wird **DataReader** und als verfügbar gemacht wird eine **DataReader** Objekt.</span><span class="sxs-lookup"><span data-stu-id="11755-133">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="11755-134">ADO.NET **DataSet** kann auch verwendet werden, um hierarchische Rowsets mit über-und untergeordnete Beziehungen zwischen Tabellen darstellen.</span><span class="sxs-lookup"><span data-stu-id="11755-134">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets by using parent-child relationships between tables.</span></span> <span data-ttu-id="11755-135">Weitere Informationen finden Sie unter [DataSets, DataTables und DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span><span class="sxs-lookup"><span data-stu-id="11755-135">For more information, see [DataSets, DataTables, and DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="11755-136">Im folgenden Codebeispiel wird mit dem MSDataShape-Anbieter eine Kapitelspalte mit Bestellungen für jeden Kunden in einer Kundenliste generiert.</span><span class="sxs-lookup"><span data-stu-id="11755-136">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="11755-137">Zurückgeben von Ergebnissen mit Oracle-REF CURSORs</span><span class="sxs-lookup"><span data-stu-id="11755-137">Returning results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="11755-138">Der .NET Framework-Datenanbieter für Oracle unterstützt die Verwendung von Oracle-REF CURSORs zur Rückgabe eines Abfrageergebnisses.</span><span class="sxs-lookup"><span data-stu-id="11755-138">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="11755-139">Ein Oracle-REF CURSOR wird als <xref:System.Data.OracleClient.OracleDataReader> zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="11755-139">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="11755-140">Können Sie Abrufen einer <xref:System.Data.OracleClient.OracleDataReader> Objekt, eine Oracle-REF CURSOR darstellt, mit, der <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="11755-140">You can retrieve an <xref:System.Data.OracleClient.OracleDataReader> object that represents an Oracle REF CURSOR by using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method.</span></span> <span data-ttu-id="11755-141">Sie können auch angeben einer <xref:System.Data.OracleClient.OracleCommand> , die eine oder mehrere Oracle-REF CURSORs als zurückgibt der **SelectCommand** für eine <xref:System.Data.OracleClient.OracleDataAdapter> verwendet, um eine <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="11755-141">You can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="11755-142">Erstellen Sie aus einer Oracle-Datenquelle zurückgegebenen REF CURSOR für den Zugriff auf eine <xref:System.Data.OracleClient.OracleCommand> für die Abfrage und fügen Sie einen Output-Parameter, die den REF CURSOR verweist die <xref:System.Data.OracleClient.OracleCommand.Parameters> Auflistung von Ihrer <xref:System.Data.OracleClient.OracleCommand>.</span><span class="sxs-lookup"><span data-stu-id="11755-142">To access a REF CURSOR returned from an Oracle data source, create an <xref:System.Data.OracleClient.OracleCommand> for your query and add an output parameter that references the REF CURSOR to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection of your <xref:System.Data.OracleClient.OracleCommand>.</span></span> <span data-ttu-id="11755-143">Der Name des Parameters muss mit dem Namen des REF CURSOR-Parameters in der Abfrage übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="11755-143">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="11755-144">Legen Sie den Typ des Parameters, der <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="11755-144">Set the type of the parameter to <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>.</span></span> <span data-ttu-id="11755-145">Die <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> Methode Ihrer <xref:System.Data.OracleClient.OracleCommand> gibt ein <xref:System.Data.OracleClient.OracleDataReader> für den REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="11755-145">The <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method of your <xref:System.Data.OracleClient.OracleCommand> returns an <xref:System.Data.OracleClient.OracleDataReader> for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="11755-146">Wenn Ihre <xref:System.Data.OracleClient.OracleCommand> mehrere REF CURSORS zurückgibt fügen Sie mehrere Ausgabeparameter hinzu.</span><span class="sxs-lookup"><span data-stu-id="11755-146">If your <xref:System.Data.OracleClient.OracleCommand> returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="11755-147">Sie können die verschiedenen REF CURSORs zugreifen, durch den Aufruf der <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="11755-147">You can access the different REF CURSORs by calling the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="11755-148">Der Aufruf von <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> gibt ein <xref:System.Data.OracleClient.OracleDataReader> auf den ersten REF CURSOR verweist.</span><span class="sxs-lookup"><span data-stu-id="11755-148">The call to <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> returns an <xref:System.Data.OracleClient.OracleDataReader> referencing the first REF CURSOR.</span></span> <span data-ttu-id="11755-149">Rufen Sie anschließend die <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> Methode, um die nachfolgenden REF CURSORs zugreifen.</span><span class="sxs-lookup"><span data-stu-id="11755-149">You can then call the <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="11755-150">Obwohl die Parameter in Ihre <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> Auflistung Übereinstimmung den REF CURSOR-Ausgabeparameter anhand des Namens, der <xref:System.Data.OracleClient.OracleDataReader> greift auf sie in der Reihenfolge, in dem sie hinzugefügt wurden, die <xref:System.Data.OracleClient.OracleCommand.Parameters> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="11755-150">Although the parameters in your <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection match the REF CURSOR output parameters by name, the <xref:System.Data.OracleClient.OracleDataReader> accesses them in the order in which they were added to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection.</span></span>  
  
 <span data-ttu-id="11755-151">	Betrachten Sie z. B. das folgende Oracle-Paket und den Paketkörper.</span><span class="sxs-lookup"><span data-stu-id="11755-151">For example, consider the following Oracle package and package body.</span></span>  
  
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
  
 <span data-ttu-id="11755-152">Der folgende Code erstellt ein <xref:System.Data.OracleClient.OracleCommand> , aus dem vorherigen Oracle-Paket die REF CURSORs zurückgibt, durch das Hinzufügen von zwei Parametern vom Typ <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> auf die <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="11755-152">The following code creates an <xref:System.Data.OracleClient.OracleCommand> that returns the REF CURSORs from the previous Oracle package by adding two parameters of type <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> to the <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection.</span></span>  
  
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
  
 <span data-ttu-id="11755-153">Der folgende Code gibt die Ergebnisse des vorherigen Befehls mit der <xref:System.Data.OracleClient.OracleDataReader.Read> und <xref:System.Data.OracleClient.OracleDataReader.NextResult> Methoden der <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="11755-153">The following code returns the results of the previous command using the <xref:System.Data.OracleClient.OracleDataReader.Read> and <xref:System.Data.OracleClient.OracleDataReader.NextResult> methods of the <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="11755-154">Die REF CURSOR-Parameter werden der Reihe nach zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="11755-154">The REF CURSOR parameters are returned in order.</span></span>  
  
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
  
 <span data-ttu-id="11755-155">Im folgenden Beispiel wird den vorherigen Befehl zum Auffüllen einer <xref:System.Data.DataSet> mit den Ergebnissen des Oracle-Pakets.</span><span class="sxs-lookup"><span data-stu-id="11755-155">The following example uses the previous command to populate a <xref:System.Data.DataSet> with the results of the Oracle package.</span></span>  
  
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
>  <span data-ttu-id="11755-156">Vermeiden einer **OverflowException**, es wird empfohlen, dass Sie auch jede Konvertierung von Oracle-Typ NUMBER in einen gültigen .NET Framework-Typ vor dem Speichern des Werts in behandeln eine <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="11755-156">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="11755-157">Sie können die <xref:System.Data.Common.DataAdapter.FillError> Ereignis, um zu bestimmen, ob ein **OverflowException** aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="11755-157">You can use the <xref:System.Data.Common.DataAdapter.FillError> event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="11755-158">Weitere Informationen zu den <xref:System.Data.Common.DataAdapter.FillError> Ereignis finden Sie unter [Behandeln von DataAdapter-Ereignissen](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="11755-158">For more information on the <xref:System.Data.Common.DataAdapter.FillError> event, see [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11755-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11755-159">See also</span></span>

- [<span data-ttu-id="11755-160">DataAdapters und DataReaders</span><span class="sxs-lookup"><span data-stu-id="11755-160">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="11755-161">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="11755-161">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="11755-162">Abrufen von Datenbankschemainformationen</span><span class="sxs-lookup"><span data-stu-id="11755-162">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [<span data-ttu-id="11755-163">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="11755-163">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
