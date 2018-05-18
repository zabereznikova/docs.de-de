---
title: Anwenden vereinfachter CQRS- und DDD-Muster in einem Microservice
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Anwenden einfacher CQRS- und DDD-Muster in einem Microservice
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 4e30b4755af001f85649e611c9f1f976ed294cab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="applying-simplified-cqrs-and-ddd-patterns-in-a-microservice"></a>Anwenden vereinfachter CQRS- und DDD-Muster in einem Microservice

CQRS ist ein Architekturkonzept, in dem die Modelle zum Lesen und Schreiben von Daten getrennt sind. Der verwandte Begriff [Command Query Separation (CQS)](https://martinfowler.com/bliki/CommandQuerySeparation.html) wurde ursprünglich von Bertrand Meyer in seinem Buch *Objektorientierte Softwareentwicklung* geprägt. Die Grundidee ist, dass die Systemvorgänge in zwei vollständig getrennte Kategorien aufgeteilt werden:

-   Abfragen: Sie geben ein Ergebnis zurück und ändern nicht den Zustand des Systems. Außerdem haben sie keine Nebenwirkungen.

-   Befehle: Sie ändern den Zustand eines Systems.

CQS ist ein einfaches Konzept, in dem die Methoden innerhalb desselben Objekts entweder Abfragen oder Befehle sein können. Jede Methode gibt entweder einen Zustand zurück oder ändert ihn, jedoch nicht beides. Selbst ein einzelnes Repositorymusterobjekt kann mit CQS kompatibel sein. CQS ist das grundlegende Prinzip von CQRS.

[Command and Query Responsibility Segregation (CQRS)](https://martinfowler.com/bliki/CQRS.html) wurde von Greg Young eingeführt und von Udi Dahan und anderen bekannt gemacht. Es basiert auf dem CQS-Prinzip, ist aber detaillierter. Dieses Konzept basiert auf Befehlen und Ereignissen sowie optional auf asynchronen Nachrichten. Oftmals bezieht sich CQRS auf erweiterte Szenarios, in denen z.B. für Lesevorgänge (Abfragen) und für Schreibvorgänge (Updates) unterschiedliche physische Datenbanken eingesetzt werden. Außerdem kann in einem komplexeren CQRS-System [Event Sourcing (ES)](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/) für Ihre Updatedatenbank implementiert werden, sodass statt der aktuellen Zustandsdaten nur Ereignisse im Domänenmodell gespeichert werden. In diesem Leitfaden wird jedoch ein anderer Ansatz verfolgt. Wir verwenden den einfachsten CQRS-Ansatz, bei dem nur Abfragen von Befehlen getrennt werden.

Die Trennung wird in CQRS erzielt, indem Abfragevorgänge auf einer Ebene und Befehle auf einer anderen gruppiert werden. Jede Ebene weist ein eigenes Datenmodell auf, das nicht unbedingt einer anderen Datenbank entspricht. Außerdem werden die Ebenen mithilfe eigener Kombinationen von Mustern und Technologien erstellt. Beide Ebenen können sich sogar innerhalb derselben Ebene oder desselben Microservices befinden, so wie in dem Beispiel (Microservice für Bestellungen) in diesem Handbuch. Alternativ können sie auch in verschiedenen Microservices oder Prozessen implementiert werden, sodass sie getrennt und ohne Auswirkungen aufeinander optimiert und horizontal hochskaliert werden können.

In CQRS gibt es zwei Objekte für einen Lese-/Schreibvorgang, während es in anderen Kontexten nur eines gibt. Es gibt gute Gründe für eine nicht normalisierte Datenbank für Lesevorgänge, die Sie in der weiterführenden CQRS-Literatur nachlesen können. Da unser Ziel darin besteht, die Flexibilität der Abfragen zu erhöhen, statt die Abfragen mit Einschränkungen aus DDD-Mustern wie Aggregaten zu beschränken, wird dieser Ansatz hier jedoch nicht verwendet.

Ein Beispiel für diese Art von Dienst ist der Microservice für Bestellungen aus der Referenzanwendung „eShopOnContainers“. Er basiert auf einem vereinfachten CQRS-Ansatz und verwendet eine einzelne Datenquelle oder Datenbank, aber zwei logische Modelle sowie außerdem DDD-Muster für die Transaktionsdomäne, wie in Abbildung 9-2 dargestellt.

![](./media/image2.png)

**Abbildung 9-2:** Vereinfachter auf CQRS und DDD basierender Microservice

Die Anwendungsebene kann aus der Web-API selbst bestehen. Das Wichtige am Architekturentwurf ist dabei, dass der Microservice die Abfragen und ViewModels (speziell für die Clientanwendungen erstellte Datenmodelle) nach dem CQRS-Muster von den Befehlen, Domänenmodellen und Transaktionen trennt. Dadurch bleiben die Abfragen unabhängig von den Einschränkungen der DDD-Muster, die nur für Transaktionen und Updates sinnvoll sind. Dies wird in späteren Abschnitten erläutert.


>[!div class="step-by-step"]
[Zurück] (index.md) [Weiter] (eshoponcontainers-cqrs-ddd-microservice.md)
