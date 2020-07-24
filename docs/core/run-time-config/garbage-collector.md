---
title: Garbage-Collector-Konfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, um zu konfigurieren, wie der Garbage Collector Arbeitsspeicher für .NET Core-Apps verwaltet.
ms.date: 07/10/2020
ms.topic: reference
ms.openlocfilehash: 6ae5b7447fb0df4978ea9dcaa5e76fcc7a6cc4ca
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441405"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="9bc73-103">Laufzeitkonfigurationsoptionen für die Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="9bc73-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="9bc73-104">Diese Seite enthält Informationen zu Garbage-Collector-Einstellungen (GC), die zur Laufzeit geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="9bc73-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="9bc73-105">Verwenden Sie diese Einstellungen, wenn Sie versuchen, die maximale Leistung einer ausgeführten App zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="9bc73-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="9bc73-106">Die Standardwerte bieten jedoch in typischen Situationen eine optimale Leistung für die meisten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="9bc73-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="9bc73-107">Einstellungen werden auf dieser Seite in Gruppen angeordnet.</span><span class="sxs-lookup"><span data-stu-id="9bc73-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="9bc73-108">Die Einstellungen in den einzelnen Gruppen werden häufig zusammen verwendet, um ein bestimmtes Ergebnis zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="9bc73-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="9bc73-109">Diese Einstellungen können auch dynamisch von der App geändert werden, während diese ausgeführt wird, sodass die von Ihnen festgelegten Laufzeiteinstellungen überschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="9bc73-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="9bc73-110">Einige Einstellungen, wie z. B. die [Latenzebene](../../standard/garbage-collection/latency.md), werden in der Regel nur über die API zur Entwurfszeit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9bc73-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="9bc73-111">Diese Einstellungen werden auf dieser Seite weggelassen.</span><span class="sxs-lookup"><span data-stu-id="9bc73-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="9bc73-112">Verwenden Sie für Zahlenwerte für Einstellungen in der Datei *runtimeconfig.json* die Dezimalschreibweise und für Einstellungen in der Umgebungsvariablen die Hexadezimalnotation.</span><span class="sxs-lookup"><span data-stu-id="9bc73-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="9bc73-113">Bei hexadezimalen Werten können Sie sie mit dem oder ohne das Präfix „0x“ angeben.</span><span class="sxs-lookup"><span data-stu-id="9bc73-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="9bc73-114">Varianten der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="9bc73-114">Flavors of garbage collection</span></span>

<span data-ttu-id="9bc73-115">Die zwei Hauptvarianten der Garbage Collection sind Arbeitsstation-GC und Server-GC.</span><span class="sxs-lookup"><span data-stu-id="9bc73-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="9bc73-116">Weitere Informationen zu den Unterschieden zwischen diesen beiden Varianten finden Sie unter [Garbage Collection für die Arbeitsstation und Garbage Collection auf dem Server](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="9bc73-116">For more information about differences between the two, see [Workstation and server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span>

<span data-ttu-id="9bc73-117">Die Untervarianten der Garbage Collection sind Hintergrund-GC und nicht gleichzeitige GC.</span><span class="sxs-lookup"><span data-stu-id="9bc73-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="9bc73-118">Verwenden Sie die folgenden Einstellungen, um Varianten der Garbage Collection auszuwählen:</span><span class="sxs-lookup"><span data-stu-id="9bc73-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="9bc73-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="9bc73-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="9bc73-120">Konfiguriert, ob die Anwendung die Arbeitsstation-GC oder die Server-GC verwendet</span><span class="sxs-lookup"><span data-stu-id="9bc73-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="9bc73-121">Standard: Arbeitsstation-Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="9bc73-121">Default: Workstation garbage collection.</span></span> <span data-ttu-id="9bc73-122">Dies entspricht der Einstellung des Werts auf `false`.</span><span class="sxs-lookup"><span data-stu-id="9bc73-122">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="9bc73-123">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="9bc73-123">Setting name</span></span> | <span data-ttu-id="9bc73-124">Werte</span><span class="sxs-lookup"><span data-stu-id="9bc73-124">Values</span></span> | <span data-ttu-id="9bc73-125">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9bc73-125">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9bc73-126">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9bc73-126">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="9bc73-127">`false` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="9bc73-127">`false` - workstation</span></span><br/><span data-ttu-id="9bc73-128">`true` – Server</span><span class="sxs-lookup"><span data-stu-id="9bc73-128">`true` - server</span></span> | <span data-ttu-id="9bc73-129">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-129">.NET Core 1.0</span></span> |
| <span data-ttu-id="9bc73-130">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="9bc73-130">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="9bc73-131">`false` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="9bc73-131">`false` - workstation</span></span><br/><span data-ttu-id="9bc73-132">`true` – Server</span><span class="sxs-lookup"><span data-stu-id="9bc73-132">`true` - server</span></span> | <span data-ttu-id="9bc73-133">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-133">.NET Core 1.0</span></span> |
| <span data-ttu-id="9bc73-134">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="9bc73-134">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="9bc73-135">`0` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="9bc73-135">`0` - workstation</span></span><br/><span data-ttu-id="9bc73-136">`1` – Server</span><span class="sxs-lookup"><span data-stu-id="9bc73-136">`1` - server</span></span> | <span data-ttu-id="9bc73-137">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-137">.NET Core 1.0</span></span> |
| <span data-ttu-id="9bc73-138">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="9bc73-138">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9bc73-139">GCServer</span><span class="sxs-lookup"><span data-stu-id="9bc73-139">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="9bc73-140">`false` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="9bc73-140">`false` - workstation</span></span><br/><span data-ttu-id="9bc73-141">`true` – Server</span><span class="sxs-lookup"><span data-stu-id="9bc73-141">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="9bc73-142">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9bc73-142">Examples</span></span>

<span data-ttu-id="9bc73-143">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="9bc73-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="9bc73-144">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="9bc73-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="9bc73-145">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="9bc73-145">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="9bc73-146">Konfiguriert, ob die (gleichzeitige) Hintergrund-GC aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="9bc73-146">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="9bc73-147">Standard: Garbage Collection im Hintergrund verwenden.</span><span class="sxs-lookup"><span data-stu-id="9bc73-147">Default: Use background GC.</span></span> <span data-ttu-id="9bc73-148">Dies entspricht der Einstellung des Werts auf `true`.</span><span class="sxs-lookup"><span data-stu-id="9bc73-148">This is equivalent to setting the value to `true`.</span></span>
- <span data-ttu-id="9bc73-149">Weitere Informationen finden Sie unter [Hintergrund der Garbage Collection](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="9bc73-149">For more information, see [Background garbage collection](../../standard/garbage-collection/background-gc.md).</span></span>

| | <span data-ttu-id="9bc73-150">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="9bc73-150">Setting name</span></span> | <span data-ttu-id="9bc73-151">Werte</span><span class="sxs-lookup"><span data-stu-id="9bc73-151">Values</span></span> | <span data-ttu-id="9bc73-152">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9bc73-152">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9bc73-153">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9bc73-153">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="9bc73-154">`true` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="9bc73-154">`true` - background GC</span></span><br/><span data-ttu-id="9bc73-155">`false` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="9bc73-155">`false` - non-concurrent GC</span></span> | <span data-ttu-id="9bc73-156">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-156">.NET Core 1.0</span></span> |
| <span data-ttu-id="9bc73-157">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="9bc73-157">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="9bc73-158">`true` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="9bc73-158">`true` - background GC</span></span><br/><span data-ttu-id="9bc73-159">`false` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="9bc73-159">`false` - non-concurrent GC</span></span> | <span data-ttu-id="9bc73-160">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-160">.NET Core 1.0</span></span> |
| <span data-ttu-id="9bc73-161">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="9bc73-161">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="9bc73-162">`1` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="9bc73-162">`1` - background GC</span></span><br/><span data-ttu-id="9bc73-163">`0` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="9bc73-163">`0` - non-concurrent GC</span></span> | <span data-ttu-id="9bc73-164">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-164">.NET Core 1.0</span></span> |
| <span data-ttu-id="9bc73-165">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="9bc73-165">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9bc73-166">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="9bc73-166">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="9bc73-167">`true` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="9bc73-167">`true` - background GC</span></span><br/><span data-ttu-id="9bc73-168">`false` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="9bc73-168">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="9bc73-169">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9bc73-169">Examples</span></span>

<span data-ttu-id="9bc73-170">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="9bc73-170">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="9bc73-171">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="9bc73-171">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="9bc73-172">Verwalten des Ressourceneinsatzes</span><span class="sxs-lookup"><span data-stu-id="9bc73-172">Manage resource usage</span></span>

<span data-ttu-id="9bc73-173">Verwenden Sie die in diesem Abschnitt beschriebenen Einstellungen, um die Speicher- und Prozessorauslastung des Garbage Collectors zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="9bc73-173">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="9bc73-174">Weitere Informationen zu einigen dieser Einstellungen finden Sie im Blogeintrag [Mittelweg zwischen Arbeitsstation- und Server-GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).</span><span class="sxs-lookup"><span data-stu-id="9bc73-174">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="9bc73-175">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="9bc73-175">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="9bc73-176">Schränkt die Anzahl von Heaps ein, die vom Garbage Collector erstellt werden</span><span class="sxs-lookup"><span data-stu-id="9bc73-176">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="9bc73-177">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="9bc73-177">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="9bc73-178">Wenn die [GC-Prozessoraffinität](#systemgcnoaffinitizecomplus_gcnoaffinitize) aktiviert ist (Standardeinstellung), ordnet die Einstellung für die Heapanzahl den ersten `n` Prozessoren `n` GC-Heaps/-Threads zu.</span><span class="sxs-lookup"><span data-stu-id="9bc73-178">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="9bc73-179">(Verwenden Sie die Einstellungen [AffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) oder [AffinitizeRanges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges), um genau anzugeben, welche Prozessoren zugeordnet werden sollen.)</span><span class="sxs-lookup"><span data-stu-id="9bc73-179">(Use the [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) or [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="9bc73-180">Wenn die [GC-Prozessoraffinität](#systemgcnoaffinitizecomplus_gcnoaffinitize) deaktiviert ist, wird mit dieser Einstellung die Anzahl der GC-Heaps eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="9bc73-180">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="9bc73-181">Weitere Informationen finden Sie unter [Hinweise zu GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="9bc73-181">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="9bc73-182">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="9bc73-182">Setting name</span></span> | <span data-ttu-id="9bc73-183">Werte</span><span class="sxs-lookup"><span data-stu-id="9bc73-183">Values</span></span> | <span data-ttu-id="9bc73-184">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9bc73-184">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9bc73-185">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9bc73-185">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="9bc73-186">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="9bc73-186">*decimal value*</span></span> | <span data-ttu-id="9bc73-187">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-187">.NET Core 3.0</span></span> |
| <span data-ttu-id="9bc73-188">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="9bc73-188">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="9bc73-189">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="9bc73-189">*hexadecimal value*</span></span> | <span data-ttu-id="9bc73-190">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-190">.NET Core 3.0</span></span> |
| <span data-ttu-id="9bc73-191">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="9bc73-191">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9bc73-192">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="9bc73-192">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="9bc73-193">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="9bc73-193">*decimal value*</span></span> | <span data-ttu-id="9bc73-194">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="9bc73-194">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="9bc73-195">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9bc73-195">Example:</span></span>

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
> <span data-ttu-id="9bc73-196">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="9bc73-196">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="9bc73-197">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="9bc73-197">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="9bc73-198">Für eine Einschränkung der Heapanzahl auf 16 wären die Werte beispielsweise 16 für die JSON-Datei und 0x10 oder 10 für die Umgebungsvariable.</span><span class="sxs-lookup"><span data-stu-id="9bc73-198">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="9bc73-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="9bc73-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="9bc73-200">Gibt die genauen Prozessoren an, die Garbage-Collector-Threads verwenden sollen</span><span class="sxs-lookup"><span data-stu-id="9bc73-200">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="9bc73-201">Wenn die [GC-Prozessoraffinität](#systemgcnoaffinitizecomplus_gcnoaffinitize) deaktiviert ist, wird diese Einstellung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="9bc73-201">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="9bc73-202">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="9bc73-202">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="9bc73-203">Der Wert ist eine Bitmaske, die die für den Prozess verfügbaren Prozessoren definiert.</span><span class="sxs-lookup"><span data-stu-id="9bc73-203">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="9bc73-204">Beispielsweise ist ein Dezimalwert von 1023 (oder ein Hexadezimalwert von 0x3FF oder 3FF bei Verwendung der Umgebungsvariablen) in Binärschreibweise 0011 1111 1111.</span><span class="sxs-lookup"><span data-stu-id="9bc73-204">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="9bc73-205">Dies gibt an, dass die ersten zehn Prozessoren verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9bc73-205">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="9bc73-206">Geben Sie einen Dezimalwert von 1047552 (oder einen Hexadezimalwert von 0xFFC00 oder FFC00) an, der einem Binärwert von 1111 1111 1100 0000 0000 entspricht, um die nächsten zehn Prozessoren anzugeben, d. h. die Prozessoren 10 bis 19.</span><span class="sxs-lookup"><span data-stu-id="9bc73-206">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="9bc73-207">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="9bc73-207">Setting name</span></span> | <span data-ttu-id="9bc73-208">Werte</span><span class="sxs-lookup"><span data-stu-id="9bc73-208">Values</span></span> | <span data-ttu-id="9bc73-209">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9bc73-209">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9bc73-210">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9bc73-210">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="9bc73-211">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="9bc73-211">*decimal value*</span></span> | <span data-ttu-id="9bc73-212">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-212">.NET Core 3.0</span></span> |
| <span data-ttu-id="9bc73-213">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="9bc73-213">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="9bc73-214">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="9bc73-214">*hexadecimal value*</span></span> | <span data-ttu-id="9bc73-215">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-215">.NET Core 3.0</span></span> |
| <span data-ttu-id="9bc73-216">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="9bc73-216">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9bc73-217">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="9bc73-217">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="9bc73-218">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="9bc73-218">*decimal value*</span></span> | <span data-ttu-id="9bc73-219">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="9bc73-219">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="9bc73-220">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9bc73-220">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="9bc73-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="9bc73-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="9bc73-222">Gibt die Liste der Prozessoren an, die für Garbage-Collector-Threads verwendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="9bc73-222">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="9bc73-223">Diese Einstellung ähnelt [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), abgesehen davon, dass Sie mehr als 64 Prozessoren angeben können.</span><span class="sxs-lookup"><span data-stu-id="9bc73-223">This setting is similar to [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="9bc73-224">Stellen Sie für Windows-Betriebssysteme der Prozessornummer oder dem Prozessorbereich die entsprechende [CPU-Gruppe](/windows/win32/procthread/processor-groups) voran, z. B. „0:1-10,0:12,1:50-52,1:70“.</span><span class="sxs-lookup"><span data-stu-id="9bc73-224">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="9bc73-225">Wenn die [GC-Prozessoraffinität](#systemgcnoaffinitizecomplus_gcnoaffinitize) deaktiviert ist, wird diese Einstellung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="9bc73-225">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="9bc73-226">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="9bc73-226">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="9bc73-227">Weitere Informationen finden Sie unter [Optimieren der CPU-Konfiguration für GC auf Computern mit mehr als 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) im Blog von Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="9bc73-227">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="9bc73-228">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="9bc73-228">Setting name</span></span> | <span data-ttu-id="9bc73-229">Werte</span><span class="sxs-lookup"><span data-stu-id="9bc73-229">Values</span></span> | <span data-ttu-id="9bc73-230">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9bc73-230">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9bc73-231">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9bc73-231">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="9bc73-232">Durch Kommas getrennte Liste mit Prozessornummern oder Bereichen von Prozessornummern</span><span class="sxs-lookup"><span data-stu-id="9bc73-232">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="9bc73-233">Unix-Beispiel: „1-10,12,50-52,70“</span><span class="sxs-lookup"><span data-stu-id="9bc73-233">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="9bc73-234">Windows-Beispiel: „0:1-10,0:12,1:50-52,1:70“</span><span class="sxs-lookup"><span data-stu-id="9bc73-234">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="9bc73-235">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-235">.NET Core 3.0</span></span> |
| <span data-ttu-id="9bc73-236">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="9bc73-236">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="9bc73-237">Durch Kommas getrennte Liste mit Prozessornummern oder Bereichen von Prozessornummern</span><span class="sxs-lookup"><span data-stu-id="9bc73-237">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="9bc73-238">Unix-Beispiel: „1-10,12,50-52,70“</span><span class="sxs-lookup"><span data-stu-id="9bc73-238">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="9bc73-239">Windows-Beispiel: „0:1-10,0:12,1:50-52,1:70“</span><span class="sxs-lookup"><span data-stu-id="9bc73-239">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="9bc73-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-240">.NET Core 3.0</span></span> |

<span data-ttu-id="9bc73-241">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9bc73-241">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="9bc73-242">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="9bc73-242">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="9bc73-243">Konfiguriert, ob der Garbage Collector [CPU-Gruppen](/windows/win32/procthread/processor-groups) verwendet</span><span class="sxs-lookup"><span data-stu-id="9bc73-243">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="9bc73-244">Wenn ein 64-Bit-Windows-Computer über mehrere CPU-Gruppen verfügt, d. h. mehr als 64 Prozessoren vorhanden sind, dann wird durch die Aktivierung dieses Elements die Garbage Collection in allen CPU-Gruppen erweitert.</span><span class="sxs-lookup"><span data-stu-id="9bc73-244">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="9bc73-245">Der Garbage Collector verwendet alle Kerne zum Erstellen und Ausgleichen von Heaps.</span><span class="sxs-lookup"><span data-stu-id="9bc73-245">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="9bc73-246">Gilt nur für Garbage Collection des Servers auf 64-Bit-Windows-Betriebssystemen.</span><span class="sxs-lookup"><span data-stu-id="9bc73-246">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="9bc73-247">Standard: GC wird nicht über CPU-Gruppen hinweg erweitert.</span><span class="sxs-lookup"><span data-stu-id="9bc73-247">Default: GC does not extend across CPU groups.</span></span> <span data-ttu-id="9bc73-248">Dies entspricht der Einstellung des Werts auf `0`.</span><span class="sxs-lookup"><span data-stu-id="9bc73-248">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="9bc73-249">Weitere Informationen finden Sie unter [Optimieren der CPU-Konfiguration für GC auf Computern mit mehr als 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) im Blog von Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="9bc73-249">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="9bc73-250">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="9bc73-250">Setting name</span></span> | <span data-ttu-id="9bc73-251">Werte</span><span class="sxs-lookup"><span data-stu-id="9bc73-251">Values</span></span> | <span data-ttu-id="9bc73-252">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9bc73-252">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9bc73-253">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9bc73-253">**runtimeconfig.json**</span></span> | <span data-ttu-id="9bc73-254">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="9bc73-254">N/A</span></span> | <span data-ttu-id="9bc73-255">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="9bc73-255">N/A</span></span> | <span data-ttu-id="9bc73-256">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="9bc73-256">N/A</span></span> |
| <span data-ttu-id="9bc73-257">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="9bc73-257">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="9bc73-258">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="9bc73-258">`0` - disabled</span></span><br/><span data-ttu-id="9bc73-259">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="9bc73-259">`1` - enabled</span></span> | <span data-ttu-id="9bc73-260">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-260">.NET Core 1.0</span></span> |
| <span data-ttu-id="9bc73-261">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="9bc73-261">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9bc73-262">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="9bc73-262">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="9bc73-263">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="9bc73-263">`false` - disabled</span></span><br/><span data-ttu-id="9bc73-264">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="9bc73-264">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="9bc73-265">Aktivieren Sie die Option [Thread_UseAllCpuGroups-Element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md), um die Common Language Runtime (CLR) so zu konfigurieren, dass auch Threads aus dem Threadpool in allen CPU-Gruppen verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="9bc73-265">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="9bc73-266">Für .NET Core-Apps können Sie diese Option aktivieren, indem Sie den Wert der Umgebungsvariablen `COMPlus_Thread_UseAllCpuGroups` auf `1` setzen.</span><span class="sxs-lookup"><span data-stu-id="9bc73-266">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="9bc73-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="9bc73-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="9bc73-268">Gibt an, ob Garbage-Collection-Threads Prozessoren *zugeordnet* werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9bc73-268">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="9bc73-269">Einen GC-Thread zuzuordnen, bedeutet, dass dieser nur auf der jeweiligen CPU ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9bc73-269">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="9bc73-270">Für jeden GC-Thread wird ein Heap erstellt.</span><span class="sxs-lookup"><span data-stu-id="9bc73-270">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="9bc73-271">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="9bc73-271">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="9bc73-272">Standard: Garbage Collection-Threads werden Prozessoren zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9bc73-272">Default: Affinitize garbage collection threads with processors.</span></span> <span data-ttu-id="9bc73-273">Dies entspricht der Einstellung des Werts auf `false`.</span><span class="sxs-lookup"><span data-stu-id="9bc73-273">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="9bc73-274">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="9bc73-274">Setting name</span></span> | <span data-ttu-id="9bc73-275">Werte</span><span class="sxs-lookup"><span data-stu-id="9bc73-275">Values</span></span> | <span data-ttu-id="9bc73-276">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9bc73-276">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9bc73-277">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9bc73-277">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="9bc73-278">`false` – zuordnen</span><span class="sxs-lookup"><span data-stu-id="9bc73-278">`false` - affinitize</span></span><br/><span data-ttu-id="9bc73-279">`true` – nicht zuordnen</span><span class="sxs-lookup"><span data-stu-id="9bc73-279">`true` - don't affinitize</span></span> | <span data-ttu-id="9bc73-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="9bc73-281">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="9bc73-281">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="9bc73-282">`0` – zuordnen</span><span class="sxs-lookup"><span data-stu-id="9bc73-282">`0` - affinitize</span></span><br/><span data-ttu-id="9bc73-283">`1` – nicht zuordnen</span><span class="sxs-lookup"><span data-stu-id="9bc73-283">`1` - don't affinitize</span></span> | <span data-ttu-id="9bc73-284">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-284">.NET Core 3.0</span></span> |
| <span data-ttu-id="9bc73-285">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="9bc73-285">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9bc73-286">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="9bc73-286">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="9bc73-287">`false` – zuordnen</span><span class="sxs-lookup"><span data-stu-id="9bc73-287">`false` - affinitize</span></span><br/><span data-ttu-id="9bc73-288">`true` – nicht zuordnen</span><span class="sxs-lookup"><span data-stu-id="9bc73-288">`true` - don't affinitize</span></span> | <span data-ttu-id="9bc73-289">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="9bc73-289">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="9bc73-290">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9bc73-290">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="9bc73-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="9bc73-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="9bc73-292">Gibt die maximale Commitgröße in Bytes für den GC-Heap und die GC-Buchhaltung an</span><span class="sxs-lookup"><span data-stu-id="9bc73-292">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="9bc73-293">Diese Einstellung gilt nur für 64-Bit-Computer.</span><span class="sxs-lookup"><span data-stu-id="9bc73-293">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="9bc73-294">Diese Einstellung wird ignoriert, wenn die [Grenzwerte pro Objektheap](#per-object-heap-limits) konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="9bc73-294">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="9bc73-295">Der Standardwert, der nur in bestimmten Fällen gilt, ist der größere Wert von 20 MB oder 75 % der Speichergrenze für den Container.</span><span class="sxs-lookup"><span data-stu-id="9bc73-295">The default value, which only applies in certain cases, is the greater of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="9bc73-296">Der Standardwert wird in folgenden Fällen angewendet:</span><span class="sxs-lookup"><span data-stu-id="9bc73-296">The default value applies if:</span></span>

  - <span data-ttu-id="9bc73-297">Der Prozess wird in einem Container ausgeführt, für den ein Arbeitsspeicherlimit angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="9bc73-297">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="9bc73-298">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) ist nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9bc73-298">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) is not set.</span></span>

| | <span data-ttu-id="9bc73-299">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="9bc73-299">Setting name</span></span> | <span data-ttu-id="9bc73-300">Werte</span><span class="sxs-lookup"><span data-stu-id="9bc73-300">Values</span></span> | <span data-ttu-id="9bc73-301">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9bc73-301">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9bc73-302">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9bc73-302">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="9bc73-303">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="9bc73-303">*decimal value*</span></span> | <span data-ttu-id="9bc73-304">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-304">.NET Core 3.0</span></span> |
| <span data-ttu-id="9bc73-305">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="9bc73-305">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="9bc73-306">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="9bc73-306">*hexadecimal value*</span></span> | <span data-ttu-id="9bc73-307">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-307">.NET Core 3.0</span></span> |

<span data-ttu-id="9bc73-308">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9bc73-308">Example:</span></span>

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
> <span data-ttu-id="9bc73-309">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="9bc73-309">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="9bc73-310">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="9bc73-310">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="9bc73-311">Wenn Sie beispielsweise eine feste Heapgrenze von 200 MiB festlegen, würden die Werte für die JSON-Datei 209715200 und für die Umgebungsvariable 0xc800000 oder C800000 betragen.</span><span class="sxs-lookup"><span data-stu-id="9bc73-311">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="9bc73-312">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="9bc73-312">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="9bc73-313">Gibt den zulässigen GC-Heapverbrauch in Prozent des gesamten physischen Speichers an.</span><span class="sxs-lookup"><span data-stu-id="9bc73-313">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="9bc73-314">Wenn außerdem [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) festgelegt ist, wird diese Einstellung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="9bc73-314">If [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="9bc73-315">Diese Einstellung gilt nur für 64-Bit-Computer.</span><span class="sxs-lookup"><span data-stu-id="9bc73-315">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="9bc73-316">Wenn der Prozess in einem Container ausgeführt, für den ein Arbeitsspeicherlimit angegeben wurde, wird der Prozentsatz als Prozentsatz dieses Arbeitsspeicherlimits berechnet.</span><span class="sxs-lookup"><span data-stu-id="9bc73-316">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="9bc73-317">Diese Einstellung wird ignoriert, wenn die [Grenzwerte pro Objektheap](#per-object-heap-limits) konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="9bc73-317">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="9bc73-318">Der Standardwert, der nur in bestimmten Fällen angewendet wird, beträgt weniger als 20 MB oder 75 % des Arbeitsspeicherlimits für den Container.</span><span class="sxs-lookup"><span data-stu-id="9bc73-318">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="9bc73-319">Der Standardwert wird in folgenden Fällen angewendet:</span><span class="sxs-lookup"><span data-stu-id="9bc73-319">The default value applies if:</span></span>

  - <span data-ttu-id="9bc73-320">Der Prozess wird in einem Container ausgeführt, für den ein Arbeitsspeicherlimit angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="9bc73-320">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="9bc73-321">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) ist nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9bc73-321">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is not set.</span></span>

| | <span data-ttu-id="9bc73-322">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="9bc73-322">Setting name</span></span> | <span data-ttu-id="9bc73-323">Werte</span><span class="sxs-lookup"><span data-stu-id="9bc73-323">Values</span></span> | <span data-ttu-id="9bc73-324">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9bc73-324">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9bc73-325">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9bc73-325">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="9bc73-326">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="9bc73-326">*decimal value*</span></span> | <span data-ttu-id="9bc73-327">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-327">.NET Core 3.0</span></span> |
| <span data-ttu-id="9bc73-328">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="9bc73-328">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="9bc73-329">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="9bc73-329">*hexadecimal value*</span></span> | <span data-ttu-id="9bc73-330">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-330">.NET Core 3.0</span></span> |

<span data-ttu-id="9bc73-331">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9bc73-331">Example:</span></span>

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
> <span data-ttu-id="9bc73-332">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="9bc73-332">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="9bc73-333">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="9bc73-333">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="9bc73-334">Beispielsweise würden bei einer Begrenzung des Heapverbrauchs auf 30 % die Werte für die JSON-Datei 30 und für die Umgebungsvariable 0x1E oder 1E betragen.</span><span class="sxs-lookup"><span data-stu-id="9bc73-334">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="per-object-heap-limits"></a><span data-ttu-id="9bc73-335">Grenzwerte pro Objektheap</span><span class="sxs-lookup"><span data-stu-id="9bc73-335">Per-object-heap limits</span></span>

<span data-ttu-id="9bc73-336">Sie können die zulässige Heapnutzung bei der Garbage Collection pro Objektheap angeben.</span><span class="sxs-lookup"><span data-stu-id="9bc73-336">You can specify the GC's allowable heap usage on a per-object-heap basis.</span></span> <span data-ttu-id="9bc73-337">Die verschiedenen Arten von Heaps sind: große Objektheaps (Large Object Heap, LOH), kleine Objektheaps (Small Object Heap, SOH) und fixierte Objektheaps (Pinned Object Heap, POH).</span><span class="sxs-lookup"><span data-stu-id="9bc73-337">The different heaps are the large object heap (LOH), small object heap (SOH), and pinned object heap (POH).</span></span>

#### <a name="complus_gcheaphardlimitsoh-complus_gcheaphardlimitloh-complus_gcheaphardlimitpoh"></a><span data-ttu-id="9bc73-338">COMPLUS_GCHeapHardLimitSOH, COMPLUS_GCHeapHardLimitLOH, COMPLUS_GCHeapHardLimitPOH</span><span class="sxs-lookup"><span data-stu-id="9bc73-338">COMPLUS_GCHeapHardLimitSOH, COMPLUS_GCHeapHardLimitLOH, COMPLUS_GCHeapHardLimitPOH</span></span>

- <span data-ttu-id="9bc73-339">Wenn Sie für eine der Einstellungen `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH` oder `COMPLUS_GCHeapHardLimitPOH` einen Wert angeben, müssen Sie auch einen Wert für `COMPLUS_GCHeapHardLimitSOH` und `COMPLUS_GCHeapHardLimitLOH` angeben.</span><span class="sxs-lookup"><span data-stu-id="9bc73-339">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, or `COMPLUS_GCHeapHardLimitPOH` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH`.</span></span> <span data-ttu-id="9bc73-340">Andernfalls kann die Laufzeit nicht initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="9bc73-340">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="9bc73-341">Der Standardwert für `COMPLUS_GCHeapHardLimitPOH` ist 0.</span><span class="sxs-lookup"><span data-stu-id="9bc73-341">The default value for `COMPLUS_GCHeapHardLimitPOH` is 0.</span></span> <span data-ttu-id="9bc73-342">`COMPLUS_GCHeapHardLimitSOH` und `COMPLUS_GCHeapHardLimitLOH` verfügen über keine Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="9bc73-342">`COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH` don't have default values.</span></span>

| | <span data-ttu-id="9bc73-343">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="9bc73-343">Setting name</span></span> | <span data-ttu-id="9bc73-344">Werte</span><span class="sxs-lookup"><span data-stu-id="9bc73-344">Values</span></span> | <span data-ttu-id="9bc73-345">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9bc73-345">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9bc73-346">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="9bc73-346">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOH` | <span data-ttu-id="9bc73-347">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="9bc73-347">*hexadecimal value*</span></span> | <span data-ttu-id="9bc73-348">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-348">.NET 5.0</span></span> |
| <span data-ttu-id="9bc73-349">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="9bc73-349">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOH` | <span data-ttu-id="9bc73-350">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="9bc73-350">*hexadecimal value*</span></span> | <span data-ttu-id="9bc73-351">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-351">.NET 5.0</span></span> |
| <span data-ttu-id="9bc73-352">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="9bc73-352">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOH` | <span data-ttu-id="9bc73-353">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="9bc73-353">*hexadecimal value*</span></span> | <span data-ttu-id="9bc73-354">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-354">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="9bc73-355">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="9bc73-355">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="9bc73-356">Wenn Sie z. B. eine feste Heapgrenze von 200 Mebibyte (MiB) angeben möchten, wäre der Wert 0xC800000 oder C800000.</span><span class="sxs-lookup"><span data-stu-id="9bc73-356">For example, to specify a heap hard limit of 200 mebibytes (MiB), the value would be 0xC800000 or C800000.</span></span>

#### <a name="complus_gcheaphardlimitsohpercent-complus_gcheaphardlimitlohpercent-complus_gcheaphardlimitpohpercent"></a><span data-ttu-id="9bc73-357">COMPLUS_GCHeapHardLimitSOHPercent, COMPLUS_GCHeapHardLimitLOHPercent, COMPLUS_GCHeapHardLimitPOHPercent</span><span class="sxs-lookup"><span data-stu-id="9bc73-357">COMPLUS_GCHeapHardLimitSOHPercent, COMPLUS_GCHeapHardLimitLOHPercent, COMPLUS_GCHeapHardLimitPOHPercent</span></span>

- <span data-ttu-id="9bc73-358">Wenn Sie für eine der Einstellungen `COMPLUS_GCHeapHardLimitSOHPercent`, `COMPLUS_GCHeapHardLimitLOHPercent` oder `COMPLUS_GCHeapHardLimitPOHPercent` einen Wert angeben, müssen Sie auch einen Wert für `COMPLUS_GCHeapHardLimitSOHPercent` und `COMPLUS_GCHeapHardLimitLOHPercent` angeben.</span><span class="sxs-lookup"><span data-stu-id="9bc73-358">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOHPercent`, `COMPLUS_GCHeapHardLimitLOHPercent`, or `COMPLUS_GCHeapHardLimitPOHPercent` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOHPercent` and `COMPLUS_GCHeapHardLimitLOHPercent`.</span></span> <span data-ttu-id="9bc73-359">Andernfalls kann die Laufzeit nicht initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="9bc73-359">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="9bc73-360">Diese Einstellungen werden ignoriert, wenn `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH` und `COMPLUS_GCHeapHardLimitPOH` angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="9bc73-360">These settings are ignored if `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, and `COMPLUS_GCHeapHardLimitPOH` are specified.</span></span>
- <span data-ttu-id="9bc73-361">Der Wert 1 bedeutet, dass die Garbage Collection 1 % des gesamten physischen Speichers für diesen Objektheap verwendet.</span><span class="sxs-lookup"><span data-stu-id="9bc73-361">A value of 1 means that GC uses 1% of total physical memory for that object heap.</span></span>
- <span data-ttu-id="9bc73-362">Jeder Wert muss größer als 0 (null) und kleiner als 100 sein.</span><span class="sxs-lookup"><span data-stu-id="9bc73-362">Each value must be greater than zero and less than 100.</span></span> <span data-ttu-id="9bc73-363">Außerdem muss die Summe der drei Prozentwerte kleiner als 100 sein.</span><span class="sxs-lookup"><span data-stu-id="9bc73-363">Additionally, the sum of the three percentage values must be less than 100.</span></span> <span data-ttu-id="9bc73-364">Andernfalls tritt ein Fehler bei der Initialisierung der Laufzeit auf.</span><span class="sxs-lookup"><span data-stu-id="9bc73-364">Otherwise, the runtime will fail to initialize.</span></span>

| | <span data-ttu-id="9bc73-365">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="9bc73-365">Setting name</span></span> | <span data-ttu-id="9bc73-366">Werte</span><span class="sxs-lookup"><span data-stu-id="9bc73-366">Values</span></span> | <span data-ttu-id="9bc73-367">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9bc73-367">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9bc73-368">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="9bc73-368">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOHPercent` | <span data-ttu-id="9bc73-369">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="9bc73-369">*hexadecimal value*</span></span> | <span data-ttu-id="9bc73-370">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-370">.NET 5.0</span></span> |
| <span data-ttu-id="9bc73-371">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="9bc73-371">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOHPercent` | <span data-ttu-id="9bc73-372">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="9bc73-372">*hexadecimal value*</span></span> | <span data-ttu-id="9bc73-373">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-373">.NET 5.0</span></span> |
| <span data-ttu-id="9bc73-374">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="9bc73-374">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOHPercent` | <span data-ttu-id="9bc73-375">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="9bc73-375">*hexadecimal value*</span></span> | <span data-ttu-id="9bc73-376">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-376">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="9bc73-377">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="9bc73-377">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="9bc73-378">Wenn Sie z. B. die Heapnutzung auf 30 % beschränken möchten, wäre der entsprechende Wert 0x1E oder 1E.</span><span class="sxs-lookup"><span data-stu-id="9bc73-378">For example, to limit the heap usage to 30%, the value would be 0x1E or 1E.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="9bc73-379">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="9bc73-379">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="9bc73-380">Konfiguriert, ob Segmente, die gelöscht werden sollen, zur späteren Verwendung auf eine Standbyliste aufgenommen oder an das Betriebssystem zurückgegeben werden</span><span class="sxs-lookup"><span data-stu-id="9bc73-380">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="9bc73-381">Standard: Segmente werden an das Betriebssystem zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9bc73-381">Default: Release segments back to the operating system.</span></span> <span data-ttu-id="9bc73-382">Dies entspricht der Einstellung des Werts auf `false`.</span><span class="sxs-lookup"><span data-stu-id="9bc73-382">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="9bc73-383">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="9bc73-383">Setting name</span></span> | <span data-ttu-id="9bc73-384">Werte</span><span class="sxs-lookup"><span data-stu-id="9bc73-384">Values</span></span> | <span data-ttu-id="9bc73-385">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9bc73-385">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9bc73-386">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9bc73-386">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="9bc73-387">`false` – Freigabe an Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="9bc73-387">`false` - release to OS</span></span><br/><span data-ttu-id="9bc73-388">`true` – in Standbymodus versetzen</span><span class="sxs-lookup"><span data-stu-id="9bc73-388">`true` - put on standby</span></span> | <span data-ttu-id="9bc73-389">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-389">.NET Core 1.0</span></span> |
| <span data-ttu-id="9bc73-390">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="9bc73-390">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="9bc73-391">`false` – Freigabe an Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="9bc73-391">`false` - release to OS</span></span><br/><span data-ttu-id="9bc73-392">`true` – in Standbymodus versetzen</span><span class="sxs-lookup"><span data-stu-id="9bc73-392">`true` - put on standby</span></span> | <span data-ttu-id="9bc73-393">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-393">.NET Core 1.0</span></span> |
| <span data-ttu-id="9bc73-394">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="9bc73-394">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="9bc73-395">`0` – Freigabe an Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="9bc73-395">`0` - release to OS</span></span><br/><span data-ttu-id="9bc73-396">`1` – in Standbymodus versetzen</span><span class="sxs-lookup"><span data-stu-id="9bc73-396">`1` - put on standby</span></span> | <span data-ttu-id="9bc73-397">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-397">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="9bc73-398">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9bc73-398">Examples</span></span>

<span data-ttu-id="9bc73-399">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="9bc73-399">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="9bc73-400">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="9bc73-400">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="9bc73-401">Umfangreiche Seiten</span><span class="sxs-lookup"><span data-stu-id="9bc73-401">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="9bc73-402">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="9bc73-402">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="9bc73-403">Gibt an, ob umfangreiche Seiten verwendet werden sollen, wenn eine feste Heapgrenze festgelegt wird</span><span class="sxs-lookup"><span data-stu-id="9bc73-403">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="9bc73-404">Standard: Verwenden Sie keine großen Seiten, wenn eine feste Heapgrenze festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9bc73-404">Default: Don't use large pages when a heap hard limit is set.</span></span> <span data-ttu-id="9bc73-405">Dies entspricht der Einstellung des Werts auf `0`.</span><span class="sxs-lookup"><span data-stu-id="9bc73-405">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="9bc73-406">Dies ist eine experimentelle Einstellung.</span><span class="sxs-lookup"><span data-stu-id="9bc73-406">This is an experimental setting.</span></span>

| | <span data-ttu-id="9bc73-407">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="9bc73-407">Setting name</span></span> | <span data-ttu-id="9bc73-408">Werte</span><span class="sxs-lookup"><span data-stu-id="9bc73-408">Values</span></span> | <span data-ttu-id="9bc73-409">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9bc73-409">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9bc73-410">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9bc73-410">**runtimeconfig.json**</span></span> | <span data-ttu-id="9bc73-411">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="9bc73-411">N/A</span></span> | <span data-ttu-id="9bc73-412">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="9bc73-412">N/A</span></span> | <span data-ttu-id="9bc73-413">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="9bc73-413">N/A</span></span> |
| <span data-ttu-id="9bc73-414">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="9bc73-414">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="9bc73-415">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="9bc73-415">`0` - disabled</span></span><br/><span data-ttu-id="9bc73-416">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="9bc73-416">`1` - enabled</span></span> | <span data-ttu-id="9bc73-417">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-417">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="9bc73-418">Große Objekte</span><span class="sxs-lookup"><span data-stu-id="9bc73-418">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="9bc73-419">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="9bc73-419">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="9bc73-420">Konfiguriert die Garbage-Collector-Unterstützung auf 64-Bit-Plattformen für Arrays mit einer Gesamtgröße von mehr als 2 Gigabytes (GB)</span><span class="sxs-lookup"><span data-stu-id="9bc73-420">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="9bc73-421">Standard: GC unterstützt Arrays, die größer als 2 GB sind.</span><span class="sxs-lookup"><span data-stu-id="9bc73-421">Default: GC supports arrays greater than 2-GB.</span></span> <span data-ttu-id="9bc73-422">Dies entspricht der Einstellung des Werts auf `1`.</span><span class="sxs-lookup"><span data-stu-id="9bc73-422">This is equivalent to setting the value to `1`.</span></span>
- <span data-ttu-id="9bc73-423">Diese Option wird in einer zukünftigen Version von .NET möglicherweise veraltet sein.</span><span class="sxs-lookup"><span data-stu-id="9bc73-423">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="9bc73-424">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="9bc73-424">Setting name</span></span> | <span data-ttu-id="9bc73-425">Werte</span><span class="sxs-lookup"><span data-stu-id="9bc73-425">Values</span></span> | <span data-ttu-id="9bc73-426">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9bc73-426">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9bc73-427">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9bc73-427">**runtimeconfig.json**</span></span> | <span data-ttu-id="9bc73-428">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="9bc73-428">N/A</span></span> | <span data-ttu-id="9bc73-429">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="9bc73-429">N/A</span></span> | <span data-ttu-id="9bc73-430">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="9bc73-430">N/A</span></span> |
| <span data-ttu-id="9bc73-431">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="9bc73-431">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="9bc73-432">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="9bc73-432">`1` - enabled</span></span><br/> <span data-ttu-id="9bc73-433">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="9bc73-433">`0` - disabled</span></span> | <span data-ttu-id="9bc73-434">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-434">.NET Core 1.0</span></span> |
| <span data-ttu-id="9bc73-435">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="9bc73-435">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9bc73-436">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="9bc73-436">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="9bc73-437">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="9bc73-437">`1` - enabled</span></span><br/> <span data-ttu-id="9bc73-438">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="9bc73-438">`0` - disabled</span></span> | <span data-ttu-id="9bc73-439">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="9bc73-439">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="9bc73-440">Großer Objektheapschwellenwert</span><span class="sxs-lookup"><span data-stu-id="9bc73-440">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="9bc73-441">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="9bc73-441">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="9bc73-442">Gibt die Größe des Schwellenwerts in Bytes an, der bewirkt, dass Objekte auf den großen Objektheap (Large Object Heap, LOH) gehen</span><span class="sxs-lookup"><span data-stu-id="9bc73-442">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="9bc73-443">Der Standardschwellenwert beträgt 85.000 Bytes.</span><span class="sxs-lookup"><span data-stu-id="9bc73-443">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="9bc73-444">Der von Ihnen festgelegte Wert muss größer sein als der Standardschwellenwert.</span><span class="sxs-lookup"><span data-stu-id="9bc73-444">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="9bc73-445">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="9bc73-445">Setting name</span></span> | <span data-ttu-id="9bc73-446">Werte</span><span class="sxs-lookup"><span data-stu-id="9bc73-446">Values</span></span> | <span data-ttu-id="9bc73-447">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9bc73-447">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9bc73-448">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9bc73-448">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="9bc73-449">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="9bc73-449">*decimal value*</span></span> | <span data-ttu-id="9bc73-450">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-450">.NET Core 1.0</span></span> |
| <span data-ttu-id="9bc73-451">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="9bc73-451">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="9bc73-452">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="9bc73-452">*hexadecimal value*</span></span> | <span data-ttu-id="9bc73-453">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-453">.NET Core 1.0</span></span> |
| <span data-ttu-id="9bc73-454">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="9bc73-454">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9bc73-455">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="9bc73-455">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="9bc73-456">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="9bc73-456">*decimal value*</span></span> | <span data-ttu-id="9bc73-457">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="9bc73-457">.NET Framework 4.8</span></span> |

<span data-ttu-id="9bc73-458">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9bc73-458">Example:</span></span>

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
> <span data-ttu-id="9bc73-459">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="9bc73-459">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="9bc73-460">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="9bc73-460">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="9bc73-461">Wenn Sie beispielsweise die Größe eines Schwellenwerts auf 120.000 Bytes festlegen, würden die Werte für die JSON-Datei 120000 und für die Umgebungsvariable 0x1D4C0 oder 1D4C0 betragen.</span><span class="sxs-lookup"><span data-stu-id="9bc73-461">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="9bc73-462">Eigenständige GC</span><span class="sxs-lookup"><span data-stu-id="9bc73-462">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="9bc73-463">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="9bc73-463">COMPlus_GCName</span></span>

- <span data-ttu-id="9bc73-464">Gibt einen Pfad zu der Bibliothek an, die den Garbage Collector enthält, der von der Runtime geladen werden soll</span><span class="sxs-lookup"><span data-stu-id="9bc73-464">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="9bc73-465">Weitere Informationen finden Sie unter [Entwurf eines eigenständigen GC-Ladeprogramms](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="9bc73-465">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="9bc73-466">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="9bc73-466">Setting name</span></span> | <span data-ttu-id="9bc73-467">Werte</span><span class="sxs-lookup"><span data-stu-id="9bc73-467">Values</span></span> | <span data-ttu-id="9bc73-468">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9bc73-468">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9bc73-469">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9bc73-469">**runtimeconfig.json**</span></span> | <span data-ttu-id="9bc73-470">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="9bc73-470">N/A</span></span> | <span data-ttu-id="9bc73-471">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="9bc73-471">N/A</span></span> | <span data-ttu-id="9bc73-472">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="9bc73-472">N/A</span></span> |
| <span data-ttu-id="9bc73-473">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="9bc73-473">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="9bc73-474">*string_path*</span><span class="sxs-lookup"><span data-stu-id="9bc73-474">*string_path*</span></span> | <span data-ttu-id="9bc73-475">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="9bc73-475">.NET Core 2.0</span></span> |
