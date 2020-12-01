---
title: Anfordern von Daten
description: Hier erfahren Sie, wie Sie mit austauschbaren Protokollen Anwendungen entwickeln können, in denen über eine einzige Schnittstelle Daten aus mehreren Protokollen abgerufen werden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sending data
- WebRequest class, sending and receiving data
- requesting data from Internet, about requesting data
- WebClient class, sending and receiving data
- network, requesting data
- receiving data
- sending data, about sending data
- response to Internet request, about responding to Internet requests
- data requests
- receiving data, about receiving data
- Internet, requesting data
ms.assetid: df6f1e1d-6f2a-45dd-8141-4a85c3dafe1d
ms.openlocfilehash: 87ad0144f57bdca0e0235aea30c4ab450cc890f4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279297"
---
# <a name="requesting-data"></a><span data-ttu-id="81470-103">Anfordern von Daten</span><span class="sxs-lookup"><span data-stu-id="81470-103">Requesting Data</span></span>

<span data-ttu-id="81470-104">Um Anwendungen zu entwickeln, die in der verteilten Betriebssystemumgebung des heutigen Internets ausgeführt werden können, benötigen Sie eine effiziente und einfach zu nutzende Methode für das Abrufen von Daten aus Ressourcen aller Art.</span><span class="sxs-lookup"><span data-stu-id="81470-104">Developing applications that run in the distributed operating environment of today's Internet requires an efficient, easy-to-use method for retrieving data from resources of all types.</span></span> <span data-ttu-id="81470-105">Mithilfe austauschbarer Protokolle lassen sich Anwendungen entwickeln, in denen über eine einzige Schnittstelle Daten aus mehreren Internetprotokollen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="81470-105">Pluggable protocols let you develop applications that use a single interface to retrieve data from multiple Internet protocols.</span></span>  
  
## <a name="uploading-and-downloading-data-from-an-internet-server"></a><span data-ttu-id="81470-106">Hochladen und Herunterladen von Daten aus einem Internetserver</span><span class="sxs-lookup"><span data-stu-id="81470-106">Uploading and Downloading Data from an Internet Server</span></span>  

 <span data-ttu-id="81470-107">Für eine einfache Transaktion mit Anforderung und Antwort lassen sich mit der Klasse <xref:System.Net.WebClient> am einfachsten Daten auf einen Internetserver hoch- oder von ihm herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="81470-107">For simple request and response transactions, the <xref:System.Net.WebClient> class provides the easiest method for uploading data to or downloading data from an Internet server.</span></span> <span data-ttu-id="81470-108">Die Klasse **WebClient** bietet Methoden für das Hoch- und Herunterladen von Dateien, für das Senden und Empfangen von Streams und für das Senden eines Datenpuffers an den Server und den Empfang einer Antwort.</span><span class="sxs-lookup"><span data-stu-id="81470-108">**WebClient** provides methods for uploading and downloading files, sending and receiving streams, and sending a data buffer to the server and receiving a response.</span></span> <span data-ttu-id="81470-109">**WebClient** verwendet die Klassen <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse>, um die tatsächlichen Verbindungen zu den Internetressourcen herzustellen, damit jedes registrierte, austauschbare Protokoll genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="81470-109">**WebClient** uses the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes to make the actual connections to the Internet resource, so any registered pluggable protocol is available for use.</span></span>  
  
 <span data-ttu-id="81470-110">Clientanwendungen, für die komplexere Transaktionen ausgeführt werden, fordern Daten mithilfe der Klasse **WebRequest** und ihren Nachfolgern von den Servern an.</span><span class="sxs-lookup"><span data-stu-id="81470-110">Client applications that need to make more complex transactions request data from servers using the **WebRequest** class and its descendants.</span></span> <span data-ttu-id="81470-111">**WebRequest** kapselt die Details zum Aufbau der Serververbindung, zum Senden der Anforderung und zum Empfang der Nachricht ein.</span><span class="sxs-lookup"><span data-stu-id="81470-111">**WebRequest** encapsulates the details of connecting to the server, sending the request, and receiving the response.</span></span> <span data-ttu-id="81470-112">**WebRequest** ist eine abstrakte Klasse, die eine Reihe von Eigenschaften und Methoden definiert. Diese sind für alle Anwendungen verfügbar, die austauschbare Protokolle nutzen.</span><span class="sxs-lookup"><span data-stu-id="81470-112">**WebRequest** is an abstract class that defines a set of properties and methods that are available to all applications that use pluggable protocols.</span></span> <span data-ttu-id="81470-113">Nachfolger von **WebRequest**, z.B. <xref:System.Net.HttpWebRequest>, implementieren die von **WebRequest** definierten Eigenschaften und Methoden konsistent zum zu Grunde liegenden Protokoll.</span><span class="sxs-lookup"><span data-stu-id="81470-113">Descendants of **WebRequest**, such as <xref:System.Net.HttpWebRequest>, implement the properties and methods defined by **WebRequest** in a way that is consistent with the underlying protocol.</span></span>  
  
 <span data-ttu-id="81470-114">**WebRequest** erstellt protokollspezifische Instanzen von **WebRequest**-Nachfolgern. Hierfür wird mit den an die Methode <xref:System.Net.WebRequest.Create%2A> übergebenen Werten bestimmt, welche Instanz der abgeleiteten Klasse erstellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="81470-114">The **WebRequest** class creates protocol-specific instances of **WebRequest** descendants, using the value of the URI passed to its <xref:System.Net.WebRequest.Create%2A> method to determine the specific derived-class instance to create.</span></span> <span data-ttu-id="81470-115">Anwendungen geben an, welcher **WebRequest**-Nachfolger verwendet werden sollte, um eine Anforderung zu handeln. Dies geschieht durch die Registrierung des Nachfolgerkonstruktors mithilfe der Methode <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="81470-115">Applications indicate which **WebRequest** descendant should be used to handle a request by registering the descendant's constructor with the <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="81470-116">Für eine Anforderung an eine Internetressource wird die Methode <xref:System.Net.WebRequest.GetResponse%2A> der Klasse **WebRequest** aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="81470-116">A request is made to the Internet resource by calling the <xref:System.Net.WebRequest.GetResponse%2A> method on the **WebRequest**.</span></span> <span data-ttu-id="81470-117">Die Methode **GetResponse** konstruiert die protokollspezifische Anforderung aus den Eigenschaften der **WebRequest**-Klasse, stellt die TCP- oder UDP-Socketverbindung zum Server her und sendet die Anforderung.</span><span class="sxs-lookup"><span data-stu-id="81470-117">The **GetResponse** method constructs the protocol-specific request from the properties of the **WebRequest**, makes the TCP or UDP socket connection to the server, and sends the request.</span></span> <span data-ttu-id="81470-118">Bei Anforderungen, im Rahmen derer Daten an einen Server gesendet werden, z.B. HTTP **Post** oder FTP **Put**, stellt die Methode <xref:System.Net.WebRequest.GetRequestStream%2A?displayProperty=nameWithType> dafür einen Netzwerkstream bereit.</span><span class="sxs-lookup"><span data-stu-id="81470-118">For requests that send data to the server, such as HTTP **Post** or FTP **Put** requests, the <xref:System.Net.WebRequest.GetRequestStream%2A?displayProperty=nameWithType> method provides a network stream in which to send the data.</span></span>  
  
 <span data-ttu-id="81470-119">Die Methode **GetResponse** gibt eine protokollspezifische **WebResponse** zurück, die mit **WebRequest** übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="81470-119">The **GetResponse** method returns a protocol-specific **WebResponse** that matches the **WebRequest.**</span></span>  
  
 <span data-ttu-id="81470-120">Die Klasse **WebResponse** ist ebenfalls eine abstrakte Klasse, die Eigenschaften und Methoden definiert, die für alle Anwendungen mit austauschbaren Protokollen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="81470-120">The **WebResponse** class is also an abstract class that defines properties and methods that are available to all applications that use pluggable protocols.</span></span> <span data-ttu-id="81470-121">**WebResponse**-Nachfolger implementieren diese Eigenschaften und Methoden für das zu Grunde liegende Protokoll.</span><span class="sxs-lookup"><span data-stu-id="81470-121">**WebResponse** descendants implement these properties and methods for the underlying protocol.</span></span> <span data-ttu-id="81470-122">Beispielsweise implementiert die Klasse <xref:System.Net.HttpWebResponse> die **WebResponse**-Klasse für HTTP.</span><span class="sxs-lookup"><span data-stu-id="81470-122">The <xref:System.Net.HttpWebResponse> class, for example, implements the **WebResponse** class for HTTP.</span></span>  
  
 <span data-ttu-id="81470-123">Die vom Server zurückgegebenen Daten sind für die Anwendung über den von der Methode <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> zurückgegebenen Stream verfügbar.</span><span class="sxs-lookup"><span data-stu-id="81470-123">The data returned by the server is presented to the application in the stream returned by the <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="81470-124">Wie in den folgenden Beispielen gezeigt, lässt sich dieser Stream wie alle anderen auch verwenden.</span><span class="sxs-lookup"><span data-stu-id="81470-124">You can use this stream like any other, as shown in the following example.</span></span>  
  
```csharp  
StreamReader sr =  
   new StreamReader(resp.GetResponseStream(), Encoding.ASCII);  
```  
  
```vb  
Dim sr As StreamReader  
sr = New StreamReader(resp.GetResponseStream(), Encoding.ASCII)  
```  
  
## <a name="see-also"></a><span data-ttu-id="81470-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81470-125">See also</span></span>

- [<span data-ttu-id="81470-126">Netzwerkprogrammierung in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="81470-126">Network Programming in the .NET Framework</span></span>](index.md)
- [<span data-ttu-id="81470-127">How to: Anfordern einer Webseite und Abrufen der Ergebnisse als Stream</span><span class="sxs-lookup"><span data-stu-id="81470-127">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>](how-to-request-a-web-page-and-retrieve-the-results-as-a-stream.md)
- [<span data-ttu-id="81470-128">How to: Abrufen einer protokollspezifischen WebResponse-Klasse, die einer WebRequest-Klasse entspricht</span><span class="sxs-lookup"><span data-stu-id="81470-128">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>](how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest.md)
