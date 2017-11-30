---
title: Welche Ziel mit .NET Container des Betriebssystems
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Welche Ziel mit .NET Container des Betriebssystems"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 828ccb5e7a76f9419e80793b6cb3a6ba24f358cf
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="8ebd9-104">Welche Ziel mit .NET Container des Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="8ebd9-104">What OS to target with .NET containers</span></span>

<span data-ttu-id="8ebd9-105">Angesichts die Vielfalt von Docker und die Unterschiede zwischen .NET Framework und .NET Core unterstützten Betriebssysteme, sollten Sie auf einem bestimmten Betriebssystem und bestimmten Versionen, je nachdem das Framework verwendeten abzielen.</span><span class="sxs-lookup"><span data-stu-id="8ebd9-105">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span> 

<span data-ttu-id="8ebd9-106">Für Windows können Sie Windows Server Core oder Windows Nano Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ebd9-106">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="8ebd9-107">Diese Windows-Versionen bieten unterschiedliche Eigenschaften (IIS unter Windows Server Core im Vergleich zu einem selbst gehosteten Webserver wie Kestrel in Nano Server), die jeweils möglicherweise von .NET Framework oder .NET Core benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="8ebd9-107">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span> 

<span data-ttu-id="8ebd9-108">Für Linux sind-Distributionen mehrere verfügbar und in der offiziellen .NET Docker-Images (z. B. Debian) unterstützten.</span><span class="sxs-lookup"><span data-stu-id="8ebd9-108">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="8ebd9-109">In Abbildung 3 – 1 sehen Sie die mögliche Version des Betriebssystems abhängig von der .NET Framework verwendet.</span><span class="sxs-lookup"><span data-stu-id="8ebd9-109">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![](./media/image1.png)

<span data-ttu-id="8ebd9-110">**Abbildung 3 minus 1.**</span><span class="sxs-lookup"><span data-stu-id="8ebd9-110">**Figure 3-1.**</span></span> <span data-ttu-id="8ebd9-111">Abhängig von Versionen von .NET Framework als Ziel-Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="8ebd9-111">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="8ebd9-112">Sie können auch Ihr eigenes Image von Docker in Fällen erstellen, eine andere Linux-Distribution verwendet werden soll, oder ein Bild mit Versionen, die nicht von Microsoft bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8ebd9-112">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="8ebd9-113">Sie können z. B. ein Image erstellen, mit ASP.NET Core auf herkömmliche .NET Framework und Windows Server Core eine nicht damit üblichen Szenario für Docker ist ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8ebd9-113">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

<span data-ttu-id="8ebd9-114">Wenn Sie die Dockerfile-Datei den Namen des Abbilds hinzugefügt haben, können Sie auswählen, das Betriebssystem und Version je nach Tag, das Sie, das wie in den folgenden Beispielen verwenden:</span><span class="sxs-lookup"><span data-stu-id="8ebd9-114">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

-   <span data-ttu-id="8ebd9-115">Microsoft /**Dotnet:2.0.0-Runtime-Jessie**</span><span class="sxs-lookup"><span data-stu-id="8ebd9-115">microsoft/**dotnet:2.0.0-runtime-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux

-   <span data-ttu-id="8ebd9-116">Microsoft /**Dotnet:2.0.0-Runtime-Nanoserver-1709**</span><span class="sxs-lookup"><span data-stu-id="8ebd9-116">microsoft/**dotnet:2.0.0-runtime-nanoserver-1709**</span></span> 

        .NET Core 2.0 runtime-only on Windows Nano Server (Windows Server 2016 Fall Creators Update version 1709)

-   <span data-ttu-id="8ebd9-117">Microsoft /**Aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="8ebd9-117">microsoft/**aspnetcore:2.0**</span></span>
    
        .NET Core 2.0 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.
        The aspnetcore image has a few optimizations for ASP.NET Core. 





>[!div class="step-by-step"]
<span data-ttu-id="8ebd9-118">[Vorherigen] (Container-Framework-Choice-factors.md) [weiter] (offiziellen-Net-Docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="8ebd9-118">[Previous] (container-framework-choice-factors.md) [Next] (official-net-docker-images.md)</span></span>
