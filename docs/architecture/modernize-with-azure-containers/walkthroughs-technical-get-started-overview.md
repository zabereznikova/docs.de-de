---
title: Exemplarische Vorgehensweisen und technische erste Schritte (Übersicht)
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Exemplarische Vorgehensweisen und technische Übersicht über den Einstieg
ms.date: 04/28/2018
ms.openlocfilehash: 190b33c4307b09bab0543d481e66ac9328074a0d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69660881"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="30a48-103">Exemplarische Vorgehensweisen und technische erste Schritte (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="30a48-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="30a48-104">Um die Größe dieses e-Books einzuschränken, wurden zusätzliche technische Dokumentation und die vollständigen exemplarischen Vorgehensweisen in einem GitHub-Repository zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="30a48-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="30a48-105">In der Online Serie der exemplarischen Vorgehensweisen, die in diesem Kapitel beschrieben werden, wird erläutert, wie Sie die verschiedenen Umgebungen, die auf Windows-Containern basieren, und die Bereitstellung in Azure schrittweise einrichten.</span><span class="sxs-lookup"><span data-stu-id="30a48-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="30a48-106">In den folgenden Abschnitten wird erläutert, worum es sich bei jeder exemplarischen Vorgehensweise um die Ziele und die allgemeine Vision handelt, und es wird ein Diagramm der beteiligten Aufgaben bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="30a48-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="30a48-107">Die exemplarischen Vorgehensweisen können Sie auch im GitHub-Repository von *eshopmodernisierender* apps unter <https://github.com/dotnet-architecture/eShopModernizing/wiki>finden.</span><span class="sxs-lookup"><span data-stu-id="30a48-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at <https://github.com/dotnet-architecture/eShopModernizing/wiki>.</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="30a48-108">Technische Exemplarische Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="30a48-108">Technical walkthrough list</span></span>

<span data-ttu-id="30a48-109">In den folgenden exemplarischen Vorgehensweisen für die ersten Schritte finden Sie konsistente und umfassende technische Anleitungen für Beispiel-apps, die Sie mithilfe von Containern per Lift und Shift migrieren und dann mithilfe mehrerer Bereitstellungs Optionen in Azure verschieben können.</span><span class="sxs-lookup"><span data-stu-id="30a48-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="30a48-110">In jeder der folgenden exemplarischen Vorgehensweisen werden die neuen Sample eshoplegacy-und eshopmoderniup-Apps verwendet, die auf GitHub unter <https://github.com/dotnet-architecture/eShopModernizing>verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="30a48-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at <https://github.com/dotnet-architecture/eShopModernizing>.</span></span>

- <span data-ttu-id="30a48-111">**Tour durch die Legacy-apps von eShop (Baseline-Apps für die Modernisierung)**</span><span class="sxs-lookup"><span data-stu-id="30a48-111">**Tour of eShop legacy apps (baseline apps to modernize)**</span></span>

- <span data-ttu-id="30a48-112">**Containerisieren vorhandener ASP.net-Web-Apps (WebForms & MVC) mit Windows-Containern**</span><span class="sxs-lookup"><span data-stu-id="30a48-112">**Containerize your existing ASP.NET web apps (WebForms & MVC) with Windows Containers**</span></span>

- <span data-ttu-id="30a48-113">**Containerisieren Ihrer vorhandenen WCF-Dienste (N-Tier-Apps) mit Windows-Containern**</span><span class="sxs-lookup"><span data-stu-id="30a48-113">**Containerize your existing WCF services (N-Tier apps) with Windows Containers**</span></span>

- <span data-ttu-id="30a48-114">**Bereitstellen Ihrer Windows-Container-basierten App auf Azure-VMS**</span><span class="sxs-lookup"><span data-stu-id="30a48-114">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="30a48-115">**Bereitstellen Ihrer Windows-Container-basierten apps in Kubernetes in Azure Container Service**</span><span class="sxs-lookup"><span data-stu-id="30a48-115">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="30a48-116">Exemplarische Vorgehensweise 1: Tour durch die Legacy-apps von eShop</span><span class="sxs-lookup"><span data-stu-id="30a48-116">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="30a48-117">Technische Exemplarische Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="30a48-117">Technical walkthrough availability</span></span>

<span data-ttu-id="30a48-118">Die vollständige technische Exemplarische Vorgehensweise finden Sie im wiki für das eshopmoderniup-GitHub-Repository:</span><span class="sxs-lookup"><span data-stu-id="30a48-118">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="30a48-119">Exemplarische Vorgehensweisen für das eshopmodernisierende wiki</span><span class="sxs-lookup"><span data-stu-id="30a48-119">eShopModernizing wiki walkthroughs</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a><span data-ttu-id="30a48-120">Übersicht</span><span class="sxs-lookup"><span data-stu-id="30a48-120">Overview</span></span>

<span data-ttu-id="30a48-121">In dieser exemplarischen Vorgehensweise können Sie die anfängliche Implementierung von drei veralteten Beispielanwendungen untersuchen.</span><span class="sxs-lookup"><span data-stu-id="30a48-121">In this walkthrough, you can explore the initial implementation of three sample legacy applications.</span></span> <span data-ttu-id="30a48-122">Die ersten beiden Beispiel-Web-Apps verfügen über eine monolithische Architektur und wurden mit klassischem ASP.NET erstellt.</span><span class="sxs-lookup"><span data-stu-id="30a48-122">The first two sample web apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="30a48-123">Eine Anwendung basiert auf ASP.NET 4. x MVC; die zweite Anwendung basiert auf ASP.NET 4. x Web Forms.</span><span class="sxs-lookup"><span data-stu-id="30a48-123">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span>
<span data-ttu-id="30a48-124">Die dritte APP ist eine 3-Ebenen-APP, die sich aus einer WinForms-Client-App und einem serverseitigen [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) -Dienst zusammensetzt.</span><span class="sxs-lookup"><span data-stu-id="30a48-124">The third app is a 3-Tier app composed by a client WinForms app and a server-side [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) service.</span></span>

<span data-ttu-id="30a48-125">Alle diese Anwendungen sind im [eshopmodernisierenden GitHub](https://github.com/dotnet-architecture/eShopModernizing)-Repository verfügbar.</span><span class="sxs-lookup"><span data-stu-id="30a48-125">All these applications are available at the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

### <a name="goals"></a><span data-ttu-id="30a48-126">Ziele</span><span class="sxs-lookup"><span data-stu-id="30a48-126">Goals</span></span>

<span data-ttu-id="30a48-127">Das Hauptziel dieser exemplarischen Vorgehensweise besteht darin, sich mit diesen apps und Ihrem Code und ihrer Konfiguration vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="30a48-127">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="30a48-128">Sie können die apps so konfigurieren, dass Sie mockdaten generieren und verwenden, ohne die SQL-Datenbank zu Testzwecken zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="30a48-128">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="30a48-129">Diese optionale Konfiguration basiert auf einer entkoppelten Abhängigkeit von der Abhängigkeitsinjektion.</span><span class="sxs-lookup"><span data-stu-id="30a48-129">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario-1-aspnet-web-apps"></a><span data-ttu-id="30a48-130">Szenario 1: ASP.net Web-Apps</span><span class="sxs-lookup"><span data-stu-id="30a48-130">Scenario 1: ASP.NET Web apps</span></span>

<span data-ttu-id="30a48-131">Die folgende Abbildung zeigt das einfache Szenario der ursprünglichen ASP.NET-Webanwendungen.</span><span class="sxs-lookup"><span data-stu-id="30a48-131">The figure below shows the simple scenario of the original legacy ASP.NET web applications.</span></span>

![Einfaches Architektur Szenario der ursprünglichen Legacy ASP.NET Webanwendungen](./media/image5-1.png)

<span data-ttu-id="30a48-133">Aus Sicht der Geschäftsdomäne bieten beide apps die gleichen Katalog Verwaltungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="30a48-133">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="30a48-134">Mitglieder des eShop Enterprise-Teams verwenden die APP zum Anzeigen und Bearbeiten des Produktkatalogs.</span><span class="sxs-lookup"><span data-stu-id="30a48-134">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span>

<span data-ttu-id="30a48-135">Die nächste Abbildung zeigt die ersten App-Screenshots.</span><span class="sxs-lookup"><span data-stu-id="30a48-135">The next figure shows the initial app screenshots.</span></span>

![ASP.NET MVC-und ASP.net-Web Forms Anwendungen (vorhandene/ältere Technologien)](./media/image5-2.png)

<span data-ttu-id="30a48-137">Abhängigkeiten in ASP.NET 4. x oder früheren Versionen (entweder für MVC oder für Web Forms) bedeutet, dass diese Anwendungen nicht unter .net Core ausgeführt werden, es sei denn, der Code wird mit ASP.net Core MVC vollständig umgeschrieben.</span><span class="sxs-lookup"><span data-stu-id="30a48-137">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won’t run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span>

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a><span data-ttu-id="30a48-138">Szenario 2: WCF-Dienst und WinForms-Client-app (3-Ebenen-APP)</span><span class="sxs-lookup"><span data-stu-id="30a48-138">Scenario 2: WCF service and WinForms client app (3-Tier app)</span></span>

<span data-ttu-id="30a48-139">Die folgende Abbildung zeigt das einfache Szenario der ursprünglichen 3-Ebenen-Legacy Anwendung.</span><span class="sxs-lookup"><span data-stu-id="30a48-139">The figure below shows the simple scenario of the original 3-Tier legacy application.</span></span>

![Einfaches Architektur Szenario der ursprünglichen veralteten 3-Ebenen-App mit einem WCF-Dienst und einer WinForms-Client-App](./media/image5-1.5.png)

### <a name="benefits"></a><span data-ttu-id="30a48-141">Vorteile</span><span class="sxs-lookup"><span data-stu-id="30a48-141">Benefits</span></span>

<span data-ttu-id="30a48-142">Die Vorteile dieser exemplarischen Vorgehensweise sind einfach: Machen Sie sich mit dem Code und den ersten apps vertraut.</span><span class="sxs-lookup"><span data-stu-id="30a48-142">The benefits of this walkthrough are simple: Just get familiar with the code and initial apps.</span></span>

### <a name="next-steps"></a><span data-ttu-id="30a48-143">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="30a48-143">Next steps</span></span>

<span data-ttu-id="30a48-144">Erkunden Sie diesen Inhalt ausführlicher im GitHub-wiki:</span><span class="sxs-lookup"><span data-stu-id="30a48-144">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="30a48-145">Tour durch die Baseline ASP.NET MVC und Web Forms "Legacy"-Apps</span><span class="sxs-lookup"><span data-stu-id="30a48-145">Tour on the baseline ASP.NET MVC and Web Forms “legacy” apps</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [<span data-ttu-id="30a48-146">Tour durch den WCF-Basis Dienst und die Windows-Legacy-app (3 Ebenen)</span><span class="sxs-lookup"><span data-stu-id="30a48-146">Tour on the baseline WCF service and WinForms (3-Tier) “legacy” app</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="30a48-147">Exemplarische Vorgehensweise 2: Containerisieren vorhandener .NET-Anwendungen mit Windows-Containern</span><span class="sxs-lookup"><span data-stu-id="30a48-147">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="overview"></a><span data-ttu-id="30a48-148">Übersicht</span><span class="sxs-lookup"><span data-stu-id="30a48-148">Overview</span></span>

<span data-ttu-id="30a48-149">Verwenden Sie Windows-Container, um die Bereitstellung vorhandener .NET-Anwendungen, wie z. b. der auf MVC, Web Forms oder WCF, in Produktions-, Entwicklungs-und Testumgebungen zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="30a48-149">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="30a48-150">Ziele</span><span class="sxs-lookup"><span data-stu-id="30a48-150">Goals</span></span>

<span data-ttu-id="30a48-151">Das Ziel dieser exemplarischen Vorgehensweise besteht darin, Ihnen mehrere Optionen für das containerialisieren einer vorhandenen .NET Framework Anwendung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="30a48-151">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="30a48-152">Sie haben folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="30a48-152">You can:</span></span>

- <span data-ttu-id="30a48-153">Containerisieren Ihrer Anwendung mithilfe von [Visual Studio 2017-Tools für docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 oder höhere Versionen).</span><span class="sxs-lookup"><span data-stu-id="30a48-153">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="30a48-154">Containerisieren Sie Ihre Anwendung, indem Sie manuell eine [dockerfile-Datei](https://docs.docker.com/engine/reference/builder/)hinzufügen und dann die [docker-CLI](https://docs.docker.com/engine/reference/commandline/cli/)verwenden.</span><span class="sxs-lookup"><span data-stu-id="30a48-154">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="30a48-155">Containerisieren Sie Ihre Anwendung mithilfe des [Img2Docker](https://github.com/docker/communitytools-image2docker-win) -Tools (Open Source-Tool von Docker).</span><span class="sxs-lookup"><span data-stu-id="30a48-155">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="30a48-156">Diese exemplarische Vorgehensweise konzentriert sich auf den Visual Studio 2017-Tools für docker-Ansatz, aber die anderen beiden Ansätze sind hinsichtlich der Verwendung von dockerfiles ziemlich ähnlich.</span><span class="sxs-lookup"><span data-stu-id="30a48-156">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario-1-containerized-aspnet-web-apps"></a><span data-ttu-id="30a48-157">Szenario 1: Containerisiert ASP.net Web-Apps</span><span class="sxs-lookup"><span data-stu-id="30a48-157">Scenario 1: Containerized ASP.NET web apps</span></span>

<span data-ttu-id="30a48-158">In der folgenden Abbildung ist das Szenario für ältere Web-Apps-Anwendungen in einem Container im Container dargestellt.</span><span class="sxs-lookup"><span data-stu-id="30a48-158">Figure below shows the scenario for containerized eShop legacy web apps applications.</span></span>

![Vereinfachtes Architektur Diagramm von containerisierten ASP.NET-Anwendungen in einer Entwicklungsumgebung](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a><span data-ttu-id="30a48-160">Szenario 2: Containerisierter WCF-Dienst</span><span class="sxs-lookup"><span data-stu-id="30a48-160">Scenario 2: Containerized WCF service</span></span>

<span data-ttu-id="30a48-161">Die folgende Abbildung zeigt das Szenario für eine APP mit drei Ebenen und einem containerisierten WCF-Dienst.</span><span class="sxs-lookup"><span data-stu-id="30a48-161">Figure below shows the scenario for a 3-Tier app with a containerized WCF service.</span></span>

![Vereinfachtes Architektur Diagramm des containerisierten WCF-Dienstanbieter in einer Entwicklungsumgebung](./media/image5-3.5.png)

### <a name="benefits"></a><span data-ttu-id="30a48-163">Vorteile</span><span class="sxs-lookup"><span data-stu-id="30a48-163">Benefits</span></span>

<span data-ttu-id="30a48-164">Die Ausführung einer monolithischen Anwendung in einem Container hat einige Vorteile.</span><span class="sxs-lookup"><span data-stu-id="30a48-164">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="30a48-165">Zuerst erstellen Sie ein Image für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="30a48-165">First, you create an image for the application.</span></span> <span data-ttu-id="30a48-166">Ab diesem Zeitpunkt wird jede Bereitstellung in derselben Umgebung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="30a48-166">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="30a48-167">Jeder Container verwendet die gleiche Betriebssystemversion, die gleiche Version der Abhängigkeiten ist installiert, verwendet dieselbe .NET Framework-Version und wird mit demselben Prozess erstellt.</span><span class="sxs-lookup"><span data-stu-id="30a48-167">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="30a48-168">Im Grunde steuern Sie die Abhängigkeiten Ihrer Anwendung mithilfe eines docker-Images.</span><span class="sxs-lookup"><span data-stu-id="30a48-168">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="30a48-169">Die Abhängigkeiten werden bei der Bereitstellung der Container mit der Anwendung übertragen.</span><span class="sxs-lookup"><span data-stu-id="30a48-169">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="30a48-170">Ein zusätzlicher Vorteil besteht darin, dass Entwickler die Anwendung in der konsistenten Umgebung ausführen können, die von Windows-Containern bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="30a48-170">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="30a48-171">Probleme, die nur mit bestimmten Versionen auftreten, können sofort erkannt werden, anstatt in einer Staging-oder Produktionsumgebung verfügbar zu sein.</span><span class="sxs-lookup"><span data-stu-id="30a48-171">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="30a48-172">Unterschiede in Entwicklungsumgebungen, die von Mitgliedern des Entwicklungsteams verwendet werden, sind weniger wichtig, wenn Anwendungen in Containern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="30a48-172">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="30a48-173">Containerisierte Anwendungen verfügen auch über eine Flatter Scale-Out-Kurve.</span><span class="sxs-lookup"><span data-stu-id="30a48-173">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="30a48-174">Container-apps ermöglichen es Ihnen, mehr Anwendungs-und Dienst Instanzen (basierend auf Containern) auf einem virtuellen Computer oder physischen Computer auf einem virtuellen Computer oder physischen Computer zu haben, verglichen mit regulären Anwendungs Bereitstellungen pro Computer.</span><span class="sxs-lookup"><span data-stu-id="30a48-174">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="30a48-175">Dies bedeutet eine höhere Dichte und weniger erforderliche Ressourcen, insbesondere dann, wenn Sie orchestratoren wie Kubernetes verwenden.</span><span class="sxs-lookup"><span data-stu-id="30a48-175">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes.</span></span>

<span data-ttu-id="30a48-176">Die Containerisierung erfordert in idealen Situationen keine Änderungen am Anwendungscode (C\#).</span><span class="sxs-lookup"><span data-stu-id="30a48-176">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="30a48-177">In den meisten Szenarien benötigen Sie lediglich die Docker-bereitstellungsmetadatendateien (dockerfiles und docker Compose Dateien).</span><span class="sxs-lookup"><span data-stu-id="30a48-177">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="30a48-178">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="30a48-178">Next steps</span></span>

<span data-ttu-id="30a48-179">Erkunden Sie diesen Inhalt ausführlicher im GitHub-wiki:</span><span class="sxs-lookup"><span data-stu-id="30a48-179">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="30a48-180">Containerisieren der .NET Framework-Web-Apps mit Windows-Containern und docker</span><span class="sxs-lookup"><span data-stu-id="30a48-180">How to containerize the .NET Framework web apps with Windows Containers and Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [<span data-ttu-id="30a48-181">Docker-Unterstützung zu einem WCF-Dienst hinzufügen</span><span class="sxs-lookup"><span data-stu-id="30a48-181">Adding Docker Support to a WCF service</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="30a48-182">Exemplarische Vorgehensweise 3: Bereitstellen Ihrer Windows-Container-basierten App auf Azure-VMS</span><span class="sxs-lookup"><span data-stu-id="30a48-182">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="30a48-183">Technische Exemplarische Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="30a48-183">Technical walkthrough availability</span></span>

<span data-ttu-id="30a48-184">Die vollständige technische Exemplarische Vorgehensweise finden Sie im wiki für das eshopmoderniup-GitHub-Repository:<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="30a48-184">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span></span>

### <a name="overview"></a><span data-ttu-id="30a48-185">Übersicht</span><span class="sxs-lookup"><span data-stu-id="30a48-185">Overview</span></span>

<span data-ttu-id="30a48-186">Durch die Bereitstellung auf einem docker-Host auf einem virtuellen Windows Server 2016-Computer (Virtual Machine, VM) in Azure können Sie schnell Entwicklungs-/Test-/Stagingumgebungen einrichten.</span><span class="sxs-lookup"><span data-stu-id="30a48-186">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="30a48-187">Außerdem gibt es einen allgemeinen Ort für Tester oder geschäftliche Benutzer, um die APP zu validieren.</span><span class="sxs-lookup"><span data-stu-id="30a48-187">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="30a48-188">VMs können auch gültige IaaS-Produktionsumgebungen (Infrastructure-as-a-Service) sein.</span><span class="sxs-lookup"><span data-stu-id="30a48-188">VMs also can be valid Infrastructure as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="30a48-189">Ziele</span><span class="sxs-lookup"><span data-stu-id="30a48-189">Goals</span></span>

<span data-ttu-id="30a48-190">Das Ziel dieser exemplarischen Vorgehensweise besteht darin, Ihnen die verschiedenen Alternativen aufzuzeigen, die Sie bei der Bereitstellung von Windows-Containern auf virtuellen Azure-Computern haben, die auf Windows Server 2016 oder höheren Versionen basieren.</span><span class="sxs-lookup"><span data-stu-id="30a48-190">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="30a48-191">Szenarien</span><span class="sxs-lookup"><span data-stu-id="30a48-191">Scenarios</span></span>

<span data-ttu-id="30a48-192">In dieser exemplarischen Vorgehensweise werden verschiedene Szenarien behandelt.</span><span class="sxs-lookup"><span data-stu-id="30a48-192">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="30a48-193">Szenario A: Bereitstellen auf einem virtuellen Azure-Computer über einen Entwickler über die Docker-Engine-Verbindung</span><span class="sxs-lookup"><span data-stu-id="30a48-193">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Bereitstellen auf einem virtuellen Azure-Computer über einen dev-PC über eine docker-Engine-Verbindung](./media/image5-4.png)

<span data-ttu-id="30a48-195">**Abbildung 5-4.**</span><span class="sxs-lookup"><span data-stu-id="30a48-195">**Figure 5-4.**</span></span> <span data-ttu-id="30a48-196">Bereitstellen auf einem virtuellen Azure-Computer über einen dev-PC über eine docker-Engine-Verbindung</span><span class="sxs-lookup"><span data-stu-id="30a48-196">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="30a48-197">Szenario B: Bereitstellen für eine Azure-VM über eine docker-Registrierung</span><span class="sxs-lookup"><span data-stu-id="30a48-197">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Bereitstellen für eine Azure-VM über eine docker-Registrierung](./media/image5-5.png)

<span data-ttu-id="30a48-199">**Abbildung 5-5.**</span><span class="sxs-lookup"><span data-stu-id="30a48-199">**Figure 5-5.**</span></span> <span data-ttu-id="30a48-200">Bereitstellen für eine Azure-VM über eine docker-Registrierung</span><span class="sxs-lookup"><span data-stu-id="30a48-200">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="30a48-201">Szenario C: Bereitstellen auf einem virtuellen Azure-Computer über CI/CD-Pipelines in Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="30a48-201">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

![Bereitstellen auf einem virtuellen Azure-Computer über CI/CD-Pipelines in Azure DevOps Services](./media/image5-6.png)

<span data-ttu-id="30a48-203">**Abbildung 5-6.**</span><span class="sxs-lookup"><span data-stu-id="30a48-203">**Figure 5-6.**</span></span> <span data-ttu-id="30a48-204">Bereitstellen auf einem virtuellen Azure-Computer über CI/CD-Pipelines in Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="30a48-204">Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="30a48-205">Azure-VMs für Windows-Container</span><span class="sxs-lookup"><span data-stu-id="30a48-205">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="30a48-206">Azure-VMs für Windows-Container sind virtuelle Computer, die auf Windows Server 2016, Windows 10 oder höheren Versionen basieren und beide mit der Docker-Engine eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="30a48-206">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="30a48-207">In den meisten Fällen wird Windows Server 2016 auf den Azure-VMS verwendet.</span><span class="sxs-lookup"><span data-stu-id="30a48-207">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="30a48-208">Azure stellt derzeit einen virtuellen Computer namens **Windows Server 2016 mit Containern**bereit.</span><span class="sxs-lookup"><span data-stu-id="30a48-208">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="30a48-209">Mit diesem virtuellen Computer können Sie die neue Windows Server-Container Funktion mit Windows Server Core oder Windows Nano Server testen.</span><span class="sxs-lookup"><span data-stu-id="30a48-209">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="30a48-210">Container Betriebssystem-Images werden installiert, und der virtuelle Computer ist für die Verwendung mit docker bereit.</span><span class="sxs-lookup"><span data-stu-id="30a48-210">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="30a48-211">Vorteile</span><span class="sxs-lookup"><span data-stu-id="30a48-211">Benefits</span></span>

<span data-ttu-id="30a48-212">Obwohl Windows-Container auf lokalen Windows Server 2016-VMS bereitgestellt werden können, erhalten Sie bei der Bereitstellung in Azure eine einfachere Möglichkeit, mit sofort einsatzbereiten Windows Server-Container-VMs zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="30a48-212">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="30a48-213">Außerdem erhalten Sie einen gemeinsamen Online Speicherort, der für Tester verfügbar ist, und die automatische Skalierbarkeit über Azure-VM-Skalierungs Gruppen.</span><span class="sxs-lookup"><span data-stu-id="30a48-213">You also get a common online location that’s accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="30a48-214">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="30a48-214">Next steps</span></span>

<span data-ttu-id="30a48-215">Erkunden Sie diesen Inhalt ausführlicher im GitHub-wiki:</span><span class="sxs-lookup"><span data-stu-id="30a48-215">Explore this content more in-depth on the GitHub wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a><span data-ttu-id="30a48-216">Exemplarische Vorgehensweise 4: Bereitstellen Ihrer Windows-Container-basierten apps in Azure Container Instances (ACI)</span><span class="sxs-lookup"><span data-stu-id="30a48-216">Walkthrough 4: Deploy your Windows Containers-based apps to Azure Container Instances (ACI)</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="30a48-217">Technische Exemplarische Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="30a48-217">Technical walkthrough availability</span></span>

<span data-ttu-id="30a48-218">Die vollständige technische Exemplarische Vorgehensweise finden Sie im wiki für das eshopmoderniup-GitHub-Repository:</span><span class="sxs-lookup"><span data-stu-id="30a48-218">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="30a48-219">[Bereitstellen der apps in ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span><span class="sxs-lookup"><span data-stu-id="30a48-219">[Deploying the Apps to ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span></span>

### <a name="overview"></a><span data-ttu-id="30a48-220">Übersicht</span><span class="sxs-lookup"><span data-stu-id="30a48-220">Overview</span></span>

<span data-ttu-id="30a48-221">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) ist die schnellste Möglichkeit, eine Container Entwicklungs-/Test-/Stagingumgebung zu erhalten, in der Sie einzelne Instanzen von Containern bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="30a48-221">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) is the quickest way to have a Containers dev/test/staging environment where you can deploy single instances of containers.</span></span>

### <a name="goals"></a><span data-ttu-id="30a48-222">Ziele</span><span class="sxs-lookup"><span data-stu-id="30a48-222">Goals</span></span>

<span data-ttu-id="30a48-223">Diese exemplarische Vorgehensweise zeigt Ihnen die wichtigsten Szenarien für die Bereitstellung von Windows-Containern für Azure Container Instances (ACI) und wie Sie eshopmodernisierungsapps in ACI bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="30a48-223">This walkthrough shows you the main scenarios when deploying Windows Containers to Azure Container Instances (ACI) and how you can deploy eShopModernizing Apps into ACI.</span></span>

### <a name="scenarios"></a><span data-ttu-id="30a48-224">Szenarien</span><span class="sxs-lookup"><span data-stu-id="30a48-224">Scenarios</span></span>

<span data-ttu-id="30a48-225">Es können Variationen in Bezug auf die Bereitstellung der eshopmoderniup-apps in ACI auftreten, z. b. das Bereitstellen von nur einer oder aller apps (MVC-APP, WebForms-APP oder WCF-Dienst).</span><span class="sxs-lookup"><span data-stu-id="30a48-225">There can be variations about deploying the eShopModernizing apps into ACI such as deploying just one or all of the apps (MVC app, WebForms app or WCF service).</span></span> <span data-ttu-id="30a48-226">Im folgenden Szenario sehen Sie die ASP.NET MVC-APP und den SQL Server-Container, die beide als Container in ACI (Azure Container Instances) bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="30a48-226">In the following scenario shown below you can see the ASP.NET MVC app plus the SQL Server container both of them deployed as containers into ACI (Azure Container Instances).</span></span>

![Bereitstellen in ACI aus einer Entwicklungsumgebung](./media/image5-3.5.6.png)

### <a name="benefits"></a><span data-ttu-id="30a48-228">Vorteile</span><span class="sxs-lookup"><span data-stu-id="30a48-228">Benefits</span></span>

<span data-ttu-id="30a48-229">Azure Container Instances erleichtert das Erstellen und Verwalten von Docker-Containern in Azure, ohne dass Sie virtuelle Computer bereitstellen oder einen übergeordneten Dienst einführen müssen.</span><span class="sxs-lookup"><span data-stu-id="30a48-229">Azure Container Instances makes it easy to create and manage Docker containers in Azure, without having to provision virtual machines or adopt a higher-level service.</span></span> <span data-ttu-id="30a48-230">Mit ACI können Sie einen Windows-Container in Azure direkt bereitstellen und im Internet mit einem vollständig qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) innerhalb weniger Sekunden verfügbar machen (vorausgesetzt, dass das Windows-Container Image in einer docker-Registrierung wie docker Hub oder Azure Container bereit steht). Registrierung).</span><span class="sxs-lookup"><span data-stu-id="30a48-230">With ACI, you can directly deploy a Windows container in Azure and expose it to the internet with a fully qualified domain name (FQDN) in a matter of seconds (Provided that you have the Windows Container image ready in a Docker registry like Docker Hub or Azure Container Registry).</span></span>

### <a name="considerations"></a><span data-ttu-id="30a48-231">Weitere Überlegungen</span><span class="sxs-lookup"><span data-stu-id="30a48-231">Considerations</span></span>

<span data-ttu-id="30a48-232">Das Bereitstellen von Windows-Containern mit voll .NET Framework/ASP.net oder SQL Server in Azure Container Instances (ACI) ist nicht ganz so schnell wie die Bereitstellung auf einem regulären docker-Host (z. b. Windows Server 2016 mit Windows-Containern), da das docker-Image wird jedes mal heruntergeladen (aus der Docker-Registrierung abgerufen), und die Größe des SQL-Container Images (15,1 GB) und des ASP.NET-Container Images (13,9 GB) sind sehr groß, aber es ist viel günstiger als die Beibehaltung ihres eigenen docker-Hosts (dauerhaft Online). Windows Server 2016 mit Windows-Container-VM in Azure), um einen vollständigen Orchestrator wie Kubernetes in Azure (AKS) zu erwähnen, was andererseits eine gute Wahl für Produktions Bereitstellungen ist.</span><span class="sxs-lookup"><span data-stu-id="30a48-232">Deploying Windows Containers with either full .NET Framework / ASP.NET or SQL Server into Azure Container Instances (ACI) is not quite as fast as deploying to a regular Docker Host (like a Windows Server 2016 with Windows Containers) because the Docker image has to be downloaded (pulled from the Docker registry) every time and the sizes of the SQL container image (15.1 GB) and the ASP.NET container image (13.9 GB) are significantly large, however it is much cheaper than maintaining your own docker host (permanently on-line Windows Server 2016 with Windows Containers VM in Azure) not to mention a whole orchestrator like Kubernetes in Azure (AKS) which is, on the other hand, a great choice for production deployments.</span></span>

<span data-ttu-id="30a48-233">Als Hauptergebnis ist die Verwendung von Azure Container Instances eine sehr überzeugende Option für Entwicklungs-/Testszenarien und für CI/CD-Pipelines.</span><span class="sxs-lookup"><span data-stu-id="30a48-233">As main conclusion, using Azure Container Instances is a very compelling option for Dev/Test scenarios and for CI/CD pipelines.</span></span>

## <a name="next-steps"></a><span data-ttu-id="30a48-234">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="30a48-234">Next steps</span></span>

<span data-ttu-id="30a48-235">Erkunden Sie diesen Inhalt ausführlicher im GitHub-wiki:</span><span class="sxs-lookup"><span data-stu-id="30a48-235">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="30a48-236">Exemplarische Vorgehensweise 5: Bereitstellen Ihrer Windows-Container-basierten apps in Kubernetes in Azure Container Service</span><span class="sxs-lookup"><span data-stu-id="30a48-236">Walkthrough 5: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="30a48-237">Technische Exemplarische Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="30a48-237">Technical walkthrough availability</span></span>

<span data-ttu-id="30a48-238">Die vollständige technische Exemplarische Vorgehensweise finden Sie im wiki für das eshopmoderniup-GitHub-Repository:</span><span class="sxs-lookup"><span data-stu-id="30a48-238">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

### <a name="overview"></a><span data-ttu-id="30a48-239">Übersicht</span><span class="sxs-lookup"><span data-stu-id="30a48-239">Overview</span></span>

<span data-ttu-id="30a48-240">Eine Anwendung, die auf Windows-Containern basiert, muss schnell Plattformen verwenden und sich noch weiter von virtuellen IaaS-Computern verlagern.</span><span class="sxs-lookup"><span data-stu-id="30a48-240">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="30a48-241">Dies ist erforderlich, um auf einfache Weise eine hohe Skalierbarkeit und eine bessere automatisierte Skalierbarkeit zu erreichen und eine bedeutende Verbesserung bei automatisierten bereit Stellungen und Versionsverwaltung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="30a48-241">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="30a48-242">Diese Ziele können Sie mithilfe der Orchestrator- [Kubernetes](https://kubernetes.io/)erreichen, die in [Azure Container Services](https://azure.microsoft.com/services/container-service/)verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="30a48-242">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="30a48-243">Ziele</span><span class="sxs-lookup"><span data-stu-id="30a48-243">Goals</span></span>

<span data-ttu-id="30a48-244">In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie in Azure Container Service eine Windows-Container – basierte Anwendung in Kubernetes (auch als *K8s*bezeichnet) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="30a48-244">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="30a48-245">Die Bereitstellung von Grund auf Kubernetes ist ein zweistufiger Prozess:</span><span class="sxs-lookup"><span data-stu-id="30a48-245">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1. <span data-ttu-id="30a48-246">Stellen Sie einen Kubernetes-Cluster für die Azure Container Service bereit.</span><span class="sxs-lookup"><span data-stu-id="30a48-246">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2. <span data-ttu-id="30a48-247">Stellen Sie die Anwendung und zugehörige Ressourcen für den Kubernetes-Cluster bereit.</span><span class="sxs-lookup"><span data-stu-id="30a48-247">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="30a48-248">Szenarien</span><span class="sxs-lookup"><span data-stu-id="30a48-248">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="30a48-249">Szenario A: Direktes bereitstellen in einem Kubernetes-Cluster aus einer Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="30a48-249">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![Direktes bereitstellen in einem Kubernetes-Cluster aus einer Entwicklungsumgebung](./media/image5-7.png)

<span data-ttu-id="30a48-251">**Abbildung 5-7.**</span><span class="sxs-lookup"><span data-stu-id="30a48-251">**Figure 5-7.**</span></span> <span data-ttu-id="30a48-252">Direktes bereitstellen in einem Kubernetes-Cluster aus einer Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="30a48-252">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="30a48-253">Szenario B: Bereitstellen in einem Kubernetes-Cluster über CI/CD-Pipelines in Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="30a48-253">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

![Bereitstellen in einem Kubernetes-Cluster über CI/CD-Pipelines in Azure DevOps Services](./media/image5-8.png)

<span data-ttu-id="30a48-255">**Abbildung 5-8.**</span><span class="sxs-lookup"><span data-stu-id="30a48-255">**Figure 5-8.**</span></span> <span data-ttu-id="30a48-256">Bereitstellen in einem Kubernetes-Cluster über CI/CD-Pipelines in Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="30a48-256">Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="benefits"></a><span data-ttu-id="30a48-257">Vorteile</span><span class="sxs-lookup"><span data-stu-id="30a48-257">Benefits</span></span>

<span data-ttu-id="30a48-258">Die Bereitstellung in einem Cluster in Kubernetes bietet viele Vorteile.</span><span class="sxs-lookup"><span data-stu-id="30a48-258">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="30a48-259">Der größte Vorteil besteht darin, dass Sie eine Produktions bereite Umgebung erhalten, in der Sie die Anwendung basierend auf der Anzahl der zu verwendenden Container Instanzen (innere Skalierbarkeit in den vorhandenen Knoten) und basierend auf der Anzahl der Knoten oder VMS im Cluster horizontal hochskalieren können. Globale Skalierbarkeit des Clusters).</span><span class="sxs-lookup"><span data-stu-id="30a48-259">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="30a48-260">Azure Container Service optimiert beliebte Open Source-Tools und-Technologien speziell für Azure.</span><span class="sxs-lookup"><span data-stu-id="30a48-260">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="30a48-261">Sie erhalten eine offene Lösung, die Portabilität sowohl für Ihre Container als auch für Ihre Anwendungskonfiguration bietet.</span><span class="sxs-lookup"><span data-stu-id="30a48-261">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="30a48-262">Sie wählen die Größe, die Anzahl der Hosts und Orchestrator-Tools aus. der Container Dienst verarbeitet alles andere.</span><span class="sxs-lookup"><span data-stu-id="30a48-262">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="30a48-263">Mit Kubernetes können sich Entwickler über physische und virtuelle Computer nachdenken und eine Container zentrierte Infrastruktur planen, die die folgenden Funktionen unter anderem ermöglicht:</span><span class="sxs-lookup"><span data-stu-id="30a48-263">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="30a48-264">Anwendungen, die auf mehreren Containern basieren</span><span class="sxs-lookup"><span data-stu-id="30a48-264">Applications based on multiple containers</span></span>

- <span data-ttu-id="30a48-265">Replizieren von Container Instanzen und horizontaler automatischer Skalierung</span><span class="sxs-lookup"><span data-stu-id="30a48-265">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="30a48-266">Benennen und ermitteln (z. b. internes DNS)</span><span class="sxs-lookup"><span data-stu-id="30a48-266">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="30a48-267">Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="30a48-267">Balancing loads</span></span>

- <span data-ttu-id="30a48-268">Parallele Updates</span><span class="sxs-lookup"><span data-stu-id="30a48-268">Rolling updates</span></span>

- <span data-ttu-id="30a48-269">Verteilen von Geheimnissen</span><span class="sxs-lookup"><span data-stu-id="30a48-269">Distributing secrets</span></span>

- <span data-ttu-id="30a48-270">Anwendungs Integritätsprüfungen</span><span class="sxs-lookup"><span data-stu-id="30a48-270">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="30a48-271">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="30a48-271">Next steps</span></span>

<span data-ttu-id="30a48-272">Erkunden Sie diesen Inhalt ausführlicher im GitHub-wiki:<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="30a48-272">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)></span></span>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-app-service-for-containers"></a><span data-ttu-id="30a48-273">Exemplarische Vorgehensweise 6: Bereitstellen von Windows-Container-basierten Apps für die Azure App Service für Container</span><span class="sxs-lookup"><span data-stu-id="30a48-273">Walkthrough 6: Deploy your Windows Containers-based apps to Azure App Service for Containers</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="30a48-274">Technische Exemplarische Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="30a48-274">Technical walkthrough availability</span></span>

<span data-ttu-id="30a48-275">Die vollständige technische Exemplarische Vorgehensweise finden Sie im wiki für das eshopmoderniup-GitHub-Repository:</span><span class="sxs-lookup"><span data-stu-id="30a48-275">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

### <a name="overview"></a><span data-ttu-id="30a48-276">Übersicht</span><span class="sxs-lookup"><span data-stu-id="30a48-276">Overview</span></span>

<span data-ttu-id="30a48-277">Eine einfache containerisierte Anwendung, die Windows-Container verwendet Azure App Service, kann problemlos für Container bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="30a48-277">A simple containerized application using Windows Containers can easily be deployed to Azure App Service for Containers.</span></span> <span data-ttu-id="30a48-278">Dies ist die empfohlene Vorgehensweise für die meisten Windows-Container basierten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="30a48-278">This is the recommended approach for most Windows Container-based applications.</span></span>

### <a name="goals"></a><span data-ttu-id="30a48-279">Ziele</span><span class="sxs-lookup"><span data-stu-id="30a48-279">Goals</span></span>

<span data-ttu-id="30a48-280">In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie eine Windows Container – basierte Anwendung für die Azure App Service für Container aus einer Registrierung (docker Hub oder Azure Container Registry) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="30a48-280">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Azure App Service for Containers from a registry (Docker Hub or Azure Container Registry).</span></span>

### <a name="scenario"></a><span data-ttu-id="30a48-281">Szenario</span><span class="sxs-lookup"><span data-stu-id="30a48-281">Scenario</span></span>

![Bereitstellen einer Windows Container-basierten App für Azure App Service für Container](./media/image5-11.png)

### <a name="benefits"></a><span data-ttu-id="30a48-283">Vorteile</span><span class="sxs-lookup"><span data-stu-id="30a48-283">Benefits</span></span>

<span data-ttu-id="30a48-284">Die Bereitstellung in Azure App Service für Container bietet die Vorteile von Containern in Kombination mit den PaaS-Vorteilen von Azure App Service.</span><span class="sxs-lookup"><span data-stu-id="30a48-284">Deploying to Azure App Service for Containers offers the benefits of containers paired with the PaaS benefits of Azure App Service.</span></span> <span data-ttu-id="30a48-285">Der APP Service kann problemlos vertikal und horizontal skaliert werden und kann so konfiguriert werden, dass er eine automatische Skalierung durch findet, um geänderte Anforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="30a48-285">The app service can easily be scaled both vertically and horizontally, and can be configured to autoscale to meet changing demands.</span></span> <span data-ttu-id="30a48-286">Updates können ohne Ausfallzeiten ausgeführt werden, und die Konfiguration von Continuous Deployment aus einer Registrierung ist ebenfalls leicht zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="30a48-286">Updates can be performed with zero downtime and configuration of continuous deployment from a registry is easily configured as well.</span></span>

## <a name="next-steps"></a><span data-ttu-id="30a48-287">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="30a48-287">Next steps</span></span>

<span data-ttu-id="30a48-288">Erkunden Sie diesen Inhalt ausführlicher im GitHub-wiki:<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service></span><span class="sxs-lookup"><span data-stu-id="30a48-288">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service></span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="30a48-289">[Zurück](modernize-existing-apps-to-cloud-optimized/migrate-to-hybrid-cloud-scenarios.md)
> [Weiter](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="30a48-289">[Previous](modernize-existing-apps-to-cloud-optimized/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span> <!-- Next Chapter -->
