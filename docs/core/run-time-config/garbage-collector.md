---
title: Garbage-Collector-Konfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, um zu konfigurieren, wie der Garbage Collector Arbeitsspeicher für .NET Core-Apps verwaltet.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: ec575bdd17c8a7c290673b7085074bbba94cedef
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102865"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="c207f-103">Laufzeitkonfigurationsoptionen für die Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="c207f-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="c207f-104">Diese Seite enthält Informationen zu Garbage-Collector-Einstellungen (GC), die zur Laufzeit geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="c207f-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="c207f-105">Verwenden Sie diese Einstellungen, wenn Sie versuchen, die maximale Leistung einer ausgeführten App zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="c207f-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="c207f-106">Die Standardwerte bieten jedoch in typischen Situationen eine optimale Leistung für die meisten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="c207f-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="c207f-107">Einstellungen werden auf dieser Seite in Gruppen angeordnet.</span><span class="sxs-lookup"><span data-stu-id="c207f-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="c207f-108">Die Einstellungen in den einzelnen Gruppen werden häufig zusammen verwendet, um ein bestimmtes Ergebnis zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="c207f-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="c207f-109">Diese Einstellungen können auch dynamisch von der App geändert werden, während diese ausgeführt wird, sodass die von Ihnen festgelegten Laufzeiteinstellungen überschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="c207f-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="c207f-110">Einige Einstellungen, wie z. B. die [Latenzebene](../../standard/garbage-collection/latency.md), werden in der Regel nur über die API zur Entwurfszeit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c207f-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="c207f-111">Diese Einstellungen werden auf dieser Seite weggelassen.</span><span class="sxs-lookup"><span data-stu-id="c207f-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="c207f-112">Verwenden Sie für Zahlenwerte für Einstellungen in der Datei *runtimeconfig.json* die Dezimalschreibweise und für Einstellungen in der Umgebungsvariablen die Hexadezimalnotation.</span><span class="sxs-lookup"><span data-stu-id="c207f-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="c207f-113">Bei hexadezimalen Werten können Sie sie mit dem oder ohne das Präfix „0x“ angeben.</span><span class="sxs-lookup"><span data-stu-id="c207f-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="c207f-114">Varianten der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="c207f-114">Flavors of garbage collection</span></span>

<span data-ttu-id="c207f-115">Die zwei Hauptvarianten der Garbage Collection sind Arbeitsstation-GC und Server-GC.</span><span class="sxs-lookup"><span data-stu-id="c207f-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="c207f-116">Weitere Informationen zu den Unterschieden zwischen diesen beiden Varianten finden Sie unter [Garbage Collection für die Arbeitsstation und Garbage Collection auf dem Server](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="c207f-116">For more information about differences between the two, see [Workstation and server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span>

<span data-ttu-id="c207f-117">Die Untervarianten der Garbage Collection sind Hintergrund-GC und nicht gleichzeitige GC.</span><span class="sxs-lookup"><span data-stu-id="c207f-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="c207f-118">Verwenden Sie die folgenden Einstellungen, um Varianten der Garbage Collection auszuwählen:</span><span class="sxs-lookup"><span data-stu-id="c207f-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="c207f-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="c207f-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="c207f-120">Konfiguriert, ob die Anwendung die Arbeitsstation-GC oder die Server-GC verwendet</span><span class="sxs-lookup"><span data-stu-id="c207f-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="c207f-121">Standard: Arbeitsstation-Garbage-Collection (`false`)</span><span class="sxs-lookup"><span data-stu-id="c207f-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="c207f-122">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="c207f-122">Setting name</span></span> | <span data-ttu-id="c207f-123">Werte</span><span class="sxs-lookup"><span data-stu-id="c207f-123">Values</span></span> | <span data-ttu-id="c207f-124">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="c207f-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c207f-125">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c207f-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="c207f-126">`false` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="c207f-126">`false` - workstation</span></span><br/><span data-ttu-id="c207f-127">`true` – Server</span><span class="sxs-lookup"><span data-stu-id="c207f-127">`true` - server</span></span> | <span data-ttu-id="c207f-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c207f-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="c207f-129">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="c207f-129">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="c207f-130">`false` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="c207f-130">`false` - workstation</span></span><br/><span data-ttu-id="c207f-131">`true` – Server</span><span class="sxs-lookup"><span data-stu-id="c207f-131">`true` - server</span></span> | <span data-ttu-id="c207f-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c207f-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="c207f-133">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="c207f-133">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="c207f-134">`0` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="c207f-134">`0` - workstation</span></span><br/><span data-ttu-id="c207f-135">`1` – Server</span><span class="sxs-lookup"><span data-stu-id="c207f-135">`1` - server</span></span> | <span data-ttu-id="c207f-136">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c207f-136">.NET Core 1.0</span></span> |
| <span data-ttu-id="c207f-137">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="c207f-137">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="c207f-138">GCServer</span><span class="sxs-lookup"><span data-stu-id="c207f-138">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="c207f-139">`false` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="c207f-139">`false` - workstation</span></span><br/><span data-ttu-id="c207f-140">`true` – Server</span><span class="sxs-lookup"><span data-stu-id="c207f-140">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="c207f-141">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c207f-141">Examples</span></span>

<span data-ttu-id="c207f-142">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="c207f-142">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="c207f-143">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="c207f-143">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="c207f-144">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="c207f-144">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="c207f-145">Konfiguriert, ob die (gleichzeitige) Hintergrund-GC aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="c207f-145">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="c207f-146">Standard: Aktiviert (`true`)</span><span class="sxs-lookup"><span data-stu-id="c207f-146">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="c207f-147">Weitere Informationen finden Sie unter [Hintergrund der Garbage Collection](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="c207f-147">For more information, see [Background garbage collection](../../standard/garbage-collection/background-gc.md).</span></span>

| | <span data-ttu-id="c207f-148">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="c207f-148">Setting name</span></span> | <span data-ttu-id="c207f-149">Werte</span><span class="sxs-lookup"><span data-stu-id="c207f-149">Values</span></span> | <span data-ttu-id="c207f-150">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="c207f-150">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c207f-151">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c207f-151">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="c207f-152">`true` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="c207f-152">`true` - background GC</span></span><br/><span data-ttu-id="c207f-153">`false` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="c207f-153">`false` - non-concurrent GC</span></span> | <span data-ttu-id="c207f-154">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c207f-154">.NET Core 1.0</span></span> |
| <span data-ttu-id="c207f-155">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="c207f-155">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="c207f-156">`true` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="c207f-156">`true` - background GC</span></span><br/><span data-ttu-id="c207f-157">`false` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="c207f-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="c207f-158">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c207f-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="c207f-159">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="c207f-159">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="c207f-160">`true` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="c207f-160">`true` - background GC</span></span><br/><span data-ttu-id="c207f-161">`false` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="c207f-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="c207f-162">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c207f-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="c207f-163">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="c207f-163">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="c207f-164">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="c207f-164">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="c207f-165">`true` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="c207f-165">`true` - background GC</span></span><br/><span data-ttu-id="c207f-166">`false` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="c207f-166">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="c207f-167">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c207f-167">Examples</span></span>

<span data-ttu-id="c207f-168">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="c207f-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="c207f-169">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="c207f-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="c207f-170">Verwalten des Ressourceneinsatzes</span><span class="sxs-lookup"><span data-stu-id="c207f-170">Manage resource usage</span></span>

<span data-ttu-id="c207f-171">Verwenden Sie die in diesem Abschnitt beschriebenen Einstellungen, um die Speicher- und Prozessorauslastung des Garbage Collectors zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="c207f-171">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="c207f-172">Weitere Informationen zu einigen dieser Einstellungen finden Sie im Blogeintrag [Mittelweg zwischen Arbeitsstation- und Server-GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).</span><span class="sxs-lookup"><span data-stu-id="c207f-172">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="c207f-173">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="c207f-173">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="c207f-174">Schränkt die Anzahl von Heaps ein, die vom Garbage Collector erstellt werden</span><span class="sxs-lookup"><span data-stu-id="c207f-174">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="c207f-175">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="c207f-175">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="c207f-176">Wenn die [GC-Prozessoraffinität](#systemgcnoaffinitizecomplus_gcnoaffinitize) aktiviert ist (Standardeinstellung), ordnet die Einstellung für die Heapanzahl den ersten `n` Prozessoren `n` GC-Heaps/-Threads zu.</span><span class="sxs-lookup"><span data-stu-id="c207f-176">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="c207f-177">(Verwenden Sie die Einstellungen [AffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) oder [AffinitizeRanges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges), um genau anzugeben, welche Prozessoren zugeordnet werden sollen.)</span><span class="sxs-lookup"><span data-stu-id="c207f-177">(Use the [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) or [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="c207f-178">Wenn die [GC-Prozessoraffinität](#systemgcnoaffinitizecomplus_gcnoaffinitize) deaktiviert ist, wird mit dieser Einstellung die Anzahl der GC-Heaps eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="c207f-178">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="c207f-179">Weitere Informationen finden Sie unter [Hinweise zu GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="c207f-179">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="c207f-180">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="c207f-180">Setting name</span></span> | <span data-ttu-id="c207f-181">Werte</span><span class="sxs-lookup"><span data-stu-id="c207f-181">Values</span></span> | <span data-ttu-id="c207f-182">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="c207f-182">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c207f-183">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c207f-183">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="c207f-184">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="c207f-184">*decimal value*</span></span> | <span data-ttu-id="c207f-185">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c207f-185">.NET Core 3.0</span></span> |
| <span data-ttu-id="c207f-186">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="c207f-186">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="c207f-187">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="c207f-187">*hexadecimal value*</span></span> | <span data-ttu-id="c207f-188">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c207f-188">.NET Core 3.0</span></span> |
| <span data-ttu-id="c207f-189">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="c207f-189">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="c207f-190">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="c207f-190">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="c207f-191">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="c207f-191">*decimal value*</span></span> | <span data-ttu-id="c207f-192">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="c207f-192">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="c207f-193">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c207f-193">Example:</span></span>

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
> <span data-ttu-id="c207f-194">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="c207f-194">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="c207f-195">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="c207f-195">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="c207f-196">Für eine Einschränkung der Heapanzahl auf 16 wären die Werte beispielsweise 16 für die JSON-Datei und 0x10 oder 10 für die Umgebungsvariable.</span><span class="sxs-lookup"><span data-stu-id="c207f-196">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="c207f-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="c207f-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="c207f-198">Gibt die genauen Prozessoren an, die Garbage-Collector-Threads verwenden sollen</span><span class="sxs-lookup"><span data-stu-id="c207f-198">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="c207f-199">Wenn die [GC-Prozessoraffinität](#systemgcnoaffinitizecomplus_gcnoaffinitize) deaktiviert ist, wird diese Einstellung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c207f-199">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="c207f-200">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="c207f-200">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="c207f-201">Der Wert ist eine Bitmaske, die die für den Prozess verfügbaren Prozessoren definiert.</span><span class="sxs-lookup"><span data-stu-id="c207f-201">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="c207f-202">Beispielsweise ist ein Dezimalwert von 1023 (oder ein Hexadezimalwert von 0x3FF oder 3FF bei Verwendung der Umgebungsvariablen) in Binärschreibweise 0011 1111 1111.</span><span class="sxs-lookup"><span data-stu-id="c207f-202">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="c207f-203">Dies gibt an, dass die ersten zehn Prozessoren verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c207f-203">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="c207f-204">Geben Sie einen Dezimalwert von 1047552 (oder einen Hexadezimalwert von 0xFFC00 oder FFC00) an, der einem Binärwert von 1111 1111 1100 0000 0000 entspricht, um die nächsten zehn Prozessoren anzugeben, d. h. die Prozessoren 10 bis 19.</span><span class="sxs-lookup"><span data-stu-id="c207f-204">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="c207f-205">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="c207f-205">Setting name</span></span> | <span data-ttu-id="c207f-206">Werte</span><span class="sxs-lookup"><span data-stu-id="c207f-206">Values</span></span> | <span data-ttu-id="c207f-207">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="c207f-207">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c207f-208">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c207f-208">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="c207f-209">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="c207f-209">*decimal value*</span></span> | <span data-ttu-id="c207f-210">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c207f-210">.NET Core 3.0</span></span> |
| <span data-ttu-id="c207f-211">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="c207f-211">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="c207f-212">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="c207f-212">*hexadecimal value*</span></span> | <span data-ttu-id="c207f-213">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c207f-213">.NET Core 3.0</span></span> |
| <span data-ttu-id="c207f-214">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="c207f-214">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="c207f-215">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="c207f-215">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="c207f-216">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="c207f-216">*decimal value*</span></span> | <span data-ttu-id="c207f-217">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="c207f-217">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="c207f-218">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c207f-218">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="c207f-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="c207f-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="c207f-220">Gibt die Liste der Prozessoren an, die für Garbage-Collector-Threads verwendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="c207f-220">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="c207f-221">Diese Einstellung ähnelt [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), abgesehen davon, dass Sie mehr als 64 Prozessoren angeben können.</span><span class="sxs-lookup"><span data-stu-id="c207f-221">This setting is similar to [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="c207f-222">Stellen Sie für Windows-Betriebssysteme der Prozessornummer oder dem Prozessorbereich die entsprechende [CPU-Gruppe](/windows/win32/procthread/processor-groups) voran, z. B. „0:1-10,0:12,1:50-52,1:70“.</span><span class="sxs-lookup"><span data-stu-id="c207f-222">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="c207f-223">Wenn die [GC-Prozessoraffinität](#systemgcnoaffinitizecomplus_gcnoaffinitize) deaktiviert ist, wird diese Einstellung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c207f-223">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="c207f-224">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="c207f-224">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="c207f-225">Weitere Informationen finden Sie unter [Optimieren der CPU-Konfiguration für GC auf Computern mit mehr als 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) im Blog von Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="c207f-225">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="c207f-226">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="c207f-226">Setting name</span></span> | <span data-ttu-id="c207f-227">Werte</span><span class="sxs-lookup"><span data-stu-id="c207f-227">Values</span></span> | <span data-ttu-id="c207f-228">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="c207f-228">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c207f-229">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c207f-229">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="c207f-230">Durch Kommas getrennte Liste mit Prozessornummern oder Bereichen von Prozessornummern</span><span class="sxs-lookup"><span data-stu-id="c207f-230">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="c207f-231">Unix-Beispiel: „1-10,12,50-52,70“</span><span class="sxs-lookup"><span data-stu-id="c207f-231">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="c207f-232">Windows-Beispiel: „0:1-10,0:12,1:50-52,1:70“</span><span class="sxs-lookup"><span data-stu-id="c207f-232">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="c207f-233">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c207f-233">.NET Core 3.0</span></span> |
| <span data-ttu-id="c207f-234">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="c207f-234">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="c207f-235">Durch Kommas getrennte Liste mit Prozessornummern oder Bereichen von Prozessornummern</span><span class="sxs-lookup"><span data-stu-id="c207f-235">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="c207f-236">Unix-Beispiel: „1-10,12,50-52,70“</span><span class="sxs-lookup"><span data-stu-id="c207f-236">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="c207f-237">Windows-Beispiel: „0:1-10,0:12,1:50-52,1:70“</span><span class="sxs-lookup"><span data-stu-id="c207f-237">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="c207f-238">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c207f-238">.NET Core 3.0</span></span> |

<span data-ttu-id="c207f-239">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c207f-239">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="c207f-240">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="c207f-240">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="c207f-241">Konfiguriert, ob der Garbage Collector [CPU-Gruppen](/windows/win32/procthread/processor-groups) verwendet</span><span class="sxs-lookup"><span data-stu-id="c207f-241">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="c207f-242">Wenn ein 64-Bit-Windows-Computer über mehrere CPU-Gruppen verfügt, d. h. mehr als 64 Prozessoren vorhanden sind, dann wird durch die Aktivierung dieses Elements die Garbage Collection in allen CPU-Gruppen erweitert.</span><span class="sxs-lookup"><span data-stu-id="c207f-242">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="c207f-243">Der Garbage Collector verwendet alle Kerne zum Erstellen und Ausgleichen von Heaps.</span><span class="sxs-lookup"><span data-stu-id="c207f-243">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="c207f-244">Gilt nur für Garbage Collection des Servers auf 64-Bit-Windows-Betriebssystemen.</span><span class="sxs-lookup"><span data-stu-id="c207f-244">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="c207f-245">Standard: Deaktiviert (`0`)</span><span class="sxs-lookup"><span data-stu-id="c207f-245">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="c207f-246">Weitere Informationen finden Sie unter [Optimieren der CPU-Konfiguration für GC auf Computern mit mehr als 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) im Blog von Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="c207f-246">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="c207f-247">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="c207f-247">Setting name</span></span> | <span data-ttu-id="c207f-248">Werte</span><span class="sxs-lookup"><span data-stu-id="c207f-248">Values</span></span> | <span data-ttu-id="c207f-249">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="c207f-249">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c207f-250">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c207f-250">**runtimeconfig.json**</span></span> | <span data-ttu-id="c207f-251">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c207f-251">N/A</span></span> | <span data-ttu-id="c207f-252">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c207f-252">N/A</span></span> | <span data-ttu-id="c207f-253">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c207f-253">N/A</span></span> |
| <span data-ttu-id="c207f-254">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="c207f-254">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="c207f-255">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="c207f-255">`0` - disabled</span></span><br/><span data-ttu-id="c207f-256">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="c207f-256">`1` - enabled</span></span> | <span data-ttu-id="c207f-257">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c207f-257">.NET Core 1.0</span></span> |
| <span data-ttu-id="c207f-258">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="c207f-258">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="c207f-259">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="c207f-259">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="c207f-260">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="c207f-260">`false` - disabled</span></span><br/><span data-ttu-id="c207f-261">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="c207f-261">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="c207f-262">Aktivieren Sie die Option [Thread_UseAllCpuGroups-Element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md), um die Common Language Runtime (CLR) so zu konfigurieren, dass auch Threads aus dem Threadpool in allen CPU-Gruppen verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="c207f-262">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="c207f-263">Für .NET Core-Apps können Sie diese Option aktivieren, indem Sie den Wert der Umgebungsvariablen `COMPlus_Thread_UseAllCpuGroups` auf `1` setzen.</span><span class="sxs-lookup"><span data-stu-id="c207f-263">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="c207f-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="c207f-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="c207f-265">Gibt an, ob Garbage-Collection-Threads Prozessoren *zugeordnet* werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c207f-265">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="c207f-266">Einen GC-Thread zuzuordnen, bedeutet, dass dieser nur auf der jeweiligen CPU ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c207f-266">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="c207f-267">Für jeden GC-Thread wird ein Heap erstellt.</span><span class="sxs-lookup"><span data-stu-id="c207f-267">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="c207f-268">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="c207f-268">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="c207f-269">Standard: Garbage-Collection-Threads werden Prozessoren zugeordnet (`false`).</span><span class="sxs-lookup"><span data-stu-id="c207f-269">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="c207f-270">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="c207f-270">Setting name</span></span> | <span data-ttu-id="c207f-271">Werte</span><span class="sxs-lookup"><span data-stu-id="c207f-271">Values</span></span> | <span data-ttu-id="c207f-272">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="c207f-272">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c207f-273">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c207f-273">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="c207f-274">`false` – zuordnen</span><span class="sxs-lookup"><span data-stu-id="c207f-274">`false` - affinitize</span></span><br/><span data-ttu-id="c207f-275">`true` – nicht zuordnen</span><span class="sxs-lookup"><span data-stu-id="c207f-275">`true` - don't affinitize</span></span> | <span data-ttu-id="c207f-276">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c207f-276">.NET Core 3.0</span></span> |
| <span data-ttu-id="c207f-277">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="c207f-277">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="c207f-278">`0` – zuordnen</span><span class="sxs-lookup"><span data-stu-id="c207f-278">`0` - affinitize</span></span><br/><span data-ttu-id="c207f-279">`1` – nicht zuordnen</span><span class="sxs-lookup"><span data-stu-id="c207f-279">`1` - don't affinitize</span></span> | <span data-ttu-id="c207f-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c207f-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="c207f-281">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="c207f-281">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="c207f-282">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="c207f-282">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="c207f-283">`false` – zuordnen</span><span class="sxs-lookup"><span data-stu-id="c207f-283">`false` - affinitize</span></span><br/><span data-ttu-id="c207f-284">`true` – nicht zuordnen</span><span class="sxs-lookup"><span data-stu-id="c207f-284">`true` - don't affinitize</span></span> | <span data-ttu-id="c207f-285">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="c207f-285">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="c207f-286">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c207f-286">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="c207f-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="c207f-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="c207f-288">Gibt die maximale Commitgröße in Bytes für den GC-Heap und die GC-Buchhaltung an</span><span class="sxs-lookup"><span data-stu-id="c207f-288">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="c207f-289">Diese Einstellung gilt nur für 64-Bit-Computer.</span><span class="sxs-lookup"><span data-stu-id="c207f-289">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="c207f-290">Der Standardwert, der nur in bestimmten Fällen gilt, ist der größere Wert von 20 MB oder 75 % der Speichergrenze für den Container.</span><span class="sxs-lookup"><span data-stu-id="c207f-290">The default value, which only applies in certain cases, is the greater of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="c207f-291">Der Standardwert wird in folgenden Fällen angewendet:</span><span class="sxs-lookup"><span data-stu-id="c207f-291">The default value applies if:</span></span>

  - <span data-ttu-id="c207f-292">Der Prozess wird in einem Container ausgeführt, für den ein Arbeitsspeicherlimit angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="c207f-292">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="c207f-293">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) ist nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c207f-293">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) is not set.</span></span>

| | <span data-ttu-id="c207f-294">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="c207f-294">Setting name</span></span> | <span data-ttu-id="c207f-295">Werte</span><span class="sxs-lookup"><span data-stu-id="c207f-295">Values</span></span> | <span data-ttu-id="c207f-296">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="c207f-296">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c207f-297">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c207f-297">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="c207f-298">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="c207f-298">*decimal value*</span></span> | <span data-ttu-id="c207f-299">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c207f-299">.NET Core 3.0</span></span> |
| <span data-ttu-id="c207f-300">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="c207f-300">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="c207f-301">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="c207f-301">*hexadecimal value*</span></span> | <span data-ttu-id="c207f-302">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c207f-302">.NET Core 3.0</span></span> |

<span data-ttu-id="c207f-303">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c207f-303">Example:</span></span>

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
> <span data-ttu-id="c207f-304">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="c207f-304">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="c207f-305">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="c207f-305">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="c207f-306">Wenn Sie beispielsweise eine feste Heapgrenze von 200 MiB festlegen, würden die Werte für die JSON-Datei 209715200 und für die Umgebungsvariable 0xc800000 oder C800000 betragen.</span><span class="sxs-lookup"><span data-stu-id="c207f-306">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="c207f-307">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="c207f-307">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="c207f-308">Gibt den zulässigen GC-Heapverbrauch in Prozent des gesamten physischen Speichers an.</span><span class="sxs-lookup"><span data-stu-id="c207f-308">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="c207f-309">Wenn außerdem [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) festgelegt ist, wird diese Einstellung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c207f-309">If [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="c207f-310">Diese Einstellung gilt nur für 64-Bit-Computer.</span><span class="sxs-lookup"><span data-stu-id="c207f-310">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="c207f-311">Wenn der Prozess in einem Container ausgeführt, für den ein Arbeitsspeicherlimit angegeben wurde, wird der Prozentsatz als Prozentsatz dieses Arbeitsspeicherlimits berechnet.</span><span class="sxs-lookup"><span data-stu-id="c207f-311">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="c207f-312">Der Standardwert, der nur in bestimmten Fällen angewendet wird, beträgt weniger als 20 MB oder 75 % des Arbeitsspeicherlimits für den Container.</span><span class="sxs-lookup"><span data-stu-id="c207f-312">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="c207f-313">Der Standardwert wird in folgenden Fällen angewendet:</span><span class="sxs-lookup"><span data-stu-id="c207f-313">The default value applies if:</span></span>

  - <span data-ttu-id="c207f-314">Der Prozess wird in einem Container ausgeführt, für den ein Arbeitsspeicherlimit angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="c207f-314">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="c207f-315">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) ist nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c207f-315">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is not set.</span></span>

| | <span data-ttu-id="c207f-316">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="c207f-316">Setting name</span></span> | <span data-ttu-id="c207f-317">Werte</span><span class="sxs-lookup"><span data-stu-id="c207f-317">Values</span></span> | <span data-ttu-id="c207f-318">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="c207f-318">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c207f-319">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c207f-319">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="c207f-320">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="c207f-320">*decimal value*</span></span> | <span data-ttu-id="c207f-321">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c207f-321">.NET Core 3.0</span></span> |
| <span data-ttu-id="c207f-322">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="c207f-322">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="c207f-323">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="c207f-323">*hexadecimal value*</span></span> | <span data-ttu-id="c207f-324">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c207f-324">.NET Core 3.0</span></span> |

<span data-ttu-id="c207f-325">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c207f-325">Example:</span></span>

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
> <span data-ttu-id="c207f-326">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="c207f-326">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="c207f-327">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="c207f-327">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="c207f-328">Beispielsweise würden bei einer Begrenzung des Heapverbrauchs auf 30 % die Werte für die JSON-Datei 30 und für die Umgebungsvariable 0x1E oder 1E betragen.</span><span class="sxs-lookup"><span data-stu-id="c207f-328">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="c207f-329">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="c207f-329">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="c207f-330">Konfiguriert, ob Segmente, die gelöscht werden sollen, zur späteren Verwendung auf eine Standbyliste aufgenommen oder an das Betriebssystem zurückgegeben werden</span><span class="sxs-lookup"><span data-stu-id="c207f-330">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="c207f-331">Standard: Segmente werden an das Betriebssystem zurückgegeben (`false`).</span><span class="sxs-lookup"><span data-stu-id="c207f-331">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="c207f-332">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="c207f-332">Setting name</span></span> | <span data-ttu-id="c207f-333">Werte</span><span class="sxs-lookup"><span data-stu-id="c207f-333">Values</span></span> | <span data-ttu-id="c207f-334">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="c207f-334">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c207f-335">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c207f-335">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="c207f-336">`false` – Freigabe an Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="c207f-336">`false` - release to OS</span></span><br/><span data-ttu-id="c207f-337">`true` – in Standbymodus versetzen</span><span class="sxs-lookup"><span data-stu-id="c207f-337">`true` - put on standby</span></span> | <span data-ttu-id="c207f-338">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c207f-338">.NET Core 1.0</span></span> |
| <span data-ttu-id="c207f-339">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="c207f-339">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="c207f-340">`false` – Freigabe an Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="c207f-340">`false` - release to OS</span></span><br/><span data-ttu-id="c207f-341">`true` – in Standbymodus versetzen</span><span class="sxs-lookup"><span data-stu-id="c207f-341">`true` - put on standby</span></span> | <span data-ttu-id="c207f-342">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c207f-342">.NET Core 1.0</span></span> |
| <span data-ttu-id="c207f-343">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="c207f-343">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="c207f-344">`0` – Freigabe an Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="c207f-344">`0` - release to OS</span></span><br/><span data-ttu-id="c207f-345">`1` – in Standbymodus versetzen</span><span class="sxs-lookup"><span data-stu-id="c207f-345">`1` - put on standby</span></span> | <span data-ttu-id="c207f-346">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c207f-346">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="c207f-347">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c207f-347">Examples</span></span>

<span data-ttu-id="c207f-348">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="c207f-348">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="c207f-349">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="c207f-349">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="c207f-350">Umfangreiche Seiten</span><span class="sxs-lookup"><span data-stu-id="c207f-350">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="c207f-351">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="c207f-351">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="c207f-352">Gibt an, ob umfangreiche Seiten verwendet werden sollen, wenn eine feste Heapgrenze festgelegt wird</span><span class="sxs-lookup"><span data-stu-id="c207f-352">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="c207f-353">Standard: Deaktiviert (`0`)</span><span class="sxs-lookup"><span data-stu-id="c207f-353">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="c207f-354">Dies ist eine experimentelle Einstellung.</span><span class="sxs-lookup"><span data-stu-id="c207f-354">This is an experimental setting.</span></span>

| | <span data-ttu-id="c207f-355">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="c207f-355">Setting name</span></span> | <span data-ttu-id="c207f-356">Werte</span><span class="sxs-lookup"><span data-stu-id="c207f-356">Values</span></span> | <span data-ttu-id="c207f-357">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="c207f-357">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c207f-358">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c207f-358">**runtimeconfig.json**</span></span> | <span data-ttu-id="c207f-359">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c207f-359">N/A</span></span> | <span data-ttu-id="c207f-360">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c207f-360">N/A</span></span> | <span data-ttu-id="c207f-361">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c207f-361">N/A</span></span> |
| <span data-ttu-id="c207f-362">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="c207f-362">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="c207f-363">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="c207f-363">`0` - disabled</span></span><br/><span data-ttu-id="c207f-364">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="c207f-364">`1` - enabled</span></span> | <span data-ttu-id="c207f-365">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c207f-365">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="c207f-366">Große Objekte</span><span class="sxs-lookup"><span data-stu-id="c207f-366">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="c207f-367">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="c207f-367">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="c207f-368">Konfiguriert die Garbage-Collector-Unterstützung auf 64-Bit-Plattformen für Arrays mit einer Gesamtgröße von mehr als 2 Gigabytes (GB)</span><span class="sxs-lookup"><span data-stu-id="c207f-368">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="c207f-369">Standard: Aktiviert (`1`)</span><span class="sxs-lookup"><span data-stu-id="c207f-369">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="c207f-370">Diese Option wird in einer zukünftigen Version von .NET möglicherweise veraltet sein.</span><span class="sxs-lookup"><span data-stu-id="c207f-370">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="c207f-371">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="c207f-371">Setting name</span></span> | <span data-ttu-id="c207f-372">Werte</span><span class="sxs-lookup"><span data-stu-id="c207f-372">Values</span></span> | <span data-ttu-id="c207f-373">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="c207f-373">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c207f-374">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c207f-374">**runtimeconfig.json**</span></span> | <span data-ttu-id="c207f-375">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c207f-375">N/A</span></span> | <span data-ttu-id="c207f-376">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c207f-376">N/A</span></span> | <span data-ttu-id="c207f-377">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c207f-377">N/A</span></span> |
| <span data-ttu-id="c207f-378">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="c207f-378">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="c207f-379">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="c207f-379">`1` - enabled</span></span><br/> <span data-ttu-id="c207f-380">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="c207f-380">`0` - disabled</span></span> | <span data-ttu-id="c207f-381">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c207f-381">.NET Core 1.0</span></span> |
| <span data-ttu-id="c207f-382">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="c207f-382">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="c207f-383">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="c207f-383">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="c207f-384">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="c207f-384">`1` - enabled</span></span><br/> <span data-ttu-id="c207f-385">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="c207f-385">`0` - disabled</span></span> | <span data-ttu-id="c207f-386">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="c207f-386">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="c207f-387">Großer Objektheapschwellenwert</span><span class="sxs-lookup"><span data-stu-id="c207f-387">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="c207f-388">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="c207f-388">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="c207f-389">Gibt die Größe des Schwellenwerts in Bytes an, der bewirkt, dass Objekte auf den großen Objektheap (Large Object Heap, LOH) gehen</span><span class="sxs-lookup"><span data-stu-id="c207f-389">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="c207f-390">Der Standardschwellenwert beträgt 85.000 Bytes.</span><span class="sxs-lookup"><span data-stu-id="c207f-390">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="c207f-391">Der von Ihnen festgelegte Wert muss größer sein als der Standardschwellenwert.</span><span class="sxs-lookup"><span data-stu-id="c207f-391">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="c207f-392">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="c207f-392">Setting name</span></span> | <span data-ttu-id="c207f-393">Werte</span><span class="sxs-lookup"><span data-stu-id="c207f-393">Values</span></span> | <span data-ttu-id="c207f-394">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="c207f-394">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c207f-395">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c207f-395">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="c207f-396">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="c207f-396">*decimal value*</span></span> | <span data-ttu-id="c207f-397">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c207f-397">.NET Core 1.0</span></span> |
| <span data-ttu-id="c207f-398">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="c207f-398">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="c207f-399">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="c207f-399">*hexadecimal value*</span></span> | <span data-ttu-id="c207f-400">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c207f-400">.NET Core 1.0</span></span> |
| <span data-ttu-id="c207f-401">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="c207f-401">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="c207f-402">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="c207f-402">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="c207f-403">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="c207f-403">*decimal value*</span></span> | <span data-ttu-id="c207f-404">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="c207f-404">.NET Framework 4.8</span></span> |

<span data-ttu-id="c207f-405">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c207f-405">Example:</span></span>

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
> <span data-ttu-id="c207f-406">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="c207f-406">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="c207f-407">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="c207f-407">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="c207f-408">Wenn Sie beispielsweise die Größe eines Schwellenwerts auf 120.000 Bytes festlegen, würden die Werte für die JSON-Datei 120000 und für die Umgebungsvariable 0x1D4C0 oder 1D4C0 betragen.</span><span class="sxs-lookup"><span data-stu-id="c207f-408">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="c207f-409">Eigenständige GC</span><span class="sxs-lookup"><span data-stu-id="c207f-409">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="c207f-410">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="c207f-410">COMPlus_GCName</span></span>

- <span data-ttu-id="c207f-411">Gibt einen Pfad zu der Bibliothek an, die den Garbage Collector enthält, der von der Runtime geladen werden soll</span><span class="sxs-lookup"><span data-stu-id="c207f-411">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="c207f-412">Weitere Informationen finden Sie unter [Entwurf eines eigenständigen GC-Ladeprogramms](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="c207f-412">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="c207f-413">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="c207f-413">Setting name</span></span> | <span data-ttu-id="c207f-414">Werte</span><span class="sxs-lookup"><span data-stu-id="c207f-414">Values</span></span> | <span data-ttu-id="c207f-415">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="c207f-415">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c207f-416">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c207f-416">**runtimeconfig.json**</span></span> | <span data-ttu-id="c207f-417">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c207f-417">N/A</span></span> | <span data-ttu-id="c207f-418">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c207f-418">N/A</span></span> | <span data-ttu-id="c207f-419">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c207f-419">N/A</span></span> |
| <span data-ttu-id="c207f-420">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="c207f-420">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="c207f-421">*string_path*</span><span class="sxs-lookup"><span data-stu-id="c207f-421">*string_path*</span></span> | <span data-ttu-id="c207f-422">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c207f-422">.NET Core 2.0</span></span> |
