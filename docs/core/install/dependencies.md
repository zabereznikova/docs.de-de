---
title: '.NET Core SDK und Runtimeabhängigkeiten: .NET Core'
description: In diesem Artikel werden die Voraussetzungen für das Betriebssystem und die CPU-Architektur zum Installieren des .NET Core SDK und der Runtime unter Windows, Linux und macOS erläutert.
author: leecow
ms.author: leecow
ms.date: 06/01/2020
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 81f6ab436428d71f71d9fd0f560bd2b0512a519b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590759"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="1b1bf-103">.NET Core-Abhängigkeiten und -Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1b1bf-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="1b1bf-104">In diesem Artikel wird erläutert, welche Betriebssysteme und CPU-Architektur von .NET Core unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="1b1bf-105">Unterstützte Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="1b1bf-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="1b1bf-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="1b1bf-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="1b1bf-107">Die folgenden Windows-Versionen werden von .NET Core 3.1 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="1b1bf-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="1b1bf-108">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1b1bf-109">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="1b1bf-109">OS</span></span>                            | <span data-ttu-id="1b1bf-110">Version</span><span class="sxs-lookup"><span data-stu-id="1b1bf-110">Version</span></span>                        | <span data-ttu-id="1b1bf-111">Architekturen</span><span class="sxs-lookup"><span data-stu-id="1b1bf-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="1b1bf-112">Windows-Client</span><span class="sxs-lookup"><span data-stu-id="1b1bf-112">Windows Client</span></span>                | <span data-ttu-id="1b1bf-113">7 SP1 oder höher, 8.1</span><span class="sxs-lookup"><span data-stu-id="1b1bf-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="1b1bf-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1b1bf-114">x64, x86</span></span>        |
| <span data-ttu-id="1b1bf-115">Windows 10-Client</span><span class="sxs-lookup"><span data-stu-id="1b1bf-115">Windows 10 Client</span></span>             | <span data-ttu-id="1b1bf-116">Version 1607 oder höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-116">Version 1607+</span></span>                  | <span data-ttu-id="1b1bf-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1b1bf-117">x64, x86</span></span>        |
| <span data-ttu-id="1b1bf-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="1b1bf-118">Windows Server</span></span>                | <span data-ttu-id="1b1bf-119">2012 R2 oder höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-119">2012 R2+</span></span>                       | <span data-ttu-id="1b1bf-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1b1bf-120">x64, x86</span></span>        |
| <span data-ttu-id="1b1bf-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="1b1bf-121">Nano Server</span></span>                   | <span data-ttu-id="1b1bf-122">Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-122">Version 1803+</span></span>                  | <span data-ttu-id="1b1bf-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="1b1bf-123">x64, ARM32</span></span>      |

<span data-ttu-id="1b1bf-124">Weitere Informationen zu den von .NET Core 3.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="1b1bf-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="1b1bf-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1b1bf-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="1b1bf-126">*.NET Core 3.0 wird aktuell nicht unterstützt. Weitere Informationen finden Sie in der [Supportrichtlinie für .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="1b1bf-126">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="1b1bf-127">Die folgenden Windows-Versionen werden von .NET Core 3.0 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="1b1bf-127">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="1b1bf-128">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-128">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1b1bf-129">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="1b1bf-129">OS</span></span>                            | <span data-ttu-id="1b1bf-130">Version</span><span class="sxs-lookup"><span data-stu-id="1b1bf-130">Version</span></span>                        | <span data-ttu-id="1b1bf-131">Architekturen</span><span class="sxs-lookup"><span data-stu-id="1b1bf-131">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="1b1bf-132">Windows-Client</span><span class="sxs-lookup"><span data-stu-id="1b1bf-132">Windows Client</span></span>                | <span data-ttu-id="1b1bf-133">7 SP1 oder höher, 8.1</span><span class="sxs-lookup"><span data-stu-id="1b1bf-133">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="1b1bf-134">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1b1bf-134">x64, x86</span></span>        |
| <span data-ttu-id="1b1bf-135">Windows 10-Client</span><span class="sxs-lookup"><span data-stu-id="1b1bf-135">Windows 10 Client</span></span>             | <span data-ttu-id="1b1bf-136">Version 1607 oder höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-136">Version 1607+</span></span>                  | <span data-ttu-id="1b1bf-137">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1b1bf-137">x64, x86</span></span>        |
| <span data-ttu-id="1b1bf-138">Windows Server</span><span class="sxs-lookup"><span data-stu-id="1b1bf-138">Windows Server</span></span>                | <span data-ttu-id="1b1bf-139">2012 R2 oder höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-139">2012 R2+</span></span>                       | <span data-ttu-id="1b1bf-140">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1b1bf-140">x64, x86</span></span>        |
| <span data-ttu-id="1b1bf-141">Nano Server</span><span class="sxs-lookup"><span data-stu-id="1b1bf-141">Nano Server</span></span>                   | <span data-ttu-id="1b1bf-142">Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-142">Version 1803+</span></span>                  | <span data-ttu-id="1b1bf-143">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="1b1bf-143">x64, ARM32</span></span>      |

<span data-ttu-id="1b1bf-144">Weitere Informationen zu den von .NET Core 3.0 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.0 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="1b1bf-144">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="1b1bf-145">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="1b1bf-145">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="1b1bf-146">*.NET Core 2.2 wird aktuell nicht unterstützt. Weitere Informationen finden Sie in der [Supportrichtlinie für .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="1b1bf-146">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="1b1bf-147">Die folgenden Windows-Versionen werden von .NET Core 2.2 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="1b1bf-147">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="1b1bf-148">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-148">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1b1bf-149">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="1b1bf-149">OS</span></span>                            | <span data-ttu-id="1b1bf-150">Version</span><span class="sxs-lookup"><span data-stu-id="1b1bf-150">Version</span></span>                        | <span data-ttu-id="1b1bf-151">Architekturen</span><span class="sxs-lookup"><span data-stu-id="1b1bf-151">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="1b1bf-152">Windows-Client</span><span class="sxs-lookup"><span data-stu-id="1b1bf-152">Windows Client</span></span>                | <span data-ttu-id="1b1bf-153">7 SP1 oder höher, 8.1</span><span class="sxs-lookup"><span data-stu-id="1b1bf-153">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="1b1bf-154">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1b1bf-154">x64, x86</span></span>        |
| <span data-ttu-id="1b1bf-155">Windows 10-Client</span><span class="sxs-lookup"><span data-stu-id="1b1bf-155">Windows 10 Client</span></span>             | <span data-ttu-id="1b1bf-156">Version 1607 oder höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-156">Version 1607+</span></span>                  | <span data-ttu-id="1b1bf-157">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1b1bf-157">x64, x86</span></span>        |
| <span data-ttu-id="1b1bf-158">Windows Server</span><span class="sxs-lookup"><span data-stu-id="1b1bf-158">Windows Server</span></span>                | <span data-ttu-id="1b1bf-159">2008 R2 SP1 oder höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-159">2008 R2 SP1+</span></span>                   | <span data-ttu-id="1b1bf-160">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1b1bf-160">x64, x86</span></span>        |
| <span data-ttu-id="1b1bf-161">Nano Server</span><span class="sxs-lookup"><span data-stu-id="1b1bf-161">Nano Server</span></span>                   | <span data-ttu-id="1b1bf-162">Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-162">Version 1803+</span></span>                   | <span data-ttu-id="1b1bf-163">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="1b1bf-163">x64, ARM32</span></span>      |

<span data-ttu-id="1b1bf-164">Weitere Informationen zu den von .NET Core 2.2 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.2 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="1b1bf-164">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="1b1bf-165">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1b1bf-165">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="1b1bf-166">Die folgenden Windows-Versionen werden von .NET Core 2.1 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="1b1bf-166">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="1b1bf-167">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-167">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1b1bf-168">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="1b1bf-168">OS</span></span>                            | <span data-ttu-id="1b1bf-169">Version</span><span class="sxs-lookup"><span data-stu-id="1b1bf-169">Version</span></span>                        | <span data-ttu-id="1b1bf-170">Architekturen</span><span class="sxs-lookup"><span data-stu-id="1b1bf-170">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="1b1bf-171">Windows-Client</span><span class="sxs-lookup"><span data-stu-id="1b1bf-171">Windows Client</span></span>                | <span data-ttu-id="1b1bf-172">7 SP1 oder höher, 8.1</span><span class="sxs-lookup"><span data-stu-id="1b1bf-172">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="1b1bf-173">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1b1bf-173">x64, x86</span></span>        |
| <span data-ttu-id="1b1bf-174">Windows 10-Client</span><span class="sxs-lookup"><span data-stu-id="1b1bf-174">Windows 10 Client</span></span>             | <span data-ttu-id="1b1bf-175">Version 1607 oder höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-175">Version 1607+</span></span>                  | <span data-ttu-id="1b1bf-176">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1b1bf-176">x64, x86</span></span>        |
| <span data-ttu-id="1b1bf-177">Windows Server</span><span class="sxs-lookup"><span data-stu-id="1b1bf-177">Windows Server</span></span>                | <span data-ttu-id="1b1bf-178">2008 R2 SP1 oder höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-178">2008 R2 SP1+</span></span>                   | <span data-ttu-id="1b1bf-179">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1b1bf-179">x64, x86</span></span>        |
| <span data-ttu-id="1b1bf-180">Nano Server</span><span class="sxs-lookup"><span data-stu-id="1b1bf-180">Nano Server</span></span>                   | <span data-ttu-id="1b1bf-181">Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-181">Version 1803+</span></span>                  | <span data-ttu-id="1b1bf-182">x64,</span><span class="sxs-lookup"><span data-stu-id="1b1bf-182">x64,</span></span>            |

<span data-ttu-id="1b1bf-183">Weitere Informationen zu den von .NET Core 2.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="1b1bf-183">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a> <span data-ttu-id="1b1bf-184">Windows 7/Vista/8.1/Server 2008 R2/Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="1b1bf-184">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span></span>

<span data-ttu-id="1b1bf-185">Weitere Abhängigkeiten sind erforderlich, wenn Sie das .NET SDK oder die Runtime unter den folgenden Windows-Versionen installieren:</span><span class="sxs-lookup"><span data-stu-id="1b1bf-185">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="1b1bf-186">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="1b1bf-186">Windows 7 SP1</span></span>
- <span data-ttu-id="1b1bf-187">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="1b1bf-187">Windows Vista SP 2</span></span>
- <span data-ttu-id="1b1bf-188">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="1b1bf-188">Windows 8.1</span></span>
- <span data-ttu-id="1b1bf-189">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="1b1bf-189">Windows Server 2008 R2</span></span>
- <span data-ttu-id="1b1bf-190">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="1b1bf-190">Windows Server 2012 R2</span></span>

<span data-ttu-id="1b1bf-191">Installieren Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1b1bf-191">Install the following:</span></span>

- <span data-ttu-id="1b1bf-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="1b1bf-193">KB2533623</span><span class="sxs-lookup"><span data-stu-id="1b1bf-193">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="1b1bf-194">Die oben aufgeführten Anforderungen sind auch erforderlich, wenn einer der folgenden Fehler auftritt:</span><span class="sxs-lookup"><span data-stu-id="1b1bf-194">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="1b1bf-195">Das Programm kann nicht gestartet werden, da *api-ms-win-crt-runtime-l1-1-0.dll* auf dem Computer fehlt.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-195">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="1b1bf-196">Installieren Sie das Programm erneut, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-196">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="1b1bf-197">\- oder -</span><span class="sxs-lookup"><span data-stu-id="1b1bf-197">\- or -</span></span>
>
> <span data-ttu-id="1b1bf-198">Das Programm kann nicht gestartet werden, da *api-ms-win-cor-timezone-l1-1-0.dll* auf dem Computer fehlt.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-198">The program can't start because *api-ms-win-cor-timezone-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="1b1bf-199">Installieren Sie das Programm erneut, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-199">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="1b1bf-200">\- oder -</span><span class="sxs-lookup"><span data-stu-id="1b1bf-200">\- or -</span></span>
>
> <span data-ttu-id="1b1bf-201">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed. (Die Bibliothek „hostfxr.dll“ wurde gefunden, aber der Ladevorgang aus C:\<Pfad_zu_App>\hostfxr.dll ist fehlgeschlagen.)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-201">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="1b1bf-202">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="1b1bf-202">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="1b1bf-203">.NET Core 3.1 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-203">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="1b1bf-204">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-204">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="1b1bf-205">.NET Core 3.1 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="1b1bf-205">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="1b1bf-206">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-206">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1b1bf-207">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="1b1bf-207">OS</span></span>                             | <span data-ttu-id="1b1bf-208">Version</span><span class="sxs-lookup"><span data-stu-id="1b1bf-208">Version</span></span>               | <span data-ttu-id="1b1bf-209">Architekturen</span><span class="sxs-lookup"><span data-stu-id="1b1bf-209">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="1b1bf-210">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="1b1bf-210">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="1b1bf-211">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="1b1bf-211">6, 7, 8</span></span>               | <span data-ttu-id="1b1bf-212">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-212">x64</span></span> |
| <span data-ttu-id="1b1bf-213">CentOS</span><span class="sxs-lookup"><span data-stu-id="1b1bf-213">CentOS</span></span>                         | <span data-ttu-id="1b1bf-214">7 und höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-214">7+</span></span>                    | <span data-ttu-id="1b1bf-215">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-215">x64</span></span> |
| <span data-ttu-id="1b1bf-216">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="1b1bf-216">Oracle Linux</span></span>                   | <span data-ttu-id="1b1bf-217">7 und höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-217">7+</span></span>                    | <span data-ttu-id="1b1bf-218">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-218">x64</span></span> |
| <span data-ttu-id="1b1bf-219">Fedora</span><span class="sxs-lookup"><span data-stu-id="1b1bf-219">Fedora</span></span>                         | <span data-ttu-id="1b1bf-220">30 und höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-220">30+</span></span>                   | <span data-ttu-id="1b1bf-221">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-221">x64</span></span> |
| <span data-ttu-id="1b1bf-222">Debian</span><span class="sxs-lookup"><span data-stu-id="1b1bf-222">Debian</span></span>                         | <span data-ttu-id="1b1bf-223">9 und höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-223">9+</span></span>                    | <span data-ttu-id="1b1bf-224">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-224">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="1b1bf-225">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1b1bf-225">Ubuntu</span></span>                         | <span data-ttu-id="1b1bf-226">16.04 und höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-226">16.04+</span></span>                | <span data-ttu-id="1b1bf-227">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-227">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="1b1bf-228">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="1b1bf-228">Linux Mint</span></span>                     | <span data-ttu-id="1b1bf-229">18 und höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-229">18+</span></span>                   | <span data-ttu-id="1b1bf-230">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-230">x64</span></span> |
| <span data-ttu-id="1b1bf-231">openSUSE</span><span class="sxs-lookup"><span data-stu-id="1b1bf-231">openSUSE</span></span>                       | <span data-ttu-id="1b1bf-232">15 und höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-232">15+</span></span>                   | <span data-ttu-id="1b1bf-233">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-233">x64</span></span> |
| <span data-ttu-id="1b1bf-234">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-234">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="1b1bf-235">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="1b1bf-235">12 SP2+</span></span>               | <span data-ttu-id="1b1bf-236">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-236">x64</span></span> |
| <span data-ttu-id="1b1bf-237">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="1b1bf-237">Alpine Linux</span></span>                   | <span data-ttu-id="1b1bf-238">3.10 oder höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-238">3.10+</span></span>                 | <span data-ttu-id="1b1bf-239">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-239">x64, ARM64</span></span> |

<span data-ttu-id="1b1bf-240">Weitere Informationen zu den von .NET Core 3.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="1b1bf-240">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="1b1bf-241">Weitere Informationen zum Installieren von .NET Core 3.1 unter ARM64 (Kernel 4.14 oder höher) finden Sie unter [Installieren von .NET Core 3.0 unter Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span><span class="sxs-lookup"><span data-stu-id="1b1bf-241">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1b1bf-242">Für die Unterstützung von ARM64 ist Linux-Kernel 4.14 oder höher erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-242">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="1b1bf-243">Einige Linux-Verteilungen erfüllen diese Anforderung, andere hingegen nicht.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-243">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="1b1bf-244">So wird Ubuntu 18.04 im Gegensatz zu Ubuntu 16.04 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-244">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="1b1bf-245">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1b1bf-245">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="1b1bf-246">*.NET Core 3.0 wird aktuell nicht unterstützt. Weitere Informationen finden Sie in der [Supportrichtlinie für .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="1b1bf-246">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="1b1bf-247">.NET Core 3.0 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-247">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="1b1bf-248">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-248">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="1b1bf-249">.NET Core 3.0 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="1b1bf-249">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="1b1bf-250">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-250">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1b1bf-251">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="1b1bf-251">OS</span></span>                             | <span data-ttu-id="1b1bf-252">Version</span><span class="sxs-lookup"><span data-stu-id="1b1bf-252">Version</span></span>               | <span data-ttu-id="1b1bf-253">Architekturen</span><span class="sxs-lookup"><span data-stu-id="1b1bf-253">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="1b1bf-254">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="1b1bf-254">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="1b1bf-255">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="1b1bf-255">6, 7, 8</span></span>               | <span data-ttu-id="1b1bf-256">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-256">x64</span></span> |
| <span data-ttu-id="1b1bf-257">CentOS</span><span class="sxs-lookup"><span data-stu-id="1b1bf-257">CentOS</span></span>                         | <span data-ttu-id="1b1bf-258">7 und höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-258">7+</span></span>                    | <span data-ttu-id="1b1bf-259">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-259">x64</span></span> |
| <span data-ttu-id="1b1bf-260">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="1b1bf-260">Oracle Linux</span></span>                   | <span data-ttu-id="1b1bf-261">7 und höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-261">7+</span></span>                    | <span data-ttu-id="1b1bf-262">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-262">x64</span></span> |
| <span data-ttu-id="1b1bf-263">Fedora</span><span class="sxs-lookup"><span data-stu-id="1b1bf-263">Fedora</span></span>                         | <span data-ttu-id="1b1bf-264">29 und höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-264">29+</span></span>                   | <span data-ttu-id="1b1bf-265">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-265">x64</span></span> |
| <span data-ttu-id="1b1bf-266">Debian</span><span class="sxs-lookup"><span data-stu-id="1b1bf-266">Debian</span></span>                         | <span data-ttu-id="1b1bf-267">9 und höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-267">9+</span></span>                    | <span data-ttu-id="1b1bf-268">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-268">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="1b1bf-269">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1b1bf-269">Ubuntu</span></span>                         | <span data-ttu-id="1b1bf-270">16.04 und höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-270">16.04+</span></span>                | <span data-ttu-id="1b1bf-271">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-271">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="1b1bf-272">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="1b1bf-272">Linux Mint</span></span>                     | <span data-ttu-id="1b1bf-273">18 und höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-273">18+</span></span>                   | <span data-ttu-id="1b1bf-274">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-274">x64</span></span> |
| <span data-ttu-id="1b1bf-275">openSUSE</span><span class="sxs-lookup"><span data-stu-id="1b1bf-275">openSUSE</span></span>                       | <span data-ttu-id="1b1bf-276">15 und höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-276">15+</span></span>                   | <span data-ttu-id="1b1bf-277">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-277">x64</span></span> |
| <span data-ttu-id="1b1bf-278">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-278">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="1b1bf-279">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="1b1bf-279">12 SP2+</span></span>               | <span data-ttu-id="1b1bf-280">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-280">x64</span></span> |
| <span data-ttu-id="1b1bf-281">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="1b1bf-281">Alpine Linux</span></span>                   | <span data-ttu-id="1b1bf-282">3.8+</span><span class="sxs-lookup"><span data-stu-id="1b1bf-282">3.8+</span></span>                  | <span data-ttu-id="1b1bf-283">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-283">x64, ARM64</span></span> |

<span data-ttu-id="1b1bf-284">Weitere Informationen zu den von .NET Core 3.0 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.0 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="1b1bf-284">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="1b1bf-285">Weitere Informationen zum Installieren von .NET Core 3.0 unter ARM64 finden Sie unter [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Installieren von .NET Core 3.0 unter Linux ARM64).</span><span class="sxs-lookup"><span data-stu-id="1b1bf-285">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="1b1bf-286">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="1b1bf-286">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="1b1bf-287">*.NET Core 2.2 wird aktuell nicht unterstützt. Weitere Informationen finden Sie in der [Supportrichtlinie für .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="1b1bf-287">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="1b1bf-288">.NET Core 2.2 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-288">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="1b1bf-289">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-289">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="1b1bf-290">.NET Core 2.2 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="1b1bf-290">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="1b1bf-291">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-291">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1b1bf-292">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="1b1bf-292">OS</span></span>                             |  <span data-ttu-id="1b1bf-293">Version</span><span class="sxs-lookup"><span data-stu-id="1b1bf-293">Version</span></span>                |  <span data-ttu-id="1b1bf-294">Architekturen</span><span class="sxs-lookup"><span data-stu-id="1b1bf-294">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="1b1bf-295">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="1b1bf-295">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="1b1bf-296">6, 7</span><span class="sxs-lookup"><span data-stu-id="1b1bf-296">6, 7</span></span>                   | <span data-ttu-id="1b1bf-297">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-297">x64</span></span> |
| <span data-ttu-id="1b1bf-298">CentOS</span><span class="sxs-lookup"><span data-stu-id="1b1bf-298">CentOS</span></span>                         |  <span data-ttu-id="1b1bf-299">7</span><span class="sxs-lookup"><span data-stu-id="1b1bf-299">7</span></span>                      | <span data-ttu-id="1b1bf-300">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-300">x64</span></span> |
| <span data-ttu-id="1b1bf-301">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="1b1bf-301">Oracle Linux</span></span>                   |  <span data-ttu-id="1b1bf-302">7</span><span class="sxs-lookup"><span data-stu-id="1b1bf-302">7</span></span>                      | <span data-ttu-id="1b1bf-303">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-303">x64</span></span> |
| <span data-ttu-id="1b1bf-304">Fedora</span><span class="sxs-lookup"><span data-stu-id="1b1bf-304">Fedora</span></span>                         |  <span data-ttu-id="1b1bf-305">29, 30</span><span class="sxs-lookup"><span data-stu-id="1b1bf-305">29, 30</span></span>                 | <span data-ttu-id="1b1bf-306">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-306">x64</span></span> |
| <span data-ttu-id="1b1bf-307">Debian</span><span class="sxs-lookup"><span data-stu-id="1b1bf-307">Debian</span></span>                         |  <span data-ttu-id="1b1bf-308">9</span><span class="sxs-lookup"><span data-stu-id="1b1bf-308">9</span></span>                      | <span data-ttu-id="1b1bf-309">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="1b1bf-309">x64, ARM32</span></span> |
| <span data-ttu-id="1b1bf-310">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1b1bf-310">Ubuntu</span></span>                         |  <span data-ttu-id="1b1bf-311">16.04, 18.04, 18.10</span><span class="sxs-lookup"><span data-stu-id="1b1bf-311">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="1b1bf-312">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="1b1bf-312">x64, ARM32</span></span> |
| <span data-ttu-id="1b1bf-313">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="1b1bf-313">Linux Mint</span></span>                     |  <span data-ttu-id="1b1bf-314">17, 18</span><span class="sxs-lookup"><span data-stu-id="1b1bf-314">17, 18</span></span>                 | <span data-ttu-id="1b1bf-315">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-315">x64</span></span> |
| <span data-ttu-id="1b1bf-316">openSUSE</span><span class="sxs-lookup"><span data-stu-id="1b1bf-316">openSUSE</span></span>                       |  <span data-ttu-id="1b1bf-317">15 und höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-317">15+</span></span>                    | <span data-ttu-id="1b1bf-318">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-318">x64</span></span> |
| <span data-ttu-id="1b1bf-319">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-319">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="1b1bf-320">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="1b1bf-320">12 SP2+</span></span>                | <span data-ttu-id="1b1bf-321">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-321">x64</span></span> |
| <span data-ttu-id="1b1bf-322">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="1b1bf-322">Alpine Linux</span></span>                   |  <span data-ttu-id="1b1bf-323">3.8+</span><span class="sxs-lookup"><span data-stu-id="1b1bf-323">3.8+</span></span>                   | <span data-ttu-id="1b1bf-324">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-324">x64</span></span> |

<span data-ttu-id="1b1bf-325">Weitere Informationen zu den von .NET Core 2.2 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.2 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="1b1bf-325">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="1b1bf-326">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1b1bf-326">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="1b1bf-327">.NET Core 2.1 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-327">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="1b1bf-328">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-328">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="1b1bf-329">.NET Core 2.1 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="1b1bf-329">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="1b1bf-330">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-330">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1b1bf-331">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="1b1bf-331">OS</span></span>                             |  <span data-ttu-id="1b1bf-332">Version</span><span class="sxs-lookup"><span data-stu-id="1b1bf-332">Version</span></span>                |  <span data-ttu-id="1b1bf-333">Architekturen</span><span class="sxs-lookup"><span data-stu-id="1b1bf-333">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="1b1bf-334">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="1b1bf-334">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="1b1bf-335">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="1b1bf-335">6, 7, 8</span></span>                | <span data-ttu-id="1b1bf-336">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-336">x64</span></span> |
| <span data-ttu-id="1b1bf-337">CentOS</span><span class="sxs-lookup"><span data-stu-id="1b1bf-337">CentOS</span></span>                         |  <span data-ttu-id="1b1bf-338">7 und höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-338">7+</span></span>                     | <span data-ttu-id="1b1bf-339">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-339">x64</span></span> |
| <span data-ttu-id="1b1bf-340">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="1b1bf-340">Oracle Linux</span></span>                   |  <span data-ttu-id="1b1bf-341">7 und höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-341">7+</span></span>                     | <span data-ttu-id="1b1bf-342">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-342">x64</span></span> |
| <span data-ttu-id="1b1bf-343">Fedora</span><span class="sxs-lookup"><span data-stu-id="1b1bf-343">Fedora</span></span>                         |  <span data-ttu-id="1b1bf-344">30 und höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-344">30+</span></span>                    | <span data-ttu-id="1b1bf-345">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-345">x64</span></span> |
| <span data-ttu-id="1b1bf-346">Debian</span><span class="sxs-lookup"><span data-stu-id="1b1bf-346">Debian</span></span>                         |  <span data-ttu-id="1b1bf-347">9</span><span class="sxs-lookup"><span data-stu-id="1b1bf-347">9</span></span>                      | <span data-ttu-id="1b1bf-348">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="1b1bf-348">x64, ARM32</span></span> |
| <span data-ttu-id="1b1bf-349">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1b1bf-349">Ubuntu</span></span>                         |  <span data-ttu-id="1b1bf-350">16.04, 18.04, 19.04, 19.10</span><span class="sxs-lookup"><span data-stu-id="1b1bf-350">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="1b1bf-351">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="1b1bf-351">x64, ARM32</span></span> |
| <span data-ttu-id="1b1bf-352">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="1b1bf-352">Linux Mint</span></span>                     |  <span data-ttu-id="1b1bf-353">17 oder höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-353">17+</span></span>                    | <span data-ttu-id="1b1bf-354">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-354">x64</span></span> |
| <span data-ttu-id="1b1bf-355">openSUSE</span><span class="sxs-lookup"><span data-stu-id="1b1bf-355">openSUSE</span></span>                       |  <span data-ttu-id="1b1bf-356">15 und höher</span><span class="sxs-lookup"><span data-stu-id="1b1bf-356">15+</span></span>                    | <span data-ttu-id="1b1bf-357">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-357">x64</span></span> |
| <span data-ttu-id="1b1bf-358">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-358">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="1b1bf-359">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="1b1bf-359">12 SP2+</span></span>                | <span data-ttu-id="1b1bf-360">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-360">x64</span></span> |
| <span data-ttu-id="1b1bf-361">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="1b1bf-361">Alpine Linux</span></span>                   |  <span data-ttu-id="1b1bf-362">3.8+</span><span class="sxs-lookup"><span data-stu-id="1b1bf-362">3.8+</span></span>                   | <span data-ttu-id="1b1bf-363">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-363">x64</span></span> |

<span data-ttu-id="1b1bf-364">Weitere Informationen zu den von .NET Core 2.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="1b1bf-364">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="1b1bf-365">Abhängigkeiten der Linux-Distributionen</span><span class="sxs-lookup"><span data-stu-id="1b1bf-365">Linux distribution dependencies</span></span>

<span data-ttu-id="1b1bf-366">Basierend auf den Linux-Verteilungen müssen Sie möglicherweise zusätzliche Abhängigkeiten installieren.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-366">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1b1bf-367">Die exakten Versionen und Namen können sich bei der von Ihnen verwendeten Linux-Verteilung leicht unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-367">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="1b1bf-368">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1b1bf-368">Ubuntu</span></span>

<span data-ttu-id="1b1bf-369">Für Ubuntu-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:</span><span class="sxs-lookup"><span data-stu-id="1b1bf-369">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="1b1bf-370">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="1b1bf-370">liblttng-ust0</span></span>
- <span data-ttu-id="1b1bf-371">libcurl3 (für 14.x und 16.x)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-371">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="1b1bf-372">libcurl4 (für 18.x)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-372">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="1b1bf-373">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="1b1bf-373">libssl1.0.0</span></span>
- <span data-ttu-id="1b1bf-374">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="1b1bf-374">libkrb5-3</span></span>
- <span data-ttu-id="1b1bf-375">zlib1g</span><span class="sxs-lookup"><span data-stu-id="1b1bf-375">zlib1g</span></span>
- <span data-ttu-id="1b1bf-376">libicu52 (für 14.X)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-376">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="1b1bf-377">libicu55 (für 16.X)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-377">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="1b1bf-378">libicu57 (für 17.X)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-378">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="1b1bf-379">libicu60 (für 18.X)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-379">libicu60 (for 18.x)</span></span>

<span data-ttu-id="1b1bf-380">Für .NET Core-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="1b1bf-380">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="1b1bf-381">libgdiplus (Version 6.0.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-381">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="1b1bf-382">Die meisten Versionen von Ubuntu enthalten eine frühere Version von libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-382">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="1b1bf-383">Sie können eine neuere Version von libgdiplus installieren, indem Sie auf Ihrem System das Mono-Repository hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-383">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="1b1bf-384">Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-384">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="1b1bf-385">CentOS und Fedora</span><span class="sxs-lookup"><span data-stu-id="1b1bf-385">CentOS and Fedora</span></span>

<span data-ttu-id="1b1bf-386">Für CentOS-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:</span><span class="sxs-lookup"><span data-stu-id="1b1bf-386">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="1b1bf-387">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="1b1bf-387">lttng-ust</span></span>
- <span data-ttu-id="1b1bf-388">libcurl</span><span class="sxs-lookup"><span data-stu-id="1b1bf-388">libcurl</span></span>
- <span data-ttu-id="1b1bf-389">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="1b1bf-389">openssl-libs</span></span>
- <span data-ttu-id="1b1bf-390">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="1b1bf-390">krb5-libs</span></span>
- <span data-ttu-id="1b1bf-391">libicu</span><span class="sxs-lookup"><span data-stu-id="1b1bf-391">libicu</span></span>
- <span data-ttu-id="1b1bf-392">zlib</span><span class="sxs-lookup"><span data-stu-id="1b1bf-392">zlib</span></span>

<span data-ttu-id="1b1bf-393">Für Fedora-Benutzer: Wenn Ihre Version von OpenSSL Version 1.1 oder höher entspricht, müssen Sie **compat-openssl10** installieren.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-393">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="1b1bf-394">Für .NET Core 2.0 sind außerdem die folgenden Abhängigkeiten erforderlich:</span><span class="sxs-lookup"><span data-stu-id="1b1bf-394">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="1b1bf-395">libunwind</span><span class="sxs-lookup"><span data-stu-id="1b1bf-395">libunwind</span></span>
- <span data-ttu-id="1b1bf-396">libuuid</span><span class="sxs-lookup"><span data-stu-id="1b1bf-396">libuuid</span></span>

<span data-ttu-id="1b1bf-397">Weitere Informationen zu den Abhängigkeiten finden Sie unter [Eigenständige Linux-Apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="1b1bf-397">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="1b1bf-398">Für .NET Core-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="1b1bf-398">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="1b1bf-399">libgdiplus (Version 6.0.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-399">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="1b1bf-400">Die meisten Versionen von CentOS und Fedora enthalten eine frühere Version von libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-400">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="1b1bf-401">Sie können eine neuere Version von libgdiplus installieren, indem Sie auf Ihrem System das Mono-Repository hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-401">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="1b1bf-402">Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-402">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="alpine"></a><span data-ttu-id="1b1bf-403">Alpine</span><span class="sxs-lookup"><span data-stu-id="1b1bf-403">Alpine</span></span>

<span data-ttu-id="1b1bf-404">Für Alpine-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:</span><span class="sxs-lookup"><span data-stu-id="1b1bf-404">Alpine distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="1b1bf-405">icu-lisb (nicht erforderlich bei deaktivierter Globalisierung)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-405">icu-libs (this is not needed if globalization is disabled)</span></span>
- <span data-ttu-id="1b1bf-406">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="1b1bf-406">krb5-libs</span></span>
- <span data-ttu-id="1b1bf-407">libcurl</span><span class="sxs-lookup"><span data-stu-id="1b1bf-407">libcurl</span></span>
- <span data-ttu-id="1b1bf-408">libintl</span><span class="sxs-lookup"><span data-stu-id="1b1bf-408">libintl</span></span>
- <span data-ttu-id="1b1bf-409">libssl1.1 (für Alpine 3.9 oder höher) oder libssl1.0 (für ältere Versionen)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-409">libssl1.1 (for Alpine 3.9 or later) or libssl1.0 (for older ones)</span></span>
- <span data-ttu-id="1b1bf-410">libstdc++</span><span class="sxs-lookup"><span data-stu-id="1b1bf-410">libstdc++</span></span>
- <span data-ttu-id="1b1bf-411">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="1b1bf-411">lttng-ust</span></span>
- <span data-ttu-id="1b1bf-412">numactl (optional, nur für Geräte mit aktiviertem NUMA nützlich)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-412">numactl (optional, useful only for devices with NUMA enabled)</span></span>
- <span data-ttu-id="1b1bf-413">zlib</span><span class="sxs-lookup"><span data-stu-id="1b1bf-413">zlib</span></span>

<span data-ttu-id="1b1bf-414">Für .NET Core-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="1b1bf-414">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="1b1bf-415">libgdiplus (nur im Edge/Testing-Repository verfügbar)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-415">libgdiplus (it is available only in the edge/testing repository)</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="1b1bf-416">.NET Core wird von den folgenden macOS-Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="1b1bf-416">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="1b1bf-417">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-417">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1b1bf-418">.NET Core-Version</span><span class="sxs-lookup"><span data-stu-id="1b1bf-418">.NET Core Version</span></span> | <span data-ttu-id="1b1bf-419">macOS</span><span class="sxs-lookup"><span data-stu-id="1b1bf-419">macOS</span></span>                 | <span data-ttu-id="1b1bf-420">Architekturen</span><span class="sxs-lookup"><span data-stu-id="1b1bf-420">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="1b1bf-421">3.1</span><span class="sxs-lookup"><span data-stu-id="1b1bf-421">3.1</span></span>               | <span data-ttu-id="1b1bf-422">High Sierra (10.13 oder höher)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-422">High Sierra (10.13+)</span></span>  | <span data-ttu-id="1b1bf-423">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-423">x64</span></span> | [<span data-ttu-id="1b1bf-424">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b1bf-424">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="1b1bf-425">3.0</span><span class="sxs-lookup"><span data-stu-id="1b1bf-425">3.0</span></span>               | <span data-ttu-id="1b1bf-426">High Sierra (10.13 oder höher)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-426">High Sierra (10.13+)</span></span>  | <span data-ttu-id="1b1bf-427">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-427">x64</span></span> | [<span data-ttu-id="1b1bf-428">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b1bf-428">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="1b1bf-429">2.2</span><span class="sxs-lookup"><span data-stu-id="1b1bf-429">2.2</span></span>               | <span data-ttu-id="1b1bf-430">Sierra (10.12 oder höher)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-430">Sierra (10.12+)</span></span>       | <span data-ttu-id="1b1bf-431">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-431">x64</span></span> | [<span data-ttu-id="1b1bf-432">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b1bf-432">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="1b1bf-433">2.1</span><span class="sxs-lookup"><span data-stu-id="1b1bf-433">2.1</span></span>               | <span data-ttu-id="1b1bf-434">Sierra (10.12 oder höher)</span><span class="sxs-lookup"><span data-stu-id="1b1bf-434">Sierra (10.12+)</span></span>       | <span data-ttu-id="1b1bf-435">x64</span><span class="sxs-lookup"><span data-stu-id="1b1bf-435">x64</span></span> | [<span data-ttu-id="1b1bf-436">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b1bf-436">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="1b1bf-437">Ab macOS Catalina (Version 10.15) muss jegliche Software notarisiert werden, die nach dem 1. Juni 2019 erstellt wurde und mit einer Entwickler-ID verteilt wird.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-437">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="1b1bf-438">Diese Voraussetzung gilt für die .NET Core-Runtime, das .NET Core SDK und jegliche Software, die mit .NET Core erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-438">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="1b1bf-439">Die Installationsprogramme für die Versionen 3.1, 3.0 und 2.1 von .NET Core (sowohl für die Runtime als auch das SDK) wurden seit dem 18. Februar 2020 notarisiert.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-439">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="1b1bf-440">Vorherige Versionen wurden nicht notarisiert.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-440">Prior released versions aren't notarized.</span></span> <span data-ttu-id="1b1bf-441">Wenn Sie eine nicht notarisierte App ausführen, wird eine Fehlermeldung ähnlich der folgenden Abbildung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1b1bf-441">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![macOS Catalina-Notarisierungswarnung](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="1b1bf-443">Weitere Informationen dazu, wie sich die erzwungene Notarisierung auf .NET Core (und Ihre .NET Core-Apps) auswirkt, finden Sie unter [Verwenden der macOS Catalina-Notarisierung](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1b1bf-443">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="1b1bf-444">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="1b1bf-444">libgdiplus</span></span>

<span data-ttu-id="1b1bf-445">Für .NET Core-Anwendungen, die die Assembly *System.Drawing.Common* verwenden, muss libgdiplus installiert sein.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-445">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="1b1bf-446">Eine einfache Möglichkeit zum Abrufen von libgdiplus bietet der [Homebrew](https://brew.sh/)-Paket-Manager („brew“) für macOS.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-446">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="1b1bf-447">Installieren Sie nach der Installation von *brew* libgdiplus durch Ausführen der folgenden Befehle in einem Terminal (Befehl):</span><span class="sxs-lookup"><span data-stu-id="1b1bf-447">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="1b1bf-448">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1b1bf-448">Next steps</span></span>

- <span data-ttu-id="1b1bf-449">Installieren Sie das [.NET Core SDK](sdk.md) (einschließlich der Runtime), um Apps zu entwickeln und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-449">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="1b1bf-450">Installieren Sie die [.NET Core-Runtime](runtime.md), um von anderen erstellte Apps auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1b1bf-450">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
