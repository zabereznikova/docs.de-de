---
title: Verbindungsereignisse
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
ms.openlocfilehash: fd935306a493bf5a20f5cd6cd61a175c02d8bbba
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203760"
---
# <a name="connection-events"></a>Verbindungsereignisse

Alle .NET Framework Datenanbieter verfügen über **Verbindungs** Objekte mit zwei Ereignissen, mit denen Sie Informationsmeldungen aus einer Datenquelle abrufen oder ermitteln können, ob sich der Status einer **Verbindung** geändert hat. In der folgenden Tabelle werden die Ereignisse des **Connection** -Objekts beschrieben.  
  
|Ereignis|Beschreibung|  
|-----------|-----------------|  
|**Info Message**|Dieses Ereignis tritt auf, wenn eine Informationsmeldung aus einer Datenquelle zurückgegeben wird. Bei Informationsmeldungen handelt es sich um Meldungen aus einer Datenquelle, die keine Ausnahme auslösen.|  
|**StateChange**|Tritt auf, wenn sich der Zustand der **Verbindung** ändert.|  
  
## <a name="working-with-the-infomessage-event"></a>Arbeiten mit dem "InfoMessage"-Ereignis  

 Mit dem <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis des <xref:System.Data.SqlClient.SqlConnection>-Objekts können Warnungen und Informationsmeldungen aus einer SQL Server-Datenquelle abgerufen werden. Wenn von einer Datenquelle Fehler mit einem Schweregrad zwischen 11 und 16 zurückgegeben werden, wird eine Ausnahme ausgelöst. Mit dem <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis können jedoch Meldungen aus der Datenquelle abgerufen werden, die keinem Fehler zugewiesen sind. Bei Microsoft SQL Server werden alle Meldungen mit einem Schweregrad von 10 oder weniger als Informationsmeldungen betrachtet und mit dem <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis aufgezeichnet. Weitere Informationen finden Sie im Artikel [Datenbank-Engine Fehler Schweregrade](/sql/relational-databases/errors-events/database-engine-error-severities) .
  
 Das- <xref:System.Data.SqlClient.SqlConnection.InfoMessage> Ereignis empfängt ein <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> Objekt, das in der **Errors** -Eigenschaft eine Sammlung der Nachrichten aus der Datenquelle enthält. Sie können die **Fehler** Objekte in dieser Sammlung nach der Fehlernummer und dem Meldungs Text und der Fehlerquelle Abfragen. Der .NET Framework-Datenanbieter für SQL Server zeigt außerdem Details zu der Datenbank, der gespeicherten Prozedur und der Zeilennummer an, aus der die Meldung stammt.  
  
### <a name="example"></a>Beispiel  

 Im folgenden Codebeispiel wird veranschaulicht, wie für das <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis ein Ereignishandler hinzugefügt wird.  
  
```vb  
' Assumes that connection represents a SqlConnection object.  
  AddHandler connection.InfoMessage, _  
    New SqlInfoMessageEventHandler(AddressOf OnInfoMessage)  
  
Private Shared Sub OnInfoMessage(sender As Object, _  
  args As SqlInfoMessageEventArgs)  
  Dim err As SqlError  
  For Each err In args.Errors  
    Console.WriteLine("The {0} has received a severity {1}, _  
       state {2} error number {3}\n" & _  
      "on line {4} of procedure {5} on server {6}:\n{7}", _  
      err.Source, err.Class, err.State, err.Number, err.LineNumber, _  
    err.Procedure, err.Server, err.Message)  
  Next  
End Sub  
```  
  
```csharp  
// Assumes that connection represents a SqlConnection object.  
  connection.InfoMessage +=
    new SqlInfoMessageEventHandler(OnInfoMessage);  
  
protected static void OnInfoMessage(  
  object sender, SqlInfoMessageEventArgs args)  
{  
  foreach (SqlError err in args.Errors)  
  {  
    Console.WriteLine(  
  "The {0} has received a severity {1}, state {2} error number {3}\n" +  
  "on line {4} of procedure {5} on server {6}:\n{7}",  
   err.Source, err.Class, err.State, err.Number, err.LineNumber,
   err.Procedure, err.Server, err.Message);  
  }  
}  
```  
  
## <a name="handling-errors-as-infomessages"></a>Behandeln von Fehlern als "InfoMessages"  

 Das <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis wird i. d. R. nur für Informations- und Warnmeldungen ausgelöst, die vom Server gesendet werden. Wenn jedoch ein tatsächlicher Fehler auftritt, wird die Ausführung der **ExecuteNonQuery** -Methode oder der **ExecuteReader** -Methode, die den Server Vorgang initiiert hat, angehalten, und es wird eine Ausnahme ausgelöst.  
  
 Wenn Sie die Verarbeitung der restlichen Anweisungen in einem Befehl unabhängig von den vom Server erzeugten Fehlern fortsetzen möchten, legen sie die <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A>-Eigenschaft der <xref:System.Data.SqlClient.SqlConnection> auf `true` fest. Bei dieser Vorgehensweise wird bei Fehlern von der Verbindung das <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis ausgelöst, anstatt eine Ausnahme auszulösen und die Verarbeitung zu unterbrechen. Die Clientanwendung kann dann dieses Ereignis behandeln und auf Fehlerbedingungen reagieren.  
  
> [!NOTE]
> Wenn aufgrund eines Fehlers mit einem Schweregrad von 17 oder höher der Server die Verarbeitung des Befehls abbricht, muss dieser Fehler als Ausnahme behandelt werden. In diesem Fall wird unabhängig davon, wie der Fehler im <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis behandelt wird, eine Ausnahme ausgelöst.  
  
## <a name="working-with-the-statechange-event"></a>Arbeiten mit dem "StateChange"-Ereignis  

 Das **StateChange** -Ereignis tritt auf, wenn sich der Status einer **Verbindung** ändert. Das **StateChange** -Ereignis empfängt <xref:System.Data.StateChangeEventArgs> , das es Ihnen ermöglicht, die Änderung des Zustands der **Verbindung** mithilfe der **OriginalState** -Eigenschaft und der **CurrentState** -Eigenschaft zu bestimmen. Die **OriginalState** -Eigenschaft ist eine- <xref:System.Data.ConnectionState> Enumeration, die den Zustand der **Verbindung** vor der Änderung angibt. **CurrentState** ist eine- <xref:System.Data.ConnectionState> Enumeration, die den Zustand der **Verbindung** angibt, nachdem Sie geändert wurde.  
  
 Im folgenden Codebeispiel wird das **StateChange** -Ereignis verwendet, um eine Meldung in die Konsole zu schreiben, wenn sich der Zustand der **Verbindung** ändert.  
  
```vb  
' Assumes connection represents a SqlConnection object.  
  AddHandler connection.StateChange, _  
    New StateChangeEventHandler(AddressOf OnStateChange)  
  
Protected Shared Sub OnStateChange( _  
  sender As Object, args As StateChangeEventArgs)  
  
  Console.WriteLine( _  
  "The current Connection state has changed from {0} to {1}.", _  
  args.OriginalState, args.CurrentState)  
End Sub  
```  
  
```csharp  
// Assumes connection represents a SqlConnection object.  
  connection.StateChange  += new StateChangeEventHandler(OnStateChange);  
  
protected static void OnStateChange(object sender,
  StateChangeEventArgs args)  
{  
  Console.WriteLine(  
    "The current Connection state has changed from {0} to {1}.",  
      args.OriginalState, args.CurrentState);  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Herstellen der Verbindung mit einer Datenquelle](connecting-to-a-data-source.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
