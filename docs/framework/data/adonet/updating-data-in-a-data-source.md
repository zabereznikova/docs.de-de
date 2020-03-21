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
# <a name="updating-data-in-a-data-source"></a>Aktualisieren von Daten in einer Datenquelle
SQL-Anweisungen, mit denen Daten geändert werden (z. B. INSERT, UPDATE oder DELETE), geben keine Zeilen zurück. Ähnlich verhält es sich mit vielen gespeicherten Prozeduren, die zwar eine Aktion durchführen, jedoch keine Zeilen zurückgeben. Um Befehle auszuführen, die keine Zeilen zurückgeben, erstellen Sie ein **Command-Objekt** mit dem entsprechenden SQL-Befehl und einer **Verbindung**, einschließlich aller erforderlichen **Parameter**. Führen Sie den Befehl mit der **ExecuteNonQuery-Methode** des **Command-Objekts** aus.  
  
 Die **ExecuteNonQuery-Methode** gibt eine ganze Zahl zurück, die die Anzahl der Zeilen darstellt, die von der ausgeführten Anweisung oder gespeicherten Prozedur betroffen sind. Wenn mehrere Anweisungen ausgeführt werden, entspricht der zurückgegebene Wert der Summe der Datensätze, die von allen ausgeführten Anweisungen betroffen sind.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine INSERT-Anweisung ausgeführt, um einen Datensatz mithilfe von **ExecuteNonQuery**in eine Datenbank einzufügen.  
  
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
  
 Im folgenden Codebeispiel wird die gespeicherte Prozedur ausgeführt, die vom Beispielcode unter [Ausführen von Katalogvorgängen](performing-catalog-operations.md)erstellt wurde. Die gespeicherte Prozedur gibt keine Zeilen zurück, daher wird die **ExecuteNonQuery-Methode** verwendet, aber die gespeicherte Prozedur empfängt einen Eingabeparameter und gibt einen Ausgabeparameter und einen Rückgabewert zurück.  
  
 Für <xref:System.Data.OleDb.OleDbCommand> das Objekt muss der **ReturnValue-Parameter** zuerst der **Parameters-Auflistung** hinzugefügt werden.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Befehlen zum Ändern von Daten](using-commands-to-modify-data.md)
- [Updating Data Sources with DataAdapters (Aktualisieren von Datenquellen mit DataAdapters)](updating-data-sources-with-dataadapters.md)
- [Befehle und Parameter](commands-and-parameters.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
