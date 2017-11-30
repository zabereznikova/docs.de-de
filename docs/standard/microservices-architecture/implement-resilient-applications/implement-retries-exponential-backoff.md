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
# <a name="implementing-retries-with-exponential-backoff"></a><span data-ttu-id="cfb24-104">Implementieren von Wiederholungen mit exponenzieller Wartezeit</span><span class="sxs-lookup"><span data-stu-id="cfb24-104">Implementing retries with exponential backoff</span></span>

<span data-ttu-id="cfb24-105">[*Wiederholungen mit exponenzieller* ](https://docs.microsoft.com/azure/architecture/patterns/retry) ist eine Technik, die versuchen, wiederholen Sie dann einen Vorgang mit einer exponentiell zunehmenden Wartezeit, bis eine maximale Anzahl von Wiederholungsversuchen erreicht wurde (die [Exponentielles Backoff](https://en.wikipedia.org/wiki/Exponential_backoff)).</span><span class="sxs-lookup"><span data-stu-id="cfb24-105">[*Retries with exponential backoff*](https://docs.microsoft.com/azure/architecture/patterns/retry) is a technique that attempts to retry an operation, with an exponentially increasing wait time, until a maximum retry count has been reached (the [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff)).</span></span> <span data-ttu-id="cfb24-106">Diese Technik Verwaltungsteam die Tatsache, dass Cloudressourcen zeitweise für mehr als ein paar Sekunden aus irgendeinem Grund ist möglicherweise nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cfb24-106">This technique embraces the fact that cloud resources might intermittently be unavailable for more than a few seconds for any reason.</span></span> <span data-ttu-id="cfb24-107">Ein Orchestrator wird z. B. eine einen Container zu einem anderen Knoten in einem Cluster für den Lastenausgleich verschoben.</span><span class="sxs-lookup"><span data-stu-id="cfb24-107">For example, an orchestrator might be moving a container to another node in a cluster for load balancing.</span></span> <span data-ttu-id="cfb24-108">Während dieser Zeit möglicherweise manche Anforderungen nicht.</span><span class="sxs-lookup"><span data-stu-id="cfb24-108">During that time, some requests might fail.</span></span> <span data-ttu-id="cfb24-109">Ein weiteres Beispiel möglicherweise eine Datenbank wie SQL Azure, in dem eine Datenbank auf einen anderen Server für Load balancing, wodurch sich die Datenbank verschoben werden kann ein paar Sekunden lang nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="cfb24-109">Another example could be a database like SQL Azure, where a database can be moved to another server for load balancing, causing the database to be unavailable for a few seconds.</span></span>

<span data-ttu-id="cfb24-110">Es gibt viele Ansätze zum Implementieren von Logik von Wiederholungen mit exponenzieller Wartezeit.</span><span class="sxs-lookup"><span data-stu-id="cfb24-110">There are many approaches to implement retries logic with exponential backoff.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="cfb24-111">[Vorherigen] (teilweise-Fehler-strategies.md) [weiter] (Implement-resilient-entity-framework-core-sql-connections.md)</span><span class="sxs-lookup"><span data-stu-id="cfb24-111">[Previous] (partial-failure-strategies.md) [Next] (implement-resilient-entity-framework-core-sql-connections.md)</span></span>
