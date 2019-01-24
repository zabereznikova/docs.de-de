---
title: Routingszenarien
ms.date: 03/30/2017
helpviewer_keywords:
- rounting [WCF], scenarios
ms.assetid: ec22f308-665a-413e-9f94-7267cb665dab
ms.openlocfilehash: 6803468c8814b229df752e3ed9bc48aa0e632dd6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54699596"
---
# <a name="routing-scenarios"></a>Routingszenarien
Der Routingdienst lässt sich zwar stark anpassen, aber es kann aufwändig sein, beim Erstellen einer völlig neuen Konfiguration eine effiziente Routinglogik zu entwerfen.  Es gibt jedoch einige allgemeine Szenarios, auf denen die meisten Routingdienstkonfigurationen basieren. Auch wenn diese Szenarios ggf. nicht genau mit Ihrer jeweiligen Konfiguration übereinstimmen, trägt es zum Verständnis des Routingdiensts bei, wenn Sie wissen, wie dieser in bestimmten Szenarios konfiguriert werden kann.  
  
## <a name="common-scenarios"></a>Häufige Szenarien  
 Die grundlegendste Verwendung des Routingdiensts ist die Aggregation mehrerer Zielendpunkte zum Reduzieren der Anzahl von Endpunkten, die für die Clientanwendungen verfügbar gemacht werden, und die anschließende Verwendung von Nachrichtenfiltern zum Weiterleiten der einzelnen Nachrichten an das richtige Ziel. Nachrichten können basierend auf logischen oder physischen Verarbeitungsanforderungen (z. B. ein Nachrichtentyp, der von einem bestimmten Dienst verarbeitet werden muss) oder basierend auf beliebigen Geschäftsanforderungen (z. B. Bereitstellung der Verarbeitung von Nachrichten über eine bestimmte Quelle) verarbeitet werden. In der nachstehenden Tabelle sind einige allgemeine Szenarios und die Umstände aufgeführt, unter denen diese auftreten:  
  
|Szenario|Wenn folgende Bedingungen vorliegen|  
|--------------|--------------|  
|Dienstversionsverwaltung|Sie müssen mehrere Versionen eines Diensts unterstützen oder in Zukunft ggf. einen aktualisierten Dienst bereitstellen.|  
|Dienstdatenpartitionierung|Sie müssen einen Dienst über mehrere Hosts hinweg partitionieren.|  
|Dynamisches Update|Sie müssen die Routinglogik zur Laufzeit aufgrund von sich ändernden Dienstbereitstellungen dynamisch neu konfigurieren.|  
|Multicast|Sie müssen eine Nachricht an mehrere Endpunkte senden.|  
|Protokollüberbrückung|Sie empfangen Nachrichten über ein Transportprotokoll, und der Zielendpunkt verwendet ein anderes Protokoll.|  
|Fehlerbehandlung|Sie müssen für die Widerstandsfähigkeit gegen Netzwerkausfälle und Kommunikationsfehler sorgen.|  
  
> [!NOTE]
>  Viele der beschriebenen Szenarios gelten nur für bestimmte Geschäftsanforderungen oder Verarbeitungsanforderungen, aber die Planung der Unterstützung dynamischer Updates und die Verwendung der Fehlerbehandlung zählen zu den bewährten Vorgehensweise. Sie können damit die Routinglogik zur Laufzeit und die Wiederherstellung bei vorübergehenden Netzwerkfehlern und Kommunikationsfehlern sicherstellen.  
  
### <a name="service-versioning"></a>Dienstversionsverwaltung  
 Wenn Sie eine neue Version eines Diensts einführen, müssen Sie die ältere Version häufig noch so lange weiter pflegen, bis alle Clients auf den neuen Dienst umgestellt wurden. Dies ist besonders wichtig, wenn es sich bei dem Dienst um einen Prozess mit langer Laufzeit handelt, der Tage, Wochen oder sogar Monate dauert. Normalerweise erfordert dies die Implementierung einer neuen Endpunktadresse für den neuen Dienst, während der ursprüngliche Endpunkt für den vorherigen Dienst weiter verwaltet wird.  
  
 Mithilfe des Routingdiensts können Sie einen Endpunkt verfügbar machen, um Nachrichten von Clientanwendungen zu empfangen und dann jede Nachricht anhand ihres Inhalts an die richtige Endversion weiterzuleiten. Die Basisimplementierung erfordert das Hinzufügen eines benutzerdefinierten Headers zur Nachricht, der die Version des Diensts angibt, von der die Nachricht verarbeitet werden soll. Der Routingdienst kann den XPathMessageFilter verwenden, um jede Nachricht auf das Vorhandensein des benutzerdefinierten Headers zu überprüfen und die Nachricht an den entsprechenden Zielendpunkt weiterzuleiten.  
  
 Die Schritte zum Erstellen einer dienstversionskonfiguration finden Sie unter [so wird's gemacht: Dienstversionsverwaltung](../../../../docs/framework/wcf/feature-details/how-to-service-versioning.md).
  
### <a name="service-data-partitioning"></a>Dienstdatenpartitionierung  
 Beim Entwerfen einer verteilten Umgebung ist es häufig ratsam, die Verarbeitungslast auf mehrere Computer zu verteilen, um Hochverfügbarkeit sicherzustellen, die Verarbeitungslast für einzelne Computer zu verringern oder für eine bestimmte Teilmenge von Nachrichten dedizierte Ressourcen bereitzustellen. Der Routingdienst ist zwar kein Ersatz für eine dedizierte Lösung für den Lastenausgleich, aber Sie können die Funktion für das inhaltsbasierte Routing verwenden, um Nachrichten, die einander ansonsten ähnlich sind, an bestimmte Ziele weiterzuleiten. Es kann z. B. sein, dass Sie Nachrichten eines bestimmten Clients gesondert von den Nachrichten verarbeiten müssen, die Sie von anderen Clients empfangen.  
  
 Die Schritte zum Erstellen einer dienstdatenpartitionierung finden Sie unter [so wird's gemacht: Partitionieren von Daten in Service](../../../../docs/framework/wcf/feature-details/how-to-service-data-partitioning.md).  
  
### <a name="dynamic-routing"></a>Dynamisches Routing  
 Häufig ist es ratsam, die Routingkonfiguration zu ändern, um auf sich ändernde Geschäftsanforderungen zu reagieren. Dies kann das Hinzufügen einer Route zu einer neueren Version eines Diensts, das Ändern von Routingkriterien oder das Ändern des Zielendpunkts einer bestimmten Nachricht sein, an den der Filter Nachrichten weiterleitet. Mit dem Routingdienst können Sie dies mithilfe von <xref:System.ServiceModel.Routing.RoutingExtension> durchführen. Sie können damit zur Laufzeit ein neues RoutingConfiguration-Objekt bereitstellen. Die neue Konfiguration ist sofort wirksam. Sie gilt jedoch nur für die neuen Sitzungen, die vom Routingdienst verarbeitet werden.  
  
 Die Schritte zum Implementieren des dynamischen Routings finden Sie unter [so wird's gemacht: Dynamisches Update](../../../../docs/framework/wcf/feature-details/how-to-dynamic-update.md).
  
### <a name="multicast"></a>Multicast  
 Beim Weiterleiten von Nachrichten werden Nachrichten normalerweise an einen bestimmten Zielendpunkt weitergeleitet.  Es kann jedoch sein, dass Sie gelegentlich eine Kopie der Nachricht an mehrere Zielendpunkte weiterleiten müssen. Um das Routing per Multicast durchzuführen, müssen die folgenden Bedingungen erfüllt sein:  
  
-   Die Kanalform darf nicht vom Typ "Anforderung-Antwort" sein (unidirektional oder duplex ist jedoch möglich), weil dabei vorgegeben ist, dass die Clientanwendung als Antwort auf die Anforderung nur eine Antwort empfangen kann.  
  
-   Mehrere Filter müssen zurückgeben **"true"** beim Auswerten der Nachricht.  
  
 Wenn diese Bedingungen erfüllt sind, empfängt jeder Zielendpunkt, der einem Filter mit der Rückgabe "true" zugeordnet ist, eine Kopie der Nachricht.  
  
### <a name="protocol-bridging"></a>Protokollüberbrückung  
 Beim Weiterleiten von Nachrichten zwischen unterschiedlichen SOAP-Protokollen verwendet der Routingdienst WCF-APIs zum Konvertieren der Nachricht von einem Protokoll zum anderen. Dies tritt automatisch ein, wenn die vom Routingdienst verfügbar gemachten Dienstendpunkte ein anderes Protokoll verwenden als die Clientendpunkte, an die Nachrichten weitergeleitet werden. Es ist möglich, dieses Verhalten zu deaktivieren, falls keine standardmäßigen Protokolle verwendet sind. Sie müssen dann jedoch einen eigenen Überbrückungscode bereitstellen.
  
### <a name="error-handling"></a>Fehlerbehandlung  
 In einer verteilten Umgebung ist es nicht ungewöhnlich, dass vorübergehende Netzwerkfehler oder Kommunikationsfehler auftreten. Ohne einen Vermittlerdienst wie den Routingdienst ist die Clientanwendung für die Behandlung dieser Art von Fehlern zuständig. Falls die Clientanwendung keine spezielle Logik für wiederholte Versuche bei Netzwerk- oder Kommunikationsfehlern aufweist und keine alternativen Zielorte kennt, kann es zu Szenarios kommen, in denen eine Nachricht mehrere Male gesendet werden muss, bevor sie vom Zieldienst erfolgreich verarbeitet wird. Dies kann bei Kunden zu Unzufriedenheit mit der Anwendung führen, weil diese ggf. als unzuverlässig wahrgenommen wird.  
  
 Der Routingdienst versucht, dieses Szenario zu beheben, indem er robuste Fehlerbehandlungsfunktionen für Nachrichten bereitstellt, für die Netzwerk- oder Kommunikationsfehler auftreten. Wenn Sie eine Liste möglicher Zielendpunkte erstellen und diese Liste jedem Nachrichtenfilter zuordnen, beseitigen Sie die Fehlerquelle (Single Point of Failure), deren Ursache die Verwendung von nur einem möglichen Ziel ist. Bei einem Fehler versucht der Routingdienst, die Nachricht an den nächsten Endpunkt in der Liste zu übermitteln, bis die Nachricht übermittelt wurde, ein anderer Fehler als ein Kommunikationsfehler aufgetreten ist oder alle Endpunkte abgearbeitet wurden.  
  
 Die Schritte zum Konfigurieren der Fehlerbehandlung verwendet wird, finden Sie unter [so wird's gemacht: Fehlerbehandlung](../../../../docs/framework/wcf/feature-details/how-to-error-handling.md).
  
### <a name="in-this-section"></a>In diesem Abschnitt  
 [How To: Dienstversionsverwaltung](../../../../docs/framework/wcf/feature-details/how-to-service-versioning.md)  
  
 [How To: Dienstdatenpartitionierung](../../../../docs/framework/wcf/feature-details/how-to-service-data-partitioning.md)  
  
 [How To: Dynamisches Update](../../../../docs/framework/wcf/feature-details/how-to-dynamic-update.md)  
  
 [How To: Fehlerbehandlung](../../../../docs/framework/wcf/feature-details/how-to-error-handling.md)  
  
## <a name="see-also"></a>Siehe auch
- [Einführung in Routing](../../../../docs/framework/wcf/feature-details/routing-introduction.md)
