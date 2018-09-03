---
title: Abrufen von Daten mit "DataReader"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 4370a7a700a01943548bf067827e6640245caf4e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482163"
---
# <a name="retrieving-data-using-a-datareader"></a><span data-ttu-id="63370-102">Abrufen von Daten mit "DataReader"</span><span class="sxs-lookup"><span data-stu-id="63370-102">Retrieving Data Using a DataReader</span></span>
<span data-ttu-id="63370-103">Abrufen von Daten mithilfe einer **DataReader** umfasst das Erstellen einer Instanz von der **Befehl** und klicken Sie dann erstellen, eine **DataReader** durch Aufrufen von  **Command.ExecuteReader** um Zeilen aus einer Datenquelle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="63370-103">Retrieving data using a **DataReader** involves creating an instance of the **Command** object and then creating a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="63370-104">Das folgende Beispiel veranschaulicht die Verwendung einer **DataReader** , in denen `reader` stellt ein gültiger DataReader-Ziel und `command` ein gültiges Command-Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="63370-104">The following example illustrates using a **DataReader** where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  
  
```  
reader = command.ExecuteReader();  
```  
  
 <span data-ttu-id="63370-105">Sie verwenden die **lesen** Methode der **DataReader** Objekt um eine Zeile aus den Ergebnissen der Abfrage abzurufen.</span><span class="sxs-lookup"><span data-stu-id="63370-105">You use the **Read** method of the **DataReader** object to obtain a row from the results of the query.</span></span> <span data-ttu-id="63370-106">Sie können jede Spalte der zurückgegebenen Zeile zugreifen, indem Sie übergeben den Namen oder den Ordinalzahlverweis der Spalte, die die **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="63370-106">You can access each column of the returned row by passing the name or ordinal reference of the column to the **DataReader**.</span></span> <span data-ttu-id="63370-107">Allerdings für eine optimale Leistung die **DataReader** enthält eine Reihe von Methoden, die Sie auf Spaltenwerte in deren systemeigenen Datentypen zugreifen können (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**und so weiter).</span><span class="sxs-lookup"><span data-stu-id="63370-107">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="63370-108">Eine Liste der typisierten Zugriffsmethoden für anbieterspezifische **"DataReaders"**, finden Sie unter <xref:System.Data.OleDb.OleDbDataReader> und <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="63370-108">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="63370-109">Mit den typisierten Zugriffsmethoden wird der Aufwand für Typumwandlungen beim Abrufen eines Spaltenwerts reduziert, vorausgesetzt, der zugrunde liegende Datentyp ist bekannt.</span><span class="sxs-lookup"><span data-stu-id="63370-109">Using the typed accessor methods, assuming the underlying data type is known, reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63370-110">Die Windows Server 2003-Version von .NET Framework enthält eine zusätzliche Eigenschaft für die **DataReader**, **HasRows**, sodass Sie bestimmen, ob die **DataReader**Ergebnisse vor dem Lesen von ihr zurückgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="63370-110">The Windows Server 2003 release of the .NET Framework includes an additional property for the **DataReader**, **HasRows**, which enables you to determine if the **DataReader** has returned any results before reading from it.</span></span>  
  
 <span data-ttu-id="63370-111">Im folgenden Codebeispiel durchläuft eine **DataReader** Objekt und zwei Spalten aus jeder Zeile zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="63370-111">The following code example iterates through a **DataReader** object, and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
 <span data-ttu-id="63370-112">Die **DataReader** enthält einen nicht gepufferten Datenstream, mit der prozeduralen Logik, die Ergebnisse aus einer Datenquelle effizient sequenziell zu verarbeiten zu können.</span><span class="sxs-lookup"><span data-stu-id="63370-112">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="63370-113">Die **DataReader** ist eine gute Wahl, wenn große Mengen von Daten abgerufen werden, da die Daten nicht im Arbeitsspeicher zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="63370-113">The **DataReader** is a good choice when retrieving large amounts of data because the data is not cached in memory.</span></span>  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="63370-114">Schließen des "DataReader"</span><span class="sxs-lookup"><span data-stu-id="63370-114">Closing the DataReader</span></span>  
 <span data-ttu-id="63370-115">Rufen Sie immer die **schließen** Methode, wenn Sie aufgehört haben die **DataReader** Objekt.</span><span class="sxs-lookup"><span data-stu-id="63370-115">You should always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="63370-116">Wenn Ihre **Befehl** enthält die Ausgabe Parameter oder Rückgabewerte, diese werden nicht erst verfügbar, wenn die **DataReader** geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="63370-116">If your **Command** contains output parameters or return values, they will not be available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="63370-117">Beachten Sie, dass eine **DataReader** geöffnet ist, die **Verbindung** wird ausschließlich von diesem **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="63370-117">Note that while a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="63370-118">Sie können nicht ausgeführt werden Befehle für die **Verbindung**, einschließlich der Erstellung eines weiteren **DataReader**, bis die ursprüngliche **DataReader** geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="63370-118">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63370-119">Rufen Sie nicht **schließen** oder **Dispose** auf eine **Verbindung**, **DataReader**, oder andere verwaltete Objekte in der **abschließen**  Methode der Klasse.</span><span class="sxs-lookup"><span data-stu-id="63370-119">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="63370-120">Geben Sie in einer Finalize-Methode nur nicht verwaltete Ressourcen frei, die der Klasse direkt gehören.</span><span class="sxs-lookup"><span data-stu-id="63370-120">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="63370-121">Wenn Ihre Klasse keine nicht verwalteten Ressourcen besitzt, ist nicht enthalten. ein **Finalize** Methode in der Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="63370-121">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="63370-122">Weitere Informationen finden Sie unter [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="63370-122">For more information, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="63370-123">Abrufen mehrerer Resultsets mit "NextResult"</span><span class="sxs-lookup"><span data-stu-id="63370-123">Retrieving Multiple Result Sets using NextResult</span></span>  
 <span data-ttu-id="63370-124">Wenn mehrere Resultsets zurückgegeben werden, die **DataReader** bietet die **NextResult** Methode, um das Ergebnis durchlaufen legt fest, in der Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="63370-124">If multiple result sets are returned, the **DataReader** provides the **NextResult** method to iterate through the result sets in order.</span></span> <span data-ttu-id="63370-125">Im folgenden Beispiel werden die Ergebnisse von zwei SELECT-Anweisungen mit der <xref:System.Data.SqlClient.SqlDataReader>-Methode von <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="63370-125">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="63370-126">Abrufen von Schemainformationen aus dem "DataReader"</span><span class="sxs-lookup"><span data-stu-id="63370-126">Getting Schema Information from the DataReader</span></span>  
 <span data-ttu-id="63370-127">Während einer **DataReader** ist geöffnet ist, können die Schemainformationen über das aktuelle Resultset mit Abrufen der **GetSchemaTable** Methode.</span><span class="sxs-lookup"><span data-stu-id="63370-127">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="63370-128">**GetSchemaTable** gibt eine <xref:System.Data.DataTable> -Objekt mit den Zeilen und Spalten, die die Schemainformationen für das aktuelle Resultset enthalten.</span><span class="sxs-lookup"><span data-stu-id="63370-128">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="63370-129">Die **DataTable** enthält eine Zeile für jede Spalte des Resultsets.</span><span class="sxs-lookup"><span data-stu-id="63370-129">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="63370-130">Jede Spalte der Schematabellenzeile ordnet eine Eigenschaft der Spalte zurückgegeben wird, das Resultset, in denen die **ColumnName** ist der Name der Eigenschaft und der Wert der Spalte den Wert der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="63370-130">Each column of the schema table row maps to a property of the column returned in the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="63370-131">Im folgenden Codebeispiel schreibt die Schemainformationen für **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="63370-131">The following code example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="63370-132">Arbeiten mit OLE DB-Kapiteln</span><span class="sxs-lookup"><span data-stu-id="63370-132">Working with OLE DB Chapters</span></span>  
 <span data-ttu-id="63370-133">Hierarchische Rowsets oder Kapitel (OLE DB-Typ **DBTYPE_HCHAPTER**, ADO-Typ **AdChapter**) können abgerufen werden, mithilfe der <xref:System.Data.OleDb.OleDbDataReader>.</span><span class="sxs-lookup"><span data-stu-id="63370-133">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**) can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="63370-134">Wenn eine Abfrage, die einem Kapitel zurückgegeben wird, als eine **DataReader**, das Kapitel als Spalte in diesem zurückgegeben wird **DataReader** und als verfügbar gemacht wird eine **DataReader** Objekt.</span><span class="sxs-lookup"><span data-stu-id="63370-134">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="63370-135">ADO.NET **DataSet** kann auch zur Darstellung von hierarchischen Rowsets, die mit über-und untergeordnete Beziehungen zwischen Tabellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="63370-135">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets using parent-child relationships between tables.</span></span> <span data-ttu-id="63370-136">Weitere Informationen finden Sie unter [DataSets, DataTables und DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span><span class="sxs-lookup"><span data-stu-id="63370-136">For more information, see [DataSets, DataTables, and DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="63370-137">Im folgenden Codebeispiel wird mit dem MSDataShape-Anbieter eine Kapitelspalte mit Bestellungen für jeden Kunden in einer Kundenliste generiert.</span><span class="sxs-lookup"><span data-stu-id="63370-137">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection( _  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" & _  
  "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind")  
  
Dim custCMD As OleDbCommand = New OleDbCommand( _  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " & _  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " & _  
  "RELATE CustomerID TO CustomerID)", connection)  
connection.Open()  
  
Dim custReader As OleDbDataReader = custCMD.ExecuteReader()  
Dim orderReader As OleDbDataReader  
  
Do While custReader.Read()  
  Console.WriteLine("Orders for " & custReader.GetString(1))   
  ' custReader.GetString(1) = CompanyName  
  
  orderReader = custReader.GetValue(2)  
  ' custReader.GetValue(2) = Orders chapter as DataReader  
  
  Do While orderReader.Read()  
    Console.WriteLine(vbTab & orderReader.GetInt32(1))  
    ' orderReader.GetInt32(1) = OrderID  
  Loop  
  orderReader.Close()  
Loop  
' Make sure to always close readers and connections.  
custReader.Close()  
End Using  
```  
  
```csharp  
Using (OleDbConnection connection = new OleDbConnection(  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" +  
  "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind"));  
{  
OleDbCommand custCMD = new OleDbCommand(  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " +  
  "RELATE CustomerID TO CustomerID)", connection);  
connection.Open();  
  
OleDbDataReader custReader = custCMD.ExecuteReader();  
OleDbDataReader orderReader;  
  
while (custReader.Read())  
{  
  Console.WriteLine("Orders for " + custReader.GetString(1));   
  // custReader.GetString(1) = CompanyName  
  
  orderReader = (OleDbDataReader)custReader.GetValue(2);        
  // custReader.GetValue(2) = Orders chapter as DataReader  
  
  while (orderReader.Read())  
    Console.WriteLine("\t" + orderReader.GetInt32(1));          
    // orderReader.GetInt32(1) = OrderID  
  orderReader.Close();  
}  
// Make sure to always close readers and connections.  
custReader.Close();  
}  
```  
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="63370-138">Zurückgeben von Ergebnissen mit Oracle-REF CURSORn</span><span class="sxs-lookup"><span data-stu-id="63370-138">Returning Results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="63370-139">Der .NET Framework-Datenanbieter für Oracle unterstützt die Verwendung von Oracle-REF CURSORs zur Rückgabe eines Abfrageergebnisses.</span><span class="sxs-lookup"><span data-stu-id="63370-139">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="63370-140">Ein Oracle-REF CURSOR wird als <xref:System.Data.OracleClient.OracleDataReader> zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="63370-140">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="63370-141">Können Sie Abrufen einer **OracleDataReader** -Objekt, das eine Oracle-REF CURSOR darstellt der <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> Methode, und Sie können auch angeben, ein <xref:System.Data.OracleClient.OracleCommand> , die eine oder mehrere Oracle-REF CURSORs als zurückgibt der  **SelectCommand** für eine <xref:System.Data.OracleClient.OracleDataAdapter> verwendet, um eine <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="63370-141">You can retrieve an **OracleDataReader** object, that represents an Oracle REF CURSOR using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method, and you can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="63370-142">Erstellen Sie aus einer Oracle-Datenquelle zurückgegebenen REF CURSOR für den Zugriff auf eine **OracleCommand** für die Abfrage und fügen Sie einen Output-Parameter, die den REF CURSOR verweist die **Parameter** Auflistung von Ihrem  **OracleCommand**.</span><span class="sxs-lookup"><span data-stu-id="63370-142">To access a REF CURSOR returned from an Oracle data source, create an **OracleCommand** for your query and add an output parameter that references the REF CURSOR to the **Parameters** collection of your **OracleCommand**.</span></span> <span data-ttu-id="63370-143">Der Name des Parameters muss mit dem Namen des REF CURSOR-Parameters in der Abfrage übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="63370-143">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="63370-144">Legen Sie den Typ des Parameters, der **OracleType.Cursor**.</span><span class="sxs-lookup"><span data-stu-id="63370-144">Set the type of the parameter to **OracleType.Cursor**.</span></span> <span data-ttu-id="63370-145">Die **"ExecuteReader"** -Methode der Ihre **OracleCommand** gibt ein **OracleDataReader** für den REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="63370-145">The **ExecuteReader** method of your **OracleCommand** will return an **OracleDataReader** for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="63370-146">Wenn Ihre **OracleCommand** mehrere REF CURSORS zurückgibt fügen Sie mehrere Ausgabeparameter hinzu.</span><span class="sxs-lookup"><span data-stu-id="63370-146">If your **OracleCommand** returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="63370-147">Sie können die verschiedenen REF CURSORs zugreifen, durch den Aufruf der **OracleCommand.ExecuteReader** Methode.</span><span class="sxs-lookup"><span data-stu-id="63370-147">You can access the different REF CURSORs by calling the **OracleCommand.ExecuteReader** method.</span></span> <span data-ttu-id="63370-148">Der Aufruf von **"ExecuteReader"** gibt ein **OracleDataReader** auf den ersten REF CURSOR verweist.</span><span class="sxs-lookup"><span data-stu-id="63370-148">The call to **ExecuteReader** returns an **OracleDataReader** referencing the first REF CURSOR.</span></span> <span data-ttu-id="63370-149">Rufen Sie anschließend die **OracleDataReader.NextResult** Methode, um die nachfolgenden REF CURSORs zugreifen.</span><span class="sxs-lookup"><span data-stu-id="63370-149">You can then call the **OracleDataReader.NextResult** method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="63370-150">Obwohl die Parameter in Ihre **OracleCommand.Parameters** Auflistung Übereinstimmung den REF CURSOR-Ausgabeparameter anhand des Namens, der **OracleDataReader** greift auf sie in der Reihenfolge an, dass sie die hinzugefügtwurden **Parameter** Auflistung.</span><span class="sxs-lookup"><span data-stu-id="63370-150">Although the parameters in your **OracleCommand.Parameters** collection match the REF CURSOR output parameters by name, the **OracleDataReader** accesses them in the order that they were added to the **Parameters** collection.</span></span>  
  
 <span data-ttu-id="63370-151">	Betrachten Sie z. B. das folgende Oracle-Paket und den Paketkörper.</span><span class="sxs-lookup"><span data-stu-id="63370-151">For example, consider the following Oracle package and package body.</span></span>  
  
```  
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
  
 <span data-ttu-id="63370-152">Der folgende Code erstellt ein **OracleCommand** , aus dem vorherigen Oracle-Paket die REF CURSORs zurückgibt, durch das Hinzufügen von zwei Parametern vom Typ **OracleType.Cursor** auf die **Parameter** Auflistung.</span><span class="sxs-lookup"><span data-stu-id="63370-152">The following code creates an **OracleCommand** that returns the REF CURSORs from the previous Oracle package by adding two parameters of type **OracleType.Cursor** to the **Parameters** collection.</span></span>  
  
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
  
 <span data-ttu-id="63370-153">Der folgende Code gibt die Ergebnisse des vorherigen Befehls mit der **lesen** und **NextResult** Methoden der **OracleDataReader**.</span><span class="sxs-lookup"><span data-stu-id="63370-153">The following code returns the results of the previous command using the **Read** and **NextResult** methods of the **OracleDataReader**.</span></span> <span data-ttu-id="63370-154">Die REF CURSOR-Parameter werden der Reihe nach zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="63370-154">The REF CURSOR parameters are returned in order.</span></span>  
  
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
  
 <span data-ttu-id="63370-155">Im folgenden Beispiel wird den vorherigen Befehl zum Auffüllen einer **DataSet** mit den Ergebnissen des Oracle-Pakets.</span><span class="sxs-lookup"><span data-stu-id="63370-155">The following example uses the previous command to populate a **DataSet** with the results of the Oracle package.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63370-156">Vermeiden einer **OverflowException**, es wird empfohlen, dass Sie auch jede Konvertierung von Oracle-Typ NUMBER in einen gültigen .NET Framework-Typ vor dem Speichern des Werts in behandeln eine **DataRow**.</span><span class="sxs-lookup"><span data-stu-id="63370-156">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a **DataRow**.</span></span> <span data-ttu-id="63370-157">Sie können die **FillError** Ereignis, um zu bestimmen, ob ein **OverflowException** aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="63370-157">You can use the **FillError** event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="63370-158">Weitere Informationen zu den **FillError** Ereignis finden Sie unter [Behandeln von DataAdapter-Ereignissen](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="63370-158">For more information on the **FillError** event, see [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="63370-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63370-159">See Also</span></span>  
 [<span data-ttu-id="63370-160">Arbeiten mit "DataReaders"</span><span class="sxs-lookup"><span data-stu-id="63370-160">Working with DataReaders</span></span>](https://msdn.microsoft.com/library/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [<span data-ttu-id="63370-161">DataAdapters und DataReaders</span><span class="sxs-lookup"><span data-stu-id="63370-161">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="63370-162">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="63370-162">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="63370-163">Abrufen von Datenbankschemainformationen</span><span class="sxs-lookup"><span data-stu-id="63370-163">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [<span data-ttu-id="63370-164">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="63370-164">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
