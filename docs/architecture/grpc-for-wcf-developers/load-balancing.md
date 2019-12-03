---
title: Lastenausgleich von GrpC-GrpC für WCF-Entwickler
description: Auswählen eines Load Balancers zum Arbeiten mit GrpC-Diensten.
ms.date: 09/02/2019
ms.openlocfilehash: 215c0983146bbf9168f01956d64733f80cea6faf
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711173"
---
# <a name="load-balancing-grpc"></a>Lastenausgleich für GrpC

Eine typische Bereitstellung einer GrpC-Anwendung umfasst eine Reihe identischer Instanzen des Dienstanbieter, die Resilienz und horizontale Skalierbarkeit gewährleisten. Der Lastenausgleich verteilt eingehende Anforderungen auf diese Instanzen, um die vollständige Nutzung aller verfügbaren Ressourcen zu ermöglichen. Um diesen Lastenausgleich für den Client unsichtbar zu machen, ist es üblich, einen Proxy Server für den Lastenausgleich zu verwenden, um Anforderungen von Clients zu verarbeiten und an Back-End-Instanzen weiterzuleiten.

Lasten Ausgleichs Module werden entsprechend der *Ebene* klassifiziert, auf der Sie arbeiten. Schicht 4-Lasten Ausgleichs Module funktionieren auf der *Transport* Ebene, z. b. mit TCP-Sockets, Verbindungen und Paketen. Load Balancer der Ebene 7 funktionieren auf *Anwendungs* Ebene, insbesondere die Verarbeitung von http/2-Anforderungen für GrpC-Anwendungen.

## <a name="l4-load-balancers"></a>L4-Lasten Ausgleichs Module

Ein L4-Lasten Ausgleichs Modul akzeptiert eine TCP-Verbindungsanforderung von einem Client, öffnet eine weitere Verbindung mit einer der Back-End-Instanzen und kopiert Daten zwischen den beiden Verbindungen ohne wirkliche Verarbeitung. L4 bietet hervorragende Leistung und geringe Latenz, aber nur sehr wenig Kontrolle oder Intelligenz. Solange der Client die Verbindung geöffnet hält, werden alle Anforderungen an dieselbe Back-End-Instanz weitergeleitet.

 [Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/) ist ein Beispiel für einen L4 Load Balancer.

## <a name="l7-load-balancers"></a>L7-Lasten Ausgleichs Module

Ein L7-Lastenausgleich analysiert eingehende HTTP/2-Anforderungen und übergibt sie an Back-End-Instanzen auf Anforderung-für-Anforderung-Basis, unabhängig davon, wie lange die Verbindung vom Client aufbewahrt wird.

Beispiele für L7-Lasten Ausgleichs Module:

- [NGINX](https://www.nginx.com/)
- [HAProxy](https://www.haproxy.com/)
- [Traefik](https://traefik.io/)

Als Faustregel sind L7-Lasten Ausgleichs Module die beste Wahl für GrpC und andere http/2-Anwendungen (und in der Regel für HTTP-Anwendungen). L4-Lasten Ausgleichs Module *funktionieren* mit GrpC-Anwendungen, sind aber vor allem dann nützlich, wenn eine geringe Latenz und ein geringer Verwaltungsaufwand wichtig sind.

> [!IMPORTANT]
> Zum Zeitpunkt der Erstellung dieses Artikels unterstützen einige L7-Lasten Ausgleichs Module nicht alle Teile der http/2-Spezifikation, die für GrpC-Dienste erforderlich sind, wie z. b. nachfolgende Header.

Wenn Sie die TLS-Verschlüsselung verwenden, können Lasten Ausgleichs Module die TLS-Verbindung beenden und unverschlüsselte Anforderungen an die Back-End-Anwendung übergeben, oder Sie können die verschlüsselte Anforderung an Sie übergeben. In jedem Fall muss der Load Balancer mit dem öffentlichen und privaten Schlüssel des Servers konfiguriert werden, damit er Anforderungen für die Verarbeitung entschlüsseln kann.

Informationen dazu, wie Sie diese für die Verarbeitung von http/2-Anforderungen mit ihren Back-End-Diensten konfigurieren, finden Sie in der Dokumentation für Ihren bevorzugten Load Balancer.

## <a name="load-balancing-within-kubernetes"></a>Lastenausgleich innerhalb von Kubernetes

Weitere Informationen zum Lastenausgleich zwischen internen Diensten auf Kubernetes finden Sie im [Abschnitt zu Service-Netzen](service-mesh.md) .

>[!div class="step-by-step"]
>[Zurück](service-mesh.md)
>[Weiter](application-performance-management.md)
