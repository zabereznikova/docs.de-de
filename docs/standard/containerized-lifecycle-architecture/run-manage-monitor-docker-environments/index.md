---
title: Ausführen, Verwalten und Überwachen von Docker-Produktionsumgebungen
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 9c24a87fd691723b8f91077288478d26e5123265
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219125"
---
# <a name="run-manage-and-monitor-docker-production-environments"></a><span data-ttu-id="3c2fa-103">Ausführen, Verwalten und Überwachen von Docker-Produktionsumgebungen</span><span class="sxs-lookup"><span data-stu-id="3c2fa-103">Run, manage, and monitor Docker production environments</span></span>

<span data-ttu-id="3c2fa-104">Vision: In Unternehmen eingesetzten Anwendungen müssen mit hoher Verfügbarkeit und hoher Skalierbarkeit ausführen, Operative IT muss in der Lage, verwalten und überwachen die Umgebungen und die Anwendungen selbst.</span><span class="sxs-lookup"><span data-stu-id="3c2fa-104">Vision: Enterprise applications need to run with high availability and high scalability; IT operations need to be able to manage and monitor the environments and the applications themselves.</span></span>

<span data-ttu-id="3c2fa-105">Dieser letzte Eckpfeiler im Lebenszyklus der containerisierten Docker-Anwendungen ist darauf ausgerichtet, wie Sie Ihre Anwendungen in skalierbaren, hochverfügbaren Produktionsumgebungen (HA) betreiben, verwalten und überwachen können.</span><span class="sxs-lookup"><span data-stu-id="3c2fa-105">This last pillar in the containerized Docker applications life cycle is centered on how you can run, manage, and monitor your applications in scalable, high availability (HA) production environments.</span></span>

<span data-ttu-id="3c2fa-106">Wie Sie Ihre containerisierten Anwendungen in der Produktion ausführen (Infrastrukturarchitektur und Plattformtechnologien), besitzt ebenfalls einen großen Bezug zu und basiert vollständig auf den gewählten Architektur- und Entwicklungsplattformen, die wir in Kapitel 1 dieses E-Books untersucht haben.</span><span class="sxs-lookup"><span data-stu-id="3c2fa-106">How you run your containerized applications in production (infrastructure architecture and platform technologies) is also very much related and completely founded on the chosen architecture and development platforms that we looked at in the Chapter 1 of this e-book.</span></span> <span data-ttu-id="3c2fa-107">In diesem Kapitel werden spezifische Produkte und Technologien von Microsoft und anderen Anbietern untersucht, mit denen Sie hochgradig skalierbare, HA-verteilte Anwendungen effektiv ausführen können, und wie Sie diese aus IT-Perspektive verwalten und überwachen können.</span><span class="sxs-lookup"><span data-stu-id="3c2fa-107">This chapter examines specific products and technologies from Microsoft and other vendors that you can use to effectively run highly scalable, HA distributed applications plus how you can manage and monitor them from the IT perspective.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3c2fa-108">[Zurück](../docker-devops-workflow/create-ci-cd-pipelines-azure-devops-services-aspnetcore-kubernetes.md)
>[Weiter](run-microservices-based-applications-in-production.md)</span><span class="sxs-lookup"><span data-stu-id="3c2fa-108">[Previous](../docker-devops-workflow/create-ci-cd-pipelines-azure-devops-services-aspnetcore-kubernetes.md)
[Next](run-microservices-based-applications-in-production.md)</span></span>