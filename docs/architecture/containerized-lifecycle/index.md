---
title: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
description: Hier erhalten Sie einen allgemeinen Überblick über den Entwicklungs- und Bereitstellungsprozess für containerisierte Anwendungen mit Docker- und Microsoft-Plattformen und -Tools.
ms.date: 07/30/2020
ms.openlocfilehash: c506a3423ac4511f23452192e361e88dce6efec4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91160696"
---
# <a name="containerized-docker-application-lifecycle-with-microsoft-platform-and-tools"></a><span data-ttu-id="92d4e-103">Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools</span><span class="sxs-lookup"><span data-stu-id="92d4e-103">Containerized Docker Application Lifecycle with Microsoft Platform and Tools</span></span>

![Bucheinband](./media/devops-book-cover-large-we.png)

<span data-ttu-id="92d4e-105">**EDITION v3.1** – für ASP.NET Core 3.1 aktualisiert</span><span class="sxs-lookup"><span data-stu-id="92d4e-105">**EDITION v3.1** - Updated to ASP.NET Core 3.1</span></span>

<span data-ttu-id="92d4e-106">Dieser Leitfaden bietet eine allgemeine Übersicht über die Entwicklung und Bereitstellung containerisierter ASP.NET Core-Anwendungen in Docker mithilfe der Microsoft-Plattform und -Tools.</span><span class="sxs-lookup"><span data-stu-id="92d4e-106">This guide is a general overview for developing and deploying containerized ASP.NET Core applications with Docker, using the Microsoft platform and tools.</span></span> <span data-ttu-id="92d4e-107">Zudem ist eine allgemeine Einführung in Azure DevOps für die Implementierung von CI/CD-Pipelines und in Azure Container Registry (ACR) und Azure Kubernetes Service (AKS) für die Bereitstellung enthalten.</span><span class="sxs-lookup"><span data-stu-id="92d4e-107">The guide includes a high-level introduction to Azure DevOps, for implementing CI/CD pipelines, as well as Azure Container Registry (ACR), and Azure Kubernetes Services AKS for deployment.</span></span>

<span data-ttu-id="92d4e-108">Ausführlichere entwicklungsbezogene Details finden Sie im Leitfaden [.NET-Microservices: Architektur für containerisierte .NET-Anwendungen](../microservices/index.md) und in der zugehörigen Referenzanwendung [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span><span class="sxs-lookup"><span data-stu-id="92d4e-108">For low-level, development-related details you can see the [.NET Microservices: Architecture for Containerized .NET Applications](../microservices/index.md) guide and it related reference application [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="92d4e-109">Senden Sie uns Ihr Feedback!</span><span class="sxs-lookup"><span data-stu-id="92d4e-109">Send us your feedback!</span></span>

<span data-ttu-id="92d4e-110">Dieser Leitfaden wurde geschrieben, um Ihnen die Architektur von Containeranwendungen und Microservices in .NET näherzubringen.</span><span class="sxs-lookup"><span data-stu-id="92d4e-110">We wrote this guide to help you understand the architecture of containerized applications and microservices in .NET.</span></span> <span data-ttu-id="92d4e-111">Der Leitfaden und die verknüpfte Verweisanwendung werden weiterentwickelt. Wir freuen uns über Ihr Feedback!</span><span class="sxs-lookup"><span data-stu-id="92d4e-111">The guide and related reference application will be evolving, so we welcome your feedback!</span></span> <span data-ttu-id="92d4e-112">Wenn Sie Kommentare dazu haben, wie dieser Leitfaden verbessert werden kann, senden Sie Ihr Feedback bitte an <https://aka.ms/ebookfeedback>.</span><span class="sxs-lookup"><span data-stu-id="92d4e-112">If you have comments about how this guide can be improved, submit feedback at <https://aka.ms/ebookfeedback>.</span></span>

## <a name="credits"></a><span data-ttu-id="92d4e-113">Mitwirkende</span><span class="sxs-lookup"><span data-stu-id="92d4e-113">Credits</span></span>

<span data-ttu-id="92d4e-114">Autor:</span><span class="sxs-lookup"><span data-stu-id="92d4e-114">Author:</span></span>

> <span data-ttu-id="92d4e-115">**Cesar de la Torre**, leitender PM, .NET-Produktteam, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="92d4e-115">**Cesar de la Torre**, Sr. PM, .NET product team, Microsoft Corp.</span></span>

<span data-ttu-id="92d4e-116">Autorenbetreuung:</span><span class="sxs-lookup"><span data-stu-id="92d4e-116">Acquisitions Editor:</span></span>

> <span data-ttu-id="92d4e-117">**Janine Patrick**</span><span class="sxs-lookup"><span data-stu-id="92d4e-117">**Janine Patrick**</span></span>

<span data-ttu-id="92d4e-118">Entwicklungslektor:</span><span class="sxs-lookup"><span data-stu-id="92d4e-118">Developmental Editor:</span></span>

> <span data-ttu-id="92d4e-119">**Bob Russell**, Solutions Professional bei Microsoft</span><span class="sxs-lookup"><span data-stu-id="92d4e-119">**Bob Russell**, Solutions Professional at Microsoft</span></span>
>
> [<span data-ttu-id="92d4e-120">**Octal Publishing, Inc.** </span><span class="sxs-lookup"><span data-stu-id="92d4e-120">**Octal Publishing, Inc.**</span></span>](http://www.octalpub.com/)

<span data-ttu-id="92d4e-121">Redaktionelle Produktion:</span><span class="sxs-lookup"><span data-stu-id="92d4e-121">Editorial Production:</span></span>

> [<span data-ttu-id="92d4e-122">Dianne Russell</span><span class="sxs-lookup"><span data-stu-id="92d4e-122">Dianne Russell</span></span>](http://www.octalpub.com/)
>
> <span data-ttu-id="92d4e-123">**Octal Publishing, Inc.**</span><span class="sxs-lookup"><span data-stu-id="92d4e-123">**Octal Publishing, Inc.**</span></span>

<span data-ttu-id="92d4e-124">Redakteur:</span><span class="sxs-lookup"><span data-stu-id="92d4e-124">Copyeditor:</span></span>

> <span data-ttu-id="92d4e-125">**Bob Russell**, Solutions Professional bei Microsoft</span><span class="sxs-lookup"><span data-stu-id="92d4e-125">**Bob Russell**, Solutions Professional at Microsoft</span></span>

<span data-ttu-id="92d4e-126">Teilnehmer und Prüfer:</span><span class="sxs-lookup"><span data-stu-id="92d4e-126">Participants and reviewers:</span></span>

> <span data-ttu-id="92d4e-127">**Nish Anil**, Senior Program Manager, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="92d4e-127">**Nish Anil**, Sr. Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="92d4e-128">**Miguel Veloso**, Software Development Engineer bei Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="92d4e-128">**Miguel Veloso**, Software Development Engineer at Plain Concepts</span></span>
>
> <span data-ttu-id="92d4e-129">**Sumit Ghosh**, Principal Consultant bei Neudesic</span><span class="sxs-lookup"><span data-stu-id="92d4e-129">**Sumit Ghosh**, Principal Consultant at Neudesic</span></span>

## <a name="copyright"></a><span data-ttu-id="92d4e-130">Copyright</span><span class="sxs-lookup"><span data-stu-id="92d4e-130">Copyright</span></span>

<span data-ttu-id="92d4e-131">VERÖFFENTLICHT VON</span><span class="sxs-lookup"><span data-stu-id="92d4e-131">PUBLISHED BY</span></span>

<span data-ttu-id="92d4e-132">Microsoft Developer Division, .NET- und Visual Studio-Produktteams</span><span class="sxs-lookup"><span data-stu-id="92d4e-132">Microsoft Developer Division, .NET and Visual Studio product teams</span></span>

<span data-ttu-id="92d4e-133">Eine Abteilung der Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="92d4e-133">A division of Microsoft Corporation</span></span>

<span data-ttu-id="92d4e-134">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="92d4e-134">One Microsoft Way</span></span>

<span data-ttu-id="92d4e-135">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="92d4e-135">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="92d4e-136">Copyright &copy; 2020 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="92d4e-136">Copyright &copy; 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="92d4e-137">Alle Rechte vorbehalten.</span><span class="sxs-lookup"><span data-stu-id="92d4e-137">All rights reserved.</span></span> <span data-ttu-id="92d4e-138">Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="92d4e-138">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="92d4e-139">Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus.</span><span class="sxs-lookup"><span data-stu-id="92d4e-139">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="92d4e-140">Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="92d4e-140">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="92d4e-141">Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv.</span><span class="sxs-lookup"><span data-stu-id="92d4e-141">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="92d4e-142">Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.</span><span class="sxs-lookup"><span data-stu-id="92d4e-142">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="92d4e-143">Microsoft und die auf der Webseite „Marken“ unter <https://www.microsoft.com> aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.</span><span class="sxs-lookup"><span data-stu-id="92d4e-143">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="92d4e-144">Mac und macOS sind Marken von Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="92d4e-144">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="92d4e-145">Das Logo des Docker-Wals ist eine registrierte Marke von Docker, Inc. Verwendet mit Genehmigung.</span><span class="sxs-lookup"><span data-stu-id="92d4e-145">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="92d4e-146">Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.</span><span class="sxs-lookup"><span data-stu-id="92d4e-146">All other marks and logos are property of their respective owners.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="92d4e-147">Nächste</span><span class="sxs-lookup"><span data-stu-id="92d4e-147">Next</span></span>](introduction-to-containers-and-docker.md)
