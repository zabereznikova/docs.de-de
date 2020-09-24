---
title: 'Anhang: GrpC für WCF-Entwickler'
description: Erörterung verteilter Transaktionen und ihrer Implementierung in modernen microservicesarchitekturen.
ms.date: 09/02/2019
ms.openlocfilehash: f60899463a13e9f740f6ae63150d18eab3069124
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165857"
---
# <a name="appendix-a---transactions"></a>Anhang A-Transaktionen

Windows Communication Foundation (WCF) unterstützt verteilte Transaktionen, sodass Sie atomarische Vorgänge über mehrere Dienste hinweg ausführen können. Diese Funktionalität basiert auf der [Microsoft-Distributed Transaction Coordinator](/previous-versions/windows/desktop/ms684146(v=vs.85)).

In der neueren Umgebung für die mikrodienste ist diese Art der automatisierten Verarbeitung verteilter Transaktionen nicht möglich. Es sind zu viele verschiedene Technologien beteiligt, darunter relationale Datenbanken, nosql-Datenspeicher und Messaging Systeme. Möglicherweise gibt es auch eine Mischung aus Betriebssystemen, Programmiersprachen und Frameworks, die in einer einzigen Umgebung verwendet werden.

Bei der verteilten WCF-Transaktion handelt es sich um eine Implementierung eines [Zweiphasencommit (2PC)](https://en.wikipedia.org/wiki/Two-phase_commit_protocol). Sie können 2PC-Transaktionen manuell implementieren, indem Sie Nachrichten über mehrere Dienste hinweg koordinieren, offene Transaktionen in jedem Dienst erstellen und Nachrichten mit Commit oder Rollback abhängig von Erfolg oder Fehler senden. Die Komplexität bei der Verwaltung von 2PC kann jedoch exponentiell zunehmen, wenn sich Systeme weiterentwickeln. Geöffnete Transaktionen enthalten Datenbanksperren, die sich negativ auf die Leistung auswirken können, oder schlimmer, dass Dienst übergreifende Deadlocks verursachen können.

Wenn möglich, ist es am besten, verteilte Transaktionen vollständig zu vermeiden. Wenn zwei Datenelemente so verknüpft sind, dass atomarische Updates erforderlich sind, sollten Sie in Erwägung gezogen werden, beide mit dem gleichen Dienst zu verarbeiten. Wenden Sie diese atomaren Änderungen mithilfe einer einzelnen Anforderung oder Nachricht an diesen Dienst an.

Wenn dies nicht möglich ist, besteht eine Alternative darin, das [Saga-Muster](https://microservices.io/patterns/data/saga.html)zu verwenden. In einer Saga werden Updates sequenziell verarbeitet. Wenn jedes Update erfolgreich ist, wird das nächste Update ausgelöst. Diese Trigger können von Dienst zu Dienst oder von einem Saga-Koordinator oder Orchestrator verwaltet werden. Wenn ein Update zu einem beliebigen Zeitpunkt während des Prozesses fehlschlägt, wenden die Dienste, die Ihre Updates bereits abgeschlossen haben, bestimmte Logik an, um Sie umzukehren.

Eine weitere Möglichkeit ist die Verwendung von Domain-gesteuertem Design (DDD) und Command/Query Responsibility Segregation (cqrs), wie im [e-book für .net-mikrodienste](../microservices/microservice-ddd-cqrs-patterns/index.md)beschrieben. Insbesondere kann die Verwendung von Domänen Ereignissen oder der [Ereignis Beschaffung](https://martinfowler.com/eaaDev/EventSourcing.html) dabei helfen, sicherzustellen, dass Updates konsistent sind, wenn Sie nicht sofort angewendet werden.

>[!div class="step-by-step"]
>[Vorherige](application-performance-management.md)
