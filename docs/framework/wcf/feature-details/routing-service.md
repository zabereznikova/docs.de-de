---
title: Routingdienst
ms.date: 03/30/2017
ms.assetid: ca7c216a-5141-4132-8193-102c181d2eba
ms.openlocfilehash: b0d58e70d482532e3f148d3f4f92741f46221982
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495304"
---
# <a name="routing-service"></a>Routingdienst
Der Routingdienst ist ein generischer SOAP-Vermittler, der als Nachrichtenrouter fungiert. Die Kernfunktion des Routingdiensts ist die Fähigkeit, Nachrichten basierend auf Nachrichteninhalt weiterzuleiten. So können Nachrichten anhand eines Werts innerhalb der Nachricht selbst (im Header oder im Text) an einen Clientendpunkt weitergeleitet werden.  
  
 Die <xref:System.ServiceModel.Routing.RoutingService> wird als Dienst in Windows Communication Foundation (WCF) implementiert die <xref:System.ServiceModel.Routing> Namespace. Der Routingdienst macht einen oder mehrere Dienstendpunkte verfügbar, die Nachrichten empfangen und die einzelnen Nachrichten dann anhand ihres Inhalts an einen oder mehrere Clientendpunkte weiterleiten. Der Dienst stellt die folgenden Funktionen bereit:  
  
-   Inhaltsbasiertes Routing  
  
    -   Dienstaggregation  
  
    -   Dienstversionsverwaltung  
  
    -   Prioritätsrouting  
  
    -   Dynamische Konfiguration  
  
-   Protokollüberbrückung  
  
-   SOAP-Verarbeitung  
  
-   Erweiterte Fehlerbehandlung  
  
-   Sicherungsendpunkte  
  
 Es ist möglich, einen Vermittlerdienst zu erstellen, der eine oder mehrere dieser Zielsetzungen erfüllt. Häufig ist eine Implementierung dieser Art jedoch an ein bestimmtes Szenario oder eine Projektmappe gebunden und kann nicht ohne Weiteres auf neue Anwendungen angewendet werden.  
  
 Der Routingdienst stellt einen generischen, dynamisch konfigurierbaren und austauschbaren SOAP-Vermittler, der kompatibel mit den WCF-Dienst- und -Modellen und ermöglicht Ihnen das inhaltsbasierte routing von SOAP-basierten Nachrichten auszuführen.  
  
> [!NOTE]
>  Der Routingdienst unterstützt das Weiterleiten von WCF-REST-Diensten momentan nicht.  Zum Weiterleiten von REST-Aufrufe in Betracht <xref:System.Web.Routing> oder [Application Request Routing](https://go.microsoft.com/fwlink/?LinkId=164589).  
  
## <a name="content-based-routing"></a>Inhaltsbasiertes Routing  
 Das inhaltsbasierte Routing ist die Fähigkeit, eine Nachricht basierend auf einem oder mehreren Werten weiterzuleiten, die in der Nachricht enthalten sind. Der Routingdienst überprüft jede Nachricht und leitet diese basierend auf den Nachrichteninhalten und der von Ihnen erstellten Routinglogik an den Zielendpunkt weiter. Das inhaltsbasierte Routing stellt die Basis für die Dienstaggregation, die Dienstversionsverwaltung und das Prioritätsrouting dar.  
  
 Zum Implementieren von inhaltsbasiertem Routing benötigt der Routingdienst <xref:System.ServiceModel.Dispatcher.MessageFilter>-Implementierungen, mit denen innerhalb der weiterzuleitenden Nachrichten Übereinstimmungen bestimmter Werte ermittelt werden. Wenn eine **MessageFilter** Übereinstimmungen, die eine Nachricht, die Nachricht wird an den Zielendpunkt zugeordneten weitergeleitet der **MessageFilter**.  Nachrichtenfilter werden in Filtertabellen (<xref:System.ServiceModel.Routing.Configuration.FilterTableCollection>) gruppiert, um eine komplexe Routinglogik zu erstellen. Eine Filtertabelle kann z. B. fünf sich gegenseitig ausschließende Nachrichtenfilter enthalten, die bewirken, dass Nachrichten nur an einen von fünf Zielendpunkten weitergeleitet werden.  
  
 Mit dem Routingdienst können Sie die Logik konfigurieren, die verwendet wird, um das inhaltsbasierte Routing auszuführen, und Sie können die Routinglogik zur Laufzeit dynamisch aktualisieren.  
  
 Aufgrund der Gruppierung von Nachrichtenfiltern in Filtertabellen kann eine Routinglogik erstellt werden, mit deren Hilfe Sie mehrere Routingszenarien verwenden können, z. B.:  
  
-   Dienstaggregation  
  
-   Dienstversionsverwaltung  
  
-   Prioritätsrouting  
  
-   Dynamische Konfiguration  
  
 Weitere Informationen zu Nachrichtenfiltern und Filtertabellen finden Sie unter [Routing Einführung](../../../../docs/framework/wcf/feature-details/routing-introduction.md) und [Nachrichtenfilter](../../../../docs/framework/wcf/feature-details/message-filters.md).  
  
### <a name="service-aggregation"></a>Dienstaggregation  
 Mit dem inhaltsbasierten Routing können Sie einen Endpunkt verfügbar machen, der Nachrichten von externen Clientanwendungen empfängt und jede Nachricht dann anhand eines Werts in der Nachricht an den entsprechenden internen Endpunkt weiterleitet. Dies ist nützlich, um für eine Reihe unterschiedlicher Back-End-Anwendungen einen bestimmten Endpunkt bereitzustellen. Außerdem können Sie so einen Anwendungsendpunkt für Kunden bereitstellen und die Anwendung in verschiedene Dienste unterteilen.  
  
### <a name="service-versioning"></a>Dienstversionsverwaltung  
 Wenn Sie zu einer neuen Version der Projektmappe migrieren, müssen Sie die alte Version ggf. parallel weiterlaufen lassen, um bestehende Kunden weiter bedienen zu können. Häufig bedeutet dies für Clients, die über eine Verbindung zur neuen Version verfügen, dass diese für die Kommunikation mit der Projektmappe eine andere Adresse verwenden müssen. Mit dem Routingdienst können Sie einen Dienstendpunkt verfügbar machen, der für beide Versionen der Projektmappe verwendet wird, indem Nachrichten basierend auf jeweils in der Nachricht enthaltenen Informationen an die entsprechende Projektmappe weitergeleitet werden. Ein Beispiel für eine solche Implementierung finden Sie unter [so wird's gemacht: Dienstversionsverwaltung](../../../../docs/framework/wcf/feature-details/how-to-service-versioning.md).  
  
### <a name="priority-routing"></a>Prioritätsrouting  
 Wenn Sie einen Dienst für mehrere Clients bereitstellen, verfügen Sie ggf. über eine Vereinbarung zum Servicelevel (SLA) mit einigen Partnern, bei der alle Daten dieser Partner separat von den Daten anderer Clients verarbeitet werden müssen. Mit einem Filter, der in der Nachricht nach kundenspezifischen Informationen sucht, können Sie Nachrichten von bestimmten Partnern auf einfache Weise an einen Endpunkt weiterleiten, der erstellt wurde, um die SLA-Anforderungen zu erfüllen.  
  
## <a name="dynamic-configuration"></a>Dynamische Konfiguration  
 Wenn es beim Unterstützen von unternehmenswichtigen Systemen um die Nachrichtenverarbeitung ohne Dienstunterbrechungen geht, ist es von entscheidender Bedeutung, dass Sie die Konfiguration von Komponenten innerhalb des Systems während der Laufzeit ändern können. Um diese Anforderung zu unterstützen, stellt der Routingdienst eine <xref:System.ServiceModel.IExtension%601>-Implementierung bereit, und zwar <xref:System.ServiceModel.Routing.RoutingExtension>, die eine dynamische Aktualisierung der Routingdienstkonfiguration zur Laufzeit ermöglicht.  
  
 Weitere Informationen zur dynamischen Konfiguration des Routingdiensts finden Sie unter [Routing Einführung](../../../../docs/framework/wcf/feature-details/routing-introduction.md).  
  
## <a name="protocol-bridging"></a>Protokollüberbrückung  
 Eine der Herausforderungen besteht bei Vermittlerszenarios darin, dass die internen Endpunkte ggf. über andere Anforderungen an den Transport oder die SOAP-Version als der Endpunkt verfügen, an dem Nachrichten empfangen werden. Um dieses Szenario zu unterstützen, kann der Routingdienst Protokolle überbrücken, einschließlich der Verarbeitung der SOAP-Nachricht an die <xref:System.ServiceModel.Channels.MessageVersion>, die für die Zielendpunkte erforderlich ist. Auf diese Weise kann ein Protokoll für die interne Kommunikation verwendet werden, während ein anderes für die externe Kommunikation verwendet werden kann.  
  
 Um die Weiterleitung von Nachrichten zwischen Endpunkten mit verschiedenen Transporten zu unterstützen, verwendet der Routingdienst vom System bereitgestellte Bindungen, die dem Dienst das Überbrücken unterschiedlicher Protokolle ermöglichen. Dies tritt automatisch ein, wenn der vom Routingdienst verfügbar gemachte Dienstendpunkt ein anderes Protokoll verwendet als die Clientendpunkte, an die Nachrichten weitergeleitet werden.  
  
## <a name="soap-processing"></a>SOAP-Verarbeitung  
 Eine häufige Routinganforderung ist die Fähigkeit, Nachrichten zwischen Endpunkten mit sich unterscheidenden SOAP-Anforderungen weiterzuleiten. Um diese Anforderung zu unterstützen, stellt der Routingdienst eine <xref:System.ServiceModel.Routing.SoapProcessingBehavior> , die automatisch erstellt ein neues **MessageVersion** , die die Anforderungen des Zielendpunkts erfüllt, bevor die Nachricht dorthin weitergeleitet wird. Dieses Verhalten erstellt auch eine neue **MessageVersion** für jede Antwortnachricht vor der Rückgabe an die anfordernde Clientanwendung, um sicherzustellen, dass die **MessageVersion** der Antwort entspricht der die ursprüngliche Anforderung.  
  
 Weitere Informationen zu SOAP-Verarbeitung, finden Sie unter [Routing Einführung](../../../../docs/framework/wcf/feature-details/routing-introduction.md).  
  
## <a name="error-handling"></a>Fehlerbehandlung  
 In einem System, das aus verteilten Diensten besteht, die eine Netzwerkkommunikation benötigen, muss sichergestellt sein, dass die Kommunikation innerhalb des Systems gegen vorübergehende Netzwerkfehler immun ist.  Der Routingdienst implementiert eine Fehlerbehandlung, bei der Sie viele Kommunikationsfehlerszenarien behandeln können, die andernfalls zu einem Dienstausfall führen können.  
  
 Wenn der Routingdienst beim versuchten Senden einer Nachricht auf eine <xref:System.ServiceModel.CommunicationException> trifft, wird die Fehlerbehandlung durchgeführt.  Diese Ausnahmen weisen in der Regel darauf hin, dass beim Versuch der Kommunikation mit dem definierten Clientendpunkt ein Problem aufgetreten ist, z. B. <xref:System.ServiceModel.EndpointNotFoundException>, <xref:System.ServiceModel.ServerTooBusyException> oder <xref:System.ServiceModel.CommunicationObjectFaultedException>.  Der Fehlerbehandlungscode auch abfangen und versuchen, erneut zu senden, wenn eine **TimeoutException** auftritt, d.h., dass eine andere häufige Ausnahme, die nicht von abgeleitet ist **CommunicationException**.  
  
 Weitere Informationen zur Fehlerbehandlung finden Sie unter [Routing Einführung](../../../../docs/framework/wcf/feature-details/routing-introduction.md).  
  
## <a name="backup-endpoints"></a>Sicherungsendpunkte  
 Zusätzlich zu den Ziel-Clientendpunkten, die in der Filtertabelle den einzelnen Filterdefinitionen zugeordnet sind, können Sie auch eine Liste von Sicherungsendpunkten erstellen, an die die Nachricht im Fall eines Übertragungsfehlers weitergeleitet wird. Wenn ein Fehler auftritt und eine Sicherungsliste für den Filtereintrag definiert wird, versucht der Routingdienst, die Nachricht an den ersten in der Liste definierten Endpunkt zu senden. Falls bei diesem Übertragungsversuch ein Fehler auftritt, versucht es der Dienst mit dem nächsten Endpunkt und setzt diesen Vorgang so lange fort, bis die Übertragung erfolgreich ist, einen nicht die Übertragung betreffenden Fehler zurückgibt oder alle Endpunkte in der Sicherungsliste einen Übertragungsfehler zurückgegeben haben.  
  
 Weitere Informationen zu sicherungsendpunkten finden Sie unter [Routing Einführung](../../../../docs/framework/wcf/feature-details/routing-introduction.md) und [Nachrichtenfilter](../../../../docs/framework/wcf/feature-details/message-filters.md).  
  
## <a name="streaming"></a>Streaming  
 Der Routingdienst kann Nachrichten erfolgreich streamen, wenn Sie die Bindung für die Unterstützung von Streaming festlegen.  Es gibt jedoch einige Bedingungen, die möglicherweise das Puffern von Nachrichten erfordern:  
  
-   Multicast (puffern, um zusätzliche Nachrichtenkopien zu erstellen)  
  
-   Failover (puffern, falls die Nachricht an eine Sicherung gesendet werden muss)  
  
-   System.ServiceModel.Routing.RoutingConfiguration.RouteOnHeadersOnly ist false (puffern, um die MessageFilterTable mit einem MessageBuffer bereitzustellen, damit Filter den Text überprüfen können)  
  
-   Dynamische Konfiguration  
  
## <a name="see-also"></a>Siehe auch
- [Einführung in Routing](../../../../docs/framework/wcf/feature-details/routing-introduction.md)
- [Routingverträge](../../../../docs/framework/wcf/feature-details/routing-contracts.md)
- [Nachrichtenfilter](../../../../docs/framework/wcf/feature-details/message-filters.md)
