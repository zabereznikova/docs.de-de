---
title: '.NET Core SDK und Runtimeabhängigkeiten: .NET Core'
description: In diesem Artikel werden die Voraussetzungen für das Betriebssystem und die CPU-Architektur zum Installieren des .NET Core SDK und der Runtime unter Windows, Linux und macOS erläutert.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 023b8fdf029dd6b17fe2186296d87dd7507c60b5
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546561"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="02daa-103">.NET Core-Abhängigkeiten und -Anforderungen</span><span class="sxs-lookup"><span data-stu-id="02daa-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="02daa-104">In diesem Artikel wird erläutert, welche Betriebssysteme und CPU-Architektur von .NET Core unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="02daa-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="02daa-105">Unterstützte Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="02daa-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="02daa-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="02daa-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="02daa-107">Die folgenden Windows-Versionen werden von .NET Core 3.1 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="02daa-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="02daa-108">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="02daa-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="02daa-109">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="02daa-109">OS</span></span>                            | <span data-ttu-id="02daa-110">Version</span><span class="sxs-lookup"><span data-stu-id="02daa-110">Version</span></span>                        | <span data-ttu-id="02daa-111">Architekturen</span><span class="sxs-lookup"><span data-stu-id="02daa-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="02daa-112">Windows-Client</span><span class="sxs-lookup"><span data-stu-id="02daa-112">Windows Client</span></span>                | <span data-ttu-id="02daa-113">7 SP1 oder höher, 8.1</span><span class="sxs-lookup"><span data-stu-id="02daa-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="02daa-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="02daa-114">x64, x86</span></span>        |
| <span data-ttu-id="02daa-115">Windows 10-Client</span><span class="sxs-lookup"><span data-stu-id="02daa-115">Windows 10 Client</span></span>             | <span data-ttu-id="02daa-116">Version 1607 oder höher</span><span class="sxs-lookup"><span data-stu-id="02daa-116">Version 1607+</span></span>                  | <span data-ttu-id="02daa-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="02daa-117">x64, x86</span></span>        |
| <span data-ttu-id="02daa-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="02daa-118">Windows Server</span></span>                | <span data-ttu-id="02daa-119">2012 R2 oder höher</span><span class="sxs-lookup"><span data-stu-id="02daa-119">2012 R2+</span></span>                       | <span data-ttu-id="02daa-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="02daa-120">x64, x86</span></span>        |
| <span data-ttu-id="02daa-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="02daa-121">Nano Server</span></span>                   | <span data-ttu-id="02daa-122">Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="02daa-122">Version 1803+</span></span>                  | <span data-ttu-id="02daa-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="02daa-123">x64, ARM32</span></span>      |

<span data-ttu-id="02daa-124">Weitere Informationen zu den von .NET Core 3.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="02daa-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="02daa-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="02daa-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="02daa-126">*.NET Core 3.0 wird aktuell nicht unterstützt. Weitere Informationen finden Sie in der [Supportrichtlinie für .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="02daa-126">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="02daa-127">Die folgenden Windows-Versionen werden von .NET Core 3.0 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="02daa-127">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="02daa-128">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="02daa-128">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="02daa-129">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="02daa-129">OS</span></span>                            | <span data-ttu-id="02daa-130">Version</span><span class="sxs-lookup"><span data-stu-id="02daa-130">Version</span></span>                        | <span data-ttu-id="02daa-131">Architekturen</span><span class="sxs-lookup"><span data-stu-id="02daa-131">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="02daa-132">Windows-Client</span><span class="sxs-lookup"><span data-stu-id="02daa-132">Windows Client</span></span>                | <span data-ttu-id="02daa-133">7 SP1 oder höher, 8.1</span><span class="sxs-lookup"><span data-stu-id="02daa-133">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="02daa-134">x64, x86</span><span class="sxs-lookup"><span data-stu-id="02daa-134">x64, x86</span></span>        |
| <span data-ttu-id="02daa-135">Windows 10-Client</span><span class="sxs-lookup"><span data-stu-id="02daa-135">Windows 10 Client</span></span>             | <span data-ttu-id="02daa-136">Version 1607 oder höher</span><span class="sxs-lookup"><span data-stu-id="02daa-136">Version 1607+</span></span>                  | <span data-ttu-id="02daa-137">x64, x86</span><span class="sxs-lookup"><span data-stu-id="02daa-137">x64, x86</span></span>        |
| <span data-ttu-id="02daa-138">Windows Server</span><span class="sxs-lookup"><span data-stu-id="02daa-138">Windows Server</span></span>                | <span data-ttu-id="02daa-139">2012 R2 oder höher</span><span class="sxs-lookup"><span data-stu-id="02daa-139">2012 R2+</span></span>                       | <span data-ttu-id="02daa-140">x64, x86</span><span class="sxs-lookup"><span data-stu-id="02daa-140">x64, x86</span></span>        |
| <span data-ttu-id="02daa-141">Nano Server</span><span class="sxs-lookup"><span data-stu-id="02daa-141">Nano Server</span></span>                   | <span data-ttu-id="02daa-142">Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="02daa-142">Version 1803+</span></span>                  | <span data-ttu-id="02daa-143">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="02daa-143">x64, ARM32</span></span>      |

<span data-ttu-id="02daa-144">Weitere Informationen zu den von .NET Core 3.0 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.0 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="02daa-144">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="02daa-145">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="02daa-145">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="02daa-146">*.NET Core 2.2 wird aktuell nicht unterstützt. Weitere Informationen finden Sie in der [Supportrichtlinie für .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="02daa-146">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="02daa-147">Die folgenden Windows-Versionen werden von .NET Core 2.2 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="02daa-147">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="02daa-148">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="02daa-148">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="02daa-149">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="02daa-149">OS</span></span>                            | <span data-ttu-id="02daa-150">Version</span><span class="sxs-lookup"><span data-stu-id="02daa-150">Version</span></span>                        | <span data-ttu-id="02daa-151">Architekturen</span><span class="sxs-lookup"><span data-stu-id="02daa-151">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="02daa-152">Windows-Client</span><span class="sxs-lookup"><span data-stu-id="02daa-152">Windows Client</span></span>                | <span data-ttu-id="02daa-153">7 SP1 oder höher, 8.1</span><span class="sxs-lookup"><span data-stu-id="02daa-153">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="02daa-154">x64, x86</span><span class="sxs-lookup"><span data-stu-id="02daa-154">x64, x86</span></span>        |
| <span data-ttu-id="02daa-155">Windows 10-Client</span><span class="sxs-lookup"><span data-stu-id="02daa-155">Windows 10 Client</span></span>             | <span data-ttu-id="02daa-156">Version 1607 oder höher</span><span class="sxs-lookup"><span data-stu-id="02daa-156">Version 1607+</span></span>                  | <span data-ttu-id="02daa-157">x64, x86</span><span class="sxs-lookup"><span data-stu-id="02daa-157">x64, x86</span></span>        |
| <span data-ttu-id="02daa-158">Windows Server</span><span class="sxs-lookup"><span data-stu-id="02daa-158">Windows Server</span></span>                | <span data-ttu-id="02daa-159">2008 R2 SP1 oder höher</span><span class="sxs-lookup"><span data-stu-id="02daa-159">2008 R2 SP1+</span></span>                   | <span data-ttu-id="02daa-160">x64, x86</span><span class="sxs-lookup"><span data-stu-id="02daa-160">x64, x86</span></span>        |
| <span data-ttu-id="02daa-161">Nano Server</span><span class="sxs-lookup"><span data-stu-id="02daa-161">Nano Server</span></span>                   | <span data-ttu-id="02daa-162">Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="02daa-162">Version 1803+</span></span>                   | <span data-ttu-id="02daa-163">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="02daa-163">x64, ARM32</span></span>      |

<span data-ttu-id="02daa-164">Weitere Informationen zu den von .NET Core 2.2 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.2 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="02daa-164">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="02daa-165">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="02daa-165">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="02daa-166">Die folgenden Windows-Versionen werden von .NET Core 2.1 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="02daa-166">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="02daa-167">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="02daa-167">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="02daa-168">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="02daa-168">OS</span></span>                            | <span data-ttu-id="02daa-169">Version</span><span class="sxs-lookup"><span data-stu-id="02daa-169">Version</span></span>                        | <span data-ttu-id="02daa-170">Architekturen</span><span class="sxs-lookup"><span data-stu-id="02daa-170">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="02daa-171">Windows-Client</span><span class="sxs-lookup"><span data-stu-id="02daa-171">Windows Client</span></span>                | <span data-ttu-id="02daa-172">7 SP1 oder höher, 8.1</span><span class="sxs-lookup"><span data-stu-id="02daa-172">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="02daa-173">x64, x86</span><span class="sxs-lookup"><span data-stu-id="02daa-173">x64, x86</span></span>        |
| <span data-ttu-id="02daa-174">Windows 10-Client</span><span class="sxs-lookup"><span data-stu-id="02daa-174">Windows 10 Client</span></span>             | <span data-ttu-id="02daa-175">Version 1607 oder höher</span><span class="sxs-lookup"><span data-stu-id="02daa-175">Version 1607+</span></span>                  | <span data-ttu-id="02daa-176">x64, x86</span><span class="sxs-lookup"><span data-stu-id="02daa-176">x64, x86</span></span>        |
| <span data-ttu-id="02daa-177">Windows Server</span><span class="sxs-lookup"><span data-stu-id="02daa-177">Windows Server</span></span>                | <span data-ttu-id="02daa-178">2008 R2 SP1 oder höher</span><span class="sxs-lookup"><span data-stu-id="02daa-178">2008 R2 SP1+</span></span>                   | <span data-ttu-id="02daa-179">x64, x86</span><span class="sxs-lookup"><span data-stu-id="02daa-179">x64, x86</span></span>        |
| <span data-ttu-id="02daa-180">Nano Server</span><span class="sxs-lookup"><span data-stu-id="02daa-180">Nano Server</span></span>                   | <span data-ttu-id="02daa-181">Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="02daa-181">Version 1803+</span></span>                  | <span data-ttu-id="02daa-182">x64,</span><span class="sxs-lookup"><span data-stu-id="02daa-182">x64,</span></span>            |

<span data-ttu-id="02daa-183">Weitere Informationen zu den von .NET Core 2.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="02daa-183">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="02daa-184">Windows 7/Vista/8.1/Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="02daa-184">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="02daa-185">Weitere Abhängigkeiten sind erforderlich, wenn Sie das .NET SDK oder die Runtime unter den folgenden Windows-Versionen installieren:</span><span class="sxs-lookup"><span data-stu-id="02daa-185">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="02daa-186">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="02daa-186">Windows 7 SP1</span></span>
- <span data-ttu-id="02daa-187">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="02daa-187">Windows Vista SP 2</span></span>
- <span data-ttu-id="02daa-188">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="02daa-188">Windows 8.1</span></span>
- <span data-ttu-id="02daa-189">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="02daa-189">Windows Server 2008 R2</span></span>
- <span data-ttu-id="02daa-190">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="02daa-190">Windows Server 2012 R2</span></span>

<span data-ttu-id="02daa-191">Installieren Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="02daa-191">Install the following:</span></span>

- <span data-ttu-id="02daa-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685)</span><span class="sxs-lookup"><span data-stu-id="02daa-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="02daa-193">KB2533623</span><span class="sxs-lookup"><span data-stu-id="02daa-193">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="02daa-194">Die oben aufgeführten Anforderungen sind auch erforderlich, wenn einer der folgenden Fehler auftritt:</span><span class="sxs-lookup"><span data-stu-id="02daa-194">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="02daa-195">Das Programm kann nicht gestartet werden, da *api-ms-win-crt-runtime-l1-1-0.dll* auf dem Computer fehlt.</span><span class="sxs-lookup"><span data-stu-id="02daa-195">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="02daa-196">Installieren Sie das Programm erneut, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="02daa-196">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="02daa-197">\- oder -</span><span class="sxs-lookup"><span data-stu-id="02daa-197">\- or -</span></span>
>
> <span data-ttu-id="02daa-198">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed. (Die Bibliothek „hostfxr.dll“ wurde gefunden, aber der Ladevorgang aus C:\<Pfad_zu_App>\hostfxr.dll ist fehlgeschlagen.)</span><span class="sxs-lookup"><span data-stu-id="02daa-198">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="02daa-199">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="02daa-199">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="02daa-200">.NET Core 3.1 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="02daa-200">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="02daa-201">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="02daa-201">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="02daa-202">.NET Core 3.1 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="02daa-202">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="02daa-203">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="02daa-203">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="02daa-204">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="02daa-204">OS</span></span>                             | <span data-ttu-id="02daa-205">Version</span><span class="sxs-lookup"><span data-stu-id="02daa-205">Version</span></span>               | <span data-ttu-id="02daa-206">Architekturen</span><span class="sxs-lookup"><span data-stu-id="02daa-206">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="02daa-207">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="02daa-207">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="02daa-208">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="02daa-208">6, 7, 8</span></span>               | <span data-ttu-id="02daa-209">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-209">x64</span></span> |
| <span data-ttu-id="02daa-210">CentOS</span><span class="sxs-lookup"><span data-stu-id="02daa-210">CentOS</span></span>                         | <span data-ttu-id="02daa-211">7 und höher</span><span class="sxs-lookup"><span data-stu-id="02daa-211">7+</span></span>                    | <span data-ttu-id="02daa-212">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-212">x64</span></span> |
| <span data-ttu-id="02daa-213">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="02daa-213">Oracle Linux</span></span>                   | <span data-ttu-id="02daa-214">7 und höher</span><span class="sxs-lookup"><span data-stu-id="02daa-214">7+</span></span>                    | <span data-ttu-id="02daa-215">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-215">x64</span></span> |
| <span data-ttu-id="02daa-216">Fedora</span><span class="sxs-lookup"><span data-stu-id="02daa-216">Fedora</span></span>                         | <span data-ttu-id="02daa-217">30 und höher</span><span class="sxs-lookup"><span data-stu-id="02daa-217">30+</span></span>                   | <span data-ttu-id="02daa-218">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-218">x64</span></span> |
| <span data-ttu-id="02daa-219">Debian</span><span class="sxs-lookup"><span data-stu-id="02daa-219">Debian</span></span>                         | <span data-ttu-id="02daa-220">9 und höher</span><span class="sxs-lookup"><span data-stu-id="02daa-220">9+</span></span>                    | <span data-ttu-id="02daa-221">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="02daa-221">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="02daa-222">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="02daa-222">Ubuntu</span></span>                         | <span data-ttu-id="02daa-223">16.04 und höher</span><span class="sxs-lookup"><span data-stu-id="02daa-223">16.04+</span></span>                | <span data-ttu-id="02daa-224">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="02daa-224">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="02daa-225">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="02daa-225">Linux Mint</span></span>                     | <span data-ttu-id="02daa-226">18 und höher</span><span class="sxs-lookup"><span data-stu-id="02daa-226">18+</span></span>                   | <span data-ttu-id="02daa-227">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-227">x64</span></span> |
| <span data-ttu-id="02daa-228">openSUSE</span><span class="sxs-lookup"><span data-stu-id="02daa-228">openSUSE</span></span>                       | <span data-ttu-id="02daa-229">15 und höher</span><span class="sxs-lookup"><span data-stu-id="02daa-229">15+</span></span>                   | <span data-ttu-id="02daa-230">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-230">x64</span></span> |
| <span data-ttu-id="02daa-231">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="02daa-231">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="02daa-232">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="02daa-232">12 SP2+</span></span>               | <span data-ttu-id="02daa-233">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-233">x64</span></span> |
| <span data-ttu-id="02daa-234">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="02daa-234">Alpine Linux</span></span>                   | <span data-ttu-id="02daa-235">3.10 oder höher</span><span class="sxs-lookup"><span data-stu-id="02daa-235">3.10+</span></span>                 | <span data-ttu-id="02daa-236">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="02daa-236">x64, ARM64</span></span> |

<span data-ttu-id="02daa-237">Weitere Informationen zu den von .NET Core 3.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="02daa-237">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="02daa-238">Weitere Informationen zum Installieren von .NET Core 3.1 unter ARM64 (Kernel 4.14 oder höher) finden Sie unter [Installieren von .NET Core 3.0 unter Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span><span class="sxs-lookup"><span data-stu-id="02daa-238">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02daa-239">Für die Unterstützung von ARM64 ist Linux-Kernel 4.14 oder höher erforderlich.</span><span class="sxs-lookup"><span data-stu-id="02daa-239">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="02daa-240">Einige Linux-Verteilungen erfüllen diese Anforderung, andere hingegen nicht.</span><span class="sxs-lookup"><span data-stu-id="02daa-240">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="02daa-241">So wird Ubuntu 18.04 im Gegensatz zu Ubuntu 16.04 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="02daa-241">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="02daa-242">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="02daa-242">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="02daa-243">*.NET Core 3.0 wird aktuell nicht unterstützt. Weitere Informationen finden Sie in der [Supportrichtlinie für .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="02daa-243">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="02daa-244">.NET Core 3.0 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="02daa-244">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="02daa-245">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="02daa-245">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="02daa-246">.NET Core 3.0 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="02daa-246">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="02daa-247">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="02daa-247">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="02daa-248">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="02daa-248">OS</span></span>                             | <span data-ttu-id="02daa-249">Version</span><span class="sxs-lookup"><span data-stu-id="02daa-249">Version</span></span>               | <span data-ttu-id="02daa-250">Architekturen</span><span class="sxs-lookup"><span data-stu-id="02daa-250">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="02daa-251">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="02daa-251">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="02daa-252">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="02daa-252">6, 7, 8</span></span>               | <span data-ttu-id="02daa-253">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-253">x64</span></span> |
| <span data-ttu-id="02daa-254">CentOS</span><span class="sxs-lookup"><span data-stu-id="02daa-254">CentOS</span></span>                         | <span data-ttu-id="02daa-255">7 und höher</span><span class="sxs-lookup"><span data-stu-id="02daa-255">7+</span></span>                    | <span data-ttu-id="02daa-256">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-256">x64</span></span> |
| <span data-ttu-id="02daa-257">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="02daa-257">Oracle Linux</span></span>                   | <span data-ttu-id="02daa-258">7 und höher</span><span class="sxs-lookup"><span data-stu-id="02daa-258">7+</span></span>                    | <span data-ttu-id="02daa-259">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-259">x64</span></span> |
| <span data-ttu-id="02daa-260">Fedora</span><span class="sxs-lookup"><span data-stu-id="02daa-260">Fedora</span></span>                         | <span data-ttu-id="02daa-261">29 und höher</span><span class="sxs-lookup"><span data-stu-id="02daa-261">29+</span></span>                   | <span data-ttu-id="02daa-262">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-262">x64</span></span> |
| <span data-ttu-id="02daa-263">Debian</span><span class="sxs-lookup"><span data-stu-id="02daa-263">Debian</span></span>                         | <span data-ttu-id="02daa-264">9 und höher</span><span class="sxs-lookup"><span data-stu-id="02daa-264">9+</span></span>                    | <span data-ttu-id="02daa-265">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="02daa-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="02daa-266">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="02daa-266">Ubuntu</span></span>                         | <span data-ttu-id="02daa-267">16.04 und höher</span><span class="sxs-lookup"><span data-stu-id="02daa-267">16.04+</span></span>                | <span data-ttu-id="02daa-268">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="02daa-268">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="02daa-269">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="02daa-269">Linux Mint</span></span>                     | <span data-ttu-id="02daa-270">18 und höher</span><span class="sxs-lookup"><span data-stu-id="02daa-270">18+</span></span>                   | <span data-ttu-id="02daa-271">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-271">x64</span></span> |
| <span data-ttu-id="02daa-272">openSUSE</span><span class="sxs-lookup"><span data-stu-id="02daa-272">openSUSE</span></span>                       | <span data-ttu-id="02daa-273">15 und höher</span><span class="sxs-lookup"><span data-stu-id="02daa-273">15+</span></span>                   | <span data-ttu-id="02daa-274">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-274">x64</span></span> |
| <span data-ttu-id="02daa-275">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="02daa-275">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="02daa-276">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="02daa-276">12 SP2+</span></span>               | <span data-ttu-id="02daa-277">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-277">x64</span></span> |
| <span data-ttu-id="02daa-278">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="02daa-278">Alpine Linux</span></span>                   | <span data-ttu-id="02daa-279">3.8+</span><span class="sxs-lookup"><span data-stu-id="02daa-279">3.8+</span></span>                  | <span data-ttu-id="02daa-280">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="02daa-280">x64, ARM64</span></span> |

<span data-ttu-id="02daa-281">Weitere Informationen zu den von .NET Core 3.0 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.0 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="02daa-281">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="02daa-282">Weitere Informationen zum Installieren von .NET Core 3.0 unter ARM64 finden Sie unter [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Installieren von .NET Core 3.0 unter Linux ARM64).</span><span class="sxs-lookup"><span data-stu-id="02daa-282">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="02daa-283">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="02daa-283">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="02daa-284">*.NET Core 2.2 wird aktuell nicht unterstützt. Weitere Informationen finden Sie in der [Supportrichtlinie für .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="02daa-284">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="02daa-285">.NET Core 2.2 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="02daa-285">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="02daa-286">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="02daa-286">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="02daa-287">.NET Core 2.2 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="02daa-287">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="02daa-288">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="02daa-288">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="02daa-289">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="02daa-289">OS</span></span>                             |  <span data-ttu-id="02daa-290">Version</span><span class="sxs-lookup"><span data-stu-id="02daa-290">Version</span></span>                |  <span data-ttu-id="02daa-291">Architekturen</span><span class="sxs-lookup"><span data-stu-id="02daa-291">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="02daa-292">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="02daa-292">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="02daa-293">6, 7</span><span class="sxs-lookup"><span data-stu-id="02daa-293">6, 7</span></span>                   | <span data-ttu-id="02daa-294">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-294">x64</span></span> |
| <span data-ttu-id="02daa-295">CentOS</span><span class="sxs-lookup"><span data-stu-id="02daa-295">CentOS</span></span>                         |  <span data-ttu-id="02daa-296">7</span><span class="sxs-lookup"><span data-stu-id="02daa-296">7</span></span>                      | <span data-ttu-id="02daa-297">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-297">x64</span></span> |
| <span data-ttu-id="02daa-298">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="02daa-298">Oracle Linux</span></span>                   |  <span data-ttu-id="02daa-299">7</span><span class="sxs-lookup"><span data-stu-id="02daa-299">7</span></span>                      | <span data-ttu-id="02daa-300">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-300">x64</span></span> |
| <span data-ttu-id="02daa-301">Fedora</span><span class="sxs-lookup"><span data-stu-id="02daa-301">Fedora</span></span>                         |  <span data-ttu-id="02daa-302">29, 30</span><span class="sxs-lookup"><span data-stu-id="02daa-302">29, 30</span></span>                 | <span data-ttu-id="02daa-303">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-303">x64</span></span> |
| <span data-ttu-id="02daa-304">Debian</span><span class="sxs-lookup"><span data-stu-id="02daa-304">Debian</span></span>                         |  <span data-ttu-id="02daa-305">9</span><span class="sxs-lookup"><span data-stu-id="02daa-305">9</span></span>                      | <span data-ttu-id="02daa-306">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="02daa-306">x64, ARM32</span></span> |
| <span data-ttu-id="02daa-307">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="02daa-307">Ubuntu</span></span>                         |  <span data-ttu-id="02daa-308">16.04, 18.04, 18.10</span><span class="sxs-lookup"><span data-stu-id="02daa-308">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="02daa-309">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="02daa-309">x64, ARM32</span></span> |
| <span data-ttu-id="02daa-310">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="02daa-310">Linux Mint</span></span>                     |  <span data-ttu-id="02daa-311">17, 18</span><span class="sxs-lookup"><span data-stu-id="02daa-311">17, 18</span></span>                 | <span data-ttu-id="02daa-312">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-312">x64</span></span> |
| <span data-ttu-id="02daa-313">openSUSE</span><span class="sxs-lookup"><span data-stu-id="02daa-313">openSUSE</span></span>                       |  <span data-ttu-id="02daa-314">15 und höher</span><span class="sxs-lookup"><span data-stu-id="02daa-314">15+</span></span>                    | <span data-ttu-id="02daa-315">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-315">x64</span></span> |
| <span data-ttu-id="02daa-316">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="02daa-316">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="02daa-317">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="02daa-317">12 SP2+</span></span>                | <span data-ttu-id="02daa-318">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-318">x64</span></span> |
| <span data-ttu-id="02daa-319">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="02daa-319">Alpine Linux</span></span>                   |  <span data-ttu-id="02daa-320">3.8+</span><span class="sxs-lookup"><span data-stu-id="02daa-320">3.8+</span></span>                   | <span data-ttu-id="02daa-321">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-321">x64</span></span> |

<span data-ttu-id="02daa-322">Weitere Informationen zu den von .NET Core 2.2 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.2 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="02daa-322">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="02daa-323">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="02daa-323">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="02daa-324">.NET Core 2.1 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="02daa-324">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="02daa-325">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="02daa-325">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="02daa-326">.NET Core 2.1 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="02daa-326">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="02daa-327">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="02daa-327">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="02daa-328">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="02daa-328">OS</span></span>                             |  <span data-ttu-id="02daa-329">Version</span><span class="sxs-lookup"><span data-stu-id="02daa-329">Version</span></span>                |  <span data-ttu-id="02daa-330">Architekturen</span><span class="sxs-lookup"><span data-stu-id="02daa-330">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="02daa-331">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="02daa-331">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="02daa-332">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="02daa-332">6, 7, 8</span></span>                | <span data-ttu-id="02daa-333">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-333">x64</span></span> |
| <span data-ttu-id="02daa-334">CentOS</span><span class="sxs-lookup"><span data-stu-id="02daa-334">CentOS</span></span>                         |  <span data-ttu-id="02daa-335">7 und höher</span><span class="sxs-lookup"><span data-stu-id="02daa-335">7+</span></span>                     | <span data-ttu-id="02daa-336">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-336">x64</span></span> |
| <span data-ttu-id="02daa-337">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="02daa-337">Oracle Linux</span></span>                   |  <span data-ttu-id="02daa-338">7 und höher</span><span class="sxs-lookup"><span data-stu-id="02daa-338">7+</span></span>                     | <span data-ttu-id="02daa-339">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-339">x64</span></span> |
| <span data-ttu-id="02daa-340">Fedora</span><span class="sxs-lookup"><span data-stu-id="02daa-340">Fedora</span></span>                         |  <span data-ttu-id="02daa-341">30 und höher</span><span class="sxs-lookup"><span data-stu-id="02daa-341">30+</span></span>                    | <span data-ttu-id="02daa-342">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-342">x64</span></span> |
| <span data-ttu-id="02daa-343">Debian</span><span class="sxs-lookup"><span data-stu-id="02daa-343">Debian</span></span>                         |  <span data-ttu-id="02daa-344">9</span><span class="sxs-lookup"><span data-stu-id="02daa-344">9</span></span>                      | <span data-ttu-id="02daa-345">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="02daa-345">x64, ARM32</span></span> |
| <span data-ttu-id="02daa-346">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="02daa-346">Ubuntu</span></span>                         |  <span data-ttu-id="02daa-347">16.04, 18.04, 19.04, 19.10</span><span class="sxs-lookup"><span data-stu-id="02daa-347">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="02daa-348">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="02daa-348">x64, ARM32</span></span> |
| <span data-ttu-id="02daa-349">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="02daa-349">Linux Mint</span></span>                     |  <span data-ttu-id="02daa-350">17 oder höher</span><span class="sxs-lookup"><span data-stu-id="02daa-350">17+</span></span>                    | <span data-ttu-id="02daa-351">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-351">x64</span></span> |
| <span data-ttu-id="02daa-352">openSUSE</span><span class="sxs-lookup"><span data-stu-id="02daa-352">openSUSE</span></span>                       |  <span data-ttu-id="02daa-353">15 und höher</span><span class="sxs-lookup"><span data-stu-id="02daa-353">15+</span></span>                    | <span data-ttu-id="02daa-354">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-354">x64</span></span> |
| <span data-ttu-id="02daa-355">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="02daa-355">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="02daa-356">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="02daa-356">12 SP2+</span></span>                | <span data-ttu-id="02daa-357">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-357">x64</span></span> |
| <span data-ttu-id="02daa-358">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="02daa-358">Alpine Linux</span></span>                   |  <span data-ttu-id="02daa-359">3.8+</span><span class="sxs-lookup"><span data-stu-id="02daa-359">3.8+</span></span>                   | <span data-ttu-id="02daa-360">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-360">x64</span></span> |

<span data-ttu-id="02daa-361">Weitere Informationen zu den von .NET Core 2.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="02daa-361">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="02daa-362">Abhängigkeiten der Linux-Distributionen</span><span class="sxs-lookup"><span data-stu-id="02daa-362">Linux distribution dependencies</span></span>

<span data-ttu-id="02daa-363">Basierend auf den Linux-Verteilungen müssen Sie möglicherweise zusätzliche Abhängigkeiten installieren.</span><span class="sxs-lookup"><span data-stu-id="02daa-363">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02daa-364">Die exakten Versionen und Namen können sich bei der von Ihnen verwendeten Linux-Verteilung leicht unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="02daa-364">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="02daa-365">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="02daa-365">Ubuntu</span></span>

<span data-ttu-id="02daa-366">Für Ubuntu-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:</span><span class="sxs-lookup"><span data-stu-id="02daa-366">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="02daa-367">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="02daa-367">liblttng-ust0</span></span>
- <span data-ttu-id="02daa-368">libcurl3 (für 14.x und 16.x)</span><span class="sxs-lookup"><span data-stu-id="02daa-368">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="02daa-369">libcurl4 (für 18.x)</span><span class="sxs-lookup"><span data-stu-id="02daa-369">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="02daa-370">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="02daa-370">libssl1.0.0</span></span>
- <span data-ttu-id="02daa-371">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="02daa-371">libkrb5-3</span></span>
- <span data-ttu-id="02daa-372">zlib1g</span><span class="sxs-lookup"><span data-stu-id="02daa-372">zlib1g</span></span>
- <span data-ttu-id="02daa-373">libicu52 (für 14.X)</span><span class="sxs-lookup"><span data-stu-id="02daa-373">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="02daa-374">libicu55 (für 16.X)</span><span class="sxs-lookup"><span data-stu-id="02daa-374">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="02daa-375">libicu57 (für 17.X)</span><span class="sxs-lookup"><span data-stu-id="02daa-375">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="02daa-376">libicu60 (für 18.X)</span><span class="sxs-lookup"><span data-stu-id="02daa-376">libicu60 (for 18.x)</span></span>

<span data-ttu-id="02daa-377">Für .NET Core-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="02daa-377">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="02daa-378">libgdiplus (Version 6.0.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="02daa-378">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="02daa-379">Die meisten Versionen von Ubuntu enthalten eine frühere Version von libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="02daa-379">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="02daa-380">Sie können eine neuere Version von libgdiplus installieren, indem Sie auf Ihrem System das Mono-Repository hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="02daa-380">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="02daa-381">Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="02daa-381">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="02daa-382">CentOS und Fedora</span><span class="sxs-lookup"><span data-stu-id="02daa-382">CentOS and Fedora</span></span>

<span data-ttu-id="02daa-383">Für CentOS-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:</span><span class="sxs-lookup"><span data-stu-id="02daa-383">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="02daa-384">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="02daa-384">lttng-ust</span></span>
- <span data-ttu-id="02daa-385">libcurl</span><span class="sxs-lookup"><span data-stu-id="02daa-385">libcurl</span></span>
- <span data-ttu-id="02daa-386">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="02daa-386">openssl-libs</span></span>
- <span data-ttu-id="02daa-387">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="02daa-387">krb5-libs</span></span>
- <span data-ttu-id="02daa-388">libicu</span><span class="sxs-lookup"><span data-stu-id="02daa-388">libicu</span></span>
- <span data-ttu-id="02daa-389">zlib</span><span class="sxs-lookup"><span data-stu-id="02daa-389">zlib</span></span>

<span data-ttu-id="02daa-390">Für Fedora-Benutzer: Wenn Ihre Version von OpenSSL Version 1.1 oder höher entspricht, müssen Sie **compat-openssl10** installieren.</span><span class="sxs-lookup"><span data-stu-id="02daa-390">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="02daa-391">Für .NET Core 2.0 sind außerdem die folgenden Abhängigkeiten erforderlich:</span><span class="sxs-lookup"><span data-stu-id="02daa-391">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="02daa-392">libunwind</span><span class="sxs-lookup"><span data-stu-id="02daa-392">libunwind</span></span>
- <span data-ttu-id="02daa-393">libuuid</span><span class="sxs-lookup"><span data-stu-id="02daa-393">libuuid</span></span>

<span data-ttu-id="02daa-394">Weitere Informationen zu den Abhängigkeiten finden Sie unter [Eigenständige Linux-Apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="02daa-394">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="02daa-395">Für .NET Core-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="02daa-395">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="02daa-396">libgdiplus (Version 6.0.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="02daa-396">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="02daa-397">Die meisten Versionen von CentOS und Fedora enthalten eine frühere Version von libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="02daa-397">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="02daa-398">Sie können eine neuere Version von libgdiplus installieren, indem Sie auf Ihrem System das Mono-Repository hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="02daa-398">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="02daa-399">Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="02daa-399">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="02daa-400">.NET Core wird von den folgenden macOS-Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="02daa-400">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="02daa-401">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="02daa-401">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="02daa-402">.NET Core-Version</span><span class="sxs-lookup"><span data-stu-id="02daa-402">.NET Core Version</span></span> | <span data-ttu-id="02daa-403">macOS</span><span class="sxs-lookup"><span data-stu-id="02daa-403">macOS</span></span>                 | <span data-ttu-id="02daa-404">Architekturen</span><span class="sxs-lookup"><span data-stu-id="02daa-404">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="02daa-405">3.1</span><span class="sxs-lookup"><span data-stu-id="02daa-405">3.1</span></span>               | <span data-ttu-id="02daa-406">High Sierra (10.13 oder höher)</span><span class="sxs-lookup"><span data-stu-id="02daa-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="02daa-407">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-407">x64</span></span> | [<span data-ttu-id="02daa-408">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02daa-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="02daa-409">3.0</span><span class="sxs-lookup"><span data-stu-id="02daa-409">3.0</span></span>               | <span data-ttu-id="02daa-410">High Sierra (10.13 oder höher)</span><span class="sxs-lookup"><span data-stu-id="02daa-410">High Sierra (10.13+)</span></span>  | <span data-ttu-id="02daa-411">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-411">x64</span></span> | [<span data-ttu-id="02daa-412">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02daa-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="02daa-413">2.2</span><span class="sxs-lookup"><span data-stu-id="02daa-413">2.2</span></span>               | <span data-ttu-id="02daa-414">Sierra (10.12 oder höher)</span><span class="sxs-lookup"><span data-stu-id="02daa-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="02daa-415">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-415">x64</span></span> | [<span data-ttu-id="02daa-416">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02daa-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="02daa-417">2.1</span><span class="sxs-lookup"><span data-stu-id="02daa-417">2.1</span></span>               | <span data-ttu-id="02daa-418">Sierra (10.12 oder höher)</span><span class="sxs-lookup"><span data-stu-id="02daa-418">Sierra (10.12+)</span></span>       | <span data-ttu-id="02daa-419">x64</span><span class="sxs-lookup"><span data-stu-id="02daa-419">x64</span></span> | [<span data-ttu-id="02daa-420">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02daa-420">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="02daa-421">Ab macOS Catalina (Version 10.15) muss jegliche Software notarisiert werden, die nach dem 1. Juni 2019 erstellt wurde und mit einer Entwickler-ID verteilt wird.</span><span class="sxs-lookup"><span data-stu-id="02daa-421">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="02daa-422">Diese Voraussetzung gilt für die .NET Core-Runtime, das .NET Core SDK und jegliche Software, die mit .NET Core erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="02daa-422">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="02daa-423">Die Installationsprogramme für die Versionen 3.1, 3.0 und 2.1 von .NET Core (sowohl für die Runtime als auch das SDK) wurden seit dem 18. Februar 2020 notarisiert.</span><span class="sxs-lookup"><span data-stu-id="02daa-423">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="02daa-424">Vorherige Versionen wurden nicht notarisiert.</span><span class="sxs-lookup"><span data-stu-id="02daa-424">Prior released versions aren't notarized.</span></span> <span data-ttu-id="02daa-425">Wenn Sie eine nicht notarisierte App ausführen, wird eine Fehlermeldung ähnlich der folgenden Abbildung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="02daa-425">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![macOS Catalina-Notarisierungswarnung](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="02daa-427">Weitere Informationen dazu, wie sich die erzwungene Notarisierung auf .NET Core (und Ihre .NET Core-Apps) auswirkt, finden Sie unter [Verwenden der macOS Catalina-Notarisierung](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="02daa-427">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="02daa-428">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="02daa-428">libgdiplus</span></span>

<span data-ttu-id="02daa-429">Für .NET Core-Anwendungen, die die Assembly *System.Drawing.Common* verwenden, muss libgdiplus installiert sein.</span><span class="sxs-lookup"><span data-stu-id="02daa-429">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="02daa-430">Eine einfache Möglichkeit zum Abrufen von libgdiplus bietet der [Homebrew](https://brew.sh/)-Paket-Manager („brew“) für macOS.</span><span class="sxs-lookup"><span data-stu-id="02daa-430">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="02daa-431">Installieren Sie nach der Installation von *brew* libgdiplus durch Ausführen der folgenden Befehle in einem Terminal (Befehl):</span><span class="sxs-lookup"><span data-stu-id="02daa-431">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="02daa-432">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="02daa-432">Next steps</span></span>

- <span data-ttu-id="02daa-433">Installieren Sie das [.NET Core SDK](sdk.md) (einschließlich der Runtime), um Apps zu entwickeln und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="02daa-433">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="02daa-434">Installieren Sie die [.NET Core-Runtime](runtime.md), um von anderen erstellte Apps auszuführen.</span><span class="sxs-lookup"><span data-stu-id="02daa-434">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
