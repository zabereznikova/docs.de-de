---
title: Einführung in cloudbasierte Anwendungen
description: Erfahren Sie mehr über Cloud-Native Computing
author: robvet
ms.date: 08/26/2019
ms.openlocfilehash: c9ffd34ec3deb04abddbbf85a9e5a6ed2b57c8f9
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989050"
---
# <a name="introduction-to-cloud-native-applications"></a>Einführung in cloudbasierte Anwendungen

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

An einem anderen Tag, im Büro, arbeiten an "der nächsten großen Sache".

Ihr Handy klingelt. Es ist Ihr freundlicher Personalvermittler - derjenige, der Sie zweimal am Tag über neue Jobs anruft.

Aber dieses Mal ist es anders: Start-up, Eigenkapital und viel Geld.

Die Erwähnung der Cloud und modernster Technologie bringt Sie über den Haufen.

Schnell vorwärts ein paar Wochen und Sie sind jetzt ein neuer Mitarbeiter in einer Entwurfssitzung, die eine große eCommerce-Anwendung architektoniert. Sie werden mit anderen führenden eCommerce-Websites abschließen.

Wie werden Sie es bauen?

Wenn Sie den Anweisungen der letzten 15 Jahre folgen, erstellen Sie höchstwahrscheinlich das in Abbildung 1.1 dargestellte System.

![Traditionelles monolithisches Design](./media/monolithic-design.png)

**Abbildung 1-1**. Traditionelles monolithisches Design

Sie erstellen eine große Kernanwendung, die ihre gesamte Domänenlogik enthält. Es enthält Module wie Identität, Katalog, Bestellung und mehr. Die Kern-App kommuniziert mit einer großen relationalen Datenbank. Der Kern macht die Funktionalität über eine HTML-Schnittstelle verfügbar.

Herzlichen Glückwunsch!  Sie haben gerade eine monolithische Anwendung erstellt.

Nicht alles ist schlecht. Monolithen bieten einige deutliche Vorteile. Zum Beispiel sind sie einfach zu...

- build
- test
- Bereitstellen
- Beheben
- Skalierung

Viele erfolgreiche Apps, die es heute gibt, wurden als Monolithen erstellt. Die App ist ein Hit und entwickelt sich weiter, Iteration nach Iteration, Hinzufügen von mehr und mehr Funktionalität.

Irgendwann fängt man jedoch an, sich unwohl zu fühlen. Sie verlieren die Kontrolle über die Anwendung. Im Laufe der Zeit wird das Gefühl intensiver und du betrittst schließlich einen Zustand, der als **Angstzyklus**bekannt ist.

- Die App ist so überwältigend kompliziert geworden, dass es keine einzige Person versteht.
- Sie fürchten, Änderungen vorzunehmen - jede Änderung hat unbeabsichtigte und kostspielige Nebenwirkungen.
- Neue Funktionen/Korrekturen werden schwierig, zeitaufwändig und teuer zu implementieren.
- Jede Version, so klein sie auch sein kann, erfordert eine vollständige Bereitstellung der gesamten Anwendung.
- Eine instabile Komponente kann das gesamte System zum Absturz bringen.
- Neue Technologien und Frameworks sind keine Option.
- Es ist schwierig, agile Bereitstellungsmethoden zu implementieren.
- Die architektonische Erosion setzt ein, da sich die Codebasis mit endlosen "Sonderfällen" verschlechtert.
- Die Berater sagen Ihnen, es neu zu schreiben.

Viele Organisationen haben den monolithischen Angstzyklus angegangen, indem sie einen Cloud-nativen Ansatz für das Erstellen von Systemen gewählt haben. Abbildung 1-2 zeigt dasselbe System, das cloudnative Techniken und Vorgehensweisen verwendet.

![Cloud-Natives Design](./media/cloud-native-design.png)

**Abbildung 1-2**. Cloud-natives Design

Beachten Sie, wie die Anwendung über eine Reihe kleiner isolierter Microservices zerlegt wird. Jeder Dienst ist eigenständig und kapselt seinen eigenen Code, seine eigenen Daten und Abhängigkeiten. Jeder wird in einem Softwarecontainer bereitgestellt und von einem Containerorchestrator verwaltet. Anstelle einer großen relationalen Datenbank besitzt jeder Dienst seinen eigenen Datenspeicher, dessen Typ je nach Datenbedarf variiert. Beachten Sie, wie einige Dienste von einer relationalen Datenbank, andere von NoSQL-Datenbanken abhängen. Ein Dienst speichert seinen Status in einem verteilten Cache. Beachten Sie, wie der gesamte Datenverkehr über einen API Gateway-Dienst führt, der für das Routing des Datenverkehrs zu den zentralen Back-End-Diensten und das Erzwingen vieler bereichsübergreifender Probleme verantwortlich ist. Am wichtigsten ist, dass die Anwendung die Skalierbarkeits- und Ausfallsicherheitinfunktionen in modernen Cloud-Plattformen voll ausnutzt.

### <a name="cloud-native-computing"></a>Cloud-natives Computing

Hmm... Wir haben nur den Begriff *"Cloud Native"* verwendet. Sie dachten zuerst: "Was genau bedeutet das?" Ein weiteres Branchenschlagwort, das von Softwareanbietern erfunden wurde, um mehr Sachen zu vermarkten?"

Glücklicherweise ist es ganz anders und hoffentlich wird dieses Buch Helfen, Sie zu überzeugen.

Innerhalb kurzer Zeit hat sich Cloud Native zu einem treibenden Trend in der Softwarebranche entwickelt. Es ist eine neue Möglichkeit, über den Aufbau großer, komplexer Systeme nachzudenken, ein Ansatz, der die Vorteile moderner Softwareentwicklungspraktiken, -technologien und Cloud-Infrastrukturen voll ausnutzt. Der Ansatz ändert die Art und Weise, wie Sie Systeme entwerfen, implementieren, bereitstellen und operationalisieren.

Im Gegensatz zu dem anhaltenden Hype, der unsere Branche antreibt, ist Cloud native "*for-real*". Man denke an die [Cloud Native Computing Foundation](https://www.cncf.io/) (CNCF), ein Konsortium von über 300 großen Unternehmen mit einer Charta, um Cloud-natives Computing über Technologie und Cloud-Stacks hinweg allgegenwärtig zu machen. Als eine der einflussreichsten Open-Source-Gruppen beherbergt sie viele der am schnellsten wachsenden Open-Source-Projekte in GitHub. Dazu gehören Projekte wie [Kubernetes](https://kubernetes.io/), [Prometheus](https://prometheus.io/), [Helm](https://helm.sh/), [Envoy](https://www.envoyproxy.io/)und [gRPC](https://grpc.io/).

Die CNCF fördert ein Ökosystem aus Open-Source- und Anbieterneutralität. Im Anschluss an diesen Lead präsentieren wir Cloud-native Prinzipien, Muster und Best Practices, die technologieunabhängig sind. Gleichzeitig werden die Dienste und die Infrastruktur erläutert, die in der Microsoft Azure-Cloud zum Erstellen cloudnativer Systeme verfügbar sind.

Also, was genau ist Cloud Native? Lehnen Sie sich zurück, entspannen Sie sich und lassen Sie sich von uns helfen, diese neue Welt zu erkunden.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](definition.md)
