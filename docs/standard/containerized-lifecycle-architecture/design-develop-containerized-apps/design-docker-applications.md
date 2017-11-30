---
title: Entwerfen von Docker-Anwendungen
description: Lebenszyklus von Datenvolumes Docker-Anwendung mit Microsoft-Webplattform und Tools
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: db8376abf95aab51fad23f4b351cb772351117ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="design-docker-applications"></a><span data-ttu-id="8fe7a-104">Entwerfen von Docker-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="8fe7a-104">Design Docker applications</span></span>

<span data-ttu-id="8fe7a-105">Die grundlegenden Konzepte in Bezug auf Container und Docker, Kapitel 1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="8fe7a-105">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="8fe7a-106">Diese Information ist die grundlegende Informationen, die Sie benötigen, um zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="8fe7a-106">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="8fe7a-107">Allerdings unternehmensanwendungen können komplex sein und mehrere Dienste anstelle von einem Einzelgerät oder Container besteht.</span><span class="sxs-lookup"><span data-stu-id="8fe7a-107">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="8fe7a-108">Für die Fälle optional verwenden müssen Sie zusätzliche Ansätze zum Entwerfen, z. B. dienstorientierte Architektur (SOA) und die erweiterte Microservices Konzepte und Container orchestrierungskonzepte kennen, können.</span><span class="sxs-lookup"><span data-stu-id="8fe7a-108">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="8fe7a-109">Der Rahmen dieses Dokuments ist nicht beschränkt auf Microservices jedoch auf alle Docker-Anwendungslebenszyklus, daher ist nicht untersuchen Microservices Architektur im Detail, da Sie auch können Container und Docker mit regulären SÃO, Hintergrundaufgaben oder Aufträge, oder sogar mit monolithisch Anwendung Bereitstellung Ansätze.</span><span class="sxs-lookup"><span data-stu-id="8fe7a-109">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SAO, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="8fe7a-110">Bevor wir in den Lebenszyklus der Anwendung und DevOps erhalten, ist es jedoch wichtig zu wissen, wie Sie Entwurf durchlaufen und erstellen Ihre Anwendung und was Ihre Entscheidungen zum Entwurf sind.</span><span class="sxs-lookup"><span data-stu-id="8fe7a-110">However, before we get into the application life cycle and DevOps, it is important to know how you are going to design and construct your application and what are your design choices.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="8fe7a-111">[Vorherigen] (index.md) [weiter] (Common-Container-Design-principles.md)</span><span class="sxs-lookup"><span data-stu-id="8fe7a-111">[Previous] (index.md) [Next] (common-container-design-principles.md)</span></span>
