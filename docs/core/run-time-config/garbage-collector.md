---
title: Garbage-Collector-Konfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, um zu konfigurieren, wie der Garbage Collector Arbeitsspeicher für .NET Core-Apps verwaltet.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: 044083d69601f5092724a46d358b2ee5673d428d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "76733516"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="e56f5-103">Laufzeitkonfigurationsoptionen für die Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="e56f5-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="e56f5-104">Diese Seite enthält Informationen zu Garbage-Collector-Einstellungen (GC), die zur Laufzeit geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="e56f5-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="e56f5-105">Verwenden Sie diese Einstellungen, wenn Sie versuchen, die maximale Leistung einer ausgeführten App zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="e56f5-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="e56f5-106">Die Standardwerte bieten jedoch in typischen Situationen eine optimale Leistung für die meisten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="e56f5-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="e56f5-107">Einstellungen werden auf dieser Seite in Gruppen angeordnet.</span><span class="sxs-lookup"><span data-stu-id="e56f5-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="e56f5-108">Die Einstellungen in den einzelnen Gruppen werden häufig zusammen verwendet, um ein bestimmtes Ergebnis zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="e56f5-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="e56f5-109">Diese Einstellungen können auch dynamisch von der App geändert werden, während diese ausgeführt wird, sodass die von Ihnen festgelegten Laufzeiteinstellungen überschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="e56f5-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="e56f5-110">Einige Einstellungen, wie z. B. die [Latenzebene](../../standard/garbage-collection/latency.md), werden in der Regel nur über die API zur Entwurfszeit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e56f5-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="e56f5-111">Diese Einstellungen werden auf dieser Seite weggelassen.</span><span class="sxs-lookup"><span data-stu-id="e56f5-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="e56f5-112">Verwenden Sie für Zahlenwerte für Einstellungen in der Datei *runtimeconfig.json* die Dezimalschreibweise und für Einstellungen in der Umgebungsvariablen die Hexadezimalnotation.</span><span class="sxs-lookup"><span data-stu-id="e56f5-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="e56f5-113">Bei hexadezimalen Werten können Sie sie mit dem oder ohne das Präfix „0x“ angeben.</span><span class="sxs-lookup"><span data-stu-id="e56f5-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="e56f5-114">Varianten der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="e56f5-114">Flavors of garbage collection</span></span>

<span data-ttu-id="e56f5-115">Die zwei Hauptvarianten der Garbage Collection sind Arbeitsstation-GC und Server-GC.</span><span class="sxs-lookup"><span data-stu-id="e56f5-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="e56f5-116">Weitere Informationen zu den Unterschieden zwischen diesen beiden Varianten finden Sie unter [Grundlagen der Garbage Collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="e56f5-116">For more information about differences between the two, see [Fundamentals of garbage collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span></span>

<span data-ttu-id="e56f5-117">Die Untervarianten der Garbage Collection sind Hintergrund-GC und nicht gleichzeitige GC.</span><span class="sxs-lookup"><span data-stu-id="e56f5-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="e56f5-118">Verwenden Sie die folgenden Einstellungen, um Varianten der Garbage Collection auszuwählen:</span><span class="sxs-lookup"><span data-stu-id="e56f5-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="e56f5-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="e56f5-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="e56f5-120">Konfiguriert, ob die Anwendung die Arbeitsstation-GC oder die Server-GC verwendet</span><span class="sxs-lookup"><span data-stu-id="e56f5-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="e56f5-121">Standard: Arbeitsstation-Garbage-Collection (`false`)</span><span class="sxs-lookup"><span data-stu-id="e56f5-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="e56f5-122">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="e56f5-122">Setting name</span></span> | <span data-ttu-id="e56f5-123">Werte</span><span class="sxs-lookup"><span data-stu-id="e56f5-123">Values</span></span> | <span data-ttu-id="e56f5-124">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e56f5-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="e56f5-125">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e56f5-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="e56f5-126">`false` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="e56f5-126">`false` - workstation</span></span><br/><span data-ttu-id="e56f5-127">`true` – Server</span><span class="sxs-lookup"><span data-stu-id="e56f5-127">`true` - server</span></span> | <span data-ttu-id="e56f5-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="e56f5-129">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="e56f5-129">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="e56f5-130">`false` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="e56f5-130">`false` - workstation</span></span><br/><span data-ttu-id="e56f5-131">`true` – Server</span><span class="sxs-lookup"><span data-stu-id="e56f5-131">`true` - server</span></span> | <span data-ttu-id="e56f5-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="e56f5-133">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="e56f5-133">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="e56f5-134">`0` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="e56f5-134">`0` - workstation</span></span><br/><span data-ttu-id="e56f5-135">`1` – Server</span><span class="sxs-lookup"><span data-stu-id="e56f5-135">`1` - server</span></span> | <span data-ttu-id="e56f5-136">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-136">.NET Core 1.0</span></span> |
| <span data-ttu-id="e56f5-137">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="e56f5-137">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="e56f5-138">GCServer</span><span class="sxs-lookup"><span data-stu-id="e56f5-138">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="e56f5-139">`false` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="e56f5-139">`false` - workstation</span></span><br/><span data-ttu-id="e56f5-140">`true` – Server</span><span class="sxs-lookup"><span data-stu-id="e56f5-140">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="e56f5-141">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e56f5-141">Examples</span></span>

<span data-ttu-id="e56f5-142">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="e56f5-142">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="e56f5-143">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="e56f5-143">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="e56f5-144">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="e56f5-144">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="e56f5-145">Konfiguriert, ob die (gleichzeitige) Hintergrund-GC aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="e56f5-145">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="e56f5-146">Standard: Aktiviert (`true`)</span><span class="sxs-lookup"><span data-stu-id="e56f5-146">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="e56f5-147">Weitere Informationen finden Sie unter [Garbage Collection im Hintergrund](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) und [Garbage Collection auf dem Server im Hintergrund](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="e56f5-147">For more information, see [Background garbage collection](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) and [Background server garbage collection](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span></span>

| | <span data-ttu-id="e56f5-148">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="e56f5-148">Setting name</span></span> | <span data-ttu-id="e56f5-149">Werte</span><span class="sxs-lookup"><span data-stu-id="e56f5-149">Values</span></span> | <span data-ttu-id="e56f5-150">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e56f5-150">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="e56f5-151">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e56f5-151">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="e56f5-152">`true` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="e56f5-152">`true` - background GC</span></span><br/><span data-ttu-id="e56f5-153">`false` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="e56f5-153">`false` - non-concurrent GC</span></span> | <span data-ttu-id="e56f5-154">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-154">.NET Core 1.0</span></span> |
| <span data-ttu-id="e56f5-155">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="e56f5-155">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="e56f5-156">`true` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="e56f5-156">`true` - background GC</span></span><br/><span data-ttu-id="e56f5-157">`false` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="e56f5-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="e56f5-158">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="e56f5-159">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="e56f5-159">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="e56f5-160">`true` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="e56f5-160">`true` - background GC</span></span><br/><span data-ttu-id="e56f5-161">`false` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="e56f5-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="e56f5-162">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="e56f5-163">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="e56f5-163">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="e56f5-164">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="e56f5-164">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="e56f5-165">`true` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="e56f5-165">`true` - background GC</span></span><br/><span data-ttu-id="e56f5-166">`false` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="e56f5-166">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="e56f5-167">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e56f5-167">Examples</span></span>

<span data-ttu-id="e56f5-168">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="e56f5-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="e56f5-169">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="e56f5-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="e56f5-170">Verwalten des Ressourceneinsatzes</span><span class="sxs-lookup"><span data-stu-id="e56f5-170">Manage resource usage</span></span>

<span data-ttu-id="e56f5-171">Verwenden Sie die in diesem Abschnitt beschriebenen Einstellungen, um die Speicher- und Prozessorauslastung des Garbage Collectors zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="e56f5-171">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="e56f5-172">Weitere Informationen zu einigen dieser Einstellungen finden Sie im Blogeintrag [Mittelweg zwischen Arbeitsstation- und Server-GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).</span><span class="sxs-lookup"><span data-stu-id="e56f5-172">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="e56f5-173">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="e56f5-173">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="e56f5-174">Schränkt die Anzahl von Heaps ein, die vom Garbage Collector erstellt werden</span><span class="sxs-lookup"><span data-stu-id="e56f5-174">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="e56f5-175">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="e56f5-175">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="e56f5-176">Wenn die GC-Prozessoraffinität aktiviert ist (Standardeinstellung), ordnet die Einstellung für die Heapanzahl den ersten `n` Prozessoren `n` GC-Heaps/-Threads zu.</span><span class="sxs-lookup"><span data-stu-id="e56f5-176">If GC processor affinity is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="e56f5-177">(Verwenden Sie die Einstellungen „affinitize mask“ (Maske zuordnen) oder „affinitize ranges“ (Bereiche zuordnen), um genau anzugeben, welche Prozessoren zugeordnet werden sollen.)</span><span class="sxs-lookup"><span data-stu-id="e56f5-177">(Use the affinitize mask or affinitize ranges settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="e56f5-178">Wenn die GC-Prozessoraffinität deaktiviert ist, wird mit dieser Einstellung die Anzahl der GC-Heaps eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="e56f5-178">If GC processor affinity is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="e56f5-179">Weitere Informationen finden Sie unter [Hinweise zu GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="e56f5-179">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="e56f5-180">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="e56f5-180">Setting name</span></span> | <span data-ttu-id="e56f5-181">Werte</span><span class="sxs-lookup"><span data-stu-id="e56f5-181">Values</span></span> | <span data-ttu-id="e56f5-182">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e56f5-182">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="e56f5-183">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e56f5-183">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="e56f5-184">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="e56f5-184">*decimal value*</span></span> | <span data-ttu-id="e56f5-185">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-185">.NET Core 3.0</span></span> |
| <span data-ttu-id="e56f5-186">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="e56f5-186">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="e56f5-187">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="e56f5-187">*hexadecimal value*</span></span> | <span data-ttu-id="e56f5-188">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-188">.NET Core 3.0</span></span> |
| <span data-ttu-id="e56f5-189">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="e56f5-189">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="e56f5-190">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="e56f5-190">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="e56f5-191">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="e56f5-191">*decimal value*</span></span> | <span data-ttu-id="e56f5-192">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="e56f5-192">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="e56f5-193">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e56f5-193">Example:</span></span>

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
> <span data-ttu-id="e56f5-194">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="e56f5-194">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="e56f5-195">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="e56f5-195">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="e56f5-196">Für eine Einschränkung der Heapanzahl auf 16 wären die Werte beispielsweise 16 für die JSON-Datei und 0x10 oder 10 für die Umgebungsvariable.</span><span class="sxs-lookup"><span data-stu-id="e56f5-196">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="e56f5-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="e56f5-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="e56f5-198">Gibt die genauen Prozessoren an, die Garbage-Collector-Threads verwenden sollen</span><span class="sxs-lookup"><span data-stu-id="e56f5-198">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="e56f5-199">Wenn die Prozessoraffinität deaktiviert ist, indem `System.GC.NoAffinitize` auf `true` festgelegt wurde, wird diese Einstellung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="e56f5-199">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="e56f5-200">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="e56f5-200">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="e56f5-201">Der Wert ist eine Bitmaske, die die für den Prozess verfügbaren Prozessoren definiert.</span><span class="sxs-lookup"><span data-stu-id="e56f5-201">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="e56f5-202">Beispielsweise ist ein Dezimalwert von 1023 (oder ein Hexadezimalwert von 0x3FF oder 3FF bei Verwendung der Umgebungsvariablen) in Binärschreibweise 0011 1111 1111.</span><span class="sxs-lookup"><span data-stu-id="e56f5-202">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="e56f5-203">Dies gibt an, dass die ersten zehn Prozessoren verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e56f5-203">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="e56f5-204">Geben Sie einen Dezimalwert von 1047552 (oder einen Hexadezimalwert von 0xFFC00 oder FFC00) an, der einem Binärwert von 1111 1111 1100 0000 0000 entspricht, um die nächsten zehn Prozessoren anzugeben, d. h. die Prozessoren 10 bis 19.</span><span class="sxs-lookup"><span data-stu-id="e56f5-204">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="e56f5-205">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="e56f5-205">Setting name</span></span> | <span data-ttu-id="e56f5-206">Werte</span><span class="sxs-lookup"><span data-stu-id="e56f5-206">Values</span></span> | <span data-ttu-id="e56f5-207">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e56f5-207">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="e56f5-208">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e56f5-208">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="e56f5-209">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="e56f5-209">*decimal value*</span></span> | <span data-ttu-id="e56f5-210">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-210">.NET Core 3.0</span></span> |
| <span data-ttu-id="e56f5-211">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="e56f5-211">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="e56f5-212">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="e56f5-212">*hexadecimal value*</span></span> | <span data-ttu-id="e56f5-213">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-213">.NET Core 3.0</span></span> |
| <span data-ttu-id="e56f5-214">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="e56f5-214">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="e56f5-215">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="e56f5-215">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="e56f5-216">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="e56f5-216">*decimal value*</span></span> | <span data-ttu-id="e56f5-217">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="e56f5-217">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="e56f5-218">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e56f5-218">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="e56f5-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="e56f5-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="e56f5-220">Gibt die Liste der Prozessoren an, die für Garbage-Collector-Threads verwendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="e56f5-220">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="e56f5-221">Diese Einstellung ist `System.GC.HeapAffinitizeMask` ähnlich, mit der Ausnahme, dass Sie mehr als 64 Prozessoren angeben können.</span><span class="sxs-lookup"><span data-stu-id="e56f5-221">This setting is similar to `System.GC.HeapAffinitizeMask`, except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="e56f5-222">Stellen Sie für Windows-Betriebssysteme der Prozessornummer oder dem Prozessorbereich die entsprechende [CPU-Gruppe](/windows/win32/procthread/processor-groups) voran, z. B. „0:1-10,0:12,1:50-52,1:70“.</span><span class="sxs-lookup"><span data-stu-id="e56f5-222">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="e56f5-223">Wenn die Prozessoraffinität deaktiviert ist, indem `System.GC.NoAffinitize` auf `true` festgelegt wurde, wird diese Einstellung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="e56f5-223">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="e56f5-224">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="e56f5-224">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="e56f5-225">Weitere Informationen finden Sie unter [Optimieren der CPU-Konfiguration für GC auf Computern mit mehr als 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) im Blog von Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="e56f5-225">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="e56f5-226">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="e56f5-226">Setting name</span></span> | <span data-ttu-id="e56f5-227">Werte</span><span class="sxs-lookup"><span data-stu-id="e56f5-227">Values</span></span> | <span data-ttu-id="e56f5-228">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e56f5-228">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="e56f5-229">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e56f5-229">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="e56f5-230">Durch Kommas getrennte Liste mit Prozessornummern oder Bereichen von Prozessornummern</span><span class="sxs-lookup"><span data-stu-id="e56f5-230">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="e56f5-231">Unix-Beispiel: „1-10,12,50-52,70“</span><span class="sxs-lookup"><span data-stu-id="e56f5-231">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="e56f5-232">Windows-Beispiel: „0:1-10,0:12,1:50-52,1:70“</span><span class="sxs-lookup"><span data-stu-id="e56f5-232">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="e56f5-233">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-233">.NET Core 3.0</span></span> |
| <span data-ttu-id="e56f5-234">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="e56f5-234">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="e56f5-235">Durch Kommas getrennte Liste mit Prozessornummern oder Bereichen von Prozessornummern</span><span class="sxs-lookup"><span data-stu-id="e56f5-235">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="e56f5-236">Unix-Beispiel: „1-10,12,50-52,70“</span><span class="sxs-lookup"><span data-stu-id="e56f5-236">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="e56f5-237">Windows-Beispiel: „0:1-10,0:12,1:50-52,1:70“</span><span class="sxs-lookup"><span data-stu-id="e56f5-237">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="e56f5-238">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-238">.NET Core 3.0</span></span> |

<span data-ttu-id="e56f5-239">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e56f5-239">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="e56f5-240">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="e56f5-240">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="e56f5-241">Konfiguriert, ob der Garbage Collector [CPU-Gruppen](/windows/win32/procthread/processor-groups) verwendet</span><span class="sxs-lookup"><span data-stu-id="e56f5-241">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="e56f5-242">Wenn ein 64-Bit-Windows-Computer über mehrere CPU-Gruppen verfügt, d. h. mehr als 64 Prozessoren vorhanden sind, dann wird durch die Aktivierung dieses Elements die Garbage Collection in allen CPU-Gruppen erweitert.</span><span class="sxs-lookup"><span data-stu-id="e56f5-242">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="e56f5-243">Der Garbage Collector verwendet alle Kerne zum Erstellen und Ausgleichen von Heaps.</span><span class="sxs-lookup"><span data-stu-id="e56f5-243">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="e56f5-244">Gilt nur für Garbage Collection des Servers auf 64-Bit-Windows-Betriebssystemen.</span><span class="sxs-lookup"><span data-stu-id="e56f5-244">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="e56f5-245">Standard: Deaktiviert (`0`)</span><span class="sxs-lookup"><span data-stu-id="e56f5-245">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="e56f5-246">Weitere Informationen finden Sie unter [Optimieren der CPU-Konfiguration für GC auf Computern mit mehr als 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) im Blog von Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="e56f5-246">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="e56f5-247">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="e56f5-247">Setting name</span></span> | <span data-ttu-id="e56f5-248">Werte</span><span class="sxs-lookup"><span data-stu-id="e56f5-248">Values</span></span> | <span data-ttu-id="e56f5-249">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e56f5-249">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="e56f5-250">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e56f5-250">**runtimeconfig.json**</span></span> | <span data-ttu-id="e56f5-251">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e56f5-251">N/A</span></span> | <span data-ttu-id="e56f5-252">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e56f5-252">N/A</span></span> | <span data-ttu-id="e56f5-253">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e56f5-253">N/A</span></span> |
| <span data-ttu-id="e56f5-254">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="e56f5-254">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="e56f5-255">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="e56f5-255">`0` - disabled</span></span><br/><span data-ttu-id="e56f5-256">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="e56f5-256">`1` - enabled</span></span> | <span data-ttu-id="e56f5-257">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-257">.NET Core 1.0</span></span> |
| <span data-ttu-id="e56f5-258">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="e56f5-258">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="e56f5-259">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="e56f5-259">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="e56f5-260">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="e56f5-260">`false` - disabled</span></span><br/><span data-ttu-id="e56f5-261">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="e56f5-261">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="e56f5-262">Aktivieren Sie die Option [Thread_UseAllCpuGroups-Element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md), um die Common Language Runtime (CLR) so zu konfigurieren, dass auch Threads aus dem Threadpool in allen CPU-Gruppen verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="e56f5-262">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="e56f5-263">Für .NET Core-Apps können Sie diese Option aktivieren, indem Sie den Wert der Umgebungsvariablen `COMPlus_Thread_UseAllCpuGroups` auf `1` setzen.</span><span class="sxs-lookup"><span data-stu-id="e56f5-263">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="e56f5-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="e56f5-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="e56f5-265">Gibt an, ob Garbage-Collection-Threads Prozessoren *zugeordnet* werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e56f5-265">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="e56f5-266">Einen GC-Thread zuzuordnen, bedeutet, dass dieser nur auf der jeweiligen CPU ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e56f5-266">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="e56f5-267">Für jeden GC-Thread wird ein Heap erstellt.</span><span class="sxs-lookup"><span data-stu-id="e56f5-267">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="e56f5-268">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="e56f5-268">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="e56f5-269">Standard: Garbage-Collection-Threads werden Prozessoren zugeordnet (`false`).</span><span class="sxs-lookup"><span data-stu-id="e56f5-269">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="e56f5-270">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="e56f5-270">Setting name</span></span> | <span data-ttu-id="e56f5-271">Werte</span><span class="sxs-lookup"><span data-stu-id="e56f5-271">Values</span></span> | <span data-ttu-id="e56f5-272">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e56f5-272">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="e56f5-273">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e56f5-273">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="e56f5-274">`false` – zuordnen</span><span class="sxs-lookup"><span data-stu-id="e56f5-274">`false` - affinitize</span></span><br/><span data-ttu-id="e56f5-275">`true` – nicht zuordnen</span><span class="sxs-lookup"><span data-stu-id="e56f5-275">`true` - don't affinitize</span></span> | <span data-ttu-id="e56f5-276">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-276">.NET Core 3.0</span></span> |
| <span data-ttu-id="e56f5-277">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="e56f5-277">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="e56f5-278">`0` – zuordnen</span><span class="sxs-lookup"><span data-stu-id="e56f5-278">`0` - affinitize</span></span><br/><span data-ttu-id="e56f5-279">`1` – nicht zuordnen</span><span class="sxs-lookup"><span data-stu-id="e56f5-279">`1` - don't affinitize</span></span> | <span data-ttu-id="e56f5-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="e56f5-281">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="e56f5-281">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="e56f5-282">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="e56f5-282">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="e56f5-283">`false` – zuordnen</span><span class="sxs-lookup"><span data-stu-id="e56f5-283">`false` - affinitize</span></span><br/><span data-ttu-id="e56f5-284">`true` – nicht zuordnen</span><span class="sxs-lookup"><span data-stu-id="e56f5-284">`true` - don't affinitize</span></span> | <span data-ttu-id="e56f5-285">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="e56f5-285">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="e56f5-286">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e56f5-286">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="e56f5-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="e56f5-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="e56f5-288">Gibt die maximale Commitgröße in Bytes für den GC-Heap und die GC-Buchhaltung an</span><span class="sxs-lookup"><span data-stu-id="e56f5-288">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>

| | <span data-ttu-id="e56f5-289">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="e56f5-289">Setting name</span></span> | <span data-ttu-id="e56f5-290">Werte</span><span class="sxs-lookup"><span data-stu-id="e56f5-290">Values</span></span> | <span data-ttu-id="e56f5-291">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e56f5-291">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="e56f5-292">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e56f5-292">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="e56f5-293">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="e56f5-293">*decimal value*</span></span> | <span data-ttu-id="e56f5-294">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-294">.NET Core 3.0</span></span> |
| <span data-ttu-id="e56f5-295">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="e56f5-295">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="e56f5-296">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="e56f5-296">*hexadecimal value*</span></span> | <span data-ttu-id="e56f5-297">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-297">.NET Core 3.0</span></span> |

<span data-ttu-id="e56f5-298">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e56f5-298">Example:</span></span>

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
> <span data-ttu-id="e56f5-299">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="e56f5-299">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="e56f5-300">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="e56f5-300">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="e56f5-301">Wenn Sie beispielsweise eine feste Heapgrenze von 200 MiB festlegen, würden die Werte für die JSON-Datei 209715200 und für die Umgebungsvariable 0xc800000 oder C800000 betragen.</span><span class="sxs-lookup"><span data-stu-id="e56f5-301">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="e56f5-302">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="e56f5-302">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="e56f5-303">Gibt den GC-Heapverbrauch in Prozent des Gesamtspeichers an</span><span class="sxs-lookup"><span data-stu-id="e56f5-303">Specifies the GC heap usage as a percentage of the total memory.</span></span>

| | <span data-ttu-id="e56f5-304">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="e56f5-304">Setting name</span></span> | <span data-ttu-id="e56f5-305">Werte</span><span class="sxs-lookup"><span data-stu-id="e56f5-305">Values</span></span> | <span data-ttu-id="e56f5-306">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e56f5-306">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="e56f5-307">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e56f5-307">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="e56f5-308">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="e56f5-308">*decimal value*</span></span> | <span data-ttu-id="e56f5-309">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-309">.NET Core 3.0</span></span> |
| <span data-ttu-id="e56f5-310">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="e56f5-310">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="e56f5-311">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="e56f5-311">*hexadecimal value*</span></span> | <span data-ttu-id="e56f5-312">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-312">.NET Core 3.0</span></span> |

<span data-ttu-id="e56f5-313">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e56f5-313">Example:</span></span>

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
> <span data-ttu-id="e56f5-314">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="e56f5-314">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="e56f5-315">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="e56f5-315">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="e56f5-316">Beispielsweise würden bei einer Begrenzung des Heapverbrauchs auf 30 % die Werte für die JSON-Datei 30 und für die Umgebungsvariable 0x1E oder 1E betragen.</span><span class="sxs-lookup"><span data-stu-id="e56f5-316">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="e56f5-317">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="e56f5-317">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="e56f5-318">Konfiguriert, ob Segmente, die gelöscht werden sollen, zur späteren Verwendung auf eine Standbyliste aufgenommen oder an das Betriebssystem zurückgegeben werden</span><span class="sxs-lookup"><span data-stu-id="e56f5-318">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="e56f5-319">Standard: Segmente werden an das Betriebssystem zurückgegeben (`false`).</span><span class="sxs-lookup"><span data-stu-id="e56f5-319">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="e56f5-320">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="e56f5-320">Setting name</span></span> | <span data-ttu-id="e56f5-321">Werte</span><span class="sxs-lookup"><span data-stu-id="e56f5-321">Values</span></span> | <span data-ttu-id="e56f5-322">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e56f5-322">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="e56f5-323">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e56f5-323">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="e56f5-324">`false` – Freigabe an Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="e56f5-324">`false` - release to OS</span></span><br/><span data-ttu-id="e56f5-325">`true` – in Standbymodus versetzen</span><span class="sxs-lookup"><span data-stu-id="e56f5-325">`true` - put on standby</span></span> | <span data-ttu-id="e56f5-326">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-326">.NET Core 1.0</span></span> |
| <span data-ttu-id="e56f5-327">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="e56f5-327">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="e56f5-328">`false` – Freigabe an Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="e56f5-328">`false` - release to OS</span></span><br/><span data-ttu-id="e56f5-329">`true` – in Standbymodus versetzen</span><span class="sxs-lookup"><span data-stu-id="e56f5-329">`true` - put on standby</span></span> | <span data-ttu-id="e56f5-330">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-330">.NET Core 1.0</span></span> |
| <span data-ttu-id="e56f5-331">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="e56f5-331">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="e56f5-332">`0` – Freigabe an Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="e56f5-332">`0` - release to OS</span></span><br/><span data-ttu-id="e56f5-333">`1` – in Standbymodus versetzen</span><span class="sxs-lookup"><span data-stu-id="e56f5-333">`1` - put on standby</span></span> | <span data-ttu-id="e56f5-334">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-334">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="e56f5-335">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e56f5-335">Examples</span></span>

<span data-ttu-id="e56f5-336">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="e56f5-336">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="e56f5-337">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="e56f5-337">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="e56f5-338">Umfangreiche Seiten</span><span class="sxs-lookup"><span data-stu-id="e56f5-338">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="e56f5-339">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="e56f5-339">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="e56f5-340">Gibt an, ob umfangreiche Seiten verwendet werden sollen, wenn eine feste Heapgrenze festgelegt wird</span><span class="sxs-lookup"><span data-stu-id="e56f5-340">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="e56f5-341">Standard: Deaktiviert (`0`)</span><span class="sxs-lookup"><span data-stu-id="e56f5-341">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="e56f5-342">Dies ist eine experimentelle Einstellung.</span><span class="sxs-lookup"><span data-stu-id="e56f5-342">This is an experimental setting.</span></span>

| | <span data-ttu-id="e56f5-343">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="e56f5-343">Setting name</span></span> | <span data-ttu-id="e56f5-344">Werte</span><span class="sxs-lookup"><span data-stu-id="e56f5-344">Values</span></span> | <span data-ttu-id="e56f5-345">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e56f5-345">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="e56f5-346">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e56f5-346">**runtimeconfig.json**</span></span> | <span data-ttu-id="e56f5-347">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e56f5-347">N/A</span></span> | <span data-ttu-id="e56f5-348">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e56f5-348">N/A</span></span> | <span data-ttu-id="e56f5-349">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e56f5-349">N/A</span></span> |
| <span data-ttu-id="e56f5-350">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="e56f5-350">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="e56f5-351">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="e56f5-351">`0` - disabled</span></span><br/><span data-ttu-id="e56f5-352">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="e56f5-352">`1` - enabled</span></span> | <span data-ttu-id="e56f5-353">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-353">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="e56f5-354">Große Objekte</span><span class="sxs-lookup"><span data-stu-id="e56f5-354">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="e56f5-355">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="e56f5-355">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="e56f5-356">Konfiguriert die Garbage-Collector-Unterstützung auf 64-Bit-Plattformen für Arrays mit einer Gesamtgröße von mehr als 2 Gigabytes (GB)</span><span class="sxs-lookup"><span data-stu-id="e56f5-356">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="e56f5-357">Standard: Aktiviert (`1`)</span><span class="sxs-lookup"><span data-stu-id="e56f5-357">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="e56f5-358">Diese Option wird in einer zukünftigen Version von .NET möglicherweise veraltet sein.</span><span class="sxs-lookup"><span data-stu-id="e56f5-358">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="e56f5-359">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="e56f5-359">Setting name</span></span> | <span data-ttu-id="e56f5-360">Werte</span><span class="sxs-lookup"><span data-stu-id="e56f5-360">Values</span></span> | <span data-ttu-id="e56f5-361">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e56f5-361">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="e56f5-362">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e56f5-362">**runtimeconfig.json**</span></span> | <span data-ttu-id="e56f5-363">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e56f5-363">N/A</span></span> | <span data-ttu-id="e56f5-364">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e56f5-364">N/A</span></span> | <span data-ttu-id="e56f5-365">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e56f5-365">N/A</span></span> |
| <span data-ttu-id="e56f5-366">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="e56f5-366">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="e56f5-367">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="e56f5-367">`1` - enabled</span></span><br/> <span data-ttu-id="e56f5-368">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="e56f5-368">`0` - disabled</span></span> | <span data-ttu-id="e56f5-369">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-369">.NET Core 1.0</span></span> |
| <span data-ttu-id="e56f5-370">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="e56f5-370">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="e56f5-371">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="e56f5-371">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="e56f5-372">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="e56f5-372">`1` - enabled</span></span><br/> <span data-ttu-id="e56f5-373">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="e56f5-373">`0` - disabled</span></span> | <span data-ttu-id="e56f5-374">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="e56f5-374">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="e56f5-375">Großer Objektheapschwellenwert</span><span class="sxs-lookup"><span data-stu-id="e56f5-375">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="e56f5-376">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="e56f5-376">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="e56f5-377">Gibt die Größe des Schwellenwerts in Bytes an, der bewirkt, dass Objekte auf den großen Objektheap (Large Object Heap, LOH) gehen</span><span class="sxs-lookup"><span data-stu-id="e56f5-377">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="e56f5-378">Der Standardschwellenwert beträgt 85.000 Bytes.</span><span class="sxs-lookup"><span data-stu-id="e56f5-378">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="e56f5-379">Der von Ihnen festgelegte Wert muss größer sein als der Standardschwellenwert.</span><span class="sxs-lookup"><span data-stu-id="e56f5-379">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="e56f5-380">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="e56f5-380">Setting name</span></span> | <span data-ttu-id="e56f5-381">Werte</span><span class="sxs-lookup"><span data-stu-id="e56f5-381">Values</span></span> | <span data-ttu-id="e56f5-382">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e56f5-382">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="e56f5-383">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e56f5-383">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="e56f5-384">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="e56f5-384">*decimal value*</span></span> | <span data-ttu-id="e56f5-385">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-385">.NET Core 1.0</span></span> |
| <span data-ttu-id="e56f5-386">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="e56f5-386">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="e56f5-387">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="e56f5-387">*hexadecimal value*</span></span> | <span data-ttu-id="e56f5-388">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-388">.NET Core 1.0</span></span> |
| <span data-ttu-id="e56f5-389">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="e56f5-389">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="e56f5-390">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="e56f5-390">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="e56f5-391">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="e56f5-391">*decimal value*</span></span> | <span data-ttu-id="e56f5-392">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="e56f5-392">.NET Framework 4.8</span></span> |

<span data-ttu-id="e56f5-393">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e56f5-393">Example:</span></span>

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
> <span data-ttu-id="e56f5-394">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="e56f5-394">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="e56f5-395">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="e56f5-395">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="e56f5-396">Wenn Sie beispielsweise die Größe eines Schwellenwerts auf 120.000 Bytes festlegen, würden die Werte für die JSON-Datei 120000 und für die Umgebungsvariable 0x1D4C0 oder 1D4C0 betragen.</span><span class="sxs-lookup"><span data-stu-id="e56f5-396">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="e56f5-397">Eigenständige GC</span><span class="sxs-lookup"><span data-stu-id="e56f5-397">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="e56f5-398">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="e56f5-398">COMPlus_GCName</span></span>

- <span data-ttu-id="e56f5-399">Gibt einen Pfad zu der Bibliothek an, die den Garbage Collector enthält, der von der Runtime geladen werden soll</span><span class="sxs-lookup"><span data-stu-id="e56f5-399">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="e56f5-400">Weitere Informationen finden Sie unter [Entwurf eines eigenständigen GC-Ladeprogramms](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="e56f5-400">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="e56f5-401">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="e56f5-401">Setting name</span></span> | <span data-ttu-id="e56f5-402">Werte</span><span class="sxs-lookup"><span data-stu-id="e56f5-402">Values</span></span> | <span data-ttu-id="e56f5-403">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e56f5-403">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="e56f5-404">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e56f5-404">**runtimeconfig.json**</span></span> | <span data-ttu-id="e56f5-405">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e56f5-405">N/A</span></span> | <span data-ttu-id="e56f5-406">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e56f5-406">N/A</span></span> | <span data-ttu-id="e56f5-407">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e56f5-407">N/A</span></span> |
| <span data-ttu-id="e56f5-408">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="e56f5-408">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="e56f5-409">*string_path*</span><span class="sxs-lookup"><span data-stu-id="e56f5-409">*string_path*</span></span> | <span data-ttu-id="e56f5-410">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e56f5-410">.NET Core 2.0</span></span> |
