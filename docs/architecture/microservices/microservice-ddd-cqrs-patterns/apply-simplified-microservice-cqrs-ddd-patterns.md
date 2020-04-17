---
title: Anwenden vereinfachter CQRS- und DDD-Muster in einem Microservice
description: .NET-Microservicearchitektur für .NET-Containeranwendungen | Übersicht über die allgemeine Beziehung zwischen CQRS- und DDD-Mustern
ms.date: 10/08/2018
ms.openlocfilehash: e4e36bafff39f5f30d6371ed7c113322a85c3362
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805591"
---
# <a name="apply-simplified-cqrs-and-ddd-patterns-in-a-microservice"></a>Anwenden vereinfachter CQRS- und DDD-Muster in einem Microservice

CQRS ist ein Architekturkonzept, in dem die Modelle zum Lesen und Schreiben von Daten getrennt sind. Der verwandte Begriff [Command Query Separation (CQS)](https://martinfowler.com/bliki/CommandQuerySeparation.html) wurde ursprünglich von Bertrand Meyer in seinem Buch *Objektorientierte Softwareentwicklung* geprägt. Die Grundidee besteht darin, dass die Systemvorgänge in zwei vollständig getrennte Kategorien aufgeteilt werden:

- Abfragen: Sie geben ein Ergebnis zurück und ändern nicht den Zustand des Systems. Außerdem haben sie keine Nebenwirkungen.

- Befehle: Sie ändern den Zustand eines Systems.

CQS ist ein einfaches Konzept, in dem die Methoden innerhalb desselben Objekts entweder Abfragen oder Befehle sein können. Jede Methode gibt entweder einen Zustand zurück oder ändert ihn, jedoch nicht beides. Selbst ein einzelnes Repositorymusterobjekt kann mit CQS kompatibel sein. CQS ist das grundlegende Prinzip von CQRS.

[Command and Query Responsibility Segregation (CQRS)](https://martinfowler.com/bliki/CQRS.html) wurde von Greg Young eingeführt und von Udi Dahan und anderen bekannt gemacht. Es basiert auf dem CQS-Prinzip, ist aber detaillierter. Dieses Konzept basiert auf Befehlen und Ereignissen sowie optional auf asynchronen Nachrichten. Oftmals bezieht sich CQRS auf erweiterte Szenarios, in denen z.B. für Lesevorgänge (Abfragen) und für Schreibvorgänge (Updates) unterschiedliche physische Datenbanken eingesetzt werden. Außerdem kann in einem komplexeren CQRS-System [Event Sourcing (ES)](https://martinfowler.com/eaaDev/EventSourcing.html) für Ihre Updatedatenbank implementiert werden, sodass statt der aktuellen Zustandsdaten nur Ereignisse im Domänenmodell gespeichert werden. Allerdings wird dieser Ansatz nicht in diesem Leitfaden verwendet. In diesem Leitfaden wird der einfachste CQRS-Ansatz verwendet, bei dem lediglich die Abfragen von den Befehlen getrennt werden.

Die Trennung wird in CQRS erzielt, indem Abfragevorgänge auf einer Ebene und Befehle auf einer anderen gruppiert werden. Jede Ebene weist ein eigenes Datenmodell auf, das nicht unbedingt einer anderen Datenbank entspricht. Außerdem werden die Ebenen mithilfe eigener Kombinationen von Mustern und Technologien erstellt. Beide Ebenen können sich sogar innerhalb derselben Ebene oder desselben Microservices befinden, so wie in dem Beispiel (Microservice für Bestellungen) in diesem Handbuch. Alternativ können sie auch in verschiedenen Microservices oder Prozessen implementiert werden, sodass sie getrennt und ohne Auswirkungen aufeinander optimiert und horizontal hochskaliert werden können.

In CQRS gibt es zwei Objekte für einen Lese-/Schreibvorgang, während es in anderen Kontexten nur eines gibt. Es gibt gute Gründe für eine nicht normalisierte Datenbank für Lesevorgänge, die Sie in der weiterführenden CQRS-Literatur nachlesen können. Da unser Ziel darin besteht, die Flexibilität der Abfragen zu erhöhen, statt die Abfragen mit Einschränkungen aus DDD-Mustern wie Aggregaten zu beschränken, wird dieser Ansatz hier jedoch nicht verwendet.

Ein Beispiel für diese Art von Dienst ist der Microservice für Bestellungen aus der Referenzanwendung „eShopOnContainers“. Er basiert auf einem vereinfachten CQRS-Ansatz und verwendet eine einzelne Datenquelle oder Datenbank, aber zwei logische Modelle sowie DDD-Muster für die Transaktionsdomäne (s. Abbildung 7-2).

![Das Diagramm zeigt einen allgemeinen vereinfachten CQRS- und DDD-Microservice.](./media/apply-simplified-microservice-cqrs-ddd-patterns/simplified-cqrs-ddd-microservice.png)

**Abbildung 7-2**. Vereinfachter auf CQRS und DDD basierender Microservice

Der logische Microservice für Bestellungen enthält die Datenbank „Ordering“ (Bestellungen), die sich auf demselben Docker-Host befinden kann. Dies ist jedoch nicht zwingend erforderlich. Es eignet sich für die Entwicklung, aber nicht für die Produktion, wenn sich die Datenbank im selben Docker-Host befindet.

Die Anwendungsebene kann aus der Web-API selbst bestehen. Das Wichtige am Architekturentwurf ist dabei, dass der Microservice die Abfragen und ViewModels (speziell für die Clientanwendungen erstellte Datenmodelle) nach dem CQRS-Muster von den Befehlen, Domänenmodellen und Transaktionen trennt. Dadurch bleiben die Abfragen unabhängig von den Einschränkungen der DDD-Muster, die nur für Transaktionen und Updates sinnvoll sind. Dies wird in späteren Abschnitten erläutert.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Greg Young. Versioning in an Event Sourced System** (Versionsverwaltung in einem System mit Ereignisquelle (kostenloses Online-E-Book)) \
   <https://leanpub.com/esversioning/read>

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](eshoponcontainers-cqrs-ddd-microservice.md)
