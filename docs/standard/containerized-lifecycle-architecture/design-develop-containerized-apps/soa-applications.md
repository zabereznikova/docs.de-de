---
title: SOA-Anwendungen
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 37313c4eb437b6b7a362456a7d1ee3b3aecb6020
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569417"
---
# <a name="soa-applications"></a><span data-ttu-id="d7ad5-103">SOA-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="d7ad5-103">SOA applications</span></span>

<span data-ttu-id="d7ad5-104">SOA wurde ein Überbelastung Begriff und so viele verschiedene Bedeutungen für verschiedene Benutzer vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="d7ad5-104">SOA was an overused term and meant so many different things to different people.</span></span> <span data-ttu-id="d7ad5-105">Aber zumindest und als gemeinsame Nenner, SOA oder dienstausrichtung, Mittelwert Struktur die Architektur der Anwendung durch zerlegen es in mehreren Diensten (meist als HTTP-Dienste), die in verschiedenen Arten klassifiziert werden können Subsysteme oder in anderen Fällen wie leisten.</span><span class="sxs-lookup"><span data-stu-id="d7ad5-105">But at a minimum and as a common denominator, SOA, or service orientation, mean that you structure the architecture of your application by decomposing it in multiple services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="d7ad5-106">Heute können Sie diese Dienste als Docker-Containern bereitstellen, löst die Probleme in Bezug auf Bereitstellung, da alle Abhängigkeiten in Container-Abbild enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d7ad5-106">Today, you can deploy those services as Docker containers, which solves deployment-related issues because all of the dependencies are included within the container image.</span></span> <span data-ttu-id="d7ad5-107">Jedoch wenn dienstorientierter Architekturen mit horizontaler Skalierung Sie müssen, möglicherweise Probleme auftreten, wenn Sie basierend auf einzelne Instanzen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d7ad5-107">However, when you need to scale-out SOAs, you might encounter challenges if you are deploying based on single instances.</span></span> <span data-ttu-id="d7ad5-108">Dies ist, bei denen ein clustering-Software oder Orchestrator Docker Sie beitragen.</span><span class="sxs-lookup"><span data-stu-id="d7ad5-108">This is where a Docker clustering software or orchestrator will help you.</span></span> <span data-ttu-id="d7ad5-109">Betrachten wir dies im nächsten Abschnitt ausführlich beim Untersuchen wir Microservices Ansätze.</span><span class="sxs-lookup"><span data-stu-id="d7ad5-109">We'll look at this in greater detail in the next section when we examine microservices approaches.</span></span>

<span data-ttu-id="d7ad5-110">Am Ende des Tages eignen sich die Container-clustering-Lösungen für beide eine herkömmliche SOA-Architektur oder für eine erweiterte Microservices-Architektur, in der jede Microservice seine Datenmodell besitzt.</span><span class="sxs-lookup"><span data-stu-id="d7ad5-110">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture or for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="d7ad5-111">Und Dank mehrere Datenbanken Sie auch können mit horizontaler Skalierung die Datenebene statt arbeiten mit monolithisch Datenbanken, die von der SOA-Diensten gemeinsam genutzt.</span><span class="sxs-lookup"><span data-stu-id="d7ad5-111">And, thanks to multiple databases, you also can scale-out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="d7ad5-112">Ist jedoch die Erläuterung zum Teilen der Daten ausschließlich über die Architektur und Entwurf.</span><span class="sxs-lookup"><span data-stu-id="d7ad5-112">However, the discussion about splitting the data is purely about architecture and design.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="d7ad5-113">[Vorherigen] (State-and-data-in-docker-applications.md) [weiter] (orchestrieren-High-Skalierbarkeit-availability.md)</span><span class="sxs-lookup"><span data-stu-id="d7ad5-113">[Previous] (state-and-data-in-docker-applications.md) [Next] (orchestrate-high-scalability-availability.md)</span></span>
