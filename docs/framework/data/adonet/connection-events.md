---
title: Verbindungsereignisse
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
ms.openlocfilehash: a71758781511f18ddf5451feaf0d308af1b4a652
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191730"
---
# <a name="connection-events"></a><span data-ttu-id="50d2c-102">Verbindungsereignisse</span><span class="sxs-lookup"><span data-stu-id="50d2c-102">Connection Events</span></span>
<span data-ttu-id="50d2c-103">Alle von .NET Framework-Datenanbietern **Verbindung** Objekte mit zwei Ereignisse, die Sie verwenden können, um informationsmeldungen aus einer Datenquelle abzurufen oder zu bestimmen, ob der Status der eine **Verbindung** hat geändert.</span><span class="sxs-lookup"><span data-stu-id="50d2c-103">All of the .NET Framework data providers have **Connection** objects with two events that you can use to retrieve informational messages from a data source or to determine if the state of a **Connection** has changed.</span></span> <span data-ttu-id="50d2c-104">Die folgende Tabelle beschreibt die Ereignisse der **Verbindung** Objekt.</span><span class="sxs-lookup"><span data-stu-id="50d2c-104">The following table describes the events of the **Connection** object.</span></span>  
  
|<span data-ttu-id="50d2c-105">event</span><span class="sxs-lookup"><span data-stu-id="50d2c-105">Event</span></span>|<span data-ttu-id="50d2c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50d2c-106">Description</span></span>|  
|-----------|-----------------|  
|**<span data-ttu-id="50d2c-107">InfoMessage</span><span class="sxs-lookup"><span data-stu-id="50d2c-107">InfoMessage</span></span>**|<span data-ttu-id="50d2c-108">Dieses Ereignis tritt auf, wenn eine Informationsmeldung aus einer Datenquelle zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="50d2c-108">Occurs when an informational message is returned from a data source.</span></span> <span data-ttu-id="50d2c-109">Bei Informationsmeldungen handelt es sich um Meldungen aus einer Datenquelle, die keine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="50d2c-109">Informational messages are messages from a data source that do not result in an exception being thrown.</span></span>|  
|**<span data-ttu-id="50d2c-110">StateChange</span><span class="sxs-lookup"><span data-stu-id="50d2c-110">StateChange</span></span>**|<span data-ttu-id="50d2c-111">Tritt auf, wenn der Status der der **Verbindung** Änderungen.</span><span class="sxs-lookup"><span data-stu-id="50d2c-111">Occurs when the state of the **Connection** changes.</span></span>|  
  
## <a name="working-with-the-infomessage-event"></a><span data-ttu-id="50d2c-112">Arbeiten mit dem "InfoMessage"-Ereignis</span><span class="sxs-lookup"><span data-stu-id="50d2c-112">Working with the InfoMessage Event</span></span>  
 <span data-ttu-id="50d2c-113">Mit dem <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis des <xref:System.Data.SqlClient.SqlConnection>-Objekts können Warnungen und Informationsmeldungen aus einer SQL Server-Datenquelle abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="50d2c-113">You can retrieve warnings and informational messages from a SQL Server data source using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="50d2c-114">Wenn von einer Datenquelle Fehler mit einem Schweregrad zwischen 11 und 16 zurückgegeben werden, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="50d2c-114">Errors returned from the data source with a severity level of 11 through 16 cause an exception to be thrown.</span></span> <span data-ttu-id="50d2c-115">Mit dem <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis können jedoch Meldungen aus der Datenquelle abgerufen werden, die keinem Fehler zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="50d2c-115">However, the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event can be used to obtain messages from the data source that are not associated with an error.</span></span> <span data-ttu-id="50d2c-116">Bei Microsoft SQL Server werden alle Meldungen mit einem Schweregrad von 10 oder weniger als Informationsmeldungen betrachtet und mit dem <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="50d2c-116">In the case of Microsoft SQL Server, any error with a severity of 10 or less is considered to be an informational message, and can be captured by using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span> <span data-ttu-id="50d2c-117">Weitere Informationen finden Sie unter den [Schweregrade von Datenbank-Engine-Fehler](/sql/relational-databases/errors-events/database-engine-error-severities) Artikel.</span><span class="sxs-lookup"><span data-stu-id="50d2c-117">For more information, see the [Database Engine Error Severities](/sql/relational-databases/errors-events/database-engine-error-severities) article.</span></span>
  
 <span data-ttu-id="50d2c-118">Die <xref:System.Data.SqlClient.SqlConnection.InfoMessage> -Ereignis empfängt ein <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> Objekt enthält, in dessen **Fehler** -Eigenschaft, die eine Auflistung von Nachrichten aus der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="50d2c-118">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event receives an <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> object containing, in its **Errors** property, a collection of the messages from the data source.</span></span> <span data-ttu-id="50d2c-119">Sie können Abfragen, die **Fehler** Objekte in dieser Auflistung für den Fehlertext und dem Meldungstext sowie die Ursache des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="50d2c-119">You can query the **Error** objects in this collection for the error number and message text, as well as the source of the error.</span></span> <span data-ttu-id="50d2c-120">Der .NET Framework-Datenanbieter für SQL Server zeigt außerdem Details zu der Datenbank, der gespeicherten Prozedur und der Zeilennummer an, aus der die Meldung stammt.</span><span class="sxs-lookup"><span data-stu-id="50d2c-120">The .NET Framework Data Provider for SQL Server also includes detail about the database, stored procedure, and line number that the message came from.</span></span>  
  
### <a name="example"></a><span data-ttu-id="50d2c-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="50d2c-121">Example</span></span>  
 <span data-ttu-id="50d2c-122">Im folgenden Codebeispiel wird veranschaulicht, wie für das <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis ein Ereignishandler hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="50d2c-122">The following code example shows how to add an event handler for the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
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
  
## <a name="handling-errors-as-infomessages"></a><span data-ttu-id="50d2c-123">Behandeln von Fehlern als "InfoMessages"</span><span class="sxs-lookup"><span data-stu-id="50d2c-123">Handling Errors as InfoMessages</span></span>  
 <span data-ttu-id="50d2c-124">Das <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis wird i. d. R. nur für Informations- und Warnmeldungen ausgelöst, die vom Server gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="50d2c-124">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event will normally fire only for informational and warning messages that are sent from the server.</span></span> <span data-ttu-id="50d2c-125">Jedoch, wenn ein tatsächlicher Fehler auftritt, die Ausführung der **ExecuteNonQuery** oder **"ExecuteReader"** -Methode, die den Servervorgang initialisiert hat, angehalten, und eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="50d2c-125">However, when an actual error occurs, the execution of the **ExecuteNonQuery** or **ExecuteReader** method that initiated the server operation is halted and an exception is thrown.</span></span>  
  
 <span data-ttu-id="50d2c-126">Wenn Sie die Verarbeitung der restlichen Anweisungen in einem Befehl unabhängig von den vom Server erzeugten Fehlern fortsetzen möchten, legen sie die <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A>-Eigenschaft der <xref:System.Data.SqlClient.SqlConnection> auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="50d2c-126">If you want to continue processing the rest of the statements in a command regardless of any errors produced by the server, set the <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> property of the <xref:System.Data.SqlClient.SqlConnection> to `true`.</span></span> <span data-ttu-id="50d2c-127">Bei dieser Vorgehensweise wird bei Fehlern von der Verbindung das <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis ausgelöst, anstatt eine Ausnahme auszulösen und die Verarbeitung zu unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="50d2c-127">Doing this causes the connection to fire the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event for errors instead of throwing an exception and interrupting processing.</span></span> <span data-ttu-id="50d2c-128">Die Clientanwendung kann dann dieses Ereignis behandeln und auf Fehlerbedingungen reagieren.</span><span class="sxs-lookup"><span data-stu-id="50d2c-128">The client application can then handle this event and respond to error conditions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50d2c-129">Wenn aufgrund eines Fehlers mit einem Schweregrad von 17 oder höher der Server die Verarbeitung des Befehls abbricht, muss dieser Fehler als Ausnahme behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="50d2c-129">An error with a severity level of 17 or above that causes the server to stop processing the command must be handled as an exception.</span></span> <span data-ttu-id="50d2c-130">In diesem Fall wird unabhängig davon, wie der Fehler im <xref:System.Data.SqlClient.SqlConnection.InfoMessage>-Ereignis behandelt wird, eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="50d2c-130">In this case, an exception is thrown regardless of how the error is handled in the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
## <a name="working-with-the-statechange-event"></a><span data-ttu-id="50d2c-131">Arbeiten mit dem "StateChange"-Ereignis</span><span class="sxs-lookup"><span data-stu-id="50d2c-131">Working with the StateChange Event</span></span>  
 <span data-ttu-id="50d2c-132">Die **StateChange** Ereignis tritt auf, wenn der Status der eine **Verbindung** Änderungen.</span><span class="sxs-lookup"><span data-stu-id="50d2c-132">The **StateChange** event occurs when the state of a **Connection** changes.</span></span> <span data-ttu-id="50d2c-133">Die **StateChange** -Ereignis empfängt <xref:System.Data.StateChangeEventArgs> , mit denen Sie bestimmen, der die Änderung des von der **Verbindung** mithilfe der **OriginalState** und **CurrentState** Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="50d2c-133">The **StateChange** event receives <xref:System.Data.StateChangeEventArgs> that enable you to determine the change in state of the **Connection** by using the **OriginalState** and **CurrentState** properties.</span></span> <span data-ttu-id="50d2c-134">Die **OriginalState** -Eigenschaft ist eine <xref:System.Data.ConnectionState> -Enumeration, die den Status der gibt an die **Verbindung** vor der Änderung.</span><span class="sxs-lookup"><span data-stu-id="50d2c-134">The **OriginalState** property is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** before it changed.</span></span> <span data-ttu-id="50d2c-135">**CurrentState** ist eine <xref:System.Data.ConnectionState> -Enumeration, die den Status der gibt an die **Verbindung** nach der Änderung.</span><span class="sxs-lookup"><span data-stu-id="50d2c-135">**CurrentState** is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** after it changed.</span></span>  
  
 <span data-ttu-id="50d2c-136">Im folgenden Codebeispiel wird die **StateChange** Ereignis, um eine Nachricht an die Konsole schreiben bei den Status des der **Verbindung** Änderungen.</span><span class="sxs-lookup"><span data-stu-id="50d2c-136">The following code example uses the **StateChange** event to write a message to the console when the state of the **Connection** changes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="50d2c-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50d2c-137">See also</span></span>

- [<span data-ttu-id="50d2c-138">Aufbauen der Verbindung zu einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="50d2c-138">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)
- [<span data-ttu-id="50d2c-139">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="50d2c-139">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
