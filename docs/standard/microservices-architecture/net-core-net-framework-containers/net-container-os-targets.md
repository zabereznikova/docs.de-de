---
title: Mit .NET-Containern angezieltes Betriebssystem
description: ".NET-Microservicesarchitektur für .NET-Containeranwendungen | Mit .NET-Containern angezieltes Betriebssystem"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ef7a21efa23be3a5181f08066a093abbb915c20f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="d6dd2-104">Mit .NET-Containern angezieltes Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="d6dd2-104">What OS to target with .NET containers</span></span>

<span data-ttu-id="d6dd2-105">Durch die Vielzahl der von Docker unterstützten Betriebssysteme und die Unterschiede zwischen .NET Framework und .NET Core sollten Sie abhängig von dem Framework, das Sie verwenden, ein bestimmtes Betriebssystem und bestimmte Versionen anzielen.</span><span class="sxs-lookup"><span data-stu-id="d6dd2-105">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span> 

<span data-ttu-id="d6dd2-106">Für Windows können Sie Windows Server Core oder Windows Nano Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6dd2-106">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="d6dd2-107">Diese Windows-Versionen bieten unterschiedliche Eigenschaften (IIS in Windows Server Core im Vergleich zu einem selbstgehosteten Webserver wie Kestrel in Nano Server), die jeweils für .NET Framework oder .NET Core erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d6dd2-107">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span> 

<span data-ttu-id="d6dd2-108">Für Linux sind mehrere Distributionen (z.B. Debian) verfügbar und werden in offiziellen .NET Docker-Images unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d6dd2-108">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="d6dd2-109">In Abbildung 3-1 wird die mögliche Betriebssystemversion in Abhängigkeit vom verwendeten .NET Framework dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d6dd2-109">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![](./media/image1.png)

<span data-ttu-id="d6dd2-110">**Abbildung 3-1.**</span><span class="sxs-lookup"><span data-stu-id="d6dd2-110">**Figure 3-1.**</span></span> <span data-ttu-id="d6dd2-111">In Abhängigkeit der Version von .NET Framework anzuzielende Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="d6dd2-111">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="d6dd2-112">Sie können ebenfalls Ihr eigenes Docker-Image erstellen, wenn Sie eine andere Linux-Distribution verwenden oder wenn Sie ein Image mit nicht von Microsoft bereitgestellten Versionen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d6dd2-112">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="d6dd2-113">Sie könnten beispielsweise ein Image erstellen, bei dem ASP.NET Core unter dem herkömmlichen .NET Framework und Windows Server Core ausgeführt wird. Dabei handelt es sich um ein für Docker ungewöhnliches Szenario.</span><span class="sxs-lookup"><span data-stu-id="d6dd2-113">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

<span data-ttu-id="d6dd2-114">Wenn Sie den Namen des Images zu Ihrer Dockerfile-Datei hinzufügen, können Sie das Betriebssystem und die Version wie in den folgenden Beispielen dargestellt in Abhängigkeit vom verwendeten Tag auswählen:</span><span class="sxs-lookup"><span data-stu-id="d6dd2-114">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

-   <span data-ttu-id="d6dd2-115">microsoft/**dotnet:2.0.0-runtime-jessie**</span><span class="sxs-lookup"><span data-stu-id="d6dd2-115">microsoft/**dotnet:2.0.0-runtime-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux

-   <span data-ttu-id="d6dd2-116">microsoft/**dotnet:2.0.0-runtime-nanoserver-1709**</span><span class="sxs-lookup"><span data-stu-id="d6dd2-116">microsoft/**dotnet:2.0.0-runtime-nanoserver-1709**</span></span> 

        .NET Core 2.0 runtime-only on Windows Nano Server (Windows Server 2016 Fall Creators Update version 1709)

-   <span data-ttu-id="d6dd2-117">microsoft/**aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="d6dd2-117">microsoft/**aspnetcore:2.0**</span></span>
    
        .NET Core 2.0 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.
        The aspnetcore image has a few optimizations for ASP.NET Core. 





>[!div class="step-by-step"]
<span data-ttu-id="d6dd2-118">[Zurück] (container-framework-choice-factors.md) [Weiter] (official-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="d6dd2-118">[Previous] (container-framework-choice-factors.md) [Next] (official-net-docker-images.md)</span></span>
