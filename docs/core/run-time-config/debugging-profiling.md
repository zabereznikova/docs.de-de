---
title: Debuggen und Profilerstellung von Konfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die das Debuggen und die Profilerstellung für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 5efd0f776da4b7ce6ff7f3bdfda24feec6e00f79
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761992"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a><span data-ttu-id="2e5c1-103">Laufzeitkonfigurationsoptionen für das Debuggen und die Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="2e5c1-103">Run-time configuration options for debugging and profiling</span></span>

## <a name="enable-diagnostics"></a><span data-ttu-id="2e5c1-104">Aktivieren der Diagnosefunktion</span><span class="sxs-lookup"><span data-stu-id="2e5c1-104">Enable diagnostics</span></span>

- <span data-ttu-id="2e5c1-105">Konfiguriert, ob der Debugger, der Profiler und die EventPipe-Diagnose aktiviert oder deaktiviert sind</span><span class="sxs-lookup"><span data-stu-id="2e5c1-105">Configures whether the debugger, the profiler, and EventPipe diagnostics are enabled or disabled.</span></span>
- <span data-ttu-id="2e5c1-106">Wenn Sie diese Einstellung weglassen, wird die Diagnose aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2e5c1-106">If you omit this setting, diagnostics are enabled.</span></span> <span data-ttu-id="2e5c1-107">Dies entspricht der Einstellung des Werts auf `1`.</span><span class="sxs-lookup"><span data-stu-id="2e5c1-107">This is equivalent to setting the value to `1`.</span></span>

| | <span data-ttu-id="2e5c1-108">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="2e5c1-108">Setting name</span></span> | <span data-ttu-id="2e5c1-109">Werte</span><span class="sxs-lookup"><span data-stu-id="2e5c1-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="2e5c1-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="2e5c1-110">**runtimeconfig.json**</span></span> | <span data-ttu-id="2e5c1-111">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="2e5c1-111">N/A</span></span> | <span data-ttu-id="2e5c1-112">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="2e5c1-112">N/A</span></span> |
| <span data-ttu-id="2e5c1-113">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="2e5c1-113">**Environment variable**</span></span> | `COMPlus_EnableDiagnostics` | <span data-ttu-id="2e5c1-114">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="2e5c1-114">`1` - enabled</span></span><br/><span data-ttu-id="2e5c1-115">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="2e5c1-115">`0` - disabled</span></span> |

## <a name="enable-profiling"></a><span data-ttu-id="2e5c1-116">Aktivieren der Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="2e5c1-116">Enable profiling</span></span>

- <span data-ttu-id="2e5c1-117">Konfiguriert, ob die Profilerstellung für den aktuell laufenden Prozess aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="2e5c1-117">Configures whether profiling is enabled for the currently running process.</span></span>
- <span data-ttu-id="2e5c1-118">Wenn Sie diese Einstellung weglassen, ist die Profilerstellung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2e5c1-118">If you omit this setting, profiling is disabled.</span></span> <span data-ttu-id="2e5c1-119">Dies entspricht der Einstellung des Werts auf `0`.</span><span class="sxs-lookup"><span data-stu-id="2e5c1-119">This is equivalent to setting the value to `0`.</span></span>

| | <span data-ttu-id="2e5c1-120">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="2e5c1-120">Setting name</span></span> | <span data-ttu-id="2e5c1-121">Werte</span><span class="sxs-lookup"><span data-stu-id="2e5c1-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="2e5c1-122">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="2e5c1-122">**runtimeconfig.json**</span></span> | <span data-ttu-id="2e5c1-123">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="2e5c1-123">N/A</span></span> | <span data-ttu-id="2e5c1-124">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="2e5c1-124">N/A</span></span> |
| <span data-ttu-id="2e5c1-125">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="2e5c1-125">**Environment variable**</span></span> | `CORECLR_ENABLE_PROFILING` | <span data-ttu-id="2e5c1-126">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="2e5c1-126">`0` - disabled</span></span><br/><span data-ttu-id="2e5c1-127">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="2e5c1-127">`1` - enabled</span></span> |

## <a name="profiler-guid"></a><span data-ttu-id="2e5c1-128">GUID des Profilers</span><span class="sxs-lookup"><span data-stu-id="2e5c1-128">Profiler GUID</span></span>

- <span data-ttu-id="2e5c1-129">Gibt die GUID des Profilers an, der in den aktuell laufenden Prozess geladen werden soll</span><span class="sxs-lookup"><span data-stu-id="2e5c1-129">Specifies the GUID of the profiler to load into the currently running process.</span></span>

| | <span data-ttu-id="2e5c1-130">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="2e5c1-130">Setting name</span></span> | <span data-ttu-id="2e5c1-131">Werte</span><span class="sxs-lookup"><span data-stu-id="2e5c1-131">Values</span></span> |
| - | - | - |
| <span data-ttu-id="2e5c1-132">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="2e5c1-132">**runtimeconfig.json**</span></span> | <span data-ttu-id="2e5c1-133">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="2e5c1-133">N/A</span></span> | <span data-ttu-id="2e5c1-134">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="2e5c1-134">N/A</span></span> |
| <span data-ttu-id="2e5c1-135">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="2e5c1-135">**Environment variable**</span></span> | `CORECLR_PROFILER` | <span data-ttu-id="2e5c1-136">*string-guid*</span><span class="sxs-lookup"><span data-stu-id="2e5c1-136">*string-guid*</span></span> |

## <a name="profiler-location"></a><span data-ttu-id="2e5c1-137">Speicherort des Profilers</span><span class="sxs-lookup"><span data-stu-id="2e5c1-137">Profiler location</span></span>

- <span data-ttu-id="2e5c1-138">Gibt den Pfad zur Profiler-DLL an, die in den aktuell laufenden Prozess geladen werden soll (32-Bit- oder 64-Bit-Paket)</span><span class="sxs-lookup"><span data-stu-id="2e5c1-138">Specifies the path to the profiler DLL to load into the currently running process (or 32-bit or 64-bit process).</span></span>
- <span data-ttu-id="2e5c1-139">Wenn mehr als eine Variable festgelegt ist, haben die für die Bitanzahl spezifischen Variablen Vorrang.</span><span class="sxs-lookup"><span data-stu-id="2e5c1-139">If more than one variable is set, the bitness-specific variables take precedence.</span></span> <span data-ttu-id="2e5c1-140">Diese geben an, welche Bitanzahl von Profiler geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="2e5c1-140">They specify which bitness of profiler to load.</span></span>
- <span data-ttu-id="2e5c1-141">Weitere Informationen finden Sie unter [Suchen der Profilerbibliothek](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).</span><span class="sxs-lookup"><span data-stu-id="2e5c1-141">For more information, see [Finding the profiler library](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).</span></span>

| | <span data-ttu-id="2e5c1-142">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="2e5c1-142">Setting name</span></span> | <span data-ttu-id="2e5c1-143">Werte</span><span class="sxs-lookup"><span data-stu-id="2e5c1-143">Values</span></span> |
| - | - | - |
| <span data-ttu-id="2e5c1-144">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="2e5c1-144">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH` | <span data-ttu-id="2e5c1-145">*string-path*</span><span class="sxs-lookup"><span data-stu-id="2e5c1-145">*string-path*</span></span> |
| <span data-ttu-id="2e5c1-146">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="2e5c1-146">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_32` | <span data-ttu-id="2e5c1-147">*string-path*</span><span class="sxs-lookup"><span data-stu-id="2e5c1-147">*string-path*</span></span> |
| <span data-ttu-id="2e5c1-148">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="2e5c1-148">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_64` | <span data-ttu-id="2e5c1-149">*string-path*</span><span class="sxs-lookup"><span data-stu-id="2e5c1-149">*string-path*</span></span> |

## <a name="write-perf-map"></a><span data-ttu-id="2e5c1-150">Schreiben von Leistungszuordnungen</span><span class="sxs-lookup"><span data-stu-id="2e5c1-150">Write perf map</span></span>

- <span data-ttu-id="2e5c1-151">Aktiviert oder deaktiviert das Schreiben von */tmp/perf-$pid.map* auf Linux-Systemen.</span><span class="sxs-lookup"><span data-stu-id="2e5c1-151">Enables or disables writing */tmp/perf-$pid.map* on Linux systems.</span></span>
- <span data-ttu-id="2e5c1-152">Wenn Sie diese Einstellung weglassen, ist das Schreiben von Leistungszuordnungen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2e5c1-152">If you omit this setting, writing the perf map is disabled.</span></span> <span data-ttu-id="2e5c1-153">Dies entspricht der Einstellung des Werts auf `0`.</span><span class="sxs-lookup"><span data-stu-id="2e5c1-153">This is equivalent to setting the value to `0`.</span></span>

| | <span data-ttu-id="2e5c1-154">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="2e5c1-154">Setting name</span></span> | <span data-ttu-id="2e5c1-155">Werte</span><span class="sxs-lookup"><span data-stu-id="2e5c1-155">Values</span></span> |
| - | - | - |
| <span data-ttu-id="2e5c1-156">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="2e5c1-156">**runtimeconfig.json**</span></span> | <span data-ttu-id="2e5c1-157">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="2e5c1-157">N/A</span></span> | <span data-ttu-id="2e5c1-158">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="2e5c1-158">N/A</span></span> |
| <span data-ttu-id="2e5c1-159">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="2e5c1-159">**Environment variable**</span></span> | `COMPlus_PerfMapEnabled` | <span data-ttu-id="2e5c1-160">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="2e5c1-160">`0` - disabled</span></span><br/><span data-ttu-id="2e5c1-161">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="2e5c1-161">`1` - enabled</span></span> |

## <a name="perf-log-markers"></a><span data-ttu-id="2e5c1-162">Leistungsprotokollmarker</span><span class="sxs-lookup"><span data-stu-id="2e5c1-162">Perf log markers</span></span>

- <span data-ttu-id="2e5c1-163">Aktiviert oder deaktiviert das angegebene Signal, um als Marker in den Leistungsprotokollen akzeptiert oder ignoriert zu werden.</span><span class="sxs-lookup"><span data-stu-id="2e5c1-163">Enables or disables the specified signal to be accepted and ignored as a marker in the perf logs.</span></span>
- <span data-ttu-id="2e5c1-164">Wenn Sie diese Einstellung weglassen, wird das angegebene Signal nicht ignoriert.</span><span class="sxs-lookup"><span data-stu-id="2e5c1-164">If you omit this setting, the specified signal is not ignored.</span></span> <span data-ttu-id="2e5c1-165">Dies entspricht der Einstellung des Werts auf `0`.</span><span class="sxs-lookup"><span data-stu-id="2e5c1-165">This is equivalent to setting the value to `0`.</span></span>

| | <span data-ttu-id="2e5c1-166">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="2e5c1-166">Setting name</span></span> | <span data-ttu-id="2e5c1-167">Werte</span><span class="sxs-lookup"><span data-stu-id="2e5c1-167">Values</span></span> |
| - | - | - |
| <span data-ttu-id="2e5c1-168">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="2e5c1-168">**runtimeconfig.json**</span></span> | <span data-ttu-id="2e5c1-169">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="2e5c1-169">N/A</span></span> | <span data-ttu-id="2e5c1-170">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="2e5c1-170">N/A</span></span> |
| <span data-ttu-id="2e5c1-171">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="2e5c1-171">**Environment variable**</span></span> | `COMPlus_PerfMapIgnoreSignal` | <span data-ttu-id="2e5c1-172">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="2e5c1-172">`0` - disabled</span></span><br/><span data-ttu-id="2e5c1-173">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="2e5c1-173">`1` - enabled</span></span> |

> [!NOTE]
> <span data-ttu-id="2e5c1-174">Diese Einstellung wird ignoriert, wenn [COMPlus_PerfMapEnabled](#write-perf-map) ausgelassen oder auf `0` festgelegt wird (d. h. deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="2e5c1-174">This setting is ignored if [COMPlus_PerfMapEnabled](#write-perf-map) is omitted or set to `0` (that is, disabled).</span></span>
