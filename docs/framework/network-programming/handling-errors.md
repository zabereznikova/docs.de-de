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
# <a name="handling-errors"></a>Behandeln von Fehlern

Die Klassen <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> lösen beide Systemausnahmen (z.B. <xref:System.ArgumentException>) und webspezifische Ausnahmen (bei denen es sich um <xref:System.Net.WebException> handelt, ausgelöst von der <xref:System.Net.WebRequest.GetResponse%2A>-Methode) aus.  
  
Jede **WebException** enthält eine <xref:System.Net.WebException.Status%2A>-Eigenschaft, die einen Wert aus der <xref:System.Net.WebExceptionStatus>-Enumeration enthält. Sie können die **Status**-Eigenschaft untersuchen, um den aufgetretenen Fehler zu bestimmen und dann die richtigen Schritte vornehmen, um den Fehler zu beheben.  
  
In der folgenden Tabelle werden die möglichen Rückgabewerte für die **Status**-Eigenschaft beschrieben.  
  
|Status|BESCHREIBUNG|  
|------------|-----------------|  
|ConnectFailure|Der Remotedienst konnte auf Transportebene nicht erreicht werden.|  
|ConnectionClosed|Die Verbindung wurde vorzeitig getrennt.|  
|KeepAliveFailure|Der Server hat die Verbindung mit dem festgelegten Keep-Alive-Header.|  
|NameResolutionFailure|Die Namensdienst konnte den Hostnamen nicht auflösen.|  
|ProtocolError|Die Antwort, die vom Server empfangen wurde, war vollständig, aber hat einen Fehler auf Protokollebene angezeigt.|  
|ReceiveFailure|Es wurde keine vollständige Nachricht vom Remoteserver empfangen.|  
|RequestCanceled|Die Anforderung wurde abgebrochen.|  
|SecureChannelFailure|In einem sicheren Channel-Link ist ein Fehler aufgetreten.|  
|SendFailure|Es konnte keine vollständige Anforderung an den Remoteserver gesendet werden.|  
|ServerProtocolViolation|Die Serverantwort ist eine ungültige HTTP-Antwort.|  
|Erfolgreich|Es ist kein Fehler aufgetreten.|  
|Timeout|Innerhalb des festgelegten Timeouts wurde keine Antwort für die Anforderung erhalten.|  
|TrustFailure|Ein Serverzertifikat konnte nicht überprüft werden.|  
|MessageLengthLimitExceeded|Es wurde eine Nachricht erhalten, die den angegebenen Grenzwert für das Senden einer Anforderung oder das Erhalten einer Antwort vom Server überschritten hat.|  
|Ausstehend|Eine interne asynchrone Anforderung steht aus.|  
|PipelineFailure|Dieser Wert unterstützt die .NET Framework-Infrastruktur und ist nicht für die direkte Verwendung in Ihrem Code vorgesehen.|  
|ProxyNameResolutionFailure|Der Namensresolverdienst konnte den Hostnamen des Proxys nicht auflösen.|  
|UnknownError|Eine Ausnahme unbekannten Typs wurde ausgelöst.|  
  
Wenn es sich bei der **Status**-Eigenschaft um **WebExceptionStatus.ProtocolError** handelt, ist eine **WebResponse** verfügbar, die die Antwort des Servers enthält. Sie können diese Antwort untersuchen, um die tatsächliche Quelle des Protokollfehlers zu bestimmen.  
  
Das folgende Beispiel demonstriert das Abfangen einer **WebException**.  
  
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
  
Anwendungen, die die Klasse <xref:System.Net.Sockets.Socket> verwenden, lösen <xref:System.Net.Sockets.SocketException> aus, wenn ein Fehler auf dem Windows Socket auftritt. Die Klassen <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> und <xref:System.Net.Sockets.UdpClient> werden basierend auf der **Socket**-Klasse erstellt und lösen ebenfalls **SocketExceptions** aus.  
  
Wenn eine **SocketException** ausgelöst wird, legt die **SocketException**-Klasse die <xref:System.Net.Sockets.SocketException.ErrorCode%2A>-Eigenschaft auf den zuletzt aufgetretenen Betriebssystemsocketfehler fest. Weitere Informationen zu Socketfehlercodes finden Sie in der Fehlercodedokumentation von Winsock 2.0 API in MSDN.  
  
## <a name="see-also"></a>Siehe auch

- [Behandeln und Auslösen von Ausnahmen in .NET](../../standard/exceptions/index.md)
- [Requesting Data (Anfordern von Daten)](requesting-data.md)
