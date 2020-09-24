---
title: Resiliente Kommunikation
description: Architektur von Cloud Native .net-apps für Azure | Robuste Kommunikation
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 18b26223634efc5c05f680d0cbb7c8cbc2490a59
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166039"
---
# <a name="resilient-communications"></a>Robuste Kommunikation

In diesem Buch haben wir einen auf microservices basierenden Architekturansatz eingeführt. Obwohl eine solche Architektur wichtige Vorteile bietet, stellt Sie viele Herausforderungen dar:

- *Out-of-Process-Netzwerkkommunikation.* Jeder-mikrodienst kommuniziert über ein Netzwerkprotokoll, in dem Netzwerk Überlastung, Latenz und vorübergehende Fehler eingeführt werden.

- *Dienstermittlung:* Wie erkennen und kommunizieren die mikrodienste bei der Ausführung in einem Cluster von Computern mit ihren eigenen IP-Adressen und Ports?

- *Resilienz.* Wie verwalten Sie kurzlebige Ausfälle, und halten Sie das System stabil?

- *Lastenausgleich:* Wie wird eingehender Datenverkehr auf mehrere Instanzen eines-mikrodienstanzen verteilt?

- *Sicherheit.* Wie werden Sicherheitsprobleme wie die Verschlüsselung auf Transport Ebene und die Zertifikat Verwaltung erzwungen?

- *Verteilte Überwachung.* -Wie korrelieren und erfassen Sie die Rückverfolgbarkeit und Überwachung für eine einzelne Anforderung über mehrere nutzende mikrodienste?

Sie können diese Probleme mit verschiedenen Bibliotheken und Frameworks beheben, aber die Implementierung kann aufwendig, komplex und zeitaufwändig sein. Außerdem verfügen Sie über Infrastrukturprobleme, die mit der Geschäftslogik gekoppelt sind.

## <a name="service-mesh"></a>Dienst Gitter

Ein besserer Ansatz ist eine sich entwickelnde Technologie mit dem *Dienst Mesh*. Ein [Dienst Netz](https://www.nginx.com/blog/what-is-a-service-mesh/) ist eine konfigurierbare Infrastruktur Schicht mit integrierten Funktionen für die Dienst Kommunikation und die anderen oben genannten Herausforderungen. Sie entkoppelt diese Probleme, indem Sie Sie in einen Dienst Proxy verschieben. Der Proxy wird in einem separaten Prozess (als [Sidecar](/azure/architecture/patterns/sidecar)bezeichnet) bereitgestellt, um die Isolation von Geschäfts Code bereitzustellen. Der Sidecar ist jedoch mit dem Dienst verknüpft, und er wird mit dem Dienst erstellt und hat seinen Lebenszyklus gemeinsam. In Abbildung 6-7 wird dieses Szenario veranschaulicht.

![Dienst Netz mit einem seitigen Fahrzeug](./media/service-mesh-with-side-car.png)

**Abbildung 6-7**. Dienst Netz mit einem seitigen Fahrzeug

Beachten Sie in der obigen Abbildung, wie der Proxy die Kommunikation zwischen den-und dem-Cluster abfängt und verwaltet.

Ein Dienst Netz wird logisch in zwei unterschiedliche Komponenten aufgeteilt: eine [Datenebene](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc) und eine [Steuerungsebene](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc). In Abbildung 6-8 werden diese Komponenten und ihre Zuständigkeiten veranschaulicht.

![Dienstmesh-Steuerung und Datenebene](./media/istio-control-and-data-plane.png)

**Abbildung 6-8.** Dienstmesh-Steuerung und Datenebene

Nach der Konfiguration ist ein Dienst Mesh hoch funktionsfähig. Es kann einen entsprechenden Pool von Instanzen von einem Dienst Ermittlungs Endpunkt abrufen. Das Mesh kann dann eine Anforderung an eine bestimmte Instanz senden und dabei die Latenz und den Antworttyp des Ergebnisses aufzeichnen. Ein Mesh kann die Instanz auswählen, die höchstwahrscheinlich eine schnelle Antwort auf der Grundlage vieler Faktoren zurückgibt, einschließlich der beobachteten Latenzzeit für aktuelle Anforderungen.

Wenn eine Instanz nicht reagiert oder fehlschlägt, wird die Anforderung vom Mesh auf einer anderen Instanz wiederholt. Wenn Fehler zurückgegeben werden, entfernt ein Mesh die Instanz aus dem Lasten Ausgleichs Pool und gibt Sie nach ihrer Heals erneut aus. Wenn für eine Anforderung ein Timeout auftritt, kann ein Mesh fehlschlagen und dann die Anforderung wiederholen. Ein Mesh erfasst und gibt Metriken und verteilte Ablauf Verfolgung an ein zentralisiertes metriksystem aus.

## <a name="istio-and-envoy"></a>Istio und Gesandter

Während ein paar Dienst Gitter Optionen aktuell vorhanden sind, ist [istio](https://istio.io/docs/concepts/what-is-istio/) zum Zeitpunkt der Erstellung dieses Artikels am beliebtesten. Istio ist ein Joint Venture von IBM, Google und lyft. Dabei handelt es sich um ein Open Source-Angebot, das in eine neue oder vorhandene verteilte Anwendung integriert werden kann. Die Technologie stellt eine konsistente und umfassende Lösung für das sichern, verbinden und Überwachen von Mikro Diensten bereit. Zu den Features gehören:

- Sichere Dienst-zu-Dienst-Kommunikation in einem Cluster mit starker Identitäts basierter Authentifizierung und Autorisierung.
- Automatischer Lastenausgleich für http-, [GrpC](https://grpc.io/)-, WebSocket-und TCP-Datenverkehr.
- Differenzierte Kontrolle über das Datenverkehrs Verhalten durch umfangreiche Routing Regeln, Wiederholungen, Failover und Fehler Injektion.
- Eine austauschbare Richtlinien Schicht und Konfigurations-API, die Zugriffs Steuerungen, Begrenzung der Datenübertragungsrate und Kontingente unterstützt.
- Automatische Metriken, Protokolle und Ablauf Verfolgungen für den gesamten Datenverkehr in einem Cluster, einschließlich Cluster Einzug und-Ausgang.

Eine Schlüsselkomponente für eine istio-Implementierung ist ein Proxy Dienst, der den [Proxy](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy)Dienst als Anspruch hat. Sie wird neben den einzelnen Diensten ausgeführt und bietet eine plattformunabhängige Grundlage für die folgenden Features:

- Dynamische Dienst Ermittlung.
- Lastenausgleich.
- TLS-Beendigung.
- HTTP-und GrpC-Proxys.
- Resilienz der Schutzschalter.
- Integritätsprüfungen.
- Parallele Aktualisierungen mit [Canary](https://martinfowler.com/bliki/CanaryRelease.html) -bereit Stellungen.

Wie bereits erwähnt, wird der Gesandte als Sidecar für jeden der einzelnen mikrodienste im Cluster bereitgestellt.

## <a name="integration-with-azure-kubernetes-services"></a>Integration in Azure Kubernetes Services

Die Azure-Cloud bietet istio an und bietet direkten Support für Sie in Azure Kubernetes Services. Die folgenden Links helfen Ihnen beim Einstieg:

- [Installieren von istio in AKS](/azure/aks/istio-install)
- [Verwenden von AKS und istio](/azure/aks/istio-scenario-routing)

### <a name="references"></a>References

- [Polly](http://www.thepollyproject.org/)

- [Wiederholungsmuster](/azure/architecture/patterns/retry)

- [Trennschalter-Muster](/azure/architecture/patterns/circuit-breaker)

- [Whitepaper zur Resilienz in Azure](https://azure.microsoft.com/mediahandler/files/resourcefiles/resilience-in-azure-whitepaper/Resilience%20in%20Azure.pdf)

- [Netzwerk Latenz](https://www.techopedia.com/definition/8553/network-latency)

- [Redundanz](/azure/architecture/guide/design-principles/redundancy)

- [georeplikation](/azure/sql-database/sql-database-active-geo-replication)

- [Azure Traffic Manager](/azure/traffic-manager/traffic-manager-overview)

- [Anleitungen für die automatische Skalierung](/azure/architecture/best-practices/auto-scaling)

- [Istio](https://istio.io/docs/concepts/what-is-istio/)

- [Proxy Proxy](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy)

>[!div class="step-by-step"]
>[Zurück](infrastructure-resiliency-azure.md)
>[Weiter](monitoring-health.md)
