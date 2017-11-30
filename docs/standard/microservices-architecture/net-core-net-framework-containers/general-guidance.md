---
title: Allgemeine Richtlinien
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Allgemeine Richtlinien"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 22dea926e77079e4f543934613ced13a28b2dae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="general-guidance"></a><span data-ttu-id="19183-104">Allgemeine Richtlinien</span><span class="sxs-lookup"><span data-stu-id="19183-104">General guidance</span></span>

<span data-ttu-id="19183-105">Dieser Abschnitt enthält eine Zusammenfassung der wann .NET Core oder .NET Framework auswählen.</span><span class="sxs-lookup"><span data-stu-id="19183-105">This section provides a summary of when to choose .NET Core or .NET Framework.</span></span> <span data-ttu-id="19183-106">Wir bieten ausführliche Informationen zu diesen Optionen in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="19183-106">We provide more details about these choices in the sections that follow.</span></span>

<span data-ttu-id="19183-107">Verwenden Sie .NET Core, Linux- oder Windows-Container für die Datenvolumes Docker-Server-Anwendung beim:</span><span class="sxs-lookup"><span data-stu-id="19183-107">You should use .NET Core, with Linux or Windows Containers, for your containerized Docker server application when:</span></span>

-   <span data-ttu-id="19183-108">Es bestehen plattformübergreifende Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="19183-108">You have cross-platform needs.</span></span> <span data-ttu-id="19183-109">Sie möchten z. B. Linux und Windows-Container verwenden.</span><span class="sxs-lookup"><span data-stu-id="19183-109">For example, you want to use both Linux and Windows Containers.</span></span>

-   <span data-ttu-id="19183-110">Ihre Anwendungsarchitektur basiert auf Microservices.</span><span class="sxs-lookup"><span data-stu-id="19183-110">Your application architecture is based on microservices.</span></span>

-   <span data-ttu-id="19183-111">Sie müssen Containern schnell starten und einen geringen Ressourcenbedarf pro höhere Dichte zu erreichen oder die weitere Container pro Einheit Hardware anstreben, um die Kosten zu senken.</span><span class="sxs-lookup"><span data-stu-id="19183-111">You need to start containers fast and want a small footprint per container to achieve better density or more containers per hardware unit in order to lower your costs.</span></span>

<span data-ttu-id="19183-112">Kurz gesagt, sollten Sie bei der Erstellung neuer .NET Sammelartikeleinheit .NET Core als Standardwahl berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="19183-112">In short, when you create new containerized .NET applications, you should consider .NET Core as the default choice.</span></span> <span data-ttu-id="19183-113">Er weist viele Vorteile und mit dem Container Philosophie und den Stil der Arbeit am besten entspricht.</span><span class="sxs-lookup"><span data-stu-id="19183-113">It has many benefits and fits best with the containers philosophy and style of working.</span></span>

<span data-ttu-id="19183-114">Ein weiterer Vorteil der Verwendung von .NET Core ist, dass Sie nebeneinander .NET Versionen für Anwendungen, in dem gleichen Computer ausführen können.</span><span class="sxs-lookup"><span data-stu-id="19183-114">An additional benefit of using .NET Core is that you can run side by side .NET versions for applications within the same machine.</span></span> <span data-ttu-id="19183-115">Dieser Vorteil ist wichtiger für Server oder virtuelle Computer, die nicht-Container verwenden, da der Container die Versionen von .NET isolieren, die die app benötigt.</span><span class="sxs-lookup"><span data-stu-id="19183-115">This benefit is more important for servers or VMs that do not use containers, because containers isolate the versions of .NET that the app needs.</span></span> <span data-ttu-id="19183-116">(Solange sie mit dem zugrunde liegenden Betriebssystem kompatibel sind.)</span><span class="sxs-lookup"><span data-stu-id="19183-116">(As long as they are compatible with the underlying OS.)</span></span>

<span data-ttu-id="19183-117">Sollten Sie .NET Framework, mit Windows-Container verwenden, für die Datenvolumes Docker-Server-Anwendung beim:</span><span class="sxs-lookup"><span data-stu-id="19183-117">You should use .NET Framework, with Windows Containers, for your containerized Docker server application when:</span></span>

-   <span data-ttu-id="19183-118">Die Anwendung derzeit verwendet .NET Framework und weist starke Abhängigkeiten von Windows.</span><span class="sxs-lookup"><span data-stu-id="19183-118">Your application currently uses .NET Framework and has strong dependencies on Windows.</span></span>

-   <span data-ttu-id="19183-119">Sie müssen Windows-APIs verwenden, die von .NET Core nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="19183-119">You need to use Windows APIs that are not supported by .NET Core.</span></span>

-   <span data-ttu-id="19183-120">Sie müssen .NET Bibliotheken von Drittanbietern oder NuGet-Pakete, die nicht für die .NET Core verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="19183-120">You need to use third-party .NET libraries or NuGet packages that are not available for .NET Core.</span></span>

<span data-ttu-id="19183-121">Mithilfe von .NET Framework auf Docker kann Ihre bereitstellungsumgebung verbessern, indem Sie Bereitstellungsprobleme minimieren.</span><span class="sxs-lookup"><span data-stu-id="19183-121">Using .NET Framework on Docker can improve your deployment experiences by minimizing deployment issues.</span></span> <span data-ttu-id="19183-122">Dies [ *"lift- and -shift-Szenario* ](https://aka.ms/liftandshiftwithcontainersebook) ist wichtig für ältere Anwendungen, die ursprünglich mit herkömmlichen .NET Framework entwickelt wurden, wie ASP.NET Web Forms, MVC-apps oder WCF (web containerizing Windows Communication Foundation)-Dienste.</span><span class="sxs-lookup"><span data-stu-id="19183-122">This [*"lift and shift" scenario*](https://aka.ms/liftandshiftwithcontainersebook) is important for containerizing legacy applications that were originally developed with the traditional .NET Framework, like ASP.NET WebForms, MVC web apps or WCF (Windows Communication Foundation) services.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="19183-123">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="19183-123">Additional resources</span></span>

-   <span data-ttu-id="19183-124">**e-Book: Aktualisieren von vorhandenen .NET Framework-Anwendungen mit Azure und Windows-Containern**
    [*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)</span><span class="sxs-lookup"><span data-stu-id="19183-124">**e-book: Modernize existing .NET Framework applications with Azure and Windows Containers**
[*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)</span></span>

-   <span data-ttu-id="19183-125">**Beispiel-apps: Modernisierung legacy ASP.NET Web-Apps mithilfe von Windows-Containern**
    [*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)</span><span class="sxs-lookup"><span data-stu-id="19183-125">**Sample apps: Modernization of legacy ASP.NET web apps by using Windows Containers**
[*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="19183-126">[Vorherigen] (index.md) [weiter] (Net-Core-Container-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="19183-126">[Previous] (index.md) [Next] (net-core-container-scenarios.md)</span></span>
