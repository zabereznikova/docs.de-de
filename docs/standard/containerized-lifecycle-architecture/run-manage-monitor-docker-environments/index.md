---
title: Ausführen, Verwalten und Überwachen von Docker-Produktionsumgebungen
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 41c170b5e58d92c6e669de48c1f41caf5b2aa6e8
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="run-manage-and-monitor-docker-production-environments"></a><span data-ttu-id="fcefd-103">Ausführen, Verwalten und Überwachen von Docker-Produktionsumgebungen</span><span class="sxs-lookup"><span data-stu-id="fcefd-103">Run, manage, and monitor Docker production environments</span></span>

<span data-ttu-id="fcefd-104">Vision: Unternehmensanwendungen müssen hochverfügbar und hochgradig skalierbar sein, und die operative IT muss in der Lage sein, die Umgebungen und Anwendungen selbst zu verwalten und zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="fcefd-104">Vision: Enterprise applications need to run with high availability and high scalability; IT operations need to be able to manage and monitor the environments and the applications themselves.</span></span>

<span data-ttu-id="fcefd-105">Dieser letzte Eckpfeiler im Lebenszyklus der containerisierten Docker-Anwendungen ist darauf ausgerichtet, wie Sie Ihre Anwendungen in skalierbaren, hochverfügbaren Produktionsumgebungen (HA) betreiben, verwalten und überwachen können.</span><span class="sxs-lookup"><span data-stu-id="fcefd-105">This last pillar in the containerized Docker applications life cycle is centered on how you can run, manage, and monitor your applications in scalable, high availability (HA) production environments.</span></span>

<span data-ttu-id="fcefd-106">Wie Sie Ihre containerisierten Anwendungen in der Produktion ausführen (Infrastrukturarchitektur und Plattformtechnologien), besitzt ebenfalls einen großen Bezug zu und basiert vollständig auf den gewählten Architektur- und Entwicklungsplattformen, die wir in Kapitel 1 dieses E-Books untersucht haben.</span><span class="sxs-lookup"><span data-stu-id="fcefd-106">How you run your containerized applications in production (infrastructure architecture and platform technologies) is also very much related and completely founded on the chosen architecture and development platforms that we looked at in the Chapter 1 of this e-book.</span></span> <span data-ttu-id="fcefd-107">In diesem Kapitel werden spezifische Produkte und Technologien von Microsoft und anderen Anbietern untersucht, mit denen Sie hochgradig skalierbare, HA-verteilte Anwendungen effektiv ausführen können, und wie Sie diese aus IT-Perspektive verwalten und überwachen können.</span><span class="sxs-lookup"><span data-stu-id="fcefd-107">This chapter examines specific products and technologies from Microsoft and other vendors that you can use to effectively run highly scalable, HA distributed applications plus how you can manage and monitor them from the IT perspective.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="fcefd-108">[Vorheriger] (../docker-devops-workflow/docker-application-outer-loop-devops-workflow.md) [Nächster] (run-microservices-based-applications-in-production.md)</span><span class="sxs-lookup"><span data-stu-id="fcefd-108">[Previous] (../docker-devops-workflow/docker-application-outer-loop-devops-workflow.md) [Next] (run-microservices-based-applications-in-production.md)</span></span>
