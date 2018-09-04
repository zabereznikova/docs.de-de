---
title: Abrufen von Daten mit "DataReader"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 4370a7a700a01943548bf067827e6640245caf4e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516790"
---
# <a name="retrieving-data-using-a-datareader"></a>Abrufen von Daten mit "DataReader"
Abrufen von Daten mithilfe einer **DataReader** umfasst das Erstellen einer Instanz von der **Befehl** und klicken Sie dann erstellen, eine **DataReader** durch Aufrufen von  **Command.ExecuteReader** um Zeilen aus einer Datenquelle abzurufen. Das folgende Beispiel veranschaulicht die Verwendung einer **DataReader** , in denen `reader` stellt ein gültiger DataReader-Ziel und `command` ein gültiges Command-Objekt darstellt.  
  
```  
reader = command.ExecuteReader();  
```  
  
 Sie verwenden die **lesen** Methode der **DataReader** Objekt um eine Zeile aus den Ergebnissen der Abfrage abzurufen. Sie können jede Spalte der zurückgegebenen Zeile zugreifen, indem Sie übergeben den Namen oder den Ordinalzahlverweis der Spalte, die die **DataReader**. Allerdings für eine optimale Leistung die **DataReader** enthält eine Reihe von Methoden, die Sie auf Spaltenwerte in deren systemeigenen Datentypen zugreifen können (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**und so weiter). Eine Liste der typisierten Zugriffsmethoden für anbieterspezifische **"DataReaders"**, finden Sie unter <xref:System.Data.OleDb.OleDbDataReader> und <xref:System.Data.SqlClient.SqlDataReader>. Mit den typisierten Zugriffsmethoden wird der Aufwand für Typumwandlungen beim Abrufen eines Spaltenwerts reduziert, vorausgesetzt, der zugrunde liegende Datentyp ist bekannt.  
  
> [!NOTE]
>  Die Windows Server 2003-Version von .NET Framework enthält eine zusätzliche Eigenschaft für die **DataReader**, **HasRows**, sodass Sie bestimmen, ob die **DataReader**Ergebnisse vor dem Lesen von ihr zurückgegeben hat.  
  
 Im folgenden Codebeispiel durchläuft eine **DataReader** Objekt und zwei Spalten aus jeder Zeile zurückgegeben.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
 Die **DataReader** enthält einen nicht gepufferten Datenstream, mit der prozeduralen Logik, die Ergebnisse aus einer Datenquelle effizient sequenziell zu verarbeiten zu können. Die **DataReader** ist eine gute Wahl, wenn große Mengen von Daten abgerufen werden, da die Daten nicht im Arbeitsspeicher zwischengespeichert werden.  
  
## <a name="closing-the-datareader"></a>Schließen des "DataReader"  
 Rufen Sie immer die **schließen** Methode, wenn Sie aufgehört haben die **DataReader** Objekt.  
  
 Wenn Ihre **Befehl** enthält die Ausgabe Parameter oder Rückgabewerte, diese werden nicht erst verfügbar, wenn die **DataReader** geschlossen wird.  
  
 Beachten Sie, dass eine **DataReader** geöffnet ist, die **Verbindung** wird ausschließlich von diesem **DataReader**. Sie können nicht ausgeführt werden Befehle für die **Verbindung**, einschließlich der Erstellung eines weiteren **DataReader**, bis die ursprüngliche **DataReader** geschlossen wird.  
  
> [!NOTE]
>  Rufen Sie nicht **schließen** oder **Dispose** auf eine **Verbindung**, **DataReader**, oder andere verwaltete Objekte in der **abschließen**  Methode der Klasse. Geben Sie in einer Finalize-Methode nur nicht verwaltete Ressourcen frei, die der Klasse direkt gehören. Wenn Ihre Klasse keine nicht verwalteten Ressourcen besitzt, ist nicht enthalten. ein **Finalize** Methode in der Klassendefinition. Weitere Informationen finden Sie unter [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>Abrufen mehrerer Resultsets mit "NextResult"  
 Wenn mehrere Resultsets zurückgegeben werden, die **DataReader** bietet die **NextResult** Methode, um das Ergebnis durchlaufen legt fest, in der Reihenfolge. Im folgenden Beispiel werden die Ergebnisse von zwei SELECT-Anweisungen mit der <xref:System.Data.SqlClient.SqlDataReader>-Methode von <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> verarbeitet.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>Abrufen von Schemainformationen aus dem "DataReader"  
 Während einer **DataReader** ist geöffnet ist, können die Schemainformationen über das aktuelle Resultset mit Abrufen der **GetSchemaTable** Methode. **GetSchemaTable** gibt eine <xref:System.Data.DataTable> -Objekt mit den Zeilen und Spalten, die die Schemainformationen für das aktuelle Resultset enthalten. Die **DataTable** enthält eine Zeile für jede Spalte des Resultsets. Jede Spalte der Schematabellenzeile ordnet eine Eigenschaft der Spalte zurückgegeben wird, das Resultset, in denen die **ColumnName** ist der Name der Eigenschaft und der Wert der Spalte den Wert der Eigenschaft. Im folgenden Codebeispiel schreibt die Schemainformationen für **DataReader**.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>Arbeiten mit OLE DB-Kapiteln  
 Hierarchische Rowsets oder Kapitel (OLE DB-Typ **DBTYPE_HCHAPTER**, ADO-Typ **AdChapter**) können abgerufen werden, mithilfe der <xref:System.Data.OleDb.OleDbDataReader>. Wenn eine Abfrage, die einem Kapitel zurückgegeben wird, als eine **DataReader**, das Kapitel als Spalte in diesem zurückgegeben wird **DataReader** und als verfügbar gemacht wird eine **DataReader** Objekt.  
  
 ADO.NET **DataSet** kann auch zur Darstellung von hierarchischen Rowsets, die mit über-und untergeordnete Beziehungen zwischen Tabellen verwendet werden. Weitere Informationen finden Sie unter [DataSets, DataTables und DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).  
  
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
  
 Können Sie Abrufen einer **OracleDataReader** -Objekt, das eine Oracle-REF CURSOR darstellt der <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> Methode, und Sie können auch angeben, ein <xref:System.Data.OracleClient.OracleCommand> , die eine oder mehrere Oracle-REF CURSORs als zurückgibt der  **SelectCommand** für eine <xref:System.Data.OracleClient.OracleDataAdapter> verwendet, um eine <xref:System.Data.DataSet>.  
  
 Erstellen Sie aus einer Oracle-Datenquelle zurückgegebenen REF CURSOR für den Zugriff auf eine **OracleCommand** für die Abfrage und fügen Sie einen Output-Parameter, die den REF CURSOR verweist die **Parameter** Auflistung von Ihrem  **OracleCommand**. Der Name des Parameters muss mit dem Namen des REF CURSOR-Parameters in der Abfrage übereinstimmen. Legen Sie den Typ des Parameters, der **OracleType.Cursor**. Die **"ExecuteReader"** -Methode der Ihre **OracleCommand** gibt ein **OracleDataReader** für den REF CURSOR.  
  
 Wenn Ihre **OracleCommand** mehrere REF CURSORS zurückgibt fügen Sie mehrere Ausgabeparameter hinzu. Sie können die verschiedenen REF CURSORs zugreifen, durch den Aufruf der **OracleCommand.ExecuteReader** Methode. Der Aufruf von **"ExecuteReader"** gibt ein **OracleDataReader** auf den ersten REF CURSOR verweist. Rufen Sie anschließend die **OracleDataReader.NextResult** Methode, um die nachfolgenden REF CURSORs zugreifen. Obwohl die Parameter in Ihre **OracleCommand.Parameters** Auflistung Übereinstimmung den REF CURSOR-Ausgabeparameter anhand des Namens, der **OracleDataReader** greift auf sie in der Reihenfolge an, dass sie die hinzugefügtwurden **Parameter** Auflistung.  
  
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
  
 Der folgende Code erstellt ein **OracleCommand** , aus dem vorherigen Oracle-Paket die REF CURSORs zurückgibt, durch das Hinzufügen von zwei Parametern vom Typ **OracleType.Cursor** auf die **Parameter** Auflistung.  
  
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
  
 Der folgende Code gibt die Ergebnisse des vorherigen Befehls mit der **lesen** und **NextResult** Methoden der **OracleDataReader**. Die REF CURSOR-Parameter werden der Reihe nach zurückgegeben.  
  
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
>  Vermeiden einer **OverflowException**, es wird empfohlen, dass Sie auch jede Konvertierung von Oracle-Typ NUMBER in einen gültigen .NET Framework-Typ vor dem Speichern des Werts in behandeln eine **DataRow**. Sie können die **FillError** Ereignis, um zu bestimmen, ob ein **OverflowException** aufgetreten. Weitere Informationen zu den **FillError** Ereignis finden Sie unter [Behandeln von DataAdapter-Ereignissen](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
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
 [Arbeiten mit "DataReaders"](https://msdn.microsoft.com/library/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [DataAdapters und DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Abrufen von Datenbankschemainformationen](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
