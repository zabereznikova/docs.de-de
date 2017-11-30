---
title: "Erstellen, entwickelt und versionsverwaltung Microservice APIs und Verträge"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Erstellen, entwickelt und versionsverwaltung Microservice APIs und Verträge"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 433711c3479eafd52bf9f5d53faf8e5707c6c624
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="creating-evolving-and-versioning-microservice-apis-and-contracts"></a>Erstellen, entwickelt und versionsverwaltung Microservice APIs und Verträge

Ein Microservice-API ist ein Vertrag zwischen dem Dienst und seinen Clients. Sie können werden ein Microservice eigenständig nur, wenn Sie keine API-Vertrag, beschädigen daher der Vertrag so wichtig ist. Wenn Sie den Vertrag ändern, wirkt sie Ihre Clientanwendungen angewendet oder Ihr API-Gateway.

Die Art der API-Definition abhängig ist, auf welches Protokoll verwenden. Für die Instanz, wenn Sie messaging verwenden (z. B. [AMQP](https://www.amqp.org/)), die API besteht aus den Nachrichtentypen. Wenn Sie HTTP und RESTful-Dienste verwenden, besteht die API die URLs und die Anforderung und Antwort JSON-Formate.

Allerdings auch, wenn Sie Informationen zu den ersten Vertrag durchdachtes sind, müssen eine Dienst-API im Laufe der Zeit ändern. Wann dies geschieht – und insbesondere dann, wenn Ihre API eine öffentliche API von mehreren Clientanwendungen genutzt werden – Sie in der Regel können nicht erzwingen, dass alle Clients so aktualisieren Sie auf die neue API-Vertrags. Sie müssen in der Regel inkrementell auf neue Versionen eines Diensts auf eine Weise bereitstellen, die alte und neue Versionen eines Dienstvertrags gleichzeitig ausgeführt werden. Aus diesem Grund ist es wichtig, dass eine Strategie für die dienstversionsverwaltung.

Wenn die API-Änderungen "klein" sind, z. B., wenn Sie Attribute oder Parameter auf Ihre API hinzufügen, sollten Clients, bei denen eine ältere API wechseln und Arbeiten mit der neuen Version des Diensts. Möglicherweise Standardwerte für alle fehlenden Attribute bereitzustellen, die erforderlich sind, und die Clients können möglicherweise keine zusätzliche Antwort Attribute ignoriert werden sollen.

Allerdings müssen gelegentlich Sie Haupt- und nicht kompatible Änderungen an einer Dienst-API vornehmen. Da möglicherweise nicht zum Erzwingen von Clientanwendungen oder Diensten, sofort auf die neue Version aktualisiert werden können, muss ein Dienst ältere Versionen der API für einen gewissen Zeitraum unterstützen. Wenn Sie einen HTTP-basierte Mechanismus wie REST verwenden, ist ein Ansatz besteht darin, die API-Versionsnummer in der URL oder in einen HTTP-Header einzubetten. Sie können dann entscheiden, zwischen beide Versionen des Diensts gleichzeitig innerhalb der gleichen Dienstinstanz implementieren oder die Bereitstellung von anderen Instanzen, jeweils eine Version der API behandeln. Ist ein guter Ansatz für diesen die [Vermittler Muster](https://en.wikipedia.org/wiki/Mediator_pattern) (z. B. [MediatR Bibliothek](https://github.com/jbogard/MediatR)), die andere Implementierung Versionen in unabhängigen Handler zu entkoppeln.

Abschließend, wenn Sie eine REST-Architektur verwenden [Hypermedia](https://www.infoq.com/articles/mark-baker-hypermedia) besteht die beste Lösung für die versionsverwaltung Ihrer Dienste und evolvable APIs ermöglichen.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Scott Hanselman. ASP.NET Core RESTful-Web-API-versionsverwaltung lassen sich einfach**
    <http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx>

-   **Eine RESTful-Web-API-versionsverwaltung**
    [*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)

-   **Roy Fielding. Versionsverwaltung, Hypermedia und REST**
    <https://www.infoq.com/articles/roy-fielding-on-versioning>


>[!div class="step-by-step"]
[Vorherigen] (asynchrone-Nachricht-Basis-communication.md) [weiter] (Microservices-Adressierbarkeit-Service-registry.md)
