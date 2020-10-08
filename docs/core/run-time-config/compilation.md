---
title: Kompilierungskonfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die die Funktionsweise des JIT-Compilers für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: e5f9e1245b749864787fb808527d022665197edf
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654841"
---
# <a name="run-time-configuration-options-for-compilation"></a><span data-ttu-id="13e0a-103">Laufzeitkonfigurationsoptionen für die Kompilierung</span><span class="sxs-lookup"><span data-stu-id="13e0a-103">Run-time configuration options for compilation</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="13e0a-104">Mehrstufig Kompilierung</span><span class="sxs-lookup"><span data-stu-id="13e0a-104">Tiered compilation</span></span>

- <span data-ttu-id="13e0a-105">Hiermit wird konfiguriert, ob der Just-in-Time-Compiler (JIT) eine [mehrstufige Kompilierung](../whats-new/dotnet-core-3-0.md#tiered-compilation) verwendet.</span><span class="sxs-lookup"><span data-stu-id="13e0a-105">Configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="13e0a-106">Die mehrstufige Kompilierung übergibt Methoden über zwei Ebenen:</span><span class="sxs-lookup"><span data-stu-id="13e0a-106">Tiered compilation transitions methods through two tiers:</span></span>
  - <span data-ttu-id="13e0a-107">Die erste Stufe erzeugt schneller Code ([Quick JIT](#quick-jit)) oder lädt vorkompilierten Code ([ReadyToRun](#readytorun)).</span><span class="sxs-lookup"><span data-stu-id="13e0a-107">The first tier generates code more quickly ([quick JIT](#quick-jit)) or loads pre-compiled code ([ReadyToRun](#readytorun)).</span></span>
  - <span data-ttu-id="13e0a-108">Die zweite Stufe erstellt optimierten Code im Hintergrund („Optimieren von JIT“).</span><span class="sxs-lookup"><span data-stu-id="13e0a-108">The second tier generates optimized code in the background ("optimizing JIT").</span></span>
- <span data-ttu-id="13e0a-109">In .NET Core 3.0 und höher ist die mehrstufige Kompilierung standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="13e0a-109">In .NET Core 3.0 and later, tiered compilation is enabled by default.</span></span>
- <span data-ttu-id="13e0a-110">In .NET Core 2.1 und 2.2 ist die mehrstufige Kompilierung standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="13e0a-110">In .NET Core 2.1 and 2.2, tiered compilation is disabled by default.</span></span>
- <span data-ttu-id="13e0a-111">Weitere Informationen finden Sie im [Leitfaden zur mehrstufigen Kompilierung](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="13e0a-111">For more information, see the [Tiered compilation guide](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md).</span></span>

| | <span data-ttu-id="13e0a-112">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="13e0a-112">Setting name</span></span> | <span data-ttu-id="13e0a-113">Werte</span><span class="sxs-lookup"><span data-stu-id="13e0a-113">Values</span></span> |
| - | - | - |
| <span data-ttu-id="13e0a-114">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="13e0a-114">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation` | <span data-ttu-id="13e0a-115">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="13e0a-115">`true` - enabled</span></span><br/><span data-ttu-id="13e0a-116">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="13e0a-116">`false` - disabled</span></span> |
| <span data-ttu-id="13e0a-117">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="13e0a-117">**MSBuild property**</span></span> | `TieredCompilation` | <span data-ttu-id="13e0a-118">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="13e0a-118">`true` - enabled</span></span><br/><span data-ttu-id="13e0a-119">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="13e0a-119">`false` - disabled</span></span> |
| <span data-ttu-id="13e0a-120">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="13e0a-120">**Environment variable**</span></span> | `COMPlus_TieredCompilation` | <span data-ttu-id="13e0a-121">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="13e0a-121">`1` - enabled</span></span><br/><span data-ttu-id="13e0a-122">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="13e0a-122">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="13e0a-123">Beispiele</span><span class="sxs-lookup"><span data-stu-id="13e0a-123">Examples</span></span>

<span data-ttu-id="13e0a-124">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="13e0a-124">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation": false
      }
   }
}
```

<span data-ttu-id="13e0a-125">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="13e0a-125">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilation>false</TieredCompilation>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit"></a><span data-ttu-id="13e0a-126">Quick JIT</span><span class="sxs-lookup"><span data-stu-id="13e0a-126">Quick JIT</span></span>

- <span data-ttu-id="13e0a-127">Hiermit wird konfiguriert, ob der JIT-Compiler *Quick JIT* verwendet.</span><span class="sxs-lookup"><span data-stu-id="13e0a-127">Configures whether the JIT compiler uses *quick JIT*.</span></span> <span data-ttu-id="13e0a-128">Bei Methoden, die keine Schleifen enthalten und für die kein vorkompilierter Code verfügbar ist, kompiliert Quick JIT diese schneller, aber ohne Optimierungen.</span><span class="sxs-lookup"><span data-stu-id="13e0a-128">For methods that don't contain loops and for which pre-compiled code is not available, quick JIT compiles them more quickly but without optimizations.</span></span>
- <span data-ttu-id="13e0a-129">Die Aktivierung von Quick JIT verringert die Startzeit, kann aber Code mit verminderten Leistungsmerkmalen erzeugen.</span><span class="sxs-lookup"><span data-stu-id="13e0a-129">Enabling quick JIT decreases startup time but can produce code with degraded performance characteristics.</span></span> <span data-ttu-id="13e0a-130">Zum Beispiel verwendet der Code möglicherweise mehr Stapelspeicher, kann mehr Speicher belegen und langsamer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="13e0a-130">For example, the code may use more stack space, allocate more memory, and run slower.</span></span>
- <span data-ttu-id="13e0a-131">Wenn Quick JIT deaktiviert, aber die [mehrstufige Kompilierung](#tiered-compilation) aktiviert ist, wird nur vorkompilierter Code bei der mehrstufigen Kompilierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="13e0a-131">If quick JIT is disabled but [tiered compilation](#tiered-compilation) is enabled, only pre-compiled code participates in tiered compilation.</span></span> <span data-ttu-id="13e0a-132">Wenn eine Methode nicht mit [ReadyToRun](#readytorun) vorkompiliert ist, ist das JIT-Verhalten dasselbe, als wenn die [mehrstufige Kompilierung](#tiered-compilation) deaktiviert wäre.</span><span class="sxs-lookup"><span data-stu-id="13e0a-132">If a method is not pre-compiled with [ReadyToRun](#readytorun), the JIT behavior is the same as if [tiered compilation](#tiered-compilation) were disabled.</span></span>
- <span data-ttu-id="13e0a-133">In .NET Core 3.0 und höher ist Quick JIT standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="13e0a-133">In .NET Core 3.0 and later, quick JIT is enabled by default.</span></span>
- <span data-ttu-id="13e0a-134">In .NET Core 2.1 und 2.2 ist Quick JIT standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="13e0a-134">In .NET Core 2.1 and 2.2, quick JIT is disabled by default.</span></span>

| | <span data-ttu-id="13e0a-135">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="13e0a-135">Setting name</span></span> | <span data-ttu-id="13e0a-136">Werte</span><span class="sxs-lookup"><span data-stu-id="13e0a-136">Values</span></span> |
| - | - | - |
| <span data-ttu-id="13e0a-137">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="13e0a-137">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJit` | <span data-ttu-id="13e0a-138">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="13e0a-138">`true` - enabled</span></span><br/><span data-ttu-id="13e0a-139">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="13e0a-139">`false` - disabled</span></span> |
| <span data-ttu-id="13e0a-140">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="13e0a-140">**MSBuild property**</span></span> | `TieredCompilationQuickJit` | <span data-ttu-id="13e0a-141">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="13e0a-141">`true` - enabled</span></span><br/><span data-ttu-id="13e0a-142">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="13e0a-142">`false` - disabled</span></span> |
| <span data-ttu-id="13e0a-143">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="13e0a-143">**Environment variable**</span></span> | `COMPlus_TC_QuickJit` | <span data-ttu-id="13e0a-144">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="13e0a-144">`1` - enabled</span></span><br/><span data-ttu-id="13e0a-145">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="13e0a-145">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="13e0a-146">Beispiele</span><span class="sxs-lookup"><span data-stu-id="13e0a-146">Examples</span></span>

<span data-ttu-id="13e0a-147">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="13e0a-147">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJit": false
      }
   }
}
```

<span data-ttu-id="13e0a-148">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="13e0a-148">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit-for-loops"></a><span data-ttu-id="13e0a-149">Quick JIT für Schleifen</span><span class="sxs-lookup"><span data-stu-id="13e0a-149">Quick JIT for loops</span></span>

- <span data-ttu-id="13e0a-150">Hiermit wird konfiguriert, ob der JIT-Compiler Quick JIT bei Methoden verwendet, die Schleifen enthalten.</span><span class="sxs-lookup"><span data-stu-id="13e0a-150">Configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span>
- <span data-ttu-id="13e0a-151">Die Aktivierung von Quick JIT für Schleifen kann die Startleistung verbessern.</span><span class="sxs-lookup"><span data-stu-id="13e0a-151">Enabling quick JIT for loops may improve startup performance.</span></span> <span data-ttu-id="13e0a-152">Lange Schleifen können jedoch für lange Zeiträume in weniger optimiertem Code hängen bleiben.</span><span class="sxs-lookup"><span data-stu-id="13e0a-152">However, long-running loops can get stuck in less-optimized code for long periods.</span></span>
- <span data-ttu-id="13e0a-153">Wenn [Quick JIT](#quick-jit) deaktiviert ist, hat diese Einstellung keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="13e0a-153">If [quick JIT](#quick-jit) is disabled, this setting has no effect.</span></span>
- <span data-ttu-id="13e0a-154">Wenn Sie diese Einstellung weglassen, wird Quick JIT nicht für Methoden verwendet, die Schleifen enthalten.</span><span class="sxs-lookup"><span data-stu-id="13e0a-154">If you omit this setting, quick JIT is not used for methods that contain loops.</span></span> <span data-ttu-id="13e0a-155">Dies entspricht der Einstellung des Werts auf `false`.</span><span class="sxs-lookup"><span data-stu-id="13e0a-155">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="13e0a-156">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="13e0a-156">Setting name</span></span> | <span data-ttu-id="13e0a-157">Werte</span><span class="sxs-lookup"><span data-stu-id="13e0a-157">Values</span></span> |
| - | - | - |
| <span data-ttu-id="13e0a-158">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="13e0a-158">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJitForLoops` | <span data-ttu-id="13e0a-159">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="13e0a-159">`false` - disabled</span></span><br/><span data-ttu-id="13e0a-160">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="13e0a-160">`true` - enabled</span></span> |
| <span data-ttu-id="13e0a-161">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="13e0a-161">**MSBuild property**</span></span> | `TieredCompilationQuickJitForLoops` | <span data-ttu-id="13e0a-162">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="13e0a-162">`false` - disabled</span></span><br/><span data-ttu-id="13e0a-163">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="13e0a-163">`true` - enabled</span></span> |
| <span data-ttu-id="13e0a-164">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="13e0a-164">**Environment variable**</span></span> | `COMPlus_TC_QuickJitForLoops` | <span data-ttu-id="13e0a-165">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="13e0a-165">`0` - disabled</span></span><br/><span data-ttu-id="13e0a-166">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="13e0a-166">`1` - enabled</span></span> |

### <a name="examples"></a><span data-ttu-id="13e0a-167">Beispiele</span><span class="sxs-lookup"><span data-stu-id="13e0a-167">Examples</span></span>

<span data-ttu-id="13e0a-168">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="13e0a-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJitForLoops": false
      }
   }
}
```

<span data-ttu-id="13e0a-169">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="13e0a-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
  </PropertyGroup>

</Project>
```

## <a name="readytorun"></a><span data-ttu-id="13e0a-170">ReadyToRun</span><span class="sxs-lookup"><span data-stu-id="13e0a-170">ReadyToRun</span></span>

- <span data-ttu-id="13e0a-171">Das ReadyToRun-Image konfiguriert, ob die .NET Core-Runtime vorkompilierten Code für Images mit verfügbaren ReadyToRun-Daten verwendet.</span><span class="sxs-lookup"><span data-stu-id="13e0a-171">Configures whether the .NET Core runtime uses pre-compiled code for images with available ReadyToRun data.</span></span> <span data-ttu-id="13e0a-172">Wenn Sie diese Option deaktivieren, erzwingt die Runtime eine JIT-Kompilierung für Frameworkcode.</span><span class="sxs-lookup"><span data-stu-id="13e0a-172">Disabling this option forces the runtime to JIT-compile framework code.</span></span>
- <span data-ttu-id="13e0a-173">Weitere Informationen finden Sie auf der Seite zu [Bereit zur Ausführung](../deploying/ready-to-run.md).</span><span class="sxs-lookup"><span data-stu-id="13e0a-173">For more information, see [Ready to Run](../deploying/ready-to-run.md).</span></span>
- <span data-ttu-id="13e0a-174">Wenn Sie diese Einstellung weglassen, verwendet .NET ReadyToRun-Daten, sofern verfügbar.</span><span class="sxs-lookup"><span data-stu-id="13e0a-174">If you omit this setting, .NET uses ReadyToRun data when it's available.</span></span> <span data-ttu-id="13e0a-175">Dies entspricht der Einstellung des Werts auf `1`.</span><span class="sxs-lookup"><span data-stu-id="13e0a-175">This is equivalent to setting the value to `1`.</span></span>

| | <span data-ttu-id="13e0a-176">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="13e0a-176">Setting name</span></span> | <span data-ttu-id="13e0a-177">Werte</span><span class="sxs-lookup"><span data-stu-id="13e0a-177">Values</span></span> |
| - | - | - |
| <span data-ttu-id="13e0a-178">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="13e0a-178">**Environment variable**</span></span> | `COMPlus_ReadyToRun` | <span data-ttu-id="13e0a-179">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="13e0a-179">`1` - enabled</span></span><br/><span data-ttu-id="13e0a-180">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="13e0a-180">`0` - disabled</span></span> |
