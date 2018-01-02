---
title: Verbindungsereignisse
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
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: e0eb38eb764faa51524565e57826db17311fc5dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="connection-events"></a>Verbindungsereignisse
Alle .NET Framework-Datenanbieter besitzen **Verbindung** Objekte mit zwei Ereignisse, die Sie verwenden können, um informationsmeldungen aus einer Datenquelle abzurufen oder um festzustellen, den Status des eine **Verbindung** hat geändert. Die folgende Tabelle beschreibt die Ereignisse der **Verbindung** Objekt.  
  
|event|Beschreibung|  
|-----------|-----------------|  
|**InfoMessage**|Dieses Ereignis tritt auf, wenn eine Informationsmeldung aus einer Datenquelle zurückgegeben wird. Bei Informationsmeldungen handelt es sich um Meldungen aus einer Datenquelle, die keine Ausnahme auslösen.|  
|**StateChange**|Tritt auf, wenn der Status des der **Verbindung** Änderungen.|  
  
## <a name="working-with-the-infomessage-event"></a>Arbeiten mit dem "InfoMessage"-Ereignis  
 Mit dem <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis des <xref:System.Data.SqlClient.SqlConnection>-Objekts können Warnungen und Informationsmeldungen aus einer SQL Server-Datenquelle abgerufen werden. Wenn von einer Datenquelle Fehler mit einem Schweregrad zwischen 11 und 16 zurückgegeben werden, wird eine Ausnahme ausgelöst. Mit dem <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis können jedoch Meldungen aus der Datenquelle abgerufen werden, die keinem Fehler zugewiesen sind. Bei Microsoft SQL Server werden alle Meldungen mit einem Schweregrad von 10 oder weniger als Informationsmeldungen betrachtet und mit dem <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis aufgezeichnet. Weitere Informationen finden Sie unter "Error Message Severity Levels" in der SQL Server-Onlinedokumentation.  
  
 Die <xref:System.Data.SqlClient.SqlConnection.InfoMessage> -Ereignis empfängt ein <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> Objekt enthält, in dessen **Fehler** -Eigenschaft, die eine Auflistung von Nachrichten aus der Datenquelle. Sie können Abfragen, die **Fehler** Objekte in dieser Auflistung für den Fehlertext und dem Meldungstext sowie die Ursache des Fehlers. Der .NET Framework-Datenanbieter für SQL Server zeigt außerdem Details zu der Datenbank, der gespeicherten Prozedur und der Zeilennummer an, aus der die Meldung stammt.  
  
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
 Das <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis wird i. d. R. nur für Informations- und Warnmeldungen ausgelöst, die vom Server gesendet werden. Jedoch wenn ein tatsächlicher Fehler auftritt, die Ausführung der **ExecuteNonQuery** oder **ExecuteReader** Methode, die den Servervorgang initialisiert hat, angehalten, und eine Ausnahme ausgelöst.  
  
 Wenn Sie die Verarbeitung der restlichen Anweisungen in einem Befehl unabhängig von den vom Server erzeugten Fehlern fortsetzen möchten, legen sie die <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A>-Eigenschaft der <xref:System.Data.SqlClient.SqlConnection> auf `true` fest. Bei dieser Vorgehensweise wird bei Fehlern von der Verbindung das <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis ausgelöst, anstatt eine Ausnahme auszulösen und die Verarbeitung zu unterbrechen. Die Clientanwendung kann dann dieses Ereignis behandeln und auf Fehlerbedingungen reagieren.  
  
> [!NOTE]
>  Wenn aufgrund eines Fehlers mit einem Schweregrad von 17 oder höher der Server die Verarbeitung des Befehls abbricht, muss dieser Fehler als Ausnahme behandelt werden. In diesem Fall wird unabhängig davon, wie der Fehler im <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis behandelt wird, eine Ausnahme ausgelöst.  
  
## <a name="working-with-the-statechange-event"></a>Arbeiten mit dem "StateChange"-Ereignis  
 Die **StateChange** Ereignis tritt auf, wenn der Status der eine **Verbindung** Änderungen. Die **StateChange** -Ereignis empfängt <xref:System.Data.StateChangeEventArgs> , mit denen Sie die Änderung am Zustand des bestimmen die **Verbindung** mithilfe der **OriginalState** und **CurrentState** Eigenschaften. Die **OriginalState** Eigenschaft ist ein <xref:System.Data.ConnectionState> -Enumeration, der den Status der gibt an die **Verbindung** vor der Änderung. **CurrentState** ist ein <xref:System.Data.ConnectionState> -Enumeration, der den Status der gibt an die **Verbindung** nach der Änderung.  
  
 Im folgenden Codebeispiel wird mit der **StateChange** Ereignis, um eine Nachricht in die Konsole geschrieben bei den Status der **Verbindung** Änderungen.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Aufbauen der Verbindung zu einer Datenquelle](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
