---
title: Suche und FindCriteria
ms.date: 03/30/2017
ms.assetid: 99016fa4-1778-495b-b4cc-0e22fbec42c6
ms.openlocfilehash: da4c3c4a1d765e4f91b03f4f8fc1a73c3fea1535
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964836"
---
# <a name="discovery-find-and-findcriteria"></a>Suche und FindCriteria

Ein Suchvorgang wird von einem Client initiiert, um einen oder mehrere Dienste zu ermitteln, und ist eine der Hauptaktionen bei der Suche. Beim Durchführen einer Suche wird eine WS-Discovery-Probe-Nachricht über das Netzwerk gesendet. Dienste, die die angegebenen Kriterien erfüllen, antworten mit WS-Discovery-ProbeMatch-Nachrichten. Weitere Informationen zu Ermittlungs Nachrichten finden Sie in der [WS-Discovery-Spezifikation](http://schemas.xmlsoap.org/ws/2004/10/discovery/ws-discovery.pdf).

## <a name="discoveryclient"></a>DiscoveryClient

Die <xref:System.ServiceModel.Discovery.DiscoveryClient>-Klasse stellt den Mechanismus zur Durchführung von Suchvorgängen bereit und ermöglicht eine einfache Durchführung von Suchclientvorgängen. Sie enthält eine <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>-Methode, die eine synchrone (blockierende) Suche ausführt, und eine <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A>-Methode, die eine asynchrone (nicht blockierende) Suche initiiert. Beide Methoden verwenden einen <xref:System.ServiceModel.Discovery.FindCriteria>-Parameter und stellen dem Benutzer Ergebnisse über ein <xref:System.ServiceModel.Discovery.FindResponse>-Objekt bereit.

## <a name="findcriteria"></a>FindCriteria

<xref:System.ServiceModel.Discovery.FindCriteria> verfügt über mehrere Eigenschaften, die nach Suchkriterien (nach welchen Diensten soll gesucht werden) und Beendigungskriterien für die Suche (wie lange soll die Suche dauern) gruppiert werden können. Ein <xref:System.ServiceModel.Discovery.FindCriteria>-Objekt kann mehrere Suchkriterien enthalten. Standardmäßig muss der Dienst mit allen Komponenten übereinstimmen, da es sich sonst nicht um einen übereinstimmenden Dienst handelt. Falls Sie nach Diensten suchen möchten, die nur einige Kriterien erfüllen, können Sie für den Dienst eine benutzerdefinierte Suchlogik implementieren, oder Sie können mehrere Abfragen verwenden.

Zu den Suchkriterien gehört Folgendes:

- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement> – Optional. Der Vertragsname des Diensts, nach dem gesucht wird, und die Kriterien, die normalerweise beim Suchen nach einem Dienst verwendet werden. Wenn mehr als ein Vertragsname angegeben wird, antworten nur Dienstendpunkte, die mit ALLEN Verträgen übereinstimmen. Beachten Sie, dass ein Endpunkt in WCF nur einen Vertrag unterstützen kann.

- <xref:System.ServiceModel.Discovery.Configuration.ScopeElement> – Optional. Bereiche sind absolute URIs, die verwendet werden, um einzelne Dienstendpunkte zu kategorisieren. Dies ist in Szenarien nützlich, in denen mehrere Endpunkte den gleichen Vertrag verfügbar machen und in denen Sie nach einer Möglichkeit suchen, nach einer Teilmenge der Endpunkte zu suchen. Wenn mehr als ein Bereich angegeben wird, antworten nur Dienstendpunkte, die mit ALLEN Bereichen übereinstimmen.

- <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchBy%2A> – Gibt an, welcher Übereinstimmungsalgorithmus verwendet werden soll, während die Übereinstimmung der Bereiche der Probe-Nachricht mit denen des Endpunkts ermittelt wird. Es gibt fünf unterstützte Bereichsübereinstimmungsregeln:

  - <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByExact?displayProperty=nameWithType> führt einen grundlegenden Zeichenfolgenvergleich aus, bei dem die Groß-/Kleinschreibung beachtet wird.

  - <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByPrefix?displayProperty=nameWithType> Übereinstimmungen nach Segmenten, die durch "/" getrennt sind. Eine Suche nach `http://contoso/building1` entspricht einem Dienst mit Bereichs `http://contoso/building/floor1`. Beachten Sie, dass Sie nicht `http://contoso/building100` entspricht, da die beiden letzten Segmente nicht mit identisch sind.

  - <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByLdap?displayProperty=nameWithType> ermittelt für Bereiche Übereinstimmungen nach Segmenten unter Verwendung einer LDAP-URL.

  - <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByUuid?displayProperty=nameWithType> ermittelt mithilfe einer UUID-Zeichenfolge genaue Übereinstimmungen für Bereiche.

  - <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByNone?displayProperty=nameWithType> ermittelt nur Übereinstimmungen für Dienste, die keinen Bereich angeben.

  Wenn keine Bereichsübereinstimmungsregel angegeben wird, wird <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByPrefix> verwendet.

Zu den Beendigungskriterien gehört Folgendes:

1. <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> – Der maximale Zeitraum, wie lange auf Antworten der Dienste im Netzwerk gewartet wird. Der Standardzeitraum beträgt 20 Sekunden.

2. <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> – Die maximale Anzahl von Antworten, auf die gewartet wird. Wenn <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A>-Antworten empfangen werden, bevor die <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> verstrichen ist, endet der Suchvorgang.

## <a name="findresponse"></a>FindResponse

<xref:System.ServiceModel.Discovery.FindResponse> verfügt über eine <xref:System.ServiceModel.Discovery.FindResponse.Endpoints%2A>-Auflistungseigenschaft, die alle Antworten enthält, die von übereinstimmenden Diensten im Netzwerk gesendet werden. Falls keine Dienste antworten, ist die Auflistung leer. Falls ein oder mehrere Dienste antworteten, wird jede Antwort in einem <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>-Objekt gespeichert. Dieses Objekt enthält die Adresse, den Vertrag und einige weitere Informationen zum Dienst.

Im folgenden Beispiel wird gezeigt, wie Sie einen Suchvorgang per Code ausführen.

```csharp
// Create DiscoveryClient
DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());

// Create FindCriteria
FindCriteria findCriteria = new FindCriteria(typeof(IPrinterService));
findCriteria.Scopes.Add(new Uri("http://www.contoso.com/building1/floor1"));
findCriteria.Duration = TimeSpan.FromSeconds(10);

// Find ICalculatorService endpoints
FindResponse findResponse = discoveryClient.Find(findCriteria);

Console.WriteLine("Found {0} ICalculatorService endpoint(s).", findResponse.Endpoints.Count)
```

## <a name="see-also"></a>Siehe auch

- [Übersicht über die WCF-Suche](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)
- [Verwenden des Ermittlungsclientkanals](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)
- [Suche mit Bereichen](../../../../docs/framework/wcf/samples/discovery-with-scopes-sample.md)
- [Standard](../../../../docs/framework/wcf/samples/basic-sample.md)
