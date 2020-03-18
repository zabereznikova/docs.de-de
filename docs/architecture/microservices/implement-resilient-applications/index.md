---
title: Implementieren von resilienten Anwendungen
description: Erfahren Sie mehr über Resilienz, ein Kernkonzept in einer Microservicesarchitektur. Sie müssen wissen, wie Sie mit vorübergehenden Ausfällen sinnvoll umgehen, wenn diese auftreten.
ms.date: 01/30/2020
ms.openlocfilehash: 46276a6b9b36a494bfae657275692ca9d5554d86
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "78847231"
---
# <a name="implement-resilient-applications"></a>Implementieren von resilienten Anwendungen

*Ihre auf Microservice und Clouds basierenden Anwendungen müssen die Teilfehler umfassen, die letztendlich sicher auftreten. Sie müssen Ihre Anwendung so entwerfen, dass sie widerstandsfähig gegen diese Teilfehler ist.*

Als Stabilität wird die Fähigkeit zum Wiederherstellen nach Fehlern und zum Fortsetzen der Funktionsweise bezeichnet. Es geht nicht um das Vermeiden von Fehlern, sondern um das Akzeptieren der Tatsache, dass Fehler passieren und um eine angemessene Reaktion auf diese, um Ausfallzeiten und Datenverluste zu vermeiden. Das Ziel der Stabilität ist, die Anwendung nach einem Fehler wieder in einen voll funktionsfähigen Zustand zu versetzen.

Es ist schwierig genug, eine auf Microservices basierende Anwendung zu entwerfen und bereitzustellen. Sie müssen die Ausführung Ihrer Anwendung jedoch auch in einer Umgebung gewährleisten, in der Fehler mit Sicherheit auftreten. Deshalb sollte Ihre Anwendung widerstandsfähig sein. Sie sollte dafür entworfen sein, mit Teilfehlern wie Netzwerkausfällen oder Knoten bzw. virtuellen Computern, die in der Cloud abstürzen, umzugehen. Sogar Microservices (Container), die innerhalb eines Clusters auf einen anderen Knoten verschoben werden, können zeitweilig kurze Fehler in der Anwendung verursachen.

In die vielen einzelnen Komponenten Ihrer Anwendung sollten auch Features für die Systemüberwachung integriert werden. Wenn Sie die Richtlinien in diesem Kapitel befolgen, können Sie eine Anwendung erstellen, die trotz vorübergehender Ausfallzeiten oder den normalen Unterbrechungen, die in komplexen und cloudbasierten Bereitstellungen auftreten, reibungslos funktioniert.

>[!IMPORTANT]
> eShopOnContainer verwendete bis Version 3.0.0 die [Polly-Bibliothek](http://www.thepollyproject.org/), um Resilienz mithilfe von [typisierten Clients](./use-httpclientfactory-to-implement-resilient-http-requests.md) zu implementieren.
>
> Ab Version 3.0.0 wird die Resilienz von HTTP-Aufrufen mit einem [Linkerd-Mesh](https://linkerd.io/) implementiert, das Wiederholungsversuche auf transparente und konfigurierbare Weise in einem Kubernetes-Cluster verarbeitet, ohne dass Sie sich im Code um diese Vorgänge kümmern müssen.
>
> Die Polly-Bibliothek wird weiterhin verwendet, um Resilienz für Datenbankverbindungen zu implementieren, insbesondere beim Starten der Dienste.

>[!WARNING]
> Alle Codebeispiele in diesem Abschnitt waren vor der Verwendung von Linkerd gültig und wurden nicht auf den derzeit aktuellen Code aktualisiert. Daher sind sie im Kontext dieses Abschnitts sinnvoll.

>[!div class="step-by-step"]
>[Zurück](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
>[Weiter](handle-partial-failure.md)
