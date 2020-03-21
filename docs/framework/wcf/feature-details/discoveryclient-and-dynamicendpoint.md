---
title: DiscoveryClient und DynamicEndpoint
ms.date: 03/30/2017
ms.assetid: 7cd418f0-0eab-48d1-a493-7eb907867ec3
ms.openlocfilehash: c6d87a04a6787725ad7c4546650485af932882b0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185179"
---
# <a name="discoveryclient-and-dynamicendpoint"></a><span data-ttu-id="8f459-102">DiscoveryClient und DynamicEndpoint</span><span class="sxs-lookup"><span data-stu-id="8f459-102">DiscoveryClient and DynamicEndpoint</span></span>
<span data-ttu-id="8f459-103"><xref:System.ServiceModel.Discovery.DiscoveryClient> und <xref:System.ServiceModel.Discovery.DynamicEndpoint> sind zwei Klassen, die auf der Clientseite zum Suchen nach Diensten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8f459-103"><xref:System.ServiceModel.Discovery.DiscoveryClient> and <xref:System.ServiceModel.Discovery.DynamicEndpoint> are two classes used on the client side to search for services.</span></span> <span data-ttu-id="8f459-104"><xref:System.ServiceModel.Discovery.DiscoveryClient> stellt eine Liste der Dienste bereit, die bestimmten Kriterien entsprechen, und ermöglicht Ihnen das Herstellen einer Verbindung mit den Diensten.</span><span class="sxs-lookup"><span data-stu-id="8f459-104"><xref:System.ServiceModel.Discovery.DiscoveryClient> provides you with a list of services that match a specific set of criteria and allows you to connect to the services.</span></span> <span data-ttu-id="8f459-105"><xref:System.ServiceModel.Discovery.DynamicEndpoint> führt den gleichen Vorgang aus und stellt zusätzlich eine Verbindung mit einem der gefundenen Dienste her.</span><span class="sxs-lookup"><span data-stu-id="8f459-105"><xref:System.ServiceModel.Discovery.DynamicEndpoint> performs the same operation and in addition, automatically connects to one of the services that was found.</span></span> <span data-ttu-id="8f459-106">Jeder Endpunkt kann als <xref:System.ServiceModel.Discovery.DynamicEndpoint> festgelegt werden, und die Suchkriterien können auch in der Konfiguration hinzugefügt werden. <xref:System.ServiceModel.Discovery.DynamicEndpoint> ist hilfreich, wenn Sie die Suche in der Projektmappe benötigen, die Clientlogik jedoch nicht ändern möchten – Sie müssen nur die Endpunkte ändern.</span><span class="sxs-lookup"><span data-stu-id="8f459-106">Any endpoint can be made into a <xref:System.ServiceModel.Discovery.DynamicEndpoint>, the search criteria can also be added in configuration, thus <xref:System.ServiceModel.Discovery.DynamicEndpoint> is useful when you need discovery in your solution but do not want to modify the client logic – you only need to modify the endpoints.</span></span> <span data-ttu-id="8f459-107"><xref:System.ServiceModel.Discovery.DiscoveryClient> bietet Ihnen jedoch eine präzisere Steuerung des Suchvorgangs.</span><span class="sxs-lookup"><span data-stu-id="8f459-107"><xref:System.ServiceModel.Discovery.DiscoveryClient> on the other hand can be used to gain finer control over your search operation.</span></span> <span data-ttu-id="8f459-108">Die Verwendungsmöglichkeiten und Vorteile der Klassen werden unten näher beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8f459-108">The uses and benefits of each are elaborated below.</span></span>  
  
## <a name="discoveryclient"></a><span data-ttu-id="8f459-109">DiscoveryClient</span><span class="sxs-lookup"><span data-stu-id="8f459-109">DiscoveryClient</span></span>  
 <span data-ttu-id="8f459-110">Der <xref:System.ServiceModel.Discovery.DiscoveryClient> definiert synchrone und asynchrone Find-Methoden wie <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted>- und <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged>-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="8f459-110">The <xref:System.ServiceModel.Discovery.DiscoveryClient> defines synchronous and asynchronous Find methods, <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> and <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> events.</span></span>  <span data-ttu-id="8f459-111">Er definiert außerdem synchrone und asynchrone Resolve-Methoden und ein <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveCompleted>-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="8f459-111">It also defines synchronous and asynchronous Resolve methods and a <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveCompleted> event.</span></span> <span data-ttu-id="8f459-112">Verwenden Sie die Methode <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> oder <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> zum Suchen nach Diensten.</span><span class="sxs-lookup"><span data-stu-id="8f459-112">Use the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> or <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> methods to search for services.</span></span> <span data-ttu-id="8f459-113">Beide Methoden verwenden eine <xref:System.ServiceModel.Discovery.FindCriteria>-Instanz, über die Sie Folgendes angeben können: Vertragstypnamen, Bereiche, maximale Anzahl an angeforderten Ergebnissen und die Übereinstimmungsregeln für Bereiche.</span><span class="sxs-lookup"><span data-stu-id="8f459-113">Both of these methods take a <xref:System.ServiceModel.Discovery.FindCriteria> instance that allows you to specify contract type names, scopes, maximum number of results requested, and scope matching rules.</span></span> <span data-ttu-id="8f459-114">Beim Aufruf der <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted>-Methode können das <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged>-Ereignis und das <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A>-Ereignis verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8f459-114">The <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> and <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> events can be used when calling the <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> method.</span></span> <span data-ttu-id="8f459-115"><xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> wird immer ausgelöst, wenn der <xref:System.ServiceModel.Discovery.DiscoveryClient> eine Antwort von einem Dienst empfängt.</span><span class="sxs-lookup"><span data-stu-id="8f459-115"><xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> is fired whenever the <xref:System.ServiceModel.Discovery.DiscoveryClient> receives a response from a service.</span></span> <span data-ttu-id="8f459-116">Es kann verwendet werden, um eine Statusanzeige anzuzeigen, die den Status des Suchvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="8f459-116">It can be used to display a progress bar showing the progress of the find operation.</span></span> <span data-ttu-id="8f459-117">Außerdem kann es verwendet werden, um auf empfangene Suchantworten zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="8f459-117">It can also be used to act on find responses as they are received.</span></span> <span data-ttu-id="8f459-118">Das <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted>-Ereignis wird nach Abschluss des Suchvorgangs ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="8f459-118">The <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> event is fired when the find operation completes.</span></span> <span data-ttu-id="8f459-119">Dies kann der Fall sein, weil die maximale Anzahl von Antworten empfangen wurde oder wenn der unter <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> festgelegte Zeitraum verstrichen ist.</span><span class="sxs-lookup"><span data-stu-id="8f459-119">This may happen because the maximum number of responses has been received or if the <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> has elapsed.</span></span> <span data-ttu-id="8f459-120">Nachdem der Suchvorgang abgeschlossen wurde, werden die Ergebnisse in einer <xref:System.ServiceModel.Discovery.FindResponse>-Instanz zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8f459-120">When the find operation completes the results are returned in a <xref:System.ServiceModel.Discovery.FindResponse> instance.</span></span> <span data-ttu-id="8f459-121"><xref:System.ServiceModel.Discovery.FindResponse> enthält eine Auflistung von <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> mit den Adressen, Vertragstypnamen, Erweiterungen, Abhör-URIs und Bereichen der übereinstimmenden Dienste.</span><span class="sxs-lookup"><span data-stu-id="8f459-121">The <xref:System.ServiceModel.Discovery.FindResponse> contains a collection of <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> which contains the addresses, contract type names, extensions, listen URIs, and scopes of the matching services.</span></span> <span data-ttu-id="8f459-122">Sie können diese Informationen dann verwenden, um eine Verbindung zu einem der übereinstimmenden Dienste herzustellen und diesen aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="8f459-122">You can then use this information to connect to and call one of the matching services.</span></span> <span data-ttu-id="8f459-123">Das folgende Beispiel zeigt, wie Sie die System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria)-Methode aufrufen und die zurückgegebenen Metadaten verwenden, um den gefundenen Dienst aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="8f459-123">The following example shows how to call the System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria) method and use the returned metadata to call the found service.</span></span> <span data-ttu-id="8f459-124">Ein Vorteil <xref:System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria)> der Verwendung besteht darin, dass Sie die Liste der gefundenen Endpunkte zwischenspeichern und zu einem späteren Zeitpunkt verwenden können.</span><span class="sxs-lookup"><span data-stu-id="8f459-124">A benefit of using <xref:System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria)> is that you can cache the list of endpoints you’ve found and use them at a later time.</span></span> <span data-ttu-id="8f459-125">Mit diesem Cache können Sie eine benutzerdefinierte Logik zur Behandlung verschiedener Fehlerbedingungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="8f459-125">With this cache, you can build custom logic to handle various failure conditions.</span></span>  
  
```csharp
DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
FindCriteria criteria = new FindCriteria(typeof(ICalculatorService));  
FindResponse fr = dc.Find(criteria);  
  
if (fr.Endpoints.Count > 0)  
{  
   EndpointAddress ep = fr.Endpoints[0].Address;  
   CalculatorServiceClient client = new CalculatorServiceClient();  
  
    // Connect to the discovered service endpoint  
   client.Endpoint.Address = endpointAddress;  
   Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress);  
  
   double value1 = 100.00D;  
   double value2 = 15.99D;  
  
   // Call the Add service operation.  
   double result = client.Add(value1, value2);  
   Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
}  
else  
   Console.WriteLine("No matching endpoints found");  
```  
  
 <span data-ttu-id="8f459-126">Das folgende Beispiel zeigt, wie Sie einen Suchvorgang asynchron ausführen.</span><span class="sxs-lookup"><span data-stu-id="8f459-126">The following example shows how to perform a find operation asynchronously.</span></span>  
  
```csharp
static void FindServiceAsync()  
{  
   DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());
   dc.FindCompleted += new EventHandler<FindCompletedEventArgs>( discoveryClient_FindCompleted);  
   dc.FindProgressChanged += new EventHandler<FindProgressChangedEventArgs>(discoveryClient_FindProgressChanged);  
   dc.FindAsync(new FindCriteria(typeof(ICalculatorService)));
}
static void discoveryClient_FindProgressChanged(object sender, FindProgressChangedEventArgs e)  
{  
   Console.WriteLine("Found service at: " + e.EndpointDiscoveryMetadata.Address  
}
  
static void discoveryClient_FindCompleted(object sender, FindCompletedEventArgs e)  
{
      if (e.Result.Endpoints.Count > 0)  
            {  
                EndpointAddress ep = e.Result.Endpoints[0].Address;  
                CalculatorServiceClient client = new CalculatorServiceClient();  
  
                // Connect to the discovered service endpoint  
                client.Endpoint.Address = ep;  
                Console.WriteLine("Invoking CalculatorService at {0}", ep);  
  
                double value1 = 100.00D;  
                double value2 = 15.99D;  
  
                double result = client.Add(value1, value2);  
                Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
            }  
            else  
                Console.WriteLine("No matching endpoints found");  
  
        }  
```
  
 <span data-ttu-id="8f459-127">Verwenden Sie die Methoden <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> und <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveAsync%28System.ServiceModel.Discovery.ResolveCriteria%29>, um anhand der Endpunktadresse nach einem Dienst zu suchen.</span><span class="sxs-lookup"><span data-stu-id="8f459-127">Use the <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> and <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveAsync%28System.ServiceModel.Discovery.ResolveCriteria%29> methods to locate a service based on its endpoint address.</span></span> <span data-ttu-id="8f459-128">Dies ist hilfreich, wenn die Endpunktadresse im Netzwerk nicht adressierbar ist.</span><span class="sxs-lookup"><span data-stu-id="8f459-128">This is useful when the endpoint address is not network addressable.</span></span> <span data-ttu-id="8f459-129">Die Resolve-Methoden verwenden eine Instanz von <xref:System.ServiceModel.Discovery.ResolveCriteria>. Damit können Sie die Endpunktadresse des Diensts, den Sie auflösen, die Höchstdauer des Auflösungsvorgangs und eine Gruppe von Erweiterungen angeben.</span><span class="sxs-lookup"><span data-stu-id="8f459-129">The Resolve methods take an instance of <xref:System.ServiceModel.Discovery.ResolveCriteria> which allows you to specify the endpoint address of the service you are resolving, the maximum duration of the resolve operation, and a set of extensions.</span></span> <span data-ttu-id="8f459-130">Das folgende Beispiel zeigt, wie Sie die <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A>-Methode zum Auflösen eines Diensts verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f459-130">The following example shows how to use the <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> method to resolve a service.</span></span>  
  
```csharp  
DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());  
ResolveCriteria criteria = new ResolveCriteria(endpointAddress);  
ResolveResponse response = dc.Resolve(criteria);  
EndpointAddress newEp = response.EndpointDiscoveryMetadata.Address;  
```  
  
## <a name="dynamicendpoint"></a><span data-ttu-id="8f459-131">DynamicEndpoint</span><span class="sxs-lookup"><span data-stu-id="8f459-131">DynamicEndpoint</span></span>  
 <span data-ttu-id="8f459-132"><xref:System.ServiceModel.Discovery.DynamicEndpoint>ist ein Standardendpunkt (Weitere Informationen finden Sie unter [Standardendpunkte](../../../../docs/framework/wcf/feature-details/standard-endpoints.md)), der die Ermittlung durchführt und automatisch einen übereinstimmenden Dienst auswählt.</span><span class="sxs-lookup"><span data-stu-id="8f459-132"><xref:System.ServiceModel.Discovery.DynamicEndpoint> is a standard endpoint (For more information, see [Standard Endpoints](../../../../docs/framework/wcf/feature-details/standard-endpoints.md)) which performs discovery and automatically selects a matching service.</span></span> <span data-ttu-id="8f459-133">Erstellen Sie einfach einen <xref:System.ServiceModel.Discovery.DynamicEndpoint>, über den der zu suchende Vertrag und die zu verwendende Bindung übergeben werden, und übergeben Sie die <xref:System.ServiceModel.Discovery.DynamicEndpoint>-Instanz an den WCF-Client.</span><span class="sxs-lookup"><span data-stu-id="8f459-133">Just create a <xref:System.ServiceModel.Discovery.DynamicEndpoint> passing in the contract to search for and the binding to use and pass the <xref:System.ServiceModel.Discovery.DynamicEndpoint> instance to the WCF client.</span></span> <span data-ttu-id="8f459-134">Das folgende Beispiel veranschaulicht, wie Sie einen <xref:System.ServiceModel.Discovery.DynamicEndpoint> erstellen und verwenden, um den Rechnerdienst aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="8f459-134">The following example shows how to create and use a <xref:System.ServiceModel.Discovery.DynamicEndpoint> to call the calculator service.</span></span> <span data-ttu-id="8f459-135">Die Suche wird jeweils ausgeführt, wenn der Client geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="8f459-135">The discovery is performed every time the client is opened.</span></span> <span data-ttu-id="8f459-136">Jeder in der Konfiguration definierte Endpunkt <xref:System.ServiceModel.Discovery.DynamicEndpoint> kann `kind ="dynamicEndpoint"` auch in einen umgewandelt werden, indem das Attribut zum Endpunktkonfigurationselement hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="8f459-136">Any endpoint defined in configuration can also be turned into a <xref:System.ServiceModel.Discovery.DynamicEndpoint> by adding the `kind ="dynamicEndpoint"` attribute to the endpoint configuration element.</span></span>  
  
```csharp  
DynamicEndpoint dynamicEndpoint = new DynamicEndpoint(ContractDescription.GetContract(typeof(ICalculatorService)), new WSHttpBinding());  
CalculatorServiceClient client = new CalculatorServiceClient(dynamicEndpoint);  
  
Console.WriteLine("Invoking CalculatorService");  
Console.WriteLine();  
  
double value1 = 100.00D;  
double value2 = 15.99D;  
  
double result = client.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f459-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f459-137">See also</span></span>

- [<span data-ttu-id="8f459-138">Suche mit Bereichen</span><span class="sxs-lookup"><span data-stu-id="8f459-138">Discovery with Scopes</span></span>](../../../../docs/framework/wcf/samples/discovery-with-scopes-sample.md)
- [<span data-ttu-id="8f459-139">Basic</span><span class="sxs-lookup"><span data-stu-id="8f459-139">Basic</span></span>](../../../../docs/framework/wcf/samples/basic-sample.md)
