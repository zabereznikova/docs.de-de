---
title: Übersicht über die WCF-Suche
ms.date: 03/30/2017
ms.assetid: 84fad0e4-23b1-45b5-a2d4-c9cdf90bbb22
ms.openlocfilehash: 449d54e0dd1948885a7298fb4da46067de3eb9d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184212"
---
# <a name="wcf-discovery-overview"></a>Übersicht über die WCF-Suche
Die Such-APIs stellen ein einheitliches Programmiermodell zur dynamischen Veröffentlichung von und zum Suchen nach Webdiensten bereit, wobei das WS-Suchprotokoll verwendet wird. Diese APIs ermöglichen es Diensten, sich selbst zu veröffentlichen, und Client das Suchen nach veröffentlichten Diensten. Nachdem ein Dienst erkennbar gemacht wurde, kann der Dienst Ankündigungsmeldungen senden sowie eine Überwachung auf Suchanforderungen durchführen und darauf antworten. Erkennbare Dienste können Hello-Nachrichten senden, um ihre Ankunft in einem Netzwerk anzukündigen, und Bye-Nachrichten, um das Verlassen eines Netzwerks anzukündigen. Um nach einem Dienst zu suchen, senden Clients eine `Probe`-Anforderung, die bestimmte Kriterien wie den Dienstvertragstyp, Schlüsselwörter und den Bereich des Netzwerks enthält. Dienste empfangen die `Probe`-Anforderung und bestimmen, ob diese den Kriterien entspricht. Wenn sich für einen Dienst eine Übereinstimmung ergibt, antwortet dieser mit dem Rücksenden einer `ProbeMatch`-Nachricht an den Client, in der die Informationen für die Kontaktaufnahme mit dem Dienst enthalten sind. Clients können auch `Resolve`-Anforderungen senden, mit deren Hilfe sie nach Diensten suchen können, die ggf. ihre Endpunktadresse geändert haben. Dienste, die Übereinstimmungen ergeben, antworten auf `Resolve`-Anforderungen, indem sie eine `ResolveMatch`-Nachricht zurück an den Client senden.  
  
## <a name="ad-hoc-and-managed-modes"></a>Ad-hoc-Modus und verwalteter Modus  
 Die Such-API unterstützt zwei verschiedene Modi: Verwaltet und Ad-hoc. Im Modus "Verwaltet" wird ein zentralisierter Server verwendet, der als Suchproxy bezeichnet wird und Informationen zu verfügbaren Diensten verwaltet. Der Suchproxy auf verschiedene Arten mit Informationen zu Diensten aufgefüllt werden. Dienste können z. B. während des Starts Ankündigungsmeldungen an den Suchproxy senden, oder der Proxy kann Daten aus einer Datenbank oder einer Konfigurationsdatei lesen, um zu ermitteln, welche Dienste verfügbar sind. Die Art und Weise, wie der Suchproxy aufgefüllt wird, hängt vollständig vom Entwickler ab. Clients verwenden den Suchproxy zum Abrufen von Informationen zu verfügbaren Diensten. Wenn ein Client nach einem Dienst sucht, sendet er eine `Probe`-Nachricht an den Suchproxy, und der Proxy ermittelt dann, ob einer der bekannten Dienste mit dem Dienst übereinstimmt, nach dem der Client sucht. Wenn Übereinstimmungen vorhanden sind, sendet der Suchproxy eine `ProbeMatch`-Antwort zurück an den Client. Der Client kann sich dann direkt an den Dienst wenden, indem er die vom Proxy zurückgegebenen Dienstinformationen verwendet. Das Hauptprinzip hinter dem Modus "Verwaltet" beruht darauf, dass die Suchanforderungen im Unicast-Format an eine Autorität, den Suchproxy, gesendet werden. .NET Framework enthält Hauptkomponenten, mit denen Sie einen eigenen Proxy erstellen können. Es gibt für Clients und Dienste mehrere Methoden, nach dem Proxy zu suchen:  
  
- Der Proxy kann auf Ad-hoc-Nachrichten reagieren.  
  
- Der Proxy kann während des Startvorgangs eine Ankündigungsnachricht senden.  
  
- Es können Clients und Dienste geschrieben werden, um nach einem bestimmten bekannten Endpunkt zu suchen.  
  
 Im Ad-hoc-Modus gibt es keinen zentralisierten Server. Alle Suchnachrichten, z. B. Dienstankündigungen und Clientanforderungen, werden im Multicast-Format gesendet. Standardmäßig enthält .NET Framework Unterstützung für die Ad-hoc-Suche über das UDP-Protokoll. Wenn ein Dienst z. B. konfiguriert wird, um während des Startvorgangs eine Hello-Ankündigung zu senden, erfolgt das Senden über eine bekannte Multicastadresse und das UDP-Protokoll. Clients müssen über eine aktive Überwachung auf diese Ankündigungen verfügen und diese entsprechend verarbeiten. Wenn ein Client eine `Probe`-Nachricht für einen Dienst sendet, wird diese mit einem Multicastprotokoll über das Netzwerk übertragen. Jeder Dienst, der die Anforderung empfängt, ermittelt, ob diese mit den Kriterien der `Probe`-Nachricht übereinstimmt. Anschließend antwortet der jeweilige Dienst dem Client direkt mit einer `ProbeMatch`-Nachricht, falls sich für den Dienst eine Übereinstimmung mit den Kriterien ergibt, die in der `Probe`-Nachricht angegeben sind.  
  
## <a name="benefits-of-using-wcf-discovery"></a>Vorteile der WCF-Suche  
 Da die WCF-Suche mit dem WS-Discovery-Protokoll implementiert wird, besteht Interoperabilität mit anderen Clients, Diensten und Proxys, die WS-Discovery ebenfalls implementieren. Die WCF-Suche basiert auf den vorhandenen WCF-APIs, sodass Sie den vorhandenen Diensten und den Clients auf einfache Weise Suchfunktionalität hinzufügen können. Sie können die Auffindbarkeit von Diensten einfach über die Anwendungskonfigurationseinstellungen hinzufügen. Außerdem unterstützt die WCF-Suche die Verwendung des Suchprotokolls über andere Transporte wie Peernetzwerk, Namens-Overlay und HTTP. Die WCF-Suche unterstützt den Modus "Verwaltet", in dem ein Suchproxy verwendet wird. So kann der Netzwerkverkehr reduziert werden, weil Nachrichten direkt an den Suchproxy gesendet werden, und es werden keine Multicastnachrichten an das gesamte Netzwerk gesendet. Beim Arbeiten mit Webdiensten ermöglicht die WCF-Suche zudem mehr Flexibilität. Sie können z. B. die Adresse eines Diensts ändern, ohne den Client oder den Dienst neu konfigurieren zu müssen. Wenn ein Client auf den Dienst zugreifen muss, kann er über eine `Probe`-Anforderung eine `Find`-Nachricht ausgeben. Er erwartet dann, dass der Dienst mit seiner aktuellen Adresse antwortet. Mit der WCF-Suche kann ein Client anhand unterschiedlicher Kriterien, wie Vertragstypen, Bindungselemente, Namespace, Bereich und Schlüsselwörter oder Versionsnummern, nach einem Dienst suchen. Die WCF-Suche ermöglicht die Suche zur Laufzeit und zur Entwurfszeit. Das Hinzufügen der Suchfunktion zu einer Anwendung ermöglicht weitere Szenarien, z. B. Fehlertoleranz und automatische Konfiguration.  
  
## <a name="service-publication"></a>Dienstveröffentlichung  
 Um einen Dienst erkennbar zu machen, müssen Sie dem Diensthost ein <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> hinzufügen. Außerdem müssen Sie einen Suchendpunkt hinzufügen, um anzugeben, welche Komponenten auf Suchnachrichten überwacht werden sollen. Im folgenden Codebeispiel wird gezeigt, wie Sie einen selbst gehosteten Dienst ändern können, um diesen erkennbar zu machen.  
  
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
  
 Einer Dienstbeschreibung muss eine <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>-Instanz hinzugefügt werden, damit der Dienst erkennbar ist. Dem Diensthost muss eine <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>-Instanz hinzugefügt werden, um dem Dienst mitzuteilen, welche Komponenten auf Suchanforderungen überwacht werden sollen. In diesem Beispiel wird ein <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> (von <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> abgeleitet) hinzugefügt, um anzugeben, dass der Dienst die Überwachung über den UDP-Multicasttransport durchführen soll. Der <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> wird für die Ad-hoc-Suche verwendet, weil alle Nachrichten im Multicast-Format gesendet werden.  
  
## <a name="announcement"></a>Ankündigung  
 Bei der Dienstveröffentlichung werden standardmäßig keine Ankündigungsnachrichten gesendet. Der Dienst muss so konfiguriert werden, dass er Ankündigungsnachrichten sendet. Dadurch können Dienstwriter flexibler arbeiten, weil sie den Dienst getrennt von der Überwachung auf Suchnachrichten ankündigen können. Die Dienstankündigung kann auch als Mechanismus zum Registrieren von Diensten bei einem Suchproxy oder anderen Dienstregistrierungen verwendet werden. Im folgenden Code wird gezeigt, wie Sie einen Dienst zum Senden von Ankündigungsnachrichten über eine UDP-Bindung konfigurieren.  
  
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
  
## <a name="service-discovery"></a>Dienstsuche  
 Eine Clientanwendung kann die <xref:System.ServiceModel.Discovery.DiscoveryClient>-Klasse verwenden, um nach Diensten zu suchen. Der Entwickler erstellt eine Instanz der <xref:System.ServiceModel.Discovery.DiscoveryClient>-Klasse, die einen Suchendpunkt übergibt. Der Suchendpunkt gibt an, wohin `Probe`- oder `Resolve`-Nachrichten gesendet werden sollen. Der Client ruft dann die <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>-Methode auf, die die Suchkriterien innerhalb einer <xref:System.ServiceModel.Discovery.FindCriteria>-Instanz angibt. Wenn übereinstimmende Dienste gefunden werden, gibt <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> eine Auflistung von <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> zurück. Der folgende Code zeigt, wie sie die `Find`-Methode aufrufen und dann eine Verbindung zu einem ermittelten Dienst herstellen.  
  
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
  
## <a name="discovery-and-message-level-security"></a>Sicherheit der Such- und Nachrichtenebene  
 Beim Verwenden der Nachrichtenebenensicherheit müssen Sie auf dem Dienstsuchendpunkt ein <xref:System.ServiceModel.EndpointIdentity>-Objekt und auf dem Clientsuchendpunkt ein passendes <xref:System.ServiceModel.EndpointIdentity>-Objekt angeben. Weitere Informationen zur Sicherheit auf Nachrichtenebene finden Sie unter [Nachrichtensicherheit](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md).  
  
## <a name="discovery-and-web-hosted-services"></a>Suche und im Internet gehostete Dienste  
 Damit WCF-Dienste erkennbar sind, müssen sie derzeit ausgeführt werden. Unter IIS oder WAS gehostete WCF-Dienste werden erst ausgeführt, wenn IIS/WAS eine Meldung für den Dienst empfängt. Daher sind sie nicht standardmäßig erkennbar.  Es gibt zwei Möglichkeiten, im Internet gehostete Dienste als erkennbar festzulegen:  
  
1. Verwenden der Autostart-Funktion von Windows Server AppFabric  
  
2. Verwenden eines Suchproxys zur Kommunikation im Namen des Diensts  
  
 Windows Server AppFabric verfügt über eine Autostart-Funktion, mit der ein Dienst gestartet werden kann, bevor Meldungen empfangen werden. Wenn die Autostart-Funktion festgelegt ist, kann ein von IIS/WAS gehosteter Dienst als erkennbar konfiguriert werden. Weitere Informationen zur Funktion zum automatischen Start finden Sie unter [Windows Server AppFabric Auto-Start Feature](https://docs.microsoft.com/previous-versions/appfabric/ee677260(v=azure.10)). Wenn Sie die Autostart-Funktion aktivieren, müssen Sie den Dienst für die Suche konfigurieren. Weitere Informationen finden Sie unter [Gewusst wie: Programmgesteuertes Hinzufügen von Erkennungsmöglichkeiten zu einem WCF-Dienst und](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)[Clientkonfigurationsermittlung in einer Konfigurationsdatei](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md).  
  
 Ein Suchproxy kann verwendet werden, um im Namen des WCF-Diensts zu kommunizieren, wenn der Dienst nicht ausgeführt wird. Der Proxy kann Überprüfungs- oder Auflösungsmeldungen abhören und dem Client antworten. Anschließend kann der Client Meldungen direkt an den Dienst senden. Wenn der Client eine Meldung an den Dienst sendet, wird dieser instanziiert, um auf die Meldung zu antworten. Weitere Informationen zum Implementieren eines Ermittlungsproxys finden Sie unter [Implementieren eines Ermittlungsproxys](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md).  
  
> [!NOTE]
> Damit WCF Discovery ordnungsgemäß funktioniert, sollten alle Netzwerkschnittstellencontroller nur über eine IP-Adresse verfügen.
