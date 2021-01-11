---
title: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
description: Hier erhalten Sie einen allgemeinen Überblick über den Entwicklungs- und Bereitstellungsprozess für containerisierte Anwendungen mit Docker- und Microsoft-Plattformen und -Tools.
ms.date: 01/06/2021
ms.openlocfilehash: 94c277e349bacee9b9fc7b160043005dd4135958
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970114"
---
# <a name="containerized-docker-application-lifecycle-with-microsoft-platform-and-tools"></a><span data-ttu-id="dc434-103">Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools</span><span class="sxs-lookup"><span data-stu-id="dc434-103">Containerized Docker Application Lifecycle with Microsoft Platform and Tools</span></span>

![Bucheinband](./media/devops-book-cover-large-we.png)

<span data-ttu-id="dc434-105">**EDITION v5.0:** auf ASP.NET Core 5.0 aktualisiert</span><span class="sxs-lookup"><span data-stu-id="dc434-105">**EDITION v5.0** - Updated to ASP.NET Core 5.0</span></span>

<span data-ttu-id="dc434-106">Informationen zu den Buchaktualisierungen und Communitybeiträgen finden Sie im [Änderungsprotokoll](https://aka.ms/DockerLifecycleEbookChangelog).</span><span class="sxs-lookup"><span data-stu-id="dc434-106">Refer [changelog](https://aka.ms/DockerLifecycleEbookChangelog) for the book updates and community contributions.</span></span>

<span data-ttu-id="dc434-107">Dieser Leitfaden bietet eine allgemeine Übersicht über die Entwicklung und Bereitstellung containerisierter ASP.NET Core-Anwendungen in Docker mithilfe der Microsoft-Plattform und -Tools.</span><span class="sxs-lookup"><span data-stu-id="dc434-107">This guide is a general overview for developing and deploying containerized ASP.NET Core applications with Docker, using the Microsoft platform and tools.</span></span> <span data-ttu-id="dc434-108">Zudem ist eine allgemeine Einführung in Azure DevOps für die Implementierung von CI/CD-Pipelines und in Azure Container Registry (ACR) und Azure Kubernetes Service (AKS) für die Bereitstellung enthalten.</span><span class="sxs-lookup"><span data-stu-id="dc434-108">The guide includes a high-level introduction to Azure DevOps, for implementing CI/CD pipelines, as well as Azure Container Registry (ACR), and Azure Kubernetes Services AKS for deployment.</span></span>

<span data-ttu-id="dc434-109">Ausführlichere entwicklungsbezogene Details finden Sie im Leitfaden [.NET-Microservices: Architektur für containerisierte .NET-Anwendungen](../microservices/index.md) und in der zugehörigen Referenzanwendung [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span><span class="sxs-lookup"><span data-stu-id="dc434-109">For low-level, development-related details you can see the [.NET Microservices: Architecture for Containerized .NET Applications](../microservices/index.md) guide and it related reference application [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="dc434-110">Senden Sie uns Ihr Feedback!</span><span class="sxs-lookup"><span data-stu-id="dc434-110">Send us your feedback!</span></span>

<span data-ttu-id="dc434-111">Dieser Leitfaden wurde geschrieben, um Ihnen die Architektur von Containeranwendungen und Microservices in .NET näherzubringen.</span><span class="sxs-lookup"><span data-stu-id="dc434-111">We wrote this guide to help you understand the architecture of containerized applications and microservices in .NET.</span></span> <span data-ttu-id="dc434-112">Der Leitfaden und die verknüpfte Verweisanwendung werden weiterentwickelt. Wir freuen uns über Ihr Feedback!</span><span class="sxs-lookup"><span data-stu-id="dc434-112">The guide and related reference application will be evolving, so we welcome your feedback!</span></span> <span data-ttu-id="dc434-113">Wenn Sie Kommentare dazu haben, wie dieser Leitfaden verbessert werden kann, senden Sie Ihr Feedback bitte an <https://aka.ms/ebookfeedback>.</span><span class="sxs-lookup"><span data-stu-id="dc434-113">If you have comments about how this guide can be improved, submit feedback at <https://aka.ms/ebookfeedback>.</span></span>

## <a name="credits"></a><span data-ttu-id="dc434-114">Mitwirkende</span><span class="sxs-lookup"><span data-stu-id="dc434-114">Credits</span></span>

<span data-ttu-id="dc434-115">Autor:</span><span class="sxs-lookup"><span data-stu-id="dc434-115">Author:</span></span>

> <span data-ttu-id="dc434-116">**Cesar de la Torre**, leitender PM, .NET-Produktteam, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="dc434-116">**Cesar de la Torre**, Sr. PM, .NET product team, Microsoft Corp.</span></span>

<span data-ttu-id="dc434-117">Autorenbetreuung:</span><span class="sxs-lookup"><span data-stu-id="dc434-117">Acquisitions Editor:</span></span>

> <span data-ttu-id="dc434-118">**Janine Patrick**</span><span class="sxs-lookup"><span data-stu-id="dc434-118">**Janine Patrick**</span></span>

<span data-ttu-id="dc434-119">Entwicklungslektor:</span><span class="sxs-lookup"><span data-stu-id="dc434-119">Developmental Editor:</span></span>

> <span data-ttu-id="dc434-120">**Bob Russell**, Solutions Professional bei Microsoft</span><span class="sxs-lookup"><span data-stu-id="dc434-120">**Bob Russell**, Solutions Professional at Microsoft</span></span>
>
> [<span data-ttu-id="dc434-121">**Octal Publishing, Inc.**</span><span class="sxs-lookup"><span data-stu-id="dc434-121">**Octal Publishing, Inc.**</span></span>](http://www.octalpub.com/)

<span data-ttu-id="dc434-122">Redaktionelle Produktion:</span><span class="sxs-lookup"><span data-stu-id="dc434-122">Editorial Production:</span></span>

> [<span data-ttu-id="dc434-123">Dianne Russell</span><span class="sxs-lookup"><span data-stu-id="dc434-123">Dianne Russell</span></span>](http://www.octalpub.com/)
>
> <span data-ttu-id="dc434-124">**Octal Publishing, Inc.**</span><span class="sxs-lookup"><span data-stu-id="dc434-124">**Octal Publishing, Inc.**</span></span>

<span data-ttu-id="dc434-125">Redakteur:</span><span class="sxs-lookup"><span data-stu-id="dc434-125">Copyeditor:</span></span>

> <span data-ttu-id="dc434-126">**Bob Russell**, Solutions Professional bei Microsoft</span><span class="sxs-lookup"><span data-stu-id="dc434-126">**Bob Russell**, Solutions Professional at Microsoft</span></span>

<span data-ttu-id="dc434-127">Teilnehmer und Prüfer:</span><span class="sxs-lookup"><span data-stu-id="dc434-127">Participants and reviewers:</span></span>

> <span data-ttu-id="dc434-128">**Nish Anil**, Senior Program Manager, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="dc434-128">**Nish Anil**, Sr. Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="dc434-129">**Miguel Veloso**, Software Development Engineer bei Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="dc434-129">**Miguel Veloso**, Software Development Engineer at Plain Concepts</span></span>
>
> <span data-ttu-id="dc434-130">**Sumit Ghosh**, Principal Consultant bei Neudesic</span><span class="sxs-lookup"><span data-stu-id="dc434-130">**Sumit Ghosh**, Principal Consultant at Neudesic</span></span>

## <a name="copyright"></a><span data-ttu-id="dc434-131">Copyright</span><span class="sxs-lookup"><span data-stu-id="dc434-131">Copyright</span></span>

<span data-ttu-id="dc434-132">VERÖFFENTLICHT VON</span><span class="sxs-lookup"><span data-stu-id="dc434-132">PUBLISHED BY</span></span>

<span data-ttu-id="dc434-133">Microsoft Developer Division, .NET- und Visual Studio-Produktteams</span><span class="sxs-lookup"><span data-stu-id="dc434-133">Microsoft Developer Division, .NET and Visual Studio product teams</span></span>

<span data-ttu-id="dc434-134">Eine Abteilung der Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="dc434-134">A division of Microsoft Corporation</span></span>

<span data-ttu-id="dc434-135">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="dc434-135">One Microsoft Way</span></span>

<span data-ttu-id="dc434-136">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="dc434-136">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="dc434-137">Copyright &copy; 2021 by Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="dc434-137">Copyright &copy; 2021 by Microsoft Corporation</span></span>

<span data-ttu-id="dc434-138">Alle Rechte vorbehalten.</span><span class="sxs-lookup"><span data-stu-id="dc434-138">All rights reserved.</span></span> <span data-ttu-id="dc434-139">Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="dc434-139">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="dc434-140">Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus.</span><span class="sxs-lookup"><span data-stu-id="dc434-140">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="dc434-141">Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="dc434-141">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="dc434-142">Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv.</span><span class="sxs-lookup"><span data-stu-id="dc434-142">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="dc434-143">Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.</span><span class="sxs-lookup"><span data-stu-id="dc434-143">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="dc434-144">Microsoft und die auf der Webseite „Marken“ unter <https://www.microsoft.com> aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.</span><span class="sxs-lookup"><span data-stu-id="dc434-144">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="dc434-145">Mac und macOS sind Marken von Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="dc434-145">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="dc434-146">Das Logo des Docker-Wals ist eine registrierte Marke von Docker, Inc. Verwendet mit Genehmigung.</span><span class="sxs-lookup"><span data-stu-id="dc434-146">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="dc434-147">Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.</span><span class="sxs-lookup"><span data-stu-id="dc434-147">All other marks and logos are property of their respective owners.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="dc434-148">Nächste</span><span class="sxs-lookup"><span data-stu-id="dc434-148">Next</span></span>](introduction-to-containers-and-docker.md)
