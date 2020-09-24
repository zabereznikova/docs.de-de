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
# <a name="updating-data-in-a-data-source"></a>Aktualisieren von Daten in einer Datenquelle

SQL-Anweisungen, mit denen Daten geändert werden (z. B. INSERT, UPDATE oder DELETE), geben keine Zeilen zurück. Ähnlich verhält es sich mit vielen gespeicherten Prozeduren, die zwar eine Aktion durchführen, jedoch keine Zeilen zurückgeben. Zum Ausführen von Befehlen, die keine Zeilen zurückgeben, erstellen Sie ein **Command** -Objekt mit dem entsprechenden SQL-Befehl und einer **Verbindung**, einschließlich aller erforderlichen **Parameter**. Führen Sie den Befehl mit der **ExecuteNonQuery** -Methode des **Command** -Objekts aus.  
  
 Die **ExecuteNonQuery** -Methode gibt eine ganze Zahl zurück, die die Anzahl der von der ausgeführten-Anweisung oder gespeicherten Prozedur betroffenen Zeilen darstellt. Wenn mehrere Anweisungen ausgeführt werden, entspricht der zurückgegebene Wert der Summe der Datensätze, die von allen ausgeführten Anweisungen betroffen sind.  
  
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
  
 Im folgenden Codebeispiel wird die gespeicherte Prozedur ausgeführt, die vom Beispielcode bei der [Ausführung von Katalog Vorgängen](performing-catalog-operations.md)erstellt wurde. Von der gespeicherten Prozedur werden keine Zeilen zurückgegeben, sodass die **ExecuteNonQuery** -Methode verwendet wird, aber die gespeicherte Prozedur empfängt einen Eingabeparameter und gibt einen Output-Parameter und einen Rückgabewert zurück.  
  
 Für das- <xref:System.Data.OleDb.OleDbCommand> Objekt muss der **ReturnValue** -Parameter zuerst der **Parameter** Auflistung hinzugefügt werden.  
  
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
- [Aktualisieren von Datenquellen mit "DataAdapters"](updating-data-sources-with-dataadapters.md)
- [Befehle und Parameter](commands-and-parameters.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
