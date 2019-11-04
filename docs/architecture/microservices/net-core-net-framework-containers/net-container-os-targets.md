---
title: Mit .NET-Containern angezieltes Betriebssystem
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Mit .NET-Containern angezieltes Betriebssystem
ms.date: 01/07/2019
ms.openlocfilehash: 8bcfa0212f84c575a63f76e05edec1e511cadc36
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72772006"
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="219b0-103">Mit .NET-Containern angezieltes Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="219b0-103">What OS to target with .NET containers</span></span>

<span data-ttu-id="219b0-104">Durch die Vielzahl der von Docker unterstützten Betriebssysteme und die Unterschiede zwischen .NET Framework und .NET Core sollten Sie abhängig von dem Framework, das Sie verwenden, ein bestimmtes Betriebssystem und bestimmte Versionen anzielen.</span><span class="sxs-lookup"><span data-stu-id="219b0-104">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span>

<span data-ttu-id="219b0-105">Für Windows können Sie Windows Server Core oder Windows Nano Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="219b0-105">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="219b0-106">Diese Windows-Versionen bieten unterschiedliche Eigenschaften (IIS in Windows Server Core im Vergleich zu einem selbstgehosteten Webserver wie Kestrel in Nano Server), die jeweils für .NET Framework oder .NET Core erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="219b0-106">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span>

<span data-ttu-id="219b0-107">Für Linux sind mehrere Distributionen (z.B. Debian) verfügbar und werden in offiziellen .NET Docker-Images unterstützt.</span><span class="sxs-lookup"><span data-stu-id="219b0-107">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="219b0-108">In Abbildung 3-1 wird die mögliche Betriebssystemversion in Abhängigkeit vom verwendeten .NET Framework dargestellt.</span><span class="sxs-lookup"><span data-stu-id="219b0-108">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![Bei der Bereitstellung von .NET Framework-Legacyanwendungen muss Windows Server Core angezielt werden, das bei Kompatibilität mit Legacyanwendungen und IIS ein größeres Image aufweist.](./media/image1.png)

<span data-ttu-id="219b0-113">**Abbildung 3-1.**</span><span class="sxs-lookup"><span data-stu-id="219b0-113">**Figure 3-1.**</span></span> <span data-ttu-id="219b0-114">In Abhängigkeit der Version von .NET Framework anzuzielende Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="219b0-114">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="219b0-115">Sie können ebenfalls Ihr eigenes Docker-Image erstellen, wenn Sie eine andere Linux-Distribution verwenden oder wenn Sie ein Image mit nicht von Microsoft bereitgestellten Versionen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="219b0-115">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="219b0-116">Sie könnten beispielsweise ein Image erstellen, bei dem ASP.NET Core unter dem herkömmlichen .NET Framework und Windows Server Core ausgeführt wird. Dabei handelt es sich um ein für Docker ungewöhnliches Szenario.</span><span class="sxs-lookup"><span data-stu-id="219b0-116">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="219b0-117">Wenn Sie Windows Server Core-Images verwenden, stellen Sie möglicherweise fest, dass im Vergleich zu vollständigen Windows-Images einige DLLs fehlen.</span><span class="sxs-lookup"><span data-stu-id="219b0-117">When using Windows Server Core images, you might find that some DLLs are missing, when compared to full Windows images.</span></span> <span data-ttu-id="219b0-118">Sie können dieses Problem möglicherweise beheben, indem Sie ein benutzerdefiniertes Server Core-Image erstellen und die fehlenden Dateien zum Zeitpunkt der Imageerstellung hinzufügen, wie in diesem [GitHub-Kommentar](https://github.com/microsoft/dotnet-framework-docker/issues/299#issuecomment-511537448) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="219b0-118">You might be able to solve this problem by creating a custom Server Core image, adding the missing files at image build time, as mentioned in this [GitHub comment](https://github.com/microsoft/dotnet-framework-docker/issues/299#issuecomment-511537448).</span></span>

<span data-ttu-id="219b0-119">Wenn Sie den Namen des Images zu Ihrer Dockerfile-Datei hinzufügen, können Sie das Betriebssystem und die Version wie in den folgenden Beispielen dargestellt in Abhängigkeit vom verwendeten Tag auswählen:</span><span class="sxs-lookup"><span data-stu-id="219b0-119">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

| <span data-ttu-id="219b0-120">Bild</span><span class="sxs-lookup"><span data-stu-id="219b0-120">Image</span></span> | <span data-ttu-id="219b0-121">Kommentare</span><span class="sxs-lookup"><span data-stu-id="219b0-121">Comments</span></span> |
|-------|----------|
| <span data-ttu-id="219b0-122">mcr.microsoft.com/dotnet/core/runtime:2.2</span><span class="sxs-lookup"><span data-stu-id="219b0-122">mcr.microsoft.com/dotnet/core/runtime:2.2</span></span> | <span data-ttu-id="219b0-123">Mehrere .NET Core 2.2-Architekturen: Unterstützt Linux und Windows Nano Server, abhängig vom Docker-Host.</span><span class="sxs-lookup"><span data-stu-id="219b0-123">.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span> |
| <span data-ttu-id="219b0-124">mcr.microsoft.com/dotnet/core/aspnet:2.2</span><span class="sxs-lookup"><span data-stu-id="219b0-124">mcr.microsoft.com/dotnet/core/aspnet:2.2</span></span> | <span data-ttu-id="219b0-125">Mehrere ASP.NET Core 2.2-Architekturen: Unterstützt Linux und Windows Nano Server, abhängig vom Docker-Host.</span><span class="sxs-lookup"><span data-stu-id="219b0-125">ASP.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span> <br/> <span data-ttu-id="219b0-126">Das aspnetcore-Image enthält einige Optimierungen für ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="219b0-126">The aspnetcore image has a few optimizations for ASP.NET Core.</span></span> |
| <span data-ttu-id="219b0-127">mcr.microsoft.com/dotnet/core/aspnet:2.2-alpine</span><span class="sxs-lookup"><span data-stu-id="219b0-127">mcr.microsoft.com/dotnet/core/aspnet:2.2-alpine</span></span> | <span data-ttu-id="219b0-128">Unter Linux Alpine-Distribution nur .NET Core 2.2-Runtime</span><span class="sxs-lookup"><span data-stu-id="219b0-128">.NET Core 2.2 runtime-only on Linux Alpine distro</span></span> |
| <span data-ttu-id="219b0-129">mcr.microsoft.com/dotnet/core/aspnet:2.2-nanoserver-1803</span><span class="sxs-lookup"><span data-stu-id="219b0-129">mcr.microsoft.com/dotnet/core/aspnet:2.2-nanoserver-1803</span></span> | <span data-ttu-id="219b0-130">Unter Windows Nano Server (Windows Server, Version 1803) nur .NET Core 2.2-Runtime</span><span class="sxs-lookup"><span data-stu-id="219b0-130">.NET Core 2.2 runtime-only on Windows Nano Server (Windows Server version 1803)</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="219b0-131">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="219b0-131">Additional resources</span></span>

- <span data-ttu-id="219b0-132">**BitmapDecoder schlägt fehl, weil „WindowsCodecsExt.dll“ fehlt (GitHub-Issue)**</span><span class="sxs-lookup"><span data-stu-id="219b0-132">**BitmapDecoder fails due to missing WindowsCodecsExt.dll (GitHub issue)**</span></span>  
  <https://github.com/microsoft/dotnet-framework-docker/issues/299>

> [!div class="step-by-step"]
> <span data-ttu-id="219b0-133">[Zurück](container-framework-choice-factors.md)
> [Weiter](official-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="219b0-133">[Previous](container-framework-choice-factors.md)
[Next](official-net-docker-images.md)</span></span>
