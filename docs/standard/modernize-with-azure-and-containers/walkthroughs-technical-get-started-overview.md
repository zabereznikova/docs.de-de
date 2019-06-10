---
title: Exemplarische Vorgehensweisen und technische erste Schritte (Übersicht)
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Exemplarische Vorgehensweisen und technische erste Schritte (Übersicht)
ms.date: 04/28/2018
ms.openlocfilehash: 0b0dbae999e31150a55368d669f718eea0925d51
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758785"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="17f76-103">Exemplarische Vorgehensweisen und technische erste Schritte (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="17f76-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="17f76-104">Um die Größe der in diesem e-Book zu beschränken, wurden zusätzliche technische Dokumentation und die vollständigen exemplarischen Vorgehensweisen in einem GitHub-Repository verfügbar.</span><span class="sxs-lookup"><span data-stu-id="17f76-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="17f76-105">Die online Reihe von exemplarischen Vorgehensweisen, die in diesem Kapitel beschrieben werden behandelt, die für ein schrittweises Setup mehrere Umgebungen, die auf Windows-Containern und Bereitstellung in Azure basieren.</span><span class="sxs-lookup"><span data-stu-id="17f76-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="17f76-106">In den folgenden Abschnitten wird erläutert, was jeder exemplarischen Vorgehensweise ist über, ihre Ziele und den allgemeinen Vision und bietet ein Diagramm der Aufgaben, die beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="17f76-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="17f76-107">Sie können die exemplarischen Vorgehensweisen selbst abrufen, in der *eShopModernizing* apps GitHub-Repository-Wiki auf <https://github.com/dotnet-architecture/eShopModernizing/wiki>.</span><span class="sxs-lookup"><span data-stu-id="17f76-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at <https://github.com/dotnet-architecture/eShopModernizing/wiki>.</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="17f76-108">Liste der technischen exemplarischen Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="17f76-108">Technical walkthrough list</span></span>

<span data-ttu-id="17f76-109">Die folgenden Get-started exemplarischen Vorgehensweisen bieten konsistente und umfassende technische Anleitungen, die für die Beispiel-apps, die Sie können übertragen und verschieben mithilfe von Containern, und klicken Sie dann unter Verwendung von mehreren Bereitstellungsoptionen in Azure verschieben.</span><span class="sxs-lookup"><span data-stu-id="17f76-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="17f76-110">Jede der folgenden exemplarischen Vorgehensweisen verwendet die neue Beispiel eShopLegacy und eShopModernizing-apps, die auf GitHub zur Verfügung stehen <https://github.com/dotnet-architecture/eShopModernizing>.</span><span class="sxs-lookup"><span data-stu-id="17f76-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at <https://github.com/dotnet-architecture/eShopModernizing>.</span></span>

- <span data-ttu-id="17f76-111">**Überblick über die Shopping-legacy-apps (Baseline-apps zur Modernisierung von)**</span><span class="sxs-lookup"><span data-stu-id="17f76-111">**Tour of eShop legacy apps (baseline apps to modernize)**</span></span>

- <span data-ttu-id="17f76-112">**Packen Sie Ihre vorhandenen ASP.NET Web-apps (Web Forms und MVC) mit Windows-Containern in Container**</span><span class="sxs-lookup"><span data-stu-id="17f76-112">**Containerize your existing ASP.NET web apps (WebForms & MVC) with Windows Containers**</span></span>

- <span data-ttu-id="17f76-113">**Packen Sie Ihre vorhandenen WCF-Dienste (N-Tier-apps) mit Windows-Containern in Container**</span><span class="sxs-lookup"><span data-stu-id="17f76-113">**Containerize your existing WCF services (N-Tier apps) with Windows Containers**</span></span>

- <span data-ttu-id="17f76-114">**Bereitstellen Sie Ihrer Windows-Containern basierenden-app für Azure-VMs**</span><span class="sxs-lookup"><span data-stu-id="17f76-114">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="17f76-115">**Bereitstellen Sie die Windows-Containern basierende apps in Kubernetes in Azure Container Service**</span><span class="sxs-lookup"><span data-stu-id="17f76-115">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="17f76-116">Exemplarische Vorgehensweise 1: Überblick über die Shopping-legacy-apps</span><span class="sxs-lookup"><span data-stu-id="17f76-116">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="17f76-117">Technische Anleitung Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="17f76-117">Technical walkthrough availability</span></span>

<span data-ttu-id="17f76-118">Die vollständige technische Exemplarische Vorgehensweise ist im eShopModernizing GitHub Repo Wiki verfügbar:</span><span class="sxs-lookup"><span data-stu-id="17f76-118">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="17f76-119">Exemplarische Vorgehensweisen eShopModernizing-wiki</span><span class="sxs-lookup"><span data-stu-id="17f76-119">eShopModernizing wiki walkthroughs</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a><span data-ttu-id="17f76-120">Übersicht</span><span class="sxs-lookup"><span data-stu-id="17f76-120">Overview</span></span>

<span data-ttu-id="17f76-121">In dieser exemplarischen Vorgehensweise können Sie die ursprüngliche Implementierung von drei ältere Beispielanwendungen untersuchen.</span><span class="sxs-lookup"><span data-stu-id="17f76-121">In this walkthrough, you can explore the initial implementation of three sample legacy applications.</span></span> <span data-ttu-id="17f76-122">Die ersten zwei Beispiel-Web-apps eine monolithische Architektur verfügen und mithilfe der klassischen ASP.NET erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="17f76-122">The first two sample web apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="17f76-123">Eine Anwendung basiert auf ASP.NET 4.x MVC; die zweite Anwendung basiert auf ASP.NET 4.x-Web Forms.</span><span class="sxs-lookup"><span data-stu-id="17f76-123">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span>
<span data-ttu-id="17f76-124">Die dritte app ist eine 3-Tier-app, bestehend aus einer Windows Forms-Client-app und ein serverseitiges [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) Service.</span><span class="sxs-lookup"><span data-stu-id="17f76-124">The third app is a 3-Tier app composed by a client WinForms app and a server-side [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) service.</span></span>

<span data-ttu-id="17f76-125">Alle diese Anwendungen finden Sie unter den [eShopModernizing GitHub-Repository](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="17f76-125">All these applications are available at the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

### <a name="goals"></a><span data-ttu-id="17f76-126">Ziele</span><span class="sxs-lookup"><span data-stu-id="17f76-126">Goals</span></span>

<span data-ttu-id="17f76-127">Das Hauptziel der in dieser exemplarischen Vorgehensweise ist einfach, vertraut, dass mit diesen apps, und klicken Sie mit ihren Code und die Konfiguration zu.</span><span class="sxs-lookup"><span data-stu-id="17f76-127">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="17f76-128">Sie können die apps, damit sie generieren und verwenden ohne Verwendung von SQL-Datenbank, zu Testzwecken simulierte Daten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="17f76-128">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="17f76-129">Diese optionale Konfiguration basiert auf Abhängigkeitsinjektion, entkoppelt.</span><span class="sxs-lookup"><span data-stu-id="17f76-129">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario-1-aspnet-web-apps"></a><span data-ttu-id="17f76-130">Szenario 1: ASP.NET Web-apps</span><span class="sxs-lookup"><span data-stu-id="17f76-130">Scenario 1: ASP.NET Web apps</span></span>

<span data-ttu-id="17f76-131">Die folgende Abbildung zeigt das einfache Szenario die ursprünglichen älteren Webanwendungen in ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="17f76-131">The figure below shows the simple scenario of the original legacy ASP.NET web applications.</span></span>

![Einfache Architektur Szenario der ursprünglichen legacy ASP.NET-Webanwendungen](./media/image5-1.png)

<span data-ttu-id="17f76-133">Aus einer geschäftsperspektive für die Domäne bieten beide apps den gleichen Katalog Verwaltungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="17f76-133">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="17f76-134">Mitglieder des Teams Enterprise eShop werden mithilfe der app anzeigen und bearbeiten den Produktkatalog durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="17f76-134">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span>

<span data-ttu-id="17f76-135">Die folgende Abbildung zeigt die Screenshots der ersten app.</span><span class="sxs-lookup"><span data-stu-id="17f76-135">The next figure shows the initial app screenshots.</span></span>

![ASP.NET MVC und ASP.NET Web Forms-Anwendungen (vorhandenen und ältere Technologien)](./media/image5-2.png)

<span data-ttu-id="17f76-137">Abhängigkeiten ASP.NET 4.x oder früheren Versionen (entweder für MVC oder Web Forms) bedeutet, dass diese Anwendungen in .NET Core ausgeführt wird nicht, es sei denn, der Code vollständig neu geschrieben wird, mithilfe von ASP.NET Core MVC.</span><span class="sxs-lookup"><span data-stu-id="17f76-137">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won’t run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span>

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a><span data-ttu-id="17f76-138">Szenario 2: WCF-Dienst und WinForms-Client-app (3-Tier-app)</span><span class="sxs-lookup"><span data-stu-id="17f76-138">Scenario 2: WCF service and WinForms client app (3-Tier app)</span></span>

<span data-ttu-id="17f76-139">Die folgende Abbildung zeigt das einfache Szenario die ursprünglichen ältere 3-Tier-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="17f76-139">The figure below shows the simple scenario of the original 3-Tier legacy application.</span></span>

![Einfache Architektur Szenario der ursprünglichen legacy 3-Tier-app mit einem WCF-Dienst und einer WinForms-Client-app](./media/image5-1.5.png)

### <a name="benefits"></a><span data-ttu-id="17f76-141">Vorteile</span><span class="sxs-lookup"><span data-stu-id="17f76-141">Benefits</span></span>

<span data-ttu-id="17f76-142">Die Vorteile der in dieser exemplarischen Vorgehensweise sind einfach: Erhalten Sie nur mit dem Code und die ersten apps vertraut.</span><span class="sxs-lookup"><span data-stu-id="17f76-142">The benefits of this walkthrough are simple: Just get familiar with the code and initial apps.</span></span>

### <a name="next-steps"></a><span data-ttu-id="17f76-143">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="17f76-143">Next steps</span></span>

<span data-ttu-id="17f76-144">Erkunden Sie diese ausführlichere Inhalte im GitHub-Wiki:</span><span class="sxs-lookup"><span data-stu-id="17f76-144">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="17f76-145">Tour auf der Basislinie ASP.NET MVC und "legacy" Web Forms-apps</span><span class="sxs-lookup"><span data-stu-id="17f76-145">Tour on the baseline ASP.NET MVC and Web Forms “legacy” apps</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [<span data-ttu-id="17f76-146">Tour auf die Baseline-WCF-Dienst und WinForms (3-Ebenen) "legacy"-app</span><span class="sxs-lookup"><span data-stu-id="17f76-146">Tour on the baseline WCF service and WinForms (3-Tier) “legacy” app</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="17f76-147">Exemplarische Vorgehensweise 2: Packen Sie Ihre vorhandenen Anwendungen für .NET mit Windows-Containern in Container</span><span class="sxs-lookup"><span data-stu-id="17f76-147">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="overview"></a><span data-ttu-id="17f76-148">Übersicht</span><span class="sxs-lookup"><span data-stu-id="17f76-148">Overview</span></span>

<span data-ttu-id="17f76-149">Verwenden Sie Windows-Container, um die Bereitstellung von vorhandenen .NET-Anwendungen verwenden können, wie basierend auf MVC, Web Forms- oder WCF, zu der Produktion, Entwicklungs- und testumgebungen zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="17f76-149">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="17f76-150">Ziele</span><span class="sxs-lookup"><span data-stu-id="17f76-150">Goals</span></span>

<span data-ttu-id="17f76-151">Das Ziel dieser exemplarischen Vorgehensweise werden Sie mehrere Optionen für das containerisieren einer vorhandenen .NET Framework-Anwendung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="17f76-151">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="17f76-152">Sie haben folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="17f76-152">You can:</span></span>

- <span data-ttu-id="17f76-153">Packen Sie Ihre Anwendung in Container, mit [Visual Studio 2017-Tools für Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 oder höher).</span><span class="sxs-lookup"><span data-stu-id="17f76-153">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="17f76-154">Packen Sie Ihre Anwendung in Container, manuell hinzufügen eine [dockerfile-Datei](https://docs.docker.com/engine/reference/builder/), und klicken Sie dann mit der [Docker-CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span><span class="sxs-lookup"><span data-stu-id="17f76-154">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="17f76-155">Packen Sie Ihre Anwendung in Container, mit der [Img2Docker](https://github.com/docker/communitytools-image2docker-win) Tools an (ein Open-Source-Tool von Docker).</span><span class="sxs-lookup"><span data-stu-id="17f76-155">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="17f76-156">In dieser exemplarischen Vorgehensweise liegt der Schwerpunkt auf Visual Studio 2017-Tools für Docker-Ansatz, aber die anderen beiden Ansätze sind ziemlich ähnlich hinsichtlich der dockerfile-Dateien verwenden.</span><span class="sxs-lookup"><span data-stu-id="17f76-156">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario-1-containerized-aspnet-web-apps"></a><span data-ttu-id="17f76-157">Szenario 1: Containerbasierte ASP.NET Web-apps</span><span class="sxs-lookup"><span data-stu-id="17f76-157">Scenario 1: Containerized ASP.NET web apps</span></span>

<span data-ttu-id="17f76-158">Die folgende Abbildung zeigt das Szenario für Container eShop ältere apps Webanwendungen.</span><span class="sxs-lookup"><span data-stu-id="17f76-158">Figure below shows the scenario for containerized eShop legacy web apps applications.</span></span>

![Vereinfachte Architekturdiagramm von containeranwendungen auf ASP.NET in einer Entwicklungsumgebung](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a><span data-ttu-id="17f76-160">Szenario 2: WCF-containerdienst</span><span class="sxs-lookup"><span data-stu-id="17f76-160">Scenario 2: Containerized WCF service</span></span>

<span data-ttu-id="17f76-161">Die folgende Abbildung zeigt das Szenario für eine 3-Tier-app mit WCF-Dienst in einem Container.</span><span class="sxs-lookup"><span data-stu-id="17f76-161">Figure below shows the scenario for a 3-Tier app with a containerized WCF service.</span></span>

![Architekturdiagramm eines WCF-Dienst in einer Entwicklungsumgebung in Containern vereinfacht](./media/image5-3.5.png)

### <a name="benefits"></a><span data-ttu-id="17f76-163">Vorteile</span><span class="sxs-lookup"><span data-stu-id="17f76-163">Benefits</span></span>

<span data-ttu-id="17f76-164">Es gibt Vorteile zum Ausführen der monolithischen Anwendung in einem Container.</span><span class="sxs-lookup"><span data-stu-id="17f76-164">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="17f76-165">Erstellen Sie zunächst ein Image für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="17f76-165">First, you create an image for the application.</span></span> <span data-ttu-id="17f76-166">Ab diesem Punkt führt jede Bereitstellung in der gleichen Umgebung.</span><span class="sxs-lookup"><span data-stu-id="17f76-166">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="17f76-167">Alle Container verwendet die gleiche Version des Betriebssystems, hat die gleiche Version von Abhängigkeiten installiert, verwendet die gleiche Version von .NET Framework und wird unter Verwendung des gleichen Prozesses erstellt.</span><span class="sxs-lookup"><span data-stu-id="17f76-167">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="17f76-168">Im Grunde genommen, steuern Sie die Abhängigkeiten Ihrer Anwendung mithilfe eines Docker-Images.</span><span class="sxs-lookup"><span data-stu-id="17f76-168">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="17f76-169">Die Abhängigkeiten mit der Anwendung übertragen werden, wenn Sie die Container bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="17f76-169">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="17f76-170">Ein weiterer Vorteil ist, dass Entwickler die Anwendung in den konsistenten Umgebung ausführen können, die von Windows-Containern bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="17f76-170">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="17f76-171">Probleme, die nur in bestimmten Versionen angezeigt werden können sofort in einer Staging- oder produktionsumgebung Umgebung behebt, anstatt entdeckt werden.</span><span class="sxs-lookup"><span data-stu-id="17f76-171">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="17f76-172">Unterschiede in entwicklungsumgebungen verwendet, die von Mitgliedern des Entwicklungsteams sind weniger wichtig, wenn Anwendungen in Containern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="17f76-172">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="17f76-173">Containerbasierte Anwendungen müssen auch eine flachere horizontale skalierungskurve.</span><span class="sxs-lookup"><span data-stu-id="17f76-173">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="17f76-174">Container-apps können Sie mehrere Anwendungs- und Dienstinstanzen, die (auf der Grundlage der Container) verfügen, in einem virtuellen Computer oder physischen Computer, die im Vergleich zu regulären anwendungsbereitstellungen pro Computer.</span><span class="sxs-lookup"><span data-stu-id="17f76-174">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="17f76-175">Dies führt zu höhere Dichte und weniger erforderliche Ressourcen, insbesondere bei der Verwendung von orchestratoren wie Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="17f76-175">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes.</span></span>

<span data-ttu-id="17f76-176">Containerisierung, im Idealfall erfordert keine Änderungen an den Anwendungscode (C\#).</span><span class="sxs-lookup"><span data-stu-id="17f76-176">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="17f76-177">In den meisten Fällen benötigen Sie nur die Docker-Bereitstellung-Metadatendateien (dockerfile-Dateien und Docker Compose-Dateien).</span><span class="sxs-lookup"><span data-stu-id="17f76-177">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="17f76-178">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="17f76-178">Next steps</span></span>

<span data-ttu-id="17f76-179">Erkunden Sie diese ausführlichere Inhalte im GitHub-Wiki:</span><span class="sxs-lookup"><span data-stu-id="17f76-179">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="17f76-180">Packen Sie die .NET Framework-Web-apps mit Windows-Containern und Docker in Container</span><span class="sxs-lookup"><span data-stu-id="17f76-180">How to containerize the .NET Framework web apps with Windows Containers and Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [<span data-ttu-id="17f76-181">Hinzufügen von Docker-Unterstützung für einen WCF-Dienst</span><span class="sxs-lookup"><span data-stu-id="17f76-181">Adding Docker Support to a WCF service</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="17f76-182">Exemplarische Vorgehensweise 3: Bereitstellen Sie Ihrer Windows-Containern basierenden-app für Azure-VMs</span><span class="sxs-lookup"><span data-stu-id="17f76-182">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="17f76-183">Technische Anleitung Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="17f76-183">Technical walkthrough availability</span></span>

<span data-ttu-id="17f76-184">Die vollständige technische Exemplarische Vorgehensweise ist im eShopModernizing GitHub Repo Wiki verfügbar: <https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="17f76-184">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span></span>

### <a name="overview"></a><span data-ttu-id="17f76-185">Übersicht</span><span class="sxs-lookup"><span data-stu-id="17f76-185">Overview</span></span>

<span data-ttu-id="17f76-186">Bereitstellung in einem Docker-Host auf einem Windows Server 2016 Virtual Machine (VM) in Azure können Sie schnell Entwicklungs-/Test-/stagingphase Umgebungen einrichten.</span><span class="sxs-lookup"><span data-stu-id="17f76-186">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="17f76-187">Außerdem erhalten Sie einen allgemeinen Speicherort für Tester oder Benutzer in Unternehmen, um die app zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="17f76-187">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="17f76-188">Virtuelle Computer können auch gültige Infrastruktur als ein produktionsumgebungen Service (IaaS) sein.</span><span class="sxs-lookup"><span data-stu-id="17f76-188">VMs also can be valid Infrastructure as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="17f76-189">Ziele</span><span class="sxs-lookup"><span data-stu-id="17f76-189">Goals</span></span>

<span data-ttu-id="17f76-190">Das Ziel dieser exemplarischen Vorgehensweise ist die mehrere alternativen beschrieben, die Ihnen beim Bereitstellen von Windows-Container für Azure-VMs, die auf Windows Server 2016 oder höher basieren.</span><span class="sxs-lookup"><span data-stu-id="17f76-190">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="17f76-191">Szenarien</span><span class="sxs-lookup"><span data-stu-id="17f76-191">Scenarios</span></span>

<span data-ttu-id="17f76-192">In dieser exemplarischen Vorgehensweise werden verschiedene Szenarien behandelt.</span><span class="sxs-lookup"><span data-stu-id="17f76-192">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="17f76-193">Szenario A: Bereitstellen Sie in einer Azure-VM aus ein Entwickler-PC über Docker-Engine-Verbindung</span><span class="sxs-lookup"><span data-stu-id="17f76-193">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Bereitstellen Sie in einer Azure-VM aus ein Entwickler-PCs über eine Docker-Engine-Verbindung](./media/image5-4.png)

<span data-ttu-id="17f76-195">**Abbildung 5-4.**</span><span class="sxs-lookup"><span data-stu-id="17f76-195">**Figure 5-4.**</span></span> <span data-ttu-id="17f76-196">Bereitstellen Sie in einer Azure-VM aus ein Entwickler-PCs über eine Docker-Engine-Verbindung</span><span class="sxs-lookup"><span data-stu-id="17f76-196">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="17f76-197">Szenario B: Bereitstellen Sie in einer Azure-VM über eine Docker-Registrierung</span><span class="sxs-lookup"><span data-stu-id="17f76-197">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Bereitstellen Sie in einer Azure-VM über eine Docker-Registrierung](./media/image5-5.png)

<span data-ttu-id="17f76-199">**Abbildung 5-5.**</span><span class="sxs-lookup"><span data-stu-id="17f76-199">**Figure 5-5.**</span></span> <span data-ttu-id="17f76-200">Bereitstellen Sie in einer Azure-VM über eine Docker-Registrierung</span><span class="sxs-lookup"><span data-stu-id="17f76-200">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="17f76-201">Szenario "c:" Bereitstellen Sie in einer Azure-VM über CI/CD-Pipelines in Azure DevOps-Dienste</span><span class="sxs-lookup"><span data-stu-id="17f76-201">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

![Bereitstellen Sie in einer Azure-VM über CI/CD-Pipelines in Azure DevOps-Dienste](./media/image5-6.png)

<span data-ttu-id="17f76-203">**Abbildung 5-6.**</span><span class="sxs-lookup"><span data-stu-id="17f76-203">**Figure 5-6.**</span></span> <span data-ttu-id="17f76-204">Bereitstellen Sie in einer Azure-VM über CI/CD-Pipelines in Azure DevOps-Dienste</span><span class="sxs-lookup"><span data-stu-id="17f76-204">Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="17f76-205">Azure-VMs für Windows-Container</span><span class="sxs-lookup"><span data-stu-id="17f76-205">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="17f76-206">Azure-VMs für die Windows-Container werden VMs basierend auf Windows Server 2016, Windows 10 oder höher, mit der Docker-Engine einrichten.</span><span class="sxs-lookup"><span data-stu-id="17f76-206">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="17f76-207">In den meisten Fällen wird die Windows Server 2016 in die Azure-VMs verwendet.</span><span class="sxs-lookup"><span data-stu-id="17f76-207">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="17f76-208">Azure bietet derzeit einen virtuellen Computer namens **Windows Server 2016 mit Containern**.</span><span class="sxs-lookup"><span data-stu-id="17f76-208">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="17f76-209">Dieser virtuelle Computer können Sie um das neue Windows Server-Container-Feature, mit Windows Server Core oder Windows Nano Server zu testen.</span><span class="sxs-lookup"><span data-stu-id="17f76-209">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="17f76-210">Containerbetriebssystem-Images werden installiert, und klicken Sie dann die VM mit Docker verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="17f76-210">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="17f76-211">Vorteile</span><span class="sxs-lookup"><span data-stu-id="17f76-211">Benefits</span></span>

<span data-ttu-id="17f76-212">Obwohl Windows-Container bei der Bereitstellung in Azure zu lokalen Windows Server 2016-VMs bereitgestellt werden können, erhalten Sie eine einfachere Möglichkeit, sofort zu verwendende Windows Server-Container-VMs Einstieg.</span><span class="sxs-lookup"><span data-stu-id="17f76-212">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="17f76-213">Sie können auch eine allgemeine Onlinespeicherort, die für Tester und automatische Skalierbarkeit durch Azure VM Scale Sets-Instanzen zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="17f76-213">You also get a common online location that’s accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="17f76-214">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="17f76-214">Next steps</span></span>

<span data-ttu-id="17f76-215">Erkunden Sie diese ausführlichere Inhalte im GitHub-Wiki:</span><span class="sxs-lookup"><span data-stu-id="17f76-215">Explore this content more in-depth on the GitHub wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a><span data-ttu-id="17f76-216">Exemplarische Vorgehensweise 4: Bereitstellen Sie Ihrer Windows-Containern basierende apps in Azure Container Instances (ACI)</span><span class="sxs-lookup"><span data-stu-id="17f76-216">Walkthrough 4: Deploy your Windows Containers-based apps to Azure Container Instances (ACI)</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="17f76-217">Technische Anleitung Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="17f76-217">Technical walkthrough availability</span></span>

<span data-ttu-id="17f76-218">Die vollständige technische Exemplarische Vorgehensweise ist im eShopModernizing GitHub Repo Wiki verfügbar:</span><span class="sxs-lookup"><span data-stu-id="17f76-218">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="17f76-219">[Bereitstellen der Apps für ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span><span class="sxs-lookup"><span data-stu-id="17f76-219">[Deploying the Apps to ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span></span>

### <a name="overview"></a><span data-ttu-id="17f76-220">Übersicht</span><span class="sxs-lookup"><span data-stu-id="17f76-220">Overview</span></span>

<span data-ttu-id="17f76-221">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) ist die schnellste Möglichkeit, eine Container-Dev/Test/Staging-Umgebung verfügen, in dem Sie einzelne Instanzen von Containern bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="17f76-221">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) is the quickest way to have a Containers dev/test/staging environment where you can deploy single instances of containers.</span></span>

### <a name="goals"></a><span data-ttu-id="17f76-222">Ziele</span><span class="sxs-lookup"><span data-stu-id="17f76-222">Goals</span></span>

<span data-ttu-id="17f76-223">In dieser exemplarischen Vorgehensweise erfahren Sie die wichtigsten Szenarien, bei der Bereitstellung von Windows-Container für Azure Container Instances (ACI) und wie Sie in ACI eShopModernizing Apps bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="17f76-223">This walkthrough shows you the main scenarios when deploying Windows Containers to Azure Container Instances (ACI) and how you can deploy eShopModernizing Apps into ACI.</span></span>

### <a name="scenarios"></a><span data-ttu-id="17f76-224">Szenarien</span><span class="sxs-lookup"><span data-stu-id="17f76-224">Scenarios</span></span>

<span data-ttu-id="17f76-225">Unterschiede können zum Bereitstellen von apps eShopModernizing in ACI z. B. nur eine oder alle apps (MVC-app, WebForms-app oder WCF-Dienst) bereitstellen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="17f76-225">There can be variations about deploying the eShopModernizing apps into ACI such as deploying just one or all of the apps (MVC app, WebForms app or WCF service).</span></span> <span data-ttu-id="17f76-226">Im folgenden Szenario unten sehen Sie die ASP.NET MVC-app sowie SQL Server-Container, die beide bereitgestellt als Container in ACI (Azure Container Instances).</span><span class="sxs-lookup"><span data-stu-id="17f76-226">In the following scenario shown below you can see the ASP.NET MVC app plus the SQL Server container both of them deployed as containers into ACI (Azure Container Instances).</span></span>

![Bereitstellung für ACI aus einer Entwicklungsumgebung](./media/image5-3.5.6.png)

### <a name="benefits"></a><span data-ttu-id="17f76-228">Vorteile</span><span class="sxs-lookup"><span data-stu-id="17f76-228">Benefits</span></span>

<span data-ttu-id="17f76-229">Mit Azure Container Instances erleichtert das Erstellen und Verwalten von Docker-Containern in Azure, ohne dass virtuelle Computer bereitstellen oder einen übergeordneten Dienst einführen müssen.</span><span class="sxs-lookup"><span data-stu-id="17f76-229">Azure Container Instances makes it easy to create and manage Docker containers in Azure, without having to provision virtual machines or adopt a higher-level service.</span></span> <span data-ttu-id="17f76-230">Mit ACI können Sie direkt bereitstellen einen Windows-Container in Azure und machen es über einen vollständig qualifizierten Domänennamen (FQDN) im Internet in wenigen Sekunden (vorausgesetzt, dass Sie das Windows-Container-Image bereit in einer Docker-Registrierung, wie Docker Hub oder Azure Container verfügen Die Registrierung).</span><span class="sxs-lookup"><span data-stu-id="17f76-230">With ACI, you can directly deploy a Windows container in Azure and expose it to the internet with a fully qualified domain name (FQDN) in a matter of seconds (Provided that you have the Windows Container image ready in a Docker registry like Docker Hub or Azure Container Registry).</span></span>

### <a name="considerations"></a><span data-ttu-id="17f76-231">Weitere Überlegungen</span><span class="sxs-lookup"><span data-stu-id="17f76-231">Considerations</span></span>

<span data-ttu-id="17f76-232">Bereitstellen von Windows-Containern mit entweder vollständige .NET Framework / ASP.NET oder SQL Server in Azure Container Instances (ACI) ist nicht ganz so schnell wie die Bereitstellung auf eine reguläre Docker-Host (z. B. Windows Server 2016 mit Containern für Windows), da das Docker-Image muss herunterladen (Pull aus der Docker-Registrierung) jedes Mal, und die Größe der SQL-Container-Abbild (15.1 GB) und das containerimage für ASP.NET (13.9 GB) sind sehr groß ist, jedoch sehr viel kostengünstiger als die Beibehaltung von Ihren eigenen Docker-Host (dauerhaft Online ist WindowsServer 2016 mit Windows-Container-VM in Azure) nicht auf eine gesamte Orchestrator wie Kubernetes in Azure (AKS) zu erwähnen, die auf der anderen Seite eine hervorragende Wahl für Bereitstellungen in der Produktion ist.</span><span class="sxs-lookup"><span data-stu-id="17f76-232">Deploying Windows Containers with either full .NET Framework / ASP.NET or SQL Server into Azure Container Instances (ACI) is not quite as fast as deploying to a regular Docker Host (like a Windows Server 2016 with Windows Containers) because the Docker image has to be downloaded (pulled from the Docker registry) every time and the sizes of the SQL container image (15.1 GB) and the ASP.NET container image (13.9 GB) are significantly large, however it is much cheaper than maintaining your own docker host (permanently on-line Windows Server 2016 with Windows Containers VM in Azure) not to mention a whole orchestrator like Kubernetes in Azure (AKS) which is, on the other hand, a great choice for production deployments.</span></span>

<span data-ttu-id="17f76-233">Als wichtigsten Schlussfolgerung: ist mit Azure Container Instances eine sehr bestechende Option für Entwicklungs-/Testszenarios vorgesehen und für CI/CD-Pipelines aus.</span><span class="sxs-lookup"><span data-stu-id="17f76-233">As main conclusion, using Azure Container Instances is a very compelling option for Dev/Test scenarios and for CI/CD pipelines.</span></span>

## <a name="next-steps"></a><span data-ttu-id="17f76-234">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="17f76-234">Next steps</span></span>

<span data-ttu-id="17f76-235">Erkunden Sie diese ausführlichere Inhalte im GitHub-Wiki:</span><span class="sxs-lookup"><span data-stu-id="17f76-235">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)TBD)

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="17f76-236">Exemplarische Vorgehensweise 5: Bereitstellen Sie die Windows-Containern basierende apps in Kubernetes in Azure Container Service</span><span class="sxs-lookup"><span data-stu-id="17f76-236">Walkthrough 5: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="17f76-237">Technische Anleitung Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="17f76-237">Technical walkthrough availability</span></span>

<span data-ttu-id="17f76-238">Die vollständige technische Exemplarische Vorgehensweise ist im eShopModernizing GitHub Repo Wiki verfügbar:</span><span class="sxs-lookup"><span data-stu-id="17f76-238">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)>

### <a name="overview"></a><span data-ttu-id="17f76-239">Übersicht</span><span class="sxs-lookup"><span data-stu-id="17f76-239">Overview</span></span>

<span data-ttu-id="17f76-240">Eine Anwendung, die basierend auf Windows-Container müssen schnell Plattformen Umzug entfernt noch einen Schritt weiter von IaaS-VMs verwenden.</span><span class="sxs-lookup"><span data-stu-id="17f76-240">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="17f76-241">Dies ist erforderlich, um hohe Skalierbarkeit nur schwer erzielen besser automatisierte Skalierbarkeit und für eine erhebliche Verbesserung in automatisierten Bereitstellungen und der versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="17f76-241">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="17f76-242">Sie können diese Ziele erreichen, indem Sie mit der Orchestrator [Kubernetes](https://kubernetes.io/), in der verfügbaren [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span><span class="sxs-lookup"><span data-stu-id="17f76-242">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="17f76-243">Ziele</span><span class="sxs-lookup"><span data-stu-id="17f76-243">Goals</span></span>

<span data-ttu-id="17f76-244">Das Ziel dieser exemplarischen Vorgehensweise erfahren, wie zum Bereitstellen einer Windows-Container-basierte Anwendung in Kubernetes ist (so genannte *K8s*) in Azure Container Service.</span><span class="sxs-lookup"><span data-stu-id="17f76-244">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="17f76-245">Bereitstellen in Kubernetes von Grund auf neu ist ein zweistufiger Prozess:</span><span class="sxs-lookup"><span data-stu-id="17f76-245">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1. <span data-ttu-id="17f76-246">Bereitstellen eines Kubernetes-Clusters in Azure Container Service.</span><span class="sxs-lookup"><span data-stu-id="17f76-246">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2. <span data-ttu-id="17f76-247">Stellen Sie die Anwendung und die zugehörigen Ressourcen mit dem Kubernetes-Cluster bereit.</span><span class="sxs-lookup"><span data-stu-id="17f76-247">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="17f76-248">Szenarien</span><span class="sxs-lookup"><span data-stu-id="17f76-248">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="17f76-249">Szenario A: Direkt in einem Kubernetes-Cluster bereitgestellt wird, aus einer Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="17f76-249">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![Direkt in einem Kubernetes-Cluster bereitgestellt wird, aus einer Entwicklungsumgebung](./media/image5-7.png)

<span data-ttu-id="17f76-251">**Abbildung 5-7.**</span><span class="sxs-lookup"><span data-stu-id="17f76-251">**Figure 5-7.**</span></span> <span data-ttu-id="17f76-252">Direkt in einem Kubernetes-Cluster bereitgestellt wird, aus einer Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="17f76-252">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="17f76-253">Szenario B: Bereitstellen Sie in einem Kubernetes-Cluster über CI/CD-Pipelines in Azure DevOps-Dienste</span><span class="sxs-lookup"><span data-stu-id="17f76-253">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

![Bereitstellen Sie in einem Kubernetes-Cluster über CI/CD-Pipelines in Azure DevOps-Dienste](./media/image5-8.png)

<span data-ttu-id="17f76-255">**Abbildung 5-8.**</span><span class="sxs-lookup"><span data-stu-id="17f76-255">**Figure 5-8.**</span></span> <span data-ttu-id="17f76-256">Bereitstellen Sie in einem Kubernetes-Cluster über CI/CD-Pipelines in Azure DevOps-Dienste</span><span class="sxs-lookup"><span data-stu-id="17f76-256">Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="benefits"></a><span data-ttu-id="17f76-257">Vorteile</span><span class="sxs-lookup"><span data-stu-id="17f76-257">Benefits</span></span>

<span data-ttu-id="17f76-258">Es gibt viele Vorteile, die in einem Kubernetes-Cluster bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="17f76-258">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="17f76-259">Der größte Vorteil ist, dass Sie eine produktionsbereiten Umgebung erhalten, in der Sie die Anwendung basierend auf der Anzahl von containerinstanzen, die Sie (Inner-Skalierbarkeit in den vorhandenen Knoten) verwenden möchten, die und basierend auf der Anzahl von Knoten oder virtuellen Computern in den Cluster (horizontal skalieren können Globale Skalierbarkeit des Clusters).</span><span class="sxs-lookup"><span data-stu-id="17f76-259">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="17f76-260">Azure Container Service optimiert die beliebte Open-Source-Tools und Technologien, speziell für Azure.</span><span class="sxs-lookup"><span data-stu-id="17f76-260">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="17f76-261">Sie erhalten eine offene Lösung, die Portabilität für Ihre Container sowohl für die Anwendungskonfiguration bietet.</span><span class="sxs-lookup"><span data-stu-id="17f76-261">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="17f76-262">Wählen Sie die Größe, die Anzahl der Hosts, und der Orchestrator-Tools-Container Service übernimmt den Rest.</span><span class="sxs-lookup"><span data-stu-id="17f76-262">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="17f76-263">Mit Kubernetes können Entwickler Gedanken über physische und virtuelle Computer, Status, zum Planen einer Container ausgerichtete Infrastruktur, die die folgenden Funktionen, unter anderem ermöglicht:</span><span class="sxs-lookup"><span data-stu-id="17f76-263">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="17f76-264">Auf mehreren Containern basierenden Anwendungen</span><span class="sxs-lookup"><span data-stu-id="17f76-264">Applications based on multiple containers</span></span>

- <span data-ttu-id="17f76-265">Replizieren von Container Instances und automatische horizontale Skalierung</span><span class="sxs-lookup"><span data-stu-id="17f76-265">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="17f76-266">Benennen und zu ermitteln (z. B. interne DNS)</span><span class="sxs-lookup"><span data-stu-id="17f76-266">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="17f76-267">Lädt Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="17f76-267">Balancing loads</span></span>

- <span data-ttu-id="17f76-268">Parallele updates</span><span class="sxs-lookup"><span data-stu-id="17f76-268">Rolling updates</span></span>

- <span data-ttu-id="17f76-269">Verteilen von Geheimnissen</span><span class="sxs-lookup"><span data-stu-id="17f76-269">Distributing secrets</span></span>

- <span data-ttu-id="17f76-270">Integritätsprüfungen für Anwendung</span><span class="sxs-lookup"><span data-stu-id="17f76-270">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="17f76-271">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="17f76-271">Next steps</span></span>

<span data-ttu-id="17f76-272">Erkunden Sie diese ausführlichere Inhalte im GitHub-Wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)></span><span class="sxs-lookup"><span data-stu-id="17f76-272">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)></span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="17f76-273">[Zurück](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
> [Weiter](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="17f76-273">[Previous](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span>
