---
title: Exemplarische Vorgehensweisen und technische abrufen gestarteten (Übersicht)
description: Aktualisieren von vorhandenen .NET Anwendungen mit Azure-Cloud und Windows-Containern | Exemplarische Vorgehensweisen und technische abrufen gestarteten (Übersicht)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0bad7e3afbdf3e55c447319b3756f2235b9e0a19
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="416d9-103">Exemplarische Vorgehensweisen und technische abrufen gestarteten (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="416d9-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="416d9-104">Um die Größe dieser e-Book zu beschränken, wurden zusätzliche technische Dokumentation und die vollständige Exemplarische Vorgehensweisen in ein GitHub-Repository zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="416d9-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="416d9-105">Die online Reihe von exemplarischen Vorgehensweisen, die in diesem Kapitel beschriebenen behandelt schrittweise Setup von mehreren Umgebungen, die auf Windows-Containern und Bereitstellung in Azure basieren.</span><span class="sxs-lookup"><span data-stu-id="416d9-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="416d9-106">In den folgenden Abschnitten wird erläutert, was jeder exemplarischen Vorgehensweise wird erläutert, die Ziele und allgemeine Vision und enthält ein Diagramm der Aufgaben, die beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="416d9-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="416d9-107">Sie können die exemplarischen Vorgehensweisen selbst abrufen in der *eShopModernizing* apps GitHub-Repository Wiki am [ https://github.com/dotnet-architecture/eShopModernizing/wiki ](https://github.com/dotnet-architecture/eShopModernizing/wiki).</span><span class="sxs-lookup"><span data-stu-id="416d9-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at [https://github.com/dotnet-architecture/eShopModernizing/wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki).</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="416d9-108">Technische Anleitung-Liste</span><span class="sxs-lookup"><span data-stu-id="416d9-108">Technical walkthrough list</span></span>

<span data-ttu-id="416d9-109">Die folgenden abrufen gestarteten exemplarischen Vorgehensweisen bieten konsistent und umfassende technische Anleitung für die Beispiel-apps, die Sie heben und verschieben Sie mithilfe von Containern und klicken Sie dann mit der mehrere Bereitstellungsoptionen haben in Azure verschieben.</span><span class="sxs-lookup"><span data-stu-id="416d9-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="416d9-110">Jede der folgenden exemplarischen Vorgehensweisen verwendet die neue eShopLegacy und eShopModernizing beispielapps, die auf GitHub unter zur Verfügung stehen [ https://github.com/dotnet-architecture/eShopModernizing ](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="416d9-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at [https://github.com/dotnet-architecture/eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

- <span data-ttu-id="416d9-111">**Tour durch Shopping legacy-apps**</span><span class="sxs-lookup"><span data-stu-id="416d9-111">**Tour of eShop legacy apps**</span></span>

- <span data-ttu-id="416d9-112">**Containerize Ihre vorhandenen .NET Anwendungen mit Windows-Containern**</span><span class="sxs-lookup"><span data-stu-id="416d9-112">**Containerize your existing .NET applications with Windows Containers**</span></span>

- <span data-ttu-id="416d9-113">**Bereitstellen der Windows Container-basierten app in Azure-VMs**</span><span class="sxs-lookup"><span data-stu-id="416d9-113">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="416d9-114">**Bereitstellen Sie Windows-Container-basierte apps auf Kubernetes im Azure-Container-Dienst**</span><span class="sxs-lookup"><span data-stu-id="416d9-114">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

- <span data-ttu-id="416d9-115">**Bereitstellen von Windows-Container-basierten apps Azure Service Fabric**</span><span class="sxs-lookup"><span data-stu-id="416d9-115">**Deploy your Windows Containers-based apps to Azure Service Fabric**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="416d9-116">Exemplarische Vorgehensweise 1: Überblick Shopping legacy-apps</span><span class="sxs-lookup"><span data-stu-id="416d9-116">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="416d9-117">Technische Anleitung-Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="416d9-117">Technical walkthrough availability</span></span>

<span data-ttu-id="416d9-118">Die vollständige technische Exemplarische Vorgehensweise ist in der eShopModernizing GitHub-Repository-Wiki verfügbar:</span><span class="sxs-lookup"><span data-stu-id="416d9-118">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

### <a name="overview"></a><span data-ttu-id="416d9-119">Übersicht</span><span class="sxs-lookup"><span data-stu-id="416d9-119">Overview</span></span>

<span data-ttu-id="416d9-120">In dieser exemplarischen Vorgehensweise können Sie die ursprüngliche Implementierung von zwei Beispiel Legacyanwendungen untersuchen.</span><span class="sxs-lookup"><span data-stu-id="416d9-120">In this walkthrough, you can explore the initial implementation of two sample legacy applications.</span></span> <span data-ttu-id="416d9-121">Beide Beispiel-apps haben eine monolithische Architektur und mithilfe des klassischen ASP.NET erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="416d9-121">Both sample apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="416d9-122">Eine Anwendung basiert auf ASP.NET 4.x MVC; die zweite Anwendung basiert auf ASP.NET 4.x Web Forms.</span><span class="sxs-lookup"><span data-stu-id="416d9-122">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span> <span data-ttu-id="416d9-123">Beide Anwendungen sind der [eShopModernizing GitHub-Repository](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="416d9-123">Both applications are in the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

<span data-ttu-id="416d9-124">Sie können beide beispielapps containerize, ähnlich wie die können die Klassisches containerize [Windows Communication Foundation](../../framework/wcf/whats-wcf.md) (WCF)-Anwendung als eine desktop-Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="416d9-124">You can containerize both sample apps, similar to the way you can containerize a classic [Windows Communication Foundation](../../framework/wcf/whats-wcf.md) (WCF) application to be consumed as a desktop application.</span></span> <span data-ttu-id="416d9-125">Ein Beispiel finden Sie unter [eShopModernizingWCFWinForms](https://github.com/dotnet-architecture/eShopModernizingWCFWinForms).</span><span class="sxs-lookup"><span data-stu-id="416d9-125">For an example, see [eShopModernizingWCFWinForms](https://github.com/dotnet-architecture/eShopModernizingWCFWinForms).</span></span>

### <a name="goals"></a><span data-ttu-id="416d9-126">Ziele</span><span class="sxs-lookup"><span data-stu-id="416d9-126">Goals</span></span>

<span data-ttu-id="416d9-127">Das wichtigste Ziel dieser exemplarischen Vorgehensweise besteht darin, mit diesen apps und mit ihren Code und Konfiguration vertraut.</span><span class="sxs-lookup"><span data-stu-id="416d9-127">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="416d9-128">Sie können die apps konfigurieren, sodass sie generieren und Verwenden von simulierten Daten ohne Verwendung der SQL-Datenbank für Testzwecke verwenden.</span><span class="sxs-lookup"><span data-stu-id="416d9-128">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="416d9-129">Diese optionale Konfiguration basiert auf Abhängigkeitsinjektion, in einer entkoppelten Weise.</span><span class="sxs-lookup"><span data-stu-id="416d9-129">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario"></a><span data-ttu-id="416d9-130">Szenario</span><span class="sxs-lookup"><span data-stu-id="416d9-130">Scenario</span></span>

<span data-ttu-id="416d9-131">Abbildung 5 – 1 zeigt die einfachen Szenarios, die ursprüngliche Legacyanwendungen.</span><span class="sxs-lookup"><span data-stu-id="416d9-131">Figure 5-1 shows the simple scenario of the original legacy applications.</span></span>

> ![Einfache Architektur-Szenario für die ursprüngliche Legacyanwendungen](./media/image5-1.png)
>
> <span data-ttu-id="416d9-133">**Abbildung 5-1.**</span><span class="sxs-lookup"><span data-stu-id="416d9-133">**Figure 5-1.**</span></span> <span data-ttu-id="416d9-134">Einfache Architektur-Szenario für die ursprüngliche Legacyanwendungen</span><span class="sxs-lookup"><span data-stu-id="416d9-134">Simple architecture scenario of the original legacy applications</span></span>

<span data-ttu-id="416d9-135">Aus Sicht der Business-Domäne bieten beide apps den gleichen Katalog Verwaltungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="416d9-135">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="416d9-136">Mitglieder des Teams Enterprise Shopping würde die app anzeigen und Bearbeiten des Produktkatalogs verwenden.</span><span class="sxs-lookup"><span data-stu-id="416d9-136">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span> <span data-ttu-id="416d9-137">Abbildung 5 – 2 zeigt die anfänglichen app Screenshots.</span><span class="sxs-lookup"><span data-stu-id="416d9-137">Figure 5-2 shows the initial app screenshots.</span></span>

![ASP.NET MVC und ASP.NET Web Forms-Anwendungen (vorhandene/Legacy-Technologien)](./media/image5-2.png)

> <span data-ttu-id="416d9-139">**Abbildung 5-2.**</span><span class="sxs-lookup"><span data-stu-id="416d9-139">**Figure 5-2.**</span></span> <span data-ttu-id="416d9-140">ASP.NET MVC und ASP.NET Web Forms-Anwendungen (vorhandene/Legacy-Technologien)</span><span class="sxs-lookup"><span data-stu-id="416d9-140">ASP.NET MVC and ASP.NET Web Forms applications (existing/legacy technologies)</span></span>

<span data-ttu-id="416d9-141">Hierbei handelt es sich um Webanwendungen, die zum Suchen und Ändern von Katalogeinträge verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="416d9-141">These are web applications that are used to browse and modify catalog entries.</span></span> <span data-ttu-id="416d9-142">Die Tatsache, dass beide apps die gleichen Business/funktionale Funktionen bieten ist einfach für Vergleichszwecke.</span><span class="sxs-lookup"><span data-stu-id="416d9-142">The fact that both apps deliver the same business/functional features is simply for comparison purposes.</span></span> <span data-ttu-id="416d9-143">Sie können einem ähnlichen Modernisierung-Prozess für apps, die mithilfe von ASP.NET MVC und ASP.NET Web Forms-Frameworks erstellt wurden, finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="416d9-143">You can see a similar modernization process for apps that were created by using the ASP.NET MVC and ASP.NET Web Forms frameworks.</span></span>

<span data-ttu-id="416d9-144">Abhängigkeiten ASP.NET 4.x oder früheren Versionen (entweder für MVC oder Web Forms) bedeutet, dass diese Anwendungen keine auf .NET Core ausgeführt werden, wenn der Code vollständig neu geschrieben wird, mithilfe von ASP.NET Core MVC.</span><span class="sxs-lookup"><span data-stu-id="416d9-144">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won't run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span> <span data-ttu-id="416d9-145">Dies beweist dann, wenn Sie nicht möchten Umgestalten oder Schreiben Sie Code, können Sie vorhandene Anwendungen containerize und weiterhin die gleichen Technologien für .NET und denselben Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="416d9-145">This demonstrates the point that if you don't want to re-architect or rewrite code, you can containerize existing applications, and still use the same .NET technologies and the same code.</span></span> <span data-ttu-id="416d9-146">Sie können sehen, wie Sie Anwendungen, wie diese in Containern, ohne Änderungen für legacy-Code ausführen können.</span><span class="sxs-lookup"><span data-stu-id="416d9-146">You can see how you can run applications like these in containers, without any changes to legacy code.</span></span>

### <a name="benefits"></a><span data-ttu-id="416d9-147">Vorteile</span><span class="sxs-lookup"><span data-stu-id="416d9-147">Benefits</span></span>

<span data-ttu-id="416d9-148">Die Vorteile der in dieser exemplarischen Vorgehensweise sind einfach: nur den Code und Anwendungskonfiguration in, basierend auf Abhängigkeitsinjektion vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="416d9-148">The benefits of this walkthrough are simple: Just get familiar with the code and application configuration, based on dependency injection.</span></span> <span data-ttu-id="416d9-149">Anschließend können Sie bei diesem Ansatz experimentieren, beim containerize und in Zukunft in mehreren Umgebungen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="416d9-149">Then, you can experiment with this approach when you containerize and deploy to multiple environments in the future.</span></span>

### <a name="next-steps"></a><span data-ttu-id="416d9-150">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="416d9-150">Next steps</span></span>

<span data-ttu-id="416d9-151">Untersuchen Sie diese Inhalte ausführlicheren im GitHub-Wiki:</span><span class="sxs-lookup"><span data-stu-id="416d9-151">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="416d9-152">Exemplarische Vorgehensweise 2: Containerize, Ihre vorhandenen .NET Anwendungen mit Windows-Containern</span><span class="sxs-lookup"><span data-stu-id="416d9-152">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="416d9-153">Technische Anleitung-Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="416d9-153">Technical walkthrough availability</span></span>

<span data-ttu-id="416d9-154">Die vollständige technische Exemplarische Vorgehensweise ist in der eShopModernizing GitHub-Repository-Wiki verfügbar:</span><span class="sxs-lookup"><span data-stu-id="416d9-154">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)

### <a name="overview"></a><span data-ttu-id="416d9-155">Übersicht</span><span class="sxs-lookup"><span data-stu-id="416d9-155">Overview</span></span>

<span data-ttu-id="416d9-156">Mithilfe von Windows-Containern um Bereitstellung der vorhandenen .NET-Anwendungen, wie die Grundlage von MVC oder Web Forms, WCF, Produktions-, Entwicklungs- und testumgebungen zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="416d9-156">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="416d9-157">Ziele</span><span class="sxs-lookup"><span data-stu-id="416d9-157">Goals</span></span>

<span data-ttu-id="416d9-158">Das Ziel dieser exemplarischen Vorgehensweise werden Ihnen mehrere Optionen für eine vorhandene .NET Framework-Anwendung containerizing anzeigen.</span><span class="sxs-lookup"><span data-stu-id="416d9-158">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="416d9-159">Sie haben folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="416d9-159">You can:</span></span>

- <span data-ttu-id="416d9-160">Containerize Ihrer Anwendung mit [Visual Studio 2017-Tools für Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio-2017 oder höhere Versionen).</span><span class="sxs-lookup"><span data-stu-id="416d9-160">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="416d9-161">Containerize Ihrer Anwendung durch manuelles Hinzufügen von einer [dockerfile-Datei](https://docs.docker.com/engine/reference/builder/), und klicken Sie dann mit der [Docker-Befehlszeilenschnittstelle](https://docs.docker.com/engine/reference/commandline/cli/).</span><span class="sxs-lookup"><span data-stu-id="416d9-161">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="416d9-162">Containerize Ihrer Anwendung mithilfe der [Img2Docker](https://github.com/docker/communitytools-image2docker-win) -Tool (eine Open-Source-Tool von Docker).</span><span class="sxs-lookup"><span data-stu-id="416d9-162">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="416d9-163">In dieser exemplarischen Vorgehensweise konzentriert sich auf Visual Studio 2017-Tools für Docker Ansatz die anderen beiden Methoden sind allerdings hinsichtlich dockerfile-Dateien mit ähnlich.</span><span class="sxs-lookup"><span data-stu-id="416d9-163">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario"></a><span data-ttu-id="416d9-164">Szenario</span><span class="sxs-lookup"><span data-stu-id="416d9-164">Scenario</span></span>

<span data-ttu-id="416d9-165">Abbildung 5-3 wird das Szenario für Legacyanwendungen Datenvolumes Shopping.</span><span class="sxs-lookup"><span data-stu-id="416d9-165">Figure 5-3 shows the scenario for containerized eShop legacy applications.</span></span>

> ![Vereinfachte Sammelartikeleinheit in einer Entwicklungsumgebung-Architekturdiagramm](./media/image5-3.png)
>
> <span data-ttu-id="416d9-167">**Abbildung 5-3.**</span><span class="sxs-lookup"><span data-stu-id="416d9-167">**Figure 5-3.**</span></span> <span data-ttu-id="416d9-168">Vereinfachte Sammelartikeleinheit in einer Entwicklungsumgebung-Architekturdiagramm</span><span class="sxs-lookup"><span data-stu-id="416d9-168">Simplified architecture diagram of containerized applications in a development environment</span></span>

### <a name="benefits"></a><span data-ttu-id="416d9-169">Vorteile</span><span class="sxs-lookup"><span data-stu-id="416d9-169">Benefits</span></span>

<span data-ttu-id="416d9-170">Es sind Vorteile, die aufgrund eines monolithischen Anwendung in einem Container ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="416d9-170">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="416d9-171">Zunächst erstellen Sie ein Bild für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="416d9-171">First, you create an image for the application.</span></span> <span data-ttu-id="416d9-172">Ab diesem Zeitpunkt wird Sie jede Bereitstellung in der gleichen Umgebung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="416d9-172">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="416d9-173">Jeder Container verwendet die gleiche Version des Betriebssystems, die gleiche Version von Abhängigkeiten installiert wurde, verwendet die gleiche Version von .NET Framework und wird erstellt, indem Sie mit der gleichen.</span><span class="sxs-lookup"><span data-stu-id="416d9-173">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="416d9-174">Grundsätzlich können Sie die Abhängigkeiten der Anwendung mithilfe eines Images von Docker steuern.</span><span class="sxs-lookup"><span data-stu-id="416d9-174">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="416d9-175">Die Abhängigkeiten Reisen mit der Anwendung während der Bereitstellung auf den Container.</span><span class="sxs-lookup"><span data-stu-id="416d9-175">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="416d9-176">Ein zusätzlicher Vorteil besteht darin, dass Entwickler die Anwendung in die konsistente Umgebung ausführen können, die von Windows-Container bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="416d9-176">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="416d9-177">Probleme, die nur mit bestimmten Versionen angezeigt werden können sofort entdeckt werden, statt in einer Staging- oder Produktionsserver Umgebung einbringen.</span><span class="sxs-lookup"><span data-stu-id="416d9-177">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="416d9-178">Unterschiede in entwicklungsumgebungen verwendet, die von Mitgliedern des Entwicklungsteams unerheblich kleiner, wenn Anwendungen in Containern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="416d9-178">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="416d9-179">Sammelartikeleinheit haben auch eine flachere mit horizontaler Skalierung Kurve.</span><span class="sxs-lookup"><span data-stu-id="416d9-179">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="416d9-180">Datenvolumes apps können Sie weitere Anwendung und Dienstinstanzen (basierend auf den Container) verfügen, in einem virtuellen Computer oder physischen Computer im Vergleich zu normalen anwendungsbereitstellungen pro Computer.</span><span class="sxs-lookup"><span data-stu-id="416d9-180">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="416d9-181">Dies bedeutet höhere Dichte und weniger erforderlichen Ressourcen, insbesondere wenn Sie Orchestrators wie Kubernetes oder Service Fabric verwenden.</span><span class="sxs-lookup"><span data-stu-id="416d9-181">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes or Service Fabric.</span></span>

<span data-ttu-id="416d9-182">Containerization, im Idealfall, erfordert keine Änderungen am Anwendungscode (C\#).</span><span class="sxs-lookup"><span data-stu-id="416d9-182">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="416d9-183">In den meisten Fällen benötigen Sie nur die Docker-Bereitstellung-Metadatendateien (dockerfile-Dateien und Docker Compose-Dateien).</span><span class="sxs-lookup"><span data-stu-id="416d9-183">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="416d9-184">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="416d9-184">Next steps</span></span>

<span data-ttu-id="416d9-185">Untersuchen Sie diese Inhalte ausführlicheren im GitHub-Wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)</span><span class="sxs-lookup"><span data-stu-id="416d9-185">Explore this content more in-depth on the GitHub wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)</span></span>

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="416d9-186">Exemplarische Vorgehensweise 3: Bereitstellen der Windows-Container-basierten Anwendung auf Azure VMs</span><span class="sxs-lookup"><span data-stu-id="416d9-186">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="416d9-187">Technische Anleitung-Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="416d9-187">Technical walkthrough availability</span></span>

<span data-ttu-id="416d9-188">Die vollständige technische Exemplarische Vorgehensweise ist in der eShopModernizing GitHub-Repository-Wiki verfügbar:</span><span class="sxs-lookup"><span data-stu-id="416d9-188">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

### <a name="overview"></a><span data-ttu-id="416d9-189">Übersicht</span><span class="sxs-lookup"><span data-stu-id="416d9-189">Overview</span></span>

<span data-ttu-id="416d9-190">Auf einem Docker-Host auf einem Windows Server 2016 virtuellen Computer (VM) in Azure bereitstellen, können Sie die Entwicklung/Test/Stagingumgebungen schnell einzurichten.</span><span class="sxs-lookup"><span data-stu-id="416d9-190">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="416d9-191">Darüber hinaus haben Sie einen allgemeinen Platz für Tester oder Geschäftsbenutzer, um die app zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="416d9-191">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="416d9-192">Virtuelle Computer können auch gültige Infrastruktur als eine produktionsumgebungen Service (IaaS) sein.</span><span class="sxs-lookup"><span data-stu-id="416d9-192">VMs also can be valid Infrastucture as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="416d9-193">Ziele</span><span class="sxs-lookup"><span data-stu-id="416d9-193">Goals</span></span>

<span data-ttu-id="416d9-194">Das Ziel dieser exemplarischen Vorgehensweise werden Sie mehrere Alternativen an, die Ihnen beim Bereitstellen von Windows-Container für Azure-VMs, die auf Windows Server 2016 oder höher basieren.</span><span class="sxs-lookup"><span data-stu-id="416d9-194">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="416d9-195">Szenarien</span><span class="sxs-lookup"><span data-stu-id="416d9-195">Scenarios</span></span>

<span data-ttu-id="416d9-196">In dieser exemplarischen Vorgehensweise werden mehrere Szenarien behandelt.</span><span class="sxs-lookup"><span data-stu-id="416d9-196">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="416d9-197">Szenario A: Bereitstellen in einer Azure-VM aus einer Dev PC über Docker-Modul-Verbindung</span><span class="sxs-lookup"><span data-stu-id="416d9-197">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Über eine Dev PC über eine Verbindung Docker-Modul in einer Azure-VM bereitstellen](./media/image5-4.png)

> <span data-ttu-id="416d9-199">**Abbildung 5-4.**</span><span class="sxs-lookup"><span data-stu-id="416d9-199">**Figure 5-4.**</span></span> <span data-ttu-id="416d9-200">Über eine Dev PC über eine Verbindung Docker-Modul in einer Azure-VM bereitstellen</span><span class="sxs-lookup"><span data-stu-id="416d9-200">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="416d9-201">Szenario B: Bereitstellen Sie in einer Azure-VM über einen Docker-Registrierung</span><span class="sxs-lookup"><span data-stu-id="416d9-201">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Bereitstellen Sie in einer Azure-VM über einen Docker-Registrierung](./media/image5-5.png)

> <span data-ttu-id="416d9-203">**Abbildung 5-5.**</span><span class="sxs-lookup"><span data-stu-id="416d9-203">**Figure 5-5.**</span></span> <span data-ttu-id="416d9-204">Bereitstellen Sie in einer Azure-VM über einen Docker-Registrierung</span><span class="sxs-lookup"><span data-stu-id="416d9-204">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-visual-studio-team-services"></a><span data-ttu-id="416d9-205">Szenario "c:" in einer Azure-VM bereitstellen, von CI-CD-Pipelines in Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="416d9-205">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Visual Studio Team Services</span></span>

![Bereitstellen Sie in einer Azure-VM von CI-CD-Pipelines in Visual Studio Team Services](./media/image5-6.png)

> <span data-ttu-id="416d9-207">**Abbildung 5-6.**</span><span class="sxs-lookup"><span data-stu-id="416d9-207">**Figure 5-6.**</span></span> <span data-ttu-id="416d9-208">Bereitstellen Sie in einer Azure-VM von CI-CD-Pipelines in Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="416d9-208">Deploy to an Azure VM from CI/CD pipelines in Visual Studio Team Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="416d9-209">Azure-VMs für Windows-Container</span><span class="sxs-lookup"><span data-stu-id="416d9-209">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="416d9-210">Azure-VMs für Windows-Container sind virtuelle Computer basierend auf Windows Server 2016, Windows 10 oder höher, sowohl mit Docker-Modul einrichten.</span><span class="sxs-lookup"><span data-stu-id="416d9-210">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="416d9-211">In den meisten Fällen wird die Windows Server 2016 in den Azure-VMs verwendet.</span><span class="sxs-lookup"><span data-stu-id="416d9-211">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="416d9-212">Azure bietet zurzeit einen virtuellen Computer mit dem Namen **Windows Server 2016 mit Containern**.</span><span class="sxs-lookup"><span data-stu-id="416d9-212">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="416d9-213">Dieser virtuelle Computer können Sie das neue Windows Server-Container-Feature, mit Windows Server Core oder Windows Nano Server versuchen.</span><span class="sxs-lookup"><span data-stu-id="416d9-213">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="416d9-214">Containerbetriebssystem-Images werden installiert, und klicken Sie dann der virtuellen Computer ist einsatzbereit mit Docker.</span><span class="sxs-lookup"><span data-stu-id="416d9-214">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="416d9-215">Vorteile</span><span class="sxs-lookup"><span data-stu-id="416d9-215">Benefits</span></span>

<span data-ttu-id="416d9-216">Obwohl Windows-Container bei der Bereitstellung in Azure zu einer lokalen Windows Server 2016-VMs bereitgestellt werden kann, erhalten Sie eine einfachere Möglichkeit, sofort zu verwendende Windows Server-Container-VMs Einstieg.</span><span class="sxs-lookup"><span data-stu-id="416d9-216">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="416d9-217">Sie erhalten auch einen allgemeinen online Speicherort, der den Testern und automatische Skalierung über Azure VM-skalierungsgruppen zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="416d9-217">You also get a common online location that’s accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="416d9-218">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="416d9-218">Next steps</span></span>

<span data-ttu-id="416d9-219">Untersuchen Sie diese Inhalte ausführlicheren im GitHub-Wiki:</span><span class="sxs-lookup"><span data-stu-id="416d9-219">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="416d9-220">Exemplarische Vorgehensweise 4: Bereitstellen der Windows-Container-basierte apps für Kubernetes im Azure-Container-Dienst</span><span class="sxs-lookup"><span data-stu-id="416d9-220">Walkthrough 4: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="416d9-221">Technische Anleitung-Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="416d9-221">Technical walkthrough availability</span></span>

<span data-ttu-id="416d9-222">Die vollständige technische Exemplarische Vorgehensweise ist in der eShopModernizing GitHub-Repository-Wiki verfügbar:</span><span class="sxs-lookup"><span data-stu-id="416d9-222">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

### <a name="overview"></a><span data-ttu-id="416d9-223">Übersicht</span><span class="sxs-lookup"><span data-stu-id="416d9-223">Overview</span></span>

<span data-ttu-id="416d9-224">Eine Anwendung, die basierend auf Windows-Containern müssen schnell verschieben unterwegs noch weiter von IaaS-VMs-Plattformen verwenden.</span><span class="sxs-lookup"><span data-stu-id="416d9-224">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="416d9-225">Dies ist erforderlich, um problemlos hohe Skalierbarkeit zu erzielen eine bessere Leistung automatisierte Skalierbarkeit und für eine deutliche leistungsverbesserung automatische Bereitstellungen und versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="416d9-225">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="416d9-226">Sie können diese Ziele erreichen, indem Sie mit der Orchestrator [Kubernetes](https://kubernetes.io/), verfügbar im [Dienste der Azure-Container](https://azure.microsoft.com/services/container-service/).</span><span class="sxs-lookup"><span data-stu-id="416d9-226">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="416d9-227">Ziele</span><span class="sxs-lookup"><span data-stu-id="416d9-227">Goals</span></span>

<span data-ttu-id="416d9-228">Das Ziel dieser exemplarischen Vorgehensweise erfahren, wie in einer Windows-Container-basierte Anwendung Kubernetes bereitstellen ist (so genannte *K8s*) im Azure-Container-Dienst.</span><span class="sxs-lookup"><span data-stu-id="416d9-228">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="416d9-229">Bereitstellen für Kubernetes von Grund auf neu ist ein zweistufiger Prozess:</span><span class="sxs-lookup"><span data-stu-id="416d9-229">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1.  <span data-ttu-id="416d9-230">Bereitstellen eines Clusters Kubernetes Azure-Container-Dienst an.</span><span class="sxs-lookup"><span data-stu-id="416d9-230">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2.  <span data-ttu-id="416d9-231">Stellen Sie die Anwendung und die zugehörigen Ressourcen für den Cluster Kubernetes bereit.</span><span class="sxs-lookup"><span data-stu-id="416d9-231">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="416d9-232">Szenarien</span><span class="sxs-lookup"><span data-stu-id="416d9-232">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="416d9-233">Szenario A: Bereitstellen direkt zu einem Cluster Kubernetes aus einer Developer-Umgebung</span><span class="sxs-lookup"><span data-stu-id="416d9-233">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![Direkt auf einem Cluster Kubernetes aus einer Entwicklungsumgebung bereitstellen](./media/image5-7.png)

> <span data-ttu-id="416d9-235">**Abbildung 5-7.**</span><span class="sxs-lookup"><span data-stu-id="416d9-235">**Figure 5-7.**</span></span> <span data-ttu-id="416d9-236">Direkt auf einem Cluster Kubernetes aus einer Entwicklungsumgebung bereitstellen</span><span class="sxs-lookup"><span data-stu-id="416d9-236">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-team-services"></a><span data-ttu-id="416d9-237">Szenario B: zu einem Cluster Kubernetes bereitstellen, von CI-CD pipelines im Team Services</span><span class="sxs-lookup"><span data-stu-id="416d9-237">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Team Services</span></span>

![Bereitstellen Sie für einen Cluster Kubernetes CI-CD-Pipelines in Team Services](./media/image5-8.png)

> <span data-ttu-id="416d9-239">**Abbildung 5-8.**</span><span class="sxs-lookup"><span data-stu-id="416d9-239">**Figure 5-8.**</span></span> <span data-ttu-id="416d9-240">Bereitstellen Sie für einen Cluster Kubernetes CI-CD-Pipelines in Team Services</span><span class="sxs-lookup"><span data-stu-id="416d9-240">Deploy to a Kubernetes cluster from CI/CD pipelines in Team Services</span></span>

### <a name="benefits"></a><span data-ttu-id="416d9-241">Vorteile</span><span class="sxs-lookup"><span data-stu-id="416d9-241">Benefits</span></span>

<span data-ttu-id="416d9-242">Es gibt viele Vorteile für eine Bereitstellung auf einem Cluster in Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="416d9-242">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="416d9-243">Der größte Vorteil ist, dass Sie eine produktionsbereite Umgebung erhalten, in der Sie die Anwendung basierend auf der Anzahl der containerinstanzen, die Sie skalieren können (Inner-Skalierbarkeit in den vorhandenen Knoten) verwenden möchten, die und basierend auf der Anzahl von Knoten oder virtuellen Computern in den Cluster ( Globale Skalierbarkeit des Clusters).</span><span class="sxs-lookup"><span data-stu-id="416d9-243">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="416d9-244">Azure Containerdienst wird die beliebte Open Source-Tools und Technologien speziell für Azure optimiert.</span><span class="sxs-lookup"><span data-stu-id="416d9-244">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="416d9-245">Sie erhalten eine geöffnete Projektmappe, die Portabilität, die sowohl für die Container als auch für Ihre Anwendungskonfiguration bietet.</span><span class="sxs-lookup"><span data-stu-id="416d9-245">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="416d9-246">Wählen Sie die Größe der Anzahl der Hosts, und der Orchestrator-Tools-Container-Dienst verarbeitet alle anderen.</span><span class="sxs-lookup"><span data-stu-id="416d9-246">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="416d9-247">Mit Kubernetes können Entwickler Gedanken über physische und virtuelle Computer, Status, für die Planung einer Container anwendungsorientierte-Infrastruktur, die die folgenden Funktionen, u. a. erleichtert:</span><span class="sxs-lookup"><span data-stu-id="416d9-247">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="416d9-248">Anwendungen, die basierend auf mehrere Container</span><span class="sxs-lookup"><span data-stu-id="416d9-248">Applications based on multiple containers</span></span>

- <span data-ttu-id="416d9-249">Replizieren von containerinstanzen und automatische horizontale Skalierung</span><span class="sxs-lookup"><span data-stu-id="416d9-249">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="416d9-250">Benennen und ermitteln (z. B. internes DNS)</span><span class="sxs-lookup"><span data-stu-id="416d9-250">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="416d9-251">Lastenausgleich Lasten</span><span class="sxs-lookup"><span data-stu-id="416d9-251">Balancing loads</span></span>

- <span data-ttu-id="416d9-252">Parallele updates</span><span class="sxs-lookup"><span data-stu-id="416d9-252">Rolling updates</span></span>

- <span data-ttu-id="416d9-253">Verteilen von geheimen Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="416d9-253">Distributing secrets</span></span>

- <span data-ttu-id="416d9-254">Integritätsprüfungen für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="416d9-254">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="416d9-255">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="416d9-255">Next steps</span></span>

<span data-ttu-id="416d9-256">Untersuchen Sie diese Inhalte ausführlicheren im GitHub-Wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span><span class="sxs-lookup"><span data-stu-id="416d9-256">Explore this content more in-depth on the GitHub wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span></span>

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a><span data-ttu-id="416d9-257">Exemplarische Vorgehensweise 5: Bereitstellen von Windows-Container-basierte apps Azure Service Fabric</span><span class="sxs-lookup"><span data-stu-id="416d9-257">Walkthrough 5: Deploy your Windows Containers-based apps to Azure Service Fabric</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="416d9-258">Technische Anleitung-Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="416d9-258">Technical walkthrough availability</span></span>

<span data-ttu-id="416d9-259">Die vollständige technische Exemplarische Vorgehensweise ist in der eShopModernizing GitHub-Repository-Wiki verfügbar:</span><span class="sxs-lookup"><span data-stu-id="416d9-259">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

### <a name="overview"></a><span data-ttu-id="416d9-260">Übersicht</span><span class="sxs-lookup"><span data-stu-id="416d9-260">Overview</span></span>

<span data-ttu-id="416d9-261">Eine Anwendung, die basierend auf Windows-Containern schnell muss verschieben unterwegs noch weiter von IaaS-VMs-Plattformen verwenden.</span><span class="sxs-lookup"><span data-stu-id="416d9-261">An application based on Windows Containers quickly needs to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="416d9-262">Dies ist erforderlich, um problemlos hohe Skalierbarkeit zu erzielen eine bessere Leistung automatisierte Skalierbarkeit und für eine deutliche leistungsverbesserung automatische Bereitstellungen und versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="416d9-262">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="416d9-263">Sie können diese Ziele erreichen, mit dem Orchestrator Azure Service Fabric, das in der Azure-Cloud verfügbar, aber auch zur Verwendung von lokalen verfügbar ist, oder sogar in einer anderen öffentlichen Cloud.</span><span class="sxs-lookup"><span data-stu-id="416d9-263">You can achieve these goals by using the orchestrator Azure Service Fabric, which is available in the Azure cloud, but also available to use on-premises, or even in a different public cloud.</span></span>

### <a name="goals"></a><span data-ttu-id="416d9-264">Ziele</span><span class="sxs-lookup"><span data-stu-id="416d9-264">Goals</span></span>

<span data-ttu-id="416d9-265">Das Ziel dieser exemplarischen Vorgehensweise ist, wie Sie eine Windows-Container-basierte Anwendung zu einem Service Fabric-Cluster in Azure bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="416d9-265">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to a Service Fabric cluster in Azure.</span></span> <span data-ttu-id="416d9-266">Bereitstellen von Service Fabric von Grund auf neu ist ein zweistufiger Prozess:</span><span class="sxs-lookup"><span data-stu-id="416d9-266">Deploying to Service Fabric from scratch is a two-step process:</span></span>

1.  <span data-ttu-id="416d9-267">Bereitstellen von Service Fabric-Cluster in Azure (oder auf eine andere Umgebung).</span><span class="sxs-lookup"><span data-stu-id="416d9-267">Deploy a Service Fabric cluster to Azure (or to a different environment).</span></span>

2.  <span data-ttu-id="416d9-268">Stellen Sie die Anwendung und die zugehörigen Ressourcen für Service Fabric-Cluster bereit.</span><span class="sxs-lookup"><span data-stu-id="416d9-268">Deploy the application and related resources to the Service Fabric cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="416d9-269">Szenarien</span><span class="sxs-lookup"><span data-stu-id="416d9-269">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a><span data-ttu-id="416d9-270">Szenario A: Bereitstellen direkt zu einem Service Fabric-Cluster aus einer Developer-Umgebung</span><span class="sxs-lookup"><span data-stu-id="416d9-270">Scenario A: Deploy directly to a Service Fabric cluster from a dev environment</span></span>

![Direkt auf einem Service Fabric-Cluster aus einer Entwicklungsumgebung bereitstellen](./media/image5-9.png)

> <span data-ttu-id="416d9-272">**Abbildung 5-9.**</span><span class="sxs-lookup"><span data-stu-id="416d9-272">**Figure 5-9.**</span></span> <span data-ttu-id="416d9-273">Direkt auf einem Service Fabric-Cluster aus einer Entwicklungsumgebung bereitstellen</span><span class="sxs-lookup"><span data-stu-id="416d9-273">Deploy directly to a Service Fabric cluster from a development environment</span></span>

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-team-services"></a><span data-ttu-id="416d9-274">Szenario B: zu einem Service Fabric-Cluster bereitstellen, von CI-CD pipelines im Team Services</span><span class="sxs-lookup"><span data-stu-id="416d9-274">Scenario B: Deploy to a Service Fabric cluster from CI/CD pipelines in Team Services</span></span>

![Bereitstellen Sie für Service Fabric-Cluster CI-CD-Pipelines in Visual Studio Team Services](./media/image5-10.png)

> <span data-ttu-id="416d9-276">**Abbildung 5-10.**</span><span class="sxs-lookup"><span data-stu-id="416d9-276">**Figure 5-10.**</span></span> <span data-ttu-id="416d9-277">Bereitstellen Sie für Service Fabric-Cluster CI-CD-Pipelines in Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="416d9-277">Deploy to a Service Fabric cluster from CI/CD pipelines in Visual Studio Team Services</span></span>

## <a name="benefits"></a><span data-ttu-id="416d9-278">Vorteile</span><span class="sxs-lookup"><span data-stu-id="416d9-278">Benefits</span></span>

<span data-ttu-id="416d9-279">Die Vorteile der Bereitstellung auf einem Service Fabric-Cluster sind die Vorteile der Verwendung von Kubernetes ähnlich.</span><span class="sxs-lookup"><span data-stu-id="416d9-279">The benefits of deploying to a cluster in Service Fabric are similar to the benefits of using Kubernetes.</span></span> <span data-ttu-id="416d9-280">Ein Unterschied ist, dass Service Fabric ist eine ausgereiftere produktionsumgebung für Windows-Anwendungen im Vergleich zu Kubernetes, also in einer Betaphase für Windows-Containern in Kubernetes Version 1.9 (Dezember 2017).</span><span class="sxs-lookup"><span data-stu-id="416d9-280">One difference, though, is that Service Fabric is a more mature production environment for Windows applications compared to Kubernetes, which is in a beta phase for Windows Containers in Kubernetes version 1.9 (December 2017).</span></span> <span data-ttu-id="416d9-281">Kubernetes ist eine ausgereiftere für Linux.</span><span class="sxs-lookup"><span data-stu-id="416d9-281">Kubernetes is a more mature environment for Linux.</span></span>

<span data-ttu-id="416d9-282">Der wichtigste Vorteil der Verwendung von Azure Service Fabric ist, dass Sie eine produktionsbereite Umgebung erhalten, in der Sie die Anwendung basierend auf der Anzahl der containerinstanzen, die Sie skalieren können (Inner-Skalierbarkeit in den vorhandenen Knoten) verwenden möchten, die und basierend auf der Anzahl der Knoten oder virtuellen Computern im Cluster (globale Skalierbarkeit des Clusters).</span><span class="sxs-lookup"><span data-stu-id="416d9-282">The main benefit of using Azure Service Fabric is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="416d9-283">Azure Service Fabric bietet Portabilität sowohl für die Container als auch für die Anwendungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="416d9-283">Azure Service Fabric offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="416d9-284">Sie können einen Service Fabric-cluster in Azure oder lokal in Ihrem eigenen Datacenter installieren.</span><span class="sxs-lookup"><span data-stu-id="416d9-284">You can have a Service Fabric cluster in Azure, or install it on-premises in your own datacenter.</span></span> <span data-ttu-id="416d9-285">Sie können Service Fabric-Cluster in einer anderen Cloud geht auch wie installieren [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).</span><span class="sxs-lookup"><span data-stu-id="416d9-285">You can even install a Service Fabric cluster in a different cloud, like [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).</span></span>

<span data-ttu-id="416d9-286">Mit Service Fabric können Entwickler Gedanken über physische und virtuelle Computer ausgeführt, für die Planung einer Container anwendungsorientierte-Infrastruktur, die die folgenden Funktionen, u. a. erleichtert:</span><span class="sxs-lookup"><span data-stu-id="416d9-286">With Service Fabric, developers can progress from thinking about physical and virtual machines to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="416d9-287">Anwendungen, die basierend auf mehrere Container.</span><span class="sxs-lookup"><span data-stu-id="416d9-287">Applications based on multiple containers.</span></span>

- <span data-ttu-id="416d9-288">Das Replizieren von containerinstanzen und automatische horizontale Skalierung.</span><span class="sxs-lookup"><span data-stu-id="416d9-288">Replicating container instances and horizontal autoscaling.</span></span>

- <span data-ttu-id="416d9-289">Benennen und ermitteln (z. B. internes DNS).</span><span class="sxs-lookup"><span data-stu-id="416d9-289">Naming and discovering (for example, internal DNS).</span></span>

- <span data-ttu-id="416d9-290">Lastenausgleich lädt.</span><span class="sxs-lookup"><span data-stu-id="416d9-290">Balancing loads.</span></span>

- <span data-ttu-id="416d9-291">Parallele Updates an.</span><span class="sxs-lookup"><span data-stu-id="416d9-291">Rolling updates.</span></span>

- <span data-ttu-id="416d9-292">Verteilen von geheimen Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="416d9-292">Distributing secrets.</span></span>

- <span data-ttu-id="416d9-293">Anwendungsintegrität überprüft.</span><span class="sxs-lookup"><span data-stu-id="416d9-293">Application health checks.</span></span>

<span data-ttu-id="416d9-294">Die folgenden Funktionen sind exklusiv in Service Fabric (verglichen mit anderen Orchestrators):</span><span class="sxs-lookup"><span data-stu-id="416d9-294">The following capabilities are exclusive in Service Fabric (compared to other orchestrators):</span></span>

- <span data-ttu-id="416d9-295">Zustandsbehaftete Dienste-Funktion, über das Anwendungsmodell zuverlässige Dienste.</span><span class="sxs-lookup"><span data-stu-id="416d9-295">Stateful services capability, through the Reliable Services application model.</span></span>

- <span data-ttu-id="416d9-296">Akteure-Muster, über das Anwendungsmodell für Reliable Actors.</span><span class="sxs-lookup"><span data-stu-id="416d9-296">Actors pattern, through the Reliable Actors application model.</span></span>

- <span data-ttu-id="416d9-297">Bereitstellen von bare Bone Prozesse, zusätzlich zu den Windows- oder Linux-Container.</span><span class="sxs-lookup"><span data-stu-id="416d9-297">Deploy bare-bone processes, in addition to Windows or Linux containers.</span></span>

- <span data-ttu-id="416d9-298">Erweiterte parallelen Updates und Systemdiagnosen.</span><span class="sxs-lookup"><span data-stu-id="416d9-298">Advanced rolling updates and health checks.</span></span>

### <a name="next-steps"></a><span data-ttu-id="416d9-299">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="416d9-299">Next steps</span></span>

<span data-ttu-id="416d9-300">Untersuchen Sie diese Inhalte ausführlicheren im GitHub-Wiki:</span><span class="sxs-lookup"><span data-stu-id="416d9-300">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

>[!div class="step-by-step"]
<span data-ttu-id="416d9-301">[Zurück](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Weiter](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="416d9-301">[Previous](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span>
