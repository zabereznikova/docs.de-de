---
title: Implementieren von widerstandsfähigen Anwendungen
description: .NET-Microservices-Architektur für .NET-Containeranwendungen | Implementieren von widerstandsfähigen Anwendungen
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: ddb0f54b15735b9192d2088495947588f59829a0
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106050"
---
# <a name="implementing-resilient-applications"></a>Implementieren von widerstandsfähigen Anwendungen

*Ihre auf Microservice und Clouds basierenden Anwendungen müssen die Teilfehler umfassen, die letztendlich sicher auftreten. Sie müssen Ihre Anwendung so entwerfen, dass sie widerstandsfähig gegen diese Teilfehler ist.*

Als Stabilität wird die Fähigkeit zum Wiederherstellen nach Fehlern und zum Fortsetzen der Funktionsweise bezeichnet. Es geht nicht um das Vermeiden von Fehlern, sondern um das Akzeptieren der Tatsache, dass Fehler passieren und um eine angemessene Reaktion auf diese, um Ausfallzeiten und Datenverluste zu vermeiden. Das Ziel der Stabilität ist, die Anwendung nach einem Fehler wieder in einen voll funktionsfähigen Zustand zu versetzen.

Es ist schwierig genug, eine auf Microservices basierende Anwendung zu entwerfen und bereitzustellen. Sie müssen die Ausführung Ihrer Anwendung jedoch auch in einer Umgebung gewährleisten, in der Fehler mit Sicherheit auftreten. Deshalb sollte Ihre Anwendung widerstandsfähig sein. Sie sollte dafür entworfen sein, mit Teilfehlern wie Netzwerkausfällen oder Knoten bzw. virtuellen Computern, die in der Cloud abstürzen, umzugehen. Sogar Microservices (Container), die innerhalb eines Clusters auf einen anderen Knoten verschoben werden, können zeitweilig kurze Fehler in der Anwendung verursachen.

In die vielen einzelnen Komponenten Ihrer Anwendung sollten auch Features für die Systemüberwachung integriert werden. Wenn Sie die Richtlinien in diesem Kapitel befolgen, können Sie eine Anwendung erstellen, die trotz vorübergehender Ausfallzeiten oder den normalen Unterbrechungen, die in komplexen und cloudbasierten Bereitstellungen auftreten, reibungslos funktioniert.


>[!div class="step-by-step"]
[Zurück](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
[Weiter](handle-partial-failure.md)
