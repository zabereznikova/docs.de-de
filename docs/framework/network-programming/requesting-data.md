---
title: Anfordern von Daten
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
ms.openlocfilehash: 1f367caf7656a83597b6262a5746686df15d33b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047316"
---
# <a name="requesting-data"></a><span data-ttu-id="a91eb-102">Anfordern von Daten</span><span class="sxs-lookup"><span data-stu-id="a91eb-102">Requesting Data</span></span>
<span data-ttu-id="a91eb-103">Um Anwendungen zu entwickeln, die in der verteilten Betriebssystemumgebung des heutigen Internets ausgeführt werden können, benötigen Sie eine effiziente und einfach zu nutzende Methode für das Abrufen von Daten aus Ressourcen aller Art.</span><span class="sxs-lookup"><span data-stu-id="a91eb-103">Developing applications that run in the distributed operating environment of today's Internet requires an efficient, easy-to-use method for retrieving data from resources of all types.</span></span> <span data-ttu-id="a91eb-104">Mithilfe austauschbarer Protokolle lassen sich Anwendungen entwickeln, in denen über eine einzige Schnittstelle Daten aus mehreren Internetprotokollen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a91eb-104">Pluggable protocols let you develop applications that use a single interface to retrieve data from multiple Internet protocols.</span></span>  
  
## <a name="uploading-and-downloading-data-from-an-internet-server"></a><span data-ttu-id="a91eb-105">Hochladen und Herunterladen von Daten aus einem Internetserver</span><span class="sxs-lookup"><span data-stu-id="a91eb-105">Uploading and Downloading Data from an Internet Server</span></span>  
 <span data-ttu-id="a91eb-106">Für eine einfache Transaktion mit Anforderung und Antwort lassen sich mit der Klasse <xref:System.Net.WebClient> am einfachsten Daten auf einen Internetserver hoch- oder von ihm herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="a91eb-106">For simple request and response transactions, the <xref:System.Net.WebClient> class provides the easiest method for uploading data to or downloading data from an Internet server.</span></span> <span data-ttu-id="a91eb-107">Die Klasse **WebClient** bietet Methoden für das Hoch- und Herunterladen von Dateien, für das Senden und Empfangen von Streams und für das Senden eines Datenpuffers an den Server und den Empfang einer Antwort.</span><span class="sxs-lookup"><span data-stu-id="a91eb-107">**WebClient** provides methods for uploading and downloading files, sending and receiving streams, and sending a data buffer to the server and receiving a response.</span></span> <span data-ttu-id="a91eb-108">**WebClient** verwendet die Klassen <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse>, um die tatsächlichen Verbindungen zu den Internetressourcen herzustellen, damit jedes registrierte, austauschbare Protokoll genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a91eb-108">**WebClient** uses the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes to make the actual connections to the Internet resource, so any registered pluggable protocol is available for use.</span></span>  
  
 <span data-ttu-id="a91eb-109">Clientanwendungen, für die komplexere Transaktionen ausgeführt werden, fordern Daten mithilfe der Klasse **WebRequest** und ihren Nachfolgern von den Servern an.</span><span class="sxs-lookup"><span data-stu-id="a91eb-109">Client applications that need to make more complex transactions request data from servers using the **WebRequest** class and its descendants.</span></span> <span data-ttu-id="a91eb-110">**WebRequest** kapselt die Details zum Aufbau der Serververbindung, zum Senden der Anforderung und zum Empfang der Nachricht ein.</span><span class="sxs-lookup"><span data-stu-id="a91eb-110">**WebRequest** encapsulates the details of connecting to the server, sending the request, and receiving the response.</span></span> <span data-ttu-id="a91eb-111">**WebRequest** ist eine abstrakte Klasse, die eine Reihe von Eigenschaften und Methoden definiert. Diese sind für alle Anwendungen verfügbar, die austauschbare Protokolle nutzen.</span><span class="sxs-lookup"><span data-stu-id="a91eb-111">**WebRequest** is an abstract class that defines a set of properties and methods that are available to all applications that use pluggable protocols.</span></span> <span data-ttu-id="a91eb-112">Nachfolger von **WebRequest**, z.B. <xref:System.Net.HttpWebRequest>, implementieren die von **WebRequest** definierten Eigenschaften und Methoden konsistent zum zu Grunde liegenden Protokoll.</span><span class="sxs-lookup"><span data-stu-id="a91eb-112">Descendants of **WebRequest**, such as <xref:System.Net.HttpWebRequest>, implement the properties and methods defined by **WebRequest** in a way that is consistent with the underlying protocol.</span></span>  
  
 <span data-ttu-id="a91eb-113">**WebRequest** erstellt protokollspezifische Instanzen von **WebRequest**-Nachfolgern. Hierfür wird mit den an die Methode <xref:System.Net.WebRequest.Create%2A> übergebenen Werten bestimmt, welche Instanz der abgeleiteten Klasse erstellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="a91eb-113">The **WebRequest** class creates protocol-specific instances of **WebRequest** descendants, using the value of the URI passed to its <xref:System.Net.WebRequest.Create%2A> method to determine the specific derived-class instance to create.</span></span> <span data-ttu-id="a91eb-114">Anwendungen geben an, welcher **WebRequest**-Nachfolger verwendet werden sollte, um eine Anforderung zu handeln. Dies geschieht durch die Registrierung des Nachfolgerkonstruktors mithilfe der Methode <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a91eb-114">Applications indicate which **WebRequest** descendant should be used to handle a request by registering the descendant's constructor with the <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="a91eb-115">Für eine Anforderung an eine Internetressource wird die Methode <xref:System.Net.WebRequest.GetResponse%2A> der Klasse **WebRequest** aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a91eb-115">A request is made to the Internet resource by calling the <xref:System.Net.WebRequest.GetResponse%2A> method on the **WebRequest**.</span></span> <span data-ttu-id="a91eb-116">Die Methode **GetResponse** konstruiert die protokollspezifische Anforderung aus den Eigenschaften der **WebRequest**-Klasse, stellt die TCP- oder UDP-Socketverbindung zum Server her und sendet die Anforderung.</span><span class="sxs-lookup"><span data-stu-id="a91eb-116">The **GetResponse** method constructs the protocol-specific request from the properties of the **WebRequest**, makes the TCP or UDP socket connection to the server, and sends the request.</span></span> <span data-ttu-id="a91eb-117">Bei Anforderungen, im Rahmen derer Daten an einen Server gesendet werden, z.B. HTTP **Post** oder FTP **Put**, stellt die Methode <xref:System.Net.WebRequest.GetRequestStream%2A?displayProperty=nameWithType> dafür einen Netzwerkstream bereit.</span><span class="sxs-lookup"><span data-stu-id="a91eb-117">For requests that send data to the server, such as HTTP **Post** or FTP **Put** requests, the <xref:System.Net.WebRequest.GetRequestStream%2A?displayProperty=nameWithType> method provides a network stream in which to send the data.</span></span>  
  
 <span data-ttu-id="a91eb-118">Die Methode **GetResponse** gibt eine protokollspezifische **WebResponse** zurück, die mit **WebRequest** übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a91eb-118">The **GetResponse** method returns a protocol-specific **WebResponse** that matches the **WebRequest.**</span></span>  
  
 <span data-ttu-id="a91eb-119">Die Klasse **WebResponse** ist ebenfalls eine abstrakte Klasse, die Eigenschaften und Methoden definiert, die für alle Anwendungen mit austauschbaren Protokollen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a91eb-119">The **WebResponse** class is also an abstract class that defines properties and methods that are available to all applications that use pluggable protocols.</span></span> <span data-ttu-id="a91eb-120">**WebResponse**-Nachfolger implementieren diese Eigenschaften und Methoden für das zu Grunde liegende Protokoll.</span><span class="sxs-lookup"><span data-stu-id="a91eb-120">**WebResponse** descendants implement these properties and methods for the underlying protocol.</span></span> <span data-ttu-id="a91eb-121">Beispielsweise implementiert die Klasse <xref:System.Net.HttpWebResponse> die **WebResponse**-Klasse für HTTP.</span><span class="sxs-lookup"><span data-stu-id="a91eb-121">The <xref:System.Net.HttpWebResponse> class, for example, implements the **WebResponse** class for HTTP.</span></span>  
  
 <span data-ttu-id="a91eb-122">Die vom Server zurückgegebenen Daten sind für die Anwendung über den von der Methode <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> zurückgegebenen Stream verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a91eb-122">The data returned by the server is presented to the application in the stream returned by the <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a91eb-123">Wie in den folgenden Beispielen gezeigt, lässt sich dieser Stream wie alle anderen auch verwenden.</span><span class="sxs-lookup"><span data-stu-id="a91eb-123">You can use this stream like any other, as shown in the following example.</span></span>  
  
```csharp  
StreamReader sr =  
   new StreamReader(resp.GetResponseStream(), Encoding.ASCII);  
```  
  
```vb  
Dim sr As StreamReader  
sr = New StreamReader(resp.GetResponseStream(), Encoding.ASCII)  
```  
  
## <a name="see-also"></a><span data-ttu-id="a91eb-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a91eb-124">See also</span></span>

- [<span data-ttu-id="a91eb-125">Netzwerkprogrammierung in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a91eb-125">Network Programming in the .NET Framework</span></span>](index.md)
- [<span data-ttu-id="a91eb-126">Vorgehensweise: Anfordern einer Webseite und Abrufen der Ergebnisse als Stream</span><span class="sxs-lookup"><span data-stu-id="a91eb-126">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>](how-to-request-a-web-page-and-retrieve-the-results-as-a-stream.md)
- [<span data-ttu-id="a91eb-127">Vorgehensweise: Abrufen eines protokollspezifischen WebResponse, das einem WebRequest entspricht</span><span class="sxs-lookup"><span data-stu-id="a91eb-127">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>](how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest.md)
