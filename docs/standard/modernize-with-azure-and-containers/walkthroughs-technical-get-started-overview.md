---
title: Exemplarische Vorgehensweisen und technische abrufen gestarteten (Übersicht)
description: Aktualisieren von vorhandenen .NET Anwendungen mit Azure-Cloud und Windows-Containern | Exemplarische Vorgehensweisen und technische abrufen gestarteten (Übersicht)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 27de9d1c5475855a22f2d8a3518982605277f6d9
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="f5e56-103">Exemplarische Vorgehensweisen und technische abrufen gestarteten (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="f5e56-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="f5e56-104">Um die Größe dieser e-Book zu beschränken, wurden zusätzliche technische Dokumentation und die vollständige Exemplarische Vorgehensweisen in ein GitHub-Repository zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f5e56-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="f5e56-105">Die online Reihe von exemplarischen Vorgehensweisen, die in diesem Kapitel beschriebenen behandelt schrittweise Setup von mehreren Umgebungen, die auf Windows-Containern und Bereitstellung in Azure basieren.</span><span class="sxs-lookup"><span data-stu-id="f5e56-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="f5e56-106">In den folgenden Abschnitten wird erläutert, was jeder exemplarischen Vorgehensweise wird erläutert, die Ziele und allgemeine Vision und enthält ein Diagramm der Aufgaben, die beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="f5e56-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="f5e56-107">Sie können die exemplarischen Vorgehensweisen selbst abrufen in der *eShopModernizing* apps GitHub-Repository Wiki am [ https://github.com/dotnet-architecture/eShopModernizing/wiki ](https://github.com/dotnet-architecture/eShopModernizing/wiki).</span><span class="sxs-lookup"><span data-stu-id="f5e56-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at [https://github.com/dotnet-architecture/eShopModernizing/wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki).</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="f5e56-108">Technische Anleitung-Liste</span><span class="sxs-lookup"><span data-stu-id="f5e56-108">Technical walkthrough list</span></span>

<span data-ttu-id="f5e56-109">Die folgenden abrufen gestarteten exemplarischen Vorgehensweisen bieten konsistent und umfassende technische Anleitung für die Beispiel-apps, die Sie heben und verschieben Sie mithilfe von Containern und klicken Sie dann mit der mehrere Bereitstellungsoptionen haben in Azure verschieben.</span><span class="sxs-lookup"><span data-stu-id="f5e56-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="f5e56-110">Jede der folgenden exemplarischen Vorgehensweisen verwendet die neue eShopLegacy und eShopModernizing beispielapps, die auf GitHub unter zur Verfügung stehen [ https://github.com/dotnet-architecture/eShopModernizing ](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="f5e56-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at [https://github.com/dotnet-architecture/eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

- <span data-ttu-id="f5e56-111">**Tour durch Shopping legacy-apps (modernisieren Baseline-apps)**</span><span class="sxs-lookup"><span data-stu-id="f5e56-111">**Tour of eShop legacy apps (baseline apps to modernize)**</span></span>

- <span data-ttu-id="f5e56-112">**Ihre vorhandenen ASP.NET Web-apps (Web Forms und MVC) mit Windows-Containern containerize**</span><span class="sxs-lookup"><span data-stu-id="f5e56-112">**Containerize your existing ASP.NET web apps (WebForms & MVC) with Windows Containers**</span></span>

- <span data-ttu-id="f5e56-113">**Containerize vorhandenen WCF-Dienste (N-Tier-apps) mit Windows-Containern**</span><span class="sxs-lookup"><span data-stu-id="f5e56-113">**Containerize your existing WCF services (N-Tier apps) with Windows Containers**</span></span>

- <span data-ttu-id="f5e56-114">**Bereitstellen der Windows Container-basierten app in Azure-VMs**</span><span class="sxs-lookup"><span data-stu-id="f5e56-114">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="f5e56-115">**Bereitstellen Sie Windows-Container-basierte apps auf Kubernetes im Azure-Container-Dienst**</span><span class="sxs-lookup"><span data-stu-id="f5e56-115">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

- <span data-ttu-id="f5e56-116">**Bereitstellen von Windows-Container-basierten apps Azure Service Fabric**</span><span class="sxs-lookup"><span data-stu-id="f5e56-116">**Deploy your Windows Containers-based apps to Azure Service Fabric**</span></span>


## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="f5e56-117">Exemplarische Vorgehensweise 1: Überblick Shopping legacy-apps</span><span class="sxs-lookup"><span data-stu-id="f5e56-117">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="f5e56-118">Technische Anleitung-Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="f5e56-118">Technical walkthrough availability</span></span>

<span data-ttu-id="f5e56-119">Die vollständige technische Exemplarische Vorgehensweise ist in der eShopModernizing GitHub-Repository-Wiki verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f5e56-119">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="f5e56-120">eShopModernizing Wiki Exemplarische Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="f5e56-120">eShopModernizing wiki walkthroughs</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki)


### <a name="overview"></a><span data-ttu-id="f5e56-121">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f5e56-121">Overview</span></span>

<span data-ttu-id="f5e56-122">In dieser exemplarischen Vorgehensweise können Sie die ursprüngliche Implementierung von drei Beispiel Legacyanwendungen untersuchen.</span><span class="sxs-lookup"><span data-stu-id="f5e56-122">In this walkthrough, you can explore the initial implementation of three sample legacy applications.</span></span> <span data-ttu-id="f5e56-123">Die ersten beiden Beispiel Web-apps haben eine monolithische Architektur und mithilfe des klassischen ASP.NET erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f5e56-123">The first two sample web apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="f5e56-124">Eine Anwendung basiert auf ASP.NET 4.x MVC; die zweite Anwendung basiert auf ASP.NET 4.x Web Forms.</span><span class="sxs-lookup"><span data-stu-id="f5e56-124">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span> <span data-ttu-id="f5e56-125">Die dritte app ist eine 3-Ebenen-app aus, das eine WinForms-Client-app und einer serverseitigen [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) Dienst.</span><span class="sxs-lookup"><span data-stu-id="f5e56-125">The third app is a 3-Tier app composed by a client WinForms app and a server-side [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) service.</span></span>

<span data-ttu-id="f5e56-126">Alle diese Anwendungen finden Sie unter der [eShopModernizing GitHub-Repository](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="f5e56-126">All these applications are available at the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

### <a name="goals"></a><span data-ttu-id="f5e56-127">Ziele</span><span class="sxs-lookup"><span data-stu-id="f5e56-127">Goals</span></span>

<span data-ttu-id="f5e56-128">Das wichtigste Ziel dieser exemplarischen Vorgehensweise besteht darin, mit diesen apps und mit ihren Code und Konfiguration vertraut.</span><span class="sxs-lookup"><span data-stu-id="f5e56-128">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="f5e56-129">Sie können die apps konfigurieren, sodass sie generieren und Verwenden von simulierten Daten ohne Verwendung der SQL-Datenbank für Testzwecke verwenden.</span><span class="sxs-lookup"><span data-stu-id="f5e56-129">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="f5e56-130">Diese optionale Konfiguration basiert auf Abhängigkeitsinjektion, in einer entkoppelten Weise.</span><span class="sxs-lookup"><span data-stu-id="f5e56-130">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario-1-aspnet-web-apps"></a><span data-ttu-id="f5e56-131">Szenario 1: ASP.NET Web-apps</span><span class="sxs-lookup"><span data-stu-id="f5e56-131">Scenario 1: ASP.NET Web apps</span></span>

<span data-ttu-id="f5e56-132">Die folgende Abbildung zeigt die einfachen Szenarios, die ursprüngliche legacy ASP.NET-Webanwendungen.</span><span class="sxs-lookup"><span data-stu-id="f5e56-132">The figure below shows the simple scenario of the original legacy ASP.NET web applications.</span></span>

> ![Einfache Architektur-Szenario für die ursprüngliche legacy ASP.NET-Webanwendungen](./media/image5-1.png)
>

<span data-ttu-id="f5e56-134">Aus Sicht der Business-Domäne bieten beide apps den gleichen Katalog Verwaltungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="f5e56-134">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="f5e56-135">Mitglieder des Teams Enterprise Shopping würde die app anzeigen und Bearbeiten des Produktkatalogs verwenden.</span><span class="sxs-lookup"><span data-stu-id="f5e56-135">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span> 

<span data-ttu-id="f5e56-136">Die nächste Abbildung zeigt die anfänglichen app Screenshots.</span><span class="sxs-lookup"><span data-stu-id="f5e56-136">The next figure shows the initial app screenshots.</span></span>

![ASP.NET MVC und ASP.NET Web Forms-Anwendungen (vorhandene/Legacy-Technologien)](./media/image5-2.png)

<span data-ttu-id="f5e56-138">Abhängigkeiten ASP.NET 4.x oder früheren Versionen (entweder für MVC oder Web Forms) bedeutet, dass diese Anwendungen keine auf .NET Core ausgeführt werden, wenn der Code vollständig neu geschrieben wird, mithilfe von ASP.NET Core MVC.</span><span class="sxs-lookup"><span data-stu-id="f5e56-138">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won’t run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span> 

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a><span data-ttu-id="f5e56-139">Szenario 2: WCF-Diensts und WinForms-Client-app (3-Ebenen-app)</span><span class="sxs-lookup"><span data-stu-id="f5e56-139">Scenario 2: WCF service and WinForms client app (3-Tier app)</span></span>

<span data-ttu-id="f5e56-140">Die folgende Abbildung zeigt die einfachen Szenarios, die ursprüngliche ältere 3-Ebenen-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f5e56-140">The figure below shows the simple scenario of the original 3-Tier legacy application.</span></span>

> ![Einfache Architektur-Szenario für die ursprüngliche legacy 3-Ebenen-app mit einem WCF-Dienst und einer WinForms-Client-app](./media/image5-1.5.png)
>

### <a name="benefits"></a><span data-ttu-id="f5e56-142">Vorteile</span><span class="sxs-lookup"><span data-stu-id="f5e56-142">Benefits</span></span>

<span data-ttu-id="f5e56-143">Die Vorteile der in dieser exemplarischen Vorgehensweise sind einfach: nur mit dem Code und die anfängliche apps vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="f5e56-143">The benefits of this walkthrough are simple: Just get familiar with the code and initial apps.</span></span>

### <a name="next-steps"></a><span data-ttu-id="f5e56-144">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f5e56-144">Next steps</span></span>

<span data-ttu-id="f5e56-145">Untersuchen Sie diese Inhalte ausführlicheren im GitHub-Wiki:</span><span class="sxs-lookup"><span data-stu-id="f5e56-145">Explore this content more in-depth on the GitHub wiki:</span></span>

  - [<span data-ttu-id="f5e56-146">Tour auf der Basislinie ASP.NET MVC und "legacy" Web Forms-apps</span><span class="sxs-lookup"><span data-stu-id="f5e56-146">Tour on the baseline ASP.NET MVC and Web Forms “legacy” apps</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
  - [<span data-ttu-id="f5e56-147">Tour auf die Baseline-WCF-Dienst und WinForms (3-Ebenen) "legacy" app</span><span class="sxs-lookup"><span data-stu-id="f5e56-147">Tour on the baseline WCF service and WinForms (3-Tier) “legacy” app</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)


## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="f5e56-148">Exemplarische Vorgehensweise 2: Containerize, Ihre vorhandenen .NET Anwendungen mit Windows-Containern</span><span class="sxs-lookup"><span data-stu-id="f5e56-148">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="overview"></a><span data-ttu-id="f5e56-149">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f5e56-149">Overview</span></span>

<span data-ttu-id="f5e56-150">Mithilfe von Windows-Containern um Bereitstellung der vorhandenen .NET-Anwendungen, wie die Grundlage von MVC oder Web Forms, WCF, Produktions-, Entwicklungs- und testumgebungen zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="f5e56-150">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="f5e56-151">Ziele</span><span class="sxs-lookup"><span data-stu-id="f5e56-151">Goals</span></span>

<span data-ttu-id="f5e56-152">Das Ziel dieser exemplarischen Vorgehensweise werden Ihnen mehrere Optionen für eine vorhandene .NET Framework-Anwendung containerizing anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f5e56-152">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="f5e56-153">Sie haben folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="f5e56-153">You can:</span></span>

- <span data-ttu-id="f5e56-154">Containerize Ihrer Anwendung mit [Visual Studio 2017-Tools für Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio-2017 oder höhere Versionen).</span><span class="sxs-lookup"><span data-stu-id="f5e56-154">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="f5e56-155">Containerize Ihrer Anwendung durch manuelles Hinzufügen von einer [dockerfile-Datei](https://docs.docker.com/engine/reference/builder/), und klicken Sie dann mit der [Docker-Befehlszeilenschnittstelle](https://docs.docker.com/engine/reference/commandline/cli/).</span><span class="sxs-lookup"><span data-stu-id="f5e56-155">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="f5e56-156">Containerize Ihrer Anwendung mithilfe der [Img2Docker](https://github.com/docker/communitytools-image2docker-win) -Tool (eine Open-Source-Tool von Docker).</span><span class="sxs-lookup"><span data-stu-id="f5e56-156">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="f5e56-157">In dieser exemplarischen Vorgehensweise konzentriert sich auf Visual Studio 2017-Tools für Docker Ansatz die anderen beiden Methoden sind allerdings hinsichtlich dockerfile-Dateien mit ähnlich.</span><span class="sxs-lookup"><span data-stu-id="f5e56-157">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario-1-containerized-aspnet-web-apps"></a><span data-ttu-id="f5e56-158">Szenario 1: Datenvolumes ASP.NET Web-apps</span><span class="sxs-lookup"><span data-stu-id="f5e56-158">Scenario 1: Containerized ASP.NET web apps</span></span>

<span data-ttu-id="f5e56-159">Die folgende Abbildung zeigt das Szenario für Datenvolumes Shopping legacy-apps Webanwendungen.</span><span class="sxs-lookup"><span data-stu-id="f5e56-159">Figure below shows the scenario for containerized eShop legacy web apps applications.</span></span>

> ![Vereinfachte Architekturdiagramm von ASP.NET-Anwendungen in einer Entwicklungsumgebung in Containern](./media/image5-3.png)
>


### <a name="scenario-2-containerized-wcf-service"></a><span data-ttu-id="f5e56-161">Szenario 2: Datenvolumes WCF-Dienst</span><span class="sxs-lookup"><span data-stu-id="f5e56-161">Scenario 2: Containerized WCF service</span></span>

<span data-ttu-id="f5e56-162">Die folgende Abbildung zeigt das Szenario für eine 3-Ebenen-app mit einem Datenvolumes WCF-Dienst.</span><span class="sxs-lookup"><span data-stu-id="f5e56-162">Figure below shows the scenario for a 3-Tier app with a containerized WCF service.</span></span> 

> ![Architekturdiagramm von Datenvolumes WCF-Dienst in einer Entwicklungsumgebung vereinfacht](./media/image5-3.5.png)
>

### <a name="benefits"></a><span data-ttu-id="f5e56-164">Vorteile</span><span class="sxs-lookup"><span data-stu-id="f5e56-164">Benefits</span></span>

<span data-ttu-id="f5e56-165">Es sind Vorteile, die aufgrund eines monolithischen Anwendung in einem Container ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f5e56-165">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="f5e56-166">Zunächst erstellen Sie ein Bild für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f5e56-166">First, you create an image for the application.</span></span> <span data-ttu-id="f5e56-167">Ab diesem Zeitpunkt wird Sie jede Bereitstellung in der gleichen Umgebung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f5e56-167">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="f5e56-168">Jeder Container verwendet die gleiche Version des Betriebssystems, die gleiche Version von Abhängigkeiten installiert wurde, verwendet die gleiche Version von .NET Framework und wird erstellt, indem Sie mit der gleichen.</span><span class="sxs-lookup"><span data-stu-id="f5e56-168">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="f5e56-169">Grundsätzlich können Sie die Abhängigkeiten der Anwendung mithilfe eines Images von Docker steuern.</span><span class="sxs-lookup"><span data-stu-id="f5e56-169">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="f5e56-170">Die Abhängigkeiten Reisen mit der Anwendung während der Bereitstellung auf den Container.</span><span class="sxs-lookup"><span data-stu-id="f5e56-170">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="f5e56-171">Ein zusätzlicher Vorteil besteht darin, dass Entwickler die Anwendung in die konsistente Umgebung ausführen können, die von Windows-Container bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f5e56-171">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="f5e56-172">Probleme, die nur mit bestimmten Versionen angezeigt werden können sofort entdeckt werden, statt in einer Staging- oder Produktionsserver Umgebung einbringen.</span><span class="sxs-lookup"><span data-stu-id="f5e56-172">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="f5e56-173">Unterschiede in entwicklungsumgebungen verwendet, die von Mitgliedern des Entwicklungsteams unerheblich kleiner, wenn Anwendungen in Containern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f5e56-173">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="f5e56-174">Sammelartikeleinheit haben auch eine flachere mit horizontaler Skalierung Kurve.</span><span class="sxs-lookup"><span data-stu-id="f5e56-174">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="f5e56-175">Datenvolumes apps können Sie weitere Anwendung und Dienstinstanzen (basierend auf den Container) verfügen, in einem virtuellen Computer oder physischen Computer im Vergleich zu normalen anwendungsbereitstellungen pro Computer.</span><span class="sxs-lookup"><span data-stu-id="f5e56-175">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="f5e56-176">Dies bedeutet höhere Dichte und weniger erforderlichen Ressourcen, insbesondere wenn Sie Orchestrators wie Kubernetes oder Service Fabric verwenden.</span><span class="sxs-lookup"><span data-stu-id="f5e56-176">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes or Service Fabric.</span></span>

<span data-ttu-id="f5e56-177">Containerization, im Idealfall, erfordert keine Änderungen am Anwendungscode (C\#).</span><span class="sxs-lookup"><span data-stu-id="f5e56-177">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="f5e56-178">In den meisten Fällen benötigen Sie nur die Docker-Bereitstellung-Metadatendateien (dockerfile-Dateien und Docker Compose-Dateien).</span><span class="sxs-lookup"><span data-stu-id="f5e56-178">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="f5e56-179">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f5e56-179">Next steps</span></span>

<span data-ttu-id="f5e56-180">Untersuchen Sie diese Inhalte ausführlicheren im GitHub-Wiki:</span><span class="sxs-lookup"><span data-stu-id="f5e56-180">Explore this content more in-depth on the GitHub wiki:</span></span>

  - [<span data-ttu-id="f5e56-181">Wie die .NET Framework-Web-apps mit Windows-Container und Docker containerize</span><span class="sxs-lookup"><span data-stu-id="f5e56-181">How to containerize the .NET Framework web apps with Windows Containers and Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
  - [<span data-ttu-id="f5e56-182">Hinzufügen von Docker-Support, um einen WCF-Dienst</span><span class="sxs-lookup"><span data-stu-id="f5e56-182">Adding Docker Support to a WCF service</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)



## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="f5e56-183">Exemplarische Vorgehensweise 3: Bereitstellen der Windows-Container-basierten Anwendung auf Azure VMs</span><span class="sxs-lookup"><span data-stu-id="f5e56-183">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="f5e56-184">Technische Anleitung-Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="f5e56-184">Technical walkthrough availability</span></span>

<span data-ttu-id="f5e56-185">Die vollständige technische Exemplarische Vorgehensweise ist in der eShopModernizing GitHub-Repository-Wiki verfügbar: [https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span><span class="sxs-lookup"><span data-stu-id="f5e56-185">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span></span>

### <a name="overview"></a><span data-ttu-id="f5e56-186">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f5e56-186">Overview</span></span>

<span data-ttu-id="f5e56-187">Auf einem Docker-Host auf einem Windows Server 2016 virtuellen Computer (VM) in Azure bereitstellen, können Sie die Entwicklung/Test/Stagingumgebungen schnell einzurichten.</span><span class="sxs-lookup"><span data-stu-id="f5e56-187">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="f5e56-188">Darüber hinaus haben Sie einen allgemeinen Platz für Tester oder Geschäftsbenutzer, um die app zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f5e56-188">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="f5e56-189">Virtuelle Computer können auch gültige Infrastruktur als eine produktionsumgebungen Service (IaaS) sein.</span><span class="sxs-lookup"><span data-stu-id="f5e56-189">VMs also can be valid Infrastucture as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="f5e56-190">Ziele</span><span class="sxs-lookup"><span data-stu-id="f5e56-190">Goals</span></span>

<span data-ttu-id="f5e56-191">Das Ziel dieser exemplarischen Vorgehensweise werden Sie mehrere Alternativen an, die Ihnen beim Bereitstellen von Windows-Container für Azure-VMs, die auf Windows Server 2016 oder höher basieren.</span><span class="sxs-lookup"><span data-stu-id="f5e56-191">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="f5e56-192">Szenarien</span><span class="sxs-lookup"><span data-stu-id="f5e56-192">Scenarios</span></span>

<span data-ttu-id="f5e56-193">In dieser exemplarischen Vorgehensweise werden mehrere Szenarien behandelt.</span><span class="sxs-lookup"><span data-stu-id="f5e56-193">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="f5e56-194">Szenario A: Bereitstellen in einer Azure-VM aus einer Dev PC über Docker-Modul-Verbindung</span><span class="sxs-lookup"><span data-stu-id="f5e56-194">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Über eine Dev PC über eine Verbindung Docker-Modul in einer Azure-VM bereitstellen](./media/image5-4.png)

> <span data-ttu-id="f5e56-196">**Abbildung 5-4.**</span><span class="sxs-lookup"><span data-stu-id="f5e56-196">**Figure 5-4.**</span></span> <span data-ttu-id="f5e56-197">Über eine Dev PC über eine Verbindung Docker-Modul in einer Azure-VM bereitstellen</span><span class="sxs-lookup"><span data-stu-id="f5e56-197">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="f5e56-198">Szenario B: Bereitstellen Sie in einer Azure-VM über einen Docker-Registrierung</span><span class="sxs-lookup"><span data-stu-id="f5e56-198">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Bereitstellen Sie in einer Azure-VM über einen Docker-Registrierung](./media/image5-5.png)

> <span data-ttu-id="f5e56-200">**Abbildung 5-5.**</span><span class="sxs-lookup"><span data-stu-id="f5e56-200">**Figure 5-5.**</span></span> <span data-ttu-id="f5e56-201">Bereitstellen Sie in einer Azure-VM über einen Docker-Registrierung</span><span class="sxs-lookup"><span data-stu-id="f5e56-201">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-visual-studio-team-services"></a><span data-ttu-id="f5e56-202">Szenario "c:" in einer Azure-VM bereitstellen, von CI-CD-Pipelines in Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="f5e56-202">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Visual Studio Team Services</span></span>

![Bereitstellen Sie in einer Azure-VM von CI-CD-Pipelines in Visual Studio Team Services](./media/image5-6.png)

> <span data-ttu-id="f5e56-204">**Abbildung 5-6.**</span><span class="sxs-lookup"><span data-stu-id="f5e56-204">**Figure 5-6.**</span></span> <span data-ttu-id="f5e56-205">Bereitstellen Sie in einer Azure-VM von CI-CD-Pipelines in Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="f5e56-205">Deploy to an Azure VM from CI/CD pipelines in Visual Studio Team Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="f5e56-206">Azure-VMs für Windows-Container</span><span class="sxs-lookup"><span data-stu-id="f5e56-206">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="f5e56-207">Azure-VMs für Windows-Container sind virtuelle Computer basierend auf Windows Server 2016, Windows 10 oder höher, sowohl mit Docker-Modul einrichten.</span><span class="sxs-lookup"><span data-stu-id="f5e56-207">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="f5e56-208">In den meisten Fällen wird die Windows Server 2016 in den Azure-VMs verwendet.</span><span class="sxs-lookup"><span data-stu-id="f5e56-208">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="f5e56-209">Azure bietet zurzeit einen virtuellen Computer mit dem Namen **Windows Server 2016 mit Containern**.</span><span class="sxs-lookup"><span data-stu-id="f5e56-209">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="f5e56-210">Dieser virtuelle Computer können Sie das neue Windows Server-Container-Feature, mit Windows Server Core oder Windows Nano Server versuchen.</span><span class="sxs-lookup"><span data-stu-id="f5e56-210">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="f5e56-211">Containerbetriebssystem-Images werden installiert, und klicken Sie dann der virtuellen Computer ist einsatzbereit mit Docker.</span><span class="sxs-lookup"><span data-stu-id="f5e56-211">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="f5e56-212">Vorteile</span><span class="sxs-lookup"><span data-stu-id="f5e56-212">Benefits</span></span>

<span data-ttu-id="f5e56-213">Obwohl Windows-Container bei der Bereitstellung in Azure zu einer lokalen Windows Server 2016-VMs bereitgestellt werden kann, erhalten Sie eine einfachere Möglichkeit, sofort zu verwendende Windows Server-Container-VMs Einstieg.</span><span class="sxs-lookup"><span data-stu-id="f5e56-213">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="f5e56-214">Sie erhalten auch einen allgemeinen online Speicherort, der den Testern und automatische Skalierung über Azure VM-skalierungsgruppen zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="f5e56-214">You also get a common online location that’s accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="f5e56-215">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f5e56-215">Next steps</span></span>

<span data-ttu-id="f5e56-216">Untersuchen Sie diese Inhalte ausführlicheren im GitHub-Wiki:</span><span class="sxs-lookup"><span data-stu-id="f5e56-216">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a><span data-ttu-id="f5e56-217">Exemplarische Vorgehensweise 4: Bereitstellen von Windows-Container-basierte apps auf Azure-Container-Instanzen (ACI)</span><span class="sxs-lookup"><span data-stu-id="f5e56-217">Walkthrough 4: Deploy your Windows Containers-based apps to Azure Container Instances (ACI)</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="f5e56-218">Technische Anleitung-Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="f5e56-218">Technical walkthrough availability</span></span>

<span data-ttu-id="f5e56-219">Die vollständige technische Exemplarische Vorgehensweise ist in der eShopModernizing GitHub-Repository-Wiki verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f5e56-219">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="f5e56-220">[Bereitstellen von Apps für ACI (Azure-Container-Instanzen)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span><span class="sxs-lookup"><span data-stu-id="f5e56-220">[Deploying the Apps to ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span></span>

### <a name="overview"></a><span data-ttu-id="f5e56-221">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f5e56-221">Overview</span></span>

<span data-ttu-id="f5e56-222">[Azure-Container-Instanzen (ACI)](https://docs.microsoft.com/en-us/azure/container-instances/) ist die schnellste Möglichkeit, den eine Container-Dev/Test/Staging-Umgebung verfügen, in dem Sie einzelne Instanzen von Containern bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="f5e56-222">[Azure Container Instances (ACI)](https://docs.microsoft.com/en-us/azure/container-instances/) is the quickest way to have a Containers dev/test/staging environment where you can deploy single instances of containers.</span></span>

### <a name="goals"></a><span data-ttu-id="f5e56-223">Ziele</span><span class="sxs-lookup"><span data-stu-id="f5e56-223">Goals</span></span>

<span data-ttu-id="f5e56-224">In dieser exemplarischen Vorgehensweise zeigt Sie die wichtigsten Szenarien bei der Bereitstellung von Windows-Container auf Azure-Container-Instanzen (ACI) und wie Sie in ACI eShopModernizing Apps bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="f5e56-224">This walkthrough shows you the main scenarios when deploying Windows Containers to Azure Container Instances (ACI) and how you can deploy eShopModernizing Apps into ACI.</span></span>

### <a name="scenarios"></a><span data-ttu-id="f5e56-225">Szenarien</span><span class="sxs-lookup"><span data-stu-id="f5e56-225">Scenarios</span></span>

<span data-ttu-id="f5e56-226">Variationen zum Bereitstellen von apps eShopModernizing in ACI z. B. nur eine oder alle apps (MVC-Anwendung, WebForms-app oder WCF-Dienst) bereitstellen kann.</span><span class="sxs-lookup"><span data-stu-id="f5e56-226">There can be variations about deploying the eShopModernizing apps into ACI such as deploying just one or all of the apps (MVC app, WebForms app or WCF service).</span></span> <span data-ttu-id="f5e56-227">Im folgenden Szenario unten sehen Sie die ASP.NET MVC-app sowie den SQL Server-Container beider bereitgestellt als Container in ACI (Azure-Container-Instanzen).</span><span class="sxs-lookup"><span data-stu-id="f5e56-227">In the following scenario shown below you can see the ASP.NET MVC app plus the SQL Server container both of them deployed as containers into ACI (Azure Container Instances).</span></span>

![Bereitstellen einer Entwicklungsumgebung für ACI](./media/image5-3.5.6.png)

### <a name="benefits"></a><span data-ttu-id="f5e56-229">Vorteile</span><span class="sxs-lookup"><span data-stu-id="f5e56-229">Benefits</span></span>

<span data-ttu-id="f5e56-230">Azure Containerinstanzen erleichtert das Erstellen und verwalten Docker-Containern in Azure, ohne für die Bereitstellung von virtuellen Maschinen oder ein Diensts auf höherer Ebene zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f5e56-230">Azure Container Instances makes it easy to create and manage Docker containers in Azure, without having to provision virtual machines or adopt a higher-level service.</span></span> <span data-ttu-id="f5e56-231">Mit dem ACI Sie direkt einen Windows-Container in Azure bereitstellen und verfügbar machen es mit dem Internet über einen vollqualifizierten Domänennamen (FQDN) in wenigen Sekunden (vorausgesetzt, dass Sie die Windows-Container-Image kann jetzt in einem Docker-Registrierung wie Docker Hub oder Azure-Container verfügen Registrierung).</span><span class="sxs-lookup"><span data-stu-id="f5e56-231">With ACI, you can directly deploy a Windows container in Azure and expose it to the internet with a fully qualified domain name (FQDN) in a matter of seconds (Provided that you have the Windows Container image ready in a Docker registry like Docker Hub or Azure Container Registry).</span></span>

### <a name="considerations"></a><span data-ttu-id="f5e56-232">Weitere Überlegungen</span><span class="sxs-lookup"><span data-stu-id="f5e56-232">Considerations</span></span>

<span data-ttu-id="f5e56-233">Bereitstellen von Windows-Containern mit einer Vollversion von .NET Framework / ASP.NET oder SQL Server in Azure Container Instanzen (ACI) ist nicht ganz so schnell wie das zu einem regulären Docker-Host (z. B. Windows Server 2016 mit Windows-Containern) bereitstellen, da die Docker-Images werden muss (aus der Registrierung Docker Pull) jedes Mal heruntergeladen und die Größe der SQL-Container-Abbild (15.1 GB) und ASP.NET Container-Abbild (13.9 GB) sind ausgesprochen umfassende, jedoch wesentlich kostengünstiger als die Beibehaltung eines eigenen Docker-Hosts (dauerhaft Online ist WindowsServer 2016 mit Windows-Container-VM in Azure) ganz zu schweigen eine gesamte Orchestrator wie Kubernetes, die in Azure (so/ACS) oder Azure Service Fabric andererseits, großartige Auswahlmöglichkeiten für produktionsbereitstellungen sind.</span><span class="sxs-lookup"><span data-stu-id="f5e56-233">Deploying Windows Containers with either full .NET Framework / ASP.NET or SQL Server into Azure Container Instances (ACI) is not quite as fast as deploying to a regular Docker Host (like a Windows Server 2016 with Windows Containers) because the Docker image has to be downloaded (pulled from the Docker registry) every time and the sizes of the SQL container image (15.1 GB) and the ASP.NET container image (13.9 GB) are significantly large, however it is much cheaper than maintaining your own docker host (permanently on-line Windows Server 2016 with Windows Containers VM in Azure) not to mention a whole orchestrator like Kubernetes in Azure (AKS/ACS) or Azure Service Fabric which are, on the other hand, great choices for production deployments.</span></span>

<span data-ttu-id="f5e56-234">Als main Folgerung ist mithilfe von Azure-Container-Instanzen einen sehr bestechenden Option für Entwicklungs-und Testszenarien und Pipelines CI-CD aus.</span><span class="sxs-lookup"><span data-stu-id="f5e56-234">As main conclusion, using Azure Container Instances is a very compelling option for Dev/Test scenarios and for CI/CD pipelines.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f5e56-235">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f5e56-235">Next steps</span></span>

<span data-ttu-id="f5e56-236">Untersuchen Sie diese Inhalte ausführlicheren im GitHub-Wiki:</span><span class="sxs-lookup"><span data-stu-id="f5e56-236">Explore this content more in-depth on the GitHub wiki:</span></span> 

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)TBD)


## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="f5e56-237">Exemplarische Vorgehensweise 5: Bereitstellen der Windows-Container-basierte apps für Kubernetes im Azure-Container-Dienst</span><span class="sxs-lookup"><span data-stu-id="f5e56-237">Walkthrough 5: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="f5e56-238">Technische Anleitung-Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="f5e56-238">Technical walkthrough availability</span></span>

<span data-ttu-id="f5e56-239">Die vollständige technische Exemplarische Vorgehensweise ist in der eShopModernizing GitHub-Repository-Wiki verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f5e56-239">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

### <a name="overview"></a><span data-ttu-id="f5e56-240">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f5e56-240">Overview</span></span>

<span data-ttu-id="f5e56-241">Eine Anwendung, die basierend auf Windows-Containern müssen schnell verschieben unterwegs noch weiter von IaaS-VMs-Plattformen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f5e56-241">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="f5e56-242">Dies ist erforderlich, um problemlos hohe Skalierbarkeit zu erzielen eine bessere Leistung automatisierte Skalierbarkeit und für eine deutliche leistungsverbesserung automatische Bereitstellungen und versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="f5e56-242">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="f5e56-243">Sie können diese Ziele erreichen, indem Sie mit der Orchestrator [Kubernetes](https://kubernetes.io/), verfügbar im [Dienste der Azure-Container](https://azure.microsoft.com/services/container-service/).</span><span class="sxs-lookup"><span data-stu-id="f5e56-243">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="f5e56-244">Ziele</span><span class="sxs-lookup"><span data-stu-id="f5e56-244">Goals</span></span>

<span data-ttu-id="f5e56-245">Das Ziel dieser exemplarischen Vorgehensweise erfahren, wie in einer Windows-Container-basierte Anwendung Kubernetes bereitstellen ist (so genannte *K8s*) im Azure-Container-Dienst.</span><span class="sxs-lookup"><span data-stu-id="f5e56-245">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="f5e56-246">Bereitstellen für Kubernetes von Grund auf neu ist ein zweistufiger Prozess:</span><span class="sxs-lookup"><span data-stu-id="f5e56-246">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1.  <span data-ttu-id="f5e56-247">Bereitstellen eines Clusters Kubernetes Azure-Container-Dienst an.</span><span class="sxs-lookup"><span data-stu-id="f5e56-247">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2.  <span data-ttu-id="f5e56-248">Stellen Sie die Anwendung und die zugehörigen Ressourcen für den Cluster Kubernetes bereit.</span><span class="sxs-lookup"><span data-stu-id="f5e56-248">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="f5e56-249">Szenarien</span><span class="sxs-lookup"><span data-stu-id="f5e56-249">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="f5e56-250">Szenario A: Bereitstellen direkt zu einem Cluster Kubernetes aus einer Developer-Umgebung</span><span class="sxs-lookup"><span data-stu-id="f5e56-250">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![Direkt auf einem Cluster Kubernetes aus einer Entwicklungsumgebung bereitstellen](./media/image5-7.png)

> <span data-ttu-id="f5e56-252">**Abbildung 5-7.**</span><span class="sxs-lookup"><span data-stu-id="f5e56-252">**Figure 5-7.**</span></span> <span data-ttu-id="f5e56-253">Direkt auf einem Cluster Kubernetes aus einer Entwicklungsumgebung bereitstellen</span><span class="sxs-lookup"><span data-stu-id="f5e56-253">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-team-services"></a><span data-ttu-id="f5e56-254">Szenario B: zu einem Cluster Kubernetes bereitstellen, von CI-CD pipelines im Team Services</span><span class="sxs-lookup"><span data-stu-id="f5e56-254">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Team Services</span></span>

![Bereitstellen Sie für einen Cluster Kubernetes CI-CD-Pipelines in Team Services](./media/image5-8.png)

> <span data-ttu-id="f5e56-256">**Abbildung 5-8.**</span><span class="sxs-lookup"><span data-stu-id="f5e56-256">**Figure 5-8.**</span></span> <span data-ttu-id="f5e56-257">Bereitstellen Sie für einen Cluster Kubernetes CI-CD-Pipelines in Team Services</span><span class="sxs-lookup"><span data-stu-id="f5e56-257">Deploy to a Kubernetes cluster from CI/CD pipelines in Team Services</span></span>

### <a name="benefits"></a><span data-ttu-id="f5e56-258">Vorteile</span><span class="sxs-lookup"><span data-stu-id="f5e56-258">Benefits</span></span>

<span data-ttu-id="f5e56-259">Es gibt viele Vorteile für eine Bereitstellung auf einem Cluster in Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="f5e56-259">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="f5e56-260">Der größte Vorteil ist, dass Sie eine produktionsbereite Umgebung erhalten, in der Sie die Anwendung basierend auf der Anzahl der containerinstanzen, die Sie skalieren können (Inner-Skalierbarkeit in den vorhandenen Knoten) verwenden möchten, die und basierend auf der Anzahl von Knoten oder virtuellen Computern in den Cluster ( Globale Skalierbarkeit des Clusters).</span><span class="sxs-lookup"><span data-stu-id="f5e56-260">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="f5e56-261">Azure Containerdienst wird die beliebte Open Source-Tools und Technologien speziell für Azure optimiert.</span><span class="sxs-lookup"><span data-stu-id="f5e56-261">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="f5e56-262">Sie erhalten eine geöffnete Projektmappe, die Portabilität, die sowohl für die Container als auch für Ihre Anwendungskonfiguration bietet.</span><span class="sxs-lookup"><span data-stu-id="f5e56-262">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="f5e56-263">Wählen Sie die Größe der Anzahl der Hosts, und der Orchestrator-Tools-Container-Dienst verarbeitet alle anderen.</span><span class="sxs-lookup"><span data-stu-id="f5e56-263">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="f5e56-264">Mit Kubernetes können Entwickler Gedanken über physische und virtuelle Computer, Status, für die Planung einer Container anwendungsorientierte-Infrastruktur, die die folgenden Funktionen, u. a. erleichtert:</span><span class="sxs-lookup"><span data-stu-id="f5e56-264">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="f5e56-265">Anwendungen, die basierend auf mehrere Container</span><span class="sxs-lookup"><span data-stu-id="f5e56-265">Applications based on multiple containers</span></span>

- <span data-ttu-id="f5e56-266">Replizieren von containerinstanzen und automatische horizontale Skalierung</span><span class="sxs-lookup"><span data-stu-id="f5e56-266">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="f5e56-267">Benennen und ermitteln (z. B. internes DNS)</span><span class="sxs-lookup"><span data-stu-id="f5e56-267">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="f5e56-268">Lastenausgleich Lasten</span><span class="sxs-lookup"><span data-stu-id="f5e56-268">Balancing loads</span></span>

- <span data-ttu-id="f5e56-269">Parallele updates</span><span class="sxs-lookup"><span data-stu-id="f5e56-269">Rolling updates</span></span>

- <span data-ttu-id="f5e56-270">Verteilen von geheimen Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="f5e56-270">Distributing secrets</span></span>

- <span data-ttu-id="f5e56-271">Integritätsprüfungen für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="f5e56-271">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="f5e56-272">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f5e56-272">Next steps</span></span>

<span data-ttu-id="f5e56-273">Untersuchen Sie diese Inhalte ausführlicheren im GitHub-Wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span><span class="sxs-lookup"><span data-stu-id="f5e56-273">Explore this content more in-depth on the GitHub wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span></span>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a><span data-ttu-id="f5e56-274">Exemplarische Vorgehensweise 6: Bereitstellen von Windows-Container-basierte apps Azure Service Fabric</span><span class="sxs-lookup"><span data-stu-id="f5e56-274">Walkthrough 6: Deploy your Windows Containers-based apps to Azure Service Fabric</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="f5e56-275">Technische Anleitung-Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="f5e56-275">Technical walkthrough availability</span></span>

<span data-ttu-id="f5e56-276">Die vollständige technische Exemplarische Vorgehensweise ist in der eShopModernizing GitHub-Repository-Wiki verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f5e56-276">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

### <a name="overview"></a><span data-ttu-id="f5e56-277">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f5e56-277">Overview</span></span>

<span data-ttu-id="f5e56-278">Eine Anwendung, die basierend auf Windows-Containern schnell muss verschieben unterwegs noch weiter von IaaS-VMs-Plattformen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f5e56-278">An application based on Windows Containers quickly needs to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="f5e56-279">Dies ist erforderlich, um problemlos hohe Skalierbarkeit zu erzielen eine bessere Leistung automatisierte Skalierbarkeit und für eine deutliche leistungsverbesserung automatische Bereitstellungen und versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="f5e56-279">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="f5e56-280">Sie können diese Ziele erreichen, mit dem Orchestrator Azure Service Fabric, das in der Azure-Cloud verfügbar, aber auch zur Verwendung von lokalen verfügbar ist, oder sogar in einer anderen öffentlichen Cloud.</span><span class="sxs-lookup"><span data-stu-id="f5e56-280">You can achieve these goals by using the orchestrator Azure Service Fabric, which is available in the Azure cloud, but also available to use on-premises, or even in a different public cloud.</span></span>

### <a name="goals"></a><span data-ttu-id="f5e56-281">Ziele</span><span class="sxs-lookup"><span data-stu-id="f5e56-281">Goals</span></span>

<span data-ttu-id="f5e56-282">Das Ziel dieser exemplarischen Vorgehensweise ist, wie Sie eine Windows-Container-basierte Anwendung zu einem Service Fabric-Cluster in Azure bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f5e56-282">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to a Service Fabric cluster in Azure.</span></span> <span data-ttu-id="f5e56-283">Bereitstellen von Service Fabric von Grund auf neu ist ein zweistufiger Prozess:</span><span class="sxs-lookup"><span data-stu-id="f5e56-283">Deploying to Service Fabric from scratch is a two-step process:</span></span>

1.  <span data-ttu-id="f5e56-284">Bereitstellen von Service Fabric-Cluster in Azure (oder auf eine andere Umgebung).</span><span class="sxs-lookup"><span data-stu-id="f5e56-284">Deploy a Service Fabric cluster to Azure (or to a different environment).</span></span>

2.  <span data-ttu-id="f5e56-285">Stellen Sie die Anwendung und die zugehörigen Ressourcen für Service Fabric-Cluster bereit.</span><span class="sxs-lookup"><span data-stu-id="f5e56-285">Deploy the application and related resources to the Service Fabric cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="f5e56-286">Szenarien</span><span class="sxs-lookup"><span data-stu-id="f5e56-286">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a><span data-ttu-id="f5e56-287">Szenario A: Bereitstellen direkt zu einem Service Fabric-Cluster aus einer Developer-Umgebung</span><span class="sxs-lookup"><span data-stu-id="f5e56-287">Scenario A: Deploy directly to a Service Fabric cluster from a dev environment</span></span>

![Direkt auf einem Service Fabric-Cluster aus einer Entwicklungsumgebung bereitstellen](./media/image5-9.png)

> <span data-ttu-id="f5e56-289">**Abbildung 5-9.**</span><span class="sxs-lookup"><span data-stu-id="f5e56-289">**Figure 5-9.**</span></span> <span data-ttu-id="f5e56-290">Direkt auf einem Service Fabric-Cluster aus einer Entwicklungsumgebung bereitstellen</span><span class="sxs-lookup"><span data-stu-id="f5e56-290">Deploy directly to a Service Fabric cluster from a development environment</span></span>

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-team-services"></a><span data-ttu-id="f5e56-291">Szenario B: zu einem Service Fabric-Cluster bereitstellen, von CI-CD pipelines im Team Services</span><span class="sxs-lookup"><span data-stu-id="f5e56-291">Scenario B: Deploy to a Service Fabric cluster from CI/CD pipelines in Team Services</span></span>

![Bereitstellen Sie für Service Fabric-Cluster CI-CD-Pipelines in Visual Studio Team Services](./media/image5-10.png)

> <span data-ttu-id="f5e56-293">**Abbildung 5-10.**</span><span class="sxs-lookup"><span data-stu-id="f5e56-293">**Figure 5-10.**</span></span> <span data-ttu-id="f5e56-294">Bereitstellen Sie für Service Fabric-Cluster CI-CD-Pipelines in Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="f5e56-294">Deploy to a Service Fabric cluster from CI/CD pipelines in Visual Studio Team Services</span></span>

## <a name="benefits"></a><span data-ttu-id="f5e56-295">Vorteile</span><span class="sxs-lookup"><span data-stu-id="f5e56-295">Benefits</span></span>

<span data-ttu-id="f5e56-296">Die Vorteile der Bereitstellung auf einem Service Fabric-Cluster sind die Vorteile der Verwendung von Kubernetes ähnlich.</span><span class="sxs-lookup"><span data-stu-id="f5e56-296">The benefits of deploying to a cluster in Service Fabric are similar to the benefits of using Kubernetes.</span></span> <span data-ttu-id="f5e56-297">Ein Unterschied ist, dass Service Fabric ist eine ausgereiftere produktionsumgebung für Windows-Anwendungen im Vergleich zu Kubernetes, also in einer Betaphase für Windows-Containern in Kubernetes Version 1.9 (Dezember 2017).</span><span class="sxs-lookup"><span data-stu-id="f5e56-297">One difference, though, is that Service Fabric is a more mature production environment for Windows applications compared to Kubernetes, which is in a beta phase for Windows Containers in Kubernetes version 1.9 (December 2017).</span></span> <span data-ttu-id="f5e56-298">Kubernetes ist eine ausgereiftere für Linux.</span><span class="sxs-lookup"><span data-stu-id="f5e56-298">Kubernetes is a more mature environment for Linux.</span></span>

<span data-ttu-id="f5e56-299">Der wichtigste Vorteil der Verwendung von Azure Service Fabric ist, dass Sie eine produktionsbereite Umgebung erhalten, in der Sie die Anwendung basierend auf der Anzahl der containerinstanzen, die Sie skalieren können (Inner-Skalierbarkeit in den vorhandenen Knoten) verwenden möchten, die und basierend auf der Anzahl der Knoten oder virtuellen Computern im Cluster (globale Skalierbarkeit des Clusters).</span><span class="sxs-lookup"><span data-stu-id="f5e56-299">The main benefit of using Azure Service Fabric is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="f5e56-300">Azure Service Fabric bietet Portabilität sowohl für die Container als auch für die Anwendungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="f5e56-300">Azure Service Fabric offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="f5e56-301">Sie können einen Service Fabric-cluster in Azure oder lokal in Ihrem eigenen Datacenter installieren.</span><span class="sxs-lookup"><span data-stu-id="f5e56-301">You can have a Service Fabric cluster in Azure, or install it on-premises in your own datacenter.</span></span> <span data-ttu-id="f5e56-302">Sie können Service Fabric-Cluster in einer anderen Cloud geht auch wie installieren [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).</span><span class="sxs-lookup"><span data-stu-id="f5e56-302">You can even install a Service Fabric cluster in a different cloud, like [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).</span></span>

<span data-ttu-id="f5e56-303">Mit Service Fabric können Entwickler Gedanken über physische und virtuelle Computer ausgeführt, für die Planung einer Container anwendungsorientierte-Infrastruktur, die die folgenden Funktionen, u. a. erleichtert:</span><span class="sxs-lookup"><span data-stu-id="f5e56-303">With Service Fabric, developers can progress from thinking about physical and virtual machines to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="f5e56-304">Anwendungen, die basierend auf mehrere Container.</span><span class="sxs-lookup"><span data-stu-id="f5e56-304">Applications based on multiple containers.</span></span>

- <span data-ttu-id="f5e56-305">Das Replizieren von containerinstanzen und automatische horizontale Skalierung.</span><span class="sxs-lookup"><span data-stu-id="f5e56-305">Replicating container instances and horizontal autoscaling.</span></span>

- <span data-ttu-id="f5e56-306">Benennen und ermitteln (z. B. internes DNS).</span><span class="sxs-lookup"><span data-stu-id="f5e56-306">Naming and discovering (for example, internal DNS).</span></span>

- <span data-ttu-id="f5e56-307">Lastenausgleich lädt.</span><span class="sxs-lookup"><span data-stu-id="f5e56-307">Balancing loads.</span></span>

- <span data-ttu-id="f5e56-308">Parallele Updates an.</span><span class="sxs-lookup"><span data-stu-id="f5e56-308">Rolling updates.</span></span>

- <span data-ttu-id="f5e56-309">Verteilen von geheimen Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="f5e56-309">Distributing secrets.</span></span>

- <span data-ttu-id="f5e56-310">Anwendungsintegrität überprüft.</span><span class="sxs-lookup"><span data-stu-id="f5e56-310">Application health checks.</span></span>

<span data-ttu-id="f5e56-311">Die folgenden Funktionen sind exklusiv in Service Fabric (verglichen mit anderen Orchestrators):</span><span class="sxs-lookup"><span data-stu-id="f5e56-311">The following capabilities are exclusive in Service Fabric (compared to other orchestrators):</span></span>

- <span data-ttu-id="f5e56-312">Zustandsbehaftete Dienste-Funktion, über das Anwendungsmodell zuverlässige Dienste.</span><span class="sxs-lookup"><span data-stu-id="f5e56-312">Stateful services capability, through the Reliable Services application model.</span></span>

- <span data-ttu-id="f5e56-313">Akteure-Muster, über das Anwendungsmodell für Reliable Actors.</span><span class="sxs-lookup"><span data-stu-id="f5e56-313">Actors pattern, through the Reliable Actors application model.</span></span>

- <span data-ttu-id="f5e56-314">Bereitstellen von bare Bone Prozesse, zusätzlich zu den Windows- oder Linux-Container.</span><span class="sxs-lookup"><span data-stu-id="f5e56-314">Deploy bare-bone processes, in addition to Windows or Linux containers.</span></span>

- <span data-ttu-id="f5e56-315">Erweiterte parallelen Updates und Systemdiagnosen.</span><span class="sxs-lookup"><span data-stu-id="f5e56-315">Advanced rolling updates and health checks.</span></span>

### <a name="next-steps"></a><span data-ttu-id="f5e56-316">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f5e56-316">Next steps</span></span>

<span data-ttu-id="f5e56-317">Untersuchen Sie diese Inhalte ausführlicheren im GitHub-Wiki:</span><span class="sxs-lookup"><span data-stu-id="f5e56-317">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

>[!div class="step-by-step"]
<span data-ttu-id="f5e56-318">[Zurück](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Weiter](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="f5e56-318">[Previous](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span>
