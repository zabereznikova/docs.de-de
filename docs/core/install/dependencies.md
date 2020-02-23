---
title: '.NET Core SDK und Runtimeabhängigkeiten: .NET Core'
description: In diesem Artikel werden die Voraussetzungen für das Betriebssystem und die CPU-Architektur zum Installieren des .NET Core SDK und der Runtime unter Windows, Linux und macOS erläutert.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 4164ea5a04d80ab20109168a225b793b02ee616a
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448892"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="85b31-103">.NET Core-Abhängigkeiten und -Anforderungen</span><span class="sxs-lookup"><span data-stu-id="85b31-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="85b31-104">In diesem Artikel wird erläutert, welche Betriebssysteme und CPU-Architektur von .NET Core unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="85b31-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="85b31-105">Unterstützte Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="85b31-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="85b31-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="85b31-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="85b31-107">Die folgenden Windows-Versionen werden von .NET Core 3.1 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="85b31-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="85b31-108">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="85b31-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="85b31-109">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="85b31-109">OS</span></span>                            | <span data-ttu-id="85b31-110">Version</span><span class="sxs-lookup"><span data-stu-id="85b31-110">Version</span></span>                        | <span data-ttu-id="85b31-111">Architekturen</span><span class="sxs-lookup"><span data-stu-id="85b31-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="85b31-112">Windows-Client</span><span class="sxs-lookup"><span data-stu-id="85b31-112">Windows Client</span></span>                | <span data-ttu-id="85b31-113">7 SP1 oder höher, 8.1</span><span class="sxs-lookup"><span data-stu-id="85b31-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="85b31-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="85b31-114">x64, x86</span></span>        |
| <span data-ttu-id="85b31-115">Windows 10-Client</span><span class="sxs-lookup"><span data-stu-id="85b31-115">Windows 10 Client</span></span>             | <span data-ttu-id="85b31-116">Version 1607 oder höher</span><span class="sxs-lookup"><span data-stu-id="85b31-116">Version 1607+</span></span>                  | <span data-ttu-id="85b31-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="85b31-117">x64, x86</span></span>        |
| <span data-ttu-id="85b31-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="85b31-118">Windows Server</span></span>                | <span data-ttu-id="85b31-119">2012 R2 oder höher</span><span class="sxs-lookup"><span data-stu-id="85b31-119">2012 R2+</span></span>                       | <span data-ttu-id="85b31-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="85b31-120">x64, x86</span></span>        |
| <span data-ttu-id="85b31-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="85b31-121">Nano Server</span></span>                   | <span data-ttu-id="85b31-122">Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="85b31-122">Version 1803+</span></span>                  | <span data-ttu-id="85b31-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="85b31-123">x64, ARM32</span></span>      |

<span data-ttu-id="85b31-124">Weitere Informationen zu den von .NET Core 3.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="85b31-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="85b31-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="85b31-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="85b31-126">Die folgenden Windows-Versionen werden von .NET Core 3.0 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="85b31-126">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="85b31-127">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="85b31-127">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="85b31-128">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="85b31-128">OS</span></span>                            | <span data-ttu-id="85b31-129">Version</span><span class="sxs-lookup"><span data-stu-id="85b31-129">Version</span></span>                        | <span data-ttu-id="85b31-130">Architekturen</span><span class="sxs-lookup"><span data-stu-id="85b31-130">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="85b31-131">Windows-Client</span><span class="sxs-lookup"><span data-stu-id="85b31-131">Windows Client</span></span>                | <span data-ttu-id="85b31-132">7 SP1 oder höher, 8.1</span><span class="sxs-lookup"><span data-stu-id="85b31-132">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="85b31-133">x64, x86</span><span class="sxs-lookup"><span data-stu-id="85b31-133">x64, x86</span></span>        |
| <span data-ttu-id="85b31-134">Windows 10-Client</span><span class="sxs-lookup"><span data-stu-id="85b31-134">Windows 10 Client</span></span>             | <span data-ttu-id="85b31-135">Version 1607 oder höher</span><span class="sxs-lookup"><span data-stu-id="85b31-135">Version 1607+</span></span>                  | <span data-ttu-id="85b31-136">x64, x86</span><span class="sxs-lookup"><span data-stu-id="85b31-136">x64, x86</span></span>        |
| <span data-ttu-id="85b31-137">Windows Server</span><span class="sxs-lookup"><span data-stu-id="85b31-137">Windows Server</span></span>                | <span data-ttu-id="85b31-138">2012 R2 oder höher</span><span class="sxs-lookup"><span data-stu-id="85b31-138">2012 R2+</span></span>                       | <span data-ttu-id="85b31-139">x64, x86</span><span class="sxs-lookup"><span data-stu-id="85b31-139">x64, x86</span></span>        |
| <span data-ttu-id="85b31-140">Nano Server</span><span class="sxs-lookup"><span data-stu-id="85b31-140">Nano Server</span></span>                   | <span data-ttu-id="85b31-141">Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="85b31-141">Version 1803+</span></span>                  | <span data-ttu-id="85b31-142">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="85b31-142">x64, ARM32</span></span>      |

<span data-ttu-id="85b31-143">Weitere Informationen zu den von .NET Core 3.0 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.0 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="85b31-143">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="85b31-144">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="85b31-144">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="85b31-145">Die folgenden Windows-Versionen werden von .NET Core 2.2 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="85b31-145">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="85b31-146">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="85b31-146">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="85b31-147">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="85b31-147">OS</span></span>                            | <span data-ttu-id="85b31-148">Version</span><span class="sxs-lookup"><span data-stu-id="85b31-148">Version</span></span>                        | <span data-ttu-id="85b31-149">Architekturen</span><span class="sxs-lookup"><span data-stu-id="85b31-149">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="85b31-150">Windows-Client</span><span class="sxs-lookup"><span data-stu-id="85b31-150">Windows Client</span></span>                | <span data-ttu-id="85b31-151">7 SP1 oder höher, 8.1</span><span class="sxs-lookup"><span data-stu-id="85b31-151">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="85b31-152">x64, x86</span><span class="sxs-lookup"><span data-stu-id="85b31-152">x64, x86</span></span>        |
| <span data-ttu-id="85b31-153">Windows 10-Client</span><span class="sxs-lookup"><span data-stu-id="85b31-153">Windows 10 Client</span></span>             | <span data-ttu-id="85b31-154">Version 1607 oder höher</span><span class="sxs-lookup"><span data-stu-id="85b31-154">Version 1607+</span></span>                  | <span data-ttu-id="85b31-155">x64, x86</span><span class="sxs-lookup"><span data-stu-id="85b31-155">x64, x86</span></span>        |
| <span data-ttu-id="85b31-156">Windows Server</span><span class="sxs-lookup"><span data-stu-id="85b31-156">Windows Server</span></span>                | <span data-ttu-id="85b31-157">2008 R2 SP1 oder höher</span><span class="sxs-lookup"><span data-stu-id="85b31-157">2008 R2 SP1+</span></span>                   | <span data-ttu-id="85b31-158">x64, x86</span><span class="sxs-lookup"><span data-stu-id="85b31-158">x64, x86</span></span>        |
| <span data-ttu-id="85b31-159">Nano Server</span><span class="sxs-lookup"><span data-stu-id="85b31-159">Nano Server</span></span>                   | <span data-ttu-id="85b31-160">Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="85b31-160">Version 1803+</span></span>                   | <span data-ttu-id="85b31-161">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="85b31-161">x64, ARM32</span></span>      |

<span data-ttu-id="85b31-162">Weitere Informationen zu den von .NET Core 2.2 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.2 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="85b31-162">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="85b31-163">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="85b31-163">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="85b31-164">Die folgenden Windows-Versionen werden von .NET Core 2.1 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="85b31-164">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="85b31-165">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="85b31-165">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="85b31-166">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="85b31-166">OS</span></span>                            | <span data-ttu-id="85b31-167">Version</span><span class="sxs-lookup"><span data-stu-id="85b31-167">Version</span></span>                        | <span data-ttu-id="85b31-168">Architekturen</span><span class="sxs-lookup"><span data-stu-id="85b31-168">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="85b31-169">Windows-Client</span><span class="sxs-lookup"><span data-stu-id="85b31-169">Windows Client</span></span>                | <span data-ttu-id="85b31-170">7 SP1 oder höher, 8.1</span><span class="sxs-lookup"><span data-stu-id="85b31-170">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="85b31-171">x64, x86</span><span class="sxs-lookup"><span data-stu-id="85b31-171">x64, x86</span></span>        |
| <span data-ttu-id="85b31-172">Windows 10-Client</span><span class="sxs-lookup"><span data-stu-id="85b31-172">Windows 10 Client</span></span>             | <span data-ttu-id="85b31-173">Version 1607 oder höher</span><span class="sxs-lookup"><span data-stu-id="85b31-173">Version 1607+</span></span>                  | <span data-ttu-id="85b31-174">x64, x86</span><span class="sxs-lookup"><span data-stu-id="85b31-174">x64, x86</span></span>        |
| <span data-ttu-id="85b31-175">Windows Server</span><span class="sxs-lookup"><span data-stu-id="85b31-175">Windows Server</span></span>                | <span data-ttu-id="85b31-176">2008 R2 SP1 oder höher</span><span class="sxs-lookup"><span data-stu-id="85b31-176">2008 R2 SP1+</span></span>                   | <span data-ttu-id="85b31-177">x64, x86</span><span class="sxs-lookup"><span data-stu-id="85b31-177">x64, x86</span></span>        |
| <span data-ttu-id="85b31-178">Nano Server</span><span class="sxs-lookup"><span data-stu-id="85b31-178">Nano Server</span></span>                   | <span data-ttu-id="85b31-179">Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="85b31-179">Version 1803+</span></span>                  | <span data-ttu-id="85b31-180">x64,</span><span class="sxs-lookup"><span data-stu-id="85b31-180">x64,</span></span>            |

<span data-ttu-id="85b31-181">Weitere Informationen zu den von .NET Core 2.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="85b31-181">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="85b31-182">Windows 7/Vista/8.1/Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="85b31-182">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="85b31-183">Weitere Abhängigkeiten sind erforderlich, wenn Sie das .NET SDK oder die Runtime unter den folgenden Windows-Versionen installieren:</span><span class="sxs-lookup"><span data-stu-id="85b31-183">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="85b31-184">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="85b31-184">Windows 7 SP1</span></span>
- <span data-ttu-id="85b31-185">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="85b31-185">Windows Vista SP 2</span></span>
- <span data-ttu-id="85b31-186">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="85b31-186">Windows 8.1</span></span>
- <span data-ttu-id="85b31-187">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="85b31-187">Windows Server 2008 R2</span></span>
- <span data-ttu-id="85b31-188">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="85b31-188">Windows Server 2012 R2</span></span>

<span data-ttu-id="85b31-189">Installieren Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="85b31-189">Install the following:</span></span>

- <span data-ttu-id="85b31-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685)</span><span class="sxs-lookup"><span data-stu-id="85b31-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="85b31-191">KB2533623</span><span class="sxs-lookup"><span data-stu-id="85b31-191">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="85b31-192">Die oben aufgeführten Anforderungen sind auch erforderlich, wenn einer der folgenden Fehler auftritt:</span><span class="sxs-lookup"><span data-stu-id="85b31-192">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="85b31-193">Das Programm kann nicht gestartet werden, da *api-ms-win-crt-runtime-l1-1-0.dll* auf dem Computer fehlt.</span><span class="sxs-lookup"><span data-stu-id="85b31-193">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="85b31-194">Installieren Sie das Programm erneut, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="85b31-194">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="85b31-195">\- oder -</span><span class="sxs-lookup"><span data-stu-id="85b31-195">\- or -</span></span>
>
> <span data-ttu-id="85b31-196">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed. (Die Bibliothek „hostfxr.dll“ wurde gefunden, aber der Ladevorgang aus C:\<Pfad_zu_App>\hostfxr.dll ist fehlgeschlagen.)</span><span class="sxs-lookup"><span data-stu-id="85b31-196">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="85b31-197">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="85b31-197">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="85b31-198">.NET Core 3.1 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="85b31-198">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="85b31-199">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="85b31-199">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="85b31-200">.NET Core 3.1 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="85b31-200">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="85b31-201">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="85b31-201">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="85b31-202">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="85b31-202">OS</span></span>                             | <span data-ttu-id="85b31-203">Version</span><span class="sxs-lookup"><span data-stu-id="85b31-203">Version</span></span>               | <span data-ttu-id="85b31-204">Architekturen</span><span class="sxs-lookup"><span data-stu-id="85b31-204">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="85b31-205">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="85b31-205">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="85b31-206">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="85b31-206">6, 7, 8</span></span>               | <span data-ttu-id="85b31-207">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-207">x64</span></span> |
| <span data-ttu-id="85b31-208">CentOS</span><span class="sxs-lookup"><span data-stu-id="85b31-208">CentOS</span></span>                         | <span data-ttu-id="85b31-209">7 und höher</span><span class="sxs-lookup"><span data-stu-id="85b31-209">7+</span></span>                    | <span data-ttu-id="85b31-210">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-210">x64</span></span> |
| <span data-ttu-id="85b31-211">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="85b31-211">Oracle Linux</span></span>                   | <span data-ttu-id="85b31-212">7 und höher</span><span class="sxs-lookup"><span data-stu-id="85b31-212">7+</span></span>                    | <span data-ttu-id="85b31-213">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-213">x64</span></span> |
| <span data-ttu-id="85b31-214">Fedora</span><span class="sxs-lookup"><span data-stu-id="85b31-214">Fedora</span></span>                         | <span data-ttu-id="85b31-215">29 und höher</span><span class="sxs-lookup"><span data-stu-id="85b31-215">29+</span></span>                   | <span data-ttu-id="85b31-216">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-216">x64</span></span> |
| <span data-ttu-id="85b31-217">Debian</span><span class="sxs-lookup"><span data-stu-id="85b31-217">Debian</span></span>                         | <span data-ttu-id="85b31-218">9 und höher</span><span class="sxs-lookup"><span data-stu-id="85b31-218">9+</span></span>                    | <span data-ttu-id="85b31-219">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="85b31-219">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="85b31-220">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="85b31-220">Ubuntu</span></span>                         | <span data-ttu-id="85b31-221">16.04 und höher</span><span class="sxs-lookup"><span data-stu-id="85b31-221">16.04+</span></span>                | <span data-ttu-id="85b31-222">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="85b31-222">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="85b31-223">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="85b31-223">Linux Mint</span></span>                     | <span data-ttu-id="85b31-224">18 und höher</span><span class="sxs-lookup"><span data-stu-id="85b31-224">18+</span></span>                   | <span data-ttu-id="85b31-225">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-225">x64</span></span> |
| <span data-ttu-id="85b31-226">openSUSE</span><span class="sxs-lookup"><span data-stu-id="85b31-226">openSUSE</span></span>                       | <span data-ttu-id="85b31-227">15 und höher</span><span class="sxs-lookup"><span data-stu-id="85b31-227">15+</span></span>                   | <span data-ttu-id="85b31-228">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-228">x64</span></span> |
| <span data-ttu-id="85b31-229">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="85b31-229">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="85b31-230">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="85b31-230">12 SP2+</span></span>               | <span data-ttu-id="85b31-231">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-231">x64</span></span> |
| <span data-ttu-id="85b31-232">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="85b31-232">Alpine Linux</span></span>                   | <span data-ttu-id="85b31-233">3.10 oder höher</span><span class="sxs-lookup"><span data-stu-id="85b31-233">3.10+</span></span>                 | <span data-ttu-id="85b31-234">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="85b31-234">x64, ARM64</span></span> |

<span data-ttu-id="85b31-235">Weitere Informationen zu den von .NET Core 3.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="85b31-235">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="85b31-236">Weitere Informationen zum Installieren von .NET Core 3.1 unter ARM64 (Kernel 4.14 oder höher) finden Sie unter [Installieren von .NET Core 3.0 unter Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span><span class="sxs-lookup"><span data-stu-id="85b31-236">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85b31-237">Für die Unterstützung von ARM64 ist Linux-Kernel 4.14 oder höher erforderlich.</span><span class="sxs-lookup"><span data-stu-id="85b31-237">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="85b31-238">Einige Linux-Verteilungen erfüllen diese Anforderung, andere hingegen nicht.</span><span class="sxs-lookup"><span data-stu-id="85b31-238">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="85b31-239">So wird Ubuntu 18.04 im Gegensatz zu Ubuntu 16.04 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="85b31-239">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="85b31-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="85b31-240">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="85b31-241">.NET Core 3.0 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="85b31-241">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="85b31-242">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="85b31-242">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="85b31-243">.NET Core 3.0 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="85b31-243">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="85b31-244">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="85b31-244">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="85b31-245">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="85b31-245">OS</span></span>                             | <span data-ttu-id="85b31-246">Version</span><span class="sxs-lookup"><span data-stu-id="85b31-246">Version</span></span>               | <span data-ttu-id="85b31-247">Architekturen</span><span class="sxs-lookup"><span data-stu-id="85b31-247">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="85b31-248">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="85b31-248">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="85b31-249">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="85b31-249">6, 7, 8</span></span>               | <span data-ttu-id="85b31-250">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-250">x64</span></span> |
| <span data-ttu-id="85b31-251">CentOS</span><span class="sxs-lookup"><span data-stu-id="85b31-251">CentOS</span></span>                         | <span data-ttu-id="85b31-252">7 und höher</span><span class="sxs-lookup"><span data-stu-id="85b31-252">7+</span></span>                    | <span data-ttu-id="85b31-253">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-253">x64</span></span> |
| <span data-ttu-id="85b31-254">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="85b31-254">Oracle Linux</span></span>                   | <span data-ttu-id="85b31-255">7 und höher</span><span class="sxs-lookup"><span data-stu-id="85b31-255">7+</span></span>                    | <span data-ttu-id="85b31-256">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-256">x64</span></span> |
| <span data-ttu-id="85b31-257">Fedora</span><span class="sxs-lookup"><span data-stu-id="85b31-257">Fedora</span></span>                         | <span data-ttu-id="85b31-258">29 und höher</span><span class="sxs-lookup"><span data-stu-id="85b31-258">29+</span></span>                   | <span data-ttu-id="85b31-259">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-259">x64</span></span> |
| <span data-ttu-id="85b31-260">Debian</span><span class="sxs-lookup"><span data-stu-id="85b31-260">Debian</span></span>                         | <span data-ttu-id="85b31-261">9 und höher</span><span class="sxs-lookup"><span data-stu-id="85b31-261">9+</span></span>                    | <span data-ttu-id="85b31-262">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="85b31-262">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="85b31-263">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="85b31-263">Ubuntu</span></span>                         | <span data-ttu-id="85b31-264">16.04 und höher</span><span class="sxs-lookup"><span data-stu-id="85b31-264">16.04+</span></span>                | <span data-ttu-id="85b31-265">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="85b31-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="85b31-266">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="85b31-266">Linux Mint</span></span>                     | <span data-ttu-id="85b31-267">18 und höher</span><span class="sxs-lookup"><span data-stu-id="85b31-267">18+</span></span>                   | <span data-ttu-id="85b31-268">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-268">x64</span></span> |
| <span data-ttu-id="85b31-269">openSUSE</span><span class="sxs-lookup"><span data-stu-id="85b31-269">openSUSE</span></span>                       | <span data-ttu-id="85b31-270">15 und höher</span><span class="sxs-lookup"><span data-stu-id="85b31-270">15+</span></span>                   | <span data-ttu-id="85b31-271">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-271">x64</span></span> |
| <span data-ttu-id="85b31-272">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="85b31-272">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="85b31-273">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="85b31-273">12 SP2+</span></span>               | <span data-ttu-id="85b31-274">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-274">x64</span></span> |
| <span data-ttu-id="85b31-275">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="85b31-275">Alpine Linux</span></span>                   | <span data-ttu-id="85b31-276">3.8+</span><span class="sxs-lookup"><span data-stu-id="85b31-276">3.8+</span></span>                  | <span data-ttu-id="85b31-277">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="85b31-277">x64, ARM64</span></span> |

<span data-ttu-id="85b31-278">Weitere Informationen zu den von .NET Core 3.0 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.0 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="85b31-278">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="85b31-279">Weitere Informationen zum Installieren von .NET Core 3.0 unter ARM64 finden Sie unter [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Installieren von .NET Core 3.0 unter Linux ARM64).</span><span class="sxs-lookup"><span data-stu-id="85b31-279">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="85b31-280">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="85b31-280">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="85b31-281">.NET Core 2.2 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="85b31-281">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="85b31-282">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="85b31-282">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="85b31-283">.NET Core 2.2 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="85b31-283">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="85b31-284">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="85b31-284">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="85b31-285">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="85b31-285">OS</span></span>                             |  <span data-ttu-id="85b31-286">Version</span><span class="sxs-lookup"><span data-stu-id="85b31-286">Version</span></span>                |  <span data-ttu-id="85b31-287">Architekturen</span><span class="sxs-lookup"><span data-stu-id="85b31-287">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="85b31-288">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="85b31-288">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="85b31-289">6, 7</span><span class="sxs-lookup"><span data-stu-id="85b31-289">6, 7</span></span>                   | <span data-ttu-id="85b31-290">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-290">x64</span></span> |
| <span data-ttu-id="85b31-291">CentOS</span><span class="sxs-lookup"><span data-stu-id="85b31-291">CentOS</span></span>                         |  <span data-ttu-id="85b31-292">7</span><span class="sxs-lookup"><span data-stu-id="85b31-292">7</span></span>                      | <span data-ttu-id="85b31-293">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-293">x64</span></span> |
| <span data-ttu-id="85b31-294">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="85b31-294">Oracle Linux</span></span>                   |  <span data-ttu-id="85b31-295">7</span><span class="sxs-lookup"><span data-stu-id="85b31-295">7</span></span>                      | <span data-ttu-id="85b31-296">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-296">x64</span></span> |
| <span data-ttu-id="85b31-297">Fedora</span><span class="sxs-lookup"><span data-stu-id="85b31-297">Fedora</span></span>                         |  <span data-ttu-id="85b31-298">29, 30</span><span class="sxs-lookup"><span data-stu-id="85b31-298">29, 30</span></span>                 | <span data-ttu-id="85b31-299">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-299">x64</span></span> |
| <span data-ttu-id="85b31-300">Debian</span><span class="sxs-lookup"><span data-stu-id="85b31-300">Debian</span></span>                         |  <span data-ttu-id="85b31-301">9</span><span class="sxs-lookup"><span data-stu-id="85b31-301">9</span></span>                      | <span data-ttu-id="85b31-302">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="85b31-302">x64, ARM32</span></span> |
| <span data-ttu-id="85b31-303">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="85b31-303">Ubuntu</span></span>                         |  <span data-ttu-id="85b31-304">16.04, 18.04, 18.10</span><span class="sxs-lookup"><span data-stu-id="85b31-304">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="85b31-305">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="85b31-305">x64, ARM32</span></span> |
| <span data-ttu-id="85b31-306">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="85b31-306">Linux Mint</span></span>                     |  <span data-ttu-id="85b31-307">17, 18</span><span class="sxs-lookup"><span data-stu-id="85b31-307">17, 18</span></span>                 | <span data-ttu-id="85b31-308">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-308">x64</span></span> |
| <span data-ttu-id="85b31-309">openSUSE</span><span class="sxs-lookup"><span data-stu-id="85b31-309">openSUSE</span></span>                       |  <span data-ttu-id="85b31-310">15 und höher</span><span class="sxs-lookup"><span data-stu-id="85b31-310">15+</span></span>                    | <span data-ttu-id="85b31-311">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-311">x64</span></span> |
| <span data-ttu-id="85b31-312">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="85b31-312">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="85b31-313">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="85b31-313">12 SP2+</span></span>                | <span data-ttu-id="85b31-314">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-314">x64</span></span> |
| <span data-ttu-id="85b31-315">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="85b31-315">Alpine Linux</span></span>                   |  <span data-ttu-id="85b31-316">3.8+</span><span class="sxs-lookup"><span data-stu-id="85b31-316">3.8+</span></span>                   | <span data-ttu-id="85b31-317">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-317">x64</span></span> |

<span data-ttu-id="85b31-318">Weitere Informationen zu den von .NET Core 2.2 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.2 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="85b31-318">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="85b31-319">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="85b31-319">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="85b31-320">.NET Core 2.1 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="85b31-320">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="85b31-321">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="85b31-321">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="85b31-322">.NET Core 2.1 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="85b31-322">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="85b31-323">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="85b31-323">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="85b31-324">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="85b31-324">OS</span></span>                             |  <span data-ttu-id="85b31-325">Version</span><span class="sxs-lookup"><span data-stu-id="85b31-325">Version</span></span>                |  <span data-ttu-id="85b31-326">Architekturen</span><span class="sxs-lookup"><span data-stu-id="85b31-326">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="85b31-327">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="85b31-327">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="85b31-328">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="85b31-328">6, 7, 8</span></span>                | <span data-ttu-id="85b31-329">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-329">x64</span></span> |
| <span data-ttu-id="85b31-330">CentOS</span><span class="sxs-lookup"><span data-stu-id="85b31-330">CentOS</span></span>                         |  <span data-ttu-id="85b31-331">7 und höher</span><span class="sxs-lookup"><span data-stu-id="85b31-331">7+</span></span>                     | <span data-ttu-id="85b31-332">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-332">x64</span></span> |
| <span data-ttu-id="85b31-333">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="85b31-333">Oracle Linux</span></span>                   |  <span data-ttu-id="85b31-334">7 und höher</span><span class="sxs-lookup"><span data-stu-id="85b31-334">7+</span></span>                     | <span data-ttu-id="85b31-335">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-335">x64</span></span> |
| <span data-ttu-id="85b31-336">Fedora</span><span class="sxs-lookup"><span data-stu-id="85b31-336">Fedora</span></span>                         |  <span data-ttu-id="85b31-337">29 und höher</span><span class="sxs-lookup"><span data-stu-id="85b31-337">29+</span></span>                    | <span data-ttu-id="85b31-338">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-338">x64</span></span> |
| <span data-ttu-id="85b31-339">Debian</span><span class="sxs-lookup"><span data-stu-id="85b31-339">Debian</span></span>                         |  <span data-ttu-id="85b31-340">9</span><span class="sxs-lookup"><span data-stu-id="85b31-340">9</span></span>                      | <span data-ttu-id="85b31-341">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="85b31-341">x64, ARM32</span></span> |
| <span data-ttu-id="85b31-342">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="85b31-342">Ubuntu</span></span>                         |  <span data-ttu-id="85b31-343">16.04, 18.04, 19.04, 19.10</span><span class="sxs-lookup"><span data-stu-id="85b31-343">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="85b31-344">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="85b31-344">x64, ARM32</span></span> |
| <span data-ttu-id="85b31-345">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="85b31-345">Linux Mint</span></span>                     |  <span data-ttu-id="85b31-346">17 oder höher</span><span class="sxs-lookup"><span data-stu-id="85b31-346">17+</span></span>                    | <span data-ttu-id="85b31-347">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-347">x64</span></span> |
| <span data-ttu-id="85b31-348">openSUSE</span><span class="sxs-lookup"><span data-stu-id="85b31-348">openSUSE</span></span>                       |  <span data-ttu-id="85b31-349">15 und höher</span><span class="sxs-lookup"><span data-stu-id="85b31-349">15+</span></span>                    | <span data-ttu-id="85b31-350">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-350">x64</span></span> |
| <span data-ttu-id="85b31-351">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="85b31-351">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="85b31-352">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="85b31-352">12 SP2+</span></span>                | <span data-ttu-id="85b31-353">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-353">x64</span></span> |
| <span data-ttu-id="85b31-354">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="85b31-354">Alpine Linux</span></span>                   |  <span data-ttu-id="85b31-355">3.8+</span><span class="sxs-lookup"><span data-stu-id="85b31-355">3.8+</span></span>                   | <span data-ttu-id="85b31-356">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-356">x64</span></span> |

<span data-ttu-id="85b31-357">Weitere Informationen zu den von .NET Core 2.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="85b31-357">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="85b31-358">Abhängigkeiten der Linux-Distributionen</span><span class="sxs-lookup"><span data-stu-id="85b31-358">Linux distribution dependencies</span></span>

<span data-ttu-id="85b31-359">Basierend auf den Linux-Verteilungen müssen Sie möglicherweise zusätzliche Abhängigkeiten installieren.</span><span class="sxs-lookup"><span data-stu-id="85b31-359">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85b31-360">Die exakten Versionen und Namen können sich bei der von Ihnen verwendeten Linux-Verteilung leicht unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="85b31-360">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="85b31-361">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="85b31-361">Ubuntu</span></span>

<span data-ttu-id="85b31-362">Für Ubuntu-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:</span><span class="sxs-lookup"><span data-stu-id="85b31-362">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="85b31-363">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="85b31-363">liblttng-ust0</span></span>
- <span data-ttu-id="85b31-364">libcurl3 (für 14.x und 16.x)</span><span class="sxs-lookup"><span data-stu-id="85b31-364">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="85b31-365">libcurl4 (für 18.x)</span><span class="sxs-lookup"><span data-stu-id="85b31-365">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="85b31-366">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="85b31-366">libssl1.0.0</span></span>
- <span data-ttu-id="85b31-367">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="85b31-367">libkrb5-3</span></span>
- <span data-ttu-id="85b31-368">zlib1g</span><span class="sxs-lookup"><span data-stu-id="85b31-368">zlib1g</span></span>
- <span data-ttu-id="85b31-369">libicu52 (für 14.X)</span><span class="sxs-lookup"><span data-stu-id="85b31-369">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="85b31-370">libicu55 (für 16.X)</span><span class="sxs-lookup"><span data-stu-id="85b31-370">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="85b31-371">libicu57 (für 17.X)</span><span class="sxs-lookup"><span data-stu-id="85b31-371">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="85b31-372">libicu60 (für 18.X)</span><span class="sxs-lookup"><span data-stu-id="85b31-372">libicu60 (for 18.x)</span></span>

<span data-ttu-id="85b31-373">Für .NET Core-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="85b31-373">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="85b31-374">libgdiplus (Version 6.0.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="85b31-374">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="85b31-375">Die meisten Versionen von Ubuntu enthalten eine frühere Version von libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="85b31-375">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="85b31-376">Sie können eine neuere Version von libgdiplus installieren, indem Sie auf Ihrem System das Mono-Repository hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="85b31-376">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="85b31-377">Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="85b31-377">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="85b31-378">CentOS und Fedora</span><span class="sxs-lookup"><span data-stu-id="85b31-378">CentOS and Fedora</span></span>

<span data-ttu-id="85b31-379">Für CentOS-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:</span><span class="sxs-lookup"><span data-stu-id="85b31-379">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="85b31-380">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="85b31-380">lttng-ust</span></span>
- <span data-ttu-id="85b31-381">libcurl</span><span class="sxs-lookup"><span data-stu-id="85b31-381">libcurl</span></span>
- <span data-ttu-id="85b31-382">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="85b31-382">openssl-libs</span></span>
- <span data-ttu-id="85b31-383">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="85b31-383">krb5-libs</span></span>
- <span data-ttu-id="85b31-384">libicu</span><span class="sxs-lookup"><span data-stu-id="85b31-384">libicu</span></span>
- <span data-ttu-id="85b31-385">zlib</span><span class="sxs-lookup"><span data-stu-id="85b31-385">zlib</span></span>

<span data-ttu-id="85b31-386">Für Fedora-Benutzer: Wenn Ihre Version von OpenSSL Version 1.1 oder höher entspricht, müssen Sie **compat-openssl10** installieren.</span><span class="sxs-lookup"><span data-stu-id="85b31-386">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="85b31-387">Für .NET Core 2.0 sind außerdem die folgenden Abhängigkeiten erforderlich:</span><span class="sxs-lookup"><span data-stu-id="85b31-387">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="85b31-388">libunwind</span><span class="sxs-lookup"><span data-stu-id="85b31-388">libunwind</span></span>
- <span data-ttu-id="85b31-389">libuuid</span><span class="sxs-lookup"><span data-stu-id="85b31-389">libuuid</span></span>

<span data-ttu-id="85b31-390">Weitere Informationen zu den Abhängigkeiten finden Sie unter [Eigenständige Linux-Apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="85b31-390">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="85b31-391">Für .NET Core-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="85b31-391">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="85b31-392">libgdiplus (Version 6.0.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="85b31-392">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="85b31-393">Die meisten Versionen von CentOS und Fedora enthalten eine frühere Version von libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="85b31-393">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="85b31-394">Sie können eine neuere Version von libgdiplus installieren, indem Sie auf Ihrem System das Mono-Repository hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="85b31-394">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="85b31-395">Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="85b31-395">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="85b31-396">.NET Core wird von den folgenden macOS-Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="85b31-396">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="85b31-397">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="85b31-397">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="85b31-398">.NET Core-Version</span><span class="sxs-lookup"><span data-stu-id="85b31-398">.NET Core Version</span></span> | <span data-ttu-id="85b31-399">macOS</span><span class="sxs-lookup"><span data-stu-id="85b31-399">macOS</span></span>                 | <span data-ttu-id="85b31-400">Architekturen</span><span class="sxs-lookup"><span data-stu-id="85b31-400">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="85b31-401">3.1</span><span class="sxs-lookup"><span data-stu-id="85b31-401">3.1</span></span>               | <span data-ttu-id="85b31-402">High Sierra (10.13 oder höher)</span><span class="sxs-lookup"><span data-stu-id="85b31-402">High Sierra (10.13+)</span></span>  | <span data-ttu-id="85b31-403">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-403">x64</span></span> | [<span data-ttu-id="85b31-404">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85b31-404">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="85b31-405">3.0</span><span class="sxs-lookup"><span data-stu-id="85b31-405">3.0</span></span>               | <span data-ttu-id="85b31-406">High Sierra (10.13 oder höher)</span><span class="sxs-lookup"><span data-stu-id="85b31-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="85b31-407">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-407">x64</span></span> | [<span data-ttu-id="85b31-408">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85b31-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="85b31-409">2.2</span><span class="sxs-lookup"><span data-stu-id="85b31-409">2.2</span></span>               | <span data-ttu-id="85b31-410">Sierra (10.12 oder höher)</span><span class="sxs-lookup"><span data-stu-id="85b31-410">Sierra (10.12+)</span></span>       | <span data-ttu-id="85b31-411">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-411">x64</span></span> | [<span data-ttu-id="85b31-412">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85b31-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="85b31-413">2.1</span><span class="sxs-lookup"><span data-stu-id="85b31-413">2.1</span></span>               | <span data-ttu-id="85b31-414">Sierra (10.12 oder höher)</span><span class="sxs-lookup"><span data-stu-id="85b31-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="85b31-415">x64</span><span class="sxs-lookup"><span data-stu-id="85b31-415">x64</span></span> | [<span data-ttu-id="85b31-416">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85b31-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

## <a name="libgdiplus"></a><span data-ttu-id="85b31-417">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="85b31-417">libgdiplus</span></span>

<span data-ttu-id="85b31-418">Für .NET Core-Anwendungen, die die Assembly *System.Drawing.Common* verwenden, muss libgdiplus installiert sein.</span><span class="sxs-lookup"><span data-stu-id="85b31-418">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="85b31-419">Eine einfache Möglichkeit zum Abrufen von libgdiplus bietet der [Homebrew](https://brew.sh/)-Paket-Manager („brew“) für macOS.</span><span class="sxs-lookup"><span data-stu-id="85b31-419">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="85b31-420">Installieren Sie nach der Installation von *brew* libgdiplus durch Ausführen der folgenden Befehle in einem Terminal (Befehl):</span><span class="sxs-lookup"><span data-stu-id="85b31-420">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="85b31-421">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="85b31-421">Next steps</span></span>

- <span data-ttu-id="85b31-422">Installieren Sie das [.NET Core SDK](sdk.md) (einschließlich der Runtime), um Apps zu entwickeln und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="85b31-422">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="85b31-423">Installieren Sie die [.NET Core-Runtime](runtime.md), um von anderen erstellte Apps auszuführen.</span><span class="sxs-lookup"><span data-stu-id="85b31-423">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
