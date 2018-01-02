---
title: "Implementieren von widerstandsfähigen Anwendungen"
description: ".NET-Microservices-Architektur für .NET-Containeranwendungen | Implementieren von widerstandsfähigen Anwendungen"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: a6fc2f4c963d857be06e194468e2f8514437dd1d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-resilient-applications"></a><span data-ttu-id="33725-104">Implementieren von widerstandsfähigen Anwendungen</span><span class="sxs-lookup"><span data-stu-id="33725-104">Implementing Resilient Applications</span></span>

<span data-ttu-id="33725-105"> *Ihre auf Microservice und Clouds basierenden Anwendungen müssen die Teilfehler umfassen, die letztendlich sicher auftreten. Sie müssen Ihre Anwendung so entwerfen, dass sie widerstandsfähig gegen diese Teilfehler ist.*</span><span class="sxs-lookup"><span data-stu-id="33725-105">*Your microservice and cloud based applications must embrace the partial failures that will certainly occur eventually. You need to design your application so it will be resilient to those partial failures.*</span></span>

<span data-ttu-id="33725-106">Als Stabilität wird die Fähigkeit zum Wiederherstellen nach Fehlern und zum Fortsetzen der Funktionsweise bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="33725-106">Resiliency is the ability to recover from failures and continue to function.</span></span> <span data-ttu-id="33725-107">Es geht nicht um das Vermeiden von Fehlern, sondern um das Akzeptieren der Tatsache, dass Fehler passieren und um eine angemessene Reaktion auf diese, um Ausfallzeiten und Datenverluste zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="33725-107">It is not about avoiding failures, but accepting the fact that failures will happen and responding to them in a way that avoids downtime or data loss.</span></span> <span data-ttu-id="33725-108">Das Ziel der Stabilität ist, die Anwendung nach einem Fehler wieder in einen voll funktionsfähigen Zustand zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="33725-108">The goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="33725-109">Es ist schwierig genug, eine auf Microservices basierende Anwendung zu entwerfen und bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="33725-109">It is challenging enough to design and deploy a microservices-based application.</span></span> <span data-ttu-id="33725-110">Sie müssen die Ausführung Ihrer Anwendung jedoch auch in einer Umgebung gewährleisten, in der Fehler mit Sicherheit auftreten.</span><span class="sxs-lookup"><span data-stu-id="33725-110">But you also need to keep your application running in an environment where some sort of failure is certain.</span></span> <span data-ttu-id="33725-111">Deshalb sollte Ihre Anwendung widerstandsfähig sein.</span><span class="sxs-lookup"><span data-stu-id="33725-111">Therefore, your application should be resilient.</span></span> <span data-ttu-id="33725-112">Sie sollte dafür entworfen sein, mit Teilfehlern wie Netzwerkausfällen oder Knoten bzw. virtuellen Computern, die in der Cloud abstürzen, umzugehen.</span><span class="sxs-lookup"><span data-stu-id="33725-112">It should be designed to cope with partial failures, like network outages or nodes or VMs crashing in the cloud.</span></span> <span data-ttu-id="33725-113">Sogar Microservices (Container), die innerhalb eines Clusters auf einen anderen Knoten verschoben werden, können zeitweilig kurze Fehler in der Anwendung verursachen.</span><span class="sxs-lookup"><span data-stu-id="33725-113">Even microservices (containers) being moved to a different node within a cluster can cause intermittent short failures within the application.</span></span>

<span data-ttu-id="33725-114">In die vielen einzelnen Komponenten Ihrer Anwendung sollten auch Features für die Systemüberwachung integriert werden.</span><span class="sxs-lookup"><span data-stu-id="33725-114">The many individual components of your application should also incorporate health monitoring features.</span></span> <span data-ttu-id="33725-115">Wenn Sie die Richtlinien in diesem Kapitel befolgen, können Sie eine Anwendung erstellen, die trotz vorübergehender Ausfallzeiten oder den normalen Unterbrechungen, die in komplexen und cloudbasierten Bereitstellungen auftreten, reibungslos funktioniert.</span><span class="sxs-lookup"><span data-stu-id="33725-115">By following the guidelines in this chapter, you can create an application that can work smoothly in spite of transient downtime or the normal hiccups that occur in complex and cloud-based deployments.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="33725-116">[Zurück] (../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md) [Weiter] (handle-partial-failure.md)</span><span class="sxs-lookup"><span data-stu-id="33725-116">[Previous] (../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md) [Next] (handle-partial-failure.md)</span></span>
