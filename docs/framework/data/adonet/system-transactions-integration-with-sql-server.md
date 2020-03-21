---
title: System.Transactions-Integration in SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b555544e-7abb-4814-859b-ab9cdd7d8716
ms.openlocfilehash: 42007dafbdc9f61b9fc0776e0aaa2987551b704a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174237"
---
# <a name="systemtransactions-integration-with-sql-server"></a>System.Transactions-Integration in SQL Server
Mit .NET Framework Version 2.0 wurde ein Transaktionsframework eingeführt, auf das über den <xref:System.Transactions> Namespace zugegriffen werden kann. Dieses Framework macht Transaktionen auf eine Weise verfügbar, die voll in das .NET Framework einschließlich ADO.NET integriert ist.  
  
 Zusätzlich zu den Verbesserungen der <xref:System.Transactions> Programmierbarkeit und ADO.NET können zusammenarbeiten, um Optimierungen zu koordinieren, wenn Sie mit Transaktionen arbeiten. Eine heraufstufbare Transaktion ist eine kompakte (lokale) Transaktion, die automatisch bei Bedarf auf eine vollverteilte Transaktion höhergestuft werden kann.  
  
 Beginnend mit ADO.NET 2.0, <xref:System.Data.SqlClient> unterstützt promotable Transaktionen, wenn Sie mit SQL Server arbeiten. Eine heraufstufbare Transaktion ruft den zusätzlichen Aufwand einer verteilten Transaktion nur hervor, wenn dieser erforderlich ist. Promotable-Transaktionen sind automatisch und erfordern keine Intervention des Entwicklers.  
  
 Promotable-Transaktionen sind nur verfügbar, wenn Sie den .NET`SqlClient`Framework-Datenanbieter für SQL Server ( ) mit SQL Server verwenden.  
  
## <a name="creating-promotable-transactions"></a>Erstellen heraufstufbarer Transaktionen  
 Der .NET Framework-Anbieter für SQL Server bietet Unterstützung für heraufstufbare Transaktionen, die über die Klassen im .NET Framework <xref:System.Transactions>-Namespace behandelt werden. Heraufstufbare Transaktionen optimieren verteilte Transaktionen, indem sie das Erstellen einer verteilten Transaktion verzögern, bis diese benötigt wird. Wenn nur ein Ressourcen-Manager erforderlich ist, erfolgt keine verteilte Transaktion.  
  
> [!NOTE]
> In einem teilweise vertrauenswürdigen Szenario wird die <xref:System.Transactions.DistributedTransactionPermission> benötigt, wenn eine Transaktion zu einer verteilten Transaktion heraufgestuft wird.  
  
## <a name="promotable-transaction-scenarios"></a>Szenarien für heraufstufbare Transaktionen  
 Heraufstufbare Transaktionen beanspruchen normalerweise erhebliche Systemressourcen und werden von MS DTC (Microsoft Distributed Transaction Coordinator) verwaltet, der alle Ressourcen-Manager integriert, auf die in der Transaktion zugegriffen wird. Eine promotable Transaktion ist eine <xref:System.Transactions> spezielle Form einer Transaktion, die die Arbeit effektiv an eine einfache SQL Server-Transaktion delegiert. <xref:System.Transactions>, <xref:System.Data.SqlClient>und SQL Server koordinieren die Arbeit bei der Verarbeitung der Transaktion und werden bei Bedarf zu einer vollständigen verteilten Transaktion heraufbeauft.  
  
 Der Vorteil der Verwendung heraufstufbarer Transaktionen besteht darin, dass beim Öffnen einer Verbindung mit einer aktiven <xref:System.Transactions.TransactionScope> -Transaktion die Transaktion als kompakte Transaktion durchgeführt wird, wenn keine weiteren Verbindungen geöffnet sind und der zusätzliche Mehraufwand einer vollständig verteilten Transaktion vermieden werden kann.  
  
### <a name="connection-string-keywords"></a>Schlüsselwörter für Verbindungszeichenfolgen  
 Die <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> -Eigenschaft unterstützt ein Schlüsselwort, `Enlist`, das angibt, ob der <xref:System.Data.SqlClient> Transaktionskontexte erkennt, und die Verbindung automatisch in einer verteilten Transaktion einträgt. Wenn `Enlist=true`, wird die Verbindung automatisch im aktuellen Transaktionskontext des öffnenden Threads eingetragen. Wenn `Enlist=false`, interagiert der `SqlClient` nicht mit einer verteilten Transaktion. Der Standardwert für `Enlist` ist "true". Wenn `Enlist` in der Verbindungszeichenfolge nicht angegeben ist, wird die Verbindung automatisch in einer verteilten Transaktion eingetragen, wenn eine solche zum Zeitpunkt des Öffnens der Verbindung erkannt wird.  
  
 Die `Transaction Binding` -Schlüsselwörter in einer <xref:System.Data.SqlClient.SqlConnection> -Verbindungszeichenfolge steuern die Zuordnung einer Verbindung mit einer eingetragenen `System.Transactions` -Transaktion. Diese ist auch verfügbar durch die <xref:System.Data.SqlClient.SqlConnectionStringBuilder.TransactionBinding%2A> -Eigenschaft eines <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.  
  
 In der folgenden Tabelle sind die möglichen Werte beschrieben.  
  
|Schlüsselwort|Beschreibung|  
|-------------|-----------------|  
|Implicit Unbind|Der Standardwert. Die Verbindung wird von der Transaktion getrennt, wenn diese endet, und wechselt damit zurück in den Autocommit-Modus.|  
|Explicit Unbind|Die Verbindung bleibt so lange an die Transaktion gebunden, bis die Transaktion geschlossen wird. Die Verbindung schlägt fehl, wenn die zugehörige Transaktion nicht aktiv ist oder <xref:System.Transactions.Transaction.Current%2A>nicht entspricht.|  
  
## <a name="using-transactionscope"></a>Verwenden von "TransactionScope"  
 Die <xref:System.Transactions.TransactionScope>-Klasse bewirkt, dass ein Codeblock transaktional wird, indem sie Verbindungen implizit in einer verteilten Transaktion einträgt. Sie müssen die <xref:System.Transactions.TransactionScope.Complete%2A> -Methode am Ende des <xref:System.Transactions.TransactionScope> -Blocks vor dem Verlassen aufrufen. Beim Verlassen des Blocks wird die <xref:System.Transactions.TransactionScope.Dispose%2A> -Methode aufgerufen. Wenn eine Ausnahme aufgerufen wurde, die den Code veranlasst, den Bereich zu verlassen, wird die Transaktion als abgebrochen angesehen.  
  
 Es wird empfohlen, einen `using` -Block zu verwenden, um sicherzustellen, dass <xref:System.Transactions.TransactionScope.Dispose%2A> für das <xref:System.Transactions.TransactionScope> -Objekt aufgerufen wird, wenn der verwendete Block beendet wird. Durch das Fehlschlagen von Commits oder Rollbacks ausstehender Transaktionen kann die Leistung entscheidend beeinträchtigt werden, da das Zeitlimit für <xref:System.Transactions.TransactionScope> eine Minute beträgt. Wenn Sie keine `using`-Anweisung verwenden, müssen Sie alle Arbeiten in einem `Try`-Block ausführen und die <xref:System.Transactions.TransactionScope.Dispose%2A>-Methode im `Finally`-Block explizit aufrufen.  
  
 Wenn innerhalb des <xref:System.Transactions.TransactionScope>eine Ausnahme auftritt, wird die Transaktion als inkonsistent markiert und abgebrochen. Sie wird zurückgesetzt, wenn der <xref:System.Transactions.TransactionScope> verworfen wird. Wenn keine Ausnahme auftritt, wird für teilnehmende Transaktionen ein Commit ausgeführt.  
  
> [!NOTE]
> Die `TransactionScope`-Klasse erstellt <xref:System.Transactions.Transaction.IsolationLevel%2A> standardmäßig mit dem Wert `Serializable`. Je nach Ihrer Anwendung kann es vorteilhaft sein, die Isolationsstufe herabzusetzen, um ein hohes Konfliktpotenzial in der Anwendung zu vermeiden.  
  
> [!NOTE]
> Es wird empfohlen, dass Sie nur Update-, Einfüge- und Löschvorgänge in verteilten Transaktionen durchführen, da diese erhebliche Datenbankressorcen beanspruchen. Select-Anweisungen können Datenbankressourcen unnötigerweise blockieren, und in einigen Szenarien kann es erforderlich sein, Transaktionen für Select-Vorgänge zu verwenden. Arbeiten, die nicht mit der Datenbank zusammenhängen, sollten außerhalb des Bereichs der Transaktion durchgeführt werden, außer wenn andere transaktive Ressourcen-Manager verwendet werden. Obwohl eine Ausnahme innerhalb des Bereichs der Transaktion dazu führt, dass die Transaktion keinen Commit ausführt, verfügt die <xref:System.Transactions.TransactionScope> -Klasse über keine Funktion zum Zurücksetzen von Änderungen, die vom Code außerhalb des Bereichs der Transaktion selbst durchgeführt wurden. Wenn Sie beim Zurücksetzen der Transaktion Maßnahmen ergreifen müssen, müssen Sie Ihre eigene Implementierung der <xref:System.Transactions.IEnlistmentNotification> -Schnittstelle schreiben und in der Transaktion explizit eintragen.  
  
## <a name="example"></a>Beispiel  
 Das Arbeiten mit <xref:System.Transactions> setzt einen Verweis auf "System.Transactions.dll" voraus.  
  
 Die folgende Funktion zeigt das Erstellen einer heraufstufbaren Transaktion für zwei verschiedene SQL Server-Instanzen, die von zwei verschiedenen <xref:System.Data.SqlClient.SqlConnection> -Objekten dargestellt werden, die ihrerseits von einem <xref:System.Transactions.TransactionScope> -Block umschlossen sind. Der Code erstellt den <xref:System.Transactions.TransactionScope> -Block mit einer `using` -Anweisung und öffnet die erste Verbindung, durch die er automatisch im <xref:System.Transactions.TransactionScope>eingetragen wird. Die Transaktion wird anfänglich als einfache Transaktion, nicht als vollständig verteilte Transaktion, eingetragen. Die zweite Verbindung wird nur dann im <xref:System.Transactions.TransactionScope> eingetragen, wenn der Befehl in der ersten Verbindung keine Ausnahme auslöst. Wenn die zweite Verbindung geöffnet wird, wird die Transaktion automatisch auf eine vollständig verteilte Transaktion hochgestuft. Es wird die <xref:System.Transactions.TransactionScope.Complete%2A> -Methode aufgerufen, die für die Transaktion nur dann einen Commit ausführt, wenn keine Ausnahmen ausgelöst wurden. Wenn an einem beliebigen Punkt im <xref:System.Transactions.TransactionScope> -Block eine Ausnahme ausgelöst wurde, wird `Complete` nicht aufgerufen, und die verteilte Transaktion wird zurückgenommen, sobald der <xref:System.Transactions.TransactionScope> am Ende seines `using` -Blocks verfügbar gemacht wird.  
  
```csharp  
// This function takes arguments for the 2 connection strings and commands in order  
// to create a transaction involving two SQL Servers. It returns a value > 0 if the  
// transaction committed, 0 if the transaction rolled back. To test this code, you can
// connect to two different databases on the same server by altering the connection string,  
// or to another RDBMS such as Oracle by altering the code in the connection2 code block.  
static public int CreateTransactionScope(  
    string connectString1, string connectString2,  
    string commandText1, string commandText2)  
{  
    // Initialize the return value to zero and create a StringWriter to display results.  
    int returnValue = 0;  
    System.IO.StringWriter writer = new System.IO.StringWriter();  
  
    // Create the TransactionScope in which to execute the commands, guaranteeing  
    // that both commands will commit or roll back as a single unit of work.  
    using (TransactionScope scope = new TransactionScope())  
    {  
        using (SqlConnection connection1 = new SqlConnection(connectString1))  
        {  
            try  
            {  
                // Opening the connection automatically enlists it in the
                // TransactionScope as a lightweight transaction.  
                connection1.Open();  
  
                // Create the SqlCommand object and execute the first command.  
                SqlCommand command1 = new SqlCommand(commandText1, connection1);  
                returnValue = command1.ExecuteNonQuery();  
                writer.WriteLine("Rows to be affected by command1: {0}", returnValue);  
  
                // if you get here, this means that command1 succeeded. By nesting  
                // the using block for connection2 inside that of connection1, you  
                // conserve server and network resources by opening connection2
                // only when there is a chance that the transaction can commit.
                using (SqlConnection connection2 = new SqlConnection(connectString2))  
                    try  
                    {  
                        // The transaction is promoted to a full distributed  
                        // transaction when connection2 is opened.  
                        connection2.Open();  
  
                        // Execute the second command in the second database.  
                        returnValue = 0;  
                        SqlCommand command2 = new SqlCommand(commandText2, connection2);  
                        returnValue = command2.ExecuteNonQuery();  
                        writer.WriteLine("Rows to be affected by command2: {0}", returnValue);  
                    }  
                    catch (Exception ex)  
                    {  
                        // Display information that command2 failed.  
                        writer.WriteLine("returnValue for command2: {0}", returnValue);  
                        writer.WriteLine("Exception Message2: {0}", ex.Message);  
                    }  
            }  
            catch (Exception ex)  
            {  
                // Display information that command1 failed.  
                writer.WriteLine("returnValue for command1: {0}", returnValue);  
                writer.WriteLine("Exception Message1: {0}", ex.Message);  
            }  
        }  
  
        // If an exception has been thrown, Complete will not
        // be called and the transaction is rolled back.  
        scope.Complete();  
    }  
  
    // The returnValue is greater than 0 if the transaction committed.  
    if (returnValue > 0)  
    {  
        writer.WriteLine("Transaction was committed.");  
    }  
    else  
    {  
        // You could write additional business logic here, notify the caller by  
        // throwing a TransactionAbortedException, or log the failure.  
        writer.WriteLine("Transaction rolled back.");  
    }  
  
    // Display messages.  
    Console.WriteLine(writer.ToString());  
  
    return returnValue;  
}  
```  
  
```vb  
' This function takes arguments for the 2 connection strings and commands in order  
' to create a transaction involving two SQL Servers. It returns a value > 0 if the  
' transaction committed, 0 if the transaction rolled back. To test this code, you can
' connect to two different databases on the same server by altering the connection string,  
' or to another RDBMS such as Oracle by altering the code in the connection2 code block.  
Public Function CreateTransactionScope( _  
  ByVal connectString1 As String, ByVal connectString2 As String, _  
  ByVal commandText1 As String, ByVal commandText2 As String) As Integer  
  
    ' Initialize the return value to zero and create a StringWriter to display results.  
    Dim returnValue As Integer = 0  
    Dim writer As System.IO.StringWriter = New System.IO.StringWriter  
  
    ' Create the TransactionScope in which to execute the commands, guaranteeing  
    ' that both commands will commit or roll back as a single unit of work.  
    Using scope As New TransactionScope()  
        Using connection1 As New SqlConnection(connectString1)  
            Try  
                ' Opening the connection automatically enlists it in the
                ' TransactionScope as a lightweight transaction.  
                connection1.Open()  
  
                ' Create the SqlCommand object and execute the first command.  
                Dim command1 As SqlCommand = New SqlCommand(commandText1, connection1)  
                returnValue = command1.ExecuteNonQuery()  
                writer.WriteLine("Rows to be affected by command1: {0}", returnValue)  
  
                ' If you get here, this means that command1 succeeded. By nesting  
                ' the Using block for connection2 inside that of connection1, you  
                ' conserve server and network resources by opening connection2
                ' only when there is a chance that the transaction can commit.
                Using connection2 As New SqlConnection(connectString2)  
                    Try  
                        ' The transaction is promoted to a full distributed  
                        ' transaction when connection2 is opened.  
                        connection2.Open()  
  
                        ' Execute the second command in the second database.  
                        returnValue = 0  
                        Dim command2 As SqlCommand = New SqlCommand(commandText2, connection2)  
                        returnValue = command2.ExecuteNonQuery()  
                        writer.WriteLine("Rows to be affected by command2: {0}", returnValue)  
  
                    Catch ex As Exception  
                        ' Display information that command2 failed.  
                        writer.WriteLine("returnValue for command2: {0}", returnValue)  
                        writer.WriteLine("Exception Message2: {0}", ex.Message)  
                    End Try  
                End Using  
  
            Catch ex As Exception  
                ' Display information that command1 failed.  
                writer.WriteLine("returnValue for command1: {0}", returnValue)  
                writer.WriteLine("Exception Message1: {0}", ex.Message)  
            End Try  
        End Using  
  
        ' If an exception has been thrown, Complete will
        ' not be called and the transaction is rolled back.  
        scope.Complete()  
    End Using  
  
    ' The returnValue is greater than 0 if the transaction committed.  
    If returnValue > 0 Then  
        writer.WriteLine("Transaction was committed.")  
    Else  
        ' You could write additional business logic here, notify the caller by  
        ' throwing a TransactionAbortedException, or log the failure.  
       writer.WriteLine("Transaction rolled back.")  
     End If  
  
    ' Display messages.  
    Console.WriteLine(writer.ToString())  
  
    Return returnValue  
End Function  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Transaktionen und Parallelität](transactions-and-concurrency.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
