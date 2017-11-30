---
title: Implementieren von Wiederholungen mit exponenzieller Wartezeit
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Implementieren von Wiederholungen mit exponenzieller Wartezeit"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c8ad8c6363ddff59915efc076161fe6b76074bbf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-retries-with-exponential-backoff"></a>Implementieren von Wiederholungen mit exponenzieller Wartezeit

[*Wiederholungen mit exponenzieller* ](https://docs.microsoft.com/azure/architecture/patterns/retry) ist eine Technik, die versuchen, wiederholen Sie dann einen Vorgang mit einer exponentiell zunehmenden Wartezeit, bis eine maximale Anzahl von Wiederholungsversuchen erreicht wurde (die [Exponentielles Backoff](https://en.wikipedia.org/wiki/Exponential_backoff)). Diese Technik Verwaltungsteam die Tatsache, dass Cloudressourcen zeitweise für mehr als ein paar Sekunden aus irgendeinem Grund ist möglicherweise nicht verfügbar. Ein Orchestrator wird z. B. eine einen Container zu einem anderen Knoten in einem Cluster für den Lastenausgleich verschoben. Während dieser Zeit möglicherweise manche Anforderungen nicht. Ein weiteres Beispiel möglicherweise eine Datenbank wie SQL Azure, in dem eine Datenbank auf einen anderen Server für Load balancing, wodurch sich die Datenbank verschoben werden kann ein paar Sekunden lang nicht verfügbar ist.

Es gibt viele Ansätze zum Implementieren von Logik von Wiederholungen mit exponenzieller Wartezeit.


>[!div class="step-by-step"]
[Vorherigen] (teilweise-Fehler-strategies.md) [weiter] (Implement-resilient-entity-framework-core-sql-connections.md)
