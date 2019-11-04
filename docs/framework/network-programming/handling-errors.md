---
title: Behandeln von Fehlern
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Internet, WebRequest and WebResponse classes exceptions
- Status property
- WebExceptions class, about WebExceptions class
- Timeout enumeration member
- ConnectFailure enumeration member
- TrustFailure enumeration member
- WebRequest class, exceptions
- requesting data from Internet, error handling
- Success enumeration member
- receiving data, errors
- ProtocolError enumeration member
- downloading Internet resources, error handling
- WebResponse class, exceptions
- SendFailure enumeration member
- errors [.NET Framework], WebRequest and WebResponse classes exceptions
- sending data, errors
- response to Internet request, error handling
- NameResolutionFailure enumeration member
- KeepAliveFailure enumeration member
- network resources, WebRequest and WebResponse classes exceptions
- RequestCanceled enumeration member
- ReceiveFailure enumeration member
- ServerProtocolViolation enumeration member
- ConnectionClosed enumeration member
- SecureChannelFailure enumeration member
ms.assetid: 657141cd-5cf5-4fdb-a4b2-4c040eba84b5
ms.openlocfilehash: 7084c4579dd5fca0075c7516754195f7cea9e27c
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458038"
---
# <a name="handling-errors"></a><span data-ttu-id="cd042-102">Behandeln von Fehlern</span><span class="sxs-lookup"><span data-stu-id="cd042-102">Handling Errors</span></span>

<span data-ttu-id="cd042-103">Die Klassen <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> lösen beide Systemausnahmen (z.B. <xref:System.ArgumentException>) und webspezifische Ausnahmen (bei denen es sich um <xref:System.Net.WebException> handelt, ausgelöst von der <xref:System.Net.WebRequest.GetResponse%2A>-Methode) aus.</span><span class="sxs-lookup"><span data-stu-id="cd042-103">The <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes throw both system exceptions (such as <xref:System.ArgumentException>) and Web-specific exceptions (which are <xref:System.Net.WebException> thrown by the <xref:System.Net.WebRequest.GetResponse%2A> method).</span></span>  
  
<span data-ttu-id="cd042-104">Jede **WebException** enthält eine <xref:System.Net.WebException.Status%2A>-Eigenschaft, die einen Wert aus der <xref:System.Net.WebExceptionStatus>-Enumeration enthält.</span><span class="sxs-lookup"><span data-stu-id="cd042-104">Each **WebException** includes a <xref:System.Net.WebException.Status%2A> property that contains a value from the <xref:System.Net.WebExceptionStatus> enumeration.</span></span> <span data-ttu-id="cd042-105">Sie können die **Status**-Eigenschaft untersuchen, um den aufgetretenen Fehler zu bestimmen und dann die richtigen Schritte vornehmen, um den Fehler zu beheben.</span><span class="sxs-lookup"><span data-stu-id="cd042-105">You can examine the **Status** property to determine the error that occurred and take the proper steps to resolve the error.</span></span>  
  
<span data-ttu-id="cd042-106">In der folgenden Tabelle werden die möglichen Rückgabewerte für die **Status**-Eigenschaft beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cd042-106">The following table describes the possible values for the **Status** property.</span></span>  
  
|<span data-ttu-id="cd042-107">Status</span><span class="sxs-lookup"><span data-stu-id="cd042-107">Status</span></span>|<span data-ttu-id="cd042-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cd042-108">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="cd042-109">ConnectFailure</span><span class="sxs-lookup"><span data-stu-id="cd042-109">ConnectFailure</span></span>|<span data-ttu-id="cd042-110">Der Remotedienst konnte auf Transportebene nicht erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="cd042-110">The remote service could not be contacted at the transport level.</span></span>|  
|<span data-ttu-id="cd042-111">ConnectionClosed</span><span class="sxs-lookup"><span data-stu-id="cd042-111">ConnectionClosed</span></span>|<span data-ttu-id="cd042-112">Die Verbindung wurde vorzeitig getrennt.</span><span class="sxs-lookup"><span data-stu-id="cd042-112">The connection was closed prematurely.</span></span>|  
|<span data-ttu-id="cd042-113">KeepAliveFailure</span><span class="sxs-lookup"><span data-stu-id="cd042-113">KeepAliveFailure</span></span>|<span data-ttu-id="cd042-114">Der Server hat die Verbindung mit dem festgelegten Keep-Alive-Header.</span><span class="sxs-lookup"><span data-stu-id="cd042-114">The server closed a connection made with the Keep-alive header set.</span></span>|  
|<span data-ttu-id="cd042-115">NameResolutionFailure</span><span class="sxs-lookup"><span data-stu-id="cd042-115">NameResolutionFailure</span></span>|<span data-ttu-id="cd042-116">Die Namensdienst konnte den Hostnamen nicht auflösen.</span><span class="sxs-lookup"><span data-stu-id="cd042-116">The name service could not resolve the host name.</span></span>|  
|<span data-ttu-id="cd042-117">ProtocolError</span><span class="sxs-lookup"><span data-stu-id="cd042-117">ProtocolError</span></span>|<span data-ttu-id="cd042-118">Die Antwort, die vom Server empfangen wurde, war vollständig, aber hat einen Fehler auf Protokollebene angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd042-118">The response received from the server was complete but indicated an error at the protocol level.</span></span>|  
|<span data-ttu-id="cd042-119">ReceiveFailure</span><span class="sxs-lookup"><span data-stu-id="cd042-119">ReceiveFailure</span></span>|<span data-ttu-id="cd042-120">Es wurde keine vollständige Nachricht vom Remoteserver empfangen.</span><span class="sxs-lookup"><span data-stu-id="cd042-120">A complete response was not received from the remote server.</span></span>|  
|<span data-ttu-id="cd042-121">RequestCanceled</span><span class="sxs-lookup"><span data-stu-id="cd042-121">RequestCanceled</span></span>|<span data-ttu-id="cd042-122">Die Anforderung wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="cd042-122">The request was canceled.</span></span>|  
|<span data-ttu-id="cd042-123">SecureChannelFailure</span><span class="sxs-lookup"><span data-stu-id="cd042-123">SecureChannelFailure</span></span>|<span data-ttu-id="cd042-124">In einem sicheren Channel-Link ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="cd042-124">An error occurred in a secure channel link.</span></span>|  
|<span data-ttu-id="cd042-125">SendFailure</span><span class="sxs-lookup"><span data-stu-id="cd042-125">SendFailure</span></span>|<span data-ttu-id="cd042-126">Es konnte keine vollständige Anforderung an den Remoteserver gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="cd042-126">A complete request could not be sent to the remote server.</span></span>|  
|<span data-ttu-id="cd042-127">ServerProtocolViolation</span><span class="sxs-lookup"><span data-stu-id="cd042-127">ServerProtocolViolation</span></span>|<span data-ttu-id="cd042-128">Die Serverantwort ist eine ungültige HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="cd042-128">The server response was not a valid HTTP response.</span></span>|  
|<span data-ttu-id="cd042-129">Erfolgreich</span><span class="sxs-lookup"><span data-stu-id="cd042-129">Success</span></span>|<span data-ttu-id="cd042-130">Es ist kein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="cd042-130">No error was encountered.</span></span>|  
|<span data-ttu-id="cd042-131">Timeout</span><span class="sxs-lookup"><span data-stu-id="cd042-131">Timeout</span></span>|<span data-ttu-id="cd042-132">Innerhalb des festgelegten Timeouts wurde keine Antwort für die Anforderung erhalten.</span><span class="sxs-lookup"><span data-stu-id="cd042-132">No response was received within the time-out set for the request.</span></span>|  
|<span data-ttu-id="cd042-133">TrustFailure</span><span class="sxs-lookup"><span data-stu-id="cd042-133">TrustFailure</span></span>|<span data-ttu-id="cd042-134">Ein Serverzertifikat konnte nicht überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="cd042-134">A server certificate could not be validated.</span></span>|  
|<span data-ttu-id="cd042-135">MessageLengthLimitExceeded</span><span class="sxs-lookup"><span data-stu-id="cd042-135">MessageLengthLimitExceeded</span></span>|<span data-ttu-id="cd042-136">Es wurde eine Nachricht erhalten, die den angegebenen Grenzwert für das Senden einer Anforderung oder das Erhalten einer Antwort vom Server überschritten hat.</span><span class="sxs-lookup"><span data-stu-id="cd042-136">A message was received that exceeded the specified limit when sending a request or receiving a response from the server.</span></span>|  
|<span data-ttu-id="cd042-137">Ausstehend</span><span class="sxs-lookup"><span data-stu-id="cd042-137">Pending</span></span>|<span data-ttu-id="cd042-138">Eine interne asynchrone Anforderung steht aus.</span><span class="sxs-lookup"><span data-stu-id="cd042-138">An internal asynchronous request is pending.</span></span>|  
|<span data-ttu-id="cd042-139">PipelineFailure</span><span class="sxs-lookup"><span data-stu-id="cd042-139">PipelineFailure</span></span>|<span data-ttu-id="cd042-140">Dieser Wert unterstützt die .NET Framework-Infrastruktur und ist nicht für die direkte Verwendung in Ihrem Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="cd042-140">This value supports the .NET Framework infrastructure and is not intended to be used directly in your code.</span></span>|  
|<span data-ttu-id="cd042-141">ProxyNameResolutionFailure</span><span class="sxs-lookup"><span data-stu-id="cd042-141">ProxyNameResolutionFailure</span></span>|<span data-ttu-id="cd042-142">Der Namensresolverdienst konnte den Hostnamen des Proxys nicht auflösen.</span><span class="sxs-lookup"><span data-stu-id="cd042-142">The name resolver service could not resolve the proxy host name.</span></span>|  
|<span data-ttu-id="cd042-143">UnknownError</span><span class="sxs-lookup"><span data-stu-id="cd042-143">UnknownError</span></span>|<span data-ttu-id="cd042-144">Eine Ausnahme unbekannten Typs wurde ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="cd042-144">An exception of unknown type has occurred.</span></span>|  
  
<span data-ttu-id="cd042-145">Wenn es sich bei der **Status**-Eigenschaft um **WebExceptionStatus.ProtocolError** handelt, ist eine **WebResponse** verfügbar, die die Antwort des Servers enthält.</span><span class="sxs-lookup"><span data-stu-id="cd042-145">When the **Status** property is **WebExceptionStatus.ProtocolError**, a **WebResponse** that contains the response from the server is available.</span></span> <span data-ttu-id="cd042-146">Sie können diese Antwort untersuchen, um die tatsächliche Quelle des Protokollfehlers zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="cd042-146">You can examine this response to determine the actual source of the protocol error.</span></span>  
  
<span data-ttu-id="cd042-147">Das folgende Beispiel demonstriert das Abfangen einer **WebException**.</span><span class="sxs-lookup"><span data-stu-id="cd042-147">The following example shows how to catch a **WebException**.</span></span>  
  
```csharp  
try   
{  
    // Create a request instance.  
    WebRequest myRequest =   
    WebRequest.Create("http://www.contoso.com");  
    // Get the response.  
    WebResponse myResponse = myRequest.GetResponse();  
    //Get a readable stream from the server.   
    Stream sr = myResponse.GetResponseStream();  
  
    //Read from the stream and write any data to the console.  
    bytesread = sr.Read( myBuffer, 0, length);  
    while( bytesread > 0 )   
    {  
        for (int i=0; i<bytesread; i++) {  
            Console.Write( "{0}", myBuffer[i]);  
        }  
        Console.WriteLine();  
        bytesread = sr.Read( myBuffer, 0, length);  
    }  
    sr.Close();  
    myResponse.Close();  
}  
catch (WebException webExcp)   
{  
    // If you reach this point, an exception has been caught.  
    Console.WriteLine("A WebException has been caught.");  
    // Write out the WebException message.  
    Console.WriteLine(webExcp.ToString());  
    // Get the WebException status code.  
    WebExceptionStatus status =  webExcp.Status;  
    // If status is WebExceptionStatus.ProtocolError,   
    //   there has been a protocol error and a WebResponse   
    //   should exist. Display the protocol error.  
    if (status == WebExceptionStatus.ProtocolError) {  
        Console.Write("The server returned protocol error ");  
        // Get HttpWebResponse so that you can check the HTTP status code.  
        HttpWebResponse httpResponse = (HttpWebResponse)webExcp.Response;  
        Console.WriteLine((int)httpResponse.StatusCode + " - "  
           + httpResponse.StatusCode);  
    }  
}  
catch (Exception e)   
{  
    // Code to catch other exceptions goes here.  
}  
```  
  
```vb  
Try  
    ' Create a request instance.  
    Dim myRequest As WebRequest = WebRequest.Create("http://www.contoso.com")  
    ' Get the response.  
    Dim myResponse As WebResponse = myRequest.GetResponse()  
    'Get a readable stream from the server.   
    Dim sr As Stream = myResponse.GetResponseStream()  
  
    Dim i As Integer      
    'Read from the stream and write any data to the console.  
    bytesread = sr.Read(myBuffer, 0, length)  
    While bytesread > 0  
        For i = 0 To bytesread - 1  
            Console.Write("{0}", myBuffer(i))  
        Next i  
        Console.WriteLine()  
        bytesread = sr.Read(myBuffer, 0, length)  
    End While  
    sr.Close()  
    myResponse.Close()  
Catch webExcp As WebException  
    ' If you reach this point, an exception has been caught.  
    Console.WriteLine("A WebException has been caught.")  
    ' Write out the WebException message.  
    Console.WriteLine(webExcp.ToString())  
    ' Get the WebException status code.  
    Dim status As WebExceptionStatus = webExcp.Status  
    ' If status is WebExceptionStatus.ProtocolError,   
    '   there has been a protocol error and a WebResponse   
    '   should exist. Display the protocol error.  
    If status = WebExceptionStatus.ProtocolError Then  
        Console.Write("The server returned protocol error ")  
        ' Get HttpWebResponse so that you can check the HTTP status code.  
        Dim httpResponse As HttpWebResponse = _  
           CType(webExcp.Response, HttpWebResponse)  
        Console.WriteLine(CInt(httpResponse.StatusCode).ToString() & _  
           " - " & httpResponse.StatusCode.ToString())  
    End If  
Catch e As Exception  
    ' Code to catch other exceptions goes here.  
End Try  
```  
  
<span data-ttu-id="cd042-148">Anwendungen, die die Klasse <xref:System.Net.Sockets.Socket> verwenden, lösen <xref:System.Net.Sockets.SocketException> aus, wenn ein Fehler auf dem Windows Socket auftritt.</span><span class="sxs-lookup"><span data-stu-id="cd042-148">Applications that use the <xref:System.Net.Sockets.Socket> class throw <xref:System.Net.Sockets.SocketException> when errors occur on the Windows socket.</span></span> <span data-ttu-id="cd042-149">Die Klassen <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> und <xref:System.Net.Sockets.UdpClient> werden basierend auf der **Socket**-Klasse erstellt und lösen ebenfalls **SocketExceptions** aus.</span><span class="sxs-lookup"><span data-stu-id="cd042-149">The <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener>, and <xref:System.Net.Sockets.UdpClient> classes are built on top of the **Socket** class and throw **SocketExceptions** as well.</span></span>  
  
<span data-ttu-id="cd042-150">Wenn eine **SocketException** ausgelöst wird, legt die **SocketException**-Klasse die <xref:System.Net.Sockets.SocketException.ErrorCode%2A>-Eigenschaft auf den zuletzt aufgetretenen Betriebssystemsocketfehler fest.</span><span class="sxs-lookup"><span data-stu-id="cd042-150">When a **SocketException** is thrown, the **SocketException** class sets the <xref:System.Net.Sockets.SocketException.ErrorCode%2A> property to the last operating system socket error that occurred.</span></span> <span data-ttu-id="cd042-151">Weitere Informationen zu Socketfehlercodes finden Sie in der Fehlercodedokumentation von Winsock 2.0 API in MSDN.</span><span class="sxs-lookup"><span data-stu-id="cd042-151">For more information about socket error codes, see the Winsock 2.0 API error code documentation in MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd042-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd042-152">See also</span></span>

- [<span data-ttu-id="cd042-153">Behandeln und Auslösen von Ausnahmen in .NET</span><span class="sxs-lookup"><span data-stu-id="cd042-153">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="cd042-154">Requesting Data (Anfordern von Daten)</span><span class="sxs-lookup"><span data-stu-id="cd042-154">Requesting Data</span></span>](requesting-data.md)
