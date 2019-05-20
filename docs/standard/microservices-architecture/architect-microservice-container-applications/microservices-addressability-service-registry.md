---
title: Adressierbarkeit von Microservices und die Dienstregistrierung
description: Übersicht über die Rollen von Containerimageregistrierungen in der Microservicearchitektur
ms.date: 09/20/2018
ms.openlocfilehash: 5b601f19b60a8e989977e7135138add7644bd7b6
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65639966"
---
# <a name="microservices-addressability-and-the-service-registry"></a>Adressierbarkeit von Microservices und die Dienstregistrierung

Jeder Microservice hat einen eindeutigen Namen (URL), der zum Auflösen des Speicherorts verwendet wird. Ihr Microservice muss adressierbar sein, unabhängig davon, wo er ausgeführt wird. Wenn Sie darüber nachdenken müssen, welcher Computer einen bestimmten Microservice ausführt, können schnell Fehler auftreten. Ähnlich wie DNS eine URL zu einem bestimmten Computer auflöst, benötigt Ihr Microservice einen eindeutigen Namen, damit seine aktuelle Position ermittelt werden kann. Microservices benötigen adressierbare Namen, um von der Infrastruktur unabhängig zu sein, auf der sie ausgeführt werden. Da eine [Dienstregistrierung](https://microservices.io/patterns/service-registry.html) vorhanden sein muss, impliziert dies, dass eine Interaktion zwischen der Bereitstellung und der Erkennung des Diensts besteht. In gleicher Weise muss der Registrierungsdienst angeben können, wo der Dienst momentan ausgeführt wird, wenn bei einem Computer ein Fehler auftritt.

Das [Muster der Dienstregistrierung](https://microservices.io/patterns/service-registry.html) ist ein Schlüsselteil der Diensterkennung. Die Registrierung ist eine Datenbank, die Netzwerkadressen und Dienstinstanzen enthält. Eine Dienstregistrierung muss hochverfügbar und auf dem neuesten Stand sein. Clients könnten Netzwerkadressen zwischenspeichern, die sie von der Dienstregistrierung erhalten. Allerdings veralten diese Informationen, und Clients können die Dienstinstanzen nicht mehr ermitteln. Folglich besteht eine Dienstregistrierung aus einem Cluster von Servern, die ein Replikationsprotokoll verwenden, um die Konsistenz zu gewährleisten.

In manchen Bereitstellungsumgebungen für Microservices (auch Clusters genannt, wie in einem späteren Abschnitt erklärt wird) ist die Diensterkennung integriert. So kann beispielsweise eine Azure Kubernetes Service-Umgebung (AKS) die Registrierung und die Registrierungsaufhebung von Dienstinstanzen ausführen. Die Umgebung führt außerdem einen Proxy auf jedem Clusterhost aus, der die Rolle eines serverseitigen Suchrouters übernimmt. Ein weiteres Beispiel ist Azure Service Fabric, was ebenfalls eine Dienstregistrierung über einen integrierten Namensdienst bereitstellt.

Beachten Sie, dass es eine gewisse Überschneidung zwischen der Dienstregistrierung und dem API-Gatewaymuster gibt, die ebenfalls zur Lösung dieses Problems beiträgt. Zum Beispiel ist der [Service Fabric-Reverseproxy](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy) eine Art der Implementierung eines API-Gateways, die auf Naming Service von Service Fabric basiert und dabei hilft, die Adressauflösung in interne Dienste aufzulösen.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Chris Richardson. Pattern: Service Registry (Dienstregistrierung)** \
  <https://microservices.io/patterns/service-registry.html>

- **Auth0. The Service Registry (Dienstregistrierung)** \
  <https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/>

- **Gabriel Schenker. Service discovery (Dienstermittlung)** \
  <https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/>

>[!div class="step-by-step"]
>[Zurück](maintain-microservice-apis.md)
>[Weiter](microservice-based-composite-ui-shape-layout.md)
