---
title: Voraussetzungen für .NET Core unter Linux
description: Unterstützte Versionen von Linux-Versionen und .NET Core-Abhängigkeiten, um .NET Core-Anwendungen auf Linux-Computern zu entwickeln, bereitzustellen und auszuführen.
author: thraka
ms.author: adegeo
ms.date: 12/14/2018
ms.openlocfilehash: 7a2b0b3af97500ab0988e5de7a44713a8c05ccb9
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2018
ms.locfileid: "53656049"
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="b1043-103">Voraussetzungen für .NET Core unter Linux</span><span class="sxs-lookup"><span data-stu-id="b1043-103">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="b1043-104">Dieser Artikel erläutert die notwendigen Abhängigkeiten zum Entwickeln von .NET Core-Anwendungen unter Linux.</span><span class="sxs-lookup"><span data-stu-id="b1043-104">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="b1043-105">Die unterstützten Linux-Verteilungen und -Versionen und die daraus folgenden Abhängigkeiten gelten für die beiden Möglichkeiten zum Entwickeln von .NET Core-Apps unter Linux:</span><span class="sxs-lookup"><span data-stu-id="b1043-105">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="b1043-106">Erste Schritte mit .NET Core unter Windows/Linux/Mac OS unter Verwendung der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="b1043-106">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="b1043-107">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b1043-107">Visual Studio Code</span></span>](https://code.visualstudio.com/)

> [!NOTE]
> <span data-ttu-id="b1043-108">Das .NET Core SDK-Paket ist für Produktionsserver und -Umgebungen nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b1043-108">The .NET Core SDK package is not required for production servers/environments.</span></span> <span data-ttu-id="b1043-109">Für in Produktionsumgebungen bereitgestellte Apps ist nur das .NET Core-Runtime-Paket erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b1043-109">Only the .NET Core runtime package is needed for apps deployed to production environments.</span></span> <span data-ttu-id="b1043-110">Die .NET Core-Runtime wird als Teil einer eigenständigen Bereitstellung mit Apps bereitgestellt, sie muss für frameworkabhängige, bereitgestellte Apps jedoch separat bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b1043-110">The .NET Core runtime is deployed with apps as part of a self-contained deployment, however, it must be deployed for Framework-dependent deployed apps separately.</span></span> <span data-ttu-id="b1043-111">Weitere Informationen zu den frameworkabhängigen und eigenständigen Bereitstellungstypen finden Sie unter [.NET Core application deployment (Bereitstellung von .NET Core-Anwendungen)](./deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="b1043-111">For more information about framework-dependent and self-contained deployment types, see [.NET Core application deployment](./deploying/index.md).</span></span> <span data-ttu-id="b1043-112">Außerdem finden Sie bestimmte Richtlinien unter [Self-contained Linux applications (Eigenständige Linux-Anwendungen)](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="b1043-112">Also see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) for specific guidelines.</span></span>

## <a name="supported-linux-versions"></a><span data-ttu-id="b1043-113">Unterstützte Linux-Versionen</span><span class="sxs-lookup"><span data-stu-id="b1043-113">Supported Linux versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b1043-114">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b1043-114">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="b1043-115">.NET Core 2.x behandelt Linux als ein einzelnes Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="b1043-115">.NET Core 2.x treats Linux as a single operating system.</span></span> <span data-ttu-id="b1043-116">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="b1043-116">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span> 

<span data-ttu-id="b1043-117">Links zum Herunterladen und weitere Informationen finden Sie unter [.NET Core 2.2-Downloads](https://www.microsoft.com/net/download/dotnet-core/2.2) oder [.NET Core 2.1-Downloads](https://www.microsoft.com/net/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="b1043-117">For download links and more information, see [.NET Core 2.2 downloads](https://www.microsoft.com/net/download/dotnet-core/2.2) or [.NET Core 2.1 downloads](https://www.microsoft.com/net/download/dotnet-core/2.1).</span></span>

<span data-ttu-id="b1043-118">.NET Core 2.x wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="b1043-118">.NET Core 2.x is supported on the following Linux distributions/versions:</span></span>

* <span data-ttu-id="b1043-119">Red Hat Enterprise Linux 7, 6 – 64-Bit (`x86_64` oder `amd64`)</span><span class="sxs-lookup"><span data-stu-id="b1043-119">Red Hat Enterprise Linux 7, 6 - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="b1043-120">CentOS 7 – 64-Bit (`x86_64` oder `amd64`)</span><span class="sxs-lookup"><span data-stu-id="b1043-120">CentOS 7  - 64-bit (`x86_64` or `amd64`)</span></span> 
* <span data-ttu-id="b1043-121">Oracle Linux 7 – 64-Bit (`x86_64` oder `amd64`)</span><span class="sxs-lookup"><span data-stu-id="b1043-121">Oracle Linux 7 - 64-bit (`x86_64` or `amd64`)</span></span> 
* <span data-ttu-id="b1043-122">Fedora 28, 27 – 64-Bit (`x86_64` oder `amd64`)</span><span class="sxs-lookup"><span data-stu-id="b1043-122">Fedora 28, 27 - 64-bit (`x86_64` or `amd64`)</span></span> 
* <span data-ttu-id="b1043-123">Debian 9 (64 Bit, `arm32`), 8.7 oder höher – 64 Bit (`x86_64` oder `amd64`)</span><span class="sxs-lookup"><span data-stu-id="b1043-123">Debian 9 (64-bit, `arm32`), 8.7 or later versions - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="b1043-124">Ubuntu 18.04 (64 Bit, `arm32`), 16.04, 14.04 – 64 Bit (`x86_64` oder `amd64`)</span><span class="sxs-lookup"><span data-stu-id="b1043-124">Ubuntu 18.04 (64-bit, `arm32`), 16.04, 14.04 - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="b1043-125">Linux Mint 18, 17 – 64-Bit (`x86_64` oder `amd64`)</span><span class="sxs-lookup"><span data-stu-id="b1043-125">Linux Mint 18, 17 - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="b1043-126">openSUSE 42.3 oder höhere Versionen – 64-Bit (`x86_64` oder `amd64`)</span><span class="sxs-lookup"><span data-stu-id="b1043-126">openSUSE 42.3 or later versions - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="b1043-127">SUSE Enterprise Linux (SLES) 12 Service Pack 2 oder höher – 64-Bit (`x86_64` oder `amd64`)</span><span class="sxs-lookup"><span data-stu-id="b1043-127">SUSE Enterprise Linux (SLES) 12 Service Pack 2 or later - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="b1043-128">Alpine Linux 3.7 oder höhere Versionen – 64-Bit (`x86_64` oder `amd64`)</span><span class="sxs-lookup"><span data-stu-id="b1043-128">Alpine Linux 3.7 or later versions - 64-bit (`x86_64` or `amd64`)</span></span>

<span data-ttu-id="b1043-129">Unter [Von .NET Core 2.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) und [Von .NET Core 2.2 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, Verteilungen und Versionen, die von .NET Core 2.1 und .NET Core 2.2 unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="b1043-129">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) and [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) for the complete list of .NET Core 2.1 and .NET Core 2.2 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b1043-130">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b1043-130">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="b1043-131">Links zum Herunterladen und weitere Informationen finden Sie unter [.NET Core 1.1-Downloads](https://www.microsoft.com/net/download/dotnet-core/1.1) oder [.NET Core 1.0-Downloads](https://www.microsoft.com/net/download/dotnet-core/1.0).</span><span class="sxs-lookup"><span data-stu-id="b1043-131">For download links and more information, see [.NET Core 1.1 downloads](https://www.microsoft.com/net/download/dotnet-core/1.1) or [.NET Core 1.0 downloads](https://www.microsoft.com/net/download/dotnet-core/1.0).</span></span>

<span data-ttu-id="b1043-132">.NET Core 1.x wird unter den folgenden Linux x64-Distributionen und -Versionen (`x86_64` oder `amd64`) unterstützt:</span><span class="sxs-lookup"><span data-stu-id="b1043-132">.NET Core 1.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="b1043-133">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="b1043-133">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="b1043-134">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="b1043-134">CentOS 7</span></span>
* <span data-ttu-id="b1043-135">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="b1043-135">Oracle Linux 7</span></span>
* <span data-ttu-id="b1043-136">Fedora 28 (.NET Core 1.1), 27</span><span class="sxs-lookup"><span data-stu-id="b1043-136">Fedora 28 (.NET Core 1.1), 27</span></span>
* <span data-ttu-id="b1043-137">Debian 8.2 oder höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="b1043-137">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="b1043-138">Ubuntu 18.04 (.NET Core 1.1), 16.04, 14.04</span><span class="sxs-lookup"><span data-stu-id="b1043-138">Ubuntu 18.04 (.NET Core 1.1), 16.04, 14.04</span></span>
* <span data-ttu-id="b1043-139">Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="b1043-139">Linux Mint 17</span></span>
* <span data-ttu-id="b1043-140">openSUSE 42.3 oder höhere Versionen (.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="b1043-140">openSUSE 42.3 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="b1043-141">Unter [.NET Core 1.x Supported OS Versions (Von .NET Core 1.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) finden Sie die komplette Liste der Betriebssysteme, die von .NET Core 1.x unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="b1043-141">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-30-preview-1tabnetcore30"></a>[<span data-ttu-id="b1043-142">.NET Core 3.0 Vorschauversion 1</span><span class="sxs-lookup"><span data-stu-id="b1043-142">.NET Core 3.0 Preview 1</span></span>](#tab/netcore30)

<span data-ttu-id="b1043-143">.NET Core 3.0 Vorschauversion 1 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="b1043-143">.NET Core 3.0 Preview 1 treats Linux as a single operating system.</span></span> <span data-ttu-id="b1043-144">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="b1043-144">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span> 

<span data-ttu-id="b1043-145">Links zum Herunterladen und weitere Informationen finden Sie unter [.NET Core 3.0-Downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span><span class="sxs-lookup"><span data-stu-id="b1043-145">For download links and more information, see [.NET Core 3.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="b1043-146">.NET Core 3.0 Vorschauversion 1 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b1043-146">.NET Core 3.0 Preview 1 is supported on the following Linux distributions/versions.</span></span> 

<span data-ttu-id="b1043-147">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="b1043-147">OS</span></span>                            | <span data-ttu-id="b1043-148">Version</span><span class="sxs-lookup"><span data-stu-id="b1043-148">Version</span></span>               | <span data-ttu-id="b1043-149">Architekturen</span><span class="sxs-lookup"><span data-stu-id="b1043-149">Architectures</span></span>  
------------------------------|-----------------------|----------------
<span data-ttu-id="b1043-150">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="b1043-150">Red Hat Enterprise Linux</span></span>      | <span data-ttu-id="b1043-151">6</span><span class="sxs-lookup"><span data-stu-id="b1043-151">6</span></span>                     | <span data-ttu-id="b1043-152">x64</span><span class="sxs-lookup"><span data-stu-id="b1043-152">x64</span></span>
<span data-ttu-id="b1043-153">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="b1043-153">Red Hat Enterprise Linux</span></span><br><span data-ttu-id="b1043-154">CentOS</span><span class="sxs-lookup"><span data-stu-id="b1043-154">CentOS</span></span><br><span data-ttu-id="b1043-155">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="b1043-155">Oracle Linux</span></span>  | <span data-ttu-id="b1043-156">7</span><span class="sxs-lookup"><span data-stu-id="b1043-156">7</span></span>                     | <span data-ttu-id="b1043-157">x64</span><span class="sxs-lookup"><span data-stu-id="b1043-157">x64</span></span>
<span data-ttu-id="b1043-158">Fedora</span><span class="sxs-lookup"><span data-stu-id="b1043-158">Fedora</span></span>                        | <span data-ttu-id="b1043-159">28</span><span class="sxs-lookup"><span data-stu-id="b1043-159">28</span></span>                    | <span data-ttu-id="b1043-160">x64</span><span class="sxs-lookup"><span data-stu-id="b1043-160">x64</span></span>
<span data-ttu-id="b1043-161">Debian</span><span class="sxs-lookup"><span data-stu-id="b1043-161">Debian</span></span>                        | <span data-ttu-id="b1043-162">9</span><span class="sxs-lookup"><span data-stu-id="b1043-162">9</span></span>                     | <span data-ttu-id="b1043-163">x64, ARM32\*, ARM64\*</span><span class="sxs-lookup"><span data-stu-id="b1043-163">x64, ARM32\*, ARM64\*</span></span>
<span data-ttu-id="b1043-164">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="b1043-164">Ubuntu</span></span>                        | <span data-ttu-id="b1043-165">16.04+, 18.04+</span><span class="sxs-lookup"><span data-stu-id="b1043-165">16.04+, 18.04+</span></span>        | <span data-ttu-id="b1043-166">x64, ARM32\*, ARM64\*</span><span class="sxs-lookup"><span data-stu-id="b1043-166">x64, ARM32\*, ARM64\*</span></span>
<span data-ttu-id="b1043-167">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="b1043-167">Linux Mint</span></span>                    | <span data-ttu-id="b1043-168">18</span><span class="sxs-lookup"><span data-stu-id="b1043-168">18</span></span>                    | <span data-ttu-id="b1043-169">x64</span><span class="sxs-lookup"><span data-stu-id="b1043-169">x64</span></span>
<span data-ttu-id="b1043-170">openSUSE</span><span class="sxs-lookup"><span data-stu-id="b1043-170">openSUSE</span></span>                      | <span data-ttu-id="b1043-171">42.3+</span><span class="sxs-lookup"><span data-stu-id="b1043-171">42.3+</span></span>                 | <span data-ttu-id="b1043-172">x64</span><span class="sxs-lookup"><span data-stu-id="b1043-172">x64</span></span>
<span data-ttu-id="b1043-173">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="b1043-173">SUSE Enterprise Linux (SLES)</span></span>  | <span data-ttu-id="b1043-174">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="b1043-174">12 SP2+</span></span>               | <span data-ttu-id="b1043-175">x64</span><span class="sxs-lookup"><span data-stu-id="b1043-175">x64</span></span>
<span data-ttu-id="b1043-176">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="b1043-176">Alpine Linux</span></span>                  | <span data-ttu-id="b1043-177">3.8+</span><span class="sxs-lookup"><span data-stu-id="b1043-177">3.8+</span></span>                  | <span data-ttu-id="b1043-178">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="b1043-178">x64, ARM64</span></span>

<span data-ttu-id="b1043-179">\* ARM32 und ARM64 unterstützen das Starten mit Debian 9 und Ubuntu 16.04.</span><span class="sxs-lookup"><span data-stu-id="b1043-179">\* ARM32 and ARM64 support starts with Debian 9 and Ubuntu 16.04.</span></span> <span data-ttu-id="b1043-180">Frühere Versionen dieser Distributionen werden auf ARM-Chips nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b1043-180">Earlier versions of those distros are not supported on ARM chips.</span></span>

<span data-ttu-id="b1043-181">Unter [.NET Core 3.0 Supported OS Versions (Von .NET Core 3.0 unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, Verteilungen und Versionen, die von .NET Core 3.0 unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="b1043-181">See [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) for the complete list of .NET Core 3.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="b1043-182">Weitere Informationen zum Installieren von .NET Core 3.0 unter ARM64 finden Sie unter [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Installieren von .NET Core 3.0 unter Linux ARM64).</span><span class="sxs-lookup"><span data-stu-id="b1043-182">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>



---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="b1043-183">Abhängigkeiten der Linux-Distributionen</span><span class="sxs-lookup"><span data-stu-id="b1043-183">Linux distribution dependencies</span></span>

<span data-ttu-id="b1043-184">Bei folgenden Paketen handelt es sich um Beispiele.</span><span class="sxs-lookup"><span data-stu-id="b1043-184">The following are intended to be examples.</span></span> <span data-ttu-id="b1043-185">Die exakten Versionen und Namen können sich bei der von Ihnen verwendeten Linux-Verteilung leicht unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="b1043-185">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="b1043-186">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="b1043-186">Ubuntu</span></span>

<span data-ttu-id="b1043-187">Für Ubuntu-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:</span><span class="sxs-lookup"><span data-stu-id="b1043-187">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="b1043-188">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="b1043-188">liblttng-ust0</span></span>
* <span data-ttu-id="b1043-189">libcurl3</span><span class="sxs-lookup"><span data-stu-id="b1043-189">libcurl3</span></span>
* <span data-ttu-id="b1043-190">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="b1043-190">libssl1.0.0</span></span>
* <span data-ttu-id="b1043-191">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="b1043-191">libkrb5-3</span></span>
* <span data-ttu-id="b1043-192">zlib1g</span><span class="sxs-lookup"><span data-stu-id="b1043-192">zlib1g</span></span>
* <span data-ttu-id="b1043-193">libicu52 (für 14.X)</span><span class="sxs-lookup"><span data-stu-id="b1043-193">libicu52 (for 14.x)</span></span>
* <span data-ttu-id="b1043-194">libicu55 (für 16.X)</span><span class="sxs-lookup"><span data-stu-id="b1043-194">libicu55 (for 16.x)</span></span>
* <span data-ttu-id="b1043-195">libicu57 (für 17.X)</span><span class="sxs-lookup"><span data-stu-id="b1043-195">libicu57 (for 17.x)</span></span>
* <span data-ttu-id="b1043-196">libicu60 (für 18.X)</span><span class="sxs-lookup"><span data-stu-id="b1043-196">libicu60 (for 18.x)</span></span>

<span data-ttu-id="b1043-197">Für Versionen vor .NET Core 2.1 sind außerdem folgende Abhängigkeiten erforderlich:</span><span class="sxs-lookup"><span data-stu-id="b1043-197">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

* <span data-ttu-id="b1043-198">libunwind8</span><span class="sxs-lookup"><span data-stu-id="b1043-198">libunwind8</span></span>
* <span data-ttu-id="b1043-199">libuuid1</span><span class="sxs-lookup"><span data-stu-id="b1043-199">libuuid1</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="b1043-200">CentOS und Fedora</span><span class="sxs-lookup"><span data-stu-id="b1043-200">CentOS and Fedora</span></span>

<span data-ttu-id="b1043-201">Für CentOS-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:</span><span class="sxs-lookup"><span data-stu-id="b1043-201">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="b1043-202">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="b1043-202">lttng-ust</span></span>
* <span data-ttu-id="b1043-203">libcurl</span><span class="sxs-lookup"><span data-stu-id="b1043-203">libcurl</span></span>
* <span data-ttu-id="b1043-204">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="b1043-204">openssl-libs</span></span>
* <span data-ttu-id="b1043-205">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="b1043-205">krb5-libs</span></span>
* <span data-ttu-id="b1043-206">libicu</span><span class="sxs-lookup"><span data-stu-id="b1043-206">libicu</span></span>
* <span data-ttu-id="b1043-207">zlib</span><span class="sxs-lookup"><span data-stu-id="b1043-207">zlib</span></span>

<span data-ttu-id="b1043-208">Für Fedora-Benutzer: Wenn Ihre Version von OpenSSL höher als oder gleich 1.1 ist, müssen Sie „compat-openssl10“ installieren.</span><span class="sxs-lookup"><span data-stu-id="b1043-208">Fedora users: If your openssl's version >= 1.1, you'll need to install compat-openssl10.</span></span>

<span data-ttu-id="b1043-209">Für Versionen vor .NET Core 2.1 sind außerdem folgende Abhängigkeiten erforderlich:</span><span class="sxs-lookup"><span data-stu-id="b1043-209">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

* <span data-ttu-id="b1043-210">libunwind</span><span class="sxs-lookup"><span data-stu-id="b1043-210">libunwind</span></span>
* <span data-ttu-id="b1043-211">libuuid</span><span class="sxs-lookup"><span data-stu-id="b1043-211">libuuid</span></span>

<span data-ttu-id="b1043-212">Weitere Informationen zu den Abhängigkeiten finden Sie unter [Self contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Eigenständige Linux-Anwendungen).</span><span class="sxs-lookup"><span data-stu-id="b1043-212">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="b1043-213">Installieren der erforderlichen Abhängigkeiten für .NET Core mit nativen Installationsprogrammen</span><span class="sxs-lookup"><span data-stu-id="b1043-213">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="b1043-214">Native Installationsprogramme für .NET Core sind für unterstützte Linux-Distributionen und -Versionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b1043-214">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="b1043-215">Für die nativen Installationsprogramme benötigen Sie Administratorzugriff (sudo) auf den Server.</span><span class="sxs-lookup"><span data-stu-id="b1043-215">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="b1043-216">Das Verwenden eines nativen Installationsprogramms hat den Vorteil, dass alle nativen Abhängigkeiten von .NET Core installiert werden.</span><span class="sxs-lookup"><span data-stu-id="b1043-216">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="b1043-217">Native Installationsprogramme installieren das .NET Core SDK zudem systemweit.</span><span class="sxs-lookup"><span data-stu-id="b1043-217">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="b1043-218">Unter Linux gibt es zwei Auswahlmöglichkeiten für Installationspakete:</span><span class="sxs-lookup"><span data-stu-id="b1043-218">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="b1043-219">Das Verwenden eines feedbasierten Paket-Managers, zum Beispiel „apt-get“ für Ubuntu oder „yum“ für CentOS/RHEL.</span><span class="sxs-lookup"><span data-stu-id="b1043-219">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="b1043-220">Das eigenständige Verwenden der Pakete, DEB oder RPM.</span><span class="sxs-lookup"><span data-stu-id="b1043-220">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="b1043-221">Das Skripten von Installationen mit dem Installationsskript von .NET Core</span><span class="sxs-lookup"><span data-stu-id="b1043-221">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="b1043-222">Die [Dotnet-Installationsskripts](./tools/dotnet-install-script.md) werden verwendet, um ohne Administratorrechte eine Installation der CLI-Toolkette und der freigegebenen Laufzeit auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b1043-222">The [dotnet-install scripts](./tools/dotnet-install-script.md) are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="b1043-223">Sie können das Skript unter [https://dot.net/v1/dotnet-install.sh](https://dot.net/v1/dotnet-install.sh) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="b1043-223">You can download the script from [https://dot.net/v1/dotnet-install.sh](https://dot.net/v1/dotnet-install.sh).</span></span>

<span data-ttu-id="b1043-224">Das Skript installiert standardmäßig die neueste Version von „LTS“, aktuell .NET Core 1.1.</span><span class="sxs-lookup"><span data-stu-id="b1043-224">The script defaults to installing the latest "LTS" version, which is currently .NET Core 1.1.</span></span> <span data-ttu-id="b1043-225">Zum Installieren von .NET Core 2.1 führen Sie das Skript mit dem folgenden Switch aus:</span><span class="sxs-lookup"><span data-stu-id="b1043-225">To install .NET Core 2.1, run the script with the following switch:</span></span>

```console
./dotnet-install.sh -c Current
```

<span data-ttu-id="b1043-226">Das Bash-Skript für das Installationsprogramm wird in Automatisierungsszenarios und für Installationen ohne Administratorrechte verwendet.</span><span class="sxs-lookup"><span data-stu-id="b1043-226">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="b1043-227">Dieses Skript liest auch PowerShell-Schalter, sodass diese mit dem Skript auf Linux/OS X-Systemen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b1043-227">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="b1043-228">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="b1043-228">Troubleshoot</span></span>

<span data-ttu-id="b1043-229">Weitere Informationen zu Problemen mit der Installation von .NET Core auf einer unterstützten Verteilung bzw. Version von Linux finden Sie in den folgenden Artikeln zu Ihrer installierte Verteilung bzw. Version:</span><span class="sxs-lookup"><span data-stu-id="b1043-229">If you have problems with a .NET Core installation on a supported Linux distribution/version, consult the following topics for your installed distributions/versions:</span></span>

* [<span data-ttu-id="b1043-230">.NET Core 3.0 known issues (.NET Core 1.0 Bekannte Probleme)</span><span class="sxs-lookup"><span data-stu-id="b1043-230">.NET Core 3.0 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/3.0)
* [<span data-ttu-id="b1043-231">.NET Core 2.2 known issues (.NET Core 1.0 Bekannte Probleme)</span><span class="sxs-lookup"><span data-stu-id="b1043-231">.NET Core 2.2 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.2)
* [<span data-ttu-id="b1043-232">.NET Core 2.1 known issues (.NET Core 2.1 Bekannte Probleme)</span><span class="sxs-lookup"><span data-stu-id="b1043-232">.NET Core 2.1 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.1)
* [<span data-ttu-id="b1043-233">.NET Core 1.1 known issues (.NET Core 1.1 Bekannte Probleme)</span><span class="sxs-lookup"><span data-stu-id="b1043-233">.NET Core 1.1 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.1)
* [<span data-ttu-id="b1043-234">.NET Core 1.0 known issues (.NET Core 1.0 Bekannte Probleme)</span><span class="sxs-lookup"><span data-stu-id="b1043-234">.NET Core 1.0 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0)
