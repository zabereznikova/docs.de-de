---
title: SOA-Anwendungen
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 7f88daaf0787cf780e7ab9602f35ae4e6ab8308c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155313"
---
# <a name="soa-applications"></a><span data-ttu-id="120f0-103">SOA-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="120f0-103">SOA applications</span></span>

<span data-ttu-id="120f0-104">SOA wurde ein hoher Auslastung Begriff und daher so viele verschiedene Bedeutungen für verschiedene Benutzer.</span><span class="sxs-lookup"><span data-stu-id="120f0-104">SOA was an overused term and meant so many different things to different people.</span></span> <span data-ttu-id="120f0-105">Aber zumindest und als gemeinsame Nenner, d. h. einer SOA oder die Dienstorientierung, Mean Struktur der Architektur Ihrer Anwendung durch zerlegen es in mehrere Dienste (am häufigsten als HTTP-Dienste), die in verschiedenen Arten klassifiziert werden können Subsysteme Alternativ können Sie auch in anderen Fällen als Ebenen.</span><span class="sxs-lookup"><span data-stu-id="120f0-105">But at a minimum and as a common denominator, SOA, or service orientation, mean that you structure the architecture of your application by decomposing it in multiple services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="120f0-106">Heute können Sie diese Dienste als Docker-Container bereitstellen, die Bereitstellung-bezogene Probleme gelöst, da alle Abhängigkeiten in das Container-Abbild enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="120f0-106">Today, you can deploy those services as Docker containers, which solves deployment-related issues because all of the dependencies are included within the container image.</span></span> <span data-ttu-id="120f0-107">Jedoch wenn Sie sich zur horizontalen hochskalierung SOAs müssen, können Probleme auftreten, wenn Sie basierend auf einzelne Instanzen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="120f0-107">However, when you need to scale-out SOAs, you might encounter challenges if you are deploying based on single instances.</span></span> <span data-ttu-id="120f0-108">Dies ist in eine Docker-clusteringsoftware oder Orchestrator Sie unterstützen.</span><span class="sxs-lookup"><span data-stu-id="120f0-108">This is where a Docker clustering software or orchestrator will help you.</span></span> <span data-ttu-id="120f0-109">Betrachten wir dies im nächsten Abschnitt ausführlicher beim Untersuchen wir microservicesansätzen.</span><span class="sxs-lookup"><span data-stu-id="120f0-109">We'll look at this in greater detail in the next section when we examine microservices approaches.</span></span>

<span data-ttu-id="120f0-110">Am Ende des Tages eignen sich die Container-clustering-Lösungen für beide eine konventionelle SOA-Architektur oder für eine erweiterte Microservices-Architektur, die in der besitzt jeder Microservice auf das Datenmodell.</span><span class="sxs-lookup"><span data-stu-id="120f0-110">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture or for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="120f0-111">Und Dank mehrere Datenbanken, Sie auch können horizontale Skalierung die Datenebene anstelle der Arbeit mit monolithischen Datenbanken, die von der SOA-Dienste gemeinsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="120f0-111">And, thanks to multiple databases, you also can scale-out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="120f0-112">Allerdings ist die Diskussion über die Daten aufgeteilt werden, ausschließlich über Architektur und Entwurf.</span><span class="sxs-lookup"><span data-stu-id="120f0-112">However, the discussion about splitting the data is purely about architecture and design.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="120f0-113">[Zurück](state-and-data-in-docker-applications.md)
>[Weiter](orchestrate-high-scalability-availability.md)</span><span class="sxs-lookup"><span data-stu-id="120f0-113">[Previous](state-and-data-in-docker-applications.md)
[Next](orchestrate-high-scalability-availability.md)</span></span>