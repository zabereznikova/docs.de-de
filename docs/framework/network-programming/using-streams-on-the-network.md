---
title: Verwenden von Streams im Netzwerk
description: Das .NET Framework stellt die Netzwerkressourcen als Streams dar. Die NetworkStream-Klasse implementiert die Stream-Klasse für die Verwendung mit Netzwerkressourcen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- requesting data from Internet, streams
- Networking
- response to Internet request, streams
- network resources, stream capabilities
- receiving data, stream capabilities
- Network Resources
- sending data, stream capabilities
- downloading Internet resources, streams
- streams, capabilities
- Internet, streams
- streams
ms.assetid: 02b05fba-7235-45ce-94e5-060436ee0875
ms.openlocfilehash: c59e4aa2edad7b28203cfce5f568f8ccb8558dbb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263112"
---
# <a name="using-streams-on-the-network"></a>Verwenden von Streams im Netzwerk

Netzwerkressourcen werden in .NET Framework als Streams dargestellt. Durch die generische Verarbeitung von Streams verfügt .NET Framework über folgende Funktionen:  
  
- Eine allgemeine Möglichkeit zum Senden und Empfangen von Webdaten. Unabhängig vom tatsächlichen Inhalt der Datei — HTML, XML oder Sonstiges — wird Ihre Anwendung <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType> und <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType> zum Senden und Empfangen von Daten verwenden.  
  
- Kompatibilität mit Streams in .NET Framework. Streams werden überall in .NET Framework verwendet. .NET Framework besitzt eine umfangreiche Infrastruktur für deren Behandlung. Beispielsweise können Sie eine Anwendung ändern, die XML-Daten aus einer <xref:System.IO.FileStream> liest, sodass sie die Daten stattdessen aus einer <xref:System.Net.Sockets.NetworkStream> liest, anstelle einer einfachen Änderung der Codezeilen, die den Stream initialisieren. Die wichtigsten Unterschiede zwischen der **NetworkStream**-Klasse und anderen Streams sind die folgenden: **NetworkStream** ist nicht durchsuchbar, die <xref:System.Net.Sockets.NetworkStream.CanSeek%2A>-Eigenschaft gibt immer **FALSE** zurück, und die <xref:System.Net.Sockets.NetworkStream.Seek%2A>- und <xref:System.Net.Sockets.NetworkStream.Position%2A>-Methoden lösen eine <xref:System.NotSupportedException> aus.  
  
- Die Verarbeitung der eingehenden Daten. Streams bieten Zugriff auf eingehende Daten über das Netzwerk, anstatt die Anwendung zu zwingen, zu warten, bis der gesamte Datensatz heruntergeladen wurde.  
  
 Der <xref:System.Net.Sockets>-Namespace enthält eine **NetworkStream**-Klasse, die die <xref:System.IO.Stream>-Klasse speziell zur Verwendung mit Netzwerkressourcen implementiert. Klassen im <xref:System.Net.Sockets>-Namespace verwenden die **NetworkStream**-Klasse, um Streams darzustellen.  
  
 Rufen Sie zum Senden von Daten an das Netzwerk mit dem zurückgegebenen Streams <xref:System.Net.WebRequest.GetRequestStream%2A> auf Ihrer <xref:System.Net.WebRequest> auf. **WebRequest** wird Anforderungsheader an den Server senden, und dann können Sie Daten an die Netzwerkressource senden, indem Sie die <xref:System.IO.Stream.BeginWrite%2A>-, <xref:System.IO.Stream.EndWrite%2A>- oder <xref:System.IO.Stream.Write%2A>-Methode auf dem zurückgegebenen Stream aufrufen. Für einige Protokolle, z.B. HTTP, müssen Sie möglicherweise protokollspezifische Eigenschaften festlegen, bevor Sie Daten versenden. Das folgende Codebeispiel veranschaulicht, wie die HTTP-spezifischen Eigenschaften zum Versenden von Daten festgelegt werden. Es nimmt an, dass die Variable `sendData` die zu sendenden Daten enthält, und dass die Variable `sendLength` der Anzahl der zu versendenden Datenbytes entspricht.  
  
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
  
 Um Daten aus dem Netzwerk zu empfangen, rufen Sie <xref:System.Net.WebResponse.GetResponseStream%2A> auf Ihrer <xref:System.Net.WebResponse> auf. Anschließend können Sie Daten aus der Netzwerkressource lesen, indem Sie die <xref:System.IO.Stream.BeginRead%2A>-, <xref:System.IO.Stream.EndRead%2A>- oder <xref:System.IO.Stream.Read%2A>-Methode auf dem zurückgegebenen Stream aufrufen.  
  
 Wenn Sie Streams aus Netzwerkressourcen verwenden, dann beachten Sie die folgenden Punkte:  
  
- Die **CanSeek**-Eigenschaft gibt immer **FALSE** zurück, da die **NetworkStream**-Klasse die Position im Stream nicht ändern kann. Die **Seek**- und **Position**-Methoden lösen eine **NotSupportedException** aus.  
  
- Wenn Sie **WebRequest** und **WebResponse** verwenden, sind Streaminstanzen, die durch den Aufruf von **GetResponseStream** erstellt wurden, schreibgeschützt und Streaminstanzen, die durch den Aufruf von **GetRequestStream** erstellt wurden, lesegeschützt.  
  
- Verwenden Sie die <xref:System.IO.StreamReader>-Klasse, um die Codierung einfacher zu machen. Im folgenden Codebeispiel wird ein ASCII-codierter Stream mit einem **StreamReader** aus einer **WebResponse** gelesen (das Beispiel zeigt die Anforderungserstellung nicht).  
  
- Der Aufruf von **GetResponse** könnte blockiert werden, wenn Netzwerkressourcen nicht verfügbar sind. Verwenden Sie eine asynchrone Anforderung mit den <xref:System.Net.WebRequest.BeginGetResponse%2A>- und <xref:System.Net.WebRequest.EndGetResponse%2A>-Methoden.  
  
- Der Aufruf von **GetRequestStream** könnte blockiert werden während die Verbindung mit dem Server erstellt wird. Verwenden Sie eine asynchrone Anforderung für den Stream mit den <xref:System.Net.WebRequest.BeginGetRequestStream%2A>- und <xref:System.Net.WebRequest.EndGetRequestStream%2A>-Methoden.  
  
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
  
## <a name="see-also"></a>Siehe auch

- [How to: Anfordern von Daten mithilfe der WebRequest-Klasse](how-to-request-data-using-the-webrequest-class.md)
- [Requesting Data (Anfordern von Daten)](requesting-data.md)
