---
title: Paging durch ein Abfrageergebnis
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
ms.openlocfilehash: 065b509d8385ee37b2a86587f520b5fd3207ceff
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186951"
---
# <a name="paging-through-a-query-result"></a><span data-ttu-id="3b692-102">Paging durch ein Abfrageergebnis</span><span class="sxs-lookup"><span data-stu-id="3b692-102">Paging Through a Query Result</span></span>

<span data-ttu-id="3b692-103">Beim Paging durch ein Abfrageergebnis werden die Ergebnisse einer Abfrage in kleineren Untergruppen von Daten oder Seiten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3b692-103">Paging through a query result is the process of returning the results of a query in smaller subsets of data, or pages.</span></span> <span data-ttu-id="3b692-104">Dies ist eine allgemein übliche Vorgehensweise, um einem Benutzer Ergebnisse in kleinen Blöcken anzuzeigen, die sich leicht verwalten lassen.</span><span class="sxs-lookup"><span data-stu-id="3b692-104">This is a common practice for displaying results to a user in small, easy-to-manage chunks.</span></span>  
  
 <span data-ttu-id="3b692-105">Der **DataAdapter** bietet eine Möglichkeit, nur eine Datenseite über über Ladungen der **Fill** -Methode zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="3b692-105">The **DataAdapter** provides a facility for returning only a page of data, through overloads of the **Fill** method.</span></span> <span data-ttu-id="3b692-106">Dies ist jedoch möglicherweise nicht die beste Wahl für das Paging durch große Abfrageergebnisse, denn obwohl der **DataAdapter** das Ziel <xref:System.Data.DataTable> oder <xref:System.Data.DataSet> nur die angeforderten Datensätze füllt, werden die Ressourcen, die die gesamte Abfrage zurückgeben, weiterhin verwendet.</span><span class="sxs-lookup"><span data-stu-id="3b692-106">However, this might not be the best choice for paging through large query results because, although the **DataAdapter** fills the target <xref:System.Data.DataTable> or <xref:System.Data.DataSet> with only the requested records, the resources to return the entire query are still used.</span></span> <span data-ttu-id="3b692-107">Geben Sie zusätzliche Kriterien für Ihre Abfrage ein, um eine Seite mit Daten von einer Datenquelle ohne die Ressourcen zurückzugeben, die zum Zurückgeben der gesamten Abfrage erforderlich sind, sodass nur die erforderlichen Zeilen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3b692-107">To return a page of data from a data source without using the resources to return the entire query, specify additional criteria for your query that reduce the rows returned to only those required.</span></span>  
  
 <span data-ttu-id="3b692-108">Um die **Fill** -Methode zum Zurückgeben einer Datenseite zu verwenden, geben Sie für den ersten Datensatz auf der Datenseite einen **startRecord** -Parameter und einen **maxRecords** -Parameter für die Anzahl der Datensätze auf der Datenseite an.</span><span class="sxs-lookup"><span data-stu-id="3b692-108">To use the **Fill** method to return a page of data, specify a **startRecord** parameter, for the first record in the page of data, and a **maxRecords** parameter, for the number of records in the page of data.</span></span>  
  
 <span data-ttu-id="3b692-109">Im folgenden Codebeispiel wird gezeigt, wie die **Fill** -Methode verwendet wird, um die erste Seite eines Abfrage Ergebnisses zurückzugeben, bei der die Seitengröße fünf Datensätze ist.</span><span class="sxs-lookup"><span data-stu-id="3b692-109">The following code example shows how to use the **Fill** method to return the first page of a query result where the page size is five records.</span></span>  
  
```vb  
Dim currentIndex As Integer = 0  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT * FROM dbo.Orders ORDER BY OrderID"  
' Assumes that connection is a valid SqlConnection object.  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
int currentIndex = 0;  
int pageSize = 5;  
  
string orderSQL = "SELECT * FROM Orders ORDER BY OrderID";  
// Assumes that connection is a valid SqlConnection object.  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 <span data-ttu-id="3b692-110">Im vorherigen Beispiel ist das **DataSet** nur mit fünf Datensätzen gefüllt, aber die gesamte **Orders** -Tabelle wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3b692-110">In the previous example, the **DataSet** is only filled with five records, but the entire **Orders** table is returned.</span></span> <span data-ttu-id="3b692-111">Um das **DataSet** mit denselben fünf Datensätzen zu füllen, aber nur fünf Datensätze zurückgeben, verwenden Sie die Top-Klausel und die WHERE-Klausel in der SQL-Anweisung, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3b692-111">To fill the **DataSet** with those same five records, but only return five records, use the TOP and WHERE clauses in your SQL statement, as in the following code example.</span></span>  
  
```vb  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT TOP " & pageSize & _  
  " * FROM Orders ORDER BY OrderID"  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Orders")
```  
  
```csharp  
int pageSize = 5;  
  
string orderSQL = "SELECT TOP " + pageSize +
  " * FROM Orders ORDER BY OrderID";  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Orders");  
```  
  
 <span data-ttu-id="3b692-112">Wenn Sie die Abfrageergebnisse auf diese Weise durchgehen, müssen Sie den eindeutigen Bezeichner, nach dem die Zeilen geordnet sind, beibehalten, um die eindeutige ID an den Befehl zu übergeben und die nächste Seite mit Datensätzen zurückzugeben (siehe folgendes Codebeispiel).</span><span class="sxs-lookup"><span data-stu-id="3b692-112">Note that, when paging through the query results in this way, you must preserve the unique identifier that orders the rows, in order to pass the unique ID to the command to return the next page of records, as shown in the following code example.</span></span>  
  
```vb  
Dim lastRecord As String = _  
  dataSet.Tables("Orders").Rows(pageSize - 1)("OrderID").ToString()  
```  
  
```csharp  
string lastRecord =
  dataSet.Tables["Orders"].Rows[pageSize - 1]["OrderID"].ToString();  
```  
  
 <span data-ttu-id="3b692-113">Um die nächste Seite mit Datensätzen zurückzugeben, indem Sie die Überladung der **Fill** -Methode verwenden, die die Parameter **startRecord** und **maxRecords** annimmt, erhöhen Sie den aktuellen Daten Satz Index um die Seitengröße, und füllen Sie die Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="3b692-113">To return the next page of records using the overload of the **Fill** method that takes the **startRecord** and **maxRecords** parameters, increment the current record index by the page size and fill the table.</span></span> <span data-ttu-id="3b692-114">Beachten Sie, dass der Datenbankserver die gesamten Abfrageergebnisse zurückgibt, obwohl nur eine Seite mit Datensätzen dem **DataSet**hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="3b692-114">Remember that the database server returns the entire query results even though only one page of records is added to the **DataSet**.</span></span> <span data-ttu-id="3b692-115">Im folgenden Codebeispiel wird der Inhalt der Tabellenzeilen gelöscht, bevor sie mit der nächsten Seite mit Daten gefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="3b692-115">In the following code example, the table rows are cleared before they are filled with the next page of data.</span></span> <span data-ttu-id="3b692-116">Möglicherweise soll eine bestimmte Anzahl zurückgegebener Zeilen in einem lokalen Cache beibehalten werden, um die Anzahl der Schleifen zum Datenbankserver zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="3b692-116">You might want to preserve a certain number of returned rows in a local cache to reduce trips to the database server.</span></span>  
  
```vb  
currentIndex = currentIndex + pageSize  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
currentIndex += pageSize;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 <span data-ttu-id="3b692-117">Geben Sie restriktive Kriterien für die SQL-Anweisung SELECT an, um die nächste Seite mit Datensätzen zurückzugeben, ohne dass der Datenbankserver die gesamte Abfrage zurückgeben muss.</span><span class="sxs-lookup"><span data-stu-id="3b692-117">To return the next page of records without having the database server return the entire query, specify restrictive criteria to the SELECT statement.</span></span> <span data-ttu-id="3b692-118">Da im vorhergehenden Beispiel der zuletzt zurückgegebene Datensatz beibehalten wurde, können Sie ihn in der WHERE-Klausel verwenden, um – wie im folgenden Codebeispiel gezeigt – einen Ausgangspunkt für die Abfrage anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3b692-118">Because the preceding example preserved the last record returned, you can use it in the WHERE clause to specify a starting point for the query, as shown in the following code example.</span></span>  
  
```vb  
orderSQL = "SELECT TOP " & pageSize & _  
  " * FROM Orders WHERE OrderID > " & lastRecord & " ORDER BY OrderID"  
adapter.SelectCommand.CommandText = orderSQL  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, "Orders")  
```  
  
```csharp  
orderSQL = "SELECT TOP " + pageSize +
  " * FROM Orders WHERE OrderID > " + lastRecord + " ORDER BY OrderID";  
adapter.SelectCommand.CommandText = orderSQL;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, "Orders");  
```  
  
## <a name="see-also"></a><span data-ttu-id="3b692-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3b692-119">See also</span></span>

- [<span data-ttu-id="3b692-120">"DataAdapters" und "DataReaders"</span><span class="sxs-lookup"><span data-stu-id="3b692-120">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="3b692-121">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3b692-121">ADO.NET Overview</span></span>](ado-net-overview.md)
