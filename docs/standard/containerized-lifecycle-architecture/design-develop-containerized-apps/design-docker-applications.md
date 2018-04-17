---
title: Entwerfen von Docker-Anwendungen
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 54f6f1ecdd89b85d4f44136da9a5ec9610f170a9
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="design-docker-applications"></a><span data-ttu-id="48aed-103">Entwerfen von Docker-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="48aed-103">Design Docker applications</span></span>

<span data-ttu-id="48aed-104">Die grundlegenden Konzepte in Bezug auf Container und Docker, Kapitel 1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="48aed-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="48aed-105">Diese Information ist die grundlegende Informationen, die Sie benötigen, um zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="48aed-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="48aed-106">Allerdings unternehmensanwendungen können komplex sein und mehrere Dienste anstelle von einem Einzelgerät oder Container besteht.</span><span class="sxs-lookup"><span data-stu-id="48aed-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="48aed-107">Für die Fälle optional verwenden müssen Sie zusätzliche Ansätze zum Entwerfen, z. B. dienstorientierte Architektur (SOA) und die erweiterte Microservices Konzepte und Container orchestrierungskonzepte kennen, können.</span><span class="sxs-lookup"><span data-stu-id="48aed-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="48aed-108">Der Rahmen dieses Dokuments ist nicht beschränkt auf Microservices jedoch auf alle Docker-Anwendungslebenszyklus, daher ist nicht untersuchen Microservices Architektur im Detail, da Sie auch können Container und Docker mit regulären SÃO, Hintergrundaufgaben oder Aufträge, oder sogar mit monolithisch Anwendung Bereitstellung Ansätze.</span><span class="sxs-lookup"><span data-stu-id="48aed-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SAO, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="48aed-109">Bevor wir in den Lebenszyklus der Anwendung und DevOps erhalten, ist es jedoch wichtig zu wissen, wie Sie Entwurf durchlaufen und erstellen Ihre Anwendung und was Ihre Entscheidungen zum Entwurf sind.</span><span class="sxs-lookup"><span data-stu-id="48aed-109">However, before we get into the application life cycle and DevOps, it is important to know how you are going to design and construct your application and what are your design choices.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="48aed-110">[Vorherigen] (index.md) [weiter] (Common-Container-Design-principles.md)</span><span class="sxs-lookup"><span data-stu-id="48aed-110">[Previous] (index.md) [Next] (common-container-design-principles.md)</span></span>
