---
title: Anbieterstatistiken für SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 429c9d09-92ac-46ec-829a-fbff0a9575a2
ms.openlocfilehash: d52c6bfdadf0a53ac4c5f62c37f1056c6702a82c
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48842709"
---
# <a name="provider-statistics-for-sql-server"></a>Anbieterstatistiken für SQL Server
Ab .NET Framework Version 2.0 unterstützt der .NET Framework-Datenanbieter für SQL Server Laufzeitstatistiken. Sie müssen die Statistik aktivieren, indem Sie nach dem Erstellen eines gültigen Verbindungsobjekts die <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A>-Eigenschaft des <xref:System.Data.SqlClient.SqlConnection>-Objekts auf `True` festlegen. Nach dem Aktivieren der Statistik können Sie sie als "Momentaufnahme" betrachten, indem Sie einen <xref:System.Collections.IDictionary>-Verweis über die <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A>-Methode des <xref:System.Data.SqlClient.SqlConnection>-Objekts abrufen. Blättern Sie durch die Liste wie durch Wörterbucheinträge mit Name-Wert-Paaren. Diese Name-Wert-Paare sind nicht sortiert. Sie können jederzeit die <xref:System.Data.SqlClient.SqlConnection.ResetStatistics%2A>-Methode des <xref:System.Data.SqlClient.SqlConnection>-Objekts aufrufen, um die Zähler zurückzusetzen. Wenn das Erfassen der Statistik nicht aktiviert wurde, wird keine Ausnahme ausgelöst. Wenn <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> aufgerufen wird, ohne vorher <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> aufzurufen, stellen die abgerufenen Werte die Anfangswerte für die einzelnen Einträge dar. Wenn Sie die Statistik aktivieren, die Anwendung für eine gewisse Zeit ausführen und dann die Statistik wieder deaktivieren, entsprechen die abgerufenen Werte den Werten, die bis zu dem Zeitpunkt erfasst wurden, an dem die Statistik deaktiviert wurde. Alle statistischen Werte werden auf der Basis einzelner Verbindungen erfasst.  
  
## <a name="statistical-values-available"></a>Verfügbare statistische Werte  
 Gegenwärtig sind vom Anbieter Microsoft SQL Server 18 verschiedene Elemente verfügbar. Die Anzahl der verfügbaren Elemente zugegriffen werden kann, über die **Anzahl** Eigenschaft der <xref:System.Collections.IDictionary> Schnittstellenreferenz zurückgegebenes <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A>. Alle Zähler für Anbieterstatistiken verwenden die common Language Runtime <xref:System.Int64> Typ (**lange** in c# und Visual Basic), d.h. 64 Bits breit. Der maximale Wert, der die **int64** -Datentyp, gemäß der **int64. MaxValue** Feld, ((2^63)-1)). Wenn die Werte für die Zähler diesen Maximalwert erreichen, können sie nicht mehr als korrekt bezeichnet werden. Dies bedeutet, dass **int64. MaxValue**-1((2^63)-2) ist tatsächlich der größte gültige Wert für alle Statistiken.  
  
> [!NOTE]
>  Für die zurückgegebene Anbieterstatistik wird ein Wörterbuch verwendet, da sich die Anzahl, die Namen und die Reihenfolge der zurückgegebenen Statistiken zukünftig ändern können. Anwendungen sollten sich nicht darauf verlassen, dass ein bestimmter Wert in einem Wörterbuch gefunden wird, sondern stattdessen überprüfen, ob der Wert vorhanden ist, und entsprechend verzweigen.  
  
 In der folgenden Tabelle werden die aktuell verfügbaren statistischen Werte beschrieben. Beachten Sie, dass die Schlüsselnamen für die einzelnen Werte für regionale Versionen von Microsoft .NET Framework nicht lokalisiert werden.  
  
|Schlüsselname|Beschreibung|  
|--------------|-----------------|  
|`BuffersReceived`|Gibt die Anzahl der TDS-Pakete (Tabular Data Stream) zurück, die vom Anbieter von SQL Server empfangen wurden, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.|  
|`BuffersSent`|Gibt die Anzahl der TDS-Pakete zurück, die vom Anbieter an SQL Server gesendet wurden, seit die Statistik aktiviert wurde. Für umfangreiche Befehle sind möglicherweise mehrere Puffer erforderlich. Wenn z. B. ein großer Befehl an der Server gesendet wurde und 6 Pakete erfordert, wird `ServerRoundtrips` um 1 vergrößert und `BuffersSent` um 6 vergrößert.|  
|`BytesReceived`|Gibt die Anzahl der Bytes der Daten in TDS-Paketen zurück, die vom Anbieter von SQL Server empfangen wurden, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.|  
|`BytesSent`|Gibt die Anzahl der Bytes der Daten zurück, die in TDS-Paketen an SQL Server gesendet wurden, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.|  
|`ConnectionTime`|Die Zeitspanne (in Millisekunden), die die Verbindung nach dem Aktivieren der Statistik geöffnet war (die Gesamtverbindungszeit, wenn die Statistik vor dem Öffnen der Verbindung aktiviert wurde).|  
|`CursorOpens`|Gibt zurück, wie oft während der Verbindung ein Cursor geöffnet war, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.<br /><br /> Beachten Sie, dass schreibgeschützte Vorwärtsergebnisse, die von SELECT-Anweisungen zurückgegeben wurden, nicht als Cursor betrachtet werden und deshalb diesen Zähler nicht beeinflussen.|  
|`ExecutionTime`|Gibt die Gesamtzeitspanne (in Millisekunden) zurück, die der Anbieter seit dem Aktivieren der Statistik mit der Verarbeitung verbracht hat, einschließlich der Zeit zum Warten auf Antworten vom Server und zum Ausführen von Code im Anbieter selbst.<br /><br /> Folgende Klassen enthalten Zeiterfassungscode:<br /><br /> SqlConnection<br /><br /> SqlCommand<br /><br /> SqlDataReader<br /><br /> SqlDataAdapter<br /><br /> SqlTransaction<br /><br /> SqlCommandBuilder<br /><br /> Um leistungswichtige Member so klein wie möglich zu halten, erfolgt für die folgenden Member keine Zeiterfassung:<br /><br /> SqlDataReader<br /><br /> this[]-Operator (alle Überladungen)<br /><br /> GetBoolean<br /><br /> GetChar<br /><br /> GetDateTime<br /><br /> GetDecimal<br /><br /> GetDouble<br /><br /> GetFloat<br /><br /> GetGuid<br /><br /> GetInt16<br /><br /> GetInt32<br /><br /> GetInt64<br /><br /> GetName<br /><br /> GetOrdinal<br /><br /> GetSqlBinary<br /><br /> GetSqlBoolean <br /><br /> GetSqlByte <br /><br /> GetSqlDateTime <br /><br /> GetSqlDecimal <br /><br /> GetSqlDouble <br /><br /> GetSqlGuid <br /><br /> GetSqlInt16 <br /><br /> GetSqlInt32 <br /><br /> GetSqlInt64 <br /><br /> GetSqlMoney <br /><br /> GetSqlSingle <br /><br /> GetSqlString <br /><br /> GetString<br /><br /> IsDBNull|  
|`IduCount`|Gibt die gesamte Anzahl der über die Verbindung ausgeführten INSERT-, DELETE- und UPDATE-Anweisungen zurück, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.|  
|`IduRows`|Gibt die gesamte Anzahl der Zeilen zurück, die von über die Verbindung ausgeführten INSERT-, DELETE- und UPDATE-Anweisungen beeinflusst wurden, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.|  
|`NetworkServerTime`|Gibt die Gesamtzeitspanne (in Millisekunden) zurück, die der Anbieter zum Warten auf Antworten vom Server aufgewendet hat, seit die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.|  
|`PreparedExecs`|Gibt die Anzahl vorbereiteter Befehle zurück, die über die Verbindung ausgeführt wurden, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.|  
|`Prepares`|Gibt die Anzahl der über die Verbindung vorbereiteten Anweisungen zurück, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.|  
|`SelectCount`|Gibt die Anzahl von SELECT-Anweisungen zurück, die über die Verbindung ausgeführt wurden, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat. Darin sind FETCH-Anweisungen zum Abrufen von Zeilen von Cursors enthalten, und die Anzahl von SELECT-Anweisungen wird aktualisiert, wenn das Ende eines <xref:System.Data.SqlClient.SqlDataReader> erreicht wird.|  
|`SelectRows`|Gibt die Anzahl der Zeilen zurück, die ausgewählt wurden, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat. Dieser Zähler gibt alle Zeilen wieder, die durch SQL-Anweisungen erstellt wurden, darunter auch die, die vom Aufrufer nicht verarbeitet wurden. Das Schließen eines Datenreaders vor dem vollständigen Lesen des Ergebnisses beeinflusst z. B. die Zählung nicht. Dies gilt auch für Zeilen, die über FETCH-Anwendungen von Cursors abgerufen wurden.|  
|`ServerRoundtrips`|Gibt an, wie oft die Verbindung Befehle zum Server gesendet und eine Antwort erhalten hat, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.|  
|`SumResultSets`|Gibt die Anzahl der verwendeten Resultsets zurück, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat. Dies umfasst z. B. Resultsets, die zum Client zurückgegeben wurden. Für Cursors wird jede "fetch"- oder "block-fetch"-Operation als unabhängiges Resultset behandelt.|  
|`Transactions`|Gibt die Anzahl der gestarteten Benutzertransaktionen (einschließlich Rollbacks) zurück, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat. Wenn eine Verbindung mit aktiviertem Autocommit ausgeführt wird, wird jeder Befehl als Transaktion behandelt.<br /><br /> Dieser Zähler erhöht die Transaktionszählung, sobald eine BEGIN TRAN-Anweisung ausgeführt wird, unabhängig davon, ob die Transaktion später gespeichert oder zurückgesetzt wird.|  
|`UnpreparedExecs`|Gibt die Anzahl der nicht vorbereiteten Anweisungen zurück, die über die Verbindung ausgeführt wurden, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.|  
  
### <a name="retrieving-a-value"></a>Abrufen eines Werts  
 Die folgende Konsolenanwendung zeigt, wie die Statistik für eine Verbindung aktiviert, vier einzelne statistischen Werte abgerufen und diese in das Konsolenfenster geschrieben werden.  
  
> [!NOTE]
>  Im folgenden Beispiel wird das Beispiel **AdventureWorks** Datenbank in SQL Server enthalten. Bei der im Beispielcode bereitgestellten Verbindungszeichenfolge wird angenommen, dass die Datenbank auf dem lokalen Computer installiert und verfügbar ist. Ändern Sie die Verbindungszeichenfolge entsprechend der Umgebung.  
  
```vb  
Option Strict On  
  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
    Dim connectionString As String = GetConnectionString()  
  
    Using awConnection As New SqlConnection(connectionString)  
      ' StatisticsEnabled is False by default.  
      ' It must be set to True to start the   
      ' statistic collection process.  
      awConnection.StatisticsEnabled = True  
  
      Dim productSQL As String = "SELECT * FROM Production.Product"  
      Dim productAdapter As _  
          New SqlDataAdapter(productSQL, awConnection)  
  
      Dim awDataSet As New DataSet()  
  
      awConnection.Open()  
  
      productAdapter.Fill(awDataSet, "ProductTable")  
  
      ' Retrieve the current statistics as  
      ' a collection of values at this point  
      ' and time.  
      Dim currentStatistics As IDictionary = _  
          awConnection.RetrieveStatistics()  
  
      Console.WriteLine("Total Counters: " & _  
          currentStatistics.Count.ToString())  
      Console.WriteLine()  
  
      ' Retrieve a few individual values  
      ' related to the previous command.  
      Dim bytesReceived As Long = _  
          CLng(currentStatistics.Item("BytesReceived"))  
      Dim bytesSent As Long = _  
          CLng(currentStatistics.Item("BytesSent"))  
      Dim selectCount As Long = _  
          CLng(currentStatistics.Item("SelectCount"))  
      Dim selectRows As Long = _  
          CLng(currentStatistics.Item("SelectRows"))  
  
      Console.WriteLine("BytesReceived: " & bytesReceived.ToString())  
      Console.WriteLine("BytesSent: " & bytesSent.ToString())  
      Console.WriteLine("SelectCount: " & selectCount.ToString())  
      Console.WriteLine("SelectRows: " & selectRows.ToString())  
  
      Console.WriteLine()  
      Console.WriteLine("Press any key to continue")  
      Console.ReadLine()  
    End Using  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrive it from a configuration file.  
    Return "Data Source=localhost;Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Collections.Generic;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace CS_Stats_Console_GetValue  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string connectionString = GetConnectionString();  
  
      using (SqlConnection awConnection =   
        new SqlConnection(connectionString))  
      {  
        // StatisticsEnabled is False by default.  
        // It must be set to True to start the   
        // statistic collection process.  
        awConnection.StatisticsEnabled = true;  
  
        string productSQL = "SELECT * FROM Production.Product";  
        SqlDataAdapter productAdapter =   
          new SqlDataAdapter(productSQL, awConnection);  
  
        DataSet awDataSet = new DataSet();  
  
        awConnection.Open();  
  
        productAdapter.Fill(awDataSet, "ProductTable");  
        // Retrieve the current statistics as  
        // a collection of values at this point  
        // and time.  
        IDictionary currentStatistics =  
          awConnection.RetrieveStatistics();  
  
        Console.WriteLine("Total Counters: " +  
          currentStatistics.Count.ToString());  
        Console.WriteLine();  
  
        // Retrieve a few individual values  
        // related to the previous command.  
        long bytesReceived =  
            (long) currentStatistics["BytesReceived"];  
        long bytesSent =  
            (long) currentStatistics["BytesSent"];  
        long selectCount =  
            (long) currentStatistics["SelectCount"];  
        long selectRows =  
            (long) currentStatistics["SelectRows"];  
  
        Console.WriteLine("BytesReceived: " +  
            bytesReceived.ToString());  
        Console.WriteLine("BytesSent: " +  
            bytesSent.ToString());  
        Console.WriteLine("SelectCount: " +  
            selectCount.ToString());  
        Console.WriteLine("SelectRows: " +  
            selectRows.ToString());  
  
        Console.WriteLine();  
        Console.WriteLine("Press any key to continue");  
        Console.ReadLine();  
      }  
  
    }  
    private static string GetConnectionString()  
    {  
      // To avoid storing the connection string in your code,  
      // you can retrive it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +   
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
### <a name="retrieving-all-values"></a>Abrufen aller Werte  
 Die folgende Konsolenanwendung zeigt, wie die Statistik für eine Verbindung aktiviert, vier einzelne statistischen Werte abgerufen und diese in das Konsolenfenster geschrieben werden.  
  
> [!NOTE]
>  Im folgenden Beispiel wird das Beispiel **AdventureWorks** Datenbank in SQL Server enthalten. Bei der im Beispielcode bereitgestellten Verbindungszeichenfolge wird angenommen, dass die Datenbank auf dem lokalen Computer installiert und verfügbar ist. Ändern Sie die Verbindungszeichenfolge entsprechend der Umgebung.  
  
```vb  
Option Strict On  
  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  Sub Main()  
    Dim connectionString As String = GetConnectionString()  
  
    Using awConnection As New SqlConnection(connectionString)  
      ' StatisticsEnabled is False by default.  
      ' It must be set to True to start the   
      ' statistic collection process.  
      awConnection.StatisticsEnabled = True  
  
      Dim productSQL As String = "SELECT * FROM Production.Product"  
      Dim productAdapter As _  
          New SqlDataAdapter(productSQL, awConnection)  
  
      Dim awDataSet As New DataSet()  
  
      awConnection.Open()  
  
      productAdapter.Fill(awDataSet, "ProductTable")  
  
      ' Retrieve the current statistics as  
      ' a collection of values at this point  
      ' and time.  
      Dim currentStatistics As IDictionary = _  
          awConnection.RetrieveStatistics()  
  
      Console.WriteLine("Total Counters: " & _  
          currentStatistics.Count.ToString())  
      Console.WriteLine()  
  
      Console.WriteLine("Key Name and Value")  
  
      ' Note the entries are unsorted.  
      For Each entry As DictionaryEntry In currentStatistics  
        Console.WriteLine(entry.Key.ToString() & _  
            ": " & entry.Value.ToString())  
      Next  
  
      Console.WriteLine()  
      Console.WriteLine("Press any key to continue")  
      Console.ReadLine()  
    End Using  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrive it from a configuration file.  
    Return "Data Source=localhost;Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Collections.Generic;  
using System.Text;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace CS_Stats_Console_GetAll  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string connectionString = GetConnectionString();  
  
      using (SqlConnection awConnection =   
        new SqlConnection(connectionString))  
      {  
        // StatisticsEnabled is False by default.  
        // It must be set to True to start the   
        // statistic collection process.  
        awConnection.StatisticsEnabled = true;  
  
        string productSQL = "SELECT * FROM Production.Product";  
        SqlDataAdapter productAdapter =  
            new SqlDataAdapter(productSQL, awConnection);  
  
        DataSet awDataSet = new DataSet();  
  
        awConnection.Open();  
  
        productAdapter.Fill(awDataSet, "ProductTable");  
  
        // Retrieve the current statistics as  
        // a collection of values at this point  
        // and time.  
        IDictionary currentStatistics =  
            awConnection.RetrieveStatistics();  
  
        Console.WriteLine("Total Counters: " +  
            currentStatistics.Count.ToString());  
        Console.WriteLine();  
  
        Console.WriteLine("Key Name and Value");  
  
        // Note the entries are unsorted.  
        foreach (DictionaryEntry entry in currentStatistics)  
        {  
          Console.WriteLine(entry.Key.ToString() +  
              ": " + entry.Value.ToString());  
        }  
  
        Console.WriteLine();  
        Console.WriteLine("Press any key to continue");  
        Console.ReadLine();  
      }  
  
    }  
    private static string GetConnectionString()  
    {  
      // To avoid storing the connection string in your code,  
      // you can retrive it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +   
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server und ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
