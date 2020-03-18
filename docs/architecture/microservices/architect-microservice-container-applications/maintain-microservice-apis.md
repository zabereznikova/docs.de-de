---
title: Erstellen, Weiterentwickeln und Verwalten von Versionen von Microservice-APIs und -verträgen
description: Erstellen Sie Microservice-APIs und Verträge unter Berücksichtigung von Weiterentwicklung und Versionsverwaltung angesichts der Tatsache, dass Anforderungen sich ändern.
ms.date: 09/20/2018
ms.openlocfilehash: 1972d02d8bf7935c71bfd383707ae19ea2baded9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "68672897"
---
# <a name="creating-evolving-and-versioning-microservice-apis-and-contracts"></a>Erstellen, Weiterentwickeln und Verwalten von Versionen von Microservice-APIs und -verträgen

Eine Microservice-API stellt einen Vertrag zwischen dem Dienst und dessen Clients dar. Sie können einen Microservice nur dann unabhängig weiterentwickeln, wenn Sie den zugehörigen API-Vertrag nicht brechen. Aus diesem Grund ist dieser Vertrag so wichtig. Wenn Sie den Vertrag ändern, wirkt sich dies auf Ihre Clientanwendungen oder Ihr API-Gateway aus.

Die Art der API-Definition richtet sich nach dem von Ihnen verwendeten Protokoll. Wenn Sie z.B. Messaging (wie [AMQP](https://www.amqp.org/)) verwenden, besteht die API aus den Nachrichtentypen. Wenn Sie HTTP- und RESTful-Dienste verwenden, besteht die API aus den URLs sowie den JSON-Formaten für Anforderungen und Antworten.

Auch wenn Sie den ersten Vertrag gut durchdacht haben, wird sich die Dienst-API im Laufe der Zeit ändern. Wenn das geschieht, können Sie in der Regel nicht alle Clients dazu zwingen, ein Upgrade auf Ihren neuen API-Vertrag durchzuführen. Dies gilt besonders dann, wenn es sich bei Ihrer API um eine öffentliche API handelt, die von mehreren Clientanwendungen verwendet wird. In der Regel müssen Sie neue Versionen eines Diensts inkrementell auf eine Weise bereitstellen, sodass sowohl die alte als auch die neue Version eines Dienstvertrags gleichzeitig ausgeführt werden. Deshalb ist es wichtig, dass eine Strategie für die Versionsverwaltung Ihres Diensts vorhanden ist.

Wenn die Änderungen an der API klein sind, wenn Sie also Ihrer API zum Beispiel Attribute oder Parameter hinzufügen, sollten Clients, die eine ältere API verwenden, umschalten und mit der neueren Version des Diensts arbeiten. Möglicherweise können Sie Standardwerte für fehlende Attribute bereitstellen, die erforderlich sind, und die Clients können überflüssige Antwortattribute ignorieren.

Allerdings müssen Sie manchmal größere Änderungen an einer Dienst-API vornehmen und verstoßen dadurch gegen die Kompatibilitätsanforderungen. Da Sie möglicherweise nicht dazu in der Lage sind, Clientanwendungen oder Dienste zu einem sofortigen Upgrade auf die neue Version zu zwingen, muss ein Dienst ältere Versionen der API für einen gewissen Zeitraum unterstützen. Wenn Sie einen HTTP-basierten Mechanismus wie REST verwenden, können Sie z.B. die Versionsnummer der API in die URL oder in einen HTTP-Header einbetten. Dann können Sie sich entscheiden, ob Sie beide Versionen des Diensts gleichzeitig in die gleiche Dienstinstanz implementieren, oder ob Sie verschiedene Instanzen bereitstellen, die jeweils eine Version der API verarbeiten. Ein guter Ansatz dafür ist das [Vermittlermuster](https://en.wikipedia.org/wiki/Mediator_pattern) (z.B. die [MediatR-Bibliothek](https://github.com/jbogard/MediatR)) zum Entkoppeln der verschiedenen Implementierungsversionen in unabhängige Handler.

Und wenn Sie eine REST-Architektur verwenden, ist [Hypermedia](https://www.infoq.com/articles/mark-baker-hypermedia) die beste Lösung für die Versionsverwaltung Ihrer Dienste und das Zulassen von APIs, die sich weiterentwickeln lassen.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy (Versionsverwaltung von RESTful-Web-APIs in ASP.NET Core leicht gemacht)**  \
  <https://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx>

- **Versionsverwaltung einer RESTful-Web-API** \
  <https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api>

- **Roy Fielding. Versioning, Hypermedia, and REST (Versionsverwaltung, Hypermedia und REST)**  \
  <https://www.infoq.com/articles/roy-fielding-on-versioning>

>[!div class="step-by-step"]
>[Zurück](asynchronous-message-based-communication.md)
>[Weiter](microservices-addressability-service-registry.md)
