---
title: 'Anhang: GrpC für WCF-Entwickler'
description: Erörterung verteilter Transaktionen und ihrer Implementierung in modernen microservicesarchitekturen.
ms.date: 09/02/2019
ms.openlocfilehash: 061aef016fd0e4303e1bbcbf0e73cec2b0c54f74
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968222"
---
# <a name="appendix-a---transactions"></a>Anhang A-Transaktionen

Windows Communication Foundation (WCF) unterstützte verteilte Transaktionen, sodass atomarische Vorgänge über mehrere Dienste hinweg durchgeführt werden können. Diese Funktionalität basiert auf der [Microsoft-Distributed Transaction Coordinator](https://docs.microsoft.com/previous-versions/windows/desktop/ms684146(v=vs.85)).

In der modernen mikroserviceslandschaft ist diese Art der automatisierten Verarbeitung verteilter Transaktionen nicht möglich. Es gibt zu viele verschiedene Technologien, darunter relationale Datenbanken, nosql-Datenspeicher und Messaging Systeme, und nicht die Mischung aus Betriebssystemen, Programmiersprachen und Frameworks, die in einer einzigen Umgebung verwendet werden können.

Bei der verteilten WCF-Transaktion handelt es sich um eine Implementierung, die als [Zweiphasencommit (2PC)](https://en.wikipedia.org/wiki/Two-phase_commit_protocol)bezeichnet wird. Es ist möglich, 2PC-Transaktionen manuell zu implementieren, indem Sie Nachrichten über Dienste hinweg koordinieren, offene Transaktionen innerhalb jedes Diensts erstellen und Nachrichten vom Typ "Commit" oder "Rollback" abhängig von Erfolg oder Fehler senden. Die Komplexität, die bei der Verwaltung von 2PC beteiligt ist, kann sich jedoch exponentiell erhöhen, wenn sich Systeme weiterentwickeln, und offene Transaktionen enthalten Datenbanksperren, die sich negativ auf die Leistung auswirken können, oder eine schlechtere Anzahl von Dienst übergreifenden Deadlocks verursachen.

Wenn möglich, ist es am besten, verteilte Transaktionen vollständig zu vermeiden. Wenn zwei Datenelemente so verknüpft sind, dass atomarische Updates erforderlich sind, sollten Sie in Erwägung gezogen werden, beide mit dem gleichen Dienst zu behandeln und diese atomaren Änderungen mithilfe einer einzelnen Anforderung oder Nachricht an diesen Dienst anzuwenden.

Wenn dies nicht möglich ist, besteht eine Alternative darin, das [Saga-Muster](https://microservices.io/patterns/data/saga.html)zu verwenden. In einer Saga werden Updates sequenziell verarbeitet. Wenn jedes Update erfolgreich ausgeführt wird, wird das nächste Update ausgelöst. Diese Trigger können von Dienst zu Dienst oder von einem Saga-Koordinator oder "Orchestrator" weitergegeben werden. Wenn ein Update zu einem beliebigen Zeitpunkt während des Prozesses fehlschlägt, wenden die Dienste, die Ihre Updates bereits abgeschlossen haben, bestimmte Logik an, um Sie umzukehren.

Eine weitere Möglichkeit ist die Verwendung von Domain-gesteuertem Design (DDD) und Command/Query Responsibility Segregation (cqrs), wie im [e-book für .net-mikrodienste](https://docs.microsoft.com/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/)beschrieben. Insbesondere kann die Verwendung von Domänen Ereignissen oder der [Ereignis Beschaffung](https://martinfowler.com/eaaDev/EventSourcing.html) dabei helfen, sicherzustellen, dass Updates konsistent&mdash;werden, wenn Sie nicht sofort&mdash;angewendet werden.

>[!div class="step-by-step"]
>[Vorheriges](application-performance-management.md)
