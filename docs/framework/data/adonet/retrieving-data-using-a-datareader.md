---
title: Abrufen von Daten mit "DataReader"
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 8063f239123ec1a2f2650adf9d76f7ceaaa50673
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61664258"
---
# <a name="retrieve-data-using-a-datareader"></a>Abrufen von Daten, die mit "DataReader"
Zum Abrufen von Daten mithilfe einer **DataReader**, erstellen Sie eine Instanz von der **Befehl** Objekt aus, und erstellen Sie eine **DataReader** durch Aufrufen von **Command.ExecuteReader**  um Zeilen aus einer Datenquelle abzurufen. Die **DataReader** enthält einen nicht gepufferten Datenstream, mit der prozeduralen Logik, die Ergebnisse aus einer Datenquelle effizient sequenziell zu verarbeiten zu können. Die **DataReader** ist eine gute Wahl, wenn Sie große Mengen von Daten abgerufen werden, da die Daten nicht im Arbeitsspeicher zwischengespeichert werden.

Das folgende Beispiel veranschaulicht die Verwendung einer **DataReader**, wobei `reader` stellt ein gültiger DataReader-Ziel und `command` ein gültiges Command-Objekt darstellt.  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

Verwenden der **DataReader.Read** Methode, um eine Zeile aus die Ergebnisse der Abfrage abzurufen. Sie können jede Spalte der zurückgegebenen Zeile zugreifen, indem Sie übergeben den Namen oder die Ordnungszahl der Spalte, die die **DataReader**. Allerdings für eine optimale Leistung die **DataReader** enthält eine Reihe von Methoden, die Sie auf Spaltenwerte in deren systemeigenen Datentypen zugreifen können (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**und so weiter). Eine Liste der typisierten Zugriffsmethoden für anbieterspezifische **"DataReaders"**, finden Sie unter <xref:System.Data.OleDb.OleDbDataReader> und <xref:System.Data.SqlClient.SqlDataReader>. Verwenden die typisierten Accessormethoden bereit, wenn Sie wissen, dass die zugrunde liegenden Daten verringert Typ die Typumwandlung erforderlich, wenn der Wert der Spalte abrufen.  
  
 Das folgende Beispiel durchläuft einen **DataReader** -Objekt und zwei Spalten aus jeder Zeile zurückgegeben.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a>Schließen des "DataReader"  
 Rufen Sie immer die **schließen** Methode, wenn Sie aufgehört haben die **DataReader** Objekt.  
  
 Wenn Ihre **Befehl** enthält die Ausgabe Parameter oder Rückgabewerte, sind diese Werte nicht verfügbar, bis die **DataReader** geschlossen wird.  
  
 Während einer **DataReader** geöffnet ist, die **Verbindung** wird ausschließlich von diesem **DataReader**. Sie können nicht ausgeführt werden Befehle für die **Verbindung**, einschließlich der Erstellung eines weiteren **DataReader**, bis die ursprüngliche **DataReader** geschlossen wird.  
  
> [!NOTE]
>  Rufen Sie nicht **schließen** oder **Dispose** auf eine **Verbindung**, **DataReader**, oder andere verwaltete Objekte in der **abschließen**  Methode der Klasse. Geben Sie in einer Finalize-Methode nur nicht verwaltete Ressourcen frei, die der Klasse direkt gehören. Wenn Ihre Klasse keine nicht verwalteten Ressourcen besitzt, ist nicht enthalten. ein **Finalize** Methode in der Klassendefinition. Weitere Informationen finden Sie unter [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>Abrufen von mehreren Resultsets legt fest, die mit "NextResult"  
 Wenn die **DataReader** mehrere Resultsets Aufruf gibt die **NextResult** Methode zum iterieren durch das Ergebnis wird sequenziell. Im folgenden Beispiel werden die Ergebnisse von zwei SELECT-Anweisungen mit der <xref:System.Data.SqlClient.SqlDataReader>-Methode von <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> verarbeitet.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>Abrufen von Schemainformationen vom DataReader  
 Während einer **DataReader** ist geöffnet ist, können die Schemainformationen über das aktuelle Resultset mit Abrufen der **GetSchemaTable** Methode. **GetSchemaTable** gibt eine <xref:System.Data.DataTable> -Objekt mit den Zeilen und Spalten, die die Schemainformationen für das aktuelle Resultset enthalten. Die **DataTable** enthält eine Zeile für jede Spalte des Resultsets. Jede Spalte der Schematabelle ordnet eine Eigenschaft, die Spalten, die Zeilen des Resultsets festgelegt, wobei die **ColumnName** ist der Name der Eigenschaft und der Wert der Spalte den Wert der Eigenschaft. Im folgende Beispiel schreibt die Schemainformationen für **DataReader**.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>Arbeiten mit OLE DB-Kapitel  
 Hierarchische Rowsets oder Kapitel (OLE DB-Typ **DBTYPE_HCHAPTER**, ADO-Typ **AdChapter**), können abgerufen werden, mithilfe der <xref:System.Data.OleDb.OleDbDataReader>. Wenn eine Abfrage, die einem Kapitel zurückgegeben wird, als eine **DataReader**, das Kapitel als Spalte in diesem zurückgegeben wird **DataReader** und als verfügbar gemacht wird eine **DataReader** Objekt.  
  
 ADO.NET **DataSet** kann auch verwendet werden, um hierarchische Rowsets mit über-und untergeordnete Beziehungen zwischen Tabellen darstellen. Weitere Informationen finden Sie unter [DataSets, DataTables und DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a>Zurückgeben von Ergebnissen mit Oracle-REF CURSORs  
 Der .NET Framework-Datenanbieter für Oracle unterstützt die Verwendung von Oracle-REF CURSORs zur Rückgabe eines Abfrageergebnisses. Ein Oracle-REF CURSOR wird als <xref:System.Data.OracleClient.OracleDataReader> zurückgegeben.  
  
 Können Sie Abrufen einer <xref:System.Data.OracleClient.OracleDataReader> Objekt, eine Oracle-REF CURSOR darstellt, mit, der <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> Methode. Sie können auch angeben einer <xref:System.Data.OracleClient.OracleCommand> , die eine oder mehrere Oracle-REF CURSORs als zurückgibt der **SelectCommand** für eine <xref:System.Data.OracleClient.OracleDataAdapter> verwendet, um eine <xref:System.Data.DataSet>.  
  
 Erstellen Sie aus einer Oracle-Datenquelle zurückgegebenen REF CURSOR für den Zugriff auf eine <xref:System.Data.OracleClient.OracleCommand> für die Abfrage und fügen Sie einen Output-Parameter, die den REF CURSOR verweist die <xref:System.Data.OracleClient.OracleCommand.Parameters> Auflistung von Ihrer <xref:System.Data.OracleClient.OracleCommand>. Der Name des Parameters muss mit dem Namen des REF CURSOR-Parameters in der Abfrage übereinstimmen. Legen Sie den Typ des Parameters, der <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>. Die <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> Methode Ihrer <xref:System.Data.OracleClient.OracleCommand> gibt ein <xref:System.Data.OracleClient.OracleDataReader> für den REF CURSOR.  
  
 Wenn Ihre <xref:System.Data.OracleClient.OracleCommand> mehrere REF CURSORS zurückgibt fügen Sie mehrere Ausgabeparameter hinzu. Sie können die verschiedenen REF CURSORs zugreifen, durch den Aufruf der <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> Methode. Der Aufruf von <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> gibt ein <xref:System.Data.OracleClient.OracleDataReader> auf den ersten REF CURSOR verweist. Rufen Sie anschließend die <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> Methode, um die nachfolgenden REF CURSORs zugreifen. Obwohl die Parameter in Ihre <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> Auflistung Übereinstimmung den REF CURSOR-Ausgabeparameter anhand des Namens, der <xref:System.Data.OracleClient.OracleDataReader> greift auf sie in der Reihenfolge, in dem sie hinzugefügt wurden, die <xref:System.Data.OracleClient.OracleCommand.Parameters> Auflistung.  
  
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
  
 Der folgende Code erstellt ein <xref:System.Data.OracleClient.OracleCommand> , aus dem vorherigen Oracle-Paket die REF CURSORs zurückgibt, durch das Hinzufügen von zwei Parametern vom Typ <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> auf die <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> Auflistung.  
  
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
  
 Der folgende Code gibt die Ergebnisse des vorherigen Befehls mit der <xref:System.Data.OracleClient.OracleDataReader.Read> und <xref:System.Data.OracleClient.OracleDataReader.NextResult> Methoden der <xref:System.Data.OracleClient.OracleDataReader>. Die REF CURSOR-Parameter werden der Reihe nach zurückgegeben.  
  
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
  
 Im folgenden Beispiel wird den vorherigen Befehl zum Auffüllen einer <xref:System.Data.DataSet> mit den Ergebnissen des Oracle-Pakets.  
  
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
>  Vermeiden einer **OverflowException**, es wird empfohlen, dass Sie auch jede Konvertierung von Oracle-Typ NUMBER in einen gültigen .NET Framework-Typ vor dem Speichern des Werts in behandeln eine <xref:System.Data.DataRow>. Sie können die <xref:System.Data.Common.DataAdapter.FillError> Ereignis, um zu bestimmen, ob ein **OverflowException** aufgetreten. Weitere Informationen zu den <xref:System.Data.Common.DataAdapter.FillError> Ereignis finden Sie unter [Behandeln von DataAdapter-Ereignissen](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
## <a name="see-also"></a>Siehe auch

- [DataAdapters und DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [Abrufen von Datenbankschemainformationen](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
