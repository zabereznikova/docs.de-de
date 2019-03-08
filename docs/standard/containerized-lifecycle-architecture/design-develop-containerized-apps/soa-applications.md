---
title: SOA-Anwendungen
description: Beachten Sie, dass der Container kann auch nützlich für eine Bereitstellungsoption SOA-Anwendungen sein.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: ee71873ac15246f979fd2b08d92280ba797ff6ee
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675796"
---
# <a name="service-oriented-applications"></a><span data-ttu-id="425c7-103">Dienstorientierte Anwendungen</span><span class="sxs-lookup"><span data-stu-id="425c7-103">Service-oriented applications</span></span>

<span data-ttu-id="425c7-104">Dienstorientierte Architektur (SOA) wurde ein hoher Auslastung Ausdruck, der viele verschiedene Dinge an andere Personen gedacht.</span><span class="sxs-lookup"><span data-stu-id="425c7-104">Service-Oriented Architecture (SOA) was an overused term that meant many different things to different people.</span></span> <span data-ttu-id="425c7-105">Der gemeinsame Nenner, SOA bedeutet jedoch, dass Sie strukturieren die Architektur Ihrer Anwendung durch zerlegen ihn in mehrere Dienste (am häufigsten als HTTP-Dienste), die in verschiedenen wie Subsysteme oder in anderen Fällen als Ebenen klassifiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="425c7-105">But as a common denominator, SOA means that you structure the architecture of your application by decomposing it into several services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="425c7-106">Heute können Sie diese Dienste als Docker-Container bereitstellen, die Bereitstellung-bezogene Probleme zu lösen, da alle Abhängigkeiten im containerimage enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="425c7-106">Today, you can deploy those services as Docker containers, which solve deployment-related issues because all of the dependencies are included in the container image.</span></span> <span data-ttu-id="425c7-107">Jedoch wenn Sie zu SOAs skalieren müssen, können Probleme auftreten, wenn Sie basierend auf einzelne Instanzen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="425c7-107">However, when you need to scale out SOAs, you might encounter challenges if you're deploying based on single instances.</span></span> <span data-ttu-id="425c7-108">Diese Aufforderung kann mit Docker-clusteringsoftware oder ein Orchestrator behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="425c7-108">This challenge can be handled using Docker clustering software or an orchestrator.</span></span> <span data-ttu-id="425c7-109">Betrachten wir orchestratoren ausführlicher im nächsten Abschnitt, wenn, Ansätze für Microservices untersucht.</span><span class="sxs-lookup"><span data-stu-id="425c7-109">We'll look at orchestrators in greater detail in the next section, when we explore microservices approaches.</span></span>

<span data-ttu-id="425c7-110">Für herkömmliche serviceorientierte Architekturen und erweiterte Microservicesarchitekturen sind Docker-Container nützlich, jedoch nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="425c7-110">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="425c7-111">Am Ende des Tages eignen sich die Container-clustering-Lösungen für beide eine konventionelle SOA-Architektur und für eine erweiterte Microservices-Architektur, die in der besitzt jeder Microservice auf das Datenmodell.</span><span class="sxs-lookup"><span data-stu-id="425c7-111">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture and for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="425c7-112">Und Dank mehrere Datenbanken, außerdem können Sie horizontal hochskalieren der Datenebene anstelle der Arbeit mit monolithischen Datenbanken, die von der SOA-Dienste gemeinsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="425c7-112">And thanks to multiple databases, you also can scale out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="425c7-113">Allerdings ist die Diskussion über die Daten aufgeteilt werden, ausschließlich über Architektur und Entwurf.</span><span class="sxs-lookup"><span data-stu-id="425c7-113">However, the discussion about splitting the data is purely about architecture and design.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="425c7-114">[Zurück](state-and-data-in-docker-applications.md)
>[Weiter](orchestrate-high-scalability-availability.md)</span><span class="sxs-lookup"><span data-stu-id="425c7-114">[Previous](state-and-data-in-docker-applications.md)
[Next](orchestrate-high-scalability-availability.md)</span></span>
