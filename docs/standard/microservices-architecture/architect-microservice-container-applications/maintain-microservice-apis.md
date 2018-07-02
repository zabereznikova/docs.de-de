---
title: Erstellen, Weiterentwickeln und Verwalten von Versionen von Microservice-APIs und -verträgen
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Erstellen, Weiterentwickeln und Verwalten von Versionen von Microservice-APIs und -verträgen
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: a2ec577a12cf677c2ec5e20a6f3e862911c82fbb
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105692"
---
# <a name="creating-evolving-and-versioning-microservice-apis-and-contracts"></a>Erstellen, Weiterentwickeln und Verwalten von Versionen von Microservice-APIs und -verträgen

Eine Microservice-API stellt einen Vertrag zwischen dem Dienst und dessen Clients dar. Sie können jetzt einen Microservice unabhängig weiterzuentwickeln, sofern Sie seinen API-Vertrag nicht brechen. Aus diesem Grund ist dieser Vertrag so wichtig ist. Wenn Sie den Vertrag ändern, wirkt sich dies auf Ihre Clientanwendungen oder Ihr API-Gateway aus.

Die Art der API-Definition ist von dem Protokoll abhängig, das Sie verwenden. Wenn Sie z.B. Messaging (wie z.B. [AMQP](https://www.amqp.org/)) verwenden, besteht die API aus den Nachrichtentypen. Wenn Sie HTTP- und RESTful-Dienste verwenden, besteht die API aus den URLs und den JSON-Formaten für Anforderungen und Antworten.

Selbst wenn Sie ihren ersten Vertrag gut durchdacht haben, muss sich die Dienst-API im Laufe der Zeit ändern. Wenn das geschieht – besonders wenn es sich bei Ihrer API um eine öffentliche API handelt, die von mehreren Clientanwendungen verwendet wird – können Sie in der Regel nicht alle Clients dazu zwingen, auf Ihren neuen API-Vertrag upzugraden. In der Regel müssen Sie neue Versionen eines Diensts inkrementell auf eine Weise bereitstellen, sodass sowohl die alte als auch die neue Version eines Dienstvertrags gleichzeitig ausgeführt werden. Deshalb ist es wichtig, dass Sie eine Strategie für die Versionsverwaltung Ihres Diensts haben.

Wenn die Änderungen an der API klein sind, wenn Sie also Ihrer API zum Beispiel Attribute oder Parameter hinzufügen, sollten Clients, die eine ältere API verwenden, umschalten und mit der neueren Version des Diensts arbeiten. Möglicherweise können Sie Standardwerte für fehlende Attribute bereitstellen, die erforderlich sind, und die Clients können überflüssige Antwortattribute ignorieren.

Allerdings müssen Sie manchmal größere Änderungen an einer Dienst-API vornehmen und verstoßen dadurch gegen die Kompatibilitätsanforderungen. Da Sie möglicherweise nicht dazu in der Lage sind, Clientanwendungen oder Dienste zu einem sofortigen Upgrade auf die neue Version zu zwingen, muss ein Dienst ältere Versionen der API für einen gewissen Zeitraum unterstützen. Wenn Sie einen HTTP-basierten Mechanismus wie REST verwenden, können Sie z.B. die Versionsnummer der API in die URL oder in einen HTTP-Header einbetten. Dann können Sie sich entscheiden, ob Sie beide Versionen des Diensts gleichzeitig in die gleiche Dienstinstanz implementieren, oder ob Sie verschiedene Instanzen bereitstellen, die jeweils eine Version der API verarbeiten. Ein guter Ansatz dafür ist das [Vermittlermuster](https://en.wikipedia.org/wiki/Mediator_pattern) (z.B. die [MediatR-Bibliothek](https://github.com/jbogard/MediatR)) zum Entkoppeln der verschiedenen Implementierungsversionen in unabhängige Handler.

Letztendlich ist [Hypermedia](https://www.infoq.com/articles/mark-baker-hypermedia) die beste Lösung für die Versionsverwaltung Ihrer Dienste und das Erlauben von entwickelbaren APIs, wenn Sie eine REST-Architektur verwenden.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy (Versionsverwaltung von RESTful-Web-APIs in ASP.NET Core leicht gemacht)**
    <https://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx>

-   **Versionsverwaltung einer RESTful-Web-API**
    [*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)

-   **Roy Fielding. Versioning, Hypermedia, and REST (Versionsverwaltung, Hypermedia und REST)**
    <https://www.infoq.com/articles/roy-fielding-on-versioning>


>[!div class="step-by-step"]
[Zurück](asynchronous-message-based-communication.md)
[Weiter](microservices-addressability-service-registry.md)
