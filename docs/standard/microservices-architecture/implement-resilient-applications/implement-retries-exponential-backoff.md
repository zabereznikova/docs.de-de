---
title: Implementieren von Wiederholungen mit exponentiellem Backoff
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Implementieren von Wiederholungen mit exponentiellem Backoff
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 7f909c6f81abce80bfdf118112271f1f87254793
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571422"
---
# <a name="implementing-retries-with-exponential-backoff"></a>Implementieren von Wiederholungen mit exponentiellem Backoff

Bei [*Wiederholungen mit exponentiellem Backoff*](https://docs.microsoft.com/azure/architecture/patterns/retry) handelt es sich um eine Technik, die versucht, einen Vorgang mit einer sich exponentiell erhöhenden Wartezeit zu wiederholen, bis die maximale Anzahl von Wiederholungsversuchen erreicht ist (der [exponentielle Backoff](https://en.wikipedia.org/wiki/Exponential_backoff)). Diese Technik berücksichtigt die Tatsache, dass Cloudressourcen aus unterschiedlichen Gründen zeitweise für mehr als ein paar Sekunden nicht verfügbar sind. Ein Orchestrator könnte beispielsweise einen Container für den Lastenausgleich auf einen anderen Knoten in einem Cluster verschieben. Währenddessen schlagen einige Anforderungen möglicherweise fehl. Ein weiteres Beispiel wäre eine Datenbank wie SQL Azure. Hierbei kann eine Datenbank für den Lastenausgleich auf einen anderen Server verschoben werden, wodurch die Datenbank für einige Sekunden nicht verfügbar ist.

Es gibt viele Ansätze, um Wiederholungen mit exponentiellem Backoff zu implementieren.


>[!div class="step-by-step"]
[Zurück] (partial-failure-strategies.md) [Weiter] (implement-resilient-entity-framework-core-sql-connections.md)
