---
title: Implementieren von widerstandsfähigen Anwendungen
description: .NET-Microservices-Architektur für .NET-Containeranwendungen | Implementieren von widerstandsfähigen Anwendungen
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/08/2018
ms.openlocfilehash: dc0db8f0cdfa77bcca467c3c632b3d93de8851d8
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37875120"
---
# <a name="implementing-resilient-applications"></a><span data-ttu-id="f5b87-103">Implementieren von widerstandsfähigen Anwendungen</span><span class="sxs-lookup"><span data-stu-id="f5b87-103">Implementing Resilient Applications</span></span>

<span data-ttu-id="f5b87-104">*Ihre auf Microservice und Clouds basierenden Anwendungen müssen die Teilfehler umfassen, die letztendlich sicher auftreten. Sie müssen Ihre Anwendung so entwerfen, dass sie widerstandsfähig gegen diese Teilfehler ist.*</span><span class="sxs-lookup"><span data-stu-id="f5b87-104">*Your microservice and cloud-based applications must embrace the partial failures that will certainly occur eventually. You need to design your application so it will be resilient to those partial failures.*</span></span>

<span data-ttu-id="f5b87-105">Als Stabilität wird die Fähigkeit zum Wiederherstellen nach Fehlern und zum Fortsetzen der Funktionsweise bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f5b87-105">Resiliency is the ability to recover from failures and continue to function.</span></span> <span data-ttu-id="f5b87-106">Es geht nicht um das Vermeiden von Fehlern, sondern um das Akzeptieren der Tatsache, dass Fehler passieren und um eine angemessene Reaktion auf diese, um Ausfallzeiten und Datenverluste zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="f5b87-106">It is not about avoiding failures but accepting the fact that failures will happen and responding to them in a way that avoids downtime or data loss.</span></span> <span data-ttu-id="f5b87-107">Das Ziel der Stabilität ist, die Anwendung nach einem Fehler wieder in einen voll funktionsfähigen Zustand zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="f5b87-107">The goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="f5b87-108">Es ist schwierig genug, eine auf Microservices basierende Anwendung zu entwerfen und bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f5b87-108">It is challenging enough to design and deploy a microservices-based application.</span></span> <span data-ttu-id="f5b87-109">Sie müssen die Ausführung Ihrer Anwendung jedoch auch in einer Umgebung gewährleisten, in der Fehler mit Sicherheit auftreten.</span><span class="sxs-lookup"><span data-stu-id="f5b87-109">But you also need to keep your application running in an environment where some sort of failure is certain.</span></span> <span data-ttu-id="f5b87-110">Deshalb sollte Ihre Anwendung widerstandsfähig sein.</span><span class="sxs-lookup"><span data-stu-id="f5b87-110">Therefore, your application should be resilient.</span></span> <span data-ttu-id="f5b87-111">Sie sollte dafür entworfen sein, mit Teilfehlern wie Netzwerkausfällen oder Knoten bzw. virtuellen Computern, die in der Cloud abstürzen, umzugehen.</span><span class="sxs-lookup"><span data-stu-id="f5b87-111">It should be designed to cope with partial failures, like network outages or nodes or VMs crashing in the cloud.</span></span> <span data-ttu-id="f5b87-112">Sogar Microservices (Container), die innerhalb eines Clusters auf einen anderen Knoten verschoben werden, können zeitweilig kurze Fehler in der Anwendung verursachen.</span><span class="sxs-lookup"><span data-stu-id="f5b87-112">Even microservices (containers) being moved to a different node within a cluster can cause intermittent short failures within the application.</span></span>

<span data-ttu-id="f5b87-113">In die vielen einzelnen Komponenten Ihrer Anwendung sollten auch Features für die Systemüberwachung integriert werden.</span><span class="sxs-lookup"><span data-stu-id="f5b87-113">The many individual components of your application should also incorporate health monitoring features.</span></span> <span data-ttu-id="f5b87-114">Wenn Sie die Richtlinien in diesem Kapitel befolgen, können Sie eine Anwendung erstellen, die trotz vorübergehender Ausfallzeiten oder den normalen Unterbrechungen, die in komplexen und cloudbasierten Bereitstellungen auftreten, reibungslos funktioniert.</span><span class="sxs-lookup"><span data-stu-id="f5b87-114">By following the guidelines in this chapter, you can create an application that can work smoothly in spite of transient downtime or the normal hiccups that occur in complex and cloud-based deployments.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="f5b87-115">[Zurück](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
[Weiter](handle-partial-failure.md)</span><span class="sxs-lookup"><span data-stu-id="f5b87-115">[Previous](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
[Next](handle-partial-failure.md)</span></span>
