---
title: "&#39;Connection&#39;-Ereignisse | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# &#39;Connection&#39;-Ereignisse
Alle .NET Framework\-Datenanbieter verfügen über **Connection**\-Objekte mit zwei Ereignissen, mit denen Sie Informationsmeldungen aus einer Datenquelle abrufen oder eine Statusänderung eines **Connection**\-Objekts feststellen können.  In der folgenden Tabelle werden die Ereignisse des **Connection**\-Objekts beschrieben.  
  
|Ereignis|Beschreibung|  
|--------------|------------------|  
|**InfoMessage**|Dieses Ereignis tritt auf, wenn eine Informationsmeldung aus einer Datenquelle zurückgegeben wird.  Bei Informationsmeldungen handelt es sich um Meldungen aus einer Datenquelle, die keine Ausnahme auslösen.|  
|**StateChange**|Tritt auf, wenn sich der Status des **Connection**\-Objekts ändert.|  
  
## Arbeiten mit dem "InfoMessage"\-Ereignis  
 Mit dem <xref:System.Data.SqlClient.SqlConnection.InfoMessage>\-Ereignis des <xref:System.Data.SqlClient.SqlConnection>\-Objekts können Warnungen und Informationsmeldungen aus einer SQL Server\-Datenquelle abgerufen werden.  Wenn von einer Datenquelle Fehler mit einem Schweregrad zwischen 11 und 16 zurückgegeben werden, wird eine Ausnahme ausgelöst.  Mit dem <xref:System.Data.SqlClient.SqlConnection.InfoMessage>\-Ereignis können jedoch Meldungen aus der Datenquelle abgerufen werden, die keinem Fehler zugewiesen sind.  Bei Microsoft SQL Server werden alle Meldungen mit einem Schweregrad von 10 oder weniger als Informationsmeldungen betrachtet und mit dem <xref:System.Data.SqlClient.SqlConnection.InfoMessage>\-Ereignis aufgezeichnet.  Weitere Informationen finden Sie unter "Error Message Severity Levels" in der SQL Server\-Onlinedokumentation.  
  
 Das <xref:System.Data.SqlClient.SqlConnection.InfoMessage>\-Ereignis empfängt ein <xref:System.Data.SqlClient.SqlInfoMessageEventArgs>\-Objekt, das in der **Errors**\-Eigenschaft eine Auflistung der Meldungen von einer Datenquelle enthält.  Die **Error**\-Objekte in dieser Auflistung können nach der Fehlernummer und dem Meldungstext sowie der Quelle des Fehlers abgefragt werden.  Der .NET Framework\-Datenanbieter für SQL Server zeigt außerdem Details zu der Datenbank, der gespeicherten Prozedur und der Zeilennummer an, aus der die Meldung stammt.  
  
### Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie für das <xref:System.Data.SqlClient.SqlConnection.InfoMessage>\-Ereignis ein Ereignishandler hinzugefügt wird.  
  
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
  
## Behandeln von Fehlern als "InfoMessages"  
 Das <xref:System.Data.SqlClient.SqlConnection.InfoMessage>\-Ereignis wird i. d. R. nur für Informations\- und Warnmeldungen ausgelöst, die vom Server gesendet werden.  Bei einem tatsächlichen Fehler wird die Ausführung der **ExecuteNonQuery**\-Methode oder der **ExecuteReader**\-Methode, die den Servervorgang initialisiert hat, angehalten und eine Ausnahme ausgelöst.  
  
 Wenn Sie die Verarbeitung der restlichen Anweisungen in einem Befehl unabhängig von den vom Server erzeugten Fehlern fortsetzen möchten, legen sie die <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A>\-Eigenschaft der <xref:System.Data.SqlClient.SqlConnection> auf `true` fest.  Bei dieser Vorgehensweise wird bei Fehlern von der Verbindung das <xref:System.Data.SqlClient.SqlConnection.InfoMessage>\-Ereignis ausgelöst, anstatt eine Ausnahme auszulösen und die Verarbeitung zu unterbrechen.  Die Clientanwendung kann dann dieses Ereignis behandeln und auf Fehlerbedingungen reagieren.  
  
> [!NOTE]
>  Wenn aufgrund eines Fehlers mit einem Schweregrad von 17 oder höher der Server die Verarbeitung des Befehls abbricht, muss dieser Fehler als Ausnahme behandelt werden.  In diesem Fall wird unabhängig davon, wie der Fehler im <xref:System.Data.SqlClient.SqlConnection.InfoMessage>\-Ereignis behandelt wird, eine Ausnahme ausgelöst.  
  
## Arbeiten mit dem "StateChange"\-Ereignis  
 Das **StateChange**\-Ereignis tritt auf, wenn sich der Status eines **Connection**\-Objekts ändert.  Das **StateChange**\-Ereignis erhält <xref:System.Data.StateChangeEventArgs>, mit denen Sie anhand der **OriginalState**\-Eigenschaft und der **CurrentState**\-Eigenschaft Statusänderungen des **Connection**\-Objekts ermitteln können.  Die **OriginalState**\-Eigenschaft ist eine <xref:System.Data.ConnectionState>\-Enumeration, die den Status des **Connection**\-Objekts vor der Änderung angibt.  Die **CurrentState**\-Eigenschaft ist eine <xref:System.Data.ConnectionState>\-Enumeration, die den Status des **Connection**\-Objekts nach der Änderung angibt.  
  
 Im folgenden Codebeispiel wird mit dem **StateChange**\-Ereignis eine Meldung in die Konsole geschrieben, sobald sich der Status des **Connection**\-Objekts ändert.  
  
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
  
## Siehe auch  
 [Aufbauen der Verbindung zu einer Datenquelle](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)