---
title: Lastenausgleich von GrpC-GrpC für WCF-Entwickler
description: Auswählen eines Load Balancers zum Arbeiten mit GrpC-Diensten.
ms.date: 09/02/2019
ms.openlocfilehash: 070fc7fda73988302d15c8cec12b1ac359641317
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967453"
---
# <a name="load-balancing-grpc"></a>Lastenausgleich für GrpC

Eine typische Bereitstellung einer GrpC-Anwendung umfasst eine Reihe identischer Instanzen des Dienstanbieter, die Resilienz und horizontale Skalierbarkeit gewährleisten. Lastenausgleich verteilter eingehender Anforderungen über diese Instanzen hinweg, um die vollständige Nutzung aller verfügbaren Ressourcen zu ermöglichen. Um diesen Lastenausgleich für den Client unsichtbar zu machen, ist es üblich, einen Proxy Server für den Lastenausgleich zu verwenden, um Anforderungen von Clients zu verarbeiten und an Back-End-Instanzen weiterzuleiten.

Lasten Ausgleichs Module werden entsprechend der *Ebene* klassifiziert, auf der Sie arbeiten. Schicht 4-Lasten Ausgleichs Module funktionieren auf der *Transport* Ebene, z. b. mit TCP-Sockets, Verbindungen und Paketen. Load Balancer der Ebene 7 funktionieren auf *Anwendungs* Ebene, insbesondere die Verarbeitung von http/2-Anforderungen für GrpC-Anwendungen.

## <a name="l4-load-balancers"></a>L4-Lasten Ausgleichs Module

Ein L4-Lasten Ausgleichs Modul akzeptiert eine TCP-Verbindungsanforderung von einem Client, öffnet eine weitere Verbindung mit einer der Back-End-Instanzen und kopiert Daten zwischen den beiden Verbindungen ohne wirkliche Verarbeitung. L4 bietet hervorragende Leistung und geringe Latenz, aber nur sehr wenig Kontrolle oder Intelligenz. Solange der Client die Verbindung geöffnet hält, werden alle Anforderungen an dieselbe Back-End-Instanz weitergeleitet.

Ein Beispiel für einen L4 Load Balancer ist die [Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/).

## <a name="l7-load-balancers"></a>L7-Lasten Ausgleichs Module

Ein L7-Lastenausgleich analysiert eingehende HTTP/2-Anforderungen und übergibt sie an Back-End-Instanzen auf Anforderung-für-Anforderung-Basis, unabhängig davon, wie lange die Verbindung vom Client aufbewahrt wird.

Beispiele für L7-Lasten Ausgleichs Module:

- [Nginx](https://www.nginx.com/)
- [HAproxy](https://www.haproxy.com/)
- [Traefik](https://traefik.io/)

Als Faustregel sind L7-Lasten Ausgleichs Module die beste Wahl für GrpC und andere http/2-Anwendungen (und in der Regel für HTTP-Anwendungen). L4-Lasten Ausgleichs Module *funktionieren* mit GrpC-Anwendungen, sind jedoch in erster Linie nützlich, wenn geringe Latenzzeiten und niedriger Verwaltungsaufwand von größter Wichtigkeit sind.

> [!IMPORTANT]
> Zum Zeitpunkt der Erstellung dieses Artikels unterstützen nicht alle L7-Lasten Ausgleichs Module alle Teile der http/2-Spezifikation, die von den GrpC-Diensten benötigt werden, z. b. nachfolgende Header.

Wenn die TLS-Verschlüsselung verwendet wird, können Lasten Ausgleichs Module die TLS-Verbindung beenden und unverschlüsselte Anforderungen an die Back-End-Anwendung übergeben oder die verschlüsselte Anforderung an übergeben. In jedem Fall muss der Load Balancer mit dem öffentlichen und privaten Schlüssel des Servers konfiguriert werden, damit die Anforderungen für die Verarbeitung entschlüsselt werden können.

In der Dokumentation für Ihren bevorzugten Load Balancer finden Sie Informationen zum Konfigurieren des Diensts für die Verarbeitung von http/2-Anforderungen mit ihren Back-End-Diensten.

## <a name="load-balancing-within-kubernetes"></a>Lastenausgleich innerhalb von Kubernetes

Weitere Informationen zum Lastenausgleich zwischen internen Diensten auf Kubernetes finden Sie im [Abschnitt zu Service-Meshes](service-mesh.md) .

>[!div class="step-by-step"]
>[Zurück](service-mesh.md)
>[Weiter](application-performance-management.md)
