---
title: Aktualisieren von Daten in einer Datenquelle
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 55c545e5-dcd5-4323-a5b9-3825c2157462
ms.openlocfilehash: 18bb03e17b19243ee1bc6e3f7ebd70afb4d4c60b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174445"
---
# <a name="updating-data-in-a-data-source"></a><span data-ttu-id="f9e0a-102">Aktualisieren von Daten in einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="f9e0a-102">Updating Data in a Data Source</span></span>
<span data-ttu-id="f9e0a-103">SQL-Anweisungen, mit denen Daten geändert werden (z. B. INSERT, UPDATE oder DELETE), geben keine Zeilen zurück.</span><span class="sxs-lookup"><span data-stu-id="f9e0a-103">SQL statements that modify data (such as INSERT, UPDATE, or DELETE) do not return rows.</span></span> <span data-ttu-id="f9e0a-104">Ähnlich verhält es sich mit vielen gespeicherten Prozeduren, die zwar eine Aktion durchführen, jedoch keine Zeilen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="f9e0a-104">Similarly, many stored procedures perform an action but do not return rows.</span></span> <span data-ttu-id="f9e0a-105">Um Befehle auszuführen, die keine Zeilen zurückgeben, erstellen Sie ein **Command-Objekt** mit dem entsprechenden SQL-Befehl und einer **Verbindung**, einschließlich aller erforderlichen **Parameter**.</span><span class="sxs-lookup"><span data-stu-id="f9e0a-105">To execute commands that do not return rows, create a **Command** object with the appropriate SQL command and a **Connection**, including any required **Parameters**.</span></span> <span data-ttu-id="f9e0a-106">Führen Sie den Befehl mit der **ExecuteNonQuery-Methode** des **Command-Objekts** aus.</span><span class="sxs-lookup"><span data-stu-id="f9e0a-106">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="f9e0a-107">Die **ExecuteNonQuery-Methode** gibt eine ganze Zahl zurück, die die Anzahl der Zeilen darstellt, die von der ausgeführten Anweisung oder gespeicherten Prozedur betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="f9e0a-107">The **ExecuteNonQuery** method returns an integer that represents the number of rows affected by the statement or stored procedure that was executed.</span></span> <span data-ttu-id="f9e0a-108">Wenn mehrere Anweisungen ausgeführt werden, entspricht der zurückgegebene Wert der Summe der Datensätze, die von allen ausgeführten Anweisungen betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="f9e0a-108">If multiple statements are executed, the value returned is the sum of the records affected by all of the statements executed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9e0a-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f9e0a-109">Example</span></span>  
 <span data-ttu-id="f9e0a-110">Im folgenden Codebeispiel wird eine INSERT-Anweisung ausgeführt, um einen Datensatz mithilfe von **ExecuteNonQuery**in eine Datenbank einzufügen.</span><span class="sxs-lookup"><span data-stu-id="f9e0a-110">The following code example executes an INSERT statement to insert a record into a database using **ExecuteNonQuery**.</span></span>  
  
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
  
 <span data-ttu-id="f9e0a-111">Im folgenden Codebeispiel wird die gespeicherte Prozedur ausgeführt, die vom Beispielcode unter [Ausführen von Katalogvorgängen](performing-catalog-operations.md)erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="f9e0a-111">The following code example executes the stored procedure created by the sample code in [Performing Catalog Operations](performing-catalog-operations.md).</span></span> <span data-ttu-id="f9e0a-112">Die gespeicherte Prozedur gibt keine Zeilen zurück, daher wird die **ExecuteNonQuery-Methode** verwendet, aber die gespeicherte Prozedur empfängt einen Eingabeparameter und gibt einen Ausgabeparameter und einen Rückgabewert zurück.</span><span class="sxs-lookup"><span data-stu-id="f9e0a-112">No rows are returned by the stored procedure, so the **ExecuteNonQuery** method is used, but the stored procedure does receive an input parameter and returns an output parameter and a return value.</span></span>  
  
 <span data-ttu-id="f9e0a-113">Für <xref:System.Data.OleDb.OleDbCommand> das Objekt muss der **ReturnValue-Parameter** zuerst der **Parameters-Auflistung** hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f9e0a-113">For the <xref:System.Data.OleDb.OleDbCommand> object, the **ReturnValue** parameter must be added to the **Parameters** collection first.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f9e0a-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f9e0a-114">See also</span></span>

- [<span data-ttu-id="f9e0a-115">Verwenden von Befehlen zum Ändern von Daten</span><span class="sxs-lookup"><span data-stu-id="f9e0a-115">Using Commands to Modify Data</span></span>](using-commands-to-modify-data.md)
- [<span data-ttu-id="f9e0a-116">Updating Data Sources with DataAdapters (Aktualisieren von Datenquellen mit DataAdapters)</span><span class="sxs-lookup"><span data-stu-id="f9e0a-116">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="f9e0a-117">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="f9e0a-117">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="f9e0a-118">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f9e0a-118">ADO.NET Overview</span></span>](ado-net-overview.md)
