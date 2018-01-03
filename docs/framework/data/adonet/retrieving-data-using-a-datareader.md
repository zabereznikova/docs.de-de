---
title: Abrufen von Daten mit "DataReader"
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
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: b36f76516d4ddf94e177a5ecbb705e1d729318b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="retrieving-data-using-a-datareader"></a>Abrufen von Daten mit "DataReader"
Abrufen von Daten mittels einer **DataReader** umfasst das Erstellen einer Instanz von der **Befehl** Objekt und der anschließenden Erstellung eine **DataReader** durch Aufrufen von  **Command.ExecuteReader** zum Abrufen von Zeilen aus einer Datenquelle. Im folgende Beispiel wird die Verwendung einer **DataReader** , in denen `reader` gültige "DataReader" darstellt und `command` ein gültiges Command-Objekt darstellt.  
  
```  
reader = command.ExecuteReader();  
```  
  
 Verwenden Sie die **lesen** Methode der **DataReader** Objekt um eine Zeile aus den Ergebnissen der Abfrage abzurufen. Sie können jede Spalte der zurückgegebenen Zeile zugreifen, übergeben den Namen oder den Ordinalzahlverweis der Spalte, die die **DataReader**. Allerdings für eine optimale Leistung der **DataReader** enthält eine Reihe von Methoden, die Sie auf Spaltenwerte in ihren systemeigenen Datentypen zugreifen können (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**usw.). Eine Liste der typisierten Accessormethoden für anbieterspezifische **DataReaders**, finden Sie unter <xref:System.Data.OleDb.OleDbDataReader> und <xref:System.Data.SqlClient.SqlDataReader>. Mit den typisierten Zugriffsmethoden wird der Aufwand für Typumwandlungen beim Abrufen eines Spaltenwerts reduziert, vorausgesetzt, der zugrunde liegende Datentyp ist bekannt.  
  
> [!NOTE]
>  Die Windows Server 2003-Version von .NET Framework enthält eine zusätzliche Eigenschaft für die **DataReader**, **HasRows**, wodurch Sie zum bestimmen, ob die **DataReader**Ergebnisse vor dem Lesen von ihr zurückgegeben hat.  
  
 Im folgenden Codebeispiel durchläuft ein **DataReader** Objekt und zwei Spalten aus jeder Zeile zurückgegeben.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
 Die **DataReader** enthält einen nicht gepufferten Datenstream von Daten, die prozeduralen Logik, die Ergebnisse aus einer Datenquelle effektiv sequenziell zu verarbeiten zu können. Die **DataReader** ist eine gute Wahl, wenn große Mengen an Daten abgerufen werden, da die Daten nicht im Arbeitsspeicher zwischengespeichert werden.  
  
## <a name="closing-the-datareader"></a>Schließen des "DataReader"  
 Sie sollten immer aufrufen, die **schließen** Methode, wenn Sie aufgehört haben die **DataReader** Objekt.  
  
 Wenn Ihre **Befehl** Ausgabe enthält Parameter oder Rückgabewerte werden ist erst verfügbar, die **DataReader** geschlossen wird.  
  
 Beachten Sie, dass eine **DataReader** geöffnet ist, wird die **Verbindung** wird verwendet, die ausschließlich vom **DataReader**. Befehle für kann nicht ausgeführt werden kann die **Verbindung**, einschließlich der Erstellung eines weiteren **DataReader**, bis die ursprüngliche **DataReader** geschlossen wird.  
  
> [!NOTE]
>  Rufen Sie nicht **schließen** oder **Dispose** auf eine **Verbindung**, **DataReader**, oder ein anderes verwaltetes Objekt in der **Finalize**  -Methode der Klasse. Geben Sie in einer Finalize-Methode nur nicht verwaltete Ressourcen frei, die der Klasse direkt gehören. Wenn Ihre Klasse keine nicht verwalteten Ressourcen besitzt, schließen Sie keine **Finalize** Methode in der Klasse. Weitere Informationen finden Sie unter [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>Abrufen mehrerer Resultsets mit "NextResult"  
 Wenn mehrere Resultsets zurückgegeben werden, die **DataReader** bietet die **NextResult** Methode zum iterieren durch das Ergebnis legt fest, in der Reihenfolge. Im folgenden Beispiel werden die Ergebnisse von zwei SELECT-Anweisungen mit der <xref:System.Data.SqlClient.SqlDataReader>-Methode von <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> verarbeitet.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>Abrufen von Schemainformationen aus dem "DataReader"  
 Während einer **DataReader** ist geöffnet ist, können die Schemainformationen über das aktuelle Resultset mit Abrufen der **GetSchemaTable** Methode. **GetSchemaTable** gibt ein <xref:System.Data.DataTable> Objekt, das mit Zeilen und Spalten, die die Schemainformationen für das aktuelle Resultset enthalten. Die **DataTable** enthält eine Zeile für jede Spalte des Resultsets. Jede Spalte der Schematabellenzeile ordnet eine Eigenschaft der Spalte zurückgegeben wird, das Resultset, in dem die **ColumnName** ist der Name der Eigenschaft und der Wert der Spalte ist der Wert der Eigenschaft. Im folgenden Codebeispiel wird die Schemainformationen für schreibt **DataReader**.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>Arbeiten mit OLE DB-Kapiteln  
 Hierarchische Rowsets oder Kapitel (OLE DB-Typ **DBTYPE_HCHAPTER**, ADO-Typ **AdChapter**) können abgerufen werden, mithilfe der <xref:System.Data.OleDb.OleDbDataReader>. Bei Rückgabe eine Abfrage, die einem Kapitel als eine **DataReader**, im Kapitel als Spalte in diesem zurückgegeben **DataReader** und verfügbar gemacht wird als eine **DataReader** Objekt.  
  
 Das ADO.NET **DataSet** kann auch zur Darstellung von hierarchischen Rowsets, die mit über-und untergeordneten Beziehungen zwischen Tabellen verwendet werden. Weitere Informationen finden Sie unter [DataSets und Datentabellen "DataViews"](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).  
  
 Im folgenden Codebeispiel wird mit dem MSDataShape-Anbieter eine Kapitelspalte mit Bestellungen für jeden Kunden in einer Kundenliste generiert.  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a>Zurückgeben von Ergebnissen mit Oracle-REF CURSORn  
 Der .NET Framework-Datenanbieter für Oracle unterstützt die Verwendung von Oracle-REF CURSORs zur Rückgabe eines Abfrageergebnisses. Ein Oracle-REF CURSOR wird als <xref:System.Data.OracleClient.OracleDataReader> zurückgegeben.  
  
 Abgerufen werden kann ein **OracleDataReader** Objekt, das eine Oracle-REF CURSOR mit darstellt der <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> Methode, und Sie können auch angeben, ein <xref:System.Data.OracleClient.OracleCommand> , die eine oder mehrere Oracle-REF CURSORs als zurückgibt der  **SelectCommand** für eine <xref:System.Data.OracleClient.OracleDataAdapter> zum Füllen einer <xref:System.Data.DataSet>.  
  
 Um aus einer Oracle-Datenquelle zurückgegebenen REF CURSOR zuzugreifen, erstellen Sie ein **OracleCommand** für Ihre Abfrage und fügen Sie einen Output-Parameter, die den REF CURSOR verweist auf die **Parameter** Auflistung von Ihrem  **OracleCommand**. Der Name des Parameters muss mit dem Namen des REF CURSOR-Parameters in der Abfrage übereinstimmen. Legen Sie den Typ des Parameters, der **OracleType.Cursor**. Die **ExecuteReader** Methode Ihrer **OracleCommand** zurück ein **OracleDataReader** für den REF CURSOR.  
  
 Wenn Ihre **OracleCommand** mehrere REF CURSORS zurückgibt Hinzufügen mehrerer Output-Parameter. Sie können die verschiedenen REF CURSORs zugreifen, durch Aufrufen der **OracleCommand.ExecuteReader** Methode. Der Aufruf von **ExecuteReader** gibt eine **OracleDataReader** auf den ersten REF CURSOR verweist. Rufen Sie dann die **OracleDataReader.NextResult** Methode, um die nachfolgenden REF CURSORs zugreifen. Obwohl die Parameter in Ihre **OracleCommand.Parameters** Auflistung Übereinstimmung den REF CURSOR-Ausgabeparameter anhand des Namens, der **OracleDataReader** greift auf sie in der Reihenfolge, in der hinzugefügtwurden **Parameter** Auflistung.  
  
 	Betrachten Sie z. B. das folgende Oracle-Paket und den Paketkörper.  
  
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
  
 Der folgende Code erstellt ein **OracleCommand** , der die REF CURSORs aus dem vorherigen Oracle-Paket zurückgibt, durch Hinzufügen von zwei Parametern vom Typ **OracleType.Cursor** auf die **Parameter** Auflistung.  
  
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
  
 Der folgende Code gibt die Ergebnisse der vorherigen Befehl unter Verwendung der **lesen** und **NextResult** Methoden die **OracleDataReader**. Die REF CURSOR-Parameter werden der Reihe nach zurückgegeben.  
  
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
  
 Im folgenden Beispiel wird den vorherigen Befehl zum Auffüllen einer **DataSet** mit den Ergebnissen des Oracle-Pakets.  
  
> [!NOTE]
>  Zur Vermeidung einer **OverflowException**, es wird empfohlen, dass Sie auch Konvertierung von Oracle-Typ NUMBER in einen gültigen .NET Framework-Typ vor dem Speichern des Werts in Behandeln einer **DataRow**. Können Sie die **FillError** Ereignis, um festzustellen, wo ein **OverflowException** aufgetreten. Weitere Informationen zu den **FillError** -Ereignis finden Sie unter [Behandeln von DataAdapter-Ereignissen](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit DataReaders](http://msdn.microsoft.com/en-us/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [DataAdapters und DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Abrufen von Datenbankschemainformationen](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
