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
# <a name="using-streams-on-the-network"></a><span data-ttu-id="010bd-104">Verwenden von Streams im Netzwerk</span><span class="sxs-lookup"><span data-stu-id="010bd-104">Using Streams on the Network</span></span>

<span data-ttu-id="010bd-105">Netzwerkressourcen werden in .NET Framework als Streams dargestellt.</span><span class="sxs-lookup"><span data-stu-id="010bd-105">Network resources are represented in the .NET Framework as streams.</span></span> <span data-ttu-id="010bd-106">Durch die generische Verarbeitung von Streams verfügt .NET Framework über folgende Funktionen:</span><span class="sxs-lookup"><span data-stu-id="010bd-106">By treating streams generically, the .NET Framework offers the following capabilities:</span></span>  
  
- <span data-ttu-id="010bd-107">Eine allgemeine Möglichkeit zum Senden und Empfangen von Webdaten.</span><span class="sxs-lookup"><span data-stu-id="010bd-107">A common way to send and receive Web data.</span></span> <span data-ttu-id="010bd-108">Unabhängig vom tatsächlichen Inhalt der Datei — HTML, XML oder Sonstiges — wird Ihre Anwendung <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType> und <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType> zum Senden und Empfangen von Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="010bd-108">Whatever the actual contents of the file — HTML, XML, or anything else — your application will use <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType> and <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType> to send and receive data.</span></span>  
  
- <span data-ttu-id="010bd-109">Kompatibilität mit Streams in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="010bd-109">Compatibility with streams across the .NET Framework.</span></span> <span data-ttu-id="010bd-110">Streams werden überall in .NET Framework verwendet. .NET Framework besitzt eine umfangreiche Infrastruktur für deren Behandlung.</span><span class="sxs-lookup"><span data-stu-id="010bd-110">Streams are used throughout the .NET Framework, which has a rich infrastructure for handling them.</span></span> <span data-ttu-id="010bd-111">Beispielsweise können Sie eine Anwendung ändern, die XML-Daten aus einer <xref:System.IO.FileStream> liest, sodass sie die Daten stattdessen aus einer <xref:System.Net.Sockets.NetworkStream> liest, anstelle einer einfachen Änderung der Codezeilen, die den Stream initialisieren.</span><span class="sxs-lookup"><span data-stu-id="010bd-111">For example, you can modify an application that reads XML data from a <xref:System.IO.FileStream> to read data from a <xref:System.Net.Sockets.NetworkStream> instead by changing only the few lines of code that initialize the stream.</span></span> <span data-ttu-id="010bd-112">Die wichtigsten Unterschiede zwischen der **NetworkStream**-Klasse und anderen Streams sind die folgenden: **NetworkStream** ist nicht durchsuchbar, die <xref:System.Net.Sockets.NetworkStream.CanSeek%2A>-Eigenschaft gibt immer **FALSE** zurück, und die <xref:System.Net.Sockets.NetworkStream.Seek%2A>- und <xref:System.Net.Sockets.NetworkStream.Position%2A>-Methoden lösen eine <xref:System.NotSupportedException> aus.</span><span class="sxs-lookup"><span data-stu-id="010bd-112">The major differences between the **NetworkStream** class and other streams are that **NetworkStream** is not seekable, the <xref:System.Net.Sockets.NetworkStream.CanSeek%2A> property always returns **false**, and the <xref:System.Net.Sockets.NetworkStream.Seek%2A> and <xref:System.Net.Sockets.NetworkStream.Position%2A> methods throw a <xref:System.NotSupportedException>.</span></span>  
  
- <span data-ttu-id="010bd-113">Die Verarbeitung der eingehenden Daten.</span><span class="sxs-lookup"><span data-stu-id="010bd-113">Processing of data as it arrives.</span></span> <span data-ttu-id="010bd-114">Streams bieten Zugriff auf eingehende Daten über das Netzwerk, anstatt die Anwendung zu zwingen, zu warten, bis der gesamte Datensatz heruntergeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="010bd-114">Streams provide access to data as it arrives from the network, rather than forcing your application to wait for an entire data set to be downloaded.</span></span>  
  
 <span data-ttu-id="010bd-115">Der <xref:System.Net.Sockets>-Namespace enthält eine **NetworkStream**-Klasse, die die <xref:System.IO.Stream>-Klasse speziell zur Verwendung mit Netzwerkressourcen implementiert.</span><span class="sxs-lookup"><span data-stu-id="010bd-115">The <xref:System.Net.Sockets> namespace contains a **NetworkStream** class that implements the <xref:System.IO.Stream> class specifically for use with network resources.</span></span> <span data-ttu-id="010bd-116">Klassen im <xref:System.Net.Sockets>-Namespace verwenden die **NetworkStream**-Klasse, um Streams darzustellen.</span><span class="sxs-lookup"><span data-stu-id="010bd-116">Classes in the <xref:System.Net.Sockets> namespace use the **NetworkStream** class to represent streams.</span></span>  
  
 <span data-ttu-id="010bd-117">Rufen Sie zum Senden von Daten an das Netzwerk mit dem zurückgegebenen Streams <xref:System.Net.WebRequest.GetRequestStream%2A> auf Ihrer <xref:System.Net.WebRequest> auf.</span><span class="sxs-lookup"><span data-stu-id="010bd-117">To send data to the network using the returned stream, call <xref:System.Net.WebRequest.GetRequestStream%2A> on your <xref:System.Net.WebRequest>.</span></span> <span data-ttu-id="010bd-118">**WebRequest** wird Anforderungsheader an den Server senden, und dann können Sie Daten an die Netzwerkressource senden, indem Sie die <xref:System.IO.Stream.BeginWrite%2A>-, <xref:System.IO.Stream.EndWrite%2A>- oder <xref:System.IO.Stream.Write%2A>-Methode auf dem zurückgegebenen Stream aufrufen.</span><span class="sxs-lookup"><span data-stu-id="010bd-118">The **WebRequest** will send request headers to the server; then you can send data to the network resource by calling the <xref:System.IO.Stream.BeginWrite%2A>, <xref:System.IO.Stream.EndWrite%2A>, or <xref:System.IO.Stream.Write%2A> method on the returned stream.</span></span> <span data-ttu-id="010bd-119">Für einige Protokolle, z.B. HTTP, müssen Sie möglicherweise protokollspezifische Eigenschaften festlegen, bevor Sie Daten versenden.</span><span class="sxs-lookup"><span data-stu-id="010bd-119">Some protocols, such as HTTP, may require you to set protocol-specific properties before sending data.</span></span> <span data-ttu-id="010bd-120">Das folgende Codebeispiel veranschaulicht, wie die HTTP-spezifischen Eigenschaften zum Versenden von Daten festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="010bd-120">The following code example shows how to set HTTP-specific properties for sending data.</span></span> <span data-ttu-id="010bd-121">Es nimmt an, dass die Variable `sendData` die zu sendenden Daten enthält, und dass die Variable `sendLength` der Anzahl der zu versendenden Datenbytes entspricht.</span><span class="sxs-lookup"><span data-stu-id="010bd-121">It assumes that the variable `sendData` contains the data to send and that the variable `sendLength` is the number of bytes of data to send.</span></span>  
  
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
  
 <span data-ttu-id="010bd-122">Um Daten aus dem Netzwerk zu empfangen, rufen Sie <xref:System.Net.WebResponse.GetResponseStream%2A> auf Ihrer <xref:System.Net.WebResponse> auf.</span><span class="sxs-lookup"><span data-stu-id="010bd-122">To receive data from the network, call <xref:System.Net.WebResponse.GetResponseStream%2A> on your <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="010bd-123">Anschließend können Sie Daten aus der Netzwerkressource lesen, indem Sie die <xref:System.IO.Stream.BeginRead%2A>-, <xref:System.IO.Stream.EndRead%2A>- oder <xref:System.IO.Stream.Read%2A>-Methode auf dem zurückgegebenen Stream aufrufen.</span><span class="sxs-lookup"><span data-stu-id="010bd-123">You can then read data from the network resource by calling the <xref:System.IO.Stream.BeginRead%2A>, <xref:System.IO.Stream.EndRead%2A>, or <xref:System.IO.Stream.Read%2A> method on the returned stream.</span></span>  
  
 <span data-ttu-id="010bd-124">Wenn Sie Streams aus Netzwerkressourcen verwenden, dann beachten Sie die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="010bd-124">When using streams from network resources, keep in mind the following points:</span></span>  
  
- <span data-ttu-id="010bd-125">Die **CanSeek**-Eigenschaft gibt immer **FALSE** zurück, da die **NetworkStream**-Klasse die Position im Stream nicht ändern kann.</span><span class="sxs-lookup"><span data-stu-id="010bd-125">The **CanSeek** property always returns **false** since the **NetworkStream** class cannot change position in the stream.</span></span> <span data-ttu-id="010bd-126">Die **Seek**- und **Position**-Methoden lösen eine **NotSupportedException** aus.</span><span class="sxs-lookup"><span data-stu-id="010bd-126">The **Seek** and **Position** methods throw a **NotSupportedException**.</span></span>  
  
- <span data-ttu-id="010bd-127">Wenn Sie **WebRequest** und **WebResponse** verwenden, sind Streaminstanzen, die durch den Aufruf von **GetResponseStream** erstellt wurden, schreibgeschützt und Streaminstanzen, die durch den Aufruf von **GetRequestStream** erstellt wurden, lesegeschützt.</span><span class="sxs-lookup"><span data-stu-id="010bd-127">When you use **WebRequest** and **WebResponse**, stream instances created by calling **GetResponseStream** are read-only and stream instances created by calling **GetRequestStream** are write-only.</span></span>  
  
- <span data-ttu-id="010bd-128">Verwenden Sie die <xref:System.IO.StreamReader>-Klasse, um die Codierung einfacher zu machen.</span><span class="sxs-lookup"><span data-stu-id="010bd-128">Use the <xref:System.IO.StreamReader> class to make encoding easier.</span></span> <span data-ttu-id="010bd-129">Im folgenden Codebeispiel wird ein ASCII-codierter Stream mit einem **StreamReader** aus einer **WebResponse** gelesen (das Beispiel zeigt die Anforderungserstellung nicht).</span><span class="sxs-lookup"><span data-stu-id="010bd-129">The following code example uses a **StreamReader** to read an ASCII-encoded stream from a **WebResponse** (the example does not show creating the request).</span></span>  
  
- <span data-ttu-id="010bd-130">Der Aufruf von **GetResponse** könnte blockiert werden, wenn Netzwerkressourcen nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="010bd-130">The call to **GetResponse** can block if network resources are not available.</span></span> <span data-ttu-id="010bd-131">Verwenden Sie eine asynchrone Anforderung mit den <xref:System.Net.WebRequest.BeginGetResponse%2A>- und <xref:System.Net.WebRequest.EndGetResponse%2A>-Methoden.</span><span class="sxs-lookup"><span data-stu-id="010bd-131">You should consider using an asynchronous request with the <xref:System.Net.WebRequest.BeginGetResponse%2A> and <xref:System.Net.WebRequest.EndGetResponse%2A> methods.</span></span>  
  
- <span data-ttu-id="010bd-132">Der Aufruf von **GetRequestStream** könnte blockiert werden während die Verbindung mit dem Server erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="010bd-132">The call to **GetRequestStream** can block while the connection to the server is created.</span></span> <span data-ttu-id="010bd-133">Verwenden Sie eine asynchrone Anforderung für den Stream mit den <xref:System.Net.WebRequest.BeginGetRequestStream%2A>- und <xref:System.Net.WebRequest.EndGetRequestStream%2A>-Methoden.</span><span class="sxs-lookup"><span data-stu-id="010bd-133">You should consider using an asynchronous request for the stream with the <xref:System.Net.WebRequest.BeginGetRequestStream%2A> and <xref:System.Net.WebRequest.EndGetRequestStream%2A> methods.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="010bd-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="010bd-134">See also</span></span>

- [<span data-ttu-id="010bd-135">How to: Anfordern von Daten mithilfe der WebRequest-Klasse</span><span class="sxs-lookup"><span data-stu-id="010bd-135">How to: Request Data Using the WebRequest Class</span></span>](how-to-request-data-using-the-webrequest-class.md)
- [<span data-ttu-id="010bd-136">Requesting Data (Anfordern von Daten)</span><span class="sxs-lookup"><span data-stu-id="010bd-136">Requesting Data</span></span>](requesting-data.md)
