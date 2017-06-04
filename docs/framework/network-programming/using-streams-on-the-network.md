---
title: "Verwenden von Streams im Netzwerk | Microsoft Docs"
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
  - "Anfordern von Daten aus dem Internet, Streams"
  - "Netzwerk"
  - "Antwort auf Internetanforderung, Streams"
  - "Netzwerkressourcen, Streamfunktionen"
  - "Empfangen von Daten, Streamfunktionen"
  - "Netzwerkressourcen"
  - "Senden von Daten, Streamfunktionen"
  - "Herunterladen von Internetressourcen, Streams"
  - "Streams, Funktionen"
  - "Internet, Streams"
  - "Streams"
ms.assetid: 02b05fba-7235-45ce-94e5-060436ee0875
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Verwenden von Streams im Netzwerk
Netzwerkressourcen werden in .NET Framework als Streams dargestellt.  Durch das generisch Streams behandelt, stellt .NET Framework die folgenden Funktionen:  
  
-   Eine gängige Methode, Internet\-Daten zu senden und zu empfangen.  Was auch immer der tatsächliche Inhalt der Datei \- HTML, XML oder sonstige \- die Anwendung <xref:System.IO.Stream.Write%2A?displayProperty=fullName> und <xref:System.IO.Stream.Read%2A?displayProperty=fullName> verwendet, um Daten zu senden und zu empfangen.  
  
-   Kompatibilität mit Streams zu .NET Framework.  Streams werden beim .NET Framework verwendet, das eine umfassende Infrastruktur zum Behandeln sie verfügt.  Beispielsweise können Sie eine Anwendung ändern, die XML\-Daten aus <xref:System.IO.FileStream> zu den Lesedaten von <xref:System.Net.Sockets.NetworkStream> stattdessen wird, indem Sie nur die wenigen Codezeilen ändert, die den Stream initialisieren.  Die wichtigsten Unterschiede zwischen der **NetworkStream**\-Klasse und anderen Streams sind, dass **NetworkStream** nicht seekable ist, die <xref:System.Net.Sockets.NetworkStream.CanSeek%2A>\-Eigenschaft gibt stets **false**, und die <xref:System.Net.Sockets.NetworkStream.Seek%2A> und <xref:System.Net.Sockets.NetworkStream.Position%2A>\-Methoden lösen <xref:System.NotSupportedException> aus.  
  
-   Verarbeiten von Daten, wie sie ankommt.  Streams ermöglichen den Zugriff auf die Daten, während er vom Netzwerk eintrifft, anstatt die Anwendung kein, heruntergeladen werden Dataset zu warten ein.  
  
 Der <xref:System.Net.Sockets>\-Namespace **NetworkStream** enthält eine Klasse, die die <xref:System.IO.Stream>\-Klasse speziell für die Verwendung mit Netzwerkressourcen implementiert.  Klassen im <xref:System.Net.Sockets>\-Namespace verwenden, um die **NetworkStream**\-Klasse Streams darzustellen.  
  
 Um Daten im Netzwerk mithilfe des zurückgegebenen Streams zu senden, rufen Sie <xref:System.Net.WebRequest.GetRequestStream%2A> auf dem <xref:System.Net.WebRequest> auf.  **WebRequest** sendet Anforderungsheader an den Server; können Daten zur Netzwerkressource senden, indem Sie <xref:System.IO.Stream.BeginWrite%2A>, <xref:System.IO.Stream.EndWrite%2A> oder <xref:System.IO.Stream.Write%2A>\-Methode für den zurückgegebenen Stream aufrufen.  Einige Protokolle, wie HTTP, benötigen Sie möglicherweise, protokollspezifische Eigenschaften festlegt, bevor Daten senden.  Im folgenden Codebeispiel wird gezeigt, wie HTTP\-spezifische Eigenschaften für das Senden von Daten festlegen.  Es wird davon ausgegangen, dass variable `sendData` die Daten enthält, die zum Senden und dass variable `sendLength` die Anzahl von Bytes ist, Daten zu senden.  
  
```csharp  
HttpWebRequest request =   
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
request.Method = "POST";  
request.ContentLength = sendLength;  
try  
{  
   Stream sendStream = request.GetRequestStream();  
   sendStream.Write(sendData,0,sendLength);  
   sendStream.Close();  
}  
catch  
{  
   // Handle errors . . .  
}  
  
```  
  
```vb  
Dim request As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
request.Method = "POST"  
request.ContentLength = sendLength  
Try  
   Dim sendStream As Stream = request.GetRequestStream()  
   sendStream.Write(sendData, 0, sendLength)  
   sendStream.Close()  
Catch  
   ' Handle errors . . .  
End Try  
```  
  
 Um Daten aus dem Netzwerk empfangen, rufen Sie <xref:System.Net.WebResponse.GetResponseStream%2A> auf dem <xref:System.Net.WebResponse> auf.  Sie können Daten aus der Netzwerkressource dann lesen, indem Sie <xref:System.IO.Stream.BeginRead%2A>, <xref:System.IO.Stream.EndRead%2A> oder <xref:System.IO.Stream.Read%2A>\-Methode für den zurückgegebenen Stream aufrufen.  
  
 Bei Verwendung von den Netzwerkressourcen streamt, beachten Sie die folgenden Punkte:  
  
-   Die **CanSeek** **false**\-Eigenschaft gibt immer zurück, da die **NetworkStream**\-Klasse Position im Stream nicht ändern kann.  Die **Seek** und **Position**\-Methoden lösen **NotSupportedException** aus.  
  
-   Wenn Sie **WebRequest** und **WebResponse** verwenden, sind die Streaminstanzen, die erstellt werden, indem sie **GetResponseStream** aufrufen, schreibgeschützt und die Streaminstanzen, die erstellt werden, indem sie **GetRequestStream** aufrufen, sind lesegeschützt.  
  
-   Verwenden Sie die <xref:System.IO.StreamReader>\-Klasse, um die Codierung zu vereinfachen.  Im folgenden Codebeispiel wird **StreamReader**, um einen Stream von ASCII\-codierten **WebResponse**  zu lesen \(das Beispiel enthält nicht das Erstellen der Anforderung an\).  
  
-   Der Aufruf **GetResponse** kann blockieren, wenn Netzwerkressourcen nicht verfügbar sind.  Sie sollten eine, asynchrone Anforderung mit den <xref:System.Net.WebRequest.BeginGetResponse%2A> und <xref:System.Net.WebRequest.EndGetResponse%2A>\-Methoden in Erwägung ziehen.  
  
-   Der Aufruf **GetRequestStream** kann blockieren, während die Verbindung zum Server erstellt wird.  Sie sollten eine, asynchrone Anforderung für den Stream mit den <xref:System.Net.WebRequest.BeginGetRequestStream%2A> und <xref:System.Net.WebRequest.EndGetRequestStream%2A>\-Methoden in Erwägung ziehen.  
  
```csharp  
// Create a response object.  
WebResponse response = request.GetResponse();  
// Get a readable stream from the server.  
StreamReader sr =   
   new StreamReader(response.GetResponseStream(), Encoding.ASCII);  
// Use the stream. Remember when you are through with the stream to close it.  
sr.Close();  
```  
  
```vb  
' Create a response object.  
Dim response As WebResponse = request.GetResponse()  
' Get a readable stream from the server.  
Dim sr As _   
   New StreamReader(response.GetResponseStream(), Encoding.ASCII)  
' Use the stream. Remember when you are through with the stream to close it.  
sr.Close()  
```  
  
## Siehe auch  
 [Gewusst wie: Anfordern von Daten mithilfe der WebRequest\-Klasse](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)   
 [Anfordern von Daten](../../../docs/framework/network-programming/requesting-data.md)