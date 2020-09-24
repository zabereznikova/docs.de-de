---
title: Aktualisieren von Daten in einer Datenquelle
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 55c545e5-dcd5-4323-a5b9-3825c2157462
ms.openlocfilehash: 6b0234337c85ace0797d75b72560ccb55635daae
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177266"
---
# <a name="updating-data-in-a-data-source"></a><span data-ttu-id="097f7-102">Aktualisieren von Daten in einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="097f7-102">Updating Data in a Data Source</span></span>

<span data-ttu-id="097f7-103">SQL-Anweisungen, mit denen Daten geändert werden (z. B. INSERT, UPDATE oder DELETE), geben keine Zeilen zurück.</span><span class="sxs-lookup"><span data-stu-id="097f7-103">SQL statements that modify data (such as INSERT, UPDATE, or DELETE) do not return rows.</span></span> <span data-ttu-id="097f7-104">Ähnlich verhält es sich mit vielen gespeicherten Prozeduren, die zwar eine Aktion durchführen, jedoch keine Zeilen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="097f7-104">Similarly, many stored procedures perform an action but do not return rows.</span></span> <span data-ttu-id="097f7-105">Zum Ausführen von Befehlen, die keine Zeilen zurückgeben, erstellen Sie ein **Command** -Objekt mit dem entsprechenden SQL-Befehl und einer **Verbindung**, einschließlich aller erforderlichen **Parameter**.</span><span class="sxs-lookup"><span data-stu-id="097f7-105">To execute commands that do not return rows, create a **Command** object with the appropriate SQL command and a **Connection**, including any required **Parameters**.</span></span> <span data-ttu-id="097f7-106">Führen Sie den Befehl mit der **ExecuteNonQuery** -Methode des **Command** -Objekts aus.</span><span class="sxs-lookup"><span data-stu-id="097f7-106">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="097f7-107">Die **ExecuteNonQuery** -Methode gibt eine ganze Zahl zurück, die die Anzahl der von der ausgeführten-Anweisung oder gespeicherten Prozedur betroffenen Zeilen darstellt.</span><span class="sxs-lookup"><span data-stu-id="097f7-107">The **ExecuteNonQuery** method returns an integer that represents the number of rows affected by the statement or stored procedure that was executed.</span></span> <span data-ttu-id="097f7-108">Wenn mehrere Anweisungen ausgeführt werden, entspricht der zurückgegebene Wert der Summe der Datensätze, die von allen ausgeführten Anweisungen betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="097f7-108">If multiple statements are executed, the value returned is the sum of the records affected by all of the statements executed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="097f7-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="097f7-109">Example</span></span>  

 <span data-ttu-id="097f7-110">Im folgenden Codebeispiel wird eine INSERT-Anweisung ausgeführt, um einen Datensatz mithilfe von **ExecuteNonQuery**in eine Datenbank einzufügen.</span><span class="sxs-lookup"><span data-stu-id="097f7-110">The following code example executes an INSERT statement to insert a record into a database using **ExecuteNonQuery**.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
connection.Open()  
  
Dim queryString As String = "INSERT INTO Customers " & _  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
Dim recordsAffected As Int32 = command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
connection.Open();  
  
string queryString = "INSERT INTO Customers " +  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
Int32 recordsAffected = command.ExecuteNonQuery();  
```  
  
 <span data-ttu-id="097f7-111">Im folgenden Codebeispiel wird die gespeicherte Prozedur ausgeführt, die vom Beispielcode bei der [Ausführung von Katalog Vorgängen](performing-catalog-operations.md)erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="097f7-111">The following code example executes the stored procedure created by the sample code in [Performing Catalog Operations](performing-catalog-operations.md).</span></span> <span data-ttu-id="097f7-112">Von der gespeicherten Prozedur werden keine Zeilen zurückgegeben, sodass die **ExecuteNonQuery** -Methode verwendet wird, aber die gespeicherte Prozedur empfängt einen Eingabeparameter und gibt einen Output-Parameter und einen Rückgabewert zurück.</span><span class="sxs-lookup"><span data-stu-id="097f7-112">No rows are returned by the stored procedure, so the **ExecuteNonQuery** method is used, but the stored procedure does receive an input parameter and returns an output parameter and a return value.</span></span>  
  
 <span data-ttu-id="097f7-113">Für das- <xref:System.Data.OleDb.OleDbCommand> Objekt muss der **ReturnValue** -Parameter zuerst der **Parameter** Auflistung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="097f7-113">For the <xref:System.Data.OleDb.OleDbCommand> object, the **ReturnValue** parameter must be added to the **Parameters** collection first.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim command As SqlCommand = _  
   New SqlCommand("InsertCategory" , connection)  
command.CommandType = CommandType.StoredProcedure  
  
Dim parameter As SqlParameter = _  
 command.Parameters.Add("@RowCount", SqlDbType.Int)  
parameter.Direction = ParameterDirection.ReturnValue  
  
parameter = command.Parameters.Add( _  
  "@CategoryName", SqlDbType.NChar, 15)  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int)  
parameter.Direction = ParameterDirection.Output  
  
command.Parameters("@CategoryName").Value = "New Category"  
command.ExecuteNonQuery()  
  
Dim categoryID As Int32 = CInt(command.Parameters("@Identity").Value)  
Dim rowCount As Int32 = CInt(command.Parameters("@RowCount").Value)
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlCommand command = new SqlCommand("InsertCategory" , connection);  
command.CommandType = CommandType.StoredProcedure;  
  
SqlParameter parameter = command.Parameters.Add(  
  "@RowCount", SqlDbType.Int);  
parameter.Direction = ParameterDirection.ReturnValue;  
  
parameter = command.Parameters.Add(  
  "@CategoryName", SqlDbType.NChar, 15);  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int);  
parameter.Direction = ParameterDirection.Output;  
  
command.Parameters["@CategoryName"].Value = "New Category";  
command.ExecuteNonQuery();  
  
Int32 categoryID = (Int32) command.Parameters["@Identity"].Value;  
Int32 rowCount = (Int32) command.Parameters["@RowCount"].Value;  
```  
  
## <a name="see-also"></a><span data-ttu-id="097f7-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="097f7-114">See also</span></span>

- [<span data-ttu-id="097f7-115">Verwenden von Befehlen zum Ändern von Daten</span><span class="sxs-lookup"><span data-stu-id="097f7-115">Using Commands to Modify Data</span></span>](using-commands-to-modify-data.md)
- [<span data-ttu-id="097f7-116">Aktualisieren von Datenquellen mit "DataAdapters"</span><span class="sxs-lookup"><span data-stu-id="097f7-116">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="097f7-117">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="097f7-117">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="097f7-118">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="097f7-118">ADO.NET Overview</span></span>](ado-net-overview.md)
