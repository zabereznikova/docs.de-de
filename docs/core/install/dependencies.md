---
title: '.NET Core SDK und Runtimeabhängigkeiten: .NET Core'
description: In diesem Artikel werden die Voraussetzungen für das Betriebssystem und die CPU-Architektur zum Installieren des .NET Core SDK und der Runtime unter Windows, Linux und macOS erläutert.
author: leecow
ms.author: leecow
ms.date: 04/30/2020
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 280aa1431686ff99257580bb024a84b1e57f85c0
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895487"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="7be60-103">.NET Core-Abhängigkeiten und -Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7be60-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="7be60-104">In diesem Artikel wird erläutert, welche Betriebssysteme und CPU-Architektur von .NET Core unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7be60-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="7be60-105">Unterstützte Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="7be60-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="7be60-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="7be60-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="7be60-107">Die folgenden Windows-Versionen werden von .NET Core 3.1 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7be60-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="7be60-108">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="7be60-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="7be60-109">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="7be60-109">OS</span></span>                            | <span data-ttu-id="7be60-110">Version</span><span class="sxs-lookup"><span data-stu-id="7be60-110">Version</span></span>                        | <span data-ttu-id="7be60-111">Architekturen</span><span class="sxs-lookup"><span data-stu-id="7be60-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="7be60-112">Windows-Client</span><span class="sxs-lookup"><span data-stu-id="7be60-112">Windows Client</span></span>                | <span data-ttu-id="7be60-113">7 SP1 oder höher, 8.1</span><span class="sxs-lookup"><span data-stu-id="7be60-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="7be60-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7be60-114">x64, x86</span></span>        |
| <span data-ttu-id="7be60-115">Windows 10-Client</span><span class="sxs-lookup"><span data-stu-id="7be60-115">Windows 10 Client</span></span>             | <span data-ttu-id="7be60-116">Version 1607 oder höher</span><span class="sxs-lookup"><span data-stu-id="7be60-116">Version 1607+</span></span>                  | <span data-ttu-id="7be60-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7be60-117">x64, x86</span></span>        |
| <span data-ttu-id="7be60-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="7be60-118">Windows Server</span></span>                | <span data-ttu-id="7be60-119">2012 R2 oder höher</span><span class="sxs-lookup"><span data-stu-id="7be60-119">2012 R2+</span></span>                       | <span data-ttu-id="7be60-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7be60-120">x64, x86</span></span>        |
| <span data-ttu-id="7be60-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="7be60-121">Nano Server</span></span>                   | <span data-ttu-id="7be60-122">Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="7be60-122">Version 1803+</span></span>                  | <span data-ttu-id="7be60-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="7be60-123">x64, ARM32</span></span>      |

<span data-ttu-id="7be60-124">Weitere Informationen zu den von .NET Core 3.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="7be60-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="7be60-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="7be60-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="7be60-126">*.NET Core 3.0 wird aktuell nicht unterstützt. Weitere Informationen finden Sie in der [Supportrichtlinie für .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="7be60-126">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="7be60-127">Die folgenden Windows-Versionen werden von .NET Core 3.0 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7be60-127">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="7be60-128">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="7be60-128">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="7be60-129">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="7be60-129">OS</span></span>                            | <span data-ttu-id="7be60-130">Version</span><span class="sxs-lookup"><span data-stu-id="7be60-130">Version</span></span>                        | <span data-ttu-id="7be60-131">Architekturen</span><span class="sxs-lookup"><span data-stu-id="7be60-131">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="7be60-132">Windows-Client</span><span class="sxs-lookup"><span data-stu-id="7be60-132">Windows Client</span></span>                | <span data-ttu-id="7be60-133">7 SP1 oder höher, 8.1</span><span class="sxs-lookup"><span data-stu-id="7be60-133">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="7be60-134">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7be60-134">x64, x86</span></span>        |
| <span data-ttu-id="7be60-135">Windows 10-Client</span><span class="sxs-lookup"><span data-stu-id="7be60-135">Windows 10 Client</span></span>             | <span data-ttu-id="7be60-136">Version 1607 oder höher</span><span class="sxs-lookup"><span data-stu-id="7be60-136">Version 1607+</span></span>                  | <span data-ttu-id="7be60-137">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7be60-137">x64, x86</span></span>        |
| <span data-ttu-id="7be60-138">Windows Server</span><span class="sxs-lookup"><span data-stu-id="7be60-138">Windows Server</span></span>                | <span data-ttu-id="7be60-139">2012 R2 oder höher</span><span class="sxs-lookup"><span data-stu-id="7be60-139">2012 R2+</span></span>                       | <span data-ttu-id="7be60-140">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7be60-140">x64, x86</span></span>        |
| <span data-ttu-id="7be60-141">Nano Server</span><span class="sxs-lookup"><span data-stu-id="7be60-141">Nano Server</span></span>                   | <span data-ttu-id="7be60-142">Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="7be60-142">Version 1803+</span></span>                  | <span data-ttu-id="7be60-143">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="7be60-143">x64, ARM32</span></span>      |

<span data-ttu-id="7be60-144">Weitere Informationen zu den von .NET Core 3.0 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.0 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="7be60-144">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="7be60-145">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="7be60-145">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="7be60-146">*.NET Core 2.2 wird aktuell nicht unterstützt. Weitere Informationen finden Sie in der [Supportrichtlinie für .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="7be60-146">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="7be60-147">Die folgenden Windows-Versionen werden von .NET Core 2.2 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7be60-147">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="7be60-148">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="7be60-148">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="7be60-149">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="7be60-149">OS</span></span>                            | <span data-ttu-id="7be60-150">Version</span><span class="sxs-lookup"><span data-stu-id="7be60-150">Version</span></span>                        | <span data-ttu-id="7be60-151">Architekturen</span><span class="sxs-lookup"><span data-stu-id="7be60-151">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="7be60-152">Windows-Client</span><span class="sxs-lookup"><span data-stu-id="7be60-152">Windows Client</span></span>                | <span data-ttu-id="7be60-153">7 SP1 oder höher, 8.1</span><span class="sxs-lookup"><span data-stu-id="7be60-153">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="7be60-154">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7be60-154">x64, x86</span></span>        |
| <span data-ttu-id="7be60-155">Windows 10-Client</span><span class="sxs-lookup"><span data-stu-id="7be60-155">Windows 10 Client</span></span>             | <span data-ttu-id="7be60-156">Version 1607 oder höher</span><span class="sxs-lookup"><span data-stu-id="7be60-156">Version 1607+</span></span>                  | <span data-ttu-id="7be60-157">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7be60-157">x64, x86</span></span>        |
| <span data-ttu-id="7be60-158">Windows Server</span><span class="sxs-lookup"><span data-stu-id="7be60-158">Windows Server</span></span>                | <span data-ttu-id="7be60-159">2008 R2 SP1 oder höher</span><span class="sxs-lookup"><span data-stu-id="7be60-159">2008 R2 SP1+</span></span>                   | <span data-ttu-id="7be60-160">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7be60-160">x64, x86</span></span>        |
| <span data-ttu-id="7be60-161">Nano Server</span><span class="sxs-lookup"><span data-stu-id="7be60-161">Nano Server</span></span>                   | <span data-ttu-id="7be60-162">Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="7be60-162">Version 1803+</span></span>                   | <span data-ttu-id="7be60-163">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="7be60-163">x64, ARM32</span></span>      |

<span data-ttu-id="7be60-164">Weitere Informationen zu den von .NET Core 2.2 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.2 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="7be60-164">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="7be60-165">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7be60-165">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="7be60-166">Die folgenden Windows-Versionen werden von .NET Core 2.1 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7be60-166">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="7be60-167">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="7be60-167">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="7be60-168">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="7be60-168">OS</span></span>                            | <span data-ttu-id="7be60-169">Version</span><span class="sxs-lookup"><span data-stu-id="7be60-169">Version</span></span>                        | <span data-ttu-id="7be60-170">Architekturen</span><span class="sxs-lookup"><span data-stu-id="7be60-170">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="7be60-171">Windows-Client</span><span class="sxs-lookup"><span data-stu-id="7be60-171">Windows Client</span></span>                | <span data-ttu-id="7be60-172">7 SP1 oder höher, 8.1</span><span class="sxs-lookup"><span data-stu-id="7be60-172">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="7be60-173">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7be60-173">x64, x86</span></span>        |
| <span data-ttu-id="7be60-174">Windows 10-Client</span><span class="sxs-lookup"><span data-stu-id="7be60-174">Windows 10 Client</span></span>             | <span data-ttu-id="7be60-175">Version 1607 oder höher</span><span class="sxs-lookup"><span data-stu-id="7be60-175">Version 1607+</span></span>                  | <span data-ttu-id="7be60-176">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7be60-176">x64, x86</span></span>        |
| <span data-ttu-id="7be60-177">Windows Server</span><span class="sxs-lookup"><span data-stu-id="7be60-177">Windows Server</span></span>                | <span data-ttu-id="7be60-178">2008 R2 SP1 oder höher</span><span class="sxs-lookup"><span data-stu-id="7be60-178">2008 R2 SP1+</span></span>                   | <span data-ttu-id="7be60-179">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7be60-179">x64, x86</span></span>        |
| <span data-ttu-id="7be60-180">Nano Server</span><span class="sxs-lookup"><span data-stu-id="7be60-180">Nano Server</span></span>                   | <span data-ttu-id="7be60-181">Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="7be60-181">Version 1803+</span></span>                  | <span data-ttu-id="7be60-182">x64,</span><span class="sxs-lookup"><span data-stu-id="7be60-182">x64,</span></span>            |

<span data-ttu-id="7be60-183">Weitere Informationen zu den von .NET Core 2.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="7be60-183">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a> <span data-ttu-id="7be60-184">Windows 7/Vista/8.1/Server 2008 R2/Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="7be60-184">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span></span>

<span data-ttu-id="7be60-185">Weitere Abhängigkeiten sind erforderlich, wenn Sie das .NET SDK oder die Runtime unter den folgenden Windows-Versionen installieren:</span><span class="sxs-lookup"><span data-stu-id="7be60-185">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="7be60-186">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="7be60-186">Windows 7 SP1</span></span>
- <span data-ttu-id="7be60-187">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="7be60-187">Windows Vista SP 2</span></span>
- <span data-ttu-id="7be60-188">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="7be60-188">Windows 8.1</span></span>
- <span data-ttu-id="7be60-189">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="7be60-189">Windows Server 2008 R2</span></span>
- <span data-ttu-id="7be60-190">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="7be60-190">Windows Server 2012 R2</span></span>

<span data-ttu-id="7be60-191">Installieren Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7be60-191">Install the following:</span></span>

- <span data-ttu-id="7be60-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685)</span><span class="sxs-lookup"><span data-stu-id="7be60-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="7be60-193">KB2533623</span><span class="sxs-lookup"><span data-stu-id="7be60-193">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="7be60-194">Die oben aufgeführten Anforderungen sind auch erforderlich, wenn einer der folgenden Fehler auftritt:</span><span class="sxs-lookup"><span data-stu-id="7be60-194">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="7be60-195">Das Programm kann nicht gestartet werden, da *api-ms-win-crt-runtime-l1-1-0.dll* auf dem Computer fehlt.</span><span class="sxs-lookup"><span data-stu-id="7be60-195">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="7be60-196">Installieren Sie das Programm erneut, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="7be60-196">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="7be60-197">\- oder -</span><span class="sxs-lookup"><span data-stu-id="7be60-197">\- or -</span></span>
>
> <span data-ttu-id="7be60-198">Das Programm kann nicht gestartet werden, da *api-ms-win-cor-timezone-l1-1-0.dll* auf dem Computer fehlt.</span><span class="sxs-lookup"><span data-stu-id="7be60-198">The program can't start because *api-ms-win-cor-timezone-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="7be60-199">Installieren Sie das Programm erneut, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="7be60-199">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="7be60-200">\- oder -</span><span class="sxs-lookup"><span data-stu-id="7be60-200">\- or -</span></span>
>
> <span data-ttu-id="7be60-201">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed. (Die Bibliothek „hostfxr.dll“ wurde gefunden, aber der Ladevorgang aus C:\<Pfad_zu_App>\hostfxr.dll ist fehlgeschlagen.)</span><span class="sxs-lookup"><span data-stu-id="7be60-201">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="7be60-202">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="7be60-202">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="7be60-203">.NET Core 3.1 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="7be60-203">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="7be60-204">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="7be60-204">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="7be60-205">.NET Core 3.1 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7be60-205">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="7be60-206">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="7be60-206">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="7be60-207">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="7be60-207">OS</span></span>                             | <span data-ttu-id="7be60-208">Version</span><span class="sxs-lookup"><span data-stu-id="7be60-208">Version</span></span>               | <span data-ttu-id="7be60-209">Architekturen</span><span class="sxs-lookup"><span data-stu-id="7be60-209">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="7be60-210">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="7be60-210">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="7be60-211">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="7be60-211">6, 7, 8</span></span>               | <span data-ttu-id="7be60-212">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-212">x64</span></span> |
| <span data-ttu-id="7be60-213">CentOS</span><span class="sxs-lookup"><span data-stu-id="7be60-213">CentOS</span></span>                         | <span data-ttu-id="7be60-214">7 und höher</span><span class="sxs-lookup"><span data-stu-id="7be60-214">7+</span></span>                    | <span data-ttu-id="7be60-215">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-215">x64</span></span> |
| <span data-ttu-id="7be60-216">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="7be60-216">Oracle Linux</span></span>                   | <span data-ttu-id="7be60-217">7 und höher</span><span class="sxs-lookup"><span data-stu-id="7be60-217">7+</span></span>                    | <span data-ttu-id="7be60-218">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-218">x64</span></span> |
| <span data-ttu-id="7be60-219">Fedora</span><span class="sxs-lookup"><span data-stu-id="7be60-219">Fedora</span></span>                         | <span data-ttu-id="7be60-220">30 und höher</span><span class="sxs-lookup"><span data-stu-id="7be60-220">30+</span></span>                   | <span data-ttu-id="7be60-221">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-221">x64</span></span> |
| <span data-ttu-id="7be60-222">Debian</span><span class="sxs-lookup"><span data-stu-id="7be60-222">Debian</span></span>                         | <span data-ttu-id="7be60-223">9 und höher</span><span class="sxs-lookup"><span data-stu-id="7be60-223">9+</span></span>                    | <span data-ttu-id="7be60-224">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="7be60-224">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="7be60-225">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="7be60-225">Ubuntu</span></span>                         | <span data-ttu-id="7be60-226">16.04 und höher</span><span class="sxs-lookup"><span data-stu-id="7be60-226">16.04+</span></span>                | <span data-ttu-id="7be60-227">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="7be60-227">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="7be60-228">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="7be60-228">Linux Mint</span></span>                     | <span data-ttu-id="7be60-229">18 und höher</span><span class="sxs-lookup"><span data-stu-id="7be60-229">18+</span></span>                   | <span data-ttu-id="7be60-230">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-230">x64</span></span> |
| <span data-ttu-id="7be60-231">openSUSE</span><span class="sxs-lookup"><span data-stu-id="7be60-231">openSUSE</span></span>                       | <span data-ttu-id="7be60-232">15 und höher</span><span class="sxs-lookup"><span data-stu-id="7be60-232">15+</span></span>                   | <span data-ttu-id="7be60-233">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-233">x64</span></span> |
| <span data-ttu-id="7be60-234">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="7be60-234">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="7be60-235">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="7be60-235">12 SP2+</span></span>               | <span data-ttu-id="7be60-236">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-236">x64</span></span> |
| <span data-ttu-id="7be60-237">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="7be60-237">Alpine Linux</span></span>                   | <span data-ttu-id="7be60-238">3.10 oder höher</span><span class="sxs-lookup"><span data-stu-id="7be60-238">3.10+</span></span>                 | <span data-ttu-id="7be60-239">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="7be60-239">x64, ARM64</span></span> |

<span data-ttu-id="7be60-240">Weitere Informationen zu den von .NET Core 3.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="7be60-240">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="7be60-241">Weitere Informationen zum Installieren von .NET Core 3.1 unter ARM64 (Kernel 4.14 oder höher) finden Sie unter [Installieren von .NET Core 3.0 unter Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span><span class="sxs-lookup"><span data-stu-id="7be60-241">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7be60-242">Für die Unterstützung von ARM64 ist Linux-Kernel 4.14 oder höher erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7be60-242">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="7be60-243">Einige Linux-Verteilungen erfüllen diese Anforderung, andere hingegen nicht.</span><span class="sxs-lookup"><span data-stu-id="7be60-243">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="7be60-244">So wird Ubuntu 18.04 im Gegensatz zu Ubuntu 16.04 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7be60-244">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="7be60-245">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="7be60-245">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="7be60-246">*.NET Core 3.0 wird aktuell nicht unterstützt. Weitere Informationen finden Sie in der [Supportrichtlinie für .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="7be60-246">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="7be60-247">.NET Core 3.0 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="7be60-247">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="7be60-248">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="7be60-248">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="7be60-249">.NET Core 3.0 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7be60-249">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="7be60-250">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="7be60-250">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="7be60-251">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="7be60-251">OS</span></span>                             | <span data-ttu-id="7be60-252">Version</span><span class="sxs-lookup"><span data-stu-id="7be60-252">Version</span></span>               | <span data-ttu-id="7be60-253">Architekturen</span><span class="sxs-lookup"><span data-stu-id="7be60-253">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="7be60-254">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="7be60-254">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="7be60-255">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="7be60-255">6, 7, 8</span></span>               | <span data-ttu-id="7be60-256">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-256">x64</span></span> |
| <span data-ttu-id="7be60-257">CentOS</span><span class="sxs-lookup"><span data-stu-id="7be60-257">CentOS</span></span>                         | <span data-ttu-id="7be60-258">7 und höher</span><span class="sxs-lookup"><span data-stu-id="7be60-258">7+</span></span>                    | <span data-ttu-id="7be60-259">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-259">x64</span></span> |
| <span data-ttu-id="7be60-260">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="7be60-260">Oracle Linux</span></span>                   | <span data-ttu-id="7be60-261">7 und höher</span><span class="sxs-lookup"><span data-stu-id="7be60-261">7+</span></span>                    | <span data-ttu-id="7be60-262">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-262">x64</span></span> |
| <span data-ttu-id="7be60-263">Fedora</span><span class="sxs-lookup"><span data-stu-id="7be60-263">Fedora</span></span>                         | <span data-ttu-id="7be60-264">29 und höher</span><span class="sxs-lookup"><span data-stu-id="7be60-264">29+</span></span>                   | <span data-ttu-id="7be60-265">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-265">x64</span></span> |
| <span data-ttu-id="7be60-266">Debian</span><span class="sxs-lookup"><span data-stu-id="7be60-266">Debian</span></span>                         | <span data-ttu-id="7be60-267">9 und höher</span><span class="sxs-lookup"><span data-stu-id="7be60-267">9+</span></span>                    | <span data-ttu-id="7be60-268">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="7be60-268">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="7be60-269">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="7be60-269">Ubuntu</span></span>                         | <span data-ttu-id="7be60-270">16.04 und höher</span><span class="sxs-lookup"><span data-stu-id="7be60-270">16.04+</span></span>                | <span data-ttu-id="7be60-271">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="7be60-271">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="7be60-272">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="7be60-272">Linux Mint</span></span>                     | <span data-ttu-id="7be60-273">18 und höher</span><span class="sxs-lookup"><span data-stu-id="7be60-273">18+</span></span>                   | <span data-ttu-id="7be60-274">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-274">x64</span></span> |
| <span data-ttu-id="7be60-275">openSUSE</span><span class="sxs-lookup"><span data-stu-id="7be60-275">openSUSE</span></span>                       | <span data-ttu-id="7be60-276">15 und höher</span><span class="sxs-lookup"><span data-stu-id="7be60-276">15+</span></span>                   | <span data-ttu-id="7be60-277">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-277">x64</span></span> |
| <span data-ttu-id="7be60-278">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="7be60-278">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="7be60-279">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="7be60-279">12 SP2+</span></span>               | <span data-ttu-id="7be60-280">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-280">x64</span></span> |
| <span data-ttu-id="7be60-281">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="7be60-281">Alpine Linux</span></span>                   | <span data-ttu-id="7be60-282">3.8+</span><span class="sxs-lookup"><span data-stu-id="7be60-282">3.8+</span></span>                  | <span data-ttu-id="7be60-283">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="7be60-283">x64, ARM64</span></span> |

<span data-ttu-id="7be60-284">Weitere Informationen zu den von .NET Core 3.0 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.0 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="7be60-284">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="7be60-285">Weitere Informationen zum Installieren von .NET Core 3.0 unter ARM64 finden Sie unter [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Installieren von .NET Core 3.0 unter Linux ARM64).</span><span class="sxs-lookup"><span data-stu-id="7be60-285">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="7be60-286">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="7be60-286">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="7be60-287">*.NET Core 2.2 wird aktuell nicht unterstützt. Weitere Informationen finden Sie in der [Supportrichtlinie für .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="7be60-287">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="7be60-288">.NET Core 2.2 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="7be60-288">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="7be60-289">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="7be60-289">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="7be60-290">.NET Core 2.2 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7be60-290">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="7be60-291">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="7be60-291">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="7be60-292">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="7be60-292">OS</span></span>                             |  <span data-ttu-id="7be60-293">Version</span><span class="sxs-lookup"><span data-stu-id="7be60-293">Version</span></span>                |  <span data-ttu-id="7be60-294">Architekturen</span><span class="sxs-lookup"><span data-stu-id="7be60-294">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="7be60-295">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="7be60-295">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="7be60-296">6, 7</span><span class="sxs-lookup"><span data-stu-id="7be60-296">6, 7</span></span>                   | <span data-ttu-id="7be60-297">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-297">x64</span></span> |
| <span data-ttu-id="7be60-298">CentOS</span><span class="sxs-lookup"><span data-stu-id="7be60-298">CentOS</span></span>                         |  <span data-ttu-id="7be60-299">7</span><span class="sxs-lookup"><span data-stu-id="7be60-299">7</span></span>                      | <span data-ttu-id="7be60-300">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-300">x64</span></span> |
| <span data-ttu-id="7be60-301">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="7be60-301">Oracle Linux</span></span>                   |  <span data-ttu-id="7be60-302">7</span><span class="sxs-lookup"><span data-stu-id="7be60-302">7</span></span>                      | <span data-ttu-id="7be60-303">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-303">x64</span></span> |
| <span data-ttu-id="7be60-304">Fedora</span><span class="sxs-lookup"><span data-stu-id="7be60-304">Fedora</span></span>                         |  <span data-ttu-id="7be60-305">29, 30</span><span class="sxs-lookup"><span data-stu-id="7be60-305">29, 30</span></span>                 | <span data-ttu-id="7be60-306">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-306">x64</span></span> |
| <span data-ttu-id="7be60-307">Debian</span><span class="sxs-lookup"><span data-stu-id="7be60-307">Debian</span></span>                         |  <span data-ttu-id="7be60-308">9</span><span class="sxs-lookup"><span data-stu-id="7be60-308">9</span></span>                      | <span data-ttu-id="7be60-309">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="7be60-309">x64, ARM32</span></span> |
| <span data-ttu-id="7be60-310">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="7be60-310">Ubuntu</span></span>                         |  <span data-ttu-id="7be60-311">16.04, 18.04, 18.10</span><span class="sxs-lookup"><span data-stu-id="7be60-311">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="7be60-312">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="7be60-312">x64, ARM32</span></span> |
| <span data-ttu-id="7be60-313">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="7be60-313">Linux Mint</span></span>                     |  <span data-ttu-id="7be60-314">17, 18</span><span class="sxs-lookup"><span data-stu-id="7be60-314">17, 18</span></span>                 | <span data-ttu-id="7be60-315">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-315">x64</span></span> |
| <span data-ttu-id="7be60-316">openSUSE</span><span class="sxs-lookup"><span data-stu-id="7be60-316">openSUSE</span></span>                       |  <span data-ttu-id="7be60-317">15 und höher</span><span class="sxs-lookup"><span data-stu-id="7be60-317">15+</span></span>                    | <span data-ttu-id="7be60-318">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-318">x64</span></span> |
| <span data-ttu-id="7be60-319">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="7be60-319">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="7be60-320">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="7be60-320">12 SP2+</span></span>                | <span data-ttu-id="7be60-321">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-321">x64</span></span> |
| <span data-ttu-id="7be60-322">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="7be60-322">Alpine Linux</span></span>                   |  <span data-ttu-id="7be60-323">3.8+</span><span class="sxs-lookup"><span data-stu-id="7be60-323">3.8+</span></span>                   | <span data-ttu-id="7be60-324">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-324">x64</span></span> |

<span data-ttu-id="7be60-325">Weitere Informationen zu den von .NET Core 2.2 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.2 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="7be60-325">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="7be60-326">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7be60-326">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="7be60-327">.NET Core 2.1 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="7be60-327">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="7be60-328">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="7be60-328">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="7be60-329">.NET Core 2.1 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7be60-329">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="7be60-330">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="7be60-330">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="7be60-331">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="7be60-331">OS</span></span>                             |  <span data-ttu-id="7be60-332">Version</span><span class="sxs-lookup"><span data-stu-id="7be60-332">Version</span></span>                |  <span data-ttu-id="7be60-333">Architekturen</span><span class="sxs-lookup"><span data-stu-id="7be60-333">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="7be60-334">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="7be60-334">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="7be60-335">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="7be60-335">6, 7, 8</span></span>                | <span data-ttu-id="7be60-336">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-336">x64</span></span> |
| <span data-ttu-id="7be60-337">CentOS</span><span class="sxs-lookup"><span data-stu-id="7be60-337">CentOS</span></span>                         |  <span data-ttu-id="7be60-338">7 und höher</span><span class="sxs-lookup"><span data-stu-id="7be60-338">7+</span></span>                     | <span data-ttu-id="7be60-339">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-339">x64</span></span> |
| <span data-ttu-id="7be60-340">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="7be60-340">Oracle Linux</span></span>                   |  <span data-ttu-id="7be60-341">7 und höher</span><span class="sxs-lookup"><span data-stu-id="7be60-341">7+</span></span>                     | <span data-ttu-id="7be60-342">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-342">x64</span></span> |
| <span data-ttu-id="7be60-343">Fedora</span><span class="sxs-lookup"><span data-stu-id="7be60-343">Fedora</span></span>                         |  <span data-ttu-id="7be60-344">30 und höher</span><span class="sxs-lookup"><span data-stu-id="7be60-344">30+</span></span>                    | <span data-ttu-id="7be60-345">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-345">x64</span></span> |
| <span data-ttu-id="7be60-346">Debian</span><span class="sxs-lookup"><span data-stu-id="7be60-346">Debian</span></span>                         |  <span data-ttu-id="7be60-347">9</span><span class="sxs-lookup"><span data-stu-id="7be60-347">9</span></span>                      | <span data-ttu-id="7be60-348">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="7be60-348">x64, ARM32</span></span> |
| <span data-ttu-id="7be60-349">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="7be60-349">Ubuntu</span></span>                         |  <span data-ttu-id="7be60-350">16.04, 18.04, 19.04, 19.10</span><span class="sxs-lookup"><span data-stu-id="7be60-350">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="7be60-351">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="7be60-351">x64, ARM32</span></span> |
| <span data-ttu-id="7be60-352">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="7be60-352">Linux Mint</span></span>                     |  <span data-ttu-id="7be60-353">17 oder höher</span><span class="sxs-lookup"><span data-stu-id="7be60-353">17+</span></span>                    | <span data-ttu-id="7be60-354">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-354">x64</span></span> |
| <span data-ttu-id="7be60-355">openSUSE</span><span class="sxs-lookup"><span data-stu-id="7be60-355">openSUSE</span></span>                       |  <span data-ttu-id="7be60-356">15 und höher</span><span class="sxs-lookup"><span data-stu-id="7be60-356">15+</span></span>                    | <span data-ttu-id="7be60-357">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-357">x64</span></span> |
| <span data-ttu-id="7be60-358">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="7be60-358">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="7be60-359">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="7be60-359">12 SP2+</span></span>                | <span data-ttu-id="7be60-360">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-360">x64</span></span> |
| <span data-ttu-id="7be60-361">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="7be60-361">Alpine Linux</span></span>                   |  <span data-ttu-id="7be60-362">3.8+</span><span class="sxs-lookup"><span data-stu-id="7be60-362">3.8+</span></span>                   | <span data-ttu-id="7be60-363">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-363">x64</span></span> |

<span data-ttu-id="7be60-364">Weitere Informationen zu den von .NET Core 2.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="7be60-364">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="7be60-365">Abhängigkeiten der Linux-Distributionen</span><span class="sxs-lookup"><span data-stu-id="7be60-365">Linux distribution dependencies</span></span>

<span data-ttu-id="7be60-366">Basierend auf den Linux-Verteilungen müssen Sie möglicherweise zusätzliche Abhängigkeiten installieren.</span><span class="sxs-lookup"><span data-stu-id="7be60-366">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7be60-367">Die exakten Versionen und Namen können sich bei der von Ihnen verwendeten Linux-Verteilung leicht unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="7be60-367">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="7be60-368">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="7be60-368">Ubuntu</span></span>

<span data-ttu-id="7be60-369">Für Ubuntu-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:</span><span class="sxs-lookup"><span data-stu-id="7be60-369">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="7be60-370">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="7be60-370">liblttng-ust0</span></span>
- <span data-ttu-id="7be60-371">libcurl3 (für 14.x und 16.x)</span><span class="sxs-lookup"><span data-stu-id="7be60-371">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="7be60-372">libcurl4 (für 18.x)</span><span class="sxs-lookup"><span data-stu-id="7be60-372">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="7be60-373">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="7be60-373">libssl1.0.0</span></span>
- <span data-ttu-id="7be60-374">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="7be60-374">libkrb5-3</span></span>
- <span data-ttu-id="7be60-375">zlib1g</span><span class="sxs-lookup"><span data-stu-id="7be60-375">zlib1g</span></span>
- <span data-ttu-id="7be60-376">libicu52 (für 14.X)</span><span class="sxs-lookup"><span data-stu-id="7be60-376">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="7be60-377">libicu55 (für 16.X)</span><span class="sxs-lookup"><span data-stu-id="7be60-377">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="7be60-378">libicu57 (für 17.X)</span><span class="sxs-lookup"><span data-stu-id="7be60-378">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="7be60-379">libicu60 (für 18.X)</span><span class="sxs-lookup"><span data-stu-id="7be60-379">libicu60 (for 18.x)</span></span>

<span data-ttu-id="7be60-380">Für .NET Core-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="7be60-380">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="7be60-381">libgdiplus (Version 6.0.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="7be60-381">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="7be60-382">Die meisten Versionen von Ubuntu enthalten eine frühere Version von libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="7be60-382">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="7be60-383">Sie können eine neuere Version von libgdiplus installieren, indem Sie auf Ihrem System das Mono-Repository hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7be60-383">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="7be60-384">Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="7be60-384">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="7be60-385">CentOS und Fedora</span><span class="sxs-lookup"><span data-stu-id="7be60-385">CentOS and Fedora</span></span>

<span data-ttu-id="7be60-386">Für CentOS-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:</span><span class="sxs-lookup"><span data-stu-id="7be60-386">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="7be60-387">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="7be60-387">lttng-ust</span></span>
- <span data-ttu-id="7be60-388">libcurl</span><span class="sxs-lookup"><span data-stu-id="7be60-388">libcurl</span></span>
- <span data-ttu-id="7be60-389">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="7be60-389">openssl-libs</span></span>
- <span data-ttu-id="7be60-390">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="7be60-390">krb5-libs</span></span>
- <span data-ttu-id="7be60-391">libicu</span><span class="sxs-lookup"><span data-stu-id="7be60-391">libicu</span></span>
- <span data-ttu-id="7be60-392">zlib</span><span class="sxs-lookup"><span data-stu-id="7be60-392">zlib</span></span>

<span data-ttu-id="7be60-393">Für Fedora-Benutzer: Wenn Ihre Version von OpenSSL Version 1.1 oder höher entspricht, müssen Sie **compat-openssl10** installieren.</span><span class="sxs-lookup"><span data-stu-id="7be60-393">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="7be60-394">Für .NET Core 2.0 sind außerdem die folgenden Abhängigkeiten erforderlich:</span><span class="sxs-lookup"><span data-stu-id="7be60-394">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="7be60-395">libunwind</span><span class="sxs-lookup"><span data-stu-id="7be60-395">libunwind</span></span>
- <span data-ttu-id="7be60-396">libuuid</span><span class="sxs-lookup"><span data-stu-id="7be60-396">libuuid</span></span>

<span data-ttu-id="7be60-397">Weitere Informationen zu den Abhängigkeiten finden Sie unter [Eigenständige Linux-Apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="7be60-397">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="7be60-398">Für .NET Core-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="7be60-398">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="7be60-399">libgdiplus (Version 6.0.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="7be60-399">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="7be60-400">Die meisten Versionen von CentOS und Fedora enthalten eine frühere Version von libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="7be60-400">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="7be60-401">Sie können eine neuere Version von libgdiplus installieren, indem Sie auf Ihrem System das Mono-Repository hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7be60-401">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="7be60-402">Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="7be60-402">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="alpine"></a><span data-ttu-id="7be60-403">Alpine</span><span class="sxs-lookup"><span data-stu-id="7be60-403">Alpine</span></span>

<span data-ttu-id="7be60-404">Für Alpine-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:</span><span class="sxs-lookup"><span data-stu-id="7be60-404">Alpine distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="7be60-405">icu-lisb (nicht erforderlich bei deaktivierter Globalisierung)</span><span class="sxs-lookup"><span data-stu-id="7be60-405">icu-libs (this is not needed if globalization is disabled)</span></span>
- <span data-ttu-id="7be60-406">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="7be60-406">krb5-libs</span></span>
- <span data-ttu-id="7be60-407">libcurl</span><span class="sxs-lookup"><span data-stu-id="7be60-407">libcurl</span></span>
- <span data-ttu-id="7be60-408">libintl</span><span class="sxs-lookup"><span data-stu-id="7be60-408">libintl</span></span>
- <span data-ttu-id="7be60-409">libssl1.1 (für Alpine 3.9 oder höher) oder libssl1.0 (für ältere Versionen)</span><span class="sxs-lookup"><span data-stu-id="7be60-409">libssl1.1 (for Alpine 3.9 or later) or libssl1.0 (for older ones)</span></span>
- <span data-ttu-id="7be60-410">libstdc++</span><span class="sxs-lookup"><span data-stu-id="7be60-410">libstdc++</span></span>
- <span data-ttu-id="7be60-411">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="7be60-411">lttng-ust</span></span>
- <span data-ttu-id="7be60-412">numactl (optional, nur für Geräte mit aktiviertem NUMA nützlich)</span><span class="sxs-lookup"><span data-stu-id="7be60-412">numactl (optional, useful only for devices with NUMA enabled)</span></span>
- <span data-ttu-id="7be60-413">zlib</span><span class="sxs-lookup"><span data-stu-id="7be60-413">zlib</span></span>

<span data-ttu-id="7be60-414">Für .NET Core-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="7be60-414">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="7be60-415">libgdiplus (nur im Edge/Testing-Repository verfügbar)</span><span class="sxs-lookup"><span data-stu-id="7be60-415">libgdiplus (it is available only in the edge/testing repository)</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="7be60-416">.NET Core wird von den folgenden macOS-Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7be60-416">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="7be60-417">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="7be60-417">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="7be60-418">.NET Core-Version</span><span class="sxs-lookup"><span data-stu-id="7be60-418">.NET Core Version</span></span> | <span data-ttu-id="7be60-419">macOS</span><span class="sxs-lookup"><span data-stu-id="7be60-419">macOS</span></span>                 | <span data-ttu-id="7be60-420">Architekturen</span><span class="sxs-lookup"><span data-stu-id="7be60-420">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="7be60-421">3.1</span><span class="sxs-lookup"><span data-stu-id="7be60-421">3.1</span></span>               | <span data-ttu-id="7be60-422">High Sierra (10.13 oder höher)</span><span class="sxs-lookup"><span data-stu-id="7be60-422">High Sierra (10.13+)</span></span>  | <span data-ttu-id="7be60-423">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-423">x64</span></span> | [<span data-ttu-id="7be60-424">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7be60-424">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="7be60-425">3.0</span><span class="sxs-lookup"><span data-stu-id="7be60-425">3.0</span></span>               | <span data-ttu-id="7be60-426">High Sierra (10.13 oder höher)</span><span class="sxs-lookup"><span data-stu-id="7be60-426">High Sierra (10.13+)</span></span>  | <span data-ttu-id="7be60-427">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-427">x64</span></span> | [<span data-ttu-id="7be60-428">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7be60-428">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="7be60-429">2.2</span><span class="sxs-lookup"><span data-stu-id="7be60-429">2.2</span></span>               | <span data-ttu-id="7be60-430">Sierra (10.12 oder höher)</span><span class="sxs-lookup"><span data-stu-id="7be60-430">Sierra (10.12+)</span></span>       | <span data-ttu-id="7be60-431">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-431">x64</span></span> | [<span data-ttu-id="7be60-432">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7be60-432">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="7be60-433">2.1</span><span class="sxs-lookup"><span data-stu-id="7be60-433">2.1</span></span>               | <span data-ttu-id="7be60-434">Sierra (10.12 oder höher)</span><span class="sxs-lookup"><span data-stu-id="7be60-434">Sierra (10.12+)</span></span>       | <span data-ttu-id="7be60-435">x64</span><span class="sxs-lookup"><span data-stu-id="7be60-435">x64</span></span> | [<span data-ttu-id="7be60-436">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7be60-436">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="7be60-437">Ab macOS Catalina (Version 10.15) muss jegliche Software notarisiert werden, die nach dem 1. Juni 2019 erstellt wurde und mit einer Entwickler-ID verteilt wird.</span><span class="sxs-lookup"><span data-stu-id="7be60-437">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="7be60-438">Diese Voraussetzung gilt für die .NET Core-Runtime, das .NET Core SDK und jegliche Software, die mit .NET Core erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="7be60-438">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="7be60-439">Die Installationsprogramme für die Versionen 3.1, 3.0 und 2.1 von .NET Core (sowohl für die Runtime als auch das SDK) wurden seit dem 18. Februar 2020 notarisiert.</span><span class="sxs-lookup"><span data-stu-id="7be60-439">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="7be60-440">Vorherige Versionen wurden nicht notarisiert.</span><span class="sxs-lookup"><span data-stu-id="7be60-440">Prior released versions aren't notarized.</span></span> <span data-ttu-id="7be60-441">Wenn Sie eine nicht notarisierte App ausführen, wird eine Fehlermeldung ähnlich der folgenden Abbildung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="7be60-441">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![macOS Catalina-Notarisierungswarnung](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="7be60-443">Weitere Informationen dazu, wie sich die erzwungene Notarisierung auf .NET Core (und Ihre .NET Core-Apps) auswirkt, finden Sie unter [Verwenden der macOS Catalina-Notarisierung](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7be60-443">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="7be60-444">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="7be60-444">libgdiplus</span></span>

<span data-ttu-id="7be60-445">Für .NET Core-Anwendungen, die die Assembly *System.Drawing.Common* verwenden, muss libgdiplus installiert sein.</span><span class="sxs-lookup"><span data-stu-id="7be60-445">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="7be60-446">Eine einfache Möglichkeit zum Abrufen von libgdiplus bietet der [Homebrew](https://brew.sh/)-Paket-Manager („brew“) für macOS.</span><span class="sxs-lookup"><span data-stu-id="7be60-446">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="7be60-447">Installieren Sie nach der Installation von *brew* libgdiplus durch Ausführen der folgenden Befehle in einem Terminal (Befehl):</span><span class="sxs-lookup"><span data-stu-id="7be60-447">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="7be60-448">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7be60-448">Next steps</span></span>

- <span data-ttu-id="7be60-449">Installieren Sie das [.NET Core SDK](sdk.md) (einschließlich der Runtime), um Apps zu entwickeln und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7be60-449">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="7be60-450">Installieren Sie die [.NET Core-Runtime](runtime.md), um von anderen erstellte Apps auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7be60-450">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
