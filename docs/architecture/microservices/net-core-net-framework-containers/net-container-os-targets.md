---
title: Mit .NET-Containern angezieltes Betriebssystem
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Mit .NET-Containern angezieltes Betriebssystem
ms.date: 01/07/2019
ms.openlocfilehash: 7380889374e69ca4d3c981a401af703c19263de5
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71039692"
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="9f3a4-103">Mit .NET-Containern angezieltes Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="9f3a4-103">What OS to target with .NET containers</span></span>

<span data-ttu-id="9f3a4-104">Durch die Vielzahl der von Docker unterstützten Betriebssysteme und die Unterschiede zwischen .NET Framework und .NET Core sollten Sie abhängig von dem Framework, das Sie verwenden, ein bestimmtes Betriebssystem und bestimmte Versionen anzielen.</span><span class="sxs-lookup"><span data-stu-id="9f3a4-104">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span>

<span data-ttu-id="9f3a4-105">Für Windows können Sie Windows Server Core oder Windows Nano Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f3a4-105">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="9f3a4-106">Diese Windows-Versionen bieten unterschiedliche Eigenschaften (IIS in Windows Server Core im Vergleich zu einem selbstgehosteten Webserver wie Kestrel in Nano Server), die jeweils für .NET Framework oder .NET Core erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="9f3a4-106">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span>

<span data-ttu-id="9f3a4-107">Für Linux sind mehrere Distributionen (z.B. Debian) verfügbar und werden in offiziellen .NET Docker-Images unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9f3a4-107">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="9f3a4-108">In Abbildung 3-1 wird die mögliche Betriebssystemversion in Abhängigkeit vom verwendeten .NET Framework dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9f3a4-108">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![Bei der Bereitstellung von .NET Framework-Legacyanwendungen muss Windows Server Core angezielt werden, das bei Kompatibilität mit Legacyanwendungen und IIS ein größeres Image aufweist.](./media/image1.png)

<span data-ttu-id="9f3a4-113">**Abbildung 3-1.**</span><span class="sxs-lookup"><span data-stu-id="9f3a4-113">**Figure 3-1.**</span></span> <span data-ttu-id="9f3a4-114">In Abhängigkeit der Version von .NET Framework anzuzielende Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="9f3a4-114">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="9f3a4-115">Sie können ebenfalls Ihr eigenes Docker-Image erstellen, wenn Sie eine andere Linux-Distribution verwenden oder wenn Sie ein Image mit nicht von Microsoft bereitgestellten Versionen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="9f3a4-115">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="9f3a4-116">Sie könnten beispielsweise ein Image erstellen, bei dem ASP.NET Core unter dem herkömmlichen .NET Framework und Windows Server Core ausgeführt wird. Dabei handelt es sich um ein für Docker ungewöhnliches Szenario.</span><span class="sxs-lookup"><span data-stu-id="9f3a4-116">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

<span data-ttu-id="9f3a4-117">Wenn Sie den Namen des Images zu Ihrer Dockerfile-Datei hinzufügen, können Sie das Betriebssystem und die Version wie in den folgenden Beispielen dargestellt in Abhängigkeit vom verwendeten Tag auswählen:</span><span class="sxs-lookup"><span data-stu-id="9f3a4-117">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

| <span data-ttu-id="9f3a4-118">Bild</span><span class="sxs-lookup"><span data-stu-id="9f3a4-118">Image</span></span> | <span data-ttu-id="9f3a4-119">Kommentare</span><span class="sxs-lookup"><span data-stu-id="9f3a4-119">Comments</span></span> |
|-------|----------|
| <span data-ttu-id="9f3a4-120">mcr.microsoft.com/dotnet/core/runtime:2.2</span><span class="sxs-lookup"><span data-stu-id="9f3a4-120">mcr.microsoft.com/dotnet/core/runtime:2.2</span></span> | <span data-ttu-id="9f3a4-121">Mehrere .NET Core 2.2-Architekturen: Unterstützt Linux und Windows Nano Server, abhängig vom Docker-Host.</span><span class="sxs-lookup"><span data-stu-id="9f3a4-121">.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span> |
| <span data-ttu-id="9f3a4-122">mcr.microsoft.com/dotnet/core/aspnet:2.2</span><span class="sxs-lookup"><span data-stu-id="9f3a4-122">mcr.microsoft.com/dotnet/core/aspnet:2.2</span></span> | <span data-ttu-id="9f3a4-123">Mehrere ASP.NET Core 2.2-Architekturen: Unterstützt Linux und Windows Nano Server, abhängig vom Docker-Host.</span><span class="sxs-lookup"><span data-stu-id="9f3a4-123">ASP.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span> <br/> <span data-ttu-id="9f3a4-124">Das aspnetcore-Image enthält einige Optimierungen für ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="9f3a4-124">The aspnetcore image has a few optimizations for ASP.NET Core.</span></span> |
| <span data-ttu-id="9f3a4-125">mcr.microsoft.com/dotnet/core/aspnet:2.2-alpine</span><span class="sxs-lookup"><span data-stu-id="9f3a4-125">mcr.microsoft.com/dotnet/core/aspnet:2.2-alpine</span></span> | <span data-ttu-id="9f3a4-126">Unter Linux Alpine-Distribution nur .NET Core 2.2-Runtime</span><span class="sxs-lookup"><span data-stu-id="9f3a4-126">.NET Core 2.2 runtime-only on Linux Alpine distro</span></span> |
| <span data-ttu-id="9f3a4-127">mcr.microsoft.com/dotnet/core/aspnet:2.2-nanoserver-1803</span><span class="sxs-lookup"><span data-stu-id="9f3a4-127">mcr.microsoft.com/dotnet/core/aspnet:2.2-nanoserver-1803</span></span> | <span data-ttu-id="9f3a4-128">Unter Windows Nano Server (Windows Server, Version 1803) nur .NET Core 2.2-Runtime</span><span class="sxs-lookup"><span data-stu-id="9f3a4-128">.NET Core 2.2 runtime-only on Windows Nano Server (Windows Server version 1803)</span></span> |

> [!div class="step-by-step"]
> <span data-ttu-id="9f3a4-129">[Zurück](container-framework-choice-factors.md)
> [Weiter](official-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="9f3a4-129">[Previous](container-framework-choice-factors.md)
[Next](official-net-docker-images.md)</span></span>
