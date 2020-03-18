---
title: Adressierbarkeit von Microservices und die Dienstregistrierung
description: Übersicht über die Rollen von Containerimageregistrierungen in der Microservicearchitektur
ms.date: 09/20/2018
ms.openlocfilehash: d72ba399f3da730f0e57c44c5ec01c1cc9f5fc05
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "68674047"
---
# <a name="microservices-addressability-and-the-service-registry"></a>Adressierbarkeit von Microservices und die Dienstregistrierung

Jeder Microservice hat einen eindeutigen Namen (URL), der zum Auflösen des Speicherorts verwendet wird. Ihr Microservice muss adressierbar sein, unabhängig davon, wo er ausgeführt wird. Wenn Sie darüber nachdenken müssen, welcher Computer einen bestimmten Microservice ausführt, können schnell Fehler auftreten. Ähnlich wie DNS eine URL zu einem bestimmten Computer auflöst, benötigt Ihr Microservice einen eindeutigen Namen, damit seine aktuelle Position ermittelt werden kann. Microservices benötigen adressierbare Namen, um von der Infrastruktur unabhängig zu sein, auf der sie ausgeführt werden. Da eine [Dienstregistrierung](https://microservices.io/patterns/service-registry.html) vorhanden sein muss, impliziert dies, dass eine Interaktion zwischen der Bereitstellung und der Erkennung des Diensts besteht. In gleicher Weise muss der Registrierungsdienst angeben können, wo der Dienst momentan ausgeführt wird, wenn bei einem Computer ein Fehler auftritt.

Das [Muster der Dienstregistrierung](https://microservices.io/patterns/service-registry.html) ist ein Schlüsselteil der Diensterkennung. Die Registrierung ist eine Datenbank, die Netzwerkadressen und Dienstinstanzen enthält. Eine Dienstregistrierung muss hochverfügbar und auf dem neuesten Stand sein. Clients könnten Netzwerkadressen zwischenspeichern, die sie von der Dienstregistrierung erhalten. Allerdings veralten diese Informationen, und Clients können die Dienstinstanzen nicht mehr ermitteln. Folglich besteht eine Dienstregistrierung aus einem Cluster von Servern, die ein Replikationsprotokoll verwenden, um die Konsistenz zu gewährleisten.

In manchen Bereitstellungsumgebungen für Microservices (auch Clusters genannt, wie in einem späteren Abschnitt erklärt wird) ist die Diensterkennung integriert. So kann beispielsweise eine Azure Kubernetes Service-Umgebung (AKS) die Registrierung und die Registrierungsaufhebung von Dienstinstanzen ausführen. Die Umgebung führt außerdem einen Proxy auf jedem Clusterhost aus, der die Rolle eines serverseitigen Suchrouters übernimmt.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Chris Richardson. Pattern: Service Registry (Dienstregistrierung)**  \
  <https://microservices.io/patterns/service-registry.html>

- **Auth0. The Service Registry (Dienstregistrierung)**  \
  <https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/>

- **Gabriel Schenker. Service discovery (Dienstermittlung)**  \
  <https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/>

>[!div class="step-by-step"]
>[Zurück](maintain-microservice-apis.md)
>[Weiter](microservice-based-composite-ui-shape-layout.md)
