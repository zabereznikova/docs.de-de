---
title: Debuggen und Profilerstellung von Konfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die das Debuggen und die Profilerstellung für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: c57cfa7233f48def890ded3c9d589b7f268147df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74998858"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a><span data-ttu-id="dd3b4-103">Laufzeitkonfigurationsoptionen für das Debuggen und die Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="dd3b4-103">Run-time configuration options for debugging and profiling</span></span>

## <a name="enable-diagnostics"></a><span data-ttu-id="dd3b4-104">Aktivieren der Diagnosefunktion</span><span class="sxs-lookup"><span data-stu-id="dd3b4-104">Enable diagnostics</span></span>

- <span data-ttu-id="dd3b4-105">Konfiguriert, ob der Debugger, der Profiler und die EventPipe-Diagnose aktiviert oder deaktiviert sind</span><span class="sxs-lookup"><span data-stu-id="dd3b4-105">Configures whether the debugger, the profiler, and EventPipe diagnostics are enabled or disabled.</span></span>
- <span data-ttu-id="dd3b4-106">Standard: Aktiviert (`1`)</span><span class="sxs-lookup"><span data-stu-id="dd3b4-106">Default: Enabled (`1`).</span></span>

| | <span data-ttu-id="dd3b4-107">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="dd3b4-107">Setting name</span></span> | <span data-ttu-id="dd3b4-108">Werte</span><span class="sxs-lookup"><span data-stu-id="dd3b4-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="dd3b4-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="dd3b4-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="dd3b4-110">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="dd3b4-110">N/A</span></span> | <span data-ttu-id="dd3b4-111">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="dd3b4-111">N/A</span></span> |
| <span data-ttu-id="dd3b4-112">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="dd3b4-112">**Environment variable**</span></span> | `COMPlus_EnableDiagnostics` | <span data-ttu-id="dd3b4-113">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="dd3b4-113">`1` - enabled</span></span><br/><span data-ttu-id="dd3b4-114">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="dd3b4-114">`0` - disabled</span></span> |

## <a name="enable-profiling"></a><span data-ttu-id="dd3b4-115">Aktivieren der Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="dd3b4-115">Enable profiling</span></span>

- <span data-ttu-id="dd3b4-116">Konfiguriert, ob die Profilerstellung für den aktuell laufenden Prozess aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="dd3b4-116">Configures whether profiling is enabled for the currently running process.</span></span>
- <span data-ttu-id="dd3b4-117">Standard: Deaktiviert (`0`)</span><span class="sxs-lookup"><span data-stu-id="dd3b4-117">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="dd3b4-118">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="dd3b4-118">Setting name</span></span> | <span data-ttu-id="dd3b4-119">Werte</span><span class="sxs-lookup"><span data-stu-id="dd3b4-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="dd3b4-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="dd3b4-120">**runtimeconfig.json**</span></span> | <span data-ttu-id="dd3b4-121">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="dd3b4-121">N/A</span></span> | <span data-ttu-id="dd3b4-122">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="dd3b4-122">N/A</span></span> |
| <span data-ttu-id="dd3b4-123">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="dd3b4-123">**Environment variable**</span></span> | `CORECLR_ENABLE_PROFILING` | <span data-ttu-id="dd3b4-124">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="dd3b4-124">`0` - disabled</span></span><br/><span data-ttu-id="dd3b4-125">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="dd3b4-125">`1` - enabled</span></span> |

## <a name="profiler-guid"></a><span data-ttu-id="dd3b4-126">GUID des Profilers</span><span class="sxs-lookup"><span data-stu-id="dd3b4-126">Profiler GUID</span></span>

- <span data-ttu-id="dd3b4-127">Gibt die GUID des Profilers an, der in den aktuell laufenden Prozess geladen werden soll</span><span class="sxs-lookup"><span data-stu-id="dd3b4-127">Specifies the GUID of the profiler to load into the currently running process.</span></span>

| | <span data-ttu-id="dd3b4-128">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="dd3b4-128">Setting name</span></span> | <span data-ttu-id="dd3b4-129">Werte</span><span class="sxs-lookup"><span data-stu-id="dd3b4-129">Values</span></span> |
| - | - | - |
| <span data-ttu-id="dd3b4-130">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="dd3b4-130">**runtimeconfig.json**</span></span> | <span data-ttu-id="dd3b4-131">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="dd3b4-131">N/A</span></span> | <span data-ttu-id="dd3b4-132">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="dd3b4-132">N/A</span></span> |
| <span data-ttu-id="dd3b4-133">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="dd3b4-133">**Environment variable**</span></span> | `CORECLR_PROFILER` | <span data-ttu-id="dd3b4-134">*string-guid*</span><span class="sxs-lookup"><span data-stu-id="dd3b4-134">*string-guid*</span></span> |

## <a name="profiler-location"></a><span data-ttu-id="dd3b4-135">Speicherort des Profilers</span><span class="sxs-lookup"><span data-stu-id="dd3b4-135">Profiler location</span></span>

- <span data-ttu-id="dd3b4-136">Gibt den Pfad zur Profiler-DLL an, die in den aktuell laufenden Prozess geladen werden soll (32-Bit- oder 64-Bit-Paket)</span><span class="sxs-lookup"><span data-stu-id="dd3b4-136">Specifies the path to the profiler DLL to load into the currently running process (or 32-bit or 64-bit process).</span></span>
- <span data-ttu-id="dd3b4-137">Wenn mehr als eine Variable festgelegt ist, haben die für die Bitanzahl spezifischen Variablen Vorrang.</span><span class="sxs-lookup"><span data-stu-id="dd3b4-137">If more than one variable is set, the bitness-specific variables take precedence.</span></span> <span data-ttu-id="dd3b4-138">Diese geben an, welche Bitanzahl von Profiler geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="dd3b4-138">They specify which bitness of profiler to load.</span></span>
- <span data-ttu-id="dd3b4-139">Weitere Informationen finden Sie unter [Suchen der Profilerbibliothek](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).</span><span class="sxs-lookup"><span data-stu-id="dd3b4-139">For more information, see [Finding the profiler library](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).</span></span>

| | <span data-ttu-id="dd3b4-140">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="dd3b4-140">Setting name</span></span> | <span data-ttu-id="dd3b4-141">Werte</span><span class="sxs-lookup"><span data-stu-id="dd3b4-141">Values</span></span> |
| - | - | - |
| <span data-ttu-id="dd3b4-142">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="dd3b4-142">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH` | <span data-ttu-id="dd3b4-143">*string-path*</span><span class="sxs-lookup"><span data-stu-id="dd3b4-143">*string-path*</span></span> |
| <span data-ttu-id="dd3b4-144">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="dd3b4-144">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_32` | <span data-ttu-id="dd3b4-145">*string-path*</span><span class="sxs-lookup"><span data-stu-id="dd3b4-145">*string-path*</span></span> |
| <span data-ttu-id="dd3b4-146">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="dd3b4-146">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_64` | <span data-ttu-id="dd3b4-147">*string-path*</span><span class="sxs-lookup"><span data-stu-id="dd3b4-147">*string-path*</span></span> |

## <a name="write-perf-map"></a><span data-ttu-id="dd3b4-148">Schreiben von Leistungszuordnungen</span><span class="sxs-lookup"><span data-stu-id="dd3b4-148">Write perf map</span></span>

- <span data-ttu-id="dd3b4-149">Aktiviert oder deaktiviert das Schreiben von */tmp/perf-$pid.map* auf Linux-Systemen.</span><span class="sxs-lookup"><span data-stu-id="dd3b4-149">Enables or disables writing */tmp/perf-$pid.map* on Linux systems.</span></span>
- <span data-ttu-id="dd3b4-150">Standard: Deaktiviert (`0`)</span><span class="sxs-lookup"><span data-stu-id="dd3b4-150">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="dd3b4-151">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="dd3b4-151">Setting name</span></span> | <span data-ttu-id="dd3b4-152">Werte</span><span class="sxs-lookup"><span data-stu-id="dd3b4-152">Values</span></span> |
| - | - | - |
| <span data-ttu-id="dd3b4-153">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="dd3b4-153">**runtimeconfig.json**</span></span> | <span data-ttu-id="dd3b4-154">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="dd3b4-154">N/A</span></span> | <span data-ttu-id="dd3b4-155">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="dd3b4-155">N/A</span></span> |
| <span data-ttu-id="dd3b4-156">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="dd3b4-156">**Environment variable**</span></span> | `COMPlus_PerfMapEnabled` | <span data-ttu-id="dd3b4-157">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="dd3b4-157">`0` - disabled</span></span><br/><span data-ttu-id="dd3b4-158">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="dd3b4-158">`1` - enabled</span></span> |

## <a name="perf-log-markers"></a><span data-ttu-id="dd3b4-159">Leistungsprotokollmarker</span><span class="sxs-lookup"><span data-stu-id="dd3b4-159">Perf log markers</span></span>

- <span data-ttu-id="dd3b4-160">Aktiviert oder deaktiviert das angegebene Signal, um als Marker in den Leistungsprotokollen akzeptiert oder ignoriert zu werden, wenn `COMPlus_PerfMapEnabled` auf `1` festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="dd3b4-160">When `COMPlus_PerfMapEnabled` is set to `1`, enables or disables the specified signal to be accepted and ignored as a marker in the perf logs.</span></span>
- <span data-ttu-id="dd3b4-161">Standard: Deaktiviert (`0`)</span><span class="sxs-lookup"><span data-stu-id="dd3b4-161">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="dd3b4-162">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="dd3b4-162">Setting name</span></span> | <span data-ttu-id="dd3b4-163">Werte</span><span class="sxs-lookup"><span data-stu-id="dd3b4-163">Values</span></span> |
| - | - | - |
| <span data-ttu-id="dd3b4-164">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="dd3b4-164">**runtimeconfig.json**</span></span> | <span data-ttu-id="dd3b4-165">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="dd3b4-165">N/A</span></span> | <span data-ttu-id="dd3b4-166">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="dd3b4-166">N/A</span></span> |
| <span data-ttu-id="dd3b4-167">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="dd3b4-167">**Environment variable**</span></span> | `COMPlus_PerfMapIgnoreSignal` | <span data-ttu-id="dd3b4-168">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="dd3b4-168">`0` - disabled</span></span><br/><span data-ttu-id="dd3b4-169">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="dd3b4-169">`1` - enabled</span></span> |
