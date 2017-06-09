---
title: "Abrufen von Daten mit einem DataReader | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Abrufen von Daten mit einem DataReader
Wenn Sie Daten mit einem **DataReader** abrufen möchten, müssen Sie zunächst eine Instanz des **Command**\-Objekts und anschließend einen **DataReader** erstellen. Rufen Sie hierzu **Command.ExecuteReader** auf, um Zeilen aus einer Datenquelle abzurufen.  Im folgenden Beispiel wird die Verwendung eines **DataReader** gezeigt, wobei `reader` für einen gültigen \<legacyBold\>DataReader\<\/legacyBold\> und `command` für ein gültiges \<legacyBold\>Command\<\/legacyBold\>\-Objekt steht.  
  
```  
reader = command.ExecuteReader();  
```  
  
 Zum Abrufen einer Zeile aus den Abfrageergebnissen verwenden Sie die **Read**\-Methode des **DataReader**\-Objekts.  Sie können auf jede Spalte der zurückgegebenen Zeile zugreifen, indem Sie dem **DataReader** den Namen oder den Ordinalzahlverweis der Spalte übergeben.  Die beste Leistung erzielen Sie jedoch, wenn Sie die vom **DataReader**\-Objekt bereitgestellten Methoden verwenden, mit denen Sie auf Spaltenwerte in ihren systemeigenen Datentypen zugreifen können \(**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32** usw.\).  Eine Liste mit typisierten Accessormethoden für anbieterspezifische **DataReaders** finden Sie unter <xref:System.Data.OleDb.OleDbDataReader> und <xref:System.Data.SqlClient.SqlDataReader>.  Mit den typisierten Accessormethoden wird der Aufwand für Typumwandlungen beim Abrufen eines Spaltenwerts reduziert, vorausgesetzt, der zugrunde liegende Datentyp ist bekannt.  
  
> [!NOTE]
>  In der .NET Framework\-Version für Windows Server 2003 verfügt **DataReader** über die zusätzliche **HasRows**\-Eigenschaft, mit der vor dem Lesen ermittelt werden kann, ob der **DataReader** Ergebnisse zurückgegeben hat.  
  
 Im folgenden Codebeispiel wird ein **DataReader**\-Objekt durchlaufen, und es werden von jeder Zeile zwei Spalten zurückgegeben.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
 Das **DataReader**\-Objekt stellt einen nicht gepufferten Datenstream bereit, mit dem Prozeduren eine effektive, sequenzielle Verarbeitung der Ergebnisse aus einer Datenquelle ermöglicht wird.  Ein **DataReader** ist zu empfehlen, wenn große Datenmengen abgerufen werden, da die Daten nicht zwischengespeichert werden.  
  
## Schließen des "DataReader"  
 Wenn ein **DataReader**\-Objekt nicht mehr benötigt wird, sollte immer die **Close**\-Methode aufgerufen werden.  
  
 Wenn ein **Command** Ausgabeparameter oder Rückgabewerte enthält, sind diese erst nach dem Schließen des **DataReader** verfügbar.  
  
 Beachten Sie, dass die **Connection** ausschließlich vom **DataReader** verwendet wird, solange der **DataReader** geöffnet ist.  Sie können erst dann Befehle für die **Connection** ausführen, z. B. einen anderen **DataReader** erstellen, nachdem der erste **DataReader** geschlossen wurde.  
  
> [!NOTE]
>  Rufen Sie in der **Finalize**\-Methode einer Klasse für **Connection**\-Objekte, **DataReader**\-Objekte oder andere verwaltete Objekte nie **Close** oder **Dispose** auf.  Geben Sie in einer Finalize\-Methode nur nicht verwaltete Ressourcen frei, die der Klasse direkt gehören.  Wenn die Klasse keine nicht verwalteten Ressourcen besitzt, definieren Sie in der Klasse keine **Finalize**\-Methode.  Weitere Informationen finden Sie unter [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).  
  
## Abrufen mehrerer Resultsets mit "NextResult"  
 Wenn mehrere Resultsets zurückgegeben werden, können diese mit der **NextResult**\-Methode von **DataReader** der Reihe nach durchlaufen werden.  Im folgenden Beispiel werden die Ergebnisse von zwei SELECT\-Anweisungen mit der <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>\-Methode von <xref:System.Data.SqlClient.SqlDataReader> verarbeitet.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## Abrufen von Schemainformationen aus dem "DataReader"  
 So lange ein **DataReader** geöffnet ist, können mit der **GetSchemaTable**\-Methode Schemainformationen über das aktuelle Resultset abgerufen werden.  **GetSchemaTable** gibt ein <xref:System.Data.DataTable>\-Objekt zurück, das mit Zeilen und Spalten gefüllt ist, die die Schemainformationen für das aktuelle Resultset enthalten.  Die **DataTable** enthält eine Zeile für jede Spalte des Resultset.  Jede Spalte der Schematabellenzeile ist einer Eigenschaft der im Resultset zurückgegebenen Spalte zugeordnet, wobei **ColumnName** der Name der Eigenschaft und der Spaltenwert der Wert der Eigenschaft ist.  Im folgenden Codebeispiel werden die Schemainformationen für **DataReader** geschrieben.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## Arbeiten mit OLE DB\-Kapiteln  
 Hierarchische Rowsets oder Kapitel \(OLE DB\-Typ **DBTYPE\_HCHAPTER**, ADO\-Typ **adChapter**\) können mit dem <xref:System.Data.OleDb.OleDbDataReader> abgerufen werden.  Wenn eine Abfrage mit einem Kapitel als **DataReader** zurückgegeben wird, wird das Kapitel als Spalte in diesem **DataReader** zurückgegeben und als **DataReader**\-Objekt verfügbar gemacht.  
  
 Mit dem ADO.NET\-**DataSet** können auch hierarchische Rowsets dargestellt werden, die über\- und untergeordnete Tabellen verwenden.  Weitere Informationen finden Sie unter [DataSets, DataTables und DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).  
  
 Im folgenden Codebeispiel wird mit dem MSDataShape\-Anbieter eine Kapitelspalte mit Bestellungen für jeden Kunden in einer Kundenliste generiert.  
  
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
  
## Zurückgeben von Ergebnissen mit Oracle\-REF CURSORn  
 Der .NET Framework\-Datenanbieter für Oracle unterstützt die Verwendung von Oracle\-REF CURSORs zur Rückgabe eines Abfrageergebnisses.  Ein Oracle\-REF CURSOR wird als <xref:System.Data.OracleClient.OracleDataReader> zurückgegeben.  
  
 Sie können ein **OracleDataReader**\-Objekt, das einen Oracle\-REF CURSOR darstellt, mit der <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>\-Methode abrufen. Außerdem können Sie für einen <xref:System.Data.OracleClient.OracleDataAdapter>, der zum Auffüllen eines <xref:System.Data.DataSet> verwendet wird, ein <xref:System.Data.OracleClient.OracleCommand> angeben, das einen oder mehrere Oracle\-REF CURSORs als **SelectCommand** zurückgibt.  
  
 Erstellen Sie zum Zugreifen auf einen von einer Oracle\-Datenquelle zurückgegebenen REF CURSOR einen **OracleCommand** für die Abfrage, und fügen Sie der **Parameters**\-Auflistung des **OracleCommand** einen Ausgabeparameter hinzu, der auf den REF CURSOR verweist.  Der Name des Parameters muss mit dem Namen des REF CURSOR\-Parameters in der Abfrage übereinstimmen.  Legen Sie den Typ des Parameters auf **OracleType.Cursor** fest.  Die **ExecuteReader**\-Methode des **OracleCommand** gibt einen **OracleDataReader** für den REF CURSOR zurück.  
  
 Wenn der **OracleCommand** mehrere REF CURSORs zurückgibt, fügen Sie mehrere Ausgabeparameter hinzu.  Durch Aufrufen der **OracleCommand.ExecuteReader**\-Methode können Sie auf die verschiedenen REF CURSORs zugreifen.  Durch Aufrufen von **ExecuteReader** wird ein **OracleDataReader** zurückgegeben, der auf den ersten REF CURSOR verweist.  Sie können dann mit der **OracleDataReader.NextResult**\-Methode auf die nachfolgenden REF CURSORs zugreifen.  Obwohl die Parameter der **OracleCommand.Parameters**\-Auflistung dem Namen nach den REF CURSOR\-Ausgabeparametern entsprechen, greift der **OracleDataReader** auf diese in der Reihenfolge zu, in der sie der **Parameters**\-Auflistung hinzugefügt wurden.  
  
 Betrachten Sie z. B. das folgende Oracle\-Paket und den Paketkörper.  
  
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
  
 Im folgenden Codebeispiel wird ein **OracleCommand** erstellt, der die REF CURSORs aus dem oben stehenden Oracle\-Paket zurückgibt. Hierzu werden der **Parameters**\-Auflistung zwei Parameter vom Typ **OracleType.Cursor** hinzugefügt.  
  
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
  
 Im folgenden Codebeispiel werden die Ergebnisse des Befehls aus dem vorherigen Beispiel mit der **Read**\-Methode und der **NextResult**\-Methode des **OracleDataReader** zurückgegeben.  Die REF CURSOR\-Parameter werden der Reihe nach zurückgegeben.  
  
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
  
 Im folgenden Beispiel wird der Befehl aus dem vorherigen Codebeispiel verwendet, um ein **DataSet** mit den Ergebnissen des Oracle\-Pakets aufzufüllen.  
  
> [!NOTE]
>  Zur Vermeidung einer **OverflowException** wird empfohlen, alle notwendigen Konvertierungen vom Oracle\-Typ NUMBER in einen gültigen .NET Framework\-Typ vor dem Speichern des Werts in einer **DataRow** auszuführen.  Mit dem **FillError**\-Ereignis kann festgestellt werden, ob eine **OverflowException** aufgetreten ist.  Weitere Informationen zum **FillError**\-Ereignis finden Sie unter [Umgang mit 'DataAdapter'\-Ereignissen](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
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
  
## Siehe auch  
 [Working with DataReaders](http://msdn.microsoft.com/de-de/126a966a-d08d-4d22-a19f-f432908b2b54)   
 [DataAdapter und DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [Abrufen von Schemainformationen aus einer Datenbank](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)