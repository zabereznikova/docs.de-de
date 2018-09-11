---
title: Verwalten von Verbindungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Internet, connections
- HTTP, classes for connecting
- requesting data from Internet, connections
- sending data, connections
- receiving data, connections
- ServicePoint class, about ServicePoint class
- response to Internet request, connections
- connections [.NET Framework], classes
- network resources, connections
- downloading Internet resources, connections
- ServicePointManager class, about ServicePointManager class
ms.assetid: 9b3d3de7-189f-4f7d-81ae-9c29c441aaaa
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 29077a1c0f2b803270adb730e0d810143095e709
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526541"
---
# <a name="managing-connections"></a><span data-ttu-id="06b93-102">Verwalten von Verbindungen</span><span class="sxs-lookup"><span data-stu-id="06b93-102">Managing Connections</span></span>
<span data-ttu-id="06b93-103">Anwendungen, die HTTP zum Herstellen einer Verbindung mit Datenressourcen verwenden, können die <xref:System.Net.ServicePoint>- und <xref:System.Net.ServicePointManager>-Klassen von .NET Framework verwenden, um Verbindungen mit dem Internet zu verwalten und dabei zu helfen, dass diese eine optimale Skalierung und Leistung erreichen.</span><span class="sxs-lookup"><span data-stu-id="06b93-103">Applications that use HTTP to connect to data resources can use the .NET Framework's <xref:System.Net.ServicePoint> and <xref:System.Net.ServicePointManager> classes to manage connections to the Internet and to help them achieve optimum scale and performance.</span></span>  
  
 <span data-ttu-id="06b93-104">Die **ServicePoint**-Klasse stellt eine Anwendung mit einem Endpunkt bereit, mit der sich die Anwendung verbinden kann, um auf Internetressourcen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="06b93-104">The **ServicePoint** class provides an application with an endpoint to which the application can connect to access Internet resources.</span></span> <span data-ttu-id="06b93-105">Jede **ServicePoint**-Klasse enthält Informationen, die dabei helfen, Verbindungen mit einem Internetserver zu optimieren, indem Optimierungsinformationen zwischen Verbindungen geteilt werden, um die Leistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="06b93-105">Each **ServicePoint** contains information that helps optimize connections with an Internet server by sharing optimization information between connections to improve performance.</span></span>  
  
 <span data-ttu-id="06b93-106">Jede **ServicePoint**-Klasse wird durch einen URI (Uniform Resource Identifier) identifiziert und gemäß dem Schemabezeichner und Hostfragmenten des URI kategorisiert.</span><span class="sxs-lookup"><span data-stu-id="06b93-106">Each **ServicePoint** is identified by a Uniform Resource Identifier (URI) and is categorized according to the scheme identifier and host fragments of the URI.</span></span> <span data-ttu-id="06b93-107">Beispielsweise würde die gleiche **ServicePoint**-Instanz Anforderungen für die URIs `http://www.contoso.com/index.htm` und `http://www.contoso.com/news.htm?date=today` bereitstellen, da sie über den gleichen Schemabezeichner (HTTP) und die gleichen Hostfragmente (`www.contoso.com`) verfügen.</span><span class="sxs-lookup"><span data-stu-id="06b93-107">For example, the same **ServicePoint** instance would provide requests to the URIs `http://www.contoso.com/index.htm` and `http://www.contoso.com/news.htm?date=today` since they have the same scheme identifier (http) and host fragments (`www.contoso.com`).</span></span> <span data-ttu-id="06b93-108">Wenn die Anwendung bereits über eine persistente Verbindung mit dem Server `www.contoso.com` verfügt, ruft sie über diese Verbindung beide Anforderungen ab, wobei vermieden wird, dass zwei Verbindungen erstellt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="06b93-108">If the application already has a persistent connection to the server `www.contoso.com`, it uses that connection to retrieve both requests, avoiding the need to create two connections.</span></span>  
  
 <span data-ttu-id="06b93-109">**ServicePointManager** ist eine statische Klasse, die die Erstellung und Zerstörung von **ServicePoint**-Instanzen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="06b93-109">**ServicePointManager** is a static class that manages the creation and destruction of **ServicePoint** instances.</span></span> <span data-ttu-id="06b93-110">Die **ServicePointManager**-Klasse erstellt eine **ServicePoint**-Klasse, wenn die Anwendung eine Internetressource anfordert, die nicht in der Auflistung der vorhandenen **ServicePoint**-Instanzen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="06b93-110">The **ServicePointManager** creates a **ServicePoint** when the application requests an Internet resource that is not in the collection of existing **ServicePoint** instances.</span></span> <span data-ttu-id="06b93-111">**ServicePoint**-Instanzen werden zerstört, wenn sie die maximale Leerlaufzeit überschritten haben oder wenn die Anzahl der vorhandenen **ServicePoint**-Instanzen die maximale Anzahl von **ServicePoint**-Instanzen für die Anwendung überschreitet.</span><span class="sxs-lookup"><span data-stu-id="06b93-111">**ServicePoint** instances are destroyed when they have exceeded their maximum idle time or when the number of existing **ServicePoint** instances exceeds the maximum number of **ServicePoint** instances for the application.</span></span> <span data-ttu-id="06b93-112">Sie können sowohl die maximale Standardleerlaufzeit als auch die maximale Anzahl von **ServicePoint**-Instanzen steuern, indem Sie die <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A>- und <xref:System.Net.ServicePointManager.MaxServicePoints%2A>-Eigenschaften für die **ServicePointManager**-Klasse festlegen.</span><span class="sxs-lookup"><span data-stu-id="06b93-112">You can control both the default maximum idle time and the maximum number of **ServicePoint** instances by setting the <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A> and <xref:System.Net.ServicePointManager.MaxServicePoints%2A> properties on the **ServicePointManager**.</span></span>  
  
 <span data-ttu-id="06b93-113">Die Anzahl der Verbindungen zwischen einem Client und einem Server kann sich drastisch auf den Anwendungsdurchsatz auswirken.</span><span class="sxs-lookup"><span data-stu-id="06b93-113">The number of connections between a client and server can have a dramatic impact on application throughput.</span></span> <span data-ttu-id="06b93-114">Standardmäßig verwendet eine Anwendung, die die <xref:System.Net.HttpWebRequest>-Klasse verwendet, maximal zwei persistente Verbindungen. Sie können die maximale Anzahl von Verbindungen jedoch je nach Anwendung festlegen.</span><span class="sxs-lookup"><span data-stu-id="06b93-114">By default, an application using the <xref:System.Net.HttpWebRequest> class uses a maximum of two persistent connections to a given server, but you can set the maximum number of connections on a per-application basis.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06b93-115">Die HTTP/1.1-Spezifikation beschränkt die Anzahl der Verbindungen von einer Anwendung auf zwei Verbindungen pro Server.</span><span class="sxs-lookup"><span data-stu-id="06b93-115">The HTTP/1.1 specification limits the number of connections from an application to two connections per server.</span></span>  
  
 <span data-ttu-id="06b93-116">Die optimale Anzahl von Verbindungen hängt von den tatsächlichen Bedingungen ab, unter denen die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="06b93-116">The optimum number of connections depends on the actual conditions in which the application runs.</span></span> <span data-ttu-id="06b93-117">Das Erhöhen der Anzahl der verfügbaren Verbindungen für die Anwendung wirkt sich möglicherweise nicht auf die Leistung der Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="06b93-117">Increasing the number of connections available to the application may not affect application performance.</span></span> <span data-ttu-id="06b93-118">Um zu ermitteln, wie sich mehr Verbindungen auswirken, führen Sie Leistungstests durch, wobei Sie die Anzahl von Verbindungen variieren.</span><span class="sxs-lookup"><span data-stu-id="06b93-118">To determine the impact of more connections, run performance tests while varying the number of connections.</span></span> <span data-ttu-id="06b93-119">Sie können die Anzahl der Verbindungen ändern, die von einer Anwendung verwendet werden, indem Sie, wie im folgenden Codebeispiel gezeigt, die statische <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A>-Eigenschaft für die **ServicePointManager**-Klasse bei der Anwendungsinitialisierung ändern.</span><span class="sxs-lookup"><span data-stu-id="06b93-119">You can change the number of connections that an application uses by changing the static <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> property on the **ServicePointManager** class at application initialization, as shown in the following code sample.</span></span>  
  
```csharp  
// Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4;  
```  
  
```vb  
' Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4  
```  
  
 <span data-ttu-id="06b93-120">Das Ändern der **ServicePointManager.DefaultConnectionLimit**-Eigenschaft wirkt sich nicht auf zuvor initialisierte **ServicePoint**-Instanzen aus.</span><span class="sxs-lookup"><span data-stu-id="06b93-120">Changing the **ServicePointManager.DefaultConnectionLimit** property does not affect previously initialized **ServicePoint** instances.</span></span> <span data-ttu-id="06b93-121">Der folgende Code zeigt das Ändern der Verbindungsbeschränkung für eine vorhandene **ServicePoint**-Klasse für den Server `http://www.contoso.com` in den in `newLimit` gespeicherten Wert.</span><span class="sxs-lookup"><span data-stu-id="06b93-121">The following code demonstrates changing the connection limit on an existing **ServicePoint** for the server `http://www.contoso.com` to the value stored in `newLimit`.</span></span>  
  
```csharp  
Uri uri = new Uri("http://www.contoso.com/");  
ServicePoint sp = ServicePointManager.FindServicePoint(uri);  
sp.ConnectionLimit = newLimit;  
```  
  
```vb  
Dim uri As New Uri("http://www.contoso.com/")  
Dim sp As ServicePoint = ServicePointManager.FindServicePoint(uri)  
sp.ConnectionLimit = newLimit  
```  
  
## <a name="see-also"></a><span data-ttu-id="06b93-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06b93-122">See Also</span></span>  
 [<span data-ttu-id="06b93-123">Connection Grouping (Verbindungsgruppierung)</span><span class="sxs-lookup"><span data-stu-id="06b93-123">Connection Grouping</span></span>](../../../docs/framework/network-programming/connection-grouping.md)  
 [<span data-ttu-id="06b93-124">Verwenden von Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="06b93-124">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
