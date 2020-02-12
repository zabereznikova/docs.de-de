---
title: Kompilierungskonfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die die Funktionsweise des JIT-Compilers für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: adf1f01dba7387b89ee56784e33653d6a132c0e3
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092888"
---
# <a name="run-time-configuration-options-for-compilation"></a><span data-ttu-id="52ab0-103">Laufzeitkonfigurationsoptionen für die Kompilierung</span><span class="sxs-lookup"><span data-stu-id="52ab0-103">Run-time configuration options for compilation</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="52ab0-104">Mehrstufig Kompilierung</span><span class="sxs-lookup"><span data-stu-id="52ab0-104">Tiered compilation</span></span>

- <span data-ttu-id="52ab0-105">Hiermit wird konfiguriert, ob der Just-in-Time-Compiler (JIT) eine [mehrstufige Kompilierung](../whats-new/dotnet-core-3-0.md#tiered-compilation) verwendet.</span><span class="sxs-lookup"><span data-stu-id="52ab0-105">Configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="52ab0-106">Die mehrstufige Kompilierung übergibt Methoden über zwei Ebenen:</span><span class="sxs-lookup"><span data-stu-id="52ab0-106">Tiered compilation transitions methods through two tiers:</span></span>
  - <span data-ttu-id="52ab0-107">Die erste Stufe erzeugt schneller Code ([Quick JIT](#quick-jit)) oder lädt vorkompilierten Code ([ReadyToRun](#readytorun)).</span><span class="sxs-lookup"><span data-stu-id="52ab0-107">The first tier generates code more quickly ([quick JIT](#quick-jit)) or loads pre-compiled code ([ReadyToRun](#readytorun)).</span></span>
  - <span data-ttu-id="52ab0-108">Die zweite Stufe erstellt optimierten Code im Hintergrund („Optimieren von JIT“).</span><span class="sxs-lookup"><span data-stu-id="52ab0-108">The second tier generates optimized code in the background ("optimizing JIT").</span></span>
- <span data-ttu-id="52ab0-109">In .NET Core 3.0 und höher ist die mehrstufige Kompilierung standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="52ab0-109">In .NET Core 3.0 and later, tiered compilation is enabled by default.</span></span>
- <span data-ttu-id="52ab0-110">In .NET Core 2.1 und 2.2 ist die mehrstufige Kompilierung standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="52ab0-110">In .NET Core 2.1 and 2.2, tiered compilation is disabled by default.</span></span>
- <span data-ttu-id="52ab0-111">Weitere Informationen finden Sie im [Leitfaden zur mehrstufigen Kompilierung](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation-guide.md).</span><span class="sxs-lookup"><span data-stu-id="52ab0-111">For more information, see the [Tiered compilation guide](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation-guide.md).</span></span>

| | <span data-ttu-id="52ab0-112">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="52ab0-112">Setting name</span></span> | <span data-ttu-id="52ab0-113">Werte</span><span class="sxs-lookup"><span data-stu-id="52ab0-113">Values</span></span> |
| - | - | - |
| <span data-ttu-id="52ab0-114">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="52ab0-114">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation` | <span data-ttu-id="52ab0-115">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="52ab0-115">`true` - enabled</span></span><br/><span data-ttu-id="52ab0-116">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="52ab0-116">`false` - disabled</span></span> |
| <span data-ttu-id="52ab0-117">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="52ab0-117">**MSBuild property**</span></span> | `TieredCompilation` | <span data-ttu-id="52ab0-118">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="52ab0-118">`true` - enabled</span></span><br/><span data-ttu-id="52ab0-119">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="52ab0-119">`false` - disabled</span></span> |
| <span data-ttu-id="52ab0-120">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="52ab0-120">**Environment variable**</span></span> | `COMPlus_TieredCompilation` | <span data-ttu-id="52ab0-121">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="52ab0-121">`1` - enabled</span></span><br/><span data-ttu-id="52ab0-122">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="52ab0-122">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="52ab0-123">Beispiele</span><span class="sxs-lookup"><span data-stu-id="52ab0-123">Examples</span></span>

<span data-ttu-id="52ab0-124">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="52ab0-124">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation": false
      }
   }
}
```

<span data-ttu-id="52ab0-125">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="52ab0-125">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilation>false</TieredCompilation>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit"></a><span data-ttu-id="52ab0-126">Quick JIT</span><span class="sxs-lookup"><span data-stu-id="52ab0-126">Quick JIT</span></span>

- <span data-ttu-id="52ab0-127">Hiermit wird konfiguriert, ob der JIT-Compiler *Quick JIT* verwendet.</span><span class="sxs-lookup"><span data-stu-id="52ab0-127">Configures whether the JIT compiler uses *quick JIT*.</span></span> <span data-ttu-id="52ab0-128">Bei Methoden, die keine Schleifen enthalten und für die kein vorkompilierter Code verfügbar ist, kompiliert Quick JIT diese schneller, aber ohne Optimierungen.</span><span class="sxs-lookup"><span data-stu-id="52ab0-128">For methods that don't contain loops and for which pre-compiled code is not available, quick JIT compiles them more quickly but without optimizations.</span></span>
- <span data-ttu-id="52ab0-129">Die Aktivierung von Quick JIT verringert die Startzeit, kann aber Code mit verminderten Leistungsmerkmalen erzeugen.</span><span class="sxs-lookup"><span data-stu-id="52ab0-129">Enabling quick JIT decreases startup time but can produce code with degraded performance characteristics.</span></span> <span data-ttu-id="52ab0-130">Zum Beispiel verwendet der Code möglicherweise mehr Stapelspeicher, kann mehr Speicher belegen und langsamer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="52ab0-130">For example, the code may use more stack space, allocate more memory, and run slower.</span></span>
- <span data-ttu-id="52ab0-131">Wenn Quick JIT deaktiviert, aber die [mehrstufige Kompilierung](#tiered-compilation) aktiviert ist, wird nur vorkompilierter Code bei der mehrstufigen Kompilierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="52ab0-131">If quick JIT is disabled but [tiered compilation](#tiered-compilation) is enabled, only pre-compiled code participates in tiered compilation.</span></span> <span data-ttu-id="52ab0-132">Wenn eine Methode nicht mit [ReadyToRun](#readytorun) vorkompiliert ist, ist das JIT-Verhalten dasselbe, als wenn die [mehrstufige Kompilierung](#tiered-compilation) deaktiviert wäre.</span><span class="sxs-lookup"><span data-stu-id="52ab0-132">If a method is not pre-compiled with [ReadyToRun](#readytorun), the JIT behavior is the same as if [tiered compilation](#tiered-compilation) were disabled.</span></span>
- <span data-ttu-id="52ab0-133">In .NET Core 3.0 und höher ist Quick JIT standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="52ab0-133">In .NET Core 3.0 and later, quick JIT is enabled by default.</span></span>
- <span data-ttu-id="52ab0-134">In .NET Core 2.1 und 2.2 ist Quick JIT standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="52ab0-134">In .NET Core 2.1 and 2.2, quick JIT is disabled by default.</span></span>

| | <span data-ttu-id="52ab0-135">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="52ab0-135">Setting name</span></span> | <span data-ttu-id="52ab0-136">Werte</span><span class="sxs-lookup"><span data-stu-id="52ab0-136">Values</span></span> |
| - | - | - |
| <span data-ttu-id="52ab0-137">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="52ab0-137">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJit` | <span data-ttu-id="52ab0-138">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="52ab0-138">`true` - enabled</span></span><br/><span data-ttu-id="52ab0-139">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="52ab0-139">`false` - disabled</span></span> |
| <span data-ttu-id="52ab0-140">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="52ab0-140">**MSBuild property**</span></span> | `TieredCompilationQuickJit` | <span data-ttu-id="52ab0-141">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="52ab0-141">`true` - enabled</span></span><br/><span data-ttu-id="52ab0-142">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="52ab0-142">`false` - disabled</span></span> |
| <span data-ttu-id="52ab0-143">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="52ab0-143">**Environment variable**</span></span> | `COMPlus_TC_QuickJit` | <span data-ttu-id="52ab0-144">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="52ab0-144">`1` - enabled</span></span><br/><span data-ttu-id="52ab0-145">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="52ab0-145">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="52ab0-146">Beispiele</span><span class="sxs-lookup"><span data-stu-id="52ab0-146">Examples</span></span>

<span data-ttu-id="52ab0-147">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="52ab0-147">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJit": false
      }
   }
}
```

<span data-ttu-id="52ab0-148">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="52ab0-148">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit-for-loops"></a><span data-ttu-id="52ab0-149">Quick JIT für Schleifen</span><span class="sxs-lookup"><span data-stu-id="52ab0-149">Quick JIT for loops</span></span>

- <span data-ttu-id="52ab0-150">Hiermit wird konfiguriert, ob der JIT-Compiler Quick JIT bei Methoden verwendet, die Schleifen enthalten.</span><span class="sxs-lookup"><span data-stu-id="52ab0-150">Configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span>
- <span data-ttu-id="52ab0-151">Die Aktivierung von Quick JIT für Schleifen kann die Startleistung verbessern.</span><span class="sxs-lookup"><span data-stu-id="52ab0-151">Enabling quick JIT for loops may improve startup performance.</span></span> <span data-ttu-id="52ab0-152">Lange Schleifen können jedoch für lange Zeiträume in weniger optimiertem Code hängen bleiben.</span><span class="sxs-lookup"><span data-stu-id="52ab0-152">However, long-running loops can get stuck in less-optimized code for long periods.</span></span>
- <span data-ttu-id="52ab0-153">Wenn [Quick JIT](#quick-jit) deaktiviert ist, hat diese Einstellung keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="52ab0-153">If [quick JIT](#quick-jit) is disabled, this setting has no effect.</span></span>
- <span data-ttu-id="52ab0-154">Standard: Deaktiviert (`false`)</span><span class="sxs-lookup"><span data-stu-id="52ab0-154">Default: Disabled (`false`).</span></span>

| | <span data-ttu-id="52ab0-155">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="52ab0-155">Setting name</span></span> | <span data-ttu-id="52ab0-156">Werte</span><span class="sxs-lookup"><span data-stu-id="52ab0-156">Values</span></span> |
| - | - | - |
| <span data-ttu-id="52ab0-157">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="52ab0-157">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJitForLoops` | <span data-ttu-id="52ab0-158">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="52ab0-158">`false` - disabled</span></span><br/><span data-ttu-id="52ab0-159">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="52ab0-159">`true` - enabled</span></span> |
| <span data-ttu-id="52ab0-160">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="52ab0-160">**MSBuild property**</span></span> | `TieredCompilationQuickJitForLoops` | <span data-ttu-id="52ab0-161">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="52ab0-161">`false` - disabled</span></span><br/><span data-ttu-id="52ab0-162">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="52ab0-162">`true` - enabled</span></span> |
| <span data-ttu-id="52ab0-163">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="52ab0-163">**Environment variable**</span></span> | `COMPlus_TC_QuickJitForLoops` | <span data-ttu-id="52ab0-164">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="52ab0-164">`0` - disabled</span></span><br/><span data-ttu-id="52ab0-165">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="52ab0-165">`1` - enabled</span></span> |

### <a name="examples"></a><span data-ttu-id="52ab0-166">Beispiele</span><span class="sxs-lookup"><span data-stu-id="52ab0-166">Examples</span></span>

<span data-ttu-id="52ab0-167">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="52ab0-167">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJitForLoops": false
      }
   }
}
```

<span data-ttu-id="52ab0-168">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="52ab0-168">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJitForLoops>false</TieredCompilationQuickJitForLoops>
  </PropertyGroup>

</Project>
```

## <a name="readytorun"></a><span data-ttu-id="52ab0-169">ReadyToRun</span><span class="sxs-lookup"><span data-stu-id="52ab0-169">ReadyToRun</span></span>

- <span data-ttu-id="52ab0-170">Das ReadyToRun-Image konfiguriert, ob die .NET Core-Runtime vorkompilierten Code für Images mit verfügbaren ReadyToRun-Daten verwendet.</span><span class="sxs-lookup"><span data-stu-id="52ab0-170">Configures whether the .NET Core runtime uses pre-compiled code for images with available ReadyToRun data.</span></span> <span data-ttu-id="52ab0-171">Wenn Sie diese Option deaktivieren, erzwingt die Runtime eine JIT-Kompilierung für Frameworkcode.</span><span class="sxs-lookup"><span data-stu-id="52ab0-171">Disabling this option forces the runtime to JIT-compile framework code.</span></span>
- <span data-ttu-id="52ab0-172">Weitere Informationen finden Sie unter [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).</span><span class="sxs-lookup"><span data-stu-id="52ab0-172">For more information, see [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).</span></span>
- <span data-ttu-id="52ab0-173">Standard: Aktiviert (`1`)</span><span class="sxs-lookup"><span data-stu-id="52ab0-173">Default: Enabled (`1`).</span></span>

| | <span data-ttu-id="52ab0-174">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="52ab0-174">Setting name</span></span> | <span data-ttu-id="52ab0-175">Werte</span><span class="sxs-lookup"><span data-stu-id="52ab0-175">Values</span></span> |
| - | - | - |
| <span data-ttu-id="52ab0-176">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="52ab0-176">**Environment variable**</span></span> | `COMPlus_ReadyToRun` | <span data-ttu-id="52ab0-177">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="52ab0-177">`1` - enabled</span></span><br/><span data-ttu-id="52ab0-178">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="52ab0-178">`0` - disabled</span></span> |
