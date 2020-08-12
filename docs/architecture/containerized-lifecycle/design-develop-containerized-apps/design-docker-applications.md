---
title: Entwerfen von Docker-Anwendungen
description: Referenz zu einem tiefgreifenden Leitfaden zur Architektur von Microservices, da dieses Thema in diesem Leitfaden nicht ausführlich behandelt wird.
ms.date: 08/06/2020
ms.openlocfilehash: b63d4344abb358a393587bdacf91f6091b531af0
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915976"
---
# <a name="design-docker-applications"></a><span data-ttu-id="8ee8a-103">Entwerfen von Docker-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="8ee8a-103">Design Docker applications</span></span>

<span data-ttu-id="8ee8a-104">In Kapitel 1 wurden die grundlegenden Konzepte zu Containern und Docker vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="8ee8a-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="8ee8a-105">Diese Informationen bilden die erforderliche Basis für Ihren Einstieg.</span><span class="sxs-lookup"><span data-stu-id="8ee8a-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="8ee8a-106">Unternehmensanwendungen können allerdings komplex sein und bestehen oftmals aus mehreren Diensten statt aus einem einzelnen Dienst oder Container.</span><span class="sxs-lookup"><span data-stu-id="8ee8a-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="8ee8a-107">Für diese optionalen Anwendungsfälle müssen Sie weitere Entwurfsansätze, wie etwa die dienstorientierte Architektur (Service-Oriented Architecture, SOA) und die höher entwickelten Konzepte für Microservices und Containerorchestrierung kennen.</span><span class="sxs-lookup"><span data-stu-id="8ee8a-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="8ee8a-108">Der Umfang dieses Dokuments ist nicht auf Microservices beschränkt, sondern befasst sich mit dem Lebenszyklus beliebiger Docker-Anwendungen, daher wird die Microservicearchitektur nicht tiefgreifend behandelt, da Sie Container und Cocker auch in Kombination mit gewöhnlicher SOA, mit Hintergrundaufgaben oder Aufträgen oder sogar mit monolithischen Ansätzen zur Anwendungsbereitstellung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="8ee8a-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you can also use containers and Docker with regular SOA, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="8ee8a-109">**Weitere Informationen** Weitere, ausführliche Informationen zu Unternehmensanwendungen und Microservicearchitektur finden Sie in dem Leitfaden [.NET-Microservices:  .NET-Microservices-Architektur für .NET-Containeranwendungen](../../microservices/index.md) (NET-Microservices: Architektur für containerbasierte .NET-Anwendungen), den Sie auch von <https://aka.ms/MicroservicesEbook> herunterladen können.</span><span class="sxs-lookup"><span data-stu-id="8ee8a-109">**More info** To learn more about enterprise applications and microservices architecture in depth, read the guide [NET Microservices: Architecture for Containerized .NET Applications](../../microservices/index.md) that you can also download from <https://aka.ms/MicroservicesEbook>.</span></span>

<span data-ttu-id="8ee8a-110">Bevor Sie sich jedoch mit dem Anwendungslebenszyklus und DevOps befassen, müssen Sie wissen, wie Sie Ihre Anwendung entwerfen und erstellen möchten und welche Entwurfsoptionen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8ee8a-110">However, before you get into the application life cycle and DevOps, it's important to know how you're going to design and construct your application and what are your design choices.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="8ee8a-111">[Zurück](index.md)
>[Weiter](common-container-design-principles.md)</span><span class="sxs-lookup"><span data-stu-id="8ee8a-111">[Previous](index.md)
[Next](common-container-design-principles.md)</span></span>
