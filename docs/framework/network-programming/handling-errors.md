---
title: "Behandeln von Fehlern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Internet, Ausnahmen der WebRequest- und WebResponse-Klassen"
  - "Status-Eigenschaft"
  - "WebExceptions-Klasse, Informationen zur WebExceptions-Klasse"
  - "Timeout-Enumerationsmember"
  - "ConnectFailure-Enumerationsmember"
  - "TrustFailure-Enumerationsmember"
  - "WebRequest-Klasse, Ausnahmen"
  - "Anfordern von Daten aus dem Internet, Fehlerbehandlung"
  - "Success-Enumerationsmember"
  - "Empfangen von Daten, Fehler"
  - "ProtocolError-Enumerationsmember"
  - "Herunterladen von Internetressourcen, Fehlerbehandlung"
  - "WebResponse-Klasse, Ausnahmen"
  - "SendFailure-Enumerationsmember"
  - "Fehler [.NET Framework], Ausnahmen der WebRequest- und WebResponse-Klassen"
  - "Senden von Daten, Fehler"
  - "Antwort auf Internetanforderung, Fehlerbehandlung"
  - "NameResolutionFailure-Enumerationsmember"
  - "KeepAliveFailure-Enumerationsmember"
  - "Netzwerkressourcen, Ausnahmen der WebRequest- und WebResponse-Klassen"
  - "RequestCanceled-Enumerationsmember"
  - "ReceiveFailure-Enumerationsmember"
  - "ServerProtocolViolation-Enumerationsmember"
  - "ConnectionClosed-Enumerationsmember"
  - "SecureChannelFailure-Enumerationsmember"
ms.assetid: 657141cd-5cf5-4fdb-a4b2-4c040eba84b5
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Behandeln von Fehlern
Die <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse>\-Klassen lösen Systemausnahmen \(z <xref:System.ArgumentException>\) und Internet\-Besondere Ausnahmen aus \(die [WebExceptions](frlrfsystemnetwebexceptionclasstopic) sind, das von der <xref:System.Net.WebRequest.GetResponse%2A>\-Methode ausgelöst wird\).  
  
 Jedes **WebException** enthält eine <xref:System.Net.WebException.Status%2A>\-Eigenschaft ein, die einen Wert aus der <xref:System.Net.WebExceptionStatus>\-Enumeration enthält.  Sie können die **Status**\-Eigenschaft überprüfen, um den Fehler zu bestimmen, der aufgetreten ist und die richtigen Schritte ausführen, um den Fehler zu beheben.  
  
 Die folgende Tabelle beschreibt die möglichen Werte für die **Status**\-Eigenschaft.  
  
|Status|Description|  
|------------|-----------------|  
|ConnectFailure|Mit den Remotedienst konnte auf der Transportebene Kontakt hergestellt werden.|  
|ConnectionClosed|Die Verbindung wurde vorzeitig geschlossen.|  
|KeepAliveFailure|Der Server wurde eine Beziehung, die mit dem Keep\-Alive\-Headersatz hergestellt wurde.|  
|NameResolutionFailure|Der Namedienst konnte den Hostnamen nicht auflösen.|  
|ProtocolError|Die Antwort, die vom Server empfangen wurde, war, vollständig jedoch ist ein Fehler auf der Protokollebene an.|  
|ReceiveFailure|Es wurde keine vollständige Antwort vom Remoteserver empfangen.|  
|RequestCanceled|Die Anforderung wurde abgebrochen.|  
|SecureChannelFailure|Fehler beim in einem Link eines sicheren Channels auf.|  
|SendFailure|Es konnte keine vollständige Anforderung an den Remoteserver gesendet werden.|  
|ServerProtocolViolation|Die Antwort vom Server war keine gültige HTTP\-Antwort.|  
|Erfolgreich|Es ist kein Fehler aufgetreten.|  
|Timeout|Keine Antwort wurde innerhalb des Timeouts empfangen, das für die Anforderung festgelegt wurde.|  
|TrustFailure|Ein Serverzertifikat konnte nicht überprüft werden.|  
|MessageLengthLimitExceeded|Es wurde eine Meldung empfangen, bei der die festgelegte Größe für das Senden einer Anforderung bzw. das Empfangen einer Antwort vom Server überschritten wurde.|  
|Schwebend|Eine interne asynchrone Anforderung steht aus.|  
|PipelineFailure|Dieser Wert unterstützt die .NET Framework\-Infrastruktur und ist nicht vorgesehen, direkt im Code verwendet werden.|  
|ProxyNameResolutionFailure|Der Namensauflösungsdienst konnte den Proxyhostnamen nicht auflösen.|  
|UnknownError|Eine Ausnahme unbekannten Typs ist aufgetreten.|  
  
 Wenn die **Status**\-Eigenschaft **WebExceptionStatus.ProtocolError** ist, ist **WebResponse**, die die Antwort vom Server enthält, verfügbar.  Sie können diese Antwort überprüfen, um die tatsächliche Quelle des Protokollfehlers zu bestimmen.  
  
 Im folgenden Beispiel wird gezeigt, wie **WebException** abfängt.  
  
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
  
 Anwendungen, die den <xref:System.Net.Sockets.Socket>\-Klassenwurf [SocketExceptions](frlrfsystemnetsocketssocketexceptionclasstopic) verwenden, wenn Fehler auf dem Windows Socket auftreten.  Die [TCPClient](frlrfsystemnetsocketstcpclientclasstopic), [TCPListener](frlrfsystemnetsocketstcplistenerclasstopic) und [UDPClient](frlrfsystemnetsocketsudpclientclasstopic)\-Klassen werden auf die **Socket**\-Klasse erstellt und **SocketExceptions** auslösen.  
  
 Wenn **SocketException** ausgelöst wird, legt die **SocketException**\-Klasse die <xref:System.Net.Sockets.SocketException.ErrorCode%2A>\-Eigenschaft zum letzten Betriebssystemsocketfehler fest, der aufgetreten ist.  Weitere Informationen zu Socketfehlercodes, finden Sie die Fehlercodedokumentation Winsocks 2,0 APIs in MSDN.  
  
## Siehe auch  
 [Grundlagen der Ausnahmebehandlung](../../../docs/standard/exceptions/exception-handling-fundamentals.md)   
 [Anfordern von Daten](../../../docs/framework/network-programming/requesting-data.md)