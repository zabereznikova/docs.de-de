---
title: Garbage-Collector-Konfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, um zu konfigurieren, wie der Garbage Collector Arbeitsspeicher für .NET Core-Apps verwaltet.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: 24e5c47de781e7eed5f76d2c551cac2dce1e8f05
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900094"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="feace-103">Laufzeitkonfigurationsoptionen für die Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="feace-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="feace-104">Diese Seite enthält Informationen zu Garbage-Collector-Einstellungen (GC), die zur Laufzeit geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="feace-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="feace-105">Verwenden Sie diese Einstellungen, wenn Sie versuchen, die maximale Leistung einer ausgeführten App zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="feace-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="feace-106">Die Standardwerte bieten jedoch in typischen Situationen eine optimale Leistung für die meisten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="feace-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="feace-107">Einstellungen werden auf dieser Seite in Gruppen angeordnet.</span><span class="sxs-lookup"><span data-stu-id="feace-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="feace-108">Die Einstellungen in den einzelnen Gruppen werden häufig zusammen verwendet, um ein bestimmtes Ergebnis zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="feace-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="feace-109">Diese Einstellungen können auch dynamisch von der App geändert werden, während diese ausgeführt wird, sodass die von Ihnen festgelegten Laufzeiteinstellungen überschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="feace-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="feace-110">Einige Einstellungen, wie z. B. die [Latenzebene](../../standard/garbage-collection/latency.md), werden in der Regel nur über die API zur Entwurfszeit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="feace-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="feace-111">Diese Einstellungen werden auf dieser Seite weggelassen.</span><span class="sxs-lookup"><span data-stu-id="feace-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="feace-112">Verwenden Sie für Zahlenwerte für Einstellungen in der Datei *runtimeconfig.json* die Dezimalschreibweise und für Einstellungen in der Umgebungsvariablen die Hexadezimalnotation.</span><span class="sxs-lookup"><span data-stu-id="feace-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="feace-113">Bei hexadezimalen Werten können Sie sie mit dem oder ohne das Präfix „0x“ angeben.</span><span class="sxs-lookup"><span data-stu-id="feace-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="feace-114">Varianten der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="feace-114">Flavors of garbage collection</span></span>

<span data-ttu-id="feace-115">Die zwei Hauptvarianten der Garbage Collection sind Arbeitsstation-GC und Server-GC.</span><span class="sxs-lookup"><span data-stu-id="feace-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="feace-116">Weitere Informationen zu den Unterschieden zwischen diesen beiden Varianten finden Sie unter [Grundlagen der Garbage Collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="feace-116">For more information about differences between the two, see [Fundamentals of garbage collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span></span>

<span data-ttu-id="feace-117">Die Untervarianten der Garbage Collection sind Hintergrund-GC und nicht gleichzeitige GC.</span><span class="sxs-lookup"><span data-stu-id="feace-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="feace-118">Verwenden Sie die folgenden Einstellungen, um Varianten der Garbage Collection auszuwählen:</span><span class="sxs-lookup"><span data-stu-id="feace-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="feace-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="feace-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="feace-120">Konfiguriert, ob die Anwendung die Arbeitsstation-GC oder die Server-GC verwendet</span><span class="sxs-lookup"><span data-stu-id="feace-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="feace-121">Standard: Arbeitsstation-Garbage-Collection (`false`)</span><span class="sxs-lookup"><span data-stu-id="feace-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="feace-122">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="feace-122">Setting name</span></span> | <span data-ttu-id="feace-123">Werte</span><span class="sxs-lookup"><span data-stu-id="feace-123">Values</span></span> | <span data-ttu-id="feace-124">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="feace-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="feace-125">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="feace-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="feace-126">`false` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="feace-126">`false` - workstation</span></span><br/><span data-ttu-id="feace-127">`true` – Server</span><span class="sxs-lookup"><span data-stu-id="feace-127">`true` - server</span></span> | <span data-ttu-id="feace-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="feace-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="feace-129">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="feace-129">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="feace-130">`0` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="feace-130">`0` - workstation</span></span><br/><span data-ttu-id="feace-131">`1` – Server</span><span class="sxs-lookup"><span data-stu-id="feace-131">`1` - server</span></span> | <span data-ttu-id="feace-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="feace-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="feace-133">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="feace-133">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="feace-134">GCServer</span><span class="sxs-lookup"><span data-stu-id="feace-134">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="feace-135">`false` – Arbeitsstation</span><span class="sxs-lookup"><span data-stu-id="feace-135">`false` - workstation</span></span><br/><span data-ttu-id="feace-136">`true` – Server</span><span class="sxs-lookup"><span data-stu-id="feace-136">`true` - server</span></span> |  |

<span data-ttu-id="feace-137">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="feace-137">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="feace-138">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="feace-138">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="feace-139">Konfiguriert, ob die (gleichzeitige) Hintergrund-GC aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="feace-139">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="feace-140">Standard: Aktiviert (`true`)</span><span class="sxs-lookup"><span data-stu-id="feace-140">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="feace-141">Weitere Informationen finden Sie unter [Garbage Collection im Hintergrund](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) und [Garbage Collection auf dem Server im Hintergrund](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="feace-141">For more information, see [Background garbage collection](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) and [Background server garbage collection](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span></span>

| | <span data-ttu-id="feace-142">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="feace-142">Setting name</span></span> | <span data-ttu-id="feace-143">Werte</span><span class="sxs-lookup"><span data-stu-id="feace-143">Values</span></span> | <span data-ttu-id="feace-144">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="feace-144">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="feace-145">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="feace-145">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="feace-146">`true` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="feace-146">`true` - background GC</span></span><br/><span data-ttu-id="feace-147">`false` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="feace-147">`false` - non-concurrent GC</span></span> | <span data-ttu-id="feace-148">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="feace-148">.NET Core 1.0</span></span> |
| <span data-ttu-id="feace-149">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="feace-149">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="feace-150">`true` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="feace-150">`true` - background GC</span></span><br/><span data-ttu-id="feace-151">`false` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="feace-151">`false` - non-concurrent GC</span></span> | <span data-ttu-id="feace-152">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="feace-152">.NET Core 1.0</span></span> |
| <span data-ttu-id="feace-153">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="feace-153">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="feace-154">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="feace-154">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="feace-155">`true` – Hintergrund-GC</span><span class="sxs-lookup"><span data-stu-id="feace-155">`true` - background GC</span></span><br/><span data-ttu-id="feace-156">`false` – nicht gleichzeitige GC</span><span class="sxs-lookup"><span data-stu-id="feace-156">`false` - non-concurrent GC</span></span> |  |

<span data-ttu-id="feace-157">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="feace-157">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

## <a name="manage-resource-usage"></a><span data-ttu-id="feace-158">Verwalten des Ressourceneinsatzes</span><span class="sxs-lookup"><span data-stu-id="feace-158">Manage resource usage</span></span>

<span data-ttu-id="feace-159">Verwenden Sie die in diesem Abschnitt beschriebenen Einstellungen, um die Speicher- und Prozessorauslastung des Garbage Collectors zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="feace-159">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="feace-160">Weitere Informationen zu einigen dieser Einstellungen finden Sie im Blogeintrag [Mittelweg zwischen Arbeitsstation- und Server-GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).</span><span class="sxs-lookup"><span data-stu-id="feace-160">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="feace-161">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="feace-161">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="feace-162">Schränkt die Anzahl von Heaps ein, die vom Garbage Collector erstellt werden</span><span class="sxs-lookup"><span data-stu-id="feace-162">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="feace-163">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="feace-163">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="feace-164">Wenn die GC-Prozessoraffinität aktiviert ist (Standardeinstellung), ordnet die Einstellung für die Heapanzahl den ersten `n` Prozessoren `n` GC-Heaps/-Threads zu.</span><span class="sxs-lookup"><span data-stu-id="feace-164">If GC processor affinity is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="feace-165">(Verwenden Sie die Einstellungen „affinitize mask“ (Maske zuordnen) oder „affinitize ranges“ (Bereiche zuordnen), um genau anzugeben, welche Prozessoren zugeordnet werden sollen.)</span><span class="sxs-lookup"><span data-stu-id="feace-165">(Use the affinitize mask or affinitize ranges settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="feace-166">Wenn die GC-Prozessoraffinität deaktiviert ist, wird mit dieser Einstellung die Anzahl der GC-Heaps eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="feace-166">If GC processor affinity is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="feace-167">Weitere Informationen finden Sie unter [Hinweise zu GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="feace-167">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="feace-168">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="feace-168">Setting name</span></span> | <span data-ttu-id="feace-169">Werte</span><span class="sxs-lookup"><span data-stu-id="feace-169">Values</span></span> | <span data-ttu-id="feace-170">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="feace-170">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="feace-171">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="feace-171">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="feace-172">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="feace-172">*decimal value*</span></span> | <span data-ttu-id="feace-173">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="feace-173">.NET Core 3.0</span></span> |
| <span data-ttu-id="feace-174">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="feace-174">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="feace-175">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="feace-175">*hexadecimal value*</span></span> | <span data-ttu-id="feace-176">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="feace-176">.NET Core 3.0</span></span> |
| <span data-ttu-id="feace-177">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="feace-177">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="feace-178">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="feace-178">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="feace-179">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="feace-179">*decimal value*</span></span> | <span data-ttu-id="feace-180">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="feace-180">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="feace-181">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="feace-181">Example:</span></span>

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
> <span data-ttu-id="feace-182">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="feace-182">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="feace-183">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="feace-183">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="feace-184">Für eine Einschränkung der Heapanzahl auf 16 wären die Werte beispielsweise 16 für die JSON-Datei und 0x10 oder 10 für die Umgebungsvariable.</span><span class="sxs-lookup"><span data-stu-id="feace-184">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="feace-185">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="feace-185">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="feace-186">Gibt die genauen Prozessoren an, die Garbage-Collector-Threads verwenden sollen</span><span class="sxs-lookup"><span data-stu-id="feace-186">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="feace-187">Wenn die Prozessoraffinität deaktiviert ist, indem `System.GC.NoAffinitize` auf `true` festgelegt wurde, wird diese Einstellung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="feace-187">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="feace-188">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="feace-188">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="feace-189">Der Wert ist eine Bitmaske, die die für den Prozess verfügbaren Prozessoren definiert.</span><span class="sxs-lookup"><span data-stu-id="feace-189">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="feace-190">Beispielsweise ist ein Dezimalwert von 1023 (oder ein Hexadezimalwert von 0x3FF oder 3FF bei Verwendung der Umgebungsvariablen) in Binärschreibweise 0011 1111 1111.</span><span class="sxs-lookup"><span data-stu-id="feace-190">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="feace-191">Dies gibt an, dass die ersten zehn Prozessoren verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="feace-191">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="feace-192">Geben Sie einen Dezimalwert von 1047552 (oder einen Hexadezimalwert von 0xFFC00 oder FFC00) an, der einem Binärwert von 1111 1111 1100 0000 0000 entspricht, um die nächsten zehn Prozessoren anzugeben, d. h. die Prozessoren 10 bis 19.</span><span class="sxs-lookup"><span data-stu-id="feace-192">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="feace-193">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="feace-193">Setting name</span></span> | <span data-ttu-id="feace-194">Werte</span><span class="sxs-lookup"><span data-stu-id="feace-194">Values</span></span> | <span data-ttu-id="feace-195">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="feace-195">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="feace-196">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="feace-196">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="feace-197">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="feace-197">*decimal value*</span></span> | <span data-ttu-id="feace-198">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="feace-198">.NET Core 3.0</span></span> |
| <span data-ttu-id="feace-199">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="feace-199">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="feace-200">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="feace-200">*hexadecimal value*</span></span> | <span data-ttu-id="feace-201">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="feace-201">.NET Core 3.0</span></span> |
| <span data-ttu-id="feace-202">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="feace-202">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="feace-203">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="feace-203">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="feace-204">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="feace-204">*decimal value*</span></span> | <span data-ttu-id="feace-205">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="feace-205">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="feace-206">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="feace-206">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="feace-207">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="feace-207">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="feace-208">Gibt die Liste der Prozessoren an, die für Garbage-Collector-Threads verwendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="feace-208">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="feace-209">Diese Einstellung ist `System.GC.HeapAffinitizeMask` ähnlich, mit der Ausnahme, dass Sie mehr als 64 Prozessoren angeben können.</span><span class="sxs-lookup"><span data-stu-id="feace-209">This setting is similar to `System.GC.HeapAffinitizeMask`, except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="feace-210">Stellen Sie für Windows-Betriebssysteme der Prozessornummer oder dem Prozessorbereich die entsprechende [CPU-Gruppe](/windows/win32/procthread/processor-groups) voran, z. B. „0:1-10,0:12,1:50-52,1:70“.</span><span class="sxs-lookup"><span data-stu-id="feace-210">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="feace-211">Wenn die Prozessoraffinität deaktiviert ist, indem `System.GC.NoAffinitize` auf `true` festgelegt wurde, wird diese Einstellung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="feace-211">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="feace-212">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="feace-212">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="feace-213">Weitere Informationen finden Sie unter [Optimieren der CPU-Konfiguration für GC auf Computern mit mehr als 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) im Blog von Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="feace-213">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="feace-214">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="feace-214">Setting name</span></span> | <span data-ttu-id="feace-215">Werte</span><span class="sxs-lookup"><span data-stu-id="feace-215">Values</span></span> | <span data-ttu-id="feace-216">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="feace-216">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="feace-217">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="feace-217">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="feace-218">Durch Kommas getrennte Liste mit Prozessornummern oder Bereichen von Prozessornummern</span><span class="sxs-lookup"><span data-stu-id="feace-218">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="feace-219">Unix-Beispiel: „1-10,12,50-52,70“</span><span class="sxs-lookup"><span data-stu-id="feace-219">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="feace-220">Windows-Beispiel: „0:1-10,0:12,1:50-52,1:70“</span><span class="sxs-lookup"><span data-stu-id="feace-220">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="feace-221">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="feace-221">.NET Core 3.0</span></span> |
| <span data-ttu-id="feace-222">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="feace-222">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="feace-223">Durch Kommas getrennte Liste mit Prozessornummern oder Bereichen von Prozessornummern</span><span class="sxs-lookup"><span data-stu-id="feace-223">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="feace-224">Unix-Beispiel: „1-10,12,50-52,70“</span><span class="sxs-lookup"><span data-stu-id="feace-224">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="feace-225">Windows-Beispiel: „0:1-10,0:12,1:50-52,1:70“</span><span class="sxs-lookup"><span data-stu-id="feace-225">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="feace-226">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="feace-226">.NET Core 3.0</span></span> |

<span data-ttu-id="feace-227">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="feace-227">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="feace-228">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="feace-228">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="feace-229">Konfiguriert, ob der Garbage Collector [CPU-Gruppen](/windows/win32/procthread/processor-groups) verwendet</span><span class="sxs-lookup"><span data-stu-id="feace-229">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="feace-230">Wenn ein 64-Bit-Windows-Computer über mehrere CPU-Gruppen verfügt, d. h. mehr als 64 Prozessoren vorhanden sind, dann wird durch die Aktivierung dieses Elements die Garbage Collection in allen CPU-Gruppen erweitert.</span><span class="sxs-lookup"><span data-stu-id="feace-230">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="feace-231">Der Garbage Collector verwendet alle Kerne zum Erstellen und Ausgleichen von Heaps.</span><span class="sxs-lookup"><span data-stu-id="feace-231">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="feace-232">Gilt nur für Garbage Collection des Servers auf 64-Bit-Windows-Betriebssystemen.</span><span class="sxs-lookup"><span data-stu-id="feace-232">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="feace-233">Standard: Deaktiviert (`0`)</span><span class="sxs-lookup"><span data-stu-id="feace-233">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="feace-234">Weitere Informationen finden Sie unter [Optimieren der CPU-Konfiguration für GC auf Computern mit mehr als 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) im Blog von Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="feace-234">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="feace-235">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="feace-235">Setting name</span></span> | <span data-ttu-id="feace-236">Werte</span><span class="sxs-lookup"><span data-stu-id="feace-236">Values</span></span> | <span data-ttu-id="feace-237">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="feace-237">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="feace-238">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="feace-238">**runtimeconfig.json**</span></span> | <span data-ttu-id="feace-239">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="feace-239">N/A</span></span> | <span data-ttu-id="feace-240">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="feace-240">N/A</span></span> | <span data-ttu-id="feace-241">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="feace-241">N/A</span></span> |
| <span data-ttu-id="feace-242">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="feace-242">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="feace-243">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="feace-243">`0` - disabled</span></span><br/><span data-ttu-id="feace-244">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="feace-244">`1` - enabled</span></span> | <span data-ttu-id="feace-245">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="feace-245">.NET Core 1.0</span></span> |
| <span data-ttu-id="feace-246">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="feace-246">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="feace-247">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="feace-247">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="feace-248">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="feace-248">`false` - disabled</span></span><br/><span data-ttu-id="feace-249">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="feace-249">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="feace-250">Aktivieren Sie die Option [Thread_UseAllCpuGroups-Element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md), um die Common Language Runtime (CLR) so zu konfigurieren, dass auch Threads aus dem Threadpool in allen CPU-Gruppen verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="feace-250">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="feace-251">Für .NET Core-Apps können Sie diese Option aktivieren, indem Sie den Wert der Umgebungsvariablen `COMPlus_Thread_UseAllCpuGroups` auf `1` setzen.</span><span class="sxs-lookup"><span data-stu-id="feace-251">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="feace-252">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="feace-252">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="feace-253">Gibt an, ob Garbage-Collection-Threads Prozessoren *zugeordnet* werden sollen.</span><span class="sxs-lookup"><span data-stu-id="feace-253">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="feace-254">Einen GC-Thread zuzuordnen, bedeutet, dass dieser nur auf der jeweiligen CPU ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="feace-254">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="feace-255">Für jeden GC-Thread wird ein Heap erstellt.</span><span class="sxs-lookup"><span data-stu-id="feace-255">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="feace-256">Gilt nur für die Garbage Collection des Servers.</span><span class="sxs-lookup"><span data-stu-id="feace-256">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="feace-257">Standard: Garbage-Collection-Threads werden Prozessoren zugeordnet (`false`).</span><span class="sxs-lookup"><span data-stu-id="feace-257">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="feace-258">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="feace-258">Setting name</span></span> | <span data-ttu-id="feace-259">Werte</span><span class="sxs-lookup"><span data-stu-id="feace-259">Values</span></span> | <span data-ttu-id="feace-260">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="feace-260">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="feace-261">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="feace-261">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="feace-262">`false` – zuordnen</span><span class="sxs-lookup"><span data-stu-id="feace-262">`false` - affinitize</span></span><br/><span data-ttu-id="feace-263">`true` – nicht zuordnen</span><span class="sxs-lookup"><span data-stu-id="feace-263">`true` - don't affinitize</span></span> | <span data-ttu-id="feace-264">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="feace-264">.NET Core 3.0</span></span> |
| <span data-ttu-id="feace-265">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="feace-265">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="feace-266">`0` – zuordnen</span><span class="sxs-lookup"><span data-stu-id="feace-266">`0` - affinitize</span></span><br/><span data-ttu-id="feace-267">`1` – nicht zuordnen</span><span class="sxs-lookup"><span data-stu-id="feace-267">`1` - don't affinitize</span></span> | <span data-ttu-id="feace-268">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="feace-268">.NET Core 3.0</span></span> |
| <span data-ttu-id="feace-269">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="feace-269">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="feace-270">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="feace-270">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="feace-271">`false` – zuordnen</span><span class="sxs-lookup"><span data-stu-id="feace-271">`false` - affinitize</span></span><br/><span data-ttu-id="feace-272">`true` – nicht zuordnen</span><span class="sxs-lookup"><span data-stu-id="feace-272">`true` - don't affinitize</span></span> | <span data-ttu-id="feace-273">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="feace-273">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="feace-274">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="feace-274">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="feace-275">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="feace-275">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="feace-276">Gibt die maximale Commitgröße in Bytes für den GC-Heap und die GC-Buchhaltung an</span><span class="sxs-lookup"><span data-stu-id="feace-276">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>

| | <span data-ttu-id="feace-277">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="feace-277">Setting name</span></span> | <span data-ttu-id="feace-278">Werte</span><span class="sxs-lookup"><span data-stu-id="feace-278">Values</span></span> | <span data-ttu-id="feace-279">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="feace-279">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="feace-280">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="feace-280">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="feace-281">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="feace-281">*decimal value*</span></span> | <span data-ttu-id="feace-282">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="feace-282">.NET Core 3.0</span></span> |
| <span data-ttu-id="feace-283">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="feace-283">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="feace-284">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="feace-284">*hexadecimal value*</span></span> | <span data-ttu-id="feace-285">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="feace-285">.NET Core 3.0</span></span> |

<span data-ttu-id="feace-286">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="feace-286">Example:</span></span>

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
> <span data-ttu-id="feace-287">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="feace-287">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="feace-288">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="feace-288">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="feace-289">Wenn Sie beispielsweise eine feste Heapgrenze von 200 MiB festlegen, würden die Werte für die JSON-Datei 209715200 und für die Umgebungsvariable 0xc800000 oder C800000 betragen.</span><span class="sxs-lookup"><span data-stu-id="feace-289">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="feace-290">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="feace-290">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="feace-291">Gibt den GC-Heapverbrauch in Prozent des Gesamtspeichers an</span><span class="sxs-lookup"><span data-stu-id="feace-291">Specifies the GC heap usage as a percentage of the total memory.</span></span>

| | <span data-ttu-id="feace-292">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="feace-292">Setting name</span></span> | <span data-ttu-id="feace-293">Werte</span><span class="sxs-lookup"><span data-stu-id="feace-293">Values</span></span> | <span data-ttu-id="feace-294">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="feace-294">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="feace-295">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="feace-295">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="feace-296">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="feace-296">*decimal value*</span></span> | <span data-ttu-id="feace-297">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="feace-297">.NET Core 3.0</span></span> |
| <span data-ttu-id="feace-298">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="feace-298">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="feace-299">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="feace-299">*hexadecimal value*</span></span> | <span data-ttu-id="feace-300">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="feace-300">.NET Core 3.0</span></span> |

<span data-ttu-id="feace-301">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="feace-301">Example:</span></span>

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
> <span data-ttu-id="feace-302">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="feace-302">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="feace-303">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="feace-303">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="feace-304">Beispielsweise würden bei einer Begrenzung des Heapverbrauchs auf 30 % die Werte für die JSON-Datei 30 und für die Umgebungsvariable 0x1E oder 1E betragen.</span><span class="sxs-lookup"><span data-stu-id="feace-304">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="feace-305">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="feace-305">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="feace-306">Konfiguriert, ob Segmente, die gelöscht werden sollen, zur späteren Verwendung auf eine Standbyliste aufgenommen oder an das Betriebssystem zurückgegeben werden</span><span class="sxs-lookup"><span data-stu-id="feace-306">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="feace-307">Standard: Segmente werden an das Betriebssystem zurückgegeben (`false`).</span><span class="sxs-lookup"><span data-stu-id="feace-307">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="feace-308">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="feace-308">Setting name</span></span> | <span data-ttu-id="feace-309">Werte</span><span class="sxs-lookup"><span data-stu-id="feace-309">Values</span></span> | <span data-ttu-id="feace-310">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="feace-310">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="feace-311">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="feace-311">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="feace-312">`false` – Freigabe an Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="feace-312">`false` - release to OS</span></span><br/><span data-ttu-id="feace-313">`true` – in Standbymodus versetzen</span><span class="sxs-lookup"><span data-stu-id="feace-313">`true` - put on standby</span></span>| <span data-ttu-id="feace-314">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="feace-314">.NET Core 1.0</span></span> |
| <span data-ttu-id="feace-315">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="feace-315">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="feace-316">`0` – Freigabe an Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="feace-316">`0` - release to OS</span></span><br/><span data-ttu-id="feace-317">`1` – in Standbymodus versetzen</span><span class="sxs-lookup"><span data-stu-id="feace-317">`1` - put on standby</span></span> | <span data-ttu-id="feace-318">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="feace-318">.NET Core 1.0</span></span> |

<span data-ttu-id="feace-319">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="feace-319">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

## <a name="large-pages"></a><span data-ttu-id="feace-320">Umfangreiche Seiten</span><span class="sxs-lookup"><span data-stu-id="feace-320">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="feace-321">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="feace-321">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="feace-322">Gibt an, ob umfangreiche Seiten verwendet werden sollen, wenn eine feste Heapgrenze festgelegt wird</span><span class="sxs-lookup"><span data-stu-id="feace-322">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="feace-323">Standard: Deaktiviert (`0`)</span><span class="sxs-lookup"><span data-stu-id="feace-323">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="feace-324">Dies ist eine experimentelle Einstellung.</span><span class="sxs-lookup"><span data-stu-id="feace-324">This is an experimental setting.</span></span>

| | <span data-ttu-id="feace-325">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="feace-325">Setting name</span></span> | <span data-ttu-id="feace-326">Werte</span><span class="sxs-lookup"><span data-stu-id="feace-326">Values</span></span> | <span data-ttu-id="feace-327">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="feace-327">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="feace-328">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="feace-328">**runtimeconfig.json**</span></span> | <span data-ttu-id="feace-329">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="feace-329">N/A</span></span> | <span data-ttu-id="feace-330">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="feace-330">N/A</span></span> | <span data-ttu-id="feace-331">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="feace-331">N/A</span></span> |
| <span data-ttu-id="feace-332">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="feace-332">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="feace-333">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="feace-333">`0` - disabled</span></span><br/><span data-ttu-id="feace-334">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="feace-334">`1` - enabled</span></span> | <span data-ttu-id="feace-335">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="feace-335">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="feace-336">Große Objekte</span><span class="sxs-lookup"><span data-stu-id="feace-336">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="feace-337">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="feace-337">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="feace-338">Konfiguriert die Garbage-Collector-Unterstützung auf 64-Bit-Plattformen für Arrays mit einer Gesamtgröße von mehr als 2 Gigabytes (GB)</span><span class="sxs-lookup"><span data-stu-id="feace-338">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="feace-339">Standard: Aktiviert (`1`)</span><span class="sxs-lookup"><span data-stu-id="feace-339">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="feace-340">Diese Option wird in einer zukünftigen Version von .NET möglicherweise veraltet sein.</span><span class="sxs-lookup"><span data-stu-id="feace-340">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="feace-341">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="feace-341">Setting name</span></span> | <span data-ttu-id="feace-342">Werte</span><span class="sxs-lookup"><span data-stu-id="feace-342">Values</span></span> | <span data-ttu-id="feace-343">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="feace-343">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="feace-344">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="feace-344">**runtimeconfig.json**</span></span> | <span data-ttu-id="feace-345">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="feace-345">N/A</span></span> | <span data-ttu-id="feace-346">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="feace-346">N/A</span></span> | <span data-ttu-id="feace-347">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="feace-347">N/A</span></span> |
| <span data-ttu-id="feace-348">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="feace-348">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="feace-349">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="feace-349">`1` - enabled</span></span><br/> <span data-ttu-id="feace-350">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="feace-350">`0` - disabled</span></span> | <span data-ttu-id="feace-351">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="feace-351">.NET Core 1.0</span></span> |
| <span data-ttu-id="feace-352">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="feace-352">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="feace-353">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="feace-353">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="feace-354">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="feace-354">`1` - enabled</span></span><br/> <span data-ttu-id="feace-355">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="feace-355">`0` - disabled</span></span> | <span data-ttu-id="feace-356">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="feace-356">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="feace-357">Großer Objektheapschwellenwert</span><span class="sxs-lookup"><span data-stu-id="feace-357">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="feace-358">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="feace-358">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="feace-359">Gibt die Größe des Schwellenwerts in Bytes an, der bewirkt, dass Objekte auf den großen Objektheap (Large Object Heap, LOH) gehen</span><span class="sxs-lookup"><span data-stu-id="feace-359">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="feace-360">Der Standardschwellenwert beträgt 85.000 Bytes.</span><span class="sxs-lookup"><span data-stu-id="feace-360">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="feace-361">Der von Ihnen festgelegte Wert muss größer sein als der Standardschwellenwert.</span><span class="sxs-lookup"><span data-stu-id="feace-361">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="feace-362">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="feace-362">Setting name</span></span> | <span data-ttu-id="feace-363">Werte</span><span class="sxs-lookup"><span data-stu-id="feace-363">Values</span></span> | <span data-ttu-id="feace-364">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="feace-364">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="feace-365">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="feace-365">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="feace-366">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="feace-366">*decimal value*</span></span> | <span data-ttu-id="feace-367">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="feace-367">.NET Core 1.0</span></span> |
| <span data-ttu-id="feace-368">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="feace-368">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="feace-369">*Hexadezimalwert*</span><span class="sxs-lookup"><span data-stu-id="feace-369">*hexadecimal value*</span></span> | <span data-ttu-id="feace-370">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="feace-370">.NET Core 1.0</span></span> |
| <span data-ttu-id="feace-371">**app.config für .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="feace-371">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="feace-372">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="feace-372">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="feace-373">*Dezimalwert*</span><span class="sxs-lookup"><span data-stu-id="feace-373">*decimal value*</span></span> | <span data-ttu-id="feace-374">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="feace-374">.NET Framework 4.8</span></span> |

<span data-ttu-id="feace-375">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="feace-375">Example:</span></span>

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
> <span data-ttu-id="feace-376">Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="feace-376">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="feace-377">Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="feace-377">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="feace-378">Wenn Sie beispielsweise die Größe eines Schwellenwerts auf 120.000 Bytes festlegen, würden die Werte für die JSON-Datei 120000 und für die Umgebungsvariable 0x1D4C0 oder 1D4C0 betragen.</span><span class="sxs-lookup"><span data-stu-id="feace-378">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="feace-379">Eigenständige GC</span><span class="sxs-lookup"><span data-stu-id="feace-379">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="feace-380">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="feace-380">COMPlus_GCName</span></span>

- <span data-ttu-id="feace-381">Gibt einen Pfad zu der Bibliothek an, die den Garbage Collector enthält, der von der Runtime geladen werden soll</span><span class="sxs-lookup"><span data-stu-id="feace-381">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="feace-382">Weitere Informationen finden Sie unter [Entwurf eines eigenständigen GC-Ladeprogramms](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="feace-382">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="feace-383">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="feace-383">Setting name</span></span> | <span data-ttu-id="feace-384">Werte</span><span class="sxs-lookup"><span data-stu-id="feace-384">Values</span></span> | <span data-ttu-id="feace-385">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="feace-385">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="feace-386">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="feace-386">**runtimeconfig.json**</span></span> | <span data-ttu-id="feace-387">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="feace-387">N/A</span></span> | <span data-ttu-id="feace-388">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="feace-388">N/A</span></span> | <span data-ttu-id="feace-389">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="feace-389">N/A</span></span> |
| <span data-ttu-id="feace-390">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="feace-390">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="feace-391">*string_path*</span><span class="sxs-lookup"><span data-stu-id="feace-391">*string_path*</span></span> | <span data-ttu-id="feace-392">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="feace-392">.NET Core 2.0</span></span> |
