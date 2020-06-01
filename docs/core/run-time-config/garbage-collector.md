---
title: Garbage-Collector-Konfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, um zu konfigurieren, wie der Garbage Collector Arbeitsspeicher für .NET Core-Apps verwaltet.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: 0ce2f70204463c1525ef7d29de21ddf5384d0238
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202101"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="d4063-103">Laufzeitkonfigurationsoptionen für die Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="d4063-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="d4063-104">Diese Seite enthält Informationen zu Garbage-Collector-Einstellungen (GC), die zur Laufzeit geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="d4063-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="d4063-105">Verwenden Sie diese Einstellungen, wenn Sie versuchen, die maximale Leistung einer ausgeführten App zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="d4063-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="d4063-106">Die Standardwerte bieten jedoch in typischen Situationen eine optimale Leistung für die meisten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="d4063-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="d4063-107">Einstellungen werden auf dieser Seite in Gruppen angeordnet.</span><span class="sxs-lookup"><span data-stu-id="d4063-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="d4063-108">Die Einstellungen in den einzelnen Gruppen werden häufig zusammen verwendet, um ein bestimmtes Ergebnis zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="d4063-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="d4063-109">Diese Einstellungen können auch dynamisch von der App geändert werden, während diese ausgeführt wird, sodass die von Ihnen festgelegten Laufzeiteinstellungen überschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="d4063-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="d4063-110">Einige Einstellungen, wie z. B. die [Latenzebene](../../standard/garbage-collection/latency.md), werden in der Regel nur über die API zur Entwurfszeit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d4063-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="d4063-111">Diese Einstellungen werden auf dieser Seite weggelassen.</span><span class="sxs-lookup"><span data-stu-id="d4063-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="d4063-112">Verwenden Sie für Zahlenwerte für Einstellungen in der Datei *runtimeconfig.json* die Dezimalschreibweise und für Einstellungen in der Umgebungsvariablen die Hexadezimalnotation.</span><span class="sxs-lookup"><span data-stu-id="d4063-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="d4063-113">Bei hexadezimalen Werten können Sie sie mit dem oder ohne das Präfix „0x“ angeben.</span><span class="sxs-lookup"><span data-stu-id="d4063-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="d4063-114">Varianten der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="d4063-114">Flavors of garbage collection</span></span>

<span data-ttu-id="d4063-115">Die zwei Hauptvarianten der Garbage Collection sind Arbeitsstation-GC und Server-GC.</span><span class="sxs-lookup"><span data-stu-id="d4063-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="d4063-116">Weitere Informationen zu den Unterschieden zwischen diesen beiden Varianten finden Sie unter [Garbage Collection für die Arbeitsstation und Garbage Collection auf dem Server](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="d4063-116">For more information about differences between the two, see [Workstation and server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span>

<span data-ttu-id="d4063-117">Die Untervarianten der Garbage Collection sind Hintergrund-GC und nicht gleichzeitige GC.</span><span class="sxs-lookup"><span data-stu-id="d4063-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="d4063-118">Verwenden Sie die folgenden Einstellungen, um Varianten der Garbage Collection auszuwählen:</span><span class="sxs-lookup"><span data-stu-id="d4063-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="d4063-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="d4063-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="d4063-120">Konfiguriert, ob die Anwendung die Arbeitsstation-GC oder die Server-GC verwendet</span><span class="sxs-lookup"><span data-stu-id="d4063-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="d4063-121">Standard: Arbeitsstation-Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="d4063-121">Default: Workstation garbage collection.</span></span> <span data-ttu-id="d4063-122">Dies entspricht der Einstellung des Werts auf `false`.</span><span class="sxs-lookup"><span data-stu-id="d4063-122">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="d4063-123">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="d4063-123">Setting name</span></span> | <span data-ttu-id="d4063-124">Werte</span><span class="sxs-lookup"><span data-stu-id="d4063-124">Values</span></span> | <span data-ttu-id="d4063-125">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d4063-125">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d4063-126">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d4063-126">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="d4063-127">`false` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="d4063-127">`false` - workstation</span></span><br/><span data-ttu-id="d4063-128">`true` – Server</span><span class="sxs-lookup"><span data-stu-id="d4063-128">`true` - server</span></span> | <span data-ttu-id="d4063-129">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d4063-129">.NET Core 1.0</span></span> |
| <span data-ttu-id="d4063-130">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="d4063-130">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="d4063-131">`false` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="d4063-131">`false` - workstation</span></span><br/><span data-ttu-id="d4063-132">`true` – Server</span><span class="sxs-lookup"><span data-stu-id="d4063-132">`true` - server</span></span> | <span data-ttu-id="d4063-133">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d4063-133">.NET Core 1.0</span></span> |
| <span data-ttu-id="d4063-134">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="d4063-134">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="d4063-135">`0` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="d4063-135">`0` - workstation</span></span><br/><span data-ttu-id="d4063-136">`1` – Server</span><span class="sxs-lookup"><span data-stu-id="d4063-136">`1` - server</span></span> | <span data-ttu-id="d4063-137">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d4063-137">.NET Core 1.0</span></span> |
| <span data-ttu-id="d4063-138">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="d4063-138">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d4063-139">GCServer</span><span class="sxs-lookup"><span data-stu-id="d4063-139">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="d4063-140">`false` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="d4063-140">`false` - workstation</span></span><br/><span data-ttu-id="d4063-141">`true` – Server</span><span class="sxs-lookup"><span data-stu-id="d4063-141">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="d4063-142">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d4063-142">Examples</span></span>

<span data-ttu-id="d4063-143">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="d4063-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="d4063-144">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="d4063-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="d4063-145">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="d4063-145">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="d4063-146">Konfiguriert, ob die (gleichzeitige) Hintergrund-GC aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="d4063-146">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="d4063-147">Standard: Garbage Collection im Hintergrund verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4063-147">Default: Use background GC.</span></span> <span data-ttu-id="d4063-148">Dies entspricht der Einstellung des Werts auf `true`.</span><span class="sxs-lookup"><span data-stu-id="d4063-148">This is equivalent to setting the value to `true`.</span></span>
- <span data-ttu-id="d4063-149">Weitere Informationen finden Sie unter [Hintergrund der Garbage Collection](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="d4063-149">For more information, see [Background garbage collection](../../standard/garbage-collection/background-gc.md).</span></span>

| | <span data-ttu-id="d4063-150">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="d4063-150">Setting name</span></span> | <span data-ttu-id="d4063-151">Werte</span><span class="sxs-lookup"><span data-stu-id="d4063-151">Values</span></span> | <span data-ttu-id="d4063-152">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d4063-152">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d4063-153">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d4063-153">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="d4063-154">`true` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="d4063-154">`true` - background GC</span></span><br/><span data-ttu-id="d4063-155">`false` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="d4063-155">`false` - non-concurrent GC</span></span> | <span data-ttu-id="d4063-156">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d4063-156">.NET Core 1.0</span></span> |
| <span data-ttu-id="d4063-157">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="d4063-157">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="d4063-158">`true` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="d4063-158">`true` - background GC</span></span><br/><span data-ttu-id="d4063-159">`false` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="d4063-159">`false` - non-concurrent GC</span></span> | <span data-ttu-id="d4063-160">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d4063-160">.NET Core 1.0</span></span> |
| <span data-ttu-id="d4063-161">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="d4063-161">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="d4063-162">`1` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="d4063-162">`1` - background GC</span></span><br/><span data-ttu-id="d4063-163">`0` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="d4063-163">`0` - non-concurrent GC</span></span> | <span data-ttu-id="d4063-164">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d4063-164">.NET Core 1.0</span></span> |
| <span data-ttu-id="d4063-165">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="d4063-165">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d4063-166">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="d4063-166">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="d4063-167">`true` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="d4063-167">`true` - background GC</span></span><br/><span data-ttu-id="d4063-168">`false` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="d4063-168">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="d4063-169">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d4063-169">Examples</span></span>

<span data-ttu-id="d4063-170">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="d4063-170">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="d4063-171">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="d4063-171">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="d4063-172">Verwalten des Ressourceneinsatzes</span><span class="sxs-lookup"><span data-stu-id="d4063-172">Manage resource usage</span></span>

<span data-ttu-id="d4063-173">Verwenden Sie die in diesem Abschnitt beschriebenen Einstellungen, um die Speicher- und Prozessorauslastung des Garbage Collectors zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="d4063-173">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="d4063-174">Weitere Informationen zu einigen dieser Einstellungen finden Sie im Blogeintrag [Mittelweg zwischen Arbeitsstation- und Server-GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).</span><span class="sxs-lookup"><span data-stu-id="d4063-174">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="d4063-175">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="d4063-175">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="d4063-176">Schränkt die Anzahl von Heaps ein, die vom Garbage Collector erstellt werden</span><span class="sxs-lookup"><span data-stu-id="d4063-176">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="d4063-177">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="d4063-177">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="d4063-178">Wenn die [GC-Prozessoraffinität](#systemgcnoaffinitizecomplus_gcnoaffinitize) aktiviert ist (Standardeinstellung), ordnet die Einstellung für die Heapanzahl den ersten `n` Prozessoren `n` GC-Heaps/-Threads zu.</span><span class="sxs-lookup"><span data-stu-id="d4063-178">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="d4063-179">(Verwenden Sie die Einstellungen [AffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) oder [AffinitizeRanges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges), um genau anzugeben, welche Prozessoren zugeordnet werden sollen.)</span><span class="sxs-lookup"><span data-stu-id="d4063-179">(Use the [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) or [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="d4063-180">Wenn die [GC-Prozessoraffinität](#systemgcnoaffinitizecomplus_gcnoaffinitize) deaktiviert ist, wird mit dieser Einstellung die Anzahl der GC-Heaps eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="d4063-180">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="d4063-181">Weitere Informationen finden Sie unter [Hinweise zu GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="d4063-181">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="d4063-182">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="d4063-182">Setting name</span></span> | <span data-ttu-id="d4063-183">Werte</span><span class="sxs-lookup"><span data-stu-id="d4063-183">Values</span></span> | <span data-ttu-id="d4063-184">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d4063-184">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d4063-185">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d4063-185">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="d4063-186">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="d4063-186">*decimal value*</span></span> | <span data-ttu-id="d4063-187">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d4063-187">.NET Core 3.0</span></span> |
| <span data-ttu-id="d4063-188">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="d4063-188">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="d4063-189">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="d4063-189">*hexadecimal value*</span></span> | <span data-ttu-id="d4063-190">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d4063-190">.NET Core 3.0</span></span> |
| <span data-ttu-id="d4063-191">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="d4063-191">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d4063-192">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="d4063-192">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="d4063-193">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="d4063-193">*decimal value*</span></span> | <span data-ttu-id="d4063-194">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="d4063-194">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="d4063-195">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d4063-195">Example:</span></span>

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
> <span data-ttu-id="d4063-196">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="d4063-196">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="d4063-197">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="d4063-197">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="d4063-198">Für eine Einschränkung der Heapanzahl auf 16 wären die Werte beispielsweise 16 für die JSON-Datei und 0x10 oder 10 für die Umgebungsvariable.</span><span class="sxs-lookup"><span data-stu-id="d4063-198">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="d4063-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="d4063-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="d4063-200">Gibt die genauen Prozessoren an, die Garbage-Collector-Threads verwenden sollen</span><span class="sxs-lookup"><span data-stu-id="d4063-200">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="d4063-201">Wenn die [GC-Prozessoraffinität](#systemgcnoaffinitizecomplus_gcnoaffinitize) deaktiviert ist, wird diese Einstellung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d4063-201">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="d4063-202">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="d4063-202">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="d4063-203">Der Wert ist eine Bitmaske, die die für den Prozess verfügbaren Prozessoren definiert.</span><span class="sxs-lookup"><span data-stu-id="d4063-203">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="d4063-204">Beispielsweise ist ein Dezimalwert von 1023 (oder ein Hexadezimalwert von 0x3FF oder 3FF bei Verwendung der Umgebungsvariablen) in Binärschreibweise 0011 1111 1111.</span><span class="sxs-lookup"><span data-stu-id="d4063-204">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="d4063-205">Dies gibt an, dass die ersten zehn Prozessoren verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d4063-205">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="d4063-206">Geben Sie einen Dezimalwert von 1047552 (oder einen Hexadezimalwert von 0xFFC00 oder FFC00) an, der einem Binärwert von 1111 1111 1100 0000 0000 entspricht, um die nächsten zehn Prozessoren anzugeben, d. h. die Prozessoren 10 bis 19.</span><span class="sxs-lookup"><span data-stu-id="d4063-206">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="d4063-207">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="d4063-207">Setting name</span></span> | <span data-ttu-id="d4063-208">Werte</span><span class="sxs-lookup"><span data-stu-id="d4063-208">Values</span></span> | <span data-ttu-id="d4063-209">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d4063-209">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d4063-210">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d4063-210">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="d4063-211">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="d4063-211">*decimal value*</span></span> | <span data-ttu-id="d4063-212">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d4063-212">.NET Core 3.0</span></span> |
| <span data-ttu-id="d4063-213">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="d4063-213">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="d4063-214">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="d4063-214">*hexadecimal value*</span></span> | <span data-ttu-id="d4063-215">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d4063-215">.NET Core 3.0</span></span> |
| <span data-ttu-id="d4063-216">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="d4063-216">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d4063-217">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="d4063-217">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="d4063-218">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="d4063-218">*decimal value*</span></span> | <span data-ttu-id="d4063-219">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="d4063-219">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="d4063-220">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d4063-220">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="d4063-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="d4063-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="d4063-222">Gibt die Liste der Prozessoren an, die für Garbage-Collector-Threads verwendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="d4063-222">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="d4063-223">Diese Einstellung ähnelt [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), abgesehen davon, dass Sie mehr als 64 Prozessoren angeben können.</span><span class="sxs-lookup"><span data-stu-id="d4063-223">This setting is similar to [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="d4063-224">Stellen Sie für Windows-Betriebssysteme der Prozessornummer oder dem Prozessorbereich die entsprechende [CPU-Gruppe](/windows/win32/procthread/processor-groups) voran, z. B. „0:1-10,0:12,1:50-52,1:70“.</span><span class="sxs-lookup"><span data-stu-id="d4063-224">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="d4063-225">Wenn die [GC-Prozessoraffinität](#systemgcnoaffinitizecomplus_gcnoaffinitize) deaktiviert ist, wird diese Einstellung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d4063-225">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="d4063-226">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="d4063-226">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="d4063-227">Weitere Informationen finden Sie unter [Optimieren der CPU-Konfiguration für GC auf Computern mit mehr als 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) im Blog von Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="d4063-227">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="d4063-228">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="d4063-228">Setting name</span></span> | <span data-ttu-id="d4063-229">Werte</span><span class="sxs-lookup"><span data-stu-id="d4063-229">Values</span></span> | <span data-ttu-id="d4063-230">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d4063-230">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d4063-231">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d4063-231">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="d4063-232">Durch Kommas getrennte Liste mit Prozessornummern oder Bereichen von Prozessornummern</span><span class="sxs-lookup"><span data-stu-id="d4063-232">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="d4063-233">Unix-Beispiel: „1-10,12,50-52,70“</span><span class="sxs-lookup"><span data-stu-id="d4063-233">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="d4063-234">Windows-Beispiel: „0:1-10,0:12,1:50-52,1:70“</span><span class="sxs-lookup"><span data-stu-id="d4063-234">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="d4063-235">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d4063-235">.NET Core 3.0</span></span> |
| <span data-ttu-id="d4063-236">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="d4063-236">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="d4063-237">Durch Kommas getrennte Liste mit Prozessornummern oder Bereichen von Prozessornummern</span><span class="sxs-lookup"><span data-stu-id="d4063-237">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="d4063-238">Unix-Beispiel: „1-10,12,50-52,70“</span><span class="sxs-lookup"><span data-stu-id="d4063-238">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="d4063-239">Windows-Beispiel: „0:1-10,0:12,1:50-52,1:70“</span><span class="sxs-lookup"><span data-stu-id="d4063-239">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="d4063-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d4063-240">.NET Core 3.0</span></span> |

<span data-ttu-id="d4063-241">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d4063-241">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="d4063-242">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="d4063-242">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="d4063-243">Konfiguriert, ob der Garbage Collector [CPU-Gruppen](/windows/win32/procthread/processor-groups) verwendet</span><span class="sxs-lookup"><span data-stu-id="d4063-243">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="d4063-244">Wenn ein 64-Bit-Windows-Computer über mehrere CPU-Gruppen verfügt, d. h. mehr als 64 Prozessoren vorhanden sind, dann wird durch die Aktivierung dieses Elements die Garbage Collection in allen CPU-Gruppen erweitert.</span><span class="sxs-lookup"><span data-stu-id="d4063-244">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="d4063-245">Der Garbage Collector verwendet alle Kerne zum Erstellen und Ausgleichen von Heaps.</span><span class="sxs-lookup"><span data-stu-id="d4063-245">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="d4063-246">Gilt nur für Garbage Collection des Servers auf 64-Bit-Windows-Betriebssystemen.</span><span class="sxs-lookup"><span data-stu-id="d4063-246">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="d4063-247">Standard: GC wird nicht über CPU-Gruppen hinweg erweitert.</span><span class="sxs-lookup"><span data-stu-id="d4063-247">Default: GC does not extend across CPU groups.</span></span> <span data-ttu-id="d4063-248">Dies entspricht der Einstellung des Werts auf `0`.</span><span class="sxs-lookup"><span data-stu-id="d4063-248">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="d4063-249">Weitere Informationen finden Sie unter [Optimieren der CPU-Konfiguration für GC auf Computern mit mehr als 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) im Blog von Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="d4063-249">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="d4063-250">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="d4063-250">Setting name</span></span> | <span data-ttu-id="d4063-251">Werte</span><span class="sxs-lookup"><span data-stu-id="d4063-251">Values</span></span> | <span data-ttu-id="d4063-252">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d4063-252">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d4063-253">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d4063-253">**runtimeconfig.json**</span></span> | <span data-ttu-id="d4063-254">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d4063-254">N/A</span></span> | <span data-ttu-id="d4063-255">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d4063-255">N/A</span></span> | <span data-ttu-id="d4063-256">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d4063-256">N/A</span></span> |
| <span data-ttu-id="d4063-257">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="d4063-257">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="d4063-258">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="d4063-258">`0` - disabled</span></span><br/><span data-ttu-id="d4063-259">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="d4063-259">`1` - enabled</span></span> | <span data-ttu-id="d4063-260">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d4063-260">.NET Core 1.0</span></span> |
| <span data-ttu-id="d4063-261">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="d4063-261">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d4063-262">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="d4063-262">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="d4063-263">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="d4063-263">`false` - disabled</span></span><br/><span data-ttu-id="d4063-264">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="d4063-264">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="d4063-265">Aktivieren Sie die Option [Thread_UseAllCpuGroups-Element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md), um die Common Language Runtime (CLR) so zu konfigurieren, dass auch Threads aus dem Threadpool in allen CPU-Gruppen verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="d4063-265">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="d4063-266">Für .NET Core-Apps können Sie diese Option aktivieren, indem Sie den Wert der Umgebungsvariablen `COMPlus_Thread_UseAllCpuGroups` auf `1` setzen.</span><span class="sxs-lookup"><span data-stu-id="d4063-266">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="d4063-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="d4063-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="d4063-268">Gibt an, ob Garbage-Collection-Threads Prozessoren *zugeordnet* werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d4063-268">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="d4063-269">Einen GC-Thread zuzuordnen, bedeutet, dass dieser nur auf der jeweiligen CPU ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d4063-269">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="d4063-270">Für jeden GC-Thread wird ein Heap erstellt.</span><span class="sxs-lookup"><span data-stu-id="d4063-270">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="d4063-271">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="d4063-271">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="d4063-272">Standard: Garbage Collection-Threads werden Prozessoren zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d4063-272">Default: Affinitize garbage collection threads with processors.</span></span> <span data-ttu-id="d4063-273">Dies entspricht der Einstellung des Werts auf `false`.</span><span class="sxs-lookup"><span data-stu-id="d4063-273">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="d4063-274">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="d4063-274">Setting name</span></span> | <span data-ttu-id="d4063-275">Werte</span><span class="sxs-lookup"><span data-stu-id="d4063-275">Values</span></span> | <span data-ttu-id="d4063-276">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d4063-276">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d4063-277">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d4063-277">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="d4063-278">`false` – zuordnen</span><span class="sxs-lookup"><span data-stu-id="d4063-278">`false` - affinitize</span></span><br/><span data-ttu-id="d4063-279">`true` – nicht zuordnen</span><span class="sxs-lookup"><span data-stu-id="d4063-279">`true` - don't affinitize</span></span> | <span data-ttu-id="d4063-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d4063-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="d4063-281">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="d4063-281">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="d4063-282">`0` – zuordnen</span><span class="sxs-lookup"><span data-stu-id="d4063-282">`0` - affinitize</span></span><br/><span data-ttu-id="d4063-283">`1` – nicht zuordnen</span><span class="sxs-lookup"><span data-stu-id="d4063-283">`1` - don't affinitize</span></span> | <span data-ttu-id="d4063-284">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d4063-284">.NET Core 3.0</span></span> |
| <span data-ttu-id="d4063-285">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="d4063-285">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d4063-286">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="d4063-286">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="d4063-287">`false` – zuordnen</span><span class="sxs-lookup"><span data-stu-id="d4063-287">`false` - affinitize</span></span><br/><span data-ttu-id="d4063-288">`true` – nicht zuordnen</span><span class="sxs-lookup"><span data-stu-id="d4063-288">`true` - don't affinitize</span></span> | <span data-ttu-id="d4063-289">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="d4063-289">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="d4063-290">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d4063-290">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="d4063-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="d4063-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="d4063-292">Gibt die maximale Commitgröße in Bytes für den GC-Heap und die GC-Buchhaltung an</span><span class="sxs-lookup"><span data-stu-id="d4063-292">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="d4063-293">Diese Einstellung gilt nur für 64-Bit-Computer.</span><span class="sxs-lookup"><span data-stu-id="d4063-293">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="d4063-294">Der Standardwert, der nur in bestimmten Fällen gilt, ist der größere Wert von 20 MB oder 75 % der Speichergrenze für den Container.</span><span class="sxs-lookup"><span data-stu-id="d4063-294">The default value, which only applies in certain cases, is the greater of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="d4063-295">Der Standardwert wird in folgenden Fällen angewendet:</span><span class="sxs-lookup"><span data-stu-id="d4063-295">The default value applies if:</span></span>

  - <span data-ttu-id="d4063-296">Der Prozess wird in einem Container ausgeführt, für den ein Arbeitsspeicherlimit angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="d4063-296">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="d4063-297">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) ist nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d4063-297">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) is not set.</span></span>

| | <span data-ttu-id="d4063-298">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="d4063-298">Setting name</span></span> | <span data-ttu-id="d4063-299">Werte</span><span class="sxs-lookup"><span data-stu-id="d4063-299">Values</span></span> | <span data-ttu-id="d4063-300">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d4063-300">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d4063-301">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d4063-301">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="d4063-302">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="d4063-302">*decimal value*</span></span> | <span data-ttu-id="d4063-303">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d4063-303">.NET Core 3.0</span></span> |
| <span data-ttu-id="d4063-304">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="d4063-304">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="d4063-305">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="d4063-305">*hexadecimal value*</span></span> | <span data-ttu-id="d4063-306">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d4063-306">.NET Core 3.0</span></span> |

<span data-ttu-id="d4063-307">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d4063-307">Example:</span></span>

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
> <span data-ttu-id="d4063-308">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="d4063-308">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="d4063-309">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="d4063-309">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="d4063-310">Wenn Sie beispielsweise eine feste Heapgrenze von 200 MiB festlegen, würden die Werte für die JSON-Datei 209715200 und für die Umgebungsvariable 0xc800000 oder C800000 betragen.</span><span class="sxs-lookup"><span data-stu-id="d4063-310">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="d4063-311">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="d4063-311">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="d4063-312">Gibt den zulässigen GC-Heapverbrauch in Prozent des gesamten physischen Speichers an.</span><span class="sxs-lookup"><span data-stu-id="d4063-312">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="d4063-313">Wenn außerdem [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) festgelegt ist, wird diese Einstellung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d4063-313">If [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="d4063-314">Diese Einstellung gilt nur für 64-Bit-Computer.</span><span class="sxs-lookup"><span data-stu-id="d4063-314">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="d4063-315">Wenn der Prozess in einem Container ausgeführt, für den ein Arbeitsspeicherlimit angegeben wurde, wird der Prozentsatz als Prozentsatz dieses Arbeitsspeicherlimits berechnet.</span><span class="sxs-lookup"><span data-stu-id="d4063-315">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="d4063-316">Der Standardwert, der nur in bestimmten Fällen angewendet wird, beträgt weniger als 20 MB oder 75 % des Arbeitsspeicherlimits für den Container.</span><span class="sxs-lookup"><span data-stu-id="d4063-316">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="d4063-317">Der Standardwert wird in folgenden Fällen angewendet:</span><span class="sxs-lookup"><span data-stu-id="d4063-317">The default value applies if:</span></span>

  - <span data-ttu-id="d4063-318">Der Prozess wird in einem Container ausgeführt, für den ein Arbeitsspeicherlimit angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="d4063-318">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="d4063-319">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) ist nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d4063-319">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is not set.</span></span>

| | <span data-ttu-id="d4063-320">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="d4063-320">Setting name</span></span> | <span data-ttu-id="d4063-321">Werte</span><span class="sxs-lookup"><span data-stu-id="d4063-321">Values</span></span> | <span data-ttu-id="d4063-322">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d4063-322">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d4063-323">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d4063-323">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="d4063-324">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="d4063-324">*decimal value*</span></span> | <span data-ttu-id="d4063-325">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d4063-325">.NET Core 3.0</span></span> |
| <span data-ttu-id="d4063-326">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="d4063-326">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="d4063-327">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="d4063-327">*hexadecimal value*</span></span> | <span data-ttu-id="d4063-328">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d4063-328">.NET Core 3.0</span></span> |

<span data-ttu-id="d4063-329">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d4063-329">Example:</span></span>

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
> <span data-ttu-id="d4063-330">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="d4063-330">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="d4063-331">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="d4063-331">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="d4063-332">Beispielsweise würden bei einer Begrenzung des Heapverbrauchs auf 30 % die Werte für die JSON-Datei 30 und für die Umgebungsvariable 0x1E oder 1E betragen.</span><span class="sxs-lookup"><span data-stu-id="d4063-332">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="d4063-333">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="d4063-333">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="d4063-334">Konfiguriert, ob Segmente, die gelöscht werden sollen, zur späteren Verwendung auf eine Standbyliste aufgenommen oder an das Betriebssystem zurückgegeben werden</span><span class="sxs-lookup"><span data-stu-id="d4063-334">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="d4063-335">Standard: Segmente werden an das Betriebssystem zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d4063-335">Default: Release segments back to the operating system.</span></span> <span data-ttu-id="d4063-336">Dies entspricht der Einstellung des Werts auf `false`.</span><span class="sxs-lookup"><span data-stu-id="d4063-336">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="d4063-337">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="d4063-337">Setting name</span></span> | <span data-ttu-id="d4063-338">Werte</span><span class="sxs-lookup"><span data-stu-id="d4063-338">Values</span></span> | <span data-ttu-id="d4063-339">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d4063-339">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d4063-340">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d4063-340">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="d4063-341">`false` – Freigabe an Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="d4063-341">`false` - release to OS</span></span><br/><span data-ttu-id="d4063-342">`true` – in Standbymodus versetzen</span><span class="sxs-lookup"><span data-stu-id="d4063-342">`true` - put on standby</span></span> | <span data-ttu-id="d4063-343">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d4063-343">.NET Core 1.0</span></span> |
| <span data-ttu-id="d4063-344">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="d4063-344">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="d4063-345">`false` – Freigabe an Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="d4063-345">`false` - release to OS</span></span><br/><span data-ttu-id="d4063-346">`true` – in Standbymodus versetzen</span><span class="sxs-lookup"><span data-stu-id="d4063-346">`true` - put on standby</span></span> | <span data-ttu-id="d4063-347">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d4063-347">.NET Core 1.0</span></span> |
| <span data-ttu-id="d4063-348">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="d4063-348">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="d4063-349">`0` – Freigabe an Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="d4063-349">`0` - release to OS</span></span><br/><span data-ttu-id="d4063-350">`1` – in Standbymodus versetzen</span><span class="sxs-lookup"><span data-stu-id="d4063-350">`1` - put on standby</span></span> | <span data-ttu-id="d4063-351">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d4063-351">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="d4063-352">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d4063-352">Examples</span></span>

<span data-ttu-id="d4063-353">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="d4063-353">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="d4063-354">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="d4063-354">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="d4063-355">Umfangreiche Seiten</span><span class="sxs-lookup"><span data-stu-id="d4063-355">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="d4063-356">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="d4063-356">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="d4063-357">Gibt an, ob umfangreiche Seiten verwendet werden sollen, wenn eine feste Heapgrenze festgelegt wird</span><span class="sxs-lookup"><span data-stu-id="d4063-357">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="d4063-358">Standard: Verwenden Sie keine großen Seiten, wenn eine feste Heapgrenze festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d4063-358">Default: Don't use large pages when a heap hard limit is set.</span></span> <span data-ttu-id="d4063-359">Dies entspricht der Einstellung des Werts auf `0`.</span><span class="sxs-lookup"><span data-stu-id="d4063-359">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="d4063-360">Dies ist eine experimentelle Einstellung.</span><span class="sxs-lookup"><span data-stu-id="d4063-360">This is an experimental setting.</span></span>

| | <span data-ttu-id="d4063-361">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="d4063-361">Setting name</span></span> | <span data-ttu-id="d4063-362">Werte</span><span class="sxs-lookup"><span data-stu-id="d4063-362">Values</span></span> | <span data-ttu-id="d4063-363">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d4063-363">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d4063-364">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d4063-364">**runtimeconfig.json**</span></span> | <span data-ttu-id="d4063-365">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d4063-365">N/A</span></span> | <span data-ttu-id="d4063-366">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d4063-366">N/A</span></span> | <span data-ttu-id="d4063-367">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d4063-367">N/A</span></span> |
| <span data-ttu-id="d4063-368">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="d4063-368">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="d4063-369">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="d4063-369">`0` - disabled</span></span><br/><span data-ttu-id="d4063-370">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="d4063-370">`1` - enabled</span></span> | <span data-ttu-id="d4063-371">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d4063-371">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="d4063-372">Große Objekte</span><span class="sxs-lookup"><span data-stu-id="d4063-372">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="d4063-373">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="d4063-373">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="d4063-374">Konfiguriert die Garbage-Collector-Unterstützung auf 64-Bit-Plattformen für Arrays mit einer Gesamtgröße von mehr als 2 Gigabytes (GB)</span><span class="sxs-lookup"><span data-stu-id="d4063-374">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="d4063-375">Standard: GC unterstützt Arrays, die größer als 2 GB sind.</span><span class="sxs-lookup"><span data-stu-id="d4063-375">Default: GC supports arrays greater than 2-GB.</span></span> <span data-ttu-id="d4063-376">Dies entspricht der Einstellung des Werts auf `1`.</span><span class="sxs-lookup"><span data-stu-id="d4063-376">This is equivalent to setting the value to `1`.</span></span>
- <span data-ttu-id="d4063-377">Diese Option wird in einer zukünftigen Version von .NET möglicherweise veraltet sein.</span><span class="sxs-lookup"><span data-stu-id="d4063-377">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="d4063-378">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="d4063-378">Setting name</span></span> | <span data-ttu-id="d4063-379">Werte</span><span class="sxs-lookup"><span data-stu-id="d4063-379">Values</span></span> | <span data-ttu-id="d4063-380">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d4063-380">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d4063-381">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d4063-381">**runtimeconfig.json**</span></span> | <span data-ttu-id="d4063-382">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d4063-382">N/A</span></span> | <span data-ttu-id="d4063-383">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d4063-383">N/A</span></span> | <span data-ttu-id="d4063-384">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d4063-384">N/A</span></span> |
| <span data-ttu-id="d4063-385">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="d4063-385">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="d4063-386">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="d4063-386">`1` - enabled</span></span><br/> <span data-ttu-id="d4063-387">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="d4063-387">`0` - disabled</span></span> | <span data-ttu-id="d4063-388">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d4063-388">.NET Core 1.0</span></span> |
| <span data-ttu-id="d4063-389">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="d4063-389">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d4063-390">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="d4063-390">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="d4063-391">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="d4063-391">`1` - enabled</span></span><br/> <span data-ttu-id="d4063-392">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="d4063-392">`0` - disabled</span></span> | <span data-ttu-id="d4063-393">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="d4063-393">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="d4063-394">Großer Objektheapschwellenwert</span><span class="sxs-lookup"><span data-stu-id="d4063-394">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="d4063-395">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="d4063-395">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="d4063-396">Gibt die Größe des Schwellenwerts in Bytes an, der bewirkt, dass Objekte auf den großen Objektheap (Large Object Heap, LOH) gehen</span><span class="sxs-lookup"><span data-stu-id="d4063-396">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="d4063-397">Der Standardschwellenwert beträgt 85.000 Bytes.</span><span class="sxs-lookup"><span data-stu-id="d4063-397">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="d4063-398">Der von Ihnen festgelegte Wert muss größer sein als der Standardschwellenwert.</span><span class="sxs-lookup"><span data-stu-id="d4063-398">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="d4063-399">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="d4063-399">Setting name</span></span> | <span data-ttu-id="d4063-400">Werte</span><span class="sxs-lookup"><span data-stu-id="d4063-400">Values</span></span> | <span data-ttu-id="d4063-401">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d4063-401">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d4063-402">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d4063-402">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="d4063-403">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="d4063-403">*decimal value*</span></span> | <span data-ttu-id="d4063-404">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d4063-404">.NET Core 1.0</span></span> |
| <span data-ttu-id="d4063-405">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="d4063-405">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="d4063-406">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="d4063-406">*hexadecimal value*</span></span> | <span data-ttu-id="d4063-407">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d4063-407">.NET Core 1.0</span></span> |
| <span data-ttu-id="d4063-408">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="d4063-408">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d4063-409">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="d4063-409">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="d4063-410">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="d4063-410">*decimal value*</span></span> | <span data-ttu-id="d4063-411">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="d4063-411">.NET Framework 4.8</span></span> |

<span data-ttu-id="d4063-412">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d4063-412">Example:</span></span>

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
> <span data-ttu-id="d4063-413">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="d4063-413">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="d4063-414">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="d4063-414">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="d4063-415">Wenn Sie beispielsweise die Größe eines Schwellenwerts auf 120.000 Bytes festlegen, würden die Werte für die JSON-Datei 120000 und für die Umgebungsvariable 0x1D4C0 oder 1D4C0 betragen.</span><span class="sxs-lookup"><span data-stu-id="d4063-415">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="d4063-416">Eigenständige GC</span><span class="sxs-lookup"><span data-stu-id="d4063-416">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="d4063-417">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="d4063-417">COMPlus_GCName</span></span>

- <span data-ttu-id="d4063-418">Gibt einen Pfad zu der Bibliothek an, die den Garbage Collector enthält, der von der Runtime geladen werden soll</span><span class="sxs-lookup"><span data-stu-id="d4063-418">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="d4063-419">Weitere Informationen finden Sie unter [Entwurf eines eigenständigen GC-Ladeprogramms](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="d4063-419">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="d4063-420">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="d4063-420">Setting name</span></span> | <span data-ttu-id="d4063-421">Werte</span><span class="sxs-lookup"><span data-stu-id="d4063-421">Values</span></span> | <span data-ttu-id="d4063-422">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d4063-422">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d4063-423">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d4063-423">**runtimeconfig.json**</span></span> | <span data-ttu-id="d4063-424">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d4063-424">N/A</span></span> | <span data-ttu-id="d4063-425">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d4063-425">N/A</span></span> | <span data-ttu-id="d4063-426">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d4063-426">N/A</span></span> |
| <span data-ttu-id="d4063-427">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="d4063-427">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="d4063-428">*string_path*</span><span class="sxs-lookup"><span data-stu-id="d4063-428">*string_path*</span></span> | <span data-ttu-id="d4063-429">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="d4063-429">.NET Core 2.0</span></span> |
