---
title: "Aktualisieren von Daten in einer Datenquelle | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 55c545e5-dcd5-4323-a5b9-3825c2157462
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Aktualisieren von Daten in einer Datenquelle
SQL\-Anweisungen, mit denen Daten geändert werden \(z. B. INSERT, UPDATE oder DELETE\), geben keine Zeilen zurück.  Ähnlich verhält es sich mit vielen gespeicherten Prozeduren, die zwar eine Aktion durchführen, jedoch keine Zeilen zurückgeben.  Zum Ausführen von Befehlen, die keine Zeilen zurückgeben, erstellen Sie ein **Command**\-Objekt mit dem entsprechenden SQL\-Befehl und ein **Connection**\-Objekt, einschließlich der erforderlichen **Parameter**\-Werten.  Führen Sie den Befehl mit der **ExecuteNonQuery**\-Methode des **Command**\-Objekts aus.  
  
 Die **ExecuteNonQuery**\-Methode gibt eine ganze Zahl zurück, die der Anzahl der Zeilen entspricht, auf die die ausgeführte Anweisung oder gespeicherte Prozedur angewendet wurde.  Wenn mehrere Anweisungen ausgeführt werden, entspricht der zurückgegebene Wert der Summe der Datensätze, die von allen ausgeführten Anweisungen betroffen sind.  
  
## Beispiel  
 Im folgenden Codebeispiel wird eine INSERT\-Anweisung ausgeführt, um einen Datensatz mithilfe von **ExecuteNonQuery** in einer Datenbank einzufügen.  
  
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
  
 Im folgenden Codebeispiel wird die gespeicherte Prozedur ausgeführt, die vom Beispielcode unter [Ausführen von Katalogoperationen](../../../../docs/framework/data/adonet/performing-catalog-operations.md) erstellt wurde.  Da von der gespeicherten Prozedur keine Zeilen zurückgegeben werden, wird die **ExecuteNonQuery**\-Methode verwendet. Die gespeicherte Prozedur empfängt jedoch einen Eingabeparameter und gibt einen Ausgabeparameter und einen Rückgabewert zurück.  
  
 Für das <xref:System.Data.OleDb.OleDbCommand>\-Objekt muss zuerst der **ReturnValue**\-Parameter der **Parameters**\-Auflistung hinzugefügt werden.  
  
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
  
## Siehe auch  
 [Verwenden von Befehlen zum Ändern von Daten](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)   
 [Aktualisieren von Datenquellen mit DataAdapters](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)   
 [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)