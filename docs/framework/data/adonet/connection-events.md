---
title: Verbindungsereignisse
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
ms.openlocfilehash: a7ad0d4d950da71db0aebca872949fa82669c5c5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151700"
---
# <a name="connection-events"></a><span data-ttu-id="23a5d-102">Verbindungsereignisse</span><span class="sxs-lookup"><span data-stu-id="23a5d-102">Connection Events</span></span>
<span data-ttu-id="23a5d-103">Alle .NET Framework-Datenanbieter verfügen über **Verbindungsobjekte** mit zwei Ereignissen, mit denen Sie Informationsnachrichten aus einer Datenquelle abrufen oder bestimmen können, ob sich der Status einer **Verbindung** geändert hat.</span><span class="sxs-lookup"><span data-stu-id="23a5d-103">All of the .NET Framework data providers have **Connection** objects with two events that you can use to retrieve informational messages from a data source or to determine if the state of a **Connection** has changed.</span></span> <span data-ttu-id="23a5d-104">In der folgenden Tabelle **Connection** werden die Ereignisse des Connection-Objekts beschrieben.</span><span class="sxs-lookup"><span data-stu-id="23a5d-104">The following table describes the events of the **Connection** object.</span></span>  
  
|<span data-ttu-id="23a5d-105">Ereignis</span><span class="sxs-lookup"><span data-stu-id="23a5d-105">Event</span></span>|<span data-ttu-id="23a5d-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23a5d-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="23a5d-107">**Infomessage**</span><span class="sxs-lookup"><span data-stu-id="23a5d-107">**InfoMessage**</span></span>|<span data-ttu-id="23a5d-108">Dieses Ereignis tritt auf, wenn eine Informationsmeldung aus einer Datenquelle zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="23a5d-108">Occurs when an informational message is returned from a data source.</span></span> <span data-ttu-id="23a5d-109">Bei Informationsmeldungen handelt es sich um Meldungen aus einer Datenquelle, die keine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="23a5d-109">Informational messages are messages from a data source that do not result in an exception being thrown.</span></span>|  
|<span data-ttu-id="23a5d-110">**StateChange**</span><span class="sxs-lookup"><span data-stu-id="23a5d-110">**StateChange**</span></span>|<span data-ttu-id="23a5d-111">Tritt auf, wenn sich der Status der **Verbindung** ändert.</span><span class="sxs-lookup"><span data-stu-id="23a5d-111">Occurs when the state of the **Connection** changes.</span></span>|  
  
## <a name="working-with-the-infomessage-event"></a><span data-ttu-id="23a5d-112">Arbeiten mit dem "InfoMessage"-Ereignis</span><span class="sxs-lookup"><span data-stu-id="23a5d-112">Working with the InfoMessage Event</span></span>  
 <span data-ttu-id="23a5d-113">Mit dem <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis des <xref:System.Data.SqlClient.SqlConnection>-Objekts können Warnungen und Informationsmeldungen aus einer SQL Server-Datenquelle abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="23a5d-113">You can retrieve warnings and informational messages from a SQL Server data source using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="23a5d-114">Wenn von einer Datenquelle Fehler mit einem Schweregrad zwischen 11 und 16 zurückgegeben werden, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="23a5d-114">Errors returned from the data source with a severity level of 11 through 16 cause an exception to be thrown.</span></span> <span data-ttu-id="23a5d-115">Mit dem <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis können jedoch Meldungen aus der Datenquelle abgerufen werden, die keinem Fehler zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="23a5d-115">However, the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event can be used to obtain messages from the data source that are not associated with an error.</span></span> <span data-ttu-id="23a5d-116">Bei Microsoft SQL Server werden alle Meldungen mit einem Schweregrad von 10 oder weniger als Informationsmeldungen betrachtet und mit dem <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="23a5d-116">In the case of Microsoft SQL Server, any error with a severity of 10 or less is considered to be an informational message, and can be captured by using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span> <span data-ttu-id="23a5d-117">Weitere Informationen finden Sie im Artikel ["Datenbankmodulfehlerschweregrade".](/sql/relational-databases/errors-events/database-engine-error-severities)</span><span class="sxs-lookup"><span data-stu-id="23a5d-117">For more information, see the [Database Engine Error Severities](/sql/relational-databases/errors-events/database-engine-error-severities) article.</span></span>
  
 <span data-ttu-id="23a5d-118">Das <xref:System.Data.SqlClient.SqlConnection.InfoMessage> Ereignis <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> empfängt ein Objekt, das in seiner **Errors-Eigenschaft** eine Auflistung der Nachrichten aus der Datenquelle enthält.</span><span class="sxs-lookup"><span data-stu-id="23a5d-118">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event receives an <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> object containing, in its **Errors** property, a collection of the messages from the data source.</span></span> <span data-ttu-id="23a5d-119">Sie können die **Error-Objekte** in dieser Auflistung nach der Fehlernummer und dem Nachrichtentext sowie der Fehlerquelle abfragen.</span><span class="sxs-lookup"><span data-stu-id="23a5d-119">You can query the **Error** objects in this collection for the error number and message text, as well as the source of the error.</span></span> <span data-ttu-id="23a5d-120">Der .NET Framework-Datenanbieter für SQL Server zeigt außerdem Details zu der Datenbank, der gespeicherten Prozedur und der Zeilennummer an, aus der die Meldung stammt.</span><span class="sxs-lookup"><span data-stu-id="23a5d-120">The .NET Framework Data Provider for SQL Server also includes detail about the database, stored procedure, and line number that the message came from.</span></span>  
  
### <a name="example"></a><span data-ttu-id="23a5d-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="23a5d-121">Example</span></span>  
 <span data-ttu-id="23a5d-122">Im folgenden Codebeispiel wird veranschaulicht, wie für das <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis ein Ereignishandler hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="23a5d-122">The following code example shows how to add an event handler for the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
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
  
## <a name="handling-errors-as-infomessages"></a><span data-ttu-id="23a5d-123">Behandeln von Fehlern als "InfoMessages"</span><span class="sxs-lookup"><span data-stu-id="23a5d-123">Handling Errors as InfoMessages</span></span>  
 <span data-ttu-id="23a5d-124">Das <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis wird i. d. R. nur für Informations- und Warnmeldungen ausgelöst, die vom Server gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="23a5d-124">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event will normally fire only for informational and warning messages that are sent from the server.</span></span> <span data-ttu-id="23a5d-125">Wenn jedoch ein tatsächlicher Fehler auftritt, wird die Ausführung der **ExecuteNonQuery-** oder **ExecuteReader-Methode** angehalten, die den Servervorgang initiiert hat, und eine Ausnahme wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="23a5d-125">However, when an actual error occurs, the execution of the **ExecuteNonQuery** or **ExecuteReader** method that initiated the server operation is halted and an exception is thrown.</span></span>  
  
 <span data-ttu-id="23a5d-126">Wenn Sie die Verarbeitung der restlichen Anweisungen in einem Befehl unabhängig von den vom Server erzeugten Fehlern fortsetzen möchten, legen sie die <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A>-Eigenschaft der <xref:System.Data.SqlClient.SqlConnection> auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="23a5d-126">If you want to continue processing the rest of the statements in a command regardless of any errors produced by the server, set the <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> property of the <xref:System.Data.SqlClient.SqlConnection> to `true`.</span></span> <span data-ttu-id="23a5d-127">Bei dieser Vorgehensweise wird bei Fehlern von der Verbindung das <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis ausgelöst, anstatt eine Ausnahme auszulösen und die Verarbeitung zu unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="23a5d-127">Doing this causes the connection to fire the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event for errors instead of throwing an exception and interrupting processing.</span></span> <span data-ttu-id="23a5d-128">Die Clientanwendung kann dann dieses Ereignis behandeln und auf Fehlerbedingungen reagieren.</span><span class="sxs-lookup"><span data-stu-id="23a5d-128">The client application can then handle this event and respond to error conditions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="23a5d-129">Wenn aufgrund eines Fehlers mit einem Schweregrad von 17 oder höher der Server die Verarbeitung des Befehls abbricht, muss dieser Fehler als Ausnahme behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="23a5d-129">An error with a severity level of 17 or above that causes the server to stop processing the command must be handled as an exception.</span></span> <span data-ttu-id="23a5d-130">In diesem Fall wird unabhängig davon, wie der Fehler im <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis behandelt wird, eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="23a5d-130">In this case, an exception is thrown regardless of how the error is handled in the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
## <a name="working-with-the-statechange-event"></a><span data-ttu-id="23a5d-131">Arbeiten mit dem "StateChange"-Ereignis</span><span class="sxs-lookup"><span data-stu-id="23a5d-131">Working with the StateChange Event</span></span>  
 <span data-ttu-id="23a5d-132">Das **StateChange-Ereignis** tritt auf, wenn sich der Status einer **Verbindung** ändert.</span><span class="sxs-lookup"><span data-stu-id="23a5d-132">The **StateChange** event occurs when the state of a **Connection** changes.</span></span> <span data-ttu-id="23a5d-133">Das **StateChange-Ereignis** <xref:System.Data.StateChangeEventArgs> empfängt, mit dem Sie die Änderung des Status der **Verbindung** mithilfe der **Eigenschaften OriginalState** und **CurrentState** bestimmen können.</span><span class="sxs-lookup"><span data-stu-id="23a5d-133">The **StateChange** event receives <xref:System.Data.StateChangeEventArgs> that enable you to determine the change in state of the **Connection** by using the **OriginalState** and **CurrentState** properties.</span></span> <span data-ttu-id="23a5d-134">Die **OriginalState-Eigenschaft** ist eine <xref:System.Data.ConnectionState> Enumeration, die den Status der **Verbindung** angibt, bevor sie geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="23a5d-134">The **OriginalState** property is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** before it changed.</span></span> <span data-ttu-id="23a5d-135">**CurrentState** ist <xref:System.Data.ConnectionState> eine Enumeration, die den Status der **Verbindung** angibt, nachdem sie geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="23a5d-135">**CurrentState** is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** after it changed.</span></span>  
  
 <span data-ttu-id="23a5d-136">Im folgenden Codebeispiel wird das **StateChange-Ereignis** verwendet, um eine Nachricht in die Konsole zu schreiben, wenn sich der Status der **Verbindung** ändert.</span><span class="sxs-lookup"><span data-stu-id="23a5d-136">The following code example uses the **StateChange** event to write a message to the console when the state of the **Connection** changes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="23a5d-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="23a5d-137">See also</span></span>

- [<span data-ttu-id="23a5d-138">Herstellen der Verbindung mit einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="23a5d-138">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="23a5d-139">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="23a5d-139">ADO.NET Overview</span></span>](ado-net-overview.md)
