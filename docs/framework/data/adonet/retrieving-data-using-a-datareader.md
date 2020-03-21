---
title: Abrufen von Daten mit "DataReader"
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 88cd85ce343aaab08b944f81c9659918014da0a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149023"
---
# <a name="retrieve-data-using-a-datareader"></a>Abrufen von Daten mithilfe eines DataReaders
Um Daten mit einem **DataReader**abzurufen, erstellen Sie eine Instanz des Command-Objekts, und erstellen Sie dann einen **DataReader,** indem Sie **Command.ExecuteReader** aufrufen, um Zeilen aus einer Datenquelle abzurufen. **Command** Der **DataReader** stellt einen ungepufferten Datenstrom bereit, mit dem die Prozedurlogik Ergebnisse aus einer Datenquelle sequenziell effizient verarbeiten kann. Der **DataReader** ist eine gute Wahl, wenn Sie große Datenmengen abrufen, da die Daten nicht im Arbeitsspeicher zwischengespeichert werden.

Das folgende Beispiel veranschaulicht die Verwendung `reader` eines **DataReader** `command` , wobei ein gültiger DataReader und ein gültiges Command-Objekt darstellt.  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

Verwenden Sie die **DataReader.Read-Methode,** um eine Zeile aus den Abfrageergebnissen abzufragen. Sie können auf jede Spalte der zurückgegebenen Zeile zugreifen, indem Sie den Namen oder die Ordinalnummer der Spalte an den **DataReader**übergeben. Für eine optimale Leistung bietet **dataReader** jedoch eine Reihe von Methoden, mit denen Sie auf Spaltenwerte in ihren systemeigenen Datentypen zugreifen können (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**usw.). Eine Liste der typisierten Accessormethoden für datenanbieterspezifische <xref:System.Data.OleDb.OleDbDataReader> <xref:System.Data.SqlClient.SqlDataReader> **DataReader**finden Sie unter und . Wenn Sie die typisierten Accessormethoden verwenden, wenn Sie wissen, dass der zugrunde liegende Datentyp den Beim Abrufen des Spaltenwerts erforderlichen Typkonvertierungstyps verwendet.  
  
 Im folgenden Beispiel wird ein **DataReader-Objekt** durchlaufen und zwei Spalten aus jeder Zeile zurückgegeben.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a>Schließen des "DataReader"  
 Rufen Sie immer die **Close-Methode** auf, wenn Sie die Verwendung des **DataReader-Objekts** abgeschlossen haben.  
  
 Wenn Ihr **Befehl** Ausgabeparameter oder Rückgabewerte enthält, sind diese Werte erst verfügbar, wenn der **DataReader** geschlossen wird.  
  
 Während ein **DataReader** geöffnet ist, wird die **Verbindung** ausschließlich von **diesem DataReader**verwendet. Sie können keine Befehle für die **Verbindung**ausführen, einschließlich des Erstellens eines anderen **DataReader**, bis der ursprüngliche **DataReader** geschlossen ist.  
  
> [!NOTE]
> Rufen Sie **Close** oder **Dispose** nicht für eine **Verbindung**, einen **DataReader**oder ein anderes verwaltetes Objekt in der **Finalize-Methode** Ihrer Klasse auf. Geben Sie in einer Finalize-Methode nur nicht verwaltete Ressourcen frei, die der Klasse direkt gehören. Wenn Ihre Klasse keine nicht verwalteten Ressourcen besitzt, schließen Sie keine **Finalize-Methode** in ihre Klassendefinition ein. Weitere Informationen finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>Abrufen mehrerer Resultsets mit NextResult  
 Wenn der **DataReader** mehrere Resultsets zurückgibt, rufen Sie die **NextResult-Methode** auf, um die Resultsets sequenziell zu durchlaufen. Im folgenden Beispiel werden die Ergebnisse von zwei SELECT-Anweisungen mit der <xref:System.Data.SqlClient.SqlDataReader>-Methode von <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> verarbeitet.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>Abrufen von Schemainformationen aus dem DataReader  
 Während ein **DataReader** geöffnet ist, können Sie mithilfe der **GetSchemaTable-Methode** Schemainformationen über das aktuelle Resultset abrufen. **GetSchemaTable** gibt <xref:System.Data.DataTable> ein Objekt zurück, das mit Zeilen und Spalten gefüllt ist, die die Schemainformationen für das aktuelle Resultset enthalten. Die **DataTable** enthält eine Zeile für jede Spalte des Resultsets. Jede Spalte der Schematabelle wird einer Eigenschaft der Spalten zugeordnet, die in den Zeilen des Resultsets zurückgegeben werden, wobei der **ColumnName** der Name der Eigenschaft und der Wert der Spalte der Wert der Eigenschaft ist. Im folgenden Beispiel werden die Schemainformationen für **DataReader**ausgeschreiben.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>Arbeiten mit OLE DB-Kapiteln  
 Hierarchische Rowsets oder Kapitel (OLE DB Typ **DBTYPE_HCHAPTER**, ADO-Typ <xref:System.Data.OleDb.OleDbDataReader> **adChapter**) können mit dem abgerufen werden. Wenn eine Abfrage, die ein Kapitel enthält, als **DataReader**zurückgegeben wird, wird das Kapitel als Spalte in **diesem DataReader** zurückgegeben und als **DataReader-Objekt** verfügbar gemacht.  
  
 Das ADO.NET **DataSet** kann auch verwendet werden, um hierarchische Rowsets darzustellen, indem Parent-Child-Beziehungen zwischen Tabellen verwendet werden. Weitere Informationen finden Sie unter [DataSets, DataTables und DataViews](./dataset-datatable-dataview/index.md).  
  
 Im folgenden Codebeispiel wird mit dem MSDataShape-Anbieter eine Kapitelspalte mit Bestellungen für jeden Kunden in einer Kundenliste generiert.  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" &
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind")

    Using custCMD As OleDbCommand = New OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " &
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " &
        "RELATE CustomerID TO CustomerID)", connection)

        connection.Open()

        Using custReader As OleDbDataReader = custCMD.ExecuteReader()

            Do While custReader.Read()
                Console.WriteLine("Orders for " & custReader.GetString(1))
                ' custReader.GetString(1) = CompanyName  

                Using orderReader As OleDbDataReader = custReader.GetValue(2)
                    ' custReader.GetValue(2) = Orders chapter as DataReader  

                    Do While orderReader.Read()
                        Console.WriteLine(vbTab & orderReader.GetInt32(1))
                        ' orderReader.GetInt32(1) = OrderID  
                    Loop
                    orderReader.Close()
                End Using
            Loop
            ' Make sure to always close readers and connections.  
            custReader.Close()
        End Using
    End Using
End Using
```  
  
```csharp  
using (OleDbConnection connection = new OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" +
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind"))
{
    using (OleDbCommand custCMD = new OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " +
        "RELATE CustomerID TO CustomerID)", connection))
    {
        connection.Open();

        using (OleDbDataReader custReader = custCMD.ExecuteReader())
        {

            while (custReader.Read())
            {
                Console.WriteLine("Orders for " + custReader.GetString(1));
                // custReader.GetString(1) = CompanyName  

                using (OleDbDataReader orderReader = (OleDbDataReader)custReader.GetValue(2))
                {
                    // custReader.GetValue(2) = Orders chapter as DataReader  

                    while (orderReader.Read())
                        Console.WriteLine("\t" + orderReader.GetInt32(1));
                    // orderReader.GetInt32(1) = OrderID  
                    orderReader.Close();
                }
            }
            // Make sure to always close readers and connections.  
            custReader.Close();
        }
    }
}
```  
  
## <a name="returning-results-with-oracle-ref-cursors"></a>Ergebnisse mit Oracle REF CURSORs zurücksenden  
 Der .NET Framework-Datenanbieter für Oracle unterstützt die Verwendung von Oracle-REF CURSORs zur Rückgabe eines Abfrageergebnisses. Ein Oracle-REF CURSOR wird als <xref:System.Data.OracleClient.OracleDataReader> zurückgegeben.  
  
 Sie können <xref:System.Data.OracleClient.OracleDataReader> ein Objekt abrufen, das einen <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> Oracle REF CURSOR darstellt, indem Sie die Methode verwenden. Sie können auch <xref:System.Data.OracleClient.OracleCommand> eine angeben, die einen oder mehrere Oracle <xref:System.Data.OracleClient.OracleDataAdapter> REF CURSORs als **SelectCommand** für eine zum Ausfüllen einer <xref:System.Data.DataSet>verwendet wird.  
  
 Um auf einen REF CURSOR zuzugreifen, der <xref:System.Data.OracleClient.OracleCommand> von einer Oracle-Datenquelle zurückgegeben wird, erstellen <xref:System.Data.OracleClient.OracleCommand.Parameters> Sie <xref:System.Data.OracleClient.OracleCommand>eine für Ihre Abfrage, und fügen Sie einen Ausgabeparameter hinzu, der auf den REF CURSOR zur Auflistung Ihrer verweist. Der Name des Parameters muss mit dem Namen des REF CURSOR-Parameters in der Abfrage übereinstimmen. Legen Sie den Typ <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>des Parameters auf . Die <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> Methode <xref:System.Data.OracleClient.OracleCommand> von <xref:System.Data.OracleClient.OracleDataReader> Ihnen gibt eine für den REF CURSOR zurück.  
  
 Wenn <xref:System.Data.OracleClient.OracleCommand> Sie mehrere REF CURSORS zurückgibt, fügen Sie mehrere Ausgabeparameter hinzu. Sie können auf die verschiedenen REF <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> CURSORs zugreifen, indem Sie die Methode aufrufen. Der Aufruf, <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> <xref:System.Data.OracleClient.OracleDataReader> einen Verweis auf den ersten REF CURSOR zurückzurufen. Sie können dann <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> die Methode aufrufen, um auf nachfolgende REF CURSORs zuzugreifen. Obwohl die Parameter <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> in Ihrer Auflistung mit den <xref:System.Data.OracleClient.OracleDataReader> REF CURSOR-Ausgabeparametern übereinstimmen, greift <xref:System.Data.OracleClient.OracleCommand.Parameters> der Zugriff auf sie in der Reihenfolge zu, in der sie der Auflistung hinzugefügt wurden.  
  
 	Betrachten Sie z. B. das folgende Oracle-Paket und den Paketkörper.  
  
```sql
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
  
 Der folgende Code <xref:System.Data.OracleClient.OracleCommand> erstellt eine, die die REF CURSORs aus <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> dem <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> vorherigen Oracle-Paket zurückgibt, indem der Auflistung zwei Parameter vom Typ hinzugefügt werden.  
  
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
  
 Der folgende Code gibt die Ergebnisse <xref:System.Data.OracleClient.OracleDataReader.Read> des <xref:System.Data.OracleClient.OracleDataReader.NextResult> vorherigen <xref:System.Data.OracleClient.OracleDataReader>Befehls mithilfe der und-Methoden der zurück. Die REF CURSOR-Parameter werden der Reihe nach zurückgegeben.  
  
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
  
 Im folgenden Beispiel wird der vorherige <xref:System.Data.DataSet> Befehl verwendet, um eine mit den Ergebnissen des Oracle-Pakets aufzufüllen.  
  
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

> [!NOTE]
> Um eine **OverflowException**zu vermeiden, wird empfohlen, dass Sie auch jede Konvertierung vom Oracle NUMBER-Typ in einen gültigen .NET Framework-Typ behandeln, bevor Sie den Wert in einer <xref:System.Data.DataRow>speichern. Sie können <xref:System.Data.Common.DataAdapter.FillError> das Ereignis verwenden, um zu bestimmen, ob eine **OverflowException** aufgetreten ist. Weitere Informationen zum <xref:System.Data.Common.DataAdapter.FillError> Ereignis finden Sie [unter Behandeln von DataAdapter-Ereignissen](handling-dataadapter-events.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [DataAdapters und DataReaders](dataadapters-and-datareaders.md)
- [Befehle und Parameter](commands-and-parameters.md)
- [Abrufen von Datenbankschemainformationen](retrieving-database-schema-information.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
