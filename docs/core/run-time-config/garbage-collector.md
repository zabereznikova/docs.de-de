---
title: Garbage-Collector-Konfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, um zu konfigurieren, wie der Garbage Collector Arbeitsspeicher für .NET Core-Apps verwaltet.
ms.date: 07/10/2020
ms.topic: reference
ms.openlocfilehash: 91d155b638c7e69b3d2c0216266a7c0c0410db4c
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915989"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="72e82-103">Laufzeitkonfigurationsoptionen für die Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="72e82-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="72e82-104">Diese Seite enthält Informationen zu Garbage-Collector-Einstellungen (GC), die zur Laufzeit geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="72e82-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="72e82-105">Verwenden Sie diese Einstellungen, wenn Sie versuchen, die maximale Leistung einer ausgeführten App zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="72e82-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="72e82-106">Die Standardwerte bieten jedoch in typischen Situationen eine optimale Leistung für die meisten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="72e82-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="72e82-107">Einstellungen werden auf dieser Seite in Gruppen angeordnet.</span><span class="sxs-lookup"><span data-stu-id="72e82-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="72e82-108">Die Einstellungen in den einzelnen Gruppen werden häufig zusammen verwendet, um ein bestimmtes Ergebnis zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="72e82-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="72e82-109">Diese Einstellungen können auch dynamisch von der App geändert werden, während diese ausgeführt wird, sodass die von Ihnen festgelegten Laufzeiteinstellungen überschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="72e82-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="72e82-110">Einige Einstellungen, wie z. B. die [Latenzebene](../../standard/garbage-collection/latency.md), werden in der Regel nur über die API zur Entwurfszeit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="72e82-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="72e82-111">Diese Einstellungen werden auf dieser Seite weggelassen.</span><span class="sxs-lookup"><span data-stu-id="72e82-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="72e82-112">Verwenden Sie für Zahlenwerte für Einstellungen in der Datei *runtimeconfig.json* die Dezimalschreibweise und für Einstellungen in der Umgebungsvariablen die Hexadezimalnotation.</span><span class="sxs-lookup"><span data-stu-id="72e82-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="72e82-113">Bei hexadezimalen Werten können Sie sie mit dem oder ohne das Präfix „0x“ angeben.</span><span class="sxs-lookup"><span data-stu-id="72e82-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="72e82-114">Varianten der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="72e82-114">Flavors of garbage collection</span></span>

<span data-ttu-id="72e82-115">Die zwei Hauptvarianten der Garbage Collection sind Arbeitsstation-GC und Server-GC.</span><span class="sxs-lookup"><span data-stu-id="72e82-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="72e82-116">Weitere Informationen zu den Unterschieden zwischen diesen beiden Varianten finden Sie unter [Garbage Collection für die Arbeitsstation und Garbage Collection auf dem Server](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="72e82-116">For more information about differences between the two, see [Workstation and server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span>

<span data-ttu-id="72e82-117">Die Untervarianten der Garbage Collection sind Hintergrund-GC und nicht gleichzeitige GC.</span><span class="sxs-lookup"><span data-stu-id="72e82-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="72e82-118">Verwenden Sie die folgenden Einstellungen, um Varianten der Garbage Collection auszuwählen:</span><span class="sxs-lookup"><span data-stu-id="72e82-118">Use the following settings to select flavors of garbage collection:</span></span>

- [<span data-ttu-id="72e82-119">Garbage Collection für Arbeitsstationen und Server im Vergleich</span><span class="sxs-lookup"><span data-stu-id="72e82-119">Workstation vs. server GC</span></span>](#workstation-vs-server)
- [<span data-ttu-id="72e82-120">Garbage Collection im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="72e82-120">Background GC</span></span>](#background-gc)

### <a name="workstation-vs-server"></a><span data-ttu-id="72e82-121">Arbeitsstationen und Server im Vergleich</span><span class="sxs-lookup"><span data-stu-id="72e82-121">Workstation vs. server</span></span>

- <span data-ttu-id="72e82-122">Konfiguriert, ob die Anwendung die Arbeitsstation-GC oder die Server-GC verwendet</span><span class="sxs-lookup"><span data-stu-id="72e82-122">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="72e82-123">Standard: Arbeitsstation-Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="72e82-123">Default: Workstation garbage collection.</span></span> <span data-ttu-id="72e82-124">Dies entspricht der Einstellung des Werts auf `false`.</span><span class="sxs-lookup"><span data-stu-id="72e82-124">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="72e82-125">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72e82-125">Setting name</span></span> | <span data-ttu-id="72e82-126">Werte</span><span class="sxs-lookup"><span data-stu-id="72e82-126">Values</span></span> | <span data-ttu-id="72e82-127">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="72e82-127">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="72e82-128">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72e82-128">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="72e82-129">`false` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="72e82-129">`false` - workstation</span></span><br/><span data-ttu-id="72e82-130">`true` – Server</span><span class="sxs-lookup"><span data-stu-id="72e82-130">`true` - server</span></span> | <span data-ttu-id="72e82-131">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="72e82-131">.NET Core 1.0</span></span> |
| <span data-ttu-id="72e82-132">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="72e82-132">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="72e82-133">`false` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="72e82-133">`false` - workstation</span></span><br/><span data-ttu-id="72e82-134">`true` – Server</span><span class="sxs-lookup"><span data-stu-id="72e82-134">`true` - server</span></span> | <span data-ttu-id="72e82-135">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="72e82-135">.NET Core 1.0</span></span> |
| <span data-ttu-id="72e82-136">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72e82-136">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="72e82-137">`0` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="72e82-137">`0` - workstation</span></span><br/><span data-ttu-id="72e82-138">`1` – Server</span><span class="sxs-lookup"><span data-stu-id="72e82-138">`1` - server</span></span> | <span data-ttu-id="72e82-139">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="72e82-139">.NET Core 1.0</span></span> |
| <span data-ttu-id="72e82-140">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="72e82-140">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="72e82-141">GCServer</span><span class="sxs-lookup"><span data-stu-id="72e82-141">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="72e82-142">`false` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="72e82-142">`false` - workstation</span></span><br/><span data-ttu-id="72e82-143">`true` – Server</span><span class="sxs-lookup"><span data-stu-id="72e82-143">`true` - server</span></span> |  |

#### <a name="examples"></a><span data-ttu-id="72e82-144">Beispiele</span><span class="sxs-lookup"><span data-stu-id="72e82-144">Examples</span></span>

<span data-ttu-id="72e82-145">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="72e82-145">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="72e82-146">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="72e82-146">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="background-gc"></a><span data-ttu-id="72e82-147">Garbage Collection im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="72e82-147">Background GC</span></span>

- <span data-ttu-id="72e82-148">Konfiguriert, ob die (gleichzeitige) Hintergrund-GC aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="72e82-148">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="72e82-149">Standard: Garbage Collection im Hintergrund verwenden.</span><span class="sxs-lookup"><span data-stu-id="72e82-149">Default: Use background GC.</span></span> <span data-ttu-id="72e82-150">Dies entspricht der Einstellung des Werts auf `true`.</span><span class="sxs-lookup"><span data-stu-id="72e82-150">This is equivalent to setting the value to `true`.</span></span>
- <span data-ttu-id="72e82-151">Weitere Informationen finden Sie unter [Hintergrund der Garbage Collection](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="72e82-151">For more information, see [Background garbage collection](../../standard/garbage-collection/background-gc.md).</span></span>

| | <span data-ttu-id="72e82-152">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72e82-152">Setting name</span></span> | <span data-ttu-id="72e82-153">Werte</span><span class="sxs-lookup"><span data-stu-id="72e82-153">Values</span></span> | <span data-ttu-id="72e82-154">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="72e82-154">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="72e82-155">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72e82-155">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="72e82-156">`true` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="72e82-156">`true` - background GC</span></span><br/><span data-ttu-id="72e82-157">`false` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="72e82-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="72e82-158">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="72e82-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="72e82-159">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="72e82-159">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="72e82-160">`true` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="72e82-160">`true` - background GC</span></span><br/><span data-ttu-id="72e82-161">`false` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="72e82-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="72e82-162">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="72e82-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="72e82-163">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72e82-163">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="72e82-164">`1` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="72e82-164">`1` - background GC</span></span><br/><span data-ttu-id="72e82-165">`0` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="72e82-165">`0` - non-concurrent GC</span></span> | <span data-ttu-id="72e82-166">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="72e82-166">.NET Core 1.0</span></span> |
| <span data-ttu-id="72e82-167">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="72e82-167">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="72e82-168">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="72e82-168">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="72e82-169">`true` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="72e82-169">`true` - background GC</span></span><br/><span data-ttu-id="72e82-170">`false` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="72e82-170">`false` - non-concurrent GC</span></span> |  |

#### <a name="examples"></a><span data-ttu-id="72e82-171">Beispiele</span><span class="sxs-lookup"><span data-stu-id="72e82-171">Examples</span></span>

<span data-ttu-id="72e82-172">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="72e82-172">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="72e82-173">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="72e82-173">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="72e82-174">Verwalten des Ressourceneinsatzes</span><span class="sxs-lookup"><span data-stu-id="72e82-174">Manage resource usage</span></span>

<span data-ttu-id="72e82-175">Verwenden Sie die folgenden Einstellungen, um die Speicher- und Prozessorauslastung des Garbage Collectors zu verwalten:</span><span class="sxs-lookup"><span data-stu-id="72e82-175">Use the following settings to manage the garbage collector's memory and processor usage:</span></span>

- [<span data-ttu-id="72e82-176">Zuordnen</span><span class="sxs-lookup"><span data-stu-id="72e82-176">Affinitize</span></span>](#affinitize)
- [<span data-ttu-id="72e82-177">Maske zuordnen</span><span class="sxs-lookup"><span data-stu-id="72e82-177">Affinitize mask</span></span>](#affinitize-mask)
- [<span data-ttu-id="72e82-178">Bereiche zuordnen</span><span class="sxs-lookup"><span data-stu-id="72e82-178">Affinitize ranges</span></span>](#affinitize-ranges)
- [<span data-ttu-id="72e82-179">CPU-Gruppen</span><span class="sxs-lookup"><span data-stu-id="72e82-179">CPU groups</span></span>](#cpu-groups)
- [<span data-ttu-id="72e82-180">Heapanzahl</span><span class="sxs-lookup"><span data-stu-id="72e82-180">Heap count</span></span>](#heap-count)
- [<span data-ttu-id="72e82-181">Heapgrenzwert</span><span class="sxs-lookup"><span data-stu-id="72e82-181">Heap limit</span></span>](#heap-limit)
- [<span data-ttu-id="72e82-182">Heapgrenzwert (Prozent)</span><span class="sxs-lookup"><span data-stu-id="72e82-182">Heap limit percent</span></span>](#heap-limit-percent)
- [<span data-ttu-id="72e82-183">Hohe Speicherauslastung (Prozent)</span><span class="sxs-lookup"><span data-stu-id="72e82-183">High memory percent</span></span>](#high-memory-percent)
- [<span data-ttu-id="72e82-184">Grenzwerte pro Objektheap</span><span class="sxs-lookup"><span data-stu-id="72e82-184">Per-object-heap limits</span></span>](#per-object-heap-limits)
- [<span data-ttu-id="72e82-185">Grenzwerte pro Objektheap (Prozent)</span><span class="sxs-lookup"><span data-stu-id="72e82-185">Per-object-heap limit percents</span></span>](#per-object-heap-limit-percents)
- [<span data-ttu-id="72e82-186">VM beibehalten</span><span class="sxs-lookup"><span data-stu-id="72e82-186">Retain VM</span></span>](#retain-vm)

<span data-ttu-id="72e82-187">Weitere Informationen zu einigen dieser Einstellungen finden Sie im Blogeintrag [Mittelweg zwischen Arbeitsstation- und Server-GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).</span><span class="sxs-lookup"><span data-stu-id="72e82-187">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="heap-count"></a><span data-ttu-id="72e82-188">Heapanzahl</span><span class="sxs-lookup"><span data-stu-id="72e82-188">Heap count</span></span>

- <span data-ttu-id="72e82-189">Schränkt die Anzahl von Heaps ein, die vom Garbage Collector erstellt werden</span><span class="sxs-lookup"><span data-stu-id="72e82-189">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="72e82-190">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="72e82-190">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="72e82-191">Wenn die [GC-Prozessoraffinität](#affinitize) aktiviert ist (Standardeinstellung), ordnet die Einstellung für die Heapanzahl den ersten `n` Prozessoren `n` GC-Heaps/-Threads zu.</span><span class="sxs-lookup"><span data-stu-id="72e82-191">If [GC processor affinity](#affinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="72e82-192">(Verwenden Sie die Einstellungen [AffinitizeMask](#affinitize-mask) oder [AffinitizeRanges](#affinitize-ranges), um genau anzugeben, welche Prozessoren zugeordnet werden sollen.)</span><span class="sxs-lookup"><span data-stu-id="72e82-192">(Use the [affinitize mask](#affinitize-mask) or [affinitize ranges](#affinitize-ranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="72e82-193">Wenn die [GC-Prozessoraffinität](#affinitize) deaktiviert ist, wird mit dieser Einstellung die Anzahl der GC-Heaps eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="72e82-193">If [GC processor affinity](#affinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="72e82-194">Weitere Informationen finden Sie unter [Hinweise zu GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="72e82-194">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="72e82-195">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72e82-195">Setting name</span></span> | <span data-ttu-id="72e82-196">Werte</span><span class="sxs-lookup"><span data-stu-id="72e82-196">Values</span></span> | <span data-ttu-id="72e82-197">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="72e82-197">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="72e82-198">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72e82-198">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="72e82-199">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-199">*decimal value*</span></span> | <span data-ttu-id="72e82-200">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="72e82-200">.NET Core 3.0</span></span> |
| <span data-ttu-id="72e82-201">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72e82-201">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="72e82-202">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-202">*hexadecimal value*</span></span> | <span data-ttu-id="72e82-203">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="72e82-203">.NET Core 3.0</span></span> |
| <span data-ttu-id="72e82-204">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="72e82-204">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="72e82-205">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="72e82-205">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="72e82-206">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-206">*decimal value*</span></span> | <span data-ttu-id="72e82-207">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="72e82-207">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="72e82-208">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="72e82-208">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapCount": 16
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="72e82-209">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="72e82-209">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="72e82-210">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="72e82-210">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="72e82-211">Für eine Einschränkung der Heapanzahl auf 16 wären die Werte beispielsweise 16 für die JSON-Datei und 0x10 oder 10 für die Umgebungsvariable.</span><span class="sxs-lookup"><span data-stu-id="72e82-211">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="affinitize-mask"></a><span data-ttu-id="72e82-212">Maske zuordnen</span><span class="sxs-lookup"><span data-stu-id="72e82-212">Affinitize mask</span></span>

- <span data-ttu-id="72e82-213">Gibt die genauen Prozessoren an, die Garbage-Collector-Threads verwenden sollen</span><span class="sxs-lookup"><span data-stu-id="72e82-213">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="72e82-214">Wenn die [GC-Prozessoraffinität](#affinitize) deaktiviert ist, wird diese Einstellung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="72e82-214">If [GC processor affinity](#affinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="72e82-215">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="72e82-215">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="72e82-216">Der Wert ist eine Bitmaske, die die für den Prozess verfügbaren Prozessoren definiert.</span><span class="sxs-lookup"><span data-stu-id="72e82-216">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="72e82-217">Beispielsweise ist ein Dezimalwert von 1023 (oder ein Hexadezimalwert von 0x3FF oder 3FF bei Verwendung der Umgebungsvariablen) in Binärschreibweise 0011 1111 1111.</span><span class="sxs-lookup"><span data-stu-id="72e82-217">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="72e82-218">Dies gibt an, dass die ersten zehn Prozessoren verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="72e82-218">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="72e82-219">Geben Sie einen Dezimalwert von 1047552 (oder einen Hexadezimalwert von 0xFFC00 oder FFC00) an, der einem Binärwert von 1111 1111 1100 0000 0000 entspricht, um die nächsten zehn Prozessoren anzugeben, d. h. die Prozessoren 10 bis 19.</span><span class="sxs-lookup"><span data-stu-id="72e82-219">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="72e82-220">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72e82-220">Setting name</span></span> | <span data-ttu-id="72e82-221">Werte</span><span class="sxs-lookup"><span data-stu-id="72e82-221">Values</span></span> | <span data-ttu-id="72e82-222">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="72e82-222">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="72e82-223">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72e82-223">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="72e82-224">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-224">*decimal value*</span></span> | <span data-ttu-id="72e82-225">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="72e82-225">.NET Core 3.0</span></span> |
| <span data-ttu-id="72e82-226">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72e82-226">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="72e82-227">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-227">*hexadecimal value*</span></span> | <span data-ttu-id="72e82-228">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="72e82-228">.NET Core 3.0</span></span> |
| <span data-ttu-id="72e82-229">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="72e82-229">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="72e82-230">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="72e82-230">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="72e82-231">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-231">*decimal value*</span></span> | <span data-ttu-id="72e82-232">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="72e82-232">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="72e82-233">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="72e82-233">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="affinitize-ranges"></a><span data-ttu-id="72e82-234">Bereiche zuordnen</span><span class="sxs-lookup"><span data-stu-id="72e82-234">Affinitize ranges</span></span>

- <span data-ttu-id="72e82-235">Gibt die Liste der Prozessoren an, die für Garbage-Collector-Threads verwendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="72e82-235">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="72e82-236">Diese Einstellung ähnelt [System.GC.HeapAffinitizeMask](#affinitize-mask), abgesehen davon, dass Sie mehr als 64 Prozessoren angeben können.</span><span class="sxs-lookup"><span data-stu-id="72e82-236">This setting is similar to [System.GC.HeapAffinitizeMask](#affinitize-mask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="72e82-237">Stellen Sie für Windows-Betriebssysteme der Prozessornummer oder dem Prozessorbereich die entsprechende [CPU-Gruppe](/windows/win32/procthread/processor-groups) voran, z. B. „0:1-10,0:12,1:50-52,1:70“.</span><span class="sxs-lookup"><span data-stu-id="72e82-237">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="72e82-238">Wenn die [GC-Prozessoraffinität](#affinitize) deaktiviert ist, wird diese Einstellung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="72e82-238">If [GC processor affinity](#affinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="72e82-239">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="72e82-239">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="72e82-240">Weitere Informationen finden Sie unter [Optimieren der CPU-Konfiguration für GC auf Computern mit mehr als 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) im Blog von Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="72e82-240">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="72e82-241">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72e82-241">Setting name</span></span> | <span data-ttu-id="72e82-242">Werte</span><span class="sxs-lookup"><span data-stu-id="72e82-242">Values</span></span> | <span data-ttu-id="72e82-243">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="72e82-243">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="72e82-244">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72e82-244">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="72e82-245">Durch Kommas getrennte Liste mit Prozessornummern oder Bereichen von Prozessornummern</span><span class="sxs-lookup"><span data-stu-id="72e82-245">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="72e82-246">Unix-Beispiel: „1-10,12,50-52,70“</span><span class="sxs-lookup"><span data-stu-id="72e82-246">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="72e82-247">Windows-Beispiel: „0:1-10,0:12,1:50-52,1:70“</span><span class="sxs-lookup"><span data-stu-id="72e82-247">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="72e82-248">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="72e82-248">.NET Core 3.0</span></span> |
| <span data-ttu-id="72e82-249">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72e82-249">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="72e82-250">Durch Kommas getrennte Liste mit Prozessornummern oder Bereichen von Prozessornummern</span><span class="sxs-lookup"><span data-stu-id="72e82-250">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="72e82-251">Unix-Beispiel: „1-10,12,50-52,70“</span><span class="sxs-lookup"><span data-stu-id="72e82-251">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="72e82-252">Windows-Beispiel: „0:1-10,0:12,1:50-52,1:70“</span><span class="sxs-lookup"><span data-stu-id="72e82-252">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="72e82-253">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="72e82-253">.NET Core 3.0</span></span> |

<span data-ttu-id="72e82-254">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="72e82-254">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="cpu-groups"></a><span data-ttu-id="72e82-255">CPU-Gruppen</span><span class="sxs-lookup"><span data-stu-id="72e82-255">CPU groups</span></span>

- <span data-ttu-id="72e82-256">Konfiguriert, ob der Garbage Collector [CPU-Gruppen](/windows/win32/procthread/processor-groups) verwendet</span><span class="sxs-lookup"><span data-stu-id="72e82-256">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="72e82-257">Wenn ein 64-Bit-Windows-Computer über mehrere CPU-Gruppen verfügt, d. h. mehr als 64 Prozessoren vorhanden sind, dann wird durch die Aktivierung dieses Elements die Garbage Collection in allen CPU-Gruppen erweitert.</span><span class="sxs-lookup"><span data-stu-id="72e82-257">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="72e82-258">Der Garbage Collector verwendet alle Kerne zum Erstellen und Ausgleichen von Heaps.</span><span class="sxs-lookup"><span data-stu-id="72e82-258">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="72e82-259">Gilt nur für Garbage Collection des Servers auf 64-Bit-Windows-Betriebssystemen.</span><span class="sxs-lookup"><span data-stu-id="72e82-259">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="72e82-260">Standard: GC wird nicht über CPU-Gruppen hinweg erweitert.</span><span class="sxs-lookup"><span data-stu-id="72e82-260">Default: GC does not extend across CPU groups.</span></span> <span data-ttu-id="72e82-261">Dies entspricht der Einstellung des Werts auf `0`.</span><span class="sxs-lookup"><span data-stu-id="72e82-261">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="72e82-262">Weitere Informationen finden Sie unter [Optimieren der CPU-Konfiguration für GC auf Computern mit mehr als 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) im Blog von Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="72e82-262">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="72e82-263">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72e82-263">Setting name</span></span> | <span data-ttu-id="72e82-264">Werte</span><span class="sxs-lookup"><span data-stu-id="72e82-264">Values</span></span> | <span data-ttu-id="72e82-265">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="72e82-265">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="72e82-266">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72e82-266">**runtimeconfig.json**</span></span> | `System.GC.CpuGroup` | <span data-ttu-id="72e82-267">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="72e82-267">`0` - disabled</span></span><br/><span data-ttu-id="72e82-268">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="72e82-268">`1` - enabled</span></span> | <span data-ttu-id="72e82-269">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="72e82-269">.NET 5.0</span></span> |
| <span data-ttu-id="72e82-270">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72e82-270">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="72e82-271">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="72e82-271">`0` - disabled</span></span><br/><span data-ttu-id="72e82-272">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="72e82-272">`1` - enabled</span></span> | <span data-ttu-id="72e82-273">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="72e82-273">.NET Core 1.0</span></span> |
| <span data-ttu-id="72e82-274">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="72e82-274">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="72e82-275">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="72e82-275">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="72e82-276">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="72e82-276">`false` - disabled</span></span><br/><span data-ttu-id="72e82-277">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="72e82-277">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="72e82-278">Aktivieren Sie die Option [Thread_UseAllCpuGroups-Element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md), um die Common Language Runtime (CLR) so zu konfigurieren, dass auch Threads aus dem Threadpool in allen CPU-Gruppen verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="72e82-278">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="72e82-279">Für .NET Core-Apps können Sie diese Option aktivieren, indem Sie den Wert der Umgebungsvariablen `COMPlus_Thread_UseAllCpuGroups` auf `1` setzen.</span><span class="sxs-lookup"><span data-stu-id="72e82-279">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="affinitize"></a><span data-ttu-id="72e82-280">Zuordnen</span><span class="sxs-lookup"><span data-stu-id="72e82-280">Affinitize</span></span>

- <span data-ttu-id="72e82-281">Gibt an, ob Garbage-Collection-Threads Prozessoren *zugeordnet* werden sollen.</span><span class="sxs-lookup"><span data-stu-id="72e82-281">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="72e82-282">Einen GC-Thread zuzuordnen, bedeutet, dass dieser nur auf der jeweiligen CPU ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="72e82-282">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="72e82-283">Für jeden GC-Thread wird ein Heap erstellt.</span><span class="sxs-lookup"><span data-stu-id="72e82-283">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="72e82-284">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="72e82-284">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="72e82-285">Standard: Garbage Collection-Threads werden Prozessoren zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="72e82-285">Default: Affinitize garbage collection threads with processors.</span></span> <span data-ttu-id="72e82-286">Dies entspricht der Einstellung des Werts auf `false`.</span><span class="sxs-lookup"><span data-stu-id="72e82-286">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="72e82-287">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72e82-287">Setting name</span></span> | <span data-ttu-id="72e82-288">Werte</span><span class="sxs-lookup"><span data-stu-id="72e82-288">Values</span></span> | <span data-ttu-id="72e82-289">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="72e82-289">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="72e82-290">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72e82-290">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="72e82-291">`false` – zuordnen</span><span class="sxs-lookup"><span data-stu-id="72e82-291">`false` - affinitize</span></span><br/><span data-ttu-id="72e82-292">`true` – nicht zuordnen</span><span class="sxs-lookup"><span data-stu-id="72e82-292">`true` - don't affinitize</span></span> | <span data-ttu-id="72e82-293">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="72e82-293">.NET Core 3.0</span></span> |
| <span data-ttu-id="72e82-294">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72e82-294">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="72e82-295">`0` – zuordnen</span><span class="sxs-lookup"><span data-stu-id="72e82-295">`0` - affinitize</span></span><br/><span data-ttu-id="72e82-296">`1` – nicht zuordnen</span><span class="sxs-lookup"><span data-stu-id="72e82-296">`1` - don't affinitize</span></span> | <span data-ttu-id="72e82-297">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="72e82-297">.NET Core 3.0</span></span> |
| <span data-ttu-id="72e82-298">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="72e82-298">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="72e82-299">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="72e82-299">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="72e82-300">`false` – zuordnen</span><span class="sxs-lookup"><span data-stu-id="72e82-300">`false` - affinitize</span></span><br/><span data-ttu-id="72e82-301">`true` – nicht zuordnen</span><span class="sxs-lookup"><span data-stu-id="72e82-301">`true` - don't affinitize</span></span> | <span data-ttu-id="72e82-302">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="72e82-302">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="72e82-303">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="72e82-303">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="heap-limit"></a><span data-ttu-id="72e82-304">Heapgrenzwert</span><span class="sxs-lookup"><span data-stu-id="72e82-304">Heap limit</span></span>

- <span data-ttu-id="72e82-305">Gibt die maximale Commitgröße in Bytes für den GC-Heap und die GC-Buchhaltung an</span><span class="sxs-lookup"><span data-stu-id="72e82-305">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="72e82-306">Diese Einstellung gilt nur für 64-Bit-Computer.</span><span class="sxs-lookup"><span data-stu-id="72e82-306">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="72e82-307">Diese Einstellung wird ignoriert, wenn die [Grenzwerte pro Objektheap](#per-object-heap-limits) konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="72e82-307">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="72e82-308">Der Standardwert, der nur in bestimmten Fällen gilt, ist der größere Wert von 20 MB oder 75 % der Speichergrenze für den Container.</span><span class="sxs-lookup"><span data-stu-id="72e82-308">The default value, which only applies in certain cases, is the greater of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="72e82-309">Der Standardwert wird in folgenden Fällen angewendet:</span><span class="sxs-lookup"><span data-stu-id="72e82-309">The default value applies if:</span></span>

  - <span data-ttu-id="72e82-310">Der Prozess wird in einem Container ausgeführt, für den ein Arbeitsspeicherlimit angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="72e82-310">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="72e82-311">[System.GC.HeapHardLimitPercent](#heap-limit-percent) ist nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="72e82-311">[System.GC.HeapHardLimitPercent](#heap-limit-percent) is not set.</span></span>

| | <span data-ttu-id="72e82-312">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72e82-312">Setting name</span></span> | <span data-ttu-id="72e82-313">Werte</span><span class="sxs-lookup"><span data-stu-id="72e82-313">Values</span></span> | <span data-ttu-id="72e82-314">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="72e82-314">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="72e82-315">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72e82-315">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="72e82-316">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-316">*decimal value*</span></span> | <span data-ttu-id="72e82-317">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="72e82-317">.NET Core 3.0</span></span> |
| <span data-ttu-id="72e82-318">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72e82-318">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="72e82-319">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-319">*hexadecimal value*</span></span> | <span data-ttu-id="72e82-320">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="72e82-320">.NET Core 3.0</span></span> |

<span data-ttu-id="72e82-321">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="72e82-321">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimit": 209715200
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="72e82-322">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="72e82-322">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="72e82-323">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="72e82-323">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="72e82-324">Wenn Sie beispielsweise eine feste Heapgrenze von 200 MiB festlegen, würden die Werte für die JSON-Datei 209715200 und für die Umgebungsvariable 0xc800000 oder C800000 betragen.</span><span class="sxs-lookup"><span data-stu-id="72e82-324">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="heap-limit-percent"></a><span data-ttu-id="72e82-325">Heapgrenzwert (Prozent)</span><span class="sxs-lookup"><span data-stu-id="72e82-325">Heap limit percent</span></span>

- <span data-ttu-id="72e82-326">Gibt den zulässigen GC-Heapverbrauch in Prozent des gesamten physischen Speichers an.</span><span class="sxs-lookup"><span data-stu-id="72e82-326">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="72e82-327">Wenn außerdem [System.GC.HeapHardLimit](#heap-limit) festgelegt ist, wird diese Einstellung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="72e82-327">If [System.GC.HeapHardLimit](#heap-limit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="72e82-328">Diese Einstellung gilt nur für 64-Bit-Computer.</span><span class="sxs-lookup"><span data-stu-id="72e82-328">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="72e82-329">Wenn der Prozess in einem Container ausgeführt, für den ein Arbeitsspeicherlimit angegeben wurde, wird der Prozentsatz als Prozentsatz dieses Arbeitsspeicherlimits berechnet.</span><span class="sxs-lookup"><span data-stu-id="72e82-329">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="72e82-330">Diese Einstellung wird ignoriert, wenn die [Grenzwerte pro Objektheap](#per-object-heap-limits) konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="72e82-330">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="72e82-331">Der Standardwert, der nur in bestimmten Fällen angewendet wird, beträgt weniger als 20 MB oder 75 % des Arbeitsspeicherlimits für den Container.</span><span class="sxs-lookup"><span data-stu-id="72e82-331">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="72e82-332">Der Standardwert wird in folgenden Fällen angewendet:</span><span class="sxs-lookup"><span data-stu-id="72e82-332">The default value applies if:</span></span>

  - <span data-ttu-id="72e82-333">Der Prozess wird in einem Container ausgeführt, für den ein Arbeitsspeicherlimit angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="72e82-333">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="72e82-334">[System.GC.HeapHardLimit](#heap-limit) ist nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="72e82-334">[System.GC.HeapHardLimit](#heap-limit) is not set.</span></span>

| | <span data-ttu-id="72e82-335">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72e82-335">Setting name</span></span> | <span data-ttu-id="72e82-336">Werte</span><span class="sxs-lookup"><span data-stu-id="72e82-336">Values</span></span> | <span data-ttu-id="72e82-337">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="72e82-337">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="72e82-338">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72e82-338">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="72e82-339">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-339">*decimal value*</span></span> | <span data-ttu-id="72e82-340">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="72e82-340">.NET Core 3.0</span></span> |
| <span data-ttu-id="72e82-341">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72e82-341">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="72e82-342">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-342">*hexadecimal value*</span></span> | <span data-ttu-id="72e82-343">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="72e82-343">.NET Core 3.0</span></span> |

<span data-ttu-id="72e82-344">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="72e82-344">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimitPercent": 30
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="72e82-345">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="72e82-345">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="72e82-346">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="72e82-346">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="72e82-347">Beispielsweise würden bei einer Begrenzung des Heapverbrauchs auf 30 % die Werte für die JSON-Datei 30 und für die Umgebungsvariable 0x1E oder 1E betragen.</span><span class="sxs-lookup"><span data-stu-id="72e82-347">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="per-object-heap-limits"></a><span data-ttu-id="72e82-348">Grenzwerte pro Objektheap</span><span class="sxs-lookup"><span data-stu-id="72e82-348">Per-object-heap limits</span></span>

<span data-ttu-id="72e82-349">Sie können die zulässige Heapnutzung bei der Garbage Collection pro Objektheap angeben.</span><span class="sxs-lookup"><span data-stu-id="72e82-349">You can specify the GC's allowable heap usage on a per-object-heap basis.</span></span> <span data-ttu-id="72e82-350">Die verschiedenen Arten von Heaps sind: große Objektheaps (Large Object Heap, LOH), kleine Objektheaps (Small Object Heap, SOH) und fixierte Objektheaps (Pinned Object Heap, POH).</span><span class="sxs-lookup"><span data-stu-id="72e82-350">The different heaps are the large object heap (LOH), small object heap (SOH), and pinned object heap (POH).</span></span>

- <span data-ttu-id="72e82-351">Wenn Sie für eine der Einstellungen `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH` oder `COMPLUS_GCHeapHardLimitPOH` einen Wert angeben, müssen Sie auch einen Wert für `COMPLUS_GCHeapHardLimitSOH` und `COMPLUS_GCHeapHardLimitLOH` angeben.</span><span class="sxs-lookup"><span data-stu-id="72e82-351">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, or `COMPLUS_GCHeapHardLimitPOH` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH`.</span></span> <span data-ttu-id="72e82-352">Andernfalls kann die Laufzeit nicht initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="72e82-352">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="72e82-353">Der Standardwert für `COMPLUS_GCHeapHardLimitPOH` ist 0.</span><span class="sxs-lookup"><span data-stu-id="72e82-353">The default value for `COMPLUS_GCHeapHardLimitPOH` is 0.</span></span> <span data-ttu-id="72e82-354">`COMPLUS_GCHeapHardLimitSOH` und `COMPLUS_GCHeapHardLimitLOH` verfügen über keine Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="72e82-354">`COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH` don't have default values.</span></span>

| | <span data-ttu-id="72e82-355">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72e82-355">Setting name</span></span> | <span data-ttu-id="72e82-356">Werte</span><span class="sxs-lookup"><span data-stu-id="72e82-356">Values</span></span> | <span data-ttu-id="72e82-357">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="72e82-357">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="72e82-358">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72e82-358">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitSOH` | <span data-ttu-id="72e82-359">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-359">*decimal value*</span></span> | <span data-ttu-id="72e82-360">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="72e82-360">.NET 5.0</span></span> |
| <span data-ttu-id="72e82-361">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72e82-361">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOH` | <span data-ttu-id="72e82-362">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-362">*hexadecimal value*</span></span> | <span data-ttu-id="72e82-363">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="72e82-363">.NET 5.0</span></span> |

| | <span data-ttu-id="72e82-364">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72e82-364">Setting name</span></span> | <span data-ttu-id="72e82-365">Werte</span><span class="sxs-lookup"><span data-stu-id="72e82-365">Values</span></span> | <span data-ttu-id="72e82-366">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="72e82-366">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="72e82-367">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72e82-367">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitLOH` | <span data-ttu-id="72e82-368">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-368">*decimal value*</span></span> | <span data-ttu-id="72e82-369">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="72e82-369">.NET 5.0</span></span> |
| <span data-ttu-id="72e82-370">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72e82-370">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOH` | <span data-ttu-id="72e82-371">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-371">*hexadecimal value*</span></span> | <span data-ttu-id="72e82-372">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="72e82-372">.NET 5.0</span></span> |

| | <span data-ttu-id="72e82-373">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72e82-373">Setting name</span></span> | <span data-ttu-id="72e82-374">Werte</span><span class="sxs-lookup"><span data-stu-id="72e82-374">Values</span></span> | <span data-ttu-id="72e82-375">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="72e82-375">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="72e82-376">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72e82-376">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPOH` | <span data-ttu-id="72e82-377">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-377">*decimal value*</span></span> | <span data-ttu-id="72e82-378">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="72e82-378">.NET 5.0</span></span> |
| <span data-ttu-id="72e82-379">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72e82-379">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOH` | <span data-ttu-id="72e82-380">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-380">*hexadecimal value*</span></span> | <span data-ttu-id="72e82-381">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="72e82-381">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="72e82-382">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="72e82-382">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="72e82-383">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="72e82-383">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="72e82-384">Wenn Sie beispielsweise eine feste Heapgrenze von 200 MiB festlegen, würden die Werte für die JSON-Datei 209715200 und für die Umgebungsvariable 0xc800000 oder C800000 betragen.</span><span class="sxs-lookup"><span data-stu-id="72e82-384">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="per-object-heap-limit-percents"></a><span data-ttu-id="72e82-385">Grenzwerte pro Objektheap (Prozent)</span><span class="sxs-lookup"><span data-stu-id="72e82-385">Per-object-heap limit percents</span></span>

<span data-ttu-id="72e82-386">Sie können die zulässige Heapnutzung bei der Garbage Collection pro Objektheap angeben.</span><span class="sxs-lookup"><span data-stu-id="72e82-386">You can specify the GC's allowable heap usage on a per-object-heap basis.</span></span> <span data-ttu-id="72e82-387">Die verschiedenen Arten von Heaps sind: große Objektheaps (Large Object Heap, LOH), kleine Objektheaps (Small Object Heap, SOH) und fixierte Objektheaps (Pinned Object Heap, POH).</span><span class="sxs-lookup"><span data-stu-id="72e82-387">The different heaps are the large object heap (LOH), small object heap (SOH), and pinned object heap (POH).</span></span>

- <span data-ttu-id="72e82-388">Wenn Sie für eine der Einstellungen `COMPLUS_GCHeapHardLimitSOHPercent`, `COMPLUS_GCHeapHardLimitLOHPercent` oder `COMPLUS_GCHeapHardLimitPOHPercent` einen Wert angeben, müssen Sie auch einen Wert für `COMPLUS_GCHeapHardLimitSOHPercent` und `COMPLUS_GCHeapHardLimitLOHPercent` angeben.</span><span class="sxs-lookup"><span data-stu-id="72e82-388">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOHPercent`, `COMPLUS_GCHeapHardLimitLOHPercent`, or `COMPLUS_GCHeapHardLimitPOHPercent` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOHPercent` and `COMPLUS_GCHeapHardLimitLOHPercent`.</span></span> <span data-ttu-id="72e82-389">Andernfalls kann die Laufzeit nicht initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="72e82-389">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="72e82-390">Diese Einstellungen werden ignoriert, wenn `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH` und `COMPLUS_GCHeapHardLimitPOH` angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="72e82-390">These settings are ignored if `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, and `COMPLUS_GCHeapHardLimitPOH` are specified.</span></span>
- <span data-ttu-id="72e82-391">Der Wert 1 bedeutet, dass die Garbage Collection 1 % des gesamten physischen Speichers für diesen Objektheap verwendet.</span><span class="sxs-lookup"><span data-stu-id="72e82-391">A value of 1 means that GC uses 1% of total physical memory for that object heap.</span></span>
- <span data-ttu-id="72e82-392">Jeder Wert muss größer als 0 (null) und kleiner als 100 sein.</span><span class="sxs-lookup"><span data-stu-id="72e82-392">Each value must be greater than zero and less than 100.</span></span> <span data-ttu-id="72e82-393">Außerdem muss die Summe der drei Prozentwerte kleiner als 100 sein.</span><span class="sxs-lookup"><span data-stu-id="72e82-393">Additionally, the sum of the three percentage values must be less than 100.</span></span> <span data-ttu-id="72e82-394">Andernfalls tritt ein Fehler bei der Initialisierung der Laufzeit auf.</span><span class="sxs-lookup"><span data-stu-id="72e82-394">Otherwise, the runtime will fail to initialize.</span></span>

| | <span data-ttu-id="72e82-395">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72e82-395">Setting name</span></span> | <span data-ttu-id="72e82-396">Werte</span><span class="sxs-lookup"><span data-stu-id="72e82-396">Values</span></span> | <span data-ttu-id="72e82-397">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="72e82-397">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="72e82-398">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72e82-398">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitSOHPercent` | <span data-ttu-id="72e82-399">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-399">*decimal value*</span></span> | <span data-ttu-id="72e82-400">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="72e82-400">.NET 5.0</span></span> |
| <span data-ttu-id="72e82-401">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72e82-401">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOHPercent` | <span data-ttu-id="72e82-402">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-402">*hexadecimal value*</span></span> | <span data-ttu-id="72e82-403">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="72e82-403">.NET 5.0</span></span> |

| | <span data-ttu-id="72e82-404">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72e82-404">Setting name</span></span> | <span data-ttu-id="72e82-405">Werte</span><span class="sxs-lookup"><span data-stu-id="72e82-405">Values</span></span> | <span data-ttu-id="72e82-406">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="72e82-406">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="72e82-407">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72e82-407">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitLOHPercent` | <span data-ttu-id="72e82-408">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-408">*decimal value*</span></span> | <span data-ttu-id="72e82-409">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="72e82-409">.NET 5.0</span></span> |
| <span data-ttu-id="72e82-410">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72e82-410">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOHPercent` | <span data-ttu-id="72e82-411">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-411">*hexadecimal value*</span></span> | <span data-ttu-id="72e82-412">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="72e82-412">.NET 5.0</span></span> |

| | <span data-ttu-id="72e82-413">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72e82-413">Setting name</span></span> | <span data-ttu-id="72e82-414">Werte</span><span class="sxs-lookup"><span data-stu-id="72e82-414">Values</span></span> | <span data-ttu-id="72e82-415">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="72e82-415">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="72e82-416">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72e82-416">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPOHPercent` | <span data-ttu-id="72e82-417">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-417">*decimal value*</span></span> | <span data-ttu-id="72e82-418">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="72e82-418">.NET 5.0</span></span> |
| <span data-ttu-id="72e82-419">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72e82-419">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOHPercent` | <span data-ttu-id="72e82-420">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-420">*hexadecimal value*</span></span> | <span data-ttu-id="72e82-421">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="72e82-421">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="72e82-422">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="72e82-422">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="72e82-423">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="72e82-423">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="72e82-424">Beispielsweise würden bei einer Begrenzung des Heapverbrauchs auf 30 % die Werte für die JSON-Datei 30 und für die Umgebungsvariable 0x1E oder 1E betragen.</span><span class="sxs-lookup"><span data-stu-id="72e82-424">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="high-memory-percent"></a><span data-ttu-id="72e82-425">Hohe Speicherauslastung (Prozent)</span><span class="sxs-lookup"><span data-stu-id="72e82-425">High memory percent</span></span>

<span data-ttu-id="72e82-426">Die Arbeitsspeicherauslastung wird durch den Prozentsatz des verwendeten physischen Speichers angegeben.</span><span class="sxs-lookup"><span data-stu-id="72e82-426">Memory load is indicated by the percentage of physical memory in use.</span></span> <span data-ttu-id="72e82-427">Wenn die physische Arbeitsspeicherauslastung **90 %** erreicht, wird die Garbage Collection standardmäßig aggressiver, um vollständige, komprimierende Garbage Collection-Vorgänge durchzuführen, um Auslagerungsvorgänge zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="72e82-427">By default, when the physical memory load reaches **90%**, garbage collection becomes more aggressive about doing full, compacting garbage collections to avoid paging.</span></span> <span data-ttu-id="72e82-428">Wenn die Arbeitsspeicherauslastung unter 90 % liegt, bevorzugt GC Hintergrundsammlungen für vollständige Garbage Collections, die kürzere Pausen aufweisen, aber die Gesamtheapgröße nicht wesentlich verringern.</span><span class="sxs-lookup"><span data-stu-id="72e82-428">When memory load is below 90%, GC favors background collections for full garbage collections, which have shorter pauses but don't reduce the total heap size by much.</span></span> <span data-ttu-id="72e82-429">Auf Computern mit einer beträchtlichen Menge an Arbeitsspeicher (80 GB oder mehr) liegt der Standardwert für die Auslastung zwischen 90 % und 97 %.</span><span class="sxs-lookup"><span data-stu-id="72e82-429">On machines with a significant amount of memory (80GB or more), the default load threshold is between 90% and 97%.</span></span>

<span data-ttu-id="72e82-430">Der Schwellenwert für hohe Arbeitsspeicherauslastung kann durch die Umgebungsvariable `COMPlus_GCHighMemPercent` oder die JSON-Konfigurationseinstellung `System.GC.HighMemoryPercent` angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="72e82-430">The high memory load threshold can be adjusted by the `COMPlus_GCHighMemPercent` environment variable or `System.GC.HighMemoryPercent` JSON configuration setting.</span></span> <span data-ttu-id="72e82-431">Wenn Sie die Heapgröße steuern möchten, sollten Sie den Schwellenwert anpassen.</span><span class="sxs-lookup"><span data-stu-id="72e82-431">Consider adjusting the threshold if you want to control heap size.</span></span> <span data-ttu-id="72e82-432">Beispielsweise ist es für den vorherrschenden Prozess auf einem Computer mit 64 GB Arbeitsspeicher sinnvoll, dass GC zu reagieren beginnt, wenn 10 % des Arbeitsspeichers verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="72e82-432">For example, for the dominant process on a machine with 64GB of memory, it's reasonable for GC to start reacting when there's 10% of memory available.</span></span> <span data-ttu-id="72e82-433">Für kleinere Prozesse (z. B. für einen Prozess, der nur 1 GB Arbeitsspeicher verbraucht) kann GC bequem mit weniger als 10 % des verfügbaren Speichers ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="72e82-433">But for smaller processes, for example, a process that only consumes 1GB of memory, GC can comfortably run with less than 10% of memory available.</span></span> <span data-ttu-id="72e82-434">Für diese kleineren Prozesse sollten Sie den Schwellenwert auf einen höheren Wert festlegen.</span><span class="sxs-lookup"><span data-stu-id="72e82-434">For these smaller processes, consider setting the threshold higher.</span></span> <span data-ttu-id="72e82-435">Wenn andererseits größere Prozesse kleinere Heapgrößen haben sollen (auch wenn genügend physischer Arbeitsspeicher verfügbar ist), ist die Herabsetzung dieses Schwellenwerts eine effektive Methode, mit der GC schneller reagieren kann, um den Heap zu komprimieren.</span><span class="sxs-lookup"><span data-stu-id="72e82-435">On the other hand, if you want larger processes to have smaller heap sizes (even when there's plenty of physical memory available), lowering this threshold is an effective way for GC to react sooner to compact the heap down.</span></span>

> [!NOTE]
> <span data-ttu-id="72e82-436">Bei Prozessen, die in einem Container ausgeführt werden, berücksichtigt GC den physischen Arbeitsspeicher basierend auf dem Containergrenzwert.</span><span class="sxs-lookup"><span data-stu-id="72e82-436">For processes running in a container, GC considers the physical memory based on the container limit.</span></span>

| | <span data-ttu-id="72e82-437">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72e82-437">Setting name</span></span> | <span data-ttu-id="72e82-438">Werte</span><span class="sxs-lookup"><span data-stu-id="72e82-438">Values</span></span> | <span data-ttu-id="72e82-439">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="72e82-439">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="72e82-440">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72e82-440">**runtimeconfig.json**</span></span> | `System.GC.HighMemoryPercent` | <span data-ttu-id="72e82-441">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-441">*decimal value*</span></span> | <span data-ttu-id="72e82-442">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="72e82-442">.NET 5.0</span></span> |
| <span data-ttu-id="72e82-443">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72e82-443">**Environment variable**</span></span> | `COMPlus_GCHighMemPercent` | <span data-ttu-id="72e82-444">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-444">*hexadecimal value*</span></span> | |

> [!TIP]
> <span data-ttu-id="72e82-445">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="72e82-445">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="72e82-446">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="72e82-446">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="72e82-447">Wenn Sie beispielsweise den Schwellenwert für hohe Arbeitsspeicherauslastung auf 75 % festlegen, würden die Werte für die JSON-Datei 75 und für die Umgebungsvariable 0x4B oder 4B betragen.</span><span class="sxs-lookup"><span data-stu-id="72e82-447">For example, to set the high memory threshold to 75%, the values would be 75 for the JSON file and 0x4B or 4B for the environment variable.</span></span>

### <a name="retain-vm"></a><span data-ttu-id="72e82-448">VM beibehalten</span><span class="sxs-lookup"><span data-stu-id="72e82-448">Retain VM</span></span>

- <span data-ttu-id="72e82-449">Konfiguriert, ob Segmente, die gelöscht werden sollen, zur späteren Verwendung auf eine Standbyliste aufgenommen oder an das Betriebssystem zurückgegeben werden</span><span class="sxs-lookup"><span data-stu-id="72e82-449">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="72e82-450">Standard: Segmente werden an das Betriebssystem zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="72e82-450">Default: Release segments back to the operating system.</span></span> <span data-ttu-id="72e82-451">Dies entspricht der Einstellung des Werts auf `false`.</span><span class="sxs-lookup"><span data-stu-id="72e82-451">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="72e82-452">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72e82-452">Setting name</span></span> | <span data-ttu-id="72e82-453">Werte</span><span class="sxs-lookup"><span data-stu-id="72e82-453">Values</span></span> | <span data-ttu-id="72e82-454">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="72e82-454">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="72e82-455">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72e82-455">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="72e82-456">`false` – Freigabe an Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="72e82-456">`false` - release to OS</span></span><br/><span data-ttu-id="72e82-457">`true` – in Standbymodus versetzen</span><span class="sxs-lookup"><span data-stu-id="72e82-457">`true` - put on standby</span></span> | <span data-ttu-id="72e82-458">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="72e82-458">.NET Core 1.0</span></span> |
| <span data-ttu-id="72e82-459">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="72e82-459">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="72e82-460">`false` – Freigabe an Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="72e82-460">`false` - release to OS</span></span><br/><span data-ttu-id="72e82-461">`true` – in Standbymodus versetzen</span><span class="sxs-lookup"><span data-stu-id="72e82-461">`true` - put on standby</span></span> | <span data-ttu-id="72e82-462">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="72e82-462">.NET Core 1.0</span></span> |
| <span data-ttu-id="72e82-463">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72e82-463">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="72e82-464">`0` – Freigabe an Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="72e82-464">`0` - release to OS</span></span><br/><span data-ttu-id="72e82-465">`1` – in Standbymodus versetzen</span><span class="sxs-lookup"><span data-stu-id="72e82-465">`1` - put on standby</span></span> | <span data-ttu-id="72e82-466">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="72e82-466">.NET Core 1.0</span></span> |

#### <a name="examples"></a><span data-ttu-id="72e82-467">Beispiele</span><span class="sxs-lookup"><span data-stu-id="72e82-467">Examples</span></span>

<span data-ttu-id="72e82-468">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="72e82-468">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="72e82-469">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="72e82-469">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="72e82-470">Umfangreiche Seiten</span><span class="sxs-lookup"><span data-stu-id="72e82-470">Large pages</span></span>

- <span data-ttu-id="72e82-471">Gibt an, ob umfangreiche Seiten verwendet werden sollen, wenn eine feste Heapgrenze festgelegt wird</span><span class="sxs-lookup"><span data-stu-id="72e82-471">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="72e82-472">Standard: Verwenden Sie keine großen Seiten, wenn eine feste Heapgrenze festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="72e82-472">Default: Don't use large pages when a heap hard limit is set.</span></span> <span data-ttu-id="72e82-473">Dies entspricht der Einstellung des Werts auf `0`.</span><span class="sxs-lookup"><span data-stu-id="72e82-473">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="72e82-474">Dies ist eine experimentelle Einstellung.</span><span class="sxs-lookup"><span data-stu-id="72e82-474">This is an experimental setting.</span></span>

| | <span data-ttu-id="72e82-475">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72e82-475">Setting name</span></span> | <span data-ttu-id="72e82-476">Werte</span><span class="sxs-lookup"><span data-stu-id="72e82-476">Values</span></span> | <span data-ttu-id="72e82-477">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="72e82-477">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="72e82-478">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72e82-478">**runtimeconfig.json**</span></span> | <span data-ttu-id="72e82-479">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="72e82-479">N/A</span></span> | <span data-ttu-id="72e82-480">–</span><span class="sxs-lookup"><span data-stu-id="72e82-480">N/A</span></span> | <span data-ttu-id="72e82-481">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="72e82-481">N/A</span></span> |
| <span data-ttu-id="72e82-482">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72e82-482">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="72e82-483">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="72e82-483">`0` - disabled</span></span><br/><span data-ttu-id="72e82-484">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="72e82-484">`1` - enabled</span></span> | <span data-ttu-id="72e82-485">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="72e82-485">.NET Core 3.0</span></span> |

## <a name="allow-large-objects"></a><span data-ttu-id="72e82-486">Große Objekte zulassen</span><span class="sxs-lookup"><span data-stu-id="72e82-486">Allow large objects</span></span>

- <span data-ttu-id="72e82-487">Konfiguriert die Garbage-Collector-Unterstützung auf 64-Bit-Plattformen für Arrays mit einer Gesamtgröße von mehr als 2 Gigabytes (GB)</span><span class="sxs-lookup"><span data-stu-id="72e82-487">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="72e82-488">Standard: GC unterstützt Arrays, die größer als 2 GB sind.</span><span class="sxs-lookup"><span data-stu-id="72e82-488">Default: GC supports arrays greater than 2-GB.</span></span> <span data-ttu-id="72e82-489">Dies entspricht der Einstellung des Werts auf `1`.</span><span class="sxs-lookup"><span data-stu-id="72e82-489">This is equivalent to setting the value to `1`.</span></span>
- <span data-ttu-id="72e82-490">Diese Option wird in einer zukünftigen Version von .NET möglicherweise veraltet sein.</span><span class="sxs-lookup"><span data-stu-id="72e82-490">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="72e82-491">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72e82-491">Setting name</span></span> | <span data-ttu-id="72e82-492">Werte</span><span class="sxs-lookup"><span data-stu-id="72e82-492">Values</span></span> | <span data-ttu-id="72e82-493">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="72e82-493">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="72e82-494">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72e82-494">**runtimeconfig.json**</span></span> | <span data-ttu-id="72e82-495">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="72e82-495">N/A</span></span> | <span data-ttu-id="72e82-496">–</span><span class="sxs-lookup"><span data-stu-id="72e82-496">N/A</span></span> | <span data-ttu-id="72e82-497">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="72e82-497">N/A</span></span> |
| <span data-ttu-id="72e82-498">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72e82-498">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="72e82-499">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="72e82-499">`1` - enabled</span></span><br/> <span data-ttu-id="72e82-500">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="72e82-500">`0` - disabled</span></span> | <span data-ttu-id="72e82-501">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="72e82-501">.NET Core 1.0</span></span> |
| <span data-ttu-id="72e82-502">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="72e82-502">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="72e82-503">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="72e82-503">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="72e82-504">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="72e82-504">`1` - enabled</span></span><br/> <span data-ttu-id="72e82-505">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="72e82-505">`0` - disabled</span></span> | <span data-ttu-id="72e82-506">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="72e82-506">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="72e82-507">Großer Objektheapschwellenwert</span><span class="sxs-lookup"><span data-stu-id="72e82-507">Large object heap threshold</span></span>

- <span data-ttu-id="72e82-508">Gibt die Größe des Schwellenwerts in Bytes an, der bewirkt, dass Objekte auf den großen Objektheap (Large Object Heap, LOH) gehen</span><span class="sxs-lookup"><span data-stu-id="72e82-508">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="72e82-509">Der Standardschwellenwert beträgt 85.000 Bytes.</span><span class="sxs-lookup"><span data-stu-id="72e82-509">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="72e82-510">Der von Ihnen festgelegte Wert muss größer sein als der Standardschwellenwert.</span><span class="sxs-lookup"><span data-stu-id="72e82-510">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="72e82-511">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72e82-511">Setting name</span></span> | <span data-ttu-id="72e82-512">Werte</span><span class="sxs-lookup"><span data-stu-id="72e82-512">Values</span></span> | <span data-ttu-id="72e82-513">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="72e82-513">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="72e82-514">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72e82-514">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="72e82-515">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-515">*decimal value*</span></span> | <span data-ttu-id="72e82-516">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="72e82-516">.NET Core 1.0</span></span> |
| <span data-ttu-id="72e82-517">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72e82-517">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="72e82-518">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-518">*hexadecimal value*</span></span> | <span data-ttu-id="72e82-519">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="72e82-519">.NET Core 1.0</span></span> |
| <span data-ttu-id="72e82-520">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="72e82-520">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="72e82-521">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="72e82-521">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="72e82-522">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="72e82-522">*decimal value*</span></span> | <span data-ttu-id="72e82-523">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="72e82-523">.NET Framework 4.8</span></span> |

<span data-ttu-id="72e82-524">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="72e82-524">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.LOHThreshold": 120000
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="72e82-525">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="72e82-525">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="72e82-526">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="72e82-526">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="72e82-527">Wenn Sie beispielsweise die Größe eines Schwellenwerts auf 120.000 Bytes festlegen, würden die Werte für die JSON-Datei 120000 und für die Umgebungsvariable 0x1D4C0 oder 1D4C0 betragen.</span><span class="sxs-lookup"><span data-stu-id="72e82-527">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="72e82-528">Eigenständige GC</span><span class="sxs-lookup"><span data-stu-id="72e82-528">Standalone GC</span></span>

- <span data-ttu-id="72e82-529">Gibt einen Pfad zu der Bibliothek an, die den Garbage Collector enthält, der von der Runtime geladen werden soll</span><span class="sxs-lookup"><span data-stu-id="72e82-529">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="72e82-530">Weitere Informationen finden Sie unter [Entwurf eines eigenständigen GC-Ladeprogramms](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="72e82-530">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="72e82-531">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72e82-531">Setting name</span></span> | <span data-ttu-id="72e82-532">Werte</span><span class="sxs-lookup"><span data-stu-id="72e82-532">Values</span></span> | <span data-ttu-id="72e82-533">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="72e82-533">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="72e82-534">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72e82-534">**runtimeconfig.json**</span></span> | <span data-ttu-id="72e82-535">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="72e82-535">N/A</span></span> | <span data-ttu-id="72e82-536">–</span><span class="sxs-lookup"><span data-stu-id="72e82-536">N/A</span></span> | <span data-ttu-id="72e82-537">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="72e82-537">N/A</span></span> |
| <span data-ttu-id="72e82-538">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72e82-538">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="72e82-539">*string_path*</span><span class="sxs-lookup"><span data-stu-id="72e82-539">*string_path*</span></span> | <span data-ttu-id="72e82-540">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="72e82-540">.NET Core 2.0</span></span> |
