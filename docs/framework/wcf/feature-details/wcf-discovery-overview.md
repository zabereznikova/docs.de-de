---
title: Übersicht über die WCF-Suche
ms.date: 03/30/2017
ms.assetid: 84fad0e4-23b1-45b5-a2d4-c9cdf90bbb22
ms.openlocfilehash: 5876605f5096bfb75c18680faaef4ba0cd15c082
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281416"
---
# <a name="wcf-discovery-overview"></a><span data-ttu-id="c7b79-102">Übersicht über die WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="c7b79-102">WCF Discovery Overview</span></span>

<span data-ttu-id="c7b79-103">Die Such-APIs stellen ein einheitliches Programmiermodell zur dynamischen Veröffentlichung von und zum Suchen nach Webdiensten bereit, wobei das WS-Suchprotokoll verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c7b79-103">The Discovery APIs provide a unified programming model for the dynamic publication and discovery of Web services using the WS-Discovery protocol.</span></span> <span data-ttu-id="c7b79-104">Diese APIs ermöglichen es Diensten, sich selbst zu veröffentlichen, und Client das Suchen nach veröffentlichten Diensten.</span><span class="sxs-lookup"><span data-stu-id="c7b79-104">These APIs allow services to publish themselves and clients to find published services.</span></span> <span data-ttu-id="c7b79-105">Nachdem ein Dienst erkennbar gemacht wurde, kann der Dienst Ankündigungsmeldungen senden sowie eine Überwachung auf Suchanforderungen durchführen und darauf antworten.</span><span class="sxs-lookup"><span data-stu-id="c7b79-105">Once a service is made discoverable, the service has the ability to send announcement messages as well as listen for and respond to discovery requests.</span></span> <span data-ttu-id="c7b79-106">Erkennbare Dienste können Hello-Nachrichten senden, um ihre Ankunft in einem Netzwerk anzukündigen, und Bye-Nachrichten, um das Verlassen eines Netzwerks anzukündigen.</span><span class="sxs-lookup"><span data-stu-id="c7b79-106">Discoverable services can send Hello messages to announce their arrival on a network and Bye messages to announce their departure from a network.</span></span> <span data-ttu-id="c7b79-107">Um nach einem Dienst zu suchen, senden Clients eine `Probe`-Anforderung, die bestimmte Kriterien wie den Dienstvertragstyp, Schlüsselwörter und den Bereich des Netzwerks enthält.</span><span class="sxs-lookup"><span data-stu-id="c7b79-107">To find a service, clients send a `Probe` request that contains specific criteria such as service contract type, keywords, and scope on the network.</span></span> <span data-ttu-id="c7b79-108">Dienste empfangen die `Probe`-Anforderung und bestimmen, ob diese den Kriterien entspricht.</span><span class="sxs-lookup"><span data-stu-id="c7b79-108">Services receive the `Probe` request and determine whether they match the criteria.</span></span> <span data-ttu-id="c7b79-109">Wenn sich für einen Dienst eine Übereinstimmung ergibt, antwortet dieser mit dem Rücksenden einer `ProbeMatch`-Nachricht an den Client, in der die Informationen für die Kontaktaufnahme mit dem Dienst enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="c7b79-109">If a service matches, it responds by sending a `ProbeMatch` message back to the client with the information necessary to contact the service.</span></span> <span data-ttu-id="c7b79-110">Clients können auch `Resolve`-Anforderungen senden, mit deren Hilfe sie nach Diensten suchen können, die ggf. ihre Endpunktadresse geändert haben.</span><span class="sxs-lookup"><span data-stu-id="c7b79-110">Clients can also send `Resolve` requests that allow them to find services that may have changed their endpoint address.</span></span> <span data-ttu-id="c7b79-111">Dienste, die Übereinstimmungen ergeben, antworten auf `Resolve`-Anforderungen, indem sie eine `ResolveMatch`-Nachricht zurück an den Client senden.</span><span class="sxs-lookup"><span data-stu-id="c7b79-111">Matching services respond to `Resolve` requests by sending a `ResolveMatch` message back to the client.</span></span>  
  
## <a name="ad-hoc-and-managed-modes"></a><span data-ttu-id="c7b79-112">Ad-hoc-Modus und verwalteter Modus</span><span class="sxs-lookup"><span data-stu-id="c7b79-112">Ad-Hoc and Managed Modes</span></span>  

 <span data-ttu-id="c7b79-113">Die Such-API unterstützt zwei verschiedene Modi: Verwaltet und Ad-hoc.</span><span class="sxs-lookup"><span data-stu-id="c7b79-113">The Discovery API supports two different modes: Managed and Ad-Hoc.</span></span> <span data-ttu-id="c7b79-114">Im Modus "Verwaltet" wird ein zentralisierter Server verwendet, der als Suchproxy bezeichnet wird und Informationen zu verfügbaren Diensten verwaltet.</span><span class="sxs-lookup"><span data-stu-id="c7b79-114">In Managed mode there is a centralized server called a discovery proxy that maintains information about available services.</span></span> <span data-ttu-id="c7b79-115">Der Suchproxy auf verschiedene Arten mit Informationen zu Diensten aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="c7b79-115">The discovery proxy can be populated with information about services in a variety of ways.</span></span> <span data-ttu-id="c7b79-116">Dienste können z. B. während des Starts Ankündigungsmeldungen an den Suchproxy senden, oder der Proxy kann Daten aus einer Datenbank oder einer Konfigurationsdatei lesen, um zu ermitteln, welche Dienste verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c7b79-116">For example, services can send announcement messages during start up to the discovery proxy or the proxy may read data from a database or a configuration file to determine what services are available.</span></span> <span data-ttu-id="c7b79-117">Die Art und Weise, wie der Suchproxy aufgefüllt wird, hängt vollständig vom Entwickler ab.</span><span class="sxs-lookup"><span data-stu-id="c7b79-117">How the discovery proxy is populated is completely up to the developer.</span></span> <span data-ttu-id="c7b79-118">Clients verwenden den Suchproxy zum Abrufen von Informationen zu verfügbaren Diensten.</span><span class="sxs-lookup"><span data-stu-id="c7b79-118">Clients use the discovery proxy to retrieve information about available services.</span></span> <span data-ttu-id="c7b79-119">Wenn ein Client nach einem Dienst sucht, sendet er eine `Probe`-Nachricht an den Suchproxy, und der Proxy ermittelt dann, ob einer der bekannten Dienste mit dem Dienst übereinstimmt, nach dem der Client sucht.</span><span class="sxs-lookup"><span data-stu-id="c7b79-119">When a client searches for a service it sends a `Probe` message to the discovery proxy and the proxy determines whether any of the services it knows about match the service the client is searching for.</span></span> <span data-ttu-id="c7b79-120">Wenn Übereinstimmungen vorhanden sind, sendet der Suchproxy eine `ProbeMatch`-Antwort zurück an den Client.</span><span class="sxs-lookup"><span data-stu-id="c7b79-120">If there are matches the discovery proxy sends a `ProbeMatch` response back to the client.</span></span> <span data-ttu-id="c7b79-121">Der Client kann sich dann direkt an den Dienst wenden, indem er die vom Proxy zurückgegebenen Dienstinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c7b79-121">The client can then contact the service directly using the service information returned from the proxy.</span></span> <span data-ttu-id="c7b79-122">Das Hauptprinzip hinter dem Modus "Verwaltet" beruht darauf, dass die Suchanforderungen im Unicast-Format an eine Autorität, den Suchproxy, gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c7b79-122">The key principle behind Managed mode is that the discovery requests are sent in a unicast manner to one authority, the discovery proxy.</span></span> <span data-ttu-id="c7b79-123">.NET Framework enthält Hauptkomponenten, mit denen Sie einen eigenen Proxy erstellen können.</span><span class="sxs-lookup"><span data-stu-id="c7b79-123">The .NET Framework contains key components that allow you to build your own proxy.</span></span> <span data-ttu-id="c7b79-124">Es gibt für Clients und Dienste mehrere Methoden, nach dem Proxy zu suchen:</span><span class="sxs-lookup"><span data-stu-id="c7b79-124">Clients and services can locate the proxy by multiple methods:</span></span>  
  
- <span data-ttu-id="c7b79-125">Der Proxy kann auf Ad-hoc-Nachrichten reagieren.</span><span class="sxs-lookup"><span data-stu-id="c7b79-125">The proxy can respond to ad-hoc messages.</span></span>  
  
- <span data-ttu-id="c7b79-126">Der Proxy kann während des Startvorgangs eine Ankündigungsnachricht senden.</span><span class="sxs-lookup"><span data-stu-id="c7b79-126">The proxy can send an announcement message during start up.</span></span>  
  
- <span data-ttu-id="c7b79-127">Es können Clients und Dienste geschrieben werden, um nach einem bestimmten bekannten Endpunkt zu suchen.</span><span class="sxs-lookup"><span data-stu-id="c7b79-127">Clients and services can be written to look for a specific well-known endpoint.</span></span>  
  
 <span data-ttu-id="c7b79-128">Im Ad-hoc-Modus gibt es keinen zentralisierten Server.</span><span class="sxs-lookup"><span data-stu-id="c7b79-128">In Ad-Hoc mode, there is no centralized server.</span></span> <span data-ttu-id="c7b79-129">Alle Suchnachrichten, z. B. Dienstankündigungen und Clientanforderungen, werden im Multicast-Format gesendet.</span><span class="sxs-lookup"><span data-stu-id="c7b79-129">All discovery messages such as service announcements and client requests are sent in a multicast fashion.</span></span> <span data-ttu-id="c7b79-130">Standardmäßig enthält .NET Framework Unterstützung für die Ad-hoc-Suche über das UDP-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="c7b79-130">By default the .NET Framework contains support for Ad-Hoc discovery over the UDP protocol.</span></span> <span data-ttu-id="c7b79-131">Wenn ein Dienst z. B. konfiguriert wird, um während des Startvorgangs eine Hello-Ankündigung zu senden, erfolgt das Senden über eine bekannte Multicastadresse und das UDP-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="c7b79-131">For example, if a service is configured to send out a Hello announcement on start up, it sends it out over a well-known, multicast address using the UDP protocol.</span></span> <span data-ttu-id="c7b79-132">Clients müssen über eine aktive Überwachung auf diese Ankündigungen verfügen und diese entsprechend verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c7b79-132">Clients have to actively listen for these announcements and process them accordingly.</span></span> <span data-ttu-id="c7b79-133">Wenn ein Client eine `Probe`-Nachricht für einen Dienst sendet, wird diese mit einem Multicastprotokoll über das Netzwerk übertragen.</span><span class="sxs-lookup"><span data-stu-id="c7b79-133">When a client sends a `Probe` message for a service it is sent over the network using a multicast protocol.</span></span> <span data-ttu-id="c7b79-134">Jeder Dienst, der die Anforderung empfängt, ermittelt, ob diese mit den Kriterien der `Probe`-Nachricht übereinstimmt. Anschließend antwortet der jeweilige Dienst dem Client direkt mit einer `ProbeMatch`-Nachricht, falls sich für den Dienst eine Übereinstimmung mit den Kriterien ergibt, die in der `Probe`-Nachricht angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="c7b79-134">Each service that receives the request determines whether it matches the criteria in the `Probe` message and responds directly to the client with a `ProbeMatch` message if the service matches the criteria specified in the `Probe` message.</span></span>  
  
## <a name="benefits-of-using-wcf-discovery"></a><span data-ttu-id="c7b79-135">Vorteile der WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="c7b79-135">Benefits of Using WCF Discovery</span></span>  

 <span data-ttu-id="c7b79-136">Da die WCF-Suche mit dem WS-Discovery-Protokoll implementiert wird, besteht Interoperabilität mit anderen Clients, Diensten und Proxys, die WS-Discovery ebenfalls implementieren.</span><span class="sxs-lookup"><span data-stu-id="c7b79-136">Because WCF Discovery is implemented using the WS-Discovery protocol it is interoperable with other clients, services, and proxies that implement WS-Discovery as well.</span></span> <span data-ttu-id="c7b79-137">Die WCF-Suche basiert auf den vorhandenen WCF-APIs, sodass Sie den vorhandenen Diensten und den Clients auf einfache Weise Suchfunktionalität hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="c7b79-137">WCF Discovery is built upon the existing WCF APIs, which makes it easy to add Discovery functionality to your existing services and clients.</span></span> <span data-ttu-id="c7b79-138">Sie können die Auffindbarkeit von Diensten einfach über die Anwendungskonfigurationseinstellungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c7b79-138">Service discoverability can be easily added through the application configuration settings.</span></span> <span data-ttu-id="c7b79-139">Außerdem unterstützt die WCF-Suche die Verwendung des Suchprotokolls über andere Transporte wie Peernetzwerk, Namens-Overlay und HTTP.</span><span class="sxs-lookup"><span data-stu-id="c7b79-139">In addition, WCF Discovery also supports using the discovery protocol over other transports such as peer net, naming overlay, and HTTP.</span></span> <span data-ttu-id="c7b79-140">Die WCF-Suche unterstützt den Modus "Verwaltet", in dem ein Suchproxy verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c7b79-140">WCF Discovery provides support for a Managed mode of operation where a discovery proxy is used.</span></span> <span data-ttu-id="c7b79-141">So kann der Netzwerkverkehr reduziert werden, weil Nachrichten direkt an den Suchproxy gesendet werden, und es werden keine Multicastnachrichten an das gesamte Netzwerk gesendet.</span><span class="sxs-lookup"><span data-stu-id="c7b79-141">This can reduce network traffic as messages are sent directly to the discovery proxy instead of sending multicast messages to the entire network.</span></span> <span data-ttu-id="c7b79-142">Beim Arbeiten mit Webdiensten ermöglicht die WCF-Suche zudem mehr Flexibilität.</span><span class="sxs-lookup"><span data-stu-id="c7b79-142">WCF Discovery also allows for more flexibility when working with Web services.</span></span> <span data-ttu-id="c7b79-143">Sie können z. B. die Adresse eines Diensts ändern, ohne den Client oder den Dienst neu konfigurieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="c7b79-143">For example, you can change the address of a service without having to reconfigure the client or the service.</span></span> <span data-ttu-id="c7b79-144">Wenn ein Client auf den Dienst zugreifen muss, kann er über eine `Probe`-Anforderung eine `Find`-Nachricht ausgeben. Er erwartet dann, dass der Dienst mit seiner aktuellen Adresse antwortet.</span><span class="sxs-lookup"><span data-stu-id="c7b79-144">When a client must access the service it can issue a `Probe` message through a `Find` request and expect the service to respond with its current address.</span></span> <span data-ttu-id="c7b79-145">Mit der WCF-Suche kann ein Client anhand unterschiedlicher Kriterien, wie Vertragstypen, Bindungselemente, Namespace, Bereich und Schlüsselwörter oder Versionsnummern, nach einem Dienst suchen.</span><span class="sxs-lookup"><span data-stu-id="c7b79-145">WCF Discovery allows a client to search for a service based on different criteria including contract types, binding elements, namespace, scope, and keywords or version numbers.</span></span> <span data-ttu-id="c7b79-146">Die WCF-Suche ermöglicht die Suche zur Laufzeit und zur Entwurfszeit.</span><span class="sxs-lookup"><span data-stu-id="c7b79-146">WCF Discovery enables runtime and design time discovery.</span></span> <span data-ttu-id="c7b79-147">Das Hinzufügen der Suchfunktion zu einer Anwendung ermöglicht weitere Szenarien, z. B. Fehlertoleranz und automatische Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="c7b79-147">Adding discovery to your application can be used to enable other scenarios such as fault tolerance and auto configuration.</span></span>  
  
## <a name="service-publication"></a><span data-ttu-id="c7b79-148">Dienstveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="c7b79-148">Service Publication</span></span>  

 <span data-ttu-id="c7b79-149">Um einen Dienst erkennbar zu machen, müssen Sie dem Diensthost ein <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> hinzufügen. Außerdem müssen Sie einen Suchendpunkt hinzufügen, um anzugeben, welche Komponenten auf Suchnachrichten überwacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c7b79-149">To make a service discoverable, a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> must be added to the service host and a discovery endpoint must be added to specify where to listen for discovery messages.</span></span> <span data-ttu-id="c7b79-150">Im folgenden Codebeispiel wird gezeigt, wie Sie einen selbst gehosteten Dienst ändern können, um diesen erkennbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="c7b79-150">The following code example shows how a self-hosted service can be modified to make it discoverable.</span></span>  
  
```csharp  
Uri baseAddress = new Uri($"http://{System.Net.Dns.GetHostName()}:8000/discovery/scenarios/calculatorservice/{Guid.NewGuid().ToString()}/");

// Create a ServiceHost for the CalculatorService type.
using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))
{
    // Add calculator endpoint
    serviceHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), string.Empty);

    // ** DISCOVERY ** //
    // Make the service discoverable by adding the discovery behavior
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());

    // ** DISCOVERY ** //
    // Add the discovery endpoint that specifies where to publish the services
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());

    // Open the ServiceHost to create listeners and start listening for messages.
    serviceHost.Open();

    // The service can now be accessed.
    Console.WriteLine("Press <ENTER> to terminate service.");
    Console.ReadLine();
}
```  
  
 <span data-ttu-id="c7b79-151">Einer Dienstbeschreibung muss eine <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>-Instanz hinzugefügt werden, damit der Dienst erkennbar ist.</span><span class="sxs-lookup"><span data-stu-id="c7b79-151">A <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> instance must be added to a service description for the service to be discoverable.</span></span> <span data-ttu-id="c7b79-152">Dem Diensthost muss eine <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>-Instanz hinzugefügt werden, um dem Dienst mitzuteilen, welche Komponenten auf Suchanforderungen überwacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c7b79-152">A <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instance must be added to the service host to tell the service where to listen for discovery requests.</span></span> <span data-ttu-id="c7b79-153">In diesem Beispiel wird ein <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> (von <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> abgeleitet) hinzugefügt, um anzugeben, dass der Dienst die Überwachung über den UDP-Multicasttransport durchführen soll.</span><span class="sxs-lookup"><span data-stu-id="c7b79-153">In this example, a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> (which is derived from <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>) is added to specify that the service should listen for discovery requests over the UDP multicast transport.</span></span> <span data-ttu-id="c7b79-154">Der <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> wird für die Ad-hoc-Suche verwendet, weil alle Nachrichten im Multicast-Format gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c7b79-154">The <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> is used for Ad-Hoc discovery because all messages are sent in a multicast fashion.</span></span>  
  
## <a name="announcement"></a><span data-ttu-id="c7b79-155">Ankündigung</span><span class="sxs-lookup"><span data-stu-id="c7b79-155">Announcement</span></span>  

 <span data-ttu-id="c7b79-156">Bei der Dienstveröffentlichung werden standardmäßig keine Ankündigungsnachrichten gesendet.</span><span class="sxs-lookup"><span data-stu-id="c7b79-156">By default, service publication does not send out announcement messages.</span></span> <span data-ttu-id="c7b79-157">Der Dienst muss so konfiguriert werden, dass er Ankündigungsnachrichten sendet.</span><span class="sxs-lookup"><span data-stu-id="c7b79-157">The service must be configured to send out announcement messages.</span></span> <span data-ttu-id="c7b79-158">Dadurch können Dienstwriter flexibler arbeiten, weil sie den Dienst getrennt von der Überwachung auf Suchnachrichten ankündigen können.</span><span class="sxs-lookup"><span data-stu-id="c7b79-158">This provides additional flexibility for service writers because they can announce the service separately from listening for discovery messages.</span></span> <span data-ttu-id="c7b79-159">Die Dienstankündigung kann auch als Mechanismus zum Registrieren von Diensten bei einem Suchproxy oder anderen Dienstregistrierungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c7b79-159">Service announcement can also be used as a mechanism for registering services with a discovery proxy or other service registries.</span></span> <span data-ttu-id="c7b79-160">Im folgenden Code wird gezeigt, wie Sie einen Dienst zum Senden von Ankündigungsnachrichten über eine UDP-Bindung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c7b79-160">The following code shows how to configure a service to send announcement messages over a UDP binding.</span></span>  
  
```csharp  
Uri baseAddress = new Uri($"http://{System.Net.Dns.GetHostName()}:8000/discovery/scenarios/calculatorservice/{Guid.NewGuid().ToString()}/");

// Create a ServiceHost for the CalculatorService type.
using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))
{
    // Add calculator endpoint
    serviceHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), string.Empty);

    // ** DISCOVERY ** //
    // Make the service discoverable by adding the discovery behavior
    ServiceDiscoveryBehavior discoveryBehavior = new ServiceDiscoveryBehavior();
    serviceHost.Description.Behaviors.Add(discoveryBehavior);

    // Send announcements on UDP multicast transport
    discoveryBehavior.AnnouncementEndpoints.Add(
      new UdpAnnouncementEndpoint());

    // ** DISCOVERY ** //
    // Add the discovery endpoint that specifies where to publish the services
    serviceHost.Description.Endpoints.Add(new UdpDiscoveryEndpoint());

    // Open the ServiceHost to create listeners and start listening for messages.
    serviceHost.Open();

    // The service can now be accessed.
    Console.WriteLine("Press <ENTER> to terminate service.");
    Console.ReadLine();
}
```  
  
## <a name="service-discovery"></a><span data-ttu-id="c7b79-161">Dienstsuche</span><span class="sxs-lookup"><span data-stu-id="c7b79-161">Service Discovery</span></span>  

 <span data-ttu-id="c7b79-162">Eine Clientanwendung kann die <xref:System.ServiceModel.Discovery.DiscoveryClient>-Klasse verwenden, um nach Diensten zu suchen.</span><span class="sxs-lookup"><span data-stu-id="c7b79-162">A client application can use the <xref:System.ServiceModel.Discovery.DiscoveryClient> class to find services.</span></span> <span data-ttu-id="c7b79-163">Der Entwickler erstellt eine Instanz der <xref:System.ServiceModel.Discovery.DiscoveryClient>-Klasse, die einen Suchendpunkt übergibt. Der Suchendpunkt gibt an, wohin `Probe`- oder `Resolve`-Nachrichten gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c7b79-163">The developer creates an instance of the <xref:System.ServiceModel.Discovery.DiscoveryClient> class that passes in a discovery endpoint that specifies where to send `Probe` or `Resolve` messages.</span></span> <span data-ttu-id="c7b79-164">Der Client ruft dann die <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>-Methode auf, die die Suchkriterien innerhalb einer <xref:System.ServiceModel.Discovery.FindCriteria>-Instanz angibt.</span><span class="sxs-lookup"><span data-stu-id="c7b79-164">The client then calls <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> that specifies search criteria within a <xref:System.ServiceModel.Discovery.FindCriteria> instance.</span></span> <span data-ttu-id="c7b79-165">Wenn übereinstimmende Dienste gefunden werden, gibt <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> eine Auflistung von <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> zurück.</span><span class="sxs-lookup"><span data-stu-id="c7b79-165">If matching services are found, <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> returns a collection of <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>.</span></span> <span data-ttu-id="c7b79-166">Der folgende Code zeigt, wie sie die `Find`-Methode aufrufen und dann eine Verbindung zu einem ermittelten Dienst herstellen.</span><span class="sxs-lookup"><span data-stu-id="c7b79-166">The following code shows how to call the `Find` method and then connect to a discovered service.</span></span>  
  
```csharp  
class Client
{
    static EndpointAddress serviceAddress;
  
    static void Main()
    {  
        if (FindService())
        {
            InvokeService();
        }
    }  
  
    // ** DISCOVERY ** //  
    static bool FindService()  
    {  
        Console.WriteLine("\nFinding Calculator Service ..");  
        DiscoveryClient discoveryClient =
            new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
        Collection<EndpointDiscoveryMetadata> calculatorServices =
            (Collection<EndpointDiscoveryMetadata>)discoveryClient.Find(new FindCriteria(typeof(ICalculator))).Endpoints;  
  
        discoveryClient.Close();  
  
        if (calculatorServices.Count == 0)  
        {  
            Console.WriteLine("\nNo services are found.");  
            return false;  
        }  
        else  
        {  
            serviceAddress = calculatorServices[0].Address;  
            return true;  
        }  
    }  
  
    static void InvokeService()  
    {  
        Console.WriteLine("\nInvoking Calculator Service at {0}\n", serviceAddress);  
  
        // Create a client  
        CalculatorClient client = new CalculatorClient();  
        client.Endpoint.Address = serviceAddress;  
        client.Add(10,3);  
    }
}  
```  
  
## <a name="discovery-and-message-level-security"></a><span data-ttu-id="c7b79-167">Sicherheit der Such- und Nachrichtenebene</span><span class="sxs-lookup"><span data-stu-id="c7b79-167">Discovery and Message Level Security</span></span>  

 <span data-ttu-id="c7b79-168">Beim Verwenden der Nachrichtenebenensicherheit müssen Sie auf dem Dienstsuchendpunkt ein <xref:System.ServiceModel.EndpointIdentity>-Objekt und auf dem Clientsuchendpunkt ein passendes <xref:System.ServiceModel.EndpointIdentity>-Objekt angeben.</span><span class="sxs-lookup"><span data-stu-id="c7b79-168">When using message level security it is necessary to specify an <xref:System.ServiceModel.EndpointIdentity> on the service discovery endpoint and a matching <xref:System.ServiceModel.EndpointIdentity> on the client discovery endpoint.</span></span> <span data-ttu-id="c7b79-169">Weitere Informationen zur Sicherheit auf Nachrichten Ebene finden Sie unter [Nachrichten Sicherheit](message-security-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="c7b79-169">For more information about message level security, see [Message Security](message-security-in-wcf.md).</span></span>  
  
## <a name="discovery-and-web-hosted-services"></a><span data-ttu-id="c7b79-170">Suche und im Internet gehostete Dienste</span><span class="sxs-lookup"><span data-stu-id="c7b79-170">Discovery and Web Hosted Services</span></span>  

 <span data-ttu-id="c7b79-171">Damit WCF-Dienste erkennbar sind, müssen sie derzeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c7b79-171">In order for WCF services to be discoverable they must be running.</span></span> <span data-ttu-id="c7b79-172">Unter IIS oder WAS gehostete WCF-Dienste werden erst ausgeführt, wenn IIS/WAS eine Meldung für den Dienst empfängt. Daher sind sie nicht standardmäßig erkennbar.</span><span class="sxs-lookup"><span data-stu-id="c7b79-172">WCF services hosted under IIS or WAS do not run until IIS/WAS receives a message bound for the service, so they cannot be discoverable by default.</span></span>  <span data-ttu-id="c7b79-173">Es gibt zwei Möglichkeiten, im Internet gehostete Dienste als erkennbar festzulegen:</span><span class="sxs-lookup"><span data-stu-id="c7b79-173">There are two options for making Web-Hosted services discoverable:</span></span>  
  
1. <span data-ttu-id="c7b79-174">Verwenden der Autostart-Funktion von Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="c7b79-174">Use the Windows Server AppFabric Auto-Start feature</span></span>  
  
2. <span data-ttu-id="c7b79-175">Verwenden eines Suchproxys zur Kommunikation im Namen des Diensts</span><span class="sxs-lookup"><span data-stu-id="c7b79-175">Use a discovery proxy to communicate on behalf of the service</span></span>  
  
 <span data-ttu-id="c7b79-176">Windows Server AppFabric verfügt über eine Autostart-Funktion, mit der ein Dienst gestartet werden kann, bevor Meldungen empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="c7b79-176">Windows Server AppFabric has an Auto-Start feature that will allow a service to be started before receiving any messages.</span></span> <span data-ttu-id="c7b79-177">Wenn die Autostart-Funktion festgelegt ist, kann ein von IIS/WAS gehosteter Dienst als erkennbar konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="c7b79-177">With this Auto-Start set, an IIS/WAS hosted service can be configured to be discoverable.</span></span> <span data-ttu-id="c7b79-178">Weitere Informationen zur automatischen Start Funktion finden Sie unter [Windows Server AppFabric Autostart Feature](/previous-versions/appfabric/ee677260(v=azure.10)).</span><span class="sxs-lookup"><span data-stu-id="c7b79-178">For more information about the Auto-Start feature see, [Windows Server AppFabric Auto-Start Feature](/previous-versions/appfabric/ee677260(v=azure.10)).</span></span> <span data-ttu-id="c7b79-179">Wenn Sie die Autostart-Funktion aktivieren, müssen Sie den Dienst für die Suche konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c7b79-179">Along with turning on the Auto-Start feature, you must configure the service for discovery.</span></span> <span data-ttu-id="c7b79-180">Weitere Informationen finden Sie unter Gewusst [wie: Programm gesteuertes hinzufügen der Auffindbarkeit zu einem WCF-Dienst und Client](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)[Konfigurieren der Ermittlung in einer Konfigurationsdatei](configuring-discovery-in-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="c7b79-180">For more information, see [How to: Programmatically Add Discoverability to a WCF Service and Client](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)[Configuring Discovery in a Configuration File](configuring-discovery-in-a-configuration-file.md).</span></span>  
  
 <span data-ttu-id="c7b79-181">Ein Suchproxy kann verwendet werden, um im Namen des WCF-Diensts zu kommunizieren, wenn der Dienst nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c7b79-181">A discovery proxy can be used to communicate on behalf of the WCF service when the service is not running.</span></span> <span data-ttu-id="c7b79-182">Der Proxy kann Überprüfungs- oder Auflösungsmeldungen abhören und dem Client antworten.</span><span class="sxs-lookup"><span data-stu-id="c7b79-182">The proxy can listen for probe or resolve messages and respond to the client.</span></span> <span data-ttu-id="c7b79-183">Anschließend kann der Client Meldungen direkt an den Dienst senden.</span><span class="sxs-lookup"><span data-stu-id="c7b79-183">The client can then send messages directly to the service.</span></span> <span data-ttu-id="c7b79-184">Wenn der Client eine Meldung an den Dienst sendet, wird dieser instanziiert, um auf die Meldung zu antworten.</span><span class="sxs-lookup"><span data-stu-id="c7b79-184">When the client sends a message to the service it will be instantiated to respond to the message.</span></span> <span data-ttu-id="c7b79-185">Weitere Informationen zum Implementieren eines Ermittlungs Proxys finden Sie unter [Implementieren eines Ermittlungs Proxys](implementing-a-discovery-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="c7b79-185">For more information about implementing a discovery proxy see, [Implementing a Discovery Proxy](implementing-a-discovery-proxy.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7b79-186">Damit die WCF-Ermittlung ordnungsgemäß funktioniert, sollten alle NICs (Netzwerkschnittstellen Controller) nur eine IP-Adresse aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c7b79-186">For WCF Discovery to work correctly, all NICs (Network Interface Controller) should only have 1 IP address.</span></span>
