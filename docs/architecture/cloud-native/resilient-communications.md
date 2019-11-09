---
title: Resiliente Kommunikation
description: Architektur von Cloud Native .net-apps für Azure | Robuste Kommunikation
ms.date: 06/30/2019
ms.openlocfilehash: 324f5426af1c892db73aa6fc2336a19b7a8e499e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "73841222"
---
# <a name="resilient-communications"></a>Robuste Kommunikation

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

In diesem Buch haben wir die Vorzüge der Umstellung auf den herkömmlichen monolithischen Anwendungs Entwurf und die Umsetzung einer auf microservices basierenden Architektur, in der ein Satz verteilter, eigenständiger Dienste unabhängig ausgeführt wird, und die Kommunikation mit jedem andere verwendet Standard Kommunikationsprotokolle wie http und HTTPS. Obwohl eine solche Architektur Ihnen viele wichtige Vorteile bietet, stellt Sie auch viele Herausforderungen dar. Beachten Sie z. b. die folgenden Probleme:

- *Out-of-Process-Netzwerkkommunikation.* Jeder Dienst kommuniziert über ein Netzwerkprotokoll, in dem Netzwerk Überlastung, Latenz und vorübergehende Fehler eingeführt werden.
- *Dienst Ermittlung.* Wenn jeder Dienst in einem Cluster von Computern mit einer eigenen IP-Adresse und einem eigenen Port ausgeführt wird, wie werden Dienste erkannt und miteinander kommunizieren?
- *Resilienz.* Wie verwalten Sie kurzlebige Ausfälle, und halten Sie das System stabil?
- *Lastenausgleich.* Wie erfolgt der eingehende Datenverkehr auf mehrere Instanzen eines Dienstanbieter?
- *Sicherheit.* Wie werden Sicherheitsprobleme wie die Verschlüsselung auf Transport Ebene und die Zertifikat Verwaltung erzwungen?
- *Verteilte Überwachung.* -Wie korrelieren und erfassen Sie die Rückverfolgbarkeit und Überwachung für eine einzelne Anforderung über mehrere verarbeitende Dienste?

Obwohl diese Probleme mit verschiedenen Bibliotheken und Frameworks angegangen werden können, kann die Implementierung in Ihre Codebasis teuer, komplex und zeitaufwändig sein. Außerdem verfügen Sie am Ende über eine Lösung, bei der Infrastrukturprobleme an die Geschäftslogik gekoppelt sind.

## <a name="service-mesh"></a>Dienst Gitter

Ein besserer Ansatz besteht darin, eine neue und schnell entwickelnde Technologie mit dem *Service Mesh*zu betrachten. Ein [Dienst Netz](https://www.nginx.com/blog/what-is-a-service-mesh/) ist eine konfigurierbare Infrastruktur Schicht mit integrierten Funktionen zum Verarbeiten der Dienst Kommunikation und vielen der oben genannten Herausforderungen. Sie entkoppelt diese Probleme von Ihrem Geschäfts Code und verschiebt Sie in einen Dienst Proxy, eine Instanz von, die die einzelnen Dienste begleitet. Der Service Mesh-Proxy wird häufig als [Sidecar-Muster](https://docs.microsoft.com/azure/architecture/patterns/sidecar)bezeichnet und wird in einem separaten Prozess bereitgestellt, um Isolation und Kapselung von Ihrem Geschäfts Code bereitzustellen. Der Proxy ist jedoch eng mit dem Dienst verknüpft, der zusammen mit dem Dienst erstellt und dessen Lebenszyklus gemeinsam genutzt wird. In Abbildung 6-9 wird dieses Szenario veranschaulicht.

![Dienst Netz mit einem seitigen Fahrzeug](./media/service-mesh-with-side-car.png)

**Abbildung 6-9**. Dienst Netz mit einem seitigen Fahrzeug

Beachten Sie in der obigen Abbildung, wie der Proxy die Kommunikation zwischen den-und dem-Cluster abfängt und verwaltet.

Ein Dienst Netz wird logisch in zwei unterschiedliche Komponenten aufgeteilt: eine [Datenebene](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc) und eine [Steuerungsebene](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc). In Abbildung 6-10 werden diese Komponenten und ihre Zuständigkeiten veranschaulicht.

![Dienstmesh-Steuerung und Datenebene](./media/istio-control-and-data-plane.png)

**Abbildung 6-10.** Dienstmesh-Steuerung und Datenebene

Nach der Konfiguration ist ein Dienst Mesh hoch funktionsfähig. Es kann einen entsprechenden Pool von Instanzen von einem Dienst Ermittlungs Endpunkt abrufen. Anschließend kann eine Anforderung an eine bestimmte Instanz gesendet werden, wobei die Latenz und der Antworttyp des Ergebnisses aufgezeichnet werden. Ein Mesh kann die Instanz auswählen, die höchstwahrscheinlich eine schnelle Antwort auf der Grundlage vieler Faktoren zurückgibt, einschließlich der beobachteten Latenzzeit für aktuelle Anforderungen.

Wenn eine Instanz nicht reagiert oder fehlschlägt, kann das Mesh die Anforderung auf einer anderen Instanz wiederholen. Wenn ein Pool konsistent Fehler zurückgibt, kann ein Mesh ihn aus dem Lasten Ausgleichs Pool entfernen, damit er in regelmäßigen Abständen später wiederholt wird. Wenn für eine Anforderung ein Timeout auftritt, kann ein Mesh fehlschlagen und dann die Anforderung wiederholen. Ein Mesh erfasst Verhalten in Form von Metriken und verteilten Ablauf Verfolgungs Daten, die dann an ein zentralisiertes metriksystem ausgegeben werden können.

## <a name="istio-and-envoy"></a>Istio und Gesandter

Obwohl zurzeit einige wenige Dienst Gitter Optionen vorhanden sind, ist [istio](https://istio.io/docs/concepts/what-is-istio/) zum Zeitpunkt der Erstellung dieses Artikels am beliebtesten. Ein Joint Venture von IBM, Google und lyft ist ein Open Source-Angebot, das in eine neue oder vorhandene verteilte Anwendung integriert werden kann. Er bietet eine konsistente und umfassende Lösung für das sichern, verbinden und Überwachen von-Diensten. Zu den Features gehören:

- Sichere Dienst-zu-Dienst-Kommunikation in einem Cluster mit starker Identitäts basierter Authentifizierung und Autorisierung.
- Automatischer Lastenausgleich für http-, [GrpC](https://grpc.io/)-, WebSocket-und TCP-Datenverkehr.
- Differenzierte Kontrolle über das Datenverkehrs Verhalten durch umfangreiche Routing Regeln, Wiederholungen, Failover und Fehler Injektion.
- Eine austauschbare Richtlinien Schicht und Konfigurations-API, die Zugriffs Steuerungen, Begrenzung der Datenübertragungsrate und Kontingente unterstützt.
- Automatische Metriken, Protokolle und Ablauf Verfolgungen für den gesamten Datenverkehr in einem Cluster, einschließlich Cluster Einzug und-Ausgang.

Eine Schlüsselkomponente für eine istio-Implementierung ist ein Proxy Dienst, der den [Proxy](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy)Dienst als Anspruch hat. Aus lyft und anschließenden Beitrag zur [Cloud Native Computing Foundation](https://www.cncf.io/) (erläutert in Kapitel 1) wird der Proxy Proxy neben den einzelnen Diensten ausgeführt und stellt eine plattformunabhängige Grundlage für die folgenden Features bereit:

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

- [Installieren von istio in AKS](https://docs.microsoft.com/azure/aks/istio-install)
- [Verwenden von AKS und istio](https://docs.microsoft.com/azure/aks/istio-scenario-routing)

>[!div class="step-by-step"]
>[Zurück](infrastructure-resiliency-azure.md)
>[Weiter](monitoring-health.md)
