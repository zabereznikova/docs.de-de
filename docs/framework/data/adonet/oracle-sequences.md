---
title: Oracle-Sequenzen
ms.date: 03/30/2017
ms.assetid: 27cd371d-8252-414d-b5b2-5d31fa44b585
ms.openlocfilehash: d6e6bb51b8bd317c7161500b89993be689659fad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149413"
---
# <a name="oracle-sequences"></a>Oracle-Sequenzen
Der .NET Framework-Datenanbieter für Oracle bietet Unterstützung für das Abrufen der vom Server generierten Oracle-Sequenz-Schlüsselwerte, nachdem mit <xref:System.Data.OracleClient.OracleDataAdapter> Einfügevorgänge ausgeführt wurden.  
  
 SQL Server und Oracle unterstützen die Erstellung von Spalten, die automatisch inkrementiert und für Primärschlüssel verwendet werden. Diese Werte werden vom Server generiert, wenn einer Tabelle Zeilen hinzugefügt werden. In SQL Server legen Sie die Identität einer Spalte fest, in Oracle erstellen Sie eine Sequenz. Zwischen den AutoIncrement-Spalten in SQL Server und den Sequenzen in Oracle besteht der folgende Unterschied:  
  
- In SQL Server markieren Sie eine Spalte als &lt;legacyBold&gt;AutoIncrement&lt;/legacyBold&gt;-Spalte, woraufhin SQL Server automatisch neue Werte für die Spalte generiert, sobald eine neue Zeile eingefügt wird.  
  
- In Oracle erstellen Sie eine Sequenz, um neue Werte für eine Spalte in Ihrer Tabelle zu generieren, wobei es aber keine direkte Verknüpfung zwischen der Sequenz und der Tabelle bzw. Spalte gibt. Eine Oracle-Sequenz ist ein Objekt wie eine Tabelle oder eine gespeicherte Prozedur.  
  
 Wenn Sie in einer Oracle-Datenbank eine Sequenz erstellen, können Sie deren Erstwert und den Inkrementwert definieren. Sie können die Sequenz auch nach neuen Werten abfragen, bevor Sie neue Zeilen senden. Das bedeutet, Ihr Code kann die Schlüsselwerte für neue Zeilen erkennen, bevor Sie sie in die Datenbank einfügen.  
  
 Weitere Informationen zum Erstellen von Spalten mit automatischer Inkrementierung mithilfe von SQL Server und ADO.NET finden Sie unter [Abrufen von Identitäts- oder Autonummernwerten](retrieving-identity-or-autonumber-values.md) und [Erstellen von AutoInkrementspalten](./dataset-datatable-dataview/creating-autoincrement-columns.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden C#-Beispiel wird gezeigt, wie Sie neue Sequenzwerte aus einer Oracle-Datenbank abrufen können. Im Beispiel wird auf die Sequenz in der INSERT INTO-Abfrage verwiesen, mit der die neuen Zeilen eingefügt werden. Daraufhin wird der Sequenzwert zurückgegeben, der mit der in Oracle10g eingeführten RETURNING-Klausel generiert wird. Das Beispiel fügt einer <xref:System.Data.DataTable> eine Reihe anstehender neuer Zeilen hinzu. Dabei kommt die ADO.NET-&lt;legacyBold&gt;AutoIncrement&lt;/legacyBold&gt;-Funktionalität zum Einsatz, mit der "Platzhalter"-Primärschlüsselwerte generiert werden. Beachten Sie, dass der von ADO.NET generierte Inkrementwert für die neue Zeile lediglich ein "Platzhalter" ist. Die Datenbank generiert u. U. andere Werte als ADO.NET.  
  
 Bevor die anstehenden Einfügungen an die Datenbank gesendet werden, zeigt das Beispiel den Inhalt der Zeilen an. Der Code erstellt dann ein neues <xref:System.Data.OracleClient.OracleDataAdapter>-Objekt und richtet dessen Eigenschaften <xref:System.Data.OracleClient.OracleDataAdapter.InsertCommand%2A> und <xref:System.Data.OracleClient.OracleDataAdapter.UpdateBatchSize%2A> ein. Im Beispiel wird auch die Logik angegeben, mit der die vom Server generierten Werte unter Verwendung von Ausgabeparametern zurückgegeben werden. Anschließend wird das Update ausgeführt, indem die anstehenden Zeilen gesendet werden, und es wird der Inhalt der <xref:System.Data.DataTable> angezeigt.  
  
```csharp  
public void OracleSequence(String connectionString)  
{  
   String insertString =
      "INSERT INTO SequenceTest_Table (ID, OtherColumn)" +  
      "VALUES (SequenceTest_Sequence.NEXTVAL, :OtherColumn)" +  
      "RETURNING ID INTO :ID";  
  
   using (OracleConnection conn = new OracleConnection(connectionString))  
   {  
      //Open a connection.  
      conn.Open();  
      OracleCommand cmd = conn.CreateCommand();  
  
      // Prepare the database.  
      cmd.CommandText = "DROP SEQUENCE SequenceTest_Sequence";  
      try { cmd.ExecuteNonQuery(); } catch { }  
  
      cmd.CommandText = "DROP TABLE SequenceTest_Table";  
      try { cmd.ExecuteNonQuery(); } catch { }  
  
      cmd.CommandText = "CREATE TABLE SequenceTest_Table " +  
                     "(ID int PRIMARY KEY, OtherColumn varchar(255))";  
      cmd.ExecuteNonQuery();  
  
      cmd.CommandText = "CREATE SEQUENCE SequenceTest_Sequence " +  
                        "START WITH 100 INCREMENT BY 5";  
      cmd.ExecuteNonQuery();  
  
      DataTable testTable = new DataTable();  
      DataColumn column = testTable.Columns.Add("ID", typeof(int));  
      column.AutoIncrement = true;  
      column.AutoIncrementSeed = -1;  
      column.AutoIncrementStep = -1;  
      testTable.PrimaryKey = new DataColumn[] { column };  
      testTable.Columns.Add("OtherColumn", typeof(string));  
      for (int rowCounter = 1; rowCounter <= 15; rowCounter++)  
      {  
         testTable.Rows.Add(null, "Row #" + rowCounter.ToString());  
      }  
  
      Console.WriteLine("Before Update => ");  
      foreach (DataRow row in testTable.Rows)  
      {  
         Console.WriteLine("   {0} - {1}", row["ID"], row["OtherColumn"]);  
      }  
      Console.WriteLine();  
  
      cmd.CommandText =
        "SELECT ID, OtherColumn FROM SequenceTest_Table";  
      OracleDataAdapter da = new OracleDataAdapter(cmd);  
      da.InsertCommand = new OracleCommand(insertString, conn);  
      da.InsertCommand.Parameters.Add(":ID", OracleType.Int32, 0, "ID");  
      da.InsertCommand.Parameters[0].Direction = ParameterDirection.Output;  
      da.InsertCommand.Parameters.Add(":OtherColumn", OracleType.VarChar, 255, "OtherColumn");  
      da.InsertCommand.UpdatedRowSource = UpdateRowSource.OutputParameters;  
      da.UpdateBatchSize = 10;  
  
      da.Update(testTable);  
  
      Console.WriteLine("After Update => ");  
      foreach (DataRow row in testTable.Rows)  
      {  
         Console.WriteLine("   {0} - {1}", row["ID"], row["OtherColumn"]);  
      }  
      // Close the connection.  
      conn.Close();  
   }  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Oracle und ADO.NET](oracle-and-adonet.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
