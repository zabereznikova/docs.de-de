---
title: Implementieren von Wiederholungen mit exponentiellem Backoff
description: Erfahren Sie, wie Sie Wiederholungen mit exponentiellem Backoff implementieren.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/16/2018
ms.openlocfilehash: 421a4535888f432974c764b238c06b5b323aefb3
ms.sourcegitcommit: 542aa405b295955eb055765f33723cb8b588d0d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2019
ms.locfileid: "54362079"
---
# <a name="implement-retries-with-exponential-backoff"></a>Implementieren von Wiederholungen mit exponentiellem Backoff

Bei [*Wiederholungen mit exponentiellem Backoff*](/azure/architecture/patterns/retry) handelt es sich um eine Technik, die einen Vorgang mit einer sich exponentiell erhöhenden Wartezeit wiederholt, bis die maximale Anzahl von Wiederholungsversuchen erreicht ist (der [exponentielle Backoff](https://en.wikipedia.org/wiki/Exponential_backoff)). Diese Technik berücksichtigt die Tatsache, dass Cloudressourcen aus unterschiedlichen Gründen zeitweise für mehr als ein paar Sekunden nicht verfügbar sind. Ein Orchestrator könnte beispielsweise einen Container für den Lastenausgleich auf einen anderen Knoten in einem Cluster verschieben. Währenddessen schlagen einige Anforderungen möglicherweise fehl. Ein weiteres Beispiel wäre eine Datenbank wie SQL Azure. Hierbei kann eine Datenbank für den Lastenausgleich auf einen anderen Server verschoben werden, wodurch die Datenbank für einige Sekunden nicht verfügbar ist.

Es gibt viele Ansätze, um Wiederholungen mit exponentiellem Backoff zu implementieren.

>[!div class="step-by-step"]
>[Zurück](partial-failure-strategies.md)
>[Weiter](implement-resilient-entity-framework-core-sql-connections.md)