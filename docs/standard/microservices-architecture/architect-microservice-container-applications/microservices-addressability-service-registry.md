---
title: Microservices Adressierbarkeit und die Service-Registrierung
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Microservices Adressierbarkeit und die Service-Registrierung"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 19a0200dadfb90a455de690d880f4eeae4772ed7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="microservices-addressability-and-the-service-registry"></a>Microservices Adressierbarkeit und die Service-Registrierung

Jede Microservice besitzt einen eindeutigen Namen (URL), der verwendet wird, um den Speicherort zu beheben. Ihre Microservice muss adressiert werden, wo er ausgeführt wird. Haben Sie Gedanken machen, über welche Computer einer bestimmten Microservice ausgeführt wird, können etwas schnell fehlerhafte geht. Auf die gleiche Weise, dass DNS eine URL zu einem bestimmten Computer aufgelöst wird muss Ihre Microservice einen eindeutigen Namen haben, damit der aktuellen Position ermittelt werden kann. Microservices benötigen adressierbare Namen, die sie unabhängig von der Infrastruktur machen, die sie ausgeführt werden. Dies bedeutet, dass da muss es eine Interaktion zwischen wie der Dienst bereitgestellt wird und wie es erkannt wird, besteht eine [dienstregistrierung](http://microservices.io/patterns/service-registry.html). Weitere bei ein Computer ein Fehler auftritt, muss der Registrierungsdienst angeben werden, in dem der Dienst nun ausgeführt wird.

Die [Registrierung-Musters](http://microservices.io/patterns/service-registry.html) ist ein wesentlicher Bestandteil der Dienstermittlung. Die Registrierung ist eine Datenbank, die Netzwerkadressen der Dienstinstanzen enthält. Eine dienstregistrierung muss hoch verfügbar und auf dem neuesten Stand sein. Netzwerkadressen abgerufen, die aus der Service-Registrierung konnte von Clients zwischengespeichert werden. Allerdings Schließlich wechselt diese Informationen nicht mehr aktuell, und Clients können nicht mehr Dienstinstanzen ermitteln. Folglich besteht aus eine Service-Registrierung einen Cluster von Servern, die eine Replikationsprotokoll verwenden, um die Konsistenz sicherzustellen.

In einigen Microservice-bereitstellungsumgebungen (so genannte-Clustern in einem späteren Abschnitt abgedeckt werden) ist die Dienstermittlung integriert. Z. B. innerhalb einer Azure-Container-Service-Umgebung, können Kubernetes DC/OS mit Marathon dienstregistrierung für die Instanz zu behandeln und die Registrierung. Sie führen Sie einen Proxy für jeden Host, der die Rolle der serverseitigen Ermittlung Router. Ein weiteres Beispiel ist die Azure Service Fabric, die auch eine Service-Registrierung über die Out-of-Box-Namensdienst bereitstellt.

Beachten Sie, dass bestimmte Überschneidung zwischen der dienstregistrierung und API-Gateway-Muster, dadurch wird auch dieses Problem zu beheben. Z. B. die [Service Fabric-Reverseproxy](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy) ist eine Art der Implementierung eines API-Gateways auf Grundlage der Fabrice Naming Service und hilft Adressauflösung in interne Dienste aufgelöst.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Chris Rißling. Muster: Dienstregistrierung**
    *http://microservices.io/patterns/service-registry.html*

-   **Auth0. Die Dienstregistrierung**
    [*https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/*](https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/)

-   **Gabriel Schenker. Dienstermittlung**
    [*https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/*](https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/)


>[!div class="step-by-step"]
[Vorherigen] (verwalten-Microservice-apis.md) [weiter] (Microservice-based-composite-ui-shape-layout.md)
