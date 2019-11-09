---
title: Resilienz der Azure-Plattform
description: Architektur von Cloud Native .net-apps für Azure | Resilienz der cloudinfrastruktur mit Azure
ms.date: 06/30/2019
ms.openlocfilehash: 02d661952c860da25442b0fa9fed0d5f93abe023
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "73841258"
---
# <a name="azure-platform-resiliency"></a>Resilienz der Azure-Plattform

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Das Entwickeln einer zuverlässigen Anwendung in der Cloud unterscheidet sich von der herkömmlichen lokalen Anwendungsentwicklung. Obwohl Sie in der Vergangenheit höhere Hardware zum zentralen hochskalieren erworben haben, können Sie in einer cloudumgebung horizontal hochskalieren. Anstatt zu versuchen, Fehler zu vermeiden, besteht das Ziel darin, die Auswirkungen zu minimieren und das System stabil zu halten.

Das heißt, zuverlässige cloudanwendungen zeigen verschiedene Merkmale an:

- Sie sind robust, werden von Problemen ordnungsgemäß wieder hergestellt und funktionieren weiterhin.
- Sie sind hoch verfügbar (ha) und werden in einem fehlerfreien Zustand ohne erhebliche Ausfallzeiten ausgeführt.

Wenn Sie wissen, wie diese Merkmale zusammenarbeiten und wie Sie sich auf die Kosten auswirken, ist es von entscheidender Bedeutung, eine zuverlässige, cloudbasierte Anwendung zu entwickeln. Im nächsten Schritt betrachten wir die Möglichkeiten, wie Sie Resilienz und Verfügbarkeit in Ihre cloudbasierten Anwendungen mit Features aus der Azure-Cloud entwickeln können.

## <a name="design-with-redundancy"></a>Entwerfen mit Redundanz

Fehler unterscheiden sich im Umfang der Auswirkungen. Ein Hardwarefehler (z. b. ein fehlerhafter Datenträger) kann sich auf einen einzelnen Knoten in einem Cluster auswirken. Ein fehlerhafter Netzwerk Switch kann sich auf ein gesamtes servergestell auswirken. Weniger häufige Fehler, wie z. b. Stromausfälle, könnten ein gesamtes Rechenzentrum stören. In seltenen Fällen steht eine gesamte Region nicht mehr zur Verfügung.

[Redundanz](https://docs.microsoft.com/azure/architecture/guide/design-principles/redundancy) ist eine Möglichkeit zum Bereitstellen von Anwendungs Resilienz. Die genaue erforderliche Redundanz Ebene hängt von Ihren Geschäftsanforderungen ab und wirkt sich sowohl auf die Kosten als auch auf die Komplexität Ihres Systems aus. Beispielsweise ist eine Bereitstellung in mehreren Regionen teurer und komplexer zu verwalten als eine Bereitstellung in einer einzelnen Region. Sie benötigen betriebliche Verfahren zum Verwalten von Failover und Failback. Die zusätzlichen Kosten und die Komplexität können für einige Geschäftsszenarien und nicht für andere gerechtfertigt werden.

Um Redundanz zu entwerfen, müssen Sie die kritischen Pfade in der Anwendung identifizieren und dann bestimmen, ob an jedem Punkt im Pfad Redundanz vorliegt? Wenn bei einem Subsystem ein Fehler auftritt, führt die Anwendung ein Failover zu einem anderen aus? Schließlich benötigen Sie ein klares Verständnis der in der Azure-cloudplattform integrierten Features, die Sie nutzen können, um Ihre Redundanz Anforderungen zu erfüllen. Im folgenden finden Sie Empfehlungen für die Architektur der Redundanz:

- *Stellen Sie mehrere Instanzen von Diensten bereit.* Wenn Ihre Anwendung von einer einzelnen Instanz eines Dienstanbieter abhängig ist, wird ein Single Point of Failure erstellt. Durch die Bereitstellung mehrerer Instanzen wird sowohl die Resilienz als auch die Skalierbarkeit verbessert. Beim Hosten im Azure Kubernetes-Dienst können Sie redundante Instanzen (Replikat Gruppen) deklarativ in der Kubernetes-Manifest-Datei konfigurieren. Der Wert Replikat Anzahl kann Programm gesteuert, im Portal oder mithilfe der Features für die automatische Skalierung verwaltet werden, die später erläutert werden.

- *Nutzung eines Load Balancers.* Beim Lastenausgleich werden die Anforderungen Ihrer Anwendung an fehlerfreie Dienst Instanzen verteilt, und fehlerhafte Instanzen werden automatisch aus der Rotation entfernt. Beim Bereitstellen in Kubernetes kann der Lastenausgleich in der Kubernetes-Manifest-Datei im Abschnitt Dienste angegeben werden.

- *Planen Sie die Bereitstellung in mehreren Regionen.* Wenn Ihre Anwendung in einer einzelnen Region bereitgestellt wird und die Region nicht mehr verfügbar ist, wird Ihre Anwendung ebenfalls nicht mehr verfügbar sein. Dies ist unter den Bedingungen der Vereinbarungen zum Service Level Ihrer Anwendung möglicherweise nicht akzeptabel. Sie sollten stattdessen die Anwendung und die zugehörigen Dienste in mehreren Regionen bereitstellen. Beispielsweise wird ein Azure Kubernetes Service-Cluster (AKS) in einer einzelnen Region bereitgestellt. Um Ihr System vor einem regionalen Ausfall zu schützen, können Sie Ihre Anwendung in mehreren AKS-Clustern in unterschiedlichen Regionen bereitstellen und das Feature " [Regions](https://buildazure.com/2017/01/06/azure-region-pairs-explained/) Paare" verwenden, um Platt Form Updates zu koordinieren und den Wiederherstellungs Aufwand zu priorisieren.

- *Aktivieren Sie die [georeplikation](https://docs.microsoft.com/azure/sql-database/sql-database-active-geo-replication).* Bei der georeplikation für Dienste wie Azure SQL-Datenbank und Cosmos DB werden sekundäre Replikate Ihrer Daten in mehreren Regionen erstellt. Obwohl beide Dienste automatisch Daten innerhalb derselben Region replizieren, schützt die georeplikation Sie vor einem regionalen Ausfall, da Sie ein Failover auf eine sekundäre Region durchführen können. Eine weitere bewährte Vorgehensweise für die georeplikation ist das Speichern von Container Images. Zum Bereitstellen eines Diensts in AKS müssen Sie das Image speichern und aus einem Repository abrufen. Azure Container Registry in AKS integrieren und Container Images sicher speichern können. Um die Leistung und Verfügbarkeit zu verbessern, sollten Sie Ihre Images in einer Registrierung in jeder Region, in der Sie einen AKS-Cluster besitzen, georeplizieren. Jeder AKS-Cluster ruft dann Container Images aus der lokalen Container Registrierung in seiner Region ab, wie in Abbildung 6-6 dargestellt:

![Regions übergreifende replizierte Ressourcen](./media/replicated-resources.png)

**Abbildung 6-6**. Regions übergreifende replizierte Ressourcen

- *Implementieren Sie einen Lastenausgleich für den DNS-Datenverkehr.* [Azure Traffic Manager](https://docs.microsoft.com/azure/traffic-manager/traffic-manager-overview) bietet hohe Verfügbarkeit für kritische Anwendungen durch Lastenausgleich auf DNS-Ebene. Er kann Datenverkehr an verschiedene Regionen weiterleiten, basierend auf Geografie, Cluster Antwortzeit und sogar der Integrität des Anwendungs Endpunkts. Beispielsweise kann Azure Traffic Manager Kunden an die nächstgelegene AKS-Cluster-und Anwendungs Instanz weiterleiten. Wenn Sie über mehrere AKS-Cluster in verschiedenen Regionen verfügen, verwenden Sie Traffic Manager, um zu steuern, wie der Datenverkehr zu den in den einzelnen Clustern betriebenen Anwendungen verläuft. In Abbildung 6-7 wird dieses Szenario veranschaulicht.

![AKS und Azure-Traffic Manager](./media/aks-traffic-manager.png)

**Abbildung 6-7**. AKS und Azure-Traffic Manager

## <a name="design-for-scalability"></a>Entwurf für die Skalierbarkeit

Die Cloud gedeiht bei der Skalierung. Die Möglichkeit, Systemressourcen zu vergrößern oder zu verringern, um das erhöhen/verringern der System Auslastung zu beheben, ist ein wichtiger Grund Satz der Azure-Cloud. Um eine Anwendung effektiv zu skalieren, benötigen Sie jedoch ein Verständnis der Skalierungs Features der einzelnen Azure-Dienste, die Sie in Ihre Anwendung einschließen.  Hier finden Sie Empfehlungen für eine effektive Implementierung der Skalierung in Ihrem System.

- *Entwurf für die Skalierung.* Eine Anwendung muss für die Skalierung entworfen werden. Zum Starten von sollten Dienste zustandslos sein, damit Anforderungen an eine beliebige Instanz weitergeleitet werden können. Die Verwendung von Zustands losen Diensten bedeutet auch, dass das Hinzufügen oder Entfernen einer Instanz die aktuellen Benutzer nicht beeinträchtigt.

- *Partitionierungs Arbeits Auslastungen*. Durch das Zerlegen von Domänen in unabhängige, eigenständige mikrodienste kann jeder Dienst unabhängig von anderen skaliert werden. In der Regel verfügen Dienste über unterschiedliche Anforderungen an die Skalierbarkeit und Anforderungen. Mithilfe der Partitionierung können Sie nur skalieren, was ohne unnötige Kosten der Skalierung einer gesamten Anwendung skaliert werden muss.

- *Bevorzugen Sie horizontales hochskalieren.* Cloudbasierte Anwendungen bevorzugen das horizontale hochskalieren von Ressourcen im Gegensatz zum horizontalen hochskalieren. Das horizontale hochskalieren (auch als horizontale Skalierung bezeichnet) umfasst das Hinzufügen von mehr Dienst Ressourcen zu einem vorhandenen System, um ein gewünschtes Leistungsniveau zu erreichen und freizugeben. Das zentrale hochskalieren (auch als vertikale Skalierung bezeichnet) umfasst das Ersetzen vorhandener Ressourcen durch leistungsfähigere Hardware (mehr Datenträger-, Arbeitsspeicher-und verarbeitungskerne). Das horizontale hochskalieren kann automatisch mit den Features für die automatische Skalierung aufgerufen werden Durch horizontales hochskalieren auf mehrere Ressourcen wird dem gesamten System auch Redundanz hinzugefügt. Das horizontale hochskalieren einer einzelnen Ressource ist in der Regel teurer als das horizontale hochskalieren über viele kleinere Ressourcen. In Abbildung 6-8 werden die beiden Ansätze veranschaulicht:

![Zentrales hochskalieren im Vergleich](./media/scale-up-scale-out.png)

**Abbildung 6-8.** Zentrales hochskalieren im Vergleich

- *Proportional skalieren.* Berücksichtigen Sie beim Skalieren eines Dienstanbieter die *Ressourcen Sätze*. Welche Auswirkung haben Sie auf Back-End-Datenspeicher, Caches und abhängige Dienste, wenn Sie einen bestimmten Dienst drastisch horizontal hochskalieren? Einige Ressourcen, z. b. Cosmos DB, können proportional horizontal hochskaliert werden, viele andere hingegen nicht. Sie möchten sicherstellen, dass Sie eine Ressource nicht auf einen Punkt horizontal hochskalieren, an dem Sie andere zugeordnete Ressourcen erschöpft.

- *Vermeiden Sie Affinität.* Eine bewährte Vorgehensweise besteht darin sicherzustellen, dass ein Knoten keine lokale Affinität erfordert, die *häufig als "* Kurznotiz" bezeichnet wird. Eine Anforderung sollte an eine beliebige Instanz weitergeleitet werden können. Wenn Sie den Zustand beibehalten müssen, sollte er in einem verteilten Cache gespeichert werden, z. b. [Azure redis Cache](https://azure.microsoft.com/services/cache/).

- *Nutzen Sie Features für die automatische Skalierung von Plattformen.* Verwenden Sie die integrierten Features für die automatische Skalierung, wann immer möglich, anstelle von benutzerdefinierten oder Drittanbieter Mechanismen. Verwenden Sie nach Möglichkeit geplante Skalierungs Regeln, um sicherzustellen, dass Ressourcen ohne Startverzögerung verfügbar sind, und fügen Sie den Regeln nach Bedarf eine reaktive automatische Skalierung hinzu, um unerwartete Änderungen an der Nachfrage zu bewältigen. Weitere Informationen finden Sie unter [Leitfaden für die automatische Skalierung](https://docs.microsoft.com/azure/architecture/best-practices/auto-scaling).

- *Horizontales hochskalieren.* Eine abschließende Vorgehensweise wäre das horizontale hochskalieren, sodass Sie schnell unmittelbare Spitzen im Datenverkehr erreichen können, ohne das Geschäft zu verlieren. Und dann skalieren (d. h. nicht benötigte Instanzen entfernen), um das System stabil zu halten. Eine einfache Möglichkeit, dies zu implementieren, besteht darin, den kühl Zeitraum festzulegen. Dies ist die Zeit, die zwischen Skalierungs Vorgängen gewartet werden soll, auf fünf Minuten für das Hinzufügen von Ressourcen und bis zu 15 Minuten zum Entfernen von Instanzen.

## <a name="built-in-retry-in-services"></a>Integrierter Wiederholungsversuch in Diensten

Wir haben empfohlen, programmatische Wiederholungs Vorgänge in einem früheren Abschnitt zu implementieren. Beachten Sie, dass viele Azure-Dienste und die zugehörigen Client-sdken auch Wiederholungs Mechanismen beinhalten. In der folgenden Liste sind die Wiederholungs Funktionen in den vielen Azure-Diensten zusammengefasst, die in diesem Buch erläutert werden:

- *Azure Cosmos DB.* Die <xref:Microsoft.Azure.Documents.Client.DocumentClient>-Klasse aus der Client-API gibt automatisch fehlgeschlagene Versuche zurück. Die Anzahl der Wiederholungen und die maximale Wartezeit sind konfigurierbar. Von der Client-API ausgelöste Ausnahmen sind entweder Anforderungen, die die Wiederholungs Richtlinie überschreiten, oder nicht vorübergehende Fehler.

- *Azure Redis Cache.* Der redis stackexchange-Client verwendet eine Verbindungs-Manager-Klasse, die Wiederholungs Versuche für fehlgeschlagene Versuche einschließt. Die Anzahl der Wiederholungs Versuche, die spezifische Wiederholungs Richtlinie und die Wartezeit sind alle konfigurierbar.

- *Azure Service Bus.* Der Service Bus Client stellt eine [retrypolicy-Klasse](xref:Microsoft.ServiceBus.RetryPolicy) zur Verfügung, die mit einem Backoff-Intervall, einer Wiederholungs Anzahl und <xref:Microsoft.ServiceBus.RetryExponential.TerminationTimeBuffer>konfiguriert werden kann, die die maximale Zeit angibt, die ein Vorgang dauern kann. Die Standard Richtlinie ist neun maximale Wiederholungs Versuche mit einem Backoff-Zeitraum von 30 Sekunden zwischen den versuchen.

- *Azure SQL-Datenbank.* Wiederholungs Unterstützung wird bei Verwendung der [Entity Framework Core](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency) Bibliothek bereitgestellt.

- *Azure Storage.* Die Speicher Client Bibliothek unterstützt Wiederholungs Vorgänge. Die Strategien variieren in Azure Storage-Tabellen,-BLOB-und-Warteschlangen. Außerdem wechseln Alternative Wiederholungen zwischen primären und sekundären Speicherdienst Standorten, wenn das Feature für die georedundanz aktiviert ist.

- *Azure-Event Hubs.* Die Event Hub-Client Bibliothek verfügt über eine retrypolicy-Eigenschaft, die eine konfigurierbare exponentielle Backoff-Funktion enthält.

>[!div class="step-by-step"]
>[Zurück](application-resiliency-patterns.md)
>[Weiter](resilient-communications.md)
