---
title: SOA-Anwendungen
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 81d2b60303e051568b664ec20225d835a09187c0
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="soa-applications"></a><span data-ttu-id="73844-104">SOA-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="73844-104">SOA applications</span></span>

<span data-ttu-id="73844-105">SOA wurde ein Überbelastung Begriff und so viele verschiedene Bedeutungen für verschiedene Benutzer vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="73844-105">SOA was an overused term and meant so many different things to different people.</span></span> <span data-ttu-id="73844-106">Aber zumindest und als gemeinsame Nenner, SOA oder dienstausrichtung, Mittelwert Struktur die Architektur der Anwendung durch zerlegen es in mehreren Diensten (meist als HTTP-Dienste), die in verschiedenen Arten klassifiziert werden können Subsysteme oder in anderen Fällen wie leisten.</span><span class="sxs-lookup"><span data-stu-id="73844-106">But at a minimum and as a common denominator, SOA, or service orientation, mean that you structure the architecture of your application by decomposing it in multiple services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="73844-107">Heute können Sie diese Dienste als Docker-Containern bereitstellen, löst die Probleme in Bezug auf Bereitstellung, da alle Abhängigkeiten in Container-Abbild enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="73844-107">Today, you can deploy those services as Docker containers, which solves deployment-related issues because all of the dependencies are included within the container image.</span></span> <span data-ttu-id="73844-108">Jedoch wenn dienstorientierter Architekturen mit horizontaler Skalierung Sie müssen, möglicherweise Probleme auftreten, wenn Sie basierend auf einzelne Instanzen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="73844-108">However, when you need to scale-out SOAs, you might encounter challenges if you are deploying based on single instances.</span></span> <span data-ttu-id="73844-109">Dies ist, bei denen ein clustering-Software oder Orchestrator Docker Sie beitragen.</span><span class="sxs-lookup"><span data-stu-id="73844-109">This is where a Docker clustering software or orchestrator will help you.</span></span> <span data-ttu-id="73844-110">Betrachten wir dies im nächsten Abschnitt ausführlich beim Untersuchen wir Microservices Ansätze.</span><span class="sxs-lookup"><span data-stu-id="73844-110">We'll look at this in greater detail in the next section when we examine microservices approaches.</span></span>

<span data-ttu-id="73844-111">Am Ende des Tages eignen sich die Container-clustering-Lösungen für beide eine herkömmliche SOA-Architektur oder für eine erweiterte Microservices-Architektur, in der jede Microservice seine Datenmodell besitzt.</span><span class="sxs-lookup"><span data-stu-id="73844-111">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture or for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="73844-112">Und Dank mehrere Datenbanken Sie auch können mit horizontaler Skalierung die Datenebene statt arbeiten mit monolithisch Datenbanken, die von der SOA-Diensten gemeinsam genutzt.</span><span class="sxs-lookup"><span data-stu-id="73844-112">And, thanks to multiple databases, you also can scale-out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="73844-113">Ist jedoch die Erläuterung zum Teilen der Daten ausschließlich über die Architektur und Entwurf.</span><span class="sxs-lookup"><span data-stu-id="73844-113">However, the discussion about splitting the data is purely about architecture and design.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="73844-114">[Vorherigen] (State-and-data-in-docker-applications.md) [weiter] (orchestrieren-High-Skalierbarkeit-availability.md)</span><span class="sxs-lookup"><span data-stu-id="73844-114">[Previous] (state-and-data-in-docker-applications.md) [Next] (orchestrate-high-scalability-availability.md)</span></span>
