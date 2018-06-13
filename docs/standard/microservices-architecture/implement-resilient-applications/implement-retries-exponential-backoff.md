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
# <a name="implementing-retries-with-exponential-backoff"></a><span data-ttu-id="b3c11-103">Implementieren von Wiederholungen mit exponentiellem Backoff</span><span class="sxs-lookup"><span data-stu-id="b3c11-103">Implementing retries with exponential backoff</span></span>

<span data-ttu-id="b3c11-104">Bei [*Wiederholungen mit exponentiellem Backoff*](https://docs.microsoft.com/azure/architecture/patterns/retry) handelt es sich um eine Technik, die versucht, einen Vorgang mit einer sich exponentiell erhöhenden Wartezeit zu wiederholen, bis die maximale Anzahl von Wiederholungsversuchen erreicht ist (der [exponentielle Backoff](https://en.wikipedia.org/wiki/Exponential_backoff)).</span><span class="sxs-lookup"><span data-stu-id="b3c11-104">[*Retries with exponential backoff*](https://docs.microsoft.com/azure/architecture/patterns/retry) is a technique that attempts to retry an operation, with an exponentially increasing wait time, until a maximum retry count has been reached (the [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff)).</span></span> <span data-ttu-id="b3c11-105">Diese Technik berücksichtigt die Tatsache, dass Cloudressourcen aus unterschiedlichen Gründen zeitweise für mehr als ein paar Sekunden nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b3c11-105">This technique embraces the fact that cloud resources might intermittently be unavailable for more than a few seconds for any reason.</span></span> <span data-ttu-id="b3c11-106">Ein Orchestrator könnte beispielsweise einen Container für den Lastenausgleich auf einen anderen Knoten in einem Cluster verschieben.</span><span class="sxs-lookup"><span data-stu-id="b3c11-106">For example, an orchestrator might be moving a container to another node in a cluster for load balancing.</span></span> <span data-ttu-id="b3c11-107">Währenddessen schlagen einige Anforderungen möglicherweise fehl.</span><span class="sxs-lookup"><span data-stu-id="b3c11-107">During that time, some requests might fail.</span></span> <span data-ttu-id="b3c11-108">Ein weiteres Beispiel wäre eine Datenbank wie SQL Azure. Hierbei kann eine Datenbank für den Lastenausgleich auf einen anderen Server verschoben werden, wodurch die Datenbank für einige Sekunden nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b3c11-108">Another example could be a database like SQL Azure, where a database can be moved to another server for load balancing, causing the database to be unavailable for a few seconds.</span></span>

<span data-ttu-id="b3c11-109">Es gibt viele Ansätze, um Wiederholungen mit exponentiellem Backoff zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="b3c11-109">There are many approaches to implement retries logic with exponential backoff.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="b3c11-110">[Zurück] (partial-failure-strategies.md) [Weiter] (implement-resilient-entity-framework-core-sql-connections.md)</span><span class="sxs-lookup"><span data-stu-id="b3c11-110">[Previous] (partial-failure-strategies.md) [Next] (implement-resilient-entity-framework-core-sql-connections.md)</span></span>
