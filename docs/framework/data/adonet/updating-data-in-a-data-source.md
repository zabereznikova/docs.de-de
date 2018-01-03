---
title: Aktualisieren von Daten in einer Datenquelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 55c545e5-dcd5-4323-a5b9-3825c2157462
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: c83b137f0de5ee165d110706dc286d13a084427c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="updating-data-in-a-data-source"></a>Aktualisieren von Daten in einer Datenquelle
SQL-Anweisungen, mit denen Daten geändert werden (z. B. INSERT, UPDATE oder DELETE), geben keine Zeilen zurück. Ähnlich verhält es sich mit vielen gespeicherten Prozeduren, die zwar eine Aktion durchführen, jedoch keine Zeilen zurückgeben. Zum Ausführen von Befehlen, die keine Zeilen zurückgeben, erstellen Sie eine **Befehl** Objekt mit den entsprechenden SQL-Befehl und einem **Verbindung**, einschließlich der erforderlichen **Parameter**. Führen Sie den Befehl mit der **ExecuteNonQuery** Methode der **Befehl** Objekt.  
  
 Die **ExecuteNonQuery** Methode gibt eine ganze Zahl, die die Anzahl der Zeilen betroffen sind, durch die Anweisung oder gespeicherte Prozedur, die ausgeführt wurde. Wenn mehrere Anweisungen ausgeführt werden, entspricht der zurückgegebene Wert der Summe der Datensätze, die von allen ausgeführten Anweisungen betroffen sind.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel führt eine INSERT-Anweisung zum Einfügen eines Datensatzes in einer Datenbank durch **ExecuteNonQuery**.  
  
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
  
 Das folgende Codebeispiel führt die gespeicherte Prozedur, die erstellt, indem der Beispielcode im [Ausführen von Katalogoperationen](../../../../docs/framework/data/adonet/performing-catalog-operations.md). Keine Zeilen zurückgegeben werden, von der gespeicherten Prozedur, sodass der **ExecuteNonQuery** Methode wird verwendet, aber die gespeicherte Prozedur empfängt einen Eingabeparameter und gibt einen Ausgabeparameter und einen Rückgabewert.  
  
 Für die <xref:System.Data.OleDb.OleDbCommand> -Objekt, das **ReturnValue** Parameter hinzugefügt werden muss die **Parameter** Auflistung erste.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Befehlen zum Ändern von Daten](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)  
 [Updating Data Sources with DataAdapters (Aktualisieren von Datenquellen mit DataAdapters)](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
