---
title: Behandeln von Fehlern
description: Hier erfahren Sie mehr über die system- und webspezifischen Ausnahmen, die von WebRequest und WebResponse ausgelöst werden. Verwenden Sie die Status-Eigenschaft, um das Problem zu verstehen und zu beheben.
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
ms.openlocfilehash: 786b2bd8bc4d1b394bcfe920053b2f4f55d1cdea
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502573"
---
# <a name="handling-errors"></a><span data-ttu-id="a8edd-104">Behandeln von Fehlern</span><span class="sxs-lookup"><span data-stu-id="a8edd-104">Handling Errors</span></span>

<span data-ttu-id="a8edd-105">Die Klassen <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> lösen beide Systemausnahmen (z.B. <xref:System.ArgumentException>) und webspezifische Ausnahmen (bei denen es sich um <xref:System.Net.WebException> handelt, ausgelöst von der <xref:System.Net.WebRequest.GetResponse%2A>-Methode) aus.</span><span class="sxs-lookup"><span data-stu-id="a8edd-105">The <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes throw both system exceptions (such as <xref:System.ArgumentException>) and Web-specific exceptions (which are <xref:System.Net.WebException> thrown by the <xref:System.Net.WebRequest.GetResponse%2A> method).</span></span>  
  
<span data-ttu-id="a8edd-106">Jede **WebException** enthält eine <xref:System.Net.WebException.Status%2A>-Eigenschaft, die einen Wert aus der <xref:System.Net.WebExceptionStatus>-Enumeration enthält.</span><span class="sxs-lookup"><span data-stu-id="a8edd-106">Each **WebException** includes a <xref:System.Net.WebException.Status%2A> property that contains a value from the <xref:System.Net.WebExceptionStatus> enumeration.</span></span> <span data-ttu-id="a8edd-107">Sie können die **Status**-Eigenschaft untersuchen, um den aufgetretenen Fehler zu bestimmen und dann die richtigen Schritte vornehmen, um den Fehler zu beheben.</span><span class="sxs-lookup"><span data-stu-id="a8edd-107">You can examine the **Status** property to determine the error that occurred and take the proper steps to resolve the error.</span></span>  
  
<span data-ttu-id="a8edd-108">In der folgenden Tabelle werden die möglichen Rückgabewerte für die **Status**-Eigenschaft beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a8edd-108">The following table describes the possible values for the **Status** property.</span></span>  
  
|<span data-ttu-id="a8edd-109">Status</span><span class="sxs-lookup"><span data-stu-id="a8edd-109">Status</span></span>|<span data-ttu-id="a8edd-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8edd-110">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a8edd-111">ConnectFailure</span><span class="sxs-lookup"><span data-stu-id="a8edd-111">ConnectFailure</span></span>|<span data-ttu-id="a8edd-112">Der Remotedienst konnte auf Transportebene nicht erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="a8edd-112">The remote service could not be contacted at the transport level.</span></span>|  
|<span data-ttu-id="a8edd-113">ConnectionClosed</span><span class="sxs-lookup"><span data-stu-id="a8edd-113">ConnectionClosed</span></span>|<span data-ttu-id="a8edd-114">Die Verbindung wurde vorzeitig getrennt.</span><span class="sxs-lookup"><span data-stu-id="a8edd-114">The connection was closed prematurely.</span></span>|  
|<span data-ttu-id="a8edd-115">KeepAliveFailure</span><span class="sxs-lookup"><span data-stu-id="a8edd-115">KeepAliveFailure</span></span>|<span data-ttu-id="a8edd-116">Der Server hat die Verbindung mit dem festgelegten Keep-Alive-Header.</span><span class="sxs-lookup"><span data-stu-id="a8edd-116">The server closed a connection made with the Keep-alive header set.</span></span>|  
|<span data-ttu-id="a8edd-117">NameResolutionFailure</span><span class="sxs-lookup"><span data-stu-id="a8edd-117">NameResolutionFailure</span></span>|<span data-ttu-id="a8edd-118">Die Namensdienst konnte den Hostnamen nicht auflösen.</span><span class="sxs-lookup"><span data-stu-id="a8edd-118">The name service could not resolve the host name.</span></span>|  
|<span data-ttu-id="a8edd-119">ProtocolError</span><span class="sxs-lookup"><span data-stu-id="a8edd-119">ProtocolError</span></span>|<span data-ttu-id="a8edd-120">Die Antwort, die vom Server empfangen wurde, war vollständig, aber hat einen Fehler auf Protokollebene angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a8edd-120">The response received from the server was complete but indicated an error at the protocol level.</span></span>|  
|<span data-ttu-id="a8edd-121">ReceiveFailure</span><span class="sxs-lookup"><span data-stu-id="a8edd-121">ReceiveFailure</span></span>|<span data-ttu-id="a8edd-122">Es wurde keine vollständige Nachricht vom Remoteserver empfangen.</span><span class="sxs-lookup"><span data-stu-id="a8edd-122">A complete response was not received from the remote server.</span></span>|  
|<span data-ttu-id="a8edd-123">RequestCanceled</span><span class="sxs-lookup"><span data-stu-id="a8edd-123">RequestCanceled</span></span>|<span data-ttu-id="a8edd-124">Die Anforderung wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="a8edd-124">The request was canceled.</span></span>|  
|<span data-ttu-id="a8edd-125">SecureChannelFailure</span><span class="sxs-lookup"><span data-stu-id="a8edd-125">SecureChannelFailure</span></span>|<span data-ttu-id="a8edd-126">In einem sicheren Channel-Link ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a8edd-126">An error occurred in a secure channel link.</span></span>|  
|<span data-ttu-id="a8edd-127">SendFailure</span><span class="sxs-lookup"><span data-stu-id="a8edd-127">SendFailure</span></span>|<span data-ttu-id="a8edd-128">Es konnte keine vollständige Anforderung an den Remoteserver gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="a8edd-128">A complete request could not be sent to the remote server.</span></span>|  
|<span data-ttu-id="a8edd-129">ServerProtocolViolation</span><span class="sxs-lookup"><span data-stu-id="a8edd-129">ServerProtocolViolation</span></span>|<span data-ttu-id="a8edd-130">Die Serverantwort ist eine ungültige HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="a8edd-130">The server response was not a valid HTTP response.</span></span>|  
|<span data-ttu-id="a8edd-131">Erfolgreich</span><span class="sxs-lookup"><span data-stu-id="a8edd-131">Success</span></span>|<span data-ttu-id="a8edd-132">Es ist kein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a8edd-132">No error was encountered.</span></span>|  
|<span data-ttu-id="a8edd-133">Timeout</span><span class="sxs-lookup"><span data-stu-id="a8edd-133">Timeout</span></span>|<span data-ttu-id="a8edd-134">Innerhalb des festgelegten Timeouts wurde keine Antwort für die Anforderung erhalten.</span><span class="sxs-lookup"><span data-stu-id="a8edd-134">No response was received within the time-out set for the request.</span></span>|  
|<span data-ttu-id="a8edd-135">TrustFailure</span><span class="sxs-lookup"><span data-stu-id="a8edd-135">TrustFailure</span></span>|<span data-ttu-id="a8edd-136">Ein Serverzertifikat konnte nicht überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="a8edd-136">A server certificate could not be validated.</span></span>|  
|<span data-ttu-id="a8edd-137">MessageLengthLimitExceeded</span><span class="sxs-lookup"><span data-stu-id="a8edd-137">MessageLengthLimitExceeded</span></span>|<span data-ttu-id="a8edd-138">Es wurde eine Nachricht erhalten, die den angegebenen Grenzwert für das Senden einer Anforderung oder das Erhalten einer Antwort vom Server überschritten hat.</span><span class="sxs-lookup"><span data-stu-id="a8edd-138">A message was received that exceeded the specified limit when sending a request or receiving a response from the server.</span></span>|  
|<span data-ttu-id="a8edd-139">Ausstehend</span><span class="sxs-lookup"><span data-stu-id="a8edd-139">Pending</span></span>|<span data-ttu-id="a8edd-140">Eine interne asynchrone Anforderung steht aus.</span><span class="sxs-lookup"><span data-stu-id="a8edd-140">An internal asynchronous request is pending.</span></span>|  
|<span data-ttu-id="a8edd-141">PipelineFailure</span><span class="sxs-lookup"><span data-stu-id="a8edd-141">PipelineFailure</span></span>|<span data-ttu-id="a8edd-142">Dieser Wert unterstützt die .NET Framework-Infrastruktur und ist nicht für die direkte Verwendung in Ihrem Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="a8edd-142">This value supports the .NET Framework infrastructure and is not intended to be used directly in your code.</span></span>|  
|<span data-ttu-id="a8edd-143">ProxyNameResolutionFailure</span><span class="sxs-lookup"><span data-stu-id="a8edd-143">ProxyNameResolutionFailure</span></span>|<span data-ttu-id="a8edd-144">Der Namensresolverdienst konnte den Hostnamen des Proxys nicht auflösen.</span><span class="sxs-lookup"><span data-stu-id="a8edd-144">The name resolver service could not resolve the proxy host name.</span></span>|  
|<span data-ttu-id="a8edd-145">UnknownError</span><span class="sxs-lookup"><span data-stu-id="a8edd-145">UnknownError</span></span>|<span data-ttu-id="a8edd-146">Eine Ausnahme unbekannten Typs wurde ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a8edd-146">An exception of unknown type has occurred.</span></span>|  
  
<span data-ttu-id="a8edd-147">Wenn es sich bei der **Status**-Eigenschaft um **WebExceptionStatus.ProtocolError** handelt, ist eine **WebResponse** verfügbar, die die Antwort des Servers enthält.</span><span class="sxs-lookup"><span data-stu-id="a8edd-147">When the **Status** property is **WebExceptionStatus.ProtocolError**, a **WebResponse** that contains the response from the server is available.</span></span> <span data-ttu-id="a8edd-148">Sie können diese Antwort untersuchen, um die tatsächliche Quelle des Protokollfehlers zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="a8edd-148">You can examine this response to determine the actual source of the protocol error.</span></span>  
  
<span data-ttu-id="a8edd-149">Das folgende Beispiel demonstriert das Abfangen einer **WebException**.</span><span class="sxs-lookup"><span data-stu-id="a8edd-149">The following example shows how to catch a **WebException**.</span></span>  
  
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
  
<span data-ttu-id="a8edd-150">Anwendungen, die die Klasse <xref:System.Net.Sockets.Socket> verwenden, lösen <xref:System.Net.Sockets.SocketException> aus, wenn ein Fehler auf dem Windows Socket auftritt.</span><span class="sxs-lookup"><span data-stu-id="a8edd-150">Applications that use the <xref:System.Net.Sockets.Socket> class throw <xref:System.Net.Sockets.SocketException> when errors occur on the Windows socket.</span></span> <span data-ttu-id="a8edd-151">Die Klassen <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> und <xref:System.Net.Sockets.UdpClient> werden basierend auf der **Socket**-Klasse erstellt und lösen ebenfalls **SocketExceptions** aus.</span><span class="sxs-lookup"><span data-stu-id="a8edd-151">The <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener>, and <xref:System.Net.Sockets.UdpClient> classes are built on top of the **Socket** class and throw **SocketExceptions** as well.</span></span>  
  
<span data-ttu-id="a8edd-152">Wenn eine **SocketException** ausgelöst wird, legt die **SocketException**-Klasse die <xref:System.Net.Sockets.SocketException.ErrorCode%2A>-Eigenschaft auf den zuletzt aufgetretenen Betriebssystemsocketfehler fest.</span><span class="sxs-lookup"><span data-stu-id="a8edd-152">When a **SocketException** is thrown, the **SocketException** class sets the <xref:System.Net.Sockets.SocketException.ErrorCode%2A> property to the last operating system socket error that occurred.</span></span> <span data-ttu-id="a8edd-153">Weitere Informationen zu Socketfehlercodes finden Sie in der Fehlercodedokumentation von Winsock 2.0 API in MSDN.</span><span class="sxs-lookup"><span data-stu-id="a8edd-153">For more information about socket error codes, see the Winsock 2.0 API error code documentation in MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8edd-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8edd-154">See also</span></span>

- [<span data-ttu-id="a8edd-155">Behandeln und Auslösen von Ausnahmen in .NET</span><span class="sxs-lookup"><span data-stu-id="a8edd-155">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="a8edd-156">Requesting Data (Anfordern von Daten)</span><span class="sxs-lookup"><span data-stu-id="a8edd-156">Requesting Data</span></span>](requesting-data.md)
