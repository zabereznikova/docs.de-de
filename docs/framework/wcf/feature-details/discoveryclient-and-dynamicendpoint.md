---
title: DiscoveryClient und DynamicEndpoint
ms.date: 03/30/2017
ms.assetid: 7cd418f0-0eab-48d1-a493-7eb907867ec3
ms.openlocfilehash: 6144a3fb528e64fd55fa125b6254d415ec3e8b26
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599164"
---
# <a name="discoveryclient-and-dynamicendpoint"></a>DiscoveryClient und DynamicEndpoint
<xref:System.ServiceModel.Discovery.DiscoveryClient> und <xref:System.ServiceModel.Discovery.DynamicEndpoint> sind zwei Klassen, die auf der Clientseite zum Suchen nach Diensten verwendet werden. <xref:System.ServiceModel.Discovery.DiscoveryClient> stellt eine Liste der Dienste bereit, die bestimmten Kriterien entsprechen, und ermöglicht Ihnen das Herstellen einer Verbindung mit den Diensten. <xref:System.ServiceModel.Discovery.DynamicEndpoint> führt den gleichen Vorgang aus und stellt zusätzlich eine Verbindung mit einem der gefundenen Dienste her. Jeder Endpunkt kann als <xref:System.ServiceModel.Discovery.DynamicEndpoint> festgelegt werden, und die Suchkriterien können auch in der Konfiguration hinzugefügt werden. <xref:System.ServiceModel.Discovery.DynamicEndpoint> ist hilfreich, wenn Sie die Suche in der Projektmappe benötigen, die Clientlogik jedoch nicht ändern möchten – Sie müssen nur die Endpunkte ändern. <xref:System.ServiceModel.Discovery.DiscoveryClient> bietet Ihnen jedoch eine präzisere Steuerung des Suchvorgangs. Die Verwendungsmöglichkeiten und Vorteile der Klassen werden unten näher beschrieben.  
  
## <a name="discoveryclient"></a>DiscoveryClient  
 Der <xref:System.ServiceModel.Discovery.DiscoveryClient> definiert synchrone und asynchrone Find-Methoden wie <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted>- und <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged>-Ereignisse.  Er definiert außerdem synchrone und asynchrone Resolve-Methoden und ein <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveCompleted>-Ereignis. Verwenden Sie die Methode <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> oder <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> zum Suchen nach Diensten. Beide Methoden verwenden eine <xref:System.ServiceModel.Discovery.FindCriteria>-Instanz, über die Sie Folgendes angeben können: Vertragstypnamen, Bereiche, maximale Anzahl an angeforderten Ergebnissen und die Übereinstimmungsregeln für Bereiche. Beim Aufruf der <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted>-Methode können das <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged>-Ereignis und das <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A>-Ereignis verwendet werden. <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> wird immer ausgelöst, wenn der <xref:System.ServiceModel.Discovery.DiscoveryClient> eine Antwort von einem Dienst empfängt. Es kann verwendet werden, um eine Statusanzeige anzuzeigen, die den Status des Suchvorgangs angibt. Außerdem kann es verwendet werden, um auf empfangene Suchantworten zu reagieren. Das <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted>-Ereignis wird nach Abschluss des Suchvorgangs ausgelöst. Dies kann der Fall sein, weil die maximale Anzahl von Antworten empfangen wurde oder wenn der unter <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> festgelegte Zeitraum verstrichen ist. Nachdem der Suchvorgang abgeschlossen wurde, werden die Ergebnisse in einer <xref:System.ServiceModel.Discovery.FindResponse>-Instanz zurückgegeben. <xref:System.ServiceModel.Discovery.FindResponse> enthält eine Auflistung von <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> mit den Adressen, Vertragstypnamen, Erweiterungen, Abhör-URIs und Bereichen der übereinstimmenden Dienste. Sie können diese Informationen dann verwenden, um eine Verbindung zu einem der übereinstimmenden Dienste herzustellen und diesen aufzurufen. Im folgenden Beispiel wird gezeigt, wie die System. Service Model. Discovery. DiscoveryClient. Find (System. Service Model. Discovery. FindCriteria)-Methode aufgerufen und die zurückgegebenen Metadaten verwendet werden, um den gefundenen Dienst aufzurufen. Ein Vorteil der Verwendung von <xref:System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria)> besteht darin, dass Sie die Liste der gefundenen Endpunkte Zwischenspeichern und Sie zu einem späteren Zeitpunkt verwenden können. Mit diesem Cache können Sie eine benutzerdefinierte Logik zur Behandlung verschiedener Fehlerbedingungen erstellen.  
  
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
  
 Das folgende Beispiel zeigt, wie Sie einen Suchvorgang asynchron ausführen.  
  
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
  
 Verwenden Sie die Methoden <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> und <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveAsync%28System.ServiceModel.Discovery.ResolveCriteria%29>, um anhand der Endpunktadresse nach einem Dienst zu suchen. Dies ist hilfreich, wenn die Endpunktadresse im Netzwerk nicht adressierbar ist. Die Resolve-Methoden verwenden eine Instanz von <xref:System.ServiceModel.Discovery.ResolveCriteria>. Damit können Sie die Endpunktadresse des Diensts, den Sie auflösen, die Höchstdauer des Auflösungsvorgangs und eine Gruppe von Erweiterungen angeben. Das folgende Beispiel zeigt, wie Sie die <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A>-Methode zum Auflösen eines Diensts verwenden.  
  
```csharp  
DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());  
ResolveCriteria criteria = new ResolveCriteria(endpointAddress);  
ResolveResponse response = dc.Resolve(criteria);  
EndpointAddress newEp = response.EndpointDiscoveryMetadata.Address;  
```  
  
## <a name="dynamicendpoint"></a>DynamicEndpoint  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>bei handelt es sich um einen Standard Endpunkt (Weitere Informationen finden Sie unter [Standard Endpunkte](standard-endpoints.md)), der die Ermittlung ausführt und automatisch einen übereinstimmenden Dienst auswählt. Erstellen Sie einfach einen <xref:System.ServiceModel.Discovery.DynamicEndpoint>, über den der zu suchende Vertrag und die zu verwendende Bindung übergeben werden, und übergeben Sie die <xref:System.ServiceModel.Discovery.DynamicEndpoint>-Instanz an den WCF-Client. Das folgende Beispiel veranschaulicht, wie Sie einen <xref:System.ServiceModel.Discovery.DynamicEndpoint> erstellen und verwenden, um den Rechnerdienst aufzurufen. Die Suche wird jeweils ausgeführt, wenn der Client geöffnet wird. Alle in der Konfiguration definierten Endpunkte können auch in eine umgewandelt werden <xref:System.ServiceModel.Discovery.DynamicEndpoint> , indem dem `kind ="dynamicEndpoint"` Endpunkt Konfigurationselement das-Attribut hinzugefügt wird.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Suche mit Bereichen](../samples/discovery-with-scopes-sample.md)
- [Grundlegend](../samples/basic-sample.md)
