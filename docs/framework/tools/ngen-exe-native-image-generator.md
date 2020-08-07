---
title: Ngen.exe (Native Image Generator)
description: Sehen Sie sich „Ngen.exe“ an, den Generator für native Images. Verbessern Sie die Leistung verwalteter Anwendungen, indem Sie native Images erstellen und im lokalen nativen Imagecache installieren.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Native Image Generator
- images [.NET Framework], native
- side-by-side execution, native images
- assemblies [.NET Framework], native image
- Ngen.exe
- native image generation
- native image cache
- publisher policy applied for native images
- invalid images
- BypassNGenAttribute
- System.Runtime.BypassNGenAttribute
ms.assetid: 44bf97aa-a9a4-4eba-9a0d-cfaa6fc53a66
ms.openlocfilehash: ae86aed773a9a13f102b1ad111cac5a3ee563508
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517268"
---
# <a name="ngenexe-native-image-generator"></a><span data-ttu-id="52adc-104">Ngen.exe (Native Image Generator)</span><span class="sxs-lookup"><span data-stu-id="52adc-104">Ngen.exe (Native Image Generator)</span></span>

<span data-ttu-id="52adc-105">Native Image Generator (Ngen.exe) ist ein Tool zur Leistungsoptimierung verwalteter Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="52adc-105">The Native Image Generator (Ngen.exe) is a tool that improves the performance of managed applications.</span></span> <span data-ttu-id="52adc-106">Mit "Ngen.exe" können Sie systemeigene Images erstellen, also Dateien mit kompiliertem prozessorspezifischem Computercode, die daraufhin im Cache für systemeigene Images auf dem lokalen Computer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-106">Ngen.exe creates native images, which are files containing compiled processor-specific machine code, and installs them into the native image cache on the local computer.</span></span> <span data-ttu-id="52adc-107">Die Laufzeit kann systemeigene Abbilder aus dem Cache nutzen und muss nicht den JIT (Just-In-Time)-Compiler verwenden, um die ursprüngliche Assembly zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="52adc-107">The runtime can use native images from the cache instead of using the just-in-time (JIT) compiler to compile the original assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="52adc-108">„Ngen. exe“ kompiliert native Images für Assemblys, die nur .NET Framework als Ziel verwenden.</span><span class="sxs-lookup"><span data-stu-id="52adc-108">Ngen.exe compiles native images for assemblies that target the .NET Framework only.</span></span> <span data-ttu-id="52adc-109">Der äquivalente Generator für native Images für .NET Core ist [CrossGen](https://github.com/dotnet/runtime/blob/master/docs/workflow/building/coreclr/crossgen.md).</span><span class="sxs-lookup"><span data-stu-id="52adc-109">The equivalent native image generator for .NET Core is [CrossGen](https://github.com/dotnet/runtime/blob/master/docs/workflow/building/coreclr/crossgen.md).</span></span>

<span data-ttu-id="52adc-110">Änderungen an „Ngen.exe“ in .NET Framework 4:</span><span class="sxs-lookup"><span data-stu-id="52adc-110">Changes to Ngen.exe in the .NET Framework 4:</span></span>

- <span data-ttu-id="52adc-111">Mit "Ngen.exe"können nun Assemblys mit vollständiger Vertrauenswürdigkeit kompiliert werden, und die Codezugriffssicherheitsrichtlinie (CAS) wird nicht mehr ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="52adc-111">Ngen.exe now compiles assemblies with full trust, and code access security (CAS) policy is no longer evaluated.</span></span>

- <span data-ttu-id="52adc-112">Systemeigene Images, die mit "Ngen.exe" generiert werden, können nicht mehr in Anwendungen geladen werden, die mit partieller Vertrauenswürdigkeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-112">Native images that are generated with Ngen.exe can no longer be loaded into applications that are running in partial trust.</span></span>

<span data-ttu-id="52adc-113">Änderungen an "Ngen.exe" in .NET Framework Version 2.0:</span><span class="sxs-lookup"><span data-stu-id="52adc-113">Changes to Ngen.exe in the .NET Framework version 2.0:</span></span>

- <span data-ttu-id="52adc-114">Mit der Installation einer Assembly werden auch ihre Abhängigkeiten installiert, und die Syntax von "Ngen.exe" wird vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="52adc-114">Installing an assembly also installs its dependencies, simplifying the syntax of Ngen.exe.</span></span>

- <span data-ttu-id="52adc-115">Systemeigene Images können jetzt für mehrere Anwendungsdomänen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-115">Native images can now be shared across application domains.</span></span>

- <span data-ttu-id="52adc-116">Die neue Aktion `update` erstellt ungültig gewordene Images neu.</span><span class="sxs-lookup"><span data-stu-id="52adc-116">A new action, `update`, re-creates images that have been invalidated.</span></span>

- <span data-ttu-id="52adc-117">Sie können Aktionen verzögern und von einem Dienst ausführen lassen, der die Leerlaufzeiten auf dem Computer nutzt, um Images zu generieren und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="52adc-117">Actions can be deferred for execution by a service that uses idle time on the computer to generate and install images.</span></span>

- <span data-ttu-id="52adc-118">Einige Ursachen für die Ungültigkeit von Images wurden eliminiert.</span><span class="sxs-lookup"><span data-stu-id="52adc-118">Some causes of image invalidation have been eliminated.</span></span>

<span data-ttu-id="52adc-119">Unter Windows 8 finden Sie weitere Informationen unter [Aufgabe zur Generierung nativer Images](#native-image-task).</span><span class="sxs-lookup"><span data-stu-id="52adc-119">On Windows 8, see [Native Image Task](#native-image-task).</span></span>

<span data-ttu-id="52adc-120">Weitere Informationen zur Verwendung von „Ngen.exe“ und des Diensts für native Images finden Sie unter [Dienst für systemeigene Abbilder](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="52adc-120">For additional information on using Ngen.exe and the native image service, see [Native Image Service](#native-image-service).</span></span>

> [!NOTE]
> <span data-ttu-id="52adc-121">Die Syntax von „Ngen.exe“ für die Versionen 1.0 und 1.1 von .NET Framework finden Sie unter [Legacysyntax des Native Image Generator (Ngen.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms165073(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="52adc-121">Ngen.exe syntax for versions 1.0 and 1.1 of the .NET Framework can be found in [Native Image Generator (Ngen.exe) Legacy Syntax](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms165073(v=vs.100)).</span></span>

<span data-ttu-id="52adc-122">Dieses Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="52adc-122">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="52adc-123">Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="52adc-123">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="52adc-124">Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="52adc-124">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="52adc-125">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="52adc-125">At the command prompt, type the following:</span></span>

## <a name="syntax"></a><span data-ttu-id="52adc-126">Syntax</span><span class="sxs-lookup"><span data-stu-id="52adc-126">Syntax</span></span>

```console
ngen action [options]
```

```console
ngen /? | /help
```

## <a name="actions"></a><span data-ttu-id="52adc-127">Aktionen</span><span class="sxs-lookup"><span data-stu-id="52adc-127">Actions</span></span>

<span data-ttu-id="52adc-128">In der folgenden Tabelle wird die Syntax für jede einzelne `action` dargestellt.</span><span class="sxs-lookup"><span data-stu-id="52adc-128">The following table shows the syntax of each `action`.</span></span> <span data-ttu-id="52adc-129">Beschreibungen der einzelnen Teile einer `action` finden Sie in den Tabellen [Argumente](#ArgumentTable), [Prioritätsebenen](#PriorityTable), [Szenarien](#ScenarioTable) und [Konfigurationen](#ConfigTable).</span><span class="sxs-lookup"><span data-stu-id="52adc-129">For descriptions of the individual parts of an `action`, see the [Arguments](#ArgumentTable), [Priority Levels](#PriorityTable), [Scenarios](#ScenarioTable), and [Config](#ConfigTable) tables.</span></span> <span data-ttu-id="52adc-130">In der Tabelle [Optionen](#OptionTable) werden die `options` und die Hilfeschalter beschrieben.</span><span class="sxs-lookup"><span data-stu-id="52adc-130">The [Options](#OptionTable) table describes the `options` and the help switches.</span></span>

|<span data-ttu-id="52adc-131">Aktion</span><span class="sxs-lookup"><span data-stu-id="52adc-131">Action</span></span>|<span data-ttu-id="52adc-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52adc-132">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="52adc-133">`install` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`] [`/queue`[`:`{`1`&#124;`2`&#124;`3`}]]</span><span class="sxs-lookup"><span data-stu-id="52adc-133">`install` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`] [`/queue`[`:`{`1`&#124;`2`&#124;`3`}]]</span></span>|<span data-ttu-id="52adc-134">Generiert systemeigene Images für eine Assembly und ihre Abhängigkeiten und installiert die Images im Cache für systemeigene Images.</span><span class="sxs-lookup"><span data-stu-id="52adc-134">Generate native images for an assembly and its dependencies and install the images in the native image cache.</span></span><br /><br /> <span data-ttu-id="52adc-135">Wenn `/queue` angegeben wird, wird die Aktion in die Warteschlange des Diensts für systemeigene Images gestellt.</span><span class="sxs-lookup"><span data-stu-id="52adc-135">If `/queue` is specified, the action is queued for the native image service.</span></span> <span data-ttu-id="52adc-136">Die Standardpriorität ist 3.</span><span class="sxs-lookup"><span data-stu-id="52adc-136">The default priority is 3.</span></span> <span data-ttu-id="52adc-137">Informationen hierzu finden Sie in der Tabelle [Prioritätsebenen](#PriorityTable).</span><span class="sxs-lookup"><span data-stu-id="52adc-137">See the [Priority Levels](#PriorityTable) table.</span></span>|
|<span data-ttu-id="52adc-138">`uninstall` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`]</span><span class="sxs-lookup"><span data-stu-id="52adc-138">`uninstall` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`]</span></span>|<span data-ttu-id="52adc-139">Löscht die systemeigenen Images einer Assembly und ihre Abhängigkeiten aus dem Cache für systemeigene Images.</span><span class="sxs-lookup"><span data-stu-id="52adc-139">Delete the native images of an assembly and its dependencies from the native image cache.</span></span><br /><br /> <span data-ttu-id="52adc-140">Verwenden Sie zum Deinstallieren eines einzelnen Images und seiner Abhängigkeiten dieselben Befehlszeilenargumente wie beim Installieren des Images.</span><span class="sxs-lookup"><span data-stu-id="52adc-140">To uninstall a single image and its dependencies, use the same command-line arguments that were used to install the image.</span></span> <span data-ttu-id="52adc-141">**Hinweis**:  Ab .NET Framework 4 wird die Aktion `uninstall` \* nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="52adc-141">**Note:**  Starting with the .NET Framework 4, the action `uninstall` \* is no longer supported.</span></span>|
|<span data-ttu-id="52adc-142">`update` [`/queue`]</span><span class="sxs-lookup"><span data-stu-id="52adc-142">`update` [`/queue`]</span></span>|<span data-ttu-id="52adc-143">Aktualisiert systemeigene Images, die ungültig geworden sind.</span><span class="sxs-lookup"><span data-stu-id="52adc-143">Update native images that have become invalid.</span></span><br /><br /> <span data-ttu-id="52adc-144">Wenn `/queue` angegeben wird, werden die Aktualisierungen in die Warteschlange des Diensts für systemeigene Images gestellt.</span><span class="sxs-lookup"><span data-stu-id="52adc-144">If `/queue` is specified, the updates are queued for the native image service.</span></span> <span data-ttu-id="52adc-145">Aktualisierungen werden immer mit Priorität 3 geplant, sodass sie zu Leerlaufzeiten des Computers ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-145">Updates are always scheduled at priority 3, so they run when the computer is idle.</span></span>|
|<span data-ttu-id="52adc-146">`display` [`assemblyName` &#124; `assemblyPath`]</span><span class="sxs-lookup"><span data-stu-id="52adc-146">`display` [`assemblyName` &#124; `assemblyPath`]</span></span>|<span data-ttu-id="52adc-147">Zeigt den Zustand der systemeigenen Images für eine Assembly und ihre Abhängigkeiten an.</span><span class="sxs-lookup"><span data-stu-id="52adc-147">Display the state of the native images for an assembly and its dependencies.</span></span><br /><br /> <span data-ttu-id="52adc-148">Wenn kein Argument angegeben wird, wird der gesamte Inhalt des Caches für native Images angezeigt.</span><span class="sxs-lookup"><span data-stu-id="52adc-148">If no argument is supplied, everything in the native image cache is displayed.</span></span>|
|<span data-ttu-id="52adc-149">`executeQueuedItems` [<code>1&#124;2&#124;3</code>]</span><span class="sxs-lookup"><span data-stu-id="52adc-149">`executeQueuedItems` [<code>1&#124;2&#124;3</code>]</span></span><br /><br /> <span data-ttu-id="52adc-150">- oder -</span><span class="sxs-lookup"><span data-stu-id="52adc-150">-or-</span></span><br /><br /> <span data-ttu-id="52adc-151">`eqi` [1&#124;2&#124;3]</span><span class="sxs-lookup"><span data-stu-id="52adc-151">`eqi` [1&#124;2&#124;3]</span></span>|<span data-ttu-id="52adc-152">Führt die in der Warteschlange enthaltenen Kompilierungsaufträge aus.</span><span class="sxs-lookup"><span data-stu-id="52adc-152">Execute queued compilation jobs.</span></span><br /><br /> <span data-ttu-id="52adc-153">Wenn eine Priorität angegeben wird, werden Kompilierungsaufträge mit höherer oder gleicher Priorität ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="52adc-153">If a priority is specified, compilation jobs with greater or equal priority are executed.</span></span> <span data-ttu-id="52adc-154">Wenn keine Priorität angegeben wird, werden alle in die Warteschlange gestellten Kompilierungsaufträge ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="52adc-154">If no priority is specified, all queued compilation jobs are executed.</span></span>|
|<span data-ttu-id="52adc-155">`queue` {`pause` &#124; `continue` &#124; `status`}</span><span class="sxs-lookup"><span data-stu-id="52adc-155">`queue` {`pause` &#124; `continue` &#124; `status`}</span></span>|<span data-ttu-id="52adc-156">Hält den Dienst für systemeigene Images an, setzt den angehaltenen Dienst fort bzw. fragt den Dienststatus ab.</span><span class="sxs-lookup"><span data-stu-id="52adc-156">Pause the native image service, allow the paused service to continue, or query the status of the service.</span></span>|

<a name="ArgumentTable"></a>

## <a name="arguments"></a><span data-ttu-id="52adc-157">Argumente</span><span class="sxs-lookup"><span data-stu-id="52adc-157">Arguments</span></span>

|<span data-ttu-id="52adc-158">Argument</span><span class="sxs-lookup"><span data-stu-id="52adc-158">Argument</span></span>|<span data-ttu-id="52adc-159">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52adc-159">Description</span></span>|
|--------------|-----------------|
|`assemblyName`|<span data-ttu-id="52adc-160">Der vollständige Anzeigename der Assembly.</span><span class="sxs-lookup"><span data-stu-id="52adc-160">The full display name of the assembly.</span></span> <span data-ttu-id="52adc-161">Beispielsweise `"myAssembly, Version=2.0.0.0, Culture=neutral, PublicKeyToken=0038abc9deabfle5"`.</span><span class="sxs-lookup"><span data-stu-id="52adc-161">For example, `"myAssembly, Version=2.0.0.0, Culture=neutral, PublicKeyToken=0038abc9deabfle5"`.</span></span> <span data-ttu-id="52adc-162">**Hinweis**:  Sie können einen partiellen Assemblynamen wie `myAssembly` für die `display`-Aktion und die `uninstall`-Aktion angeben.</span><span class="sxs-lookup"><span data-stu-id="52adc-162">**Note:**  You can supply a partial assembly name, such as `myAssembly`, for the `display` and `uninstall` actions.</span></span> <br /><br /> <span data-ttu-id="52adc-163">In jeder Befehlszeile von "Ngen.exe" kann nur eine Assembly angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-163">Only one assembly can be specified per Ngen.exe command line.</span></span>|
|`assemblyPath`|<span data-ttu-id="52adc-164">Der explizite Pfad der Assembly.</span><span class="sxs-lookup"><span data-stu-id="52adc-164">The explicit path of the assembly.</span></span> <span data-ttu-id="52adc-165">Sie können einen vollständigen oder einen relativen Pfad angeben.</span><span class="sxs-lookup"><span data-stu-id="52adc-165">You can specify a full or relative path.</span></span><br /><br /> <span data-ttu-id="52adc-166">Wenn Sie einen Dateinamen ohne Pfad angeben, muss sich die Assembly im aktuellen Verzeichnis befinden.</span><span class="sxs-lookup"><span data-stu-id="52adc-166">If you specify a file name without a path, the assembly must be located in the current directory.</span></span><br /><br /> <span data-ttu-id="52adc-167">In jeder Befehlszeile von "Ngen.exe" kann nur eine Assembly angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-167">Only one assembly can be specified per Ngen.exe command line.</span></span>|

<a name="PriorityTable"></a>

## <a name="priority-levels"></a><span data-ttu-id="52adc-168">Prioritätsebenen</span><span class="sxs-lookup"><span data-stu-id="52adc-168">Priority Levels</span></span>

|<span data-ttu-id="52adc-169">Priorität</span><span class="sxs-lookup"><span data-stu-id="52adc-169">Priority</span></span>|<span data-ttu-id="52adc-170">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52adc-170">Description</span></span>|
|--------------|-----------------|
|`1`|<span data-ttu-id="52adc-171">Systemeigene Images werden sofort generiert und installiert, ohne dass auf Leerlaufzeit gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="52adc-171">Native images are generated and installed immediately, without waiting for idle time.</span></span>|
|`2`|<span data-ttu-id="52adc-172">Systemeigene Images werden ohne Warten auf Leerlaufzeit generiert und installiert, aber nachdem alle Aktionen mit Priorität 1 (und ihre Abhängigkeiten) abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="52adc-172">Native images are generated and installed without waiting for idle time, but after all priority 1 actions (and their dependencies) have completed.</span></span>|
|`3`|<span data-ttu-id="52adc-173">Systemeigene Images werden installiert, wenn der Dienst für systemeigene Images feststellt, dass sich der Computer im Leerlauf befindet.</span><span class="sxs-lookup"><span data-stu-id="52adc-173">Native images are installed when the native image service detects that the computer is idle.</span></span> <span data-ttu-id="52adc-174">Weitere Informationen finden Sie unter [Dienst für systemeigene Abbilder](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="52adc-174">See [Native Image Service](#native-image-service).</span></span>|

<a name="ScenarioTable"></a>

## <a name="scenarios"></a><span data-ttu-id="52adc-175">Szenarien</span><span class="sxs-lookup"><span data-stu-id="52adc-175">Scenarios</span></span>

|<span data-ttu-id="52adc-176">Szenario</span><span class="sxs-lookup"><span data-stu-id="52adc-176">Scenario</span></span>|<span data-ttu-id="52adc-177">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="52adc-177">Description</span></span>|
|--------------|-----------------|
|`/Debug`|<span data-ttu-id="52adc-178">Generiert systemeigene Images, die unter einem Debugger verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="52adc-178">Generate native images that can be used under a debugger.</span></span>|
|`/Profile`|<span data-ttu-id="52adc-179">Generiert systemeigene Images, die unter einem Profiler verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="52adc-179">Generate native images that can be used under a profiler.</span></span>|
|`/NoDependencies`|<span data-ttu-id="52adc-180">Generiert die Mindestanzahl systemeigener Images, die von den angegebenen Einsatzszenarien benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-180">Generate the minimum number of native images required by the specified scenario options.</span></span>|

<a name="ConfigTable"></a>

## <a name="config"></a><span data-ttu-id="52adc-181">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="52adc-181">Config</span></span>

|<span data-ttu-id="52adc-182">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="52adc-182">Configuration</span></span>|<span data-ttu-id="52adc-183">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="52adc-183">Description</span></span>|
|-------------------|-----------------|
|<span data-ttu-id="52adc-184">`/ExeConfig:` `exePath`</span><span class="sxs-lookup"><span data-stu-id="52adc-184">`/ExeConfig:` `exePath`</span></span>|<span data-ttu-id="52adc-185">Verwendet die Konfiguration der angegebenen ausführbaren Assembly.</span><span class="sxs-lookup"><span data-stu-id="52adc-185">Use the configuration of the specified executable assembly.</span></span><br /><br /> <span data-ttu-id="52adc-186">"Ngen.exe" muss beim Binden an Abhängigkeiten die gleichen Entscheidungen wie das Ladeprogramm treffen.</span><span class="sxs-lookup"><span data-stu-id="52adc-186">Ngen.exe needs to make the same decisions as the loader when binding to dependencies.</span></span> <span data-ttu-id="52adc-187">Wenn eine freigegebene Komponente zur Laufzeit mit der <xref:System.Reflection.Assembly.Load%2A>-Methode geladen wird, bestimmt die Konfigurationsdatei der Anwendung die Abhängigkeiten, die für die freigegebene Komponente geladen werden, beispielsweise die Version einer zu ladenden Abhängigkeit.</span><span class="sxs-lookup"><span data-stu-id="52adc-187">When a shared component is loaded at run time, using the <xref:System.Reflection.Assembly.Load%2A> method, the application's configuration file determines the dependencies that are loaded for the shared component — for example, the version of a dependency that is loaded.</span></span> <span data-ttu-id="52adc-188">Über den Schalter `/ExeConfig` erhält "Ngen.exe" Anweisungen dazu, welche Abhängigkeiten zur Laufzeit geladen werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-188">The `/ExeConfig` switch gives Ngen.exe guidance on which dependencies would be loaded at run time.</span></span>|
|<span data-ttu-id="52adc-189">`/AppBase:` `directoryPath`</span><span class="sxs-lookup"><span data-stu-id="52adc-189">`/AppBase:` `directoryPath`</span></span>|<span data-ttu-id="52adc-190">Verwendet das angegebene Verzeichnis beim Suchen nach Abhängigkeiten als Anwendungsbasis.</span><span class="sxs-lookup"><span data-stu-id="52adc-190">When locating dependencies, use the specified directory as the application base.</span></span>|

<a name="OptionTable"></a>

## <a name="options"></a><span data-ttu-id="52adc-191">Optionen</span><span class="sxs-lookup"><span data-stu-id="52adc-191">Options</span></span>

|<span data-ttu-id="52adc-192">Option</span><span class="sxs-lookup"><span data-stu-id="52adc-192">Option</span></span>|<span data-ttu-id="52adc-193">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52adc-193">Description</span></span>|
|------------|-----------------|
|`/nologo`|<span data-ttu-id="52adc-194">Unterdrückt die Anzeige des Startbanners von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="52adc-194">Suppress the Microsoft startup banner display.</span></span>|
|`/silent`|<span data-ttu-id="52adc-195">Unterdrückt die Anzeige von Erfolgsmeldungen.</span><span class="sxs-lookup"><span data-stu-id="52adc-195">Suppress the display of success messages.</span></span>|
|`/verbose`|<span data-ttu-id="52adc-196">Zeigt ausführliche Informationen zum Debuggen an.</span><span class="sxs-lookup"><span data-stu-id="52adc-196">Display detailed information for debugging.</span></span> <span data-ttu-id="52adc-197">**Hinweis**:  Aufgrund von Beschränkungen im Betriebssystem werden in Windows 98 und Windows Millennium Edition durch diese Option nicht so viele zusätzliche Informationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="52adc-197">**Note:**  Due to operating system limitations, this option does not display as much additional information on Windows 98 and Windows Millennium Edition.</span></span>|
|<span data-ttu-id="52adc-198">`/help`, `/?`</span><span class="sxs-lookup"><span data-stu-id="52adc-198">`/help`, `/?`</span></span>|<span data-ttu-id="52adc-199">Zeigt die Befehlssyntax sowie Optionen für das aktuelle Release an.</span><span class="sxs-lookup"><span data-stu-id="52adc-199">Display command syntax and options for the current release.</span></span>|

## <a name="remarks"></a><span data-ttu-id="52adc-200">Hinweise</span><span class="sxs-lookup"><span data-stu-id="52adc-200">Remarks</span></span>

<span data-ttu-id="52adc-201">Zum Ausführen von "Ngen.exe" müssen Sie über Administratorrechte verfügen.</span><span class="sxs-lookup"><span data-stu-id="52adc-201">To run Ngen.exe, you must have administrative privileges.</span></span>

> [!CAUTION]
> <span data-ttu-id="52adc-202">Führen Sie "Ngen.exe" nicht für Assemblys aus, die nicht vollständig vertrauenswürdig sind.</span><span class="sxs-lookup"><span data-stu-id="52adc-202">Do not run Ngen.exe on assemblies that are not fully trusted.</span></span> <span data-ttu-id="52adc-203">Ab .NET Framework 4 kompiliert „Ngen.exe“ Assemblys mit vollständiger Vertrauenswürdigkeit, und die Codezugriffssicherheitsrichtlinie (Code Access Security, CAS) wird nicht mehr ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="52adc-203">Starting with the .NET Framework 4, Ngen.exe compiles assemblies with full trust, and code access security (CAS) policy is no longer evaluated.</span></span>

<span data-ttu-id="52adc-204">Ab .NET Framework 4 können die systemeigenen Images, die mit „Ngen.exe“ generiert werden, nicht mehr in Anwendungen geladen werden, die mit partieller Vertrauenswürdigkeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-204">Starting with the .NET Framework 4, the native images that are generated with Ngen.exe can no longer be loaded into applications that are running in partial trust.</span></span> <span data-ttu-id="52adc-205">Stattdessen wird der Just-In-Time (JIT)-Compiler aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="52adc-205">Instead, the just-in-time (JIT) compiler is invoked.</span></span>

<span data-ttu-id="52adc-206">Mit „Ngen.exe“ werden native Images für die mit dem Argument `assemblyname` für die Aktion `install` angegebene Assembly und alle ihre Abhängigkeiten generiert.</span><span class="sxs-lookup"><span data-stu-id="52adc-206">Ngen.exe generates native images for the assembly specified by the `assemblyname` argument to the `install` action and all its dependencies.</span></span> <span data-ttu-id="52adc-207">Abhängigkeiten werden anhand von Verweisen im Assemblymanifest bestimmt.</span><span class="sxs-lookup"><span data-stu-id="52adc-207">Dependencies are determined from references in the assembly manifest.</span></span> <span data-ttu-id="52adc-208">Eine Abhängigkeit müssen Sie nur in einem Szenario separat installieren, in dem die Abhängigkeit von der Anwendung mittels Reflektion geladen wird, z. B. durch Aufrufen der <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="52adc-208">The only scenario in which you need to install a dependency separately is when the application loads it using reflection, for example by calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52adc-209">Verwenden Sie die <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>-Methode nicht für systemeigene Images.</span><span class="sxs-lookup"><span data-stu-id="52adc-209">Do not use the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method with native images.</span></span> <span data-ttu-id="52adc-210">Ein mit dieser Methode geladenes Image kann nicht von anderen Assemblys im Ausführungskontext verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-210">An image loaded with this method cannot be used by other assemblies in the execution context.</span></span>

<span data-ttu-id="52adc-211">Ngen.exe erfasst die Anzahl von Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="52adc-211">Ngen.exe maintains a count on dependencies.</span></span> <span data-ttu-id="52adc-212">Angenommen, `MyAssembly.exe` und `YourAssembly.exe` sind im Cache für systemeigene Images installiert, und beide verfügen über Verweise auf `OurDependency.dll`.</span><span class="sxs-lookup"><span data-stu-id="52adc-212">For example, suppose `MyAssembly.exe` and `YourAssembly.exe` are both installed in the native image cache, and both have references to `OurDependency.dll`.</span></span> <span data-ttu-id="52adc-213">Wenn `MyAssembly.exe` deinstalliert wird, wird `OurDependency.dll` nicht deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="52adc-213">If `MyAssembly.exe` is uninstalled, `OurDependency.dll` is not uninstalled.</span></span> <span data-ttu-id="52adc-214">Die Deinstallation erfolgt erst, wenn auch `YourAssembly.exe` deinstalliert wird.</span><span class="sxs-lookup"><span data-stu-id="52adc-214">It is only removed when `YourAssembly.exe` is also uninstalled.</span></span>

<span data-ttu-id="52adc-215">Wenn Sie ein systemeigenes Image für eine Assembly im globalen Assemblycache generieren, geben Sie deren Anzeigenamen an.</span><span class="sxs-lookup"><span data-stu-id="52adc-215">If you are generating a native image for an assembly in the global assembly cache, specify its display name.</span></span> <span data-ttu-id="52adc-216">Siehe <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="52adc-216">See <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="52adc-217">Die mit Ngen.exe generierten systemeigenen Images können für andere Anwendungsdomänen freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-217">The native images that Ngen.exe generates can be shared across application domains.</span></span> <span data-ttu-id="52adc-218">Dies bedeutet, dass "Ngen.exe" in Anwendungsszenarien verwendet werden kann, in denen Assemblys von mehreren Anwendungsdomänen gemeinsam genutzt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="52adc-218">This means you can use Ngen.exe in application scenarios that require assemblies to be shared across application domains.</span></span> <span data-ttu-id="52adc-219">So geben Sie Domänenneutralität an:</span><span class="sxs-lookup"><span data-stu-id="52adc-219">To specify domain neutrality:</span></span>

- <span data-ttu-id="52adc-220">Wenden Sie das <xref:System.LoaderOptimizationAttribute>-Attribut auf die Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="52adc-220">Apply the <xref:System.LoaderOptimizationAttribute> attribute to your application.</span></span>

- <span data-ttu-id="52adc-221">Legen Sie die <xref:System.AppDomainSetup.LoaderOptimization%2A?displayProperty=nameWithType>-Eigenschaft fest, wenn Sie Setupinformationen für eine neue Anwendungsdomäne erstellen.</span><span class="sxs-lookup"><span data-stu-id="52adc-221">Set the <xref:System.AppDomainSetup.LoaderOptimization%2A?displayProperty=nameWithType> property when you create setup information for a new application domain.</span></span>

<span data-ttu-id="52adc-222">Verwenden Sie immer domänenneutralen Code, wenn Sie dieselbe Assembly in mehrere Anwendungsdomänen laden.</span><span class="sxs-lookup"><span data-stu-id="52adc-222">Always use domain-neutral code when loading the same assembly into multiple application domains.</span></span> <span data-ttu-id="52adc-223">Wenn ein systemeigenes Image in eine nicht gemeinsam genutzte Anwendungsdomäne geladen wird, nachdem es in eine gemeinsam genutzte Domäne geladen wurde, kann es nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-223">If a native image is loaded into a nonshared application domain after having been loaded into a shared domain, it cannot be used.</span></span>

> [!NOTE]
> <span data-ttu-id="52adc-224">Domänenneutraler Code kann nicht entladen werden, und die Leistung ist möglicherweise etwas vermindert, insbesondere beim Zugriff auf statische Member.</span><span class="sxs-lookup"><span data-stu-id="52adc-224">Domain-neutral code cannot be unloaded, and performance may be slightly slower, particularly when accessing static members.</span></span>

<span data-ttu-id="52adc-225">Inhalt im Abschnitt „Hinweise“:</span><span class="sxs-lookup"><span data-stu-id="52adc-225">In this Remarks section:</span></span>

- [<span data-ttu-id="52adc-226">Generieren von Images für verschiedene Szenarien</span><span class="sxs-lookup"><span data-stu-id="52adc-226">Generating images for different scenarios</span></span>](#Scenarios)

- [<span data-ttu-id="52adc-227">Wann sollten native Images verwendet werden?</span><span class="sxs-lookup"><span data-stu-id="52adc-227">Determining when to Use native images</span></span>](#WhenToUse)

  - [<span data-ttu-id="52adc-228">Verbesserte Arbeitsspeichernutzung</span><span class="sxs-lookup"><span data-stu-id="52adc-228">Improved memory use</span></span>](#Memory)

  - [<span data-ttu-id="52adc-229">Schnellerer Anwendungsstart</span><span class="sxs-lookup"><span data-stu-id="52adc-229">Faster application startup</span></span>](#Startup)

  - [<span data-ttu-id="52adc-230">Zusammenfassung der Überlegungen zur Verwendung</span><span class="sxs-lookup"><span data-stu-id="52adc-230">Summary of usage considerations</span></span>](#UsageSummary)

- [<span data-ttu-id="52adc-231">Wichtigkeit der Basisadressen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="52adc-231">Importance of assembly base addresses</span></span>](#BaseAddresses)

- [<span data-ttu-id="52adc-232">Feste Bindung</span><span class="sxs-lookup"><span data-stu-id="52adc-232">Hard binding</span></span>](#HardBinding)

  - [<span data-ttu-id="52adc-233">Angeben eines Bindungshinweises für eine Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="52adc-233">Specifying a binding hint for a dependency</span></span>](#DependencyHint)

  - [<span data-ttu-id="52adc-234">Angeben eines standardmäßigen Bindungshinweises für eine Assembly</span><span class="sxs-lookup"><span data-stu-id="52adc-234">Specifying a default binding hint for an assembly</span></span>](#AssemblyHint)

- [<span data-ttu-id="52adc-235">Verzögertes Verarbeiten</span><span class="sxs-lookup"><span data-stu-id="52adc-235">Deferred processing</span></span>](#Deferred)

- [<span data-ttu-id="52adc-236">Native Images und JIT-Kompilierung</span><span class="sxs-lookup"><span data-stu-id="52adc-236">Native images and JIT compilation</span></span>](#JITCompilation)

  - [<span data-ttu-id="52adc-237">Ungültige Images</span><span class="sxs-lookup"><span data-stu-id="52adc-237">Invalid images</span></span>](#InvalidImages)

- [<span data-ttu-id="52adc-238">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="52adc-238">Troubleshooting</span></span>](#Troubleshooting)

  - [<span data-ttu-id="52adc-239">Assembly Binding Log Viewer</span><span class="sxs-lookup"><span data-stu-id="52adc-239">Assembly Binding Log Viewer</span></span>](#Fusion)

  - [<span data-ttu-id="52adc-240">Der Assistent für verwaltetes Debuggen (jitCompilationStart)</span><span class="sxs-lookup"><span data-stu-id="52adc-240">The JITCompilationStart managed debugging assistant</span></span>](#MDA)

  - [<span data-ttu-id="52adc-241">Deaktivieren der Generierung nativer Images</span><span class="sxs-lookup"><span data-stu-id="52adc-241">Opting out of native image generation</span></span>](#OptOut)

<a name="Scenarios"></a>

## <a name="generating-images-for-----different-scenarios"></a><span data-ttu-id="52adc-242">Generieren von Images für verschiedene Szenarien</span><span class="sxs-lookup"><span data-stu-id="52adc-242">Generating images for     different scenarios</span></span>

<span data-ttu-id="52adc-243">Nachdem Sie ein natives Image für eine Assembly generiert haben, wird dieses bei jedem Ausführen der Assembly automatisch von der Laufzeit gesucht und verwendet.</span><span class="sxs-lookup"><span data-stu-id="52adc-243">After you have generated a native image for an assembly, the runtime automatically attempts to locate and use this native   image each time it runs the assembly.</span></span> <span data-ttu-id="52adc-244">Je nach Anwendungsszenario können mehrere Images generiert werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-244">Multiple images can be generated, depending on usage scenarios.</span></span>

<span data-ttu-id="52adc-245">Wenn Sie beispielsweise eine Assembly in einem Debugging- oder Profilerstellungsszenario ausführen, sucht die Laufzeit nach einem systemeigenen Image, das mit der Option `/Debug` bzw. `/Profile` generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="52adc-245">For example, if you run an assembly in a debugging or profiling scenario, the runtime looks for a native image that was generated with the `/Debug` or `/Profile` options.</span></span> <span data-ttu-id="52adc-246">Wenn kein entsprechendes systemeigenes Image gefunden wurde, wird die Laufzeit auf die standardmäßige JIT-Kompilierung zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="52adc-246">If it is unable to find a matching native image, the runtime reverts to standard JIT compilation.</span></span> <span data-ttu-id="52adc-247">Die einzige Möglichkeit zum Debuggen systemeigener Images besteht darin, ein systemeigenes Image mit der Option `/Debug` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="52adc-247">The only way to debug native images is to create a native image with the `/Debug` option.</span></span>

<span data-ttu-id="52adc-248">Die Aktion `uninstall` erkennt auch Szenarien, sodass Sie alle oder nur ausgewählte Szenarien deinstallieren können.</span><span class="sxs-lookup"><span data-stu-id="52adc-248">The `uninstall` action also recognize scenarios, so you can uninstall all scenarios or only selected scenarios.</span></span>

<a name="WhenToUse"></a>

## <a name="determining-when-to-use-native-images"></a><span data-ttu-id="52adc-249">Wann sollten native Images verwendet werden?</span><span class="sxs-lookup"><span data-stu-id="52adc-249">Determining when to Use native images</span></span>

<span data-ttu-id="52adc-250">Systemeigene Images bieten Leistungsverbesserungen in zwei Bereichen: verbesserte Arbeitsspeichernutzung und beschleunigte Startzeit.</span><span class="sxs-lookup"><span data-stu-id="52adc-250">Native images can provide performance improvements in two areas: improved memory use and reduced startup time.</span></span>

> [!NOTE]
> <span data-ttu-id="52adc-251">Die Leistung systemeigener Images hängt von einer Reihe von Faktoren ab, die die Leistungsanalyse erschweren. Dazu gehören Code- und Datenzugriffsmuster, die Anzahl der über Modulgrenzen hinweg ausgeführten Aufrufe und die Anzahl der bereits von anderen Anwendungen geladenen Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="52adc-251">Performance of native images depends on a number of factors that make analysis difficult, such as code and data access patterns, how many calls are made across module boundaries, and how many dependencies have already been loaded by other applications.</span></span> <span data-ttu-id="52adc-252">Die einzige Möglichkeit, einen eventuellen Nutzen systemeigener Images für Ihre Anwendung zu erkennen, besteht darin, gründliche Leistungsmessungen in den wichtigsten Bereitstellungsszenarien vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="52adc-252">The only way to determine whether native images benefit your application is by careful performance measurements in your key deployment scenarios.</span></span>

<a name="Memory"></a>

### <a name="improved-memory-use"></a><span data-ttu-id="52adc-253">Verbesserte Arbeitsspeichernutzung</span><span class="sxs-lookup"><span data-stu-id="52adc-253">Improved memory use</span></span>

<span data-ttu-id="52adc-254">Systemeigene Images können die Arbeitsspeichernutzung entscheidend verbessern, wenn Code zwischen Prozessen freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="52adc-254">Native images can significantly improve memory use when code is shared between processes.</span></span> <span data-ttu-id="52adc-255">Systemeigene Images werden in Form von Windows PE-Dateien gespeichert. Eine einzelne Version einer DLL-Datei kann also von mehreren Prozessen gemeinsam genutzt werden. Vom JIT-Compiler erstellter systemeigener Code wird dagegen im privaten Speicher abgelegt und kann nicht freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-255">Native images are Windows PE files, so a single copy of a .dll file can be shared by multiple processes; by contrast, native code produced by the JIT compiler is stored in private memory and cannot be shared.</span></span>

<span data-ttu-id="52adc-256">Unter Terminaldiensten ausgeführte Anwendungen können ebenfalls von freigegebenen Codepages profitieren.</span><span class="sxs-lookup"><span data-stu-id="52adc-256">Applications that are run under terminal services can also benefit from shared code pages.</span></span>

<span data-ttu-id="52adc-257">Wenn der JIT-Compiler nicht geladen wird, wird außerdem pro Anwendungsinstanz eine feste Speichergröße eingespart.</span><span class="sxs-lookup"><span data-stu-id="52adc-257">In addition, not loading the JIT compiler saves a fixed amount of memory for each application instance.</span></span>

<a name="Startup"></a>

### <a name="faster-application-startup"></a><span data-ttu-id="52adc-258">Schnellerer Anwendungsstart</span><span class="sxs-lookup"><span data-stu-id="52adc-258">Faster application startup</span></span>

<span data-ttu-id="52adc-259">Durch das Vorkompilieren von Assemblys mit Ngen.exe kann die Startzeit einiger Anwendungen beschleunigt werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-259">Precompiling assemblies with Ngen.exe can improve the startup time for some applications.</span></span> <span data-ttu-id="52adc-260">Zeit lässt sich im Allgemeinen dadurch gewinnen, dass Anwendungen Komponentenassemblys gemeinsam nutzen, denn nachdem die erste Anwendung gestartet wurde, sind die freigegebenen Komponenten für nachfolgende Anwendungen bereits geladen.</span><span class="sxs-lookup"><span data-stu-id="52adc-260">In general, gains can be made when applications share component assemblies because after the first application has been started the shared components are already loaded for subsequent applications.</span></span> <span data-ttu-id="52adc-261">Bei einem Kaltstart, bei dem alle Assemblys einer Anwendung von der Festplatte geladen werden müssen, fällt der Nutzen systemeigener Images geringer aus, da die Zeit für den Zugriff auf die Festplatte den Zeitgewinn wieder aufhebt.</span><span class="sxs-lookup"><span data-stu-id="52adc-261">Cold startup, in which all the assemblies in an application must be loaded from the hard disk, does not benefit as much from native images because the hard disk access time predominates.</span></span>

<span data-ttu-id="52adc-262">Die feste Bindung kann die Startzeit verlangsamen, da alle Images, die eine feste Bindung an die Hauptassembly der Anwendung aufweisen, gleichzeitig geladen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="52adc-262">Hard binding can affect startup time, because all images that are hard bound to the main application assembly must be loaded at the same time.</span></span>

> [!NOTE]
> <span data-ttu-id="52adc-263">Vor .NET Framework 3.5 Service Pack 1 müssen Sie freigegebene, mit starken Bezeichnungen benannte Komponenten in den globalen Assemblycache einschließen, da das Ladeprogramm für Assemblys mit starkem Namen, die nicht im globalen Assemblycache enthalten sind, eine zusätzliche Überprüfung ausführt. Dadurch wird jegliche Beschleunigung der Startzeit aufgrund der Verwendung systemeigener Images wieder zunichte gemacht.</span><span class="sxs-lookup"><span data-stu-id="52adc-263">Before the .NET Framework 3.5 Service Pack 1, you should put shared, strong-named components in the global assembly cache, because the loader performs extra validation on strong-named assemblies that are not in the global assembly cache, effectively eliminating any improvement in startup time gained by using native images.</span></span> <span data-ttu-id="52adc-264">Aufgrund von Optimierungen, die in .NET Framework 3.5 SP 1 eingeführt wurden, wurden zusätzliche Überprüfungen überflüssig.</span><span class="sxs-lookup"><span data-stu-id="52adc-264">Optimizations that were introduced in the .NET Framework 3.5 SP1 removed the extra validation.</span></span>

<a name="UsageSummary"></a>

### <a name="summary-of-usage-considerations"></a><span data-ttu-id="52adc-265">Zusammenfassung der Überlegungen zur Verwendung</span><span class="sxs-lookup"><span data-stu-id="52adc-265">Summary of usage considerations</span></span>

<span data-ttu-id="52adc-266">Anhand der folgenden allgemeinen und anwendungsspezifischen Überlegungen können Sie feststellen, ob es sich lohnt, systemeigene Images für die Anwendung auszuwerten:</span><span class="sxs-lookup"><span data-stu-id="52adc-266">The following general considerations and application considerations may assist you in deciding whether to undertake the effort of evaluating native images for your application:</span></span>

- <span data-ttu-id="52adc-267">Systemeigene Images werden schneller geladen als MSIL, da dafür zahlreiche Startaktivitäten, z. B. JIT-Kompilierung und Überprüfungen der Typsicherheit, nicht mehr notwendig sind.</span><span class="sxs-lookup"><span data-stu-id="52adc-267">Native images load faster than MSIL because they eliminate the need for many startup activities, such as JIT compilation and type-safety verification.</span></span>

- <span data-ttu-id="52adc-268">Systemeigene Images erfordern kleinere anfängliche Workingsets, da der JIT-Compiler nicht benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="52adc-268">Native images require a smaller initial working set because there is no need for the JIT compiler.</span></span>

- <span data-ttu-id="52adc-269">Systemeigene Images ermöglichen die gemeinsame Codenutzung durch Prozesse.</span><span class="sxs-lookup"><span data-stu-id="52adc-269">Native images enable code sharing between processes.</span></span>

- <span data-ttu-id="52adc-270">Für systemeigene Images wird mehr Festplattenspeicher als für MSIL-Assemblys benötigt, und für ihre Generierung ist möglicherweise wesentlich mehr Zeit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="52adc-270">Native images require more hard disk space than MSIL assemblies and may require considerable time to generate.</span></span>

- <span data-ttu-id="52adc-271">Systemeigene Images müssen verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-271">Native images must be maintained.</span></span>

  - <span data-ttu-id="52adc-272">Images müssen neu generiert werden, wenn die ursprüngliche Assembly oder eine ihrer Abhängigkeiten gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="52adc-272">Images need to be regenerated when the original assembly or one of its dependencies is serviced.</span></span>

  - <span data-ttu-id="52adc-273">Für eine einzelne Assembly sind möglicherweise mehrere systemeigene Images zur Verwendung in verschiedenen Anwendungen oder verschiedenen Szenarien erforderlich.</span><span class="sxs-lookup"><span data-stu-id="52adc-273">A single assembly may need multiple native images for use in different applications or different scenarios.</span></span> <span data-ttu-id="52adc-274">Beispielsweise können die Konfigurationsinformationen in zwei Anwendungen zu unterschiedlichen Bindungsentscheidungen für dieselbe abhängige Assembly führen.</span><span class="sxs-lookup"><span data-stu-id="52adc-274">For example, the configuration information in two applications might result in different binding decisions for the same dependent assembly.</span></span>

  - <span data-ttu-id="52adc-275">Systemeigene Images müssen von einem Administrator generiert werden, d. h. ausgehend von einem Windows-Konto der Administratorgruppe.</span><span class="sxs-lookup"><span data-stu-id="52adc-275">Native images must be generated by an administrator; that is, from a Windows account in the Administrators group.</span></span>

<span data-ttu-id="52adc-276">Zusätzlich zu diesen allgemeinen Überlegungen muss bei der Frage, ob systemeigene Images einen Leistungsgewinn bringen, auch die Art der Anwendung berücksichtigt werden:</span><span class="sxs-lookup"><span data-stu-id="52adc-276">In addition to these general considerations, the nature of your application must be considered when determining whether native images might provide a performance benefit:</span></span>

- <span data-ttu-id="52adc-277">Wenn die Anwendung in einer Umgebung ausgeführt wird, in der zahlreiche freigegebene Komponenten verwendet werden, können die Komponenten bei Verwendung systemeigener Images von mehreren Prozessen gemeinsam genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-277">If your application runs in an environment that uses many shared components, native images allow the components to be shared by multiple processes.</span></span>

- <span data-ttu-id="52adc-278">Wenn die Anwendung mehrere Anwendungsdomänen verwendet, ermöglichen systemeigene Images die gemeinsame Nutzung von Codepages zwischen Domänen.</span><span class="sxs-lookup"><span data-stu-id="52adc-278">If your application uses multiple application domains, native images allow code pages to be shared across domains.</span></span>

    > [!NOTE]
    > <span data-ttu-id="52adc-279">In .NET Framework Version 1.0 und 1.1 können systemeigene Images nicht zwischen Anwendungsdomänen freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-279">In the .NET Framework versions 1.0 and 1.1, native images cannot be shared across application domains.</span></span> <span data-ttu-id="52adc-280">Dies trifft auf Version 2.0 oder höher nicht zu.</span><span class="sxs-lookup"><span data-stu-id="52adc-280">This is not the case in version 2.0 or later.</span></span>

- <span data-ttu-id="52adc-281">Wenn die Anwendung unter Terminalserver ausgeführt wird, lassen systemeigene Images die Freigabe von Codepages zu.</span><span class="sxs-lookup"><span data-stu-id="52adc-281">If your application will be run under Terminal Server, native images allow sharing of code pages.</span></span>

- <span data-ttu-id="52adc-282">Bei umfangreicheren Anwendungen ist die Kompilierung in systemeigene Images normalerweise von Vorteil;</span><span class="sxs-lookup"><span data-stu-id="52adc-282">Large applications generally benefit from compilation to native images.</span></span> <span data-ttu-id="52adc-283">bei kleineren Anwendungen dagegen nicht.</span><span class="sxs-lookup"><span data-stu-id="52adc-283">Small applications generally do not benefit.</span></span>

- <span data-ttu-id="52adc-284">Bei Anwendungen mit langer Laufzeit weist die JIT-Kompilierung zur Laufzeit eine etwas bessere Leistung als systemeigene Images auf.</span><span class="sxs-lookup"><span data-stu-id="52adc-284">For long-running applications, run-time JIT compilation performs slightly better than native images.</span></span> <span data-ttu-id="52adc-285">(Die feste Bindung kann diesen Leistungsunterschied in gewissem Umfang abschwächen.)</span><span class="sxs-lookup"><span data-stu-id="52adc-285">(Hard binding can mitigate this performance difference to some degree.)</span></span>

<a name="BaseAddresses"></a>

## <a name="importance-of-assembly-base-addresses"></a><span data-ttu-id="52adc-286">Wichtigkeit der Basisadressen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="52adc-286">Importance of assembly base addresses</span></span>

<span data-ttu-id="52adc-287">Da es sich bei systemeigenen Images um Windows PE-Dateien handelt, unterliegen sie im Hinblick auf die Zurücksetzung denselben Voraussetzungen wie andere ausführbare Dateien.</span><span class="sxs-lookup"><span data-stu-id="52adc-287">Because native images are Windows PE files, they are subject to the same rebasing issues as other executable files.</span></span> <span data-ttu-id="52adc-288">Die Leistungseinbußen infolge der Umsetzung treten bei der festen Bindung sogar noch stärker hervor.</span><span class="sxs-lookup"><span data-stu-id="52adc-288">The performance cost of relocation is even more pronounced if hard binding is employed.</span></span>

<span data-ttu-id="52adc-289">Verwenden Sie die geeignete Compileroption zum Festlegen der Basisadresse für die Assembly, um die Basisadresse für ein systemeigenes Image anzugeben.</span><span class="sxs-lookup"><span data-stu-id="52adc-289">To set the base address for a native image, use the appropriate option of your compiler to set the base address for the assembly.</span></span> <span data-ttu-id="52adc-290">Von "Ngen.exe" wird diese Basisadresse für das systemeigene Image verwendet.</span><span class="sxs-lookup"><span data-stu-id="52adc-290">Ngen.exe uses this base address for the native image.</span></span>

> [!NOTE]
> <span data-ttu-id="52adc-291">Systemeigene Images sind größer als die verwalteten Assemblys, aus denen sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="52adc-291">Native images are larger than the managed assemblies from which they were created.</span></span> <span data-ttu-id="52adc-292">Basisadressen müssen unter Berücksichtigung dieses Größenunterschieds berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-292">Base addresses must be calculated to allow for these larger sizes.</span></span>

<span data-ttu-id="52adc-293">Mit einem Tool wie "dumpbin.exe" können Sie die bevorzugte Basisadresse eines systemeigenen Images anzeigen.</span><span class="sxs-lookup"><span data-stu-id="52adc-293">You can use a tool such as dumpbin.exe to view the preferred base address of a native image.</span></span>

<a name="HardBinding"></a>

## <a name="hard-binding"></a><span data-ttu-id="52adc-294">Feste Bindung</span><span class="sxs-lookup"><span data-stu-id="52adc-294">Hard binding</span></span>

<span data-ttu-id="52adc-295">Die feste Bindung erhöht den Durchsatz und reduziert die Größe des Workingsets für native Images.</span><span class="sxs-lookup"><span data-stu-id="52adc-295">Hard binding increases throughput and reduces working set size for native images.</span></span> <span data-ttu-id="52adc-296">Der Nachteil der festen Bindung besteht darin, dass sämtliche Images mit fester Bindung an eine Assembly beim Laden der Assembly ebenfalls geladen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="52adc-296">The disadvantage of hard binding is that all the images that are hard bound to an assembly must be loaded when the assembly is loaded.</span></span> <span data-ttu-id="52adc-297">Dies kann die Startzeit bei umfangreichen Anwendungen deutlich verlängern.</span><span class="sxs-lookup"><span data-stu-id="52adc-297">This can significantly increase startup time for a large application.</span></span>

<span data-ttu-id="52adc-298">Die feste Bindung eignet sich für Abhängigkeiten, die in allen leistungskritischen Szenarien der Anwendung geladen werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-298">Hard binding is appropriate for dependencies that are loaded in all your application's performance-critical scenarios.</span></span> <span data-ttu-id="52adc-299">Wie bereits bei anderen Verwendungsmöglichkeiten systemeigener Images stellen sorgfältige Leistungsmessungen auch hier den einzigen Indikator dafür dar, ob die Anwendungsleistung durch feste Bindung verbessert wird.</span><span class="sxs-lookup"><span data-stu-id="52adc-299">As with any aspect of native image use, careful performance measurements are the only way to determine whether hard binding improves your application's performance.</span></span>

<span data-ttu-id="52adc-300">Über das <xref:System.Runtime.CompilerServices.DependencyAttribute>-Attribut und das <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute>-Attribut können Sie "Ngen.exe" Hinweise zur Verwendung der festen Bindung übermitteln.</span><span class="sxs-lookup"><span data-stu-id="52adc-300">The <xref:System.Runtime.CompilerServices.DependencyAttribute> and <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> attributes allow you to provide hard binding hints to Ngen.exe.</span></span>

> [!NOTE]
> <span data-ttu-id="52adc-301">Diese Attribute stellen Hinweise und keine Befehle für Ngen.exe dar.</span><span class="sxs-lookup"><span data-stu-id="52adc-301">These attributes are hints to Ngen.exe, not commands.</span></span> <span data-ttu-id="52adc-302">Die Verwendung der festen Bindung kann durch diese Hinweise nicht garantiert werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-302">Using them does not guarantee hard binding.</span></span> <span data-ttu-id="52adc-303">Die Bedeutung dieser Attribute kann sich in zukünftigen Releases ändern.</span><span class="sxs-lookup"><span data-stu-id="52adc-303">The meaning of these attributes may change in future releases.</span></span>

<a name="DependencyHint"></a>

### <a name="specifying-a-binding-hint-for-a-dependency"></a><span data-ttu-id="52adc-304">Angeben eines Bindungshinweises für eine Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="52adc-304">Specifying a binding hint for a dependency</span></span>

<span data-ttu-id="52adc-305">Wenden Sie <xref:System.Runtime.CompilerServices.DependencyAttribute> auf eine Assembly an, um die Wahrscheinlichkeit anzugeben, dass eine angegebene Abhängigkeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="52adc-305">Apply the <xref:System.Runtime.CompilerServices.DependencyAttribute> to an assembly to indicate the likelihood that a specified dependency will be loaded.</span></span> <span data-ttu-id="52adc-306"><xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> gibt an, dass harte Bindung angemessen ist, <xref:System.Runtime.CompilerServices.LoadHint.Default> gibt an, dass der Standard für die Abhängigkeit verwendet werden soll, und <xref:System.Runtime.CompilerServices.LoadHint.Sometimes> gibt an, dass harte Bindung nicht angemessen ist.</span><span class="sxs-lookup"><span data-stu-id="52adc-306"><xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> indicates that hard binding is appropriate, <xref:System.Runtime.CompilerServices.LoadHint.Default> indicates that the default for the dependency should be used, and <xref:System.Runtime.CompilerServices.LoadHint.Sometimes> indicates that hard binding is not appropriate.</span></span>

<span data-ttu-id="52adc-307">Im folgenden Code werden die Attribute für eine Assembly veranschaulicht, die über zwei Abhängigkeiten verfügt.</span><span class="sxs-lookup"><span data-stu-id="52adc-307">The following code shows the attributes for an assembly that has two dependencies.</span></span> <span data-ttu-id="52adc-308">Die erste Abhängigkeit (Assembly1) ist ein geeigneter Kandidat für die feste Bindung und die zweite Abhängigkeit (Assembly2) nicht.</span><span class="sxs-lookup"><span data-stu-id="52adc-308">The first dependency (Assembly1) is an appropriate candidate for hard binding, and the second (Assembly2) is not.</span></span>

```vb
Imports System.Runtime.CompilerServices
<Assembly:DependencyAttribute("Assembly1", LoadHint.Always)>
<Assembly:DependencyAttribute("Assembly2", LoadHint.Sometimes)>
```

```csharp
using System.Runtime.CompilerServices;
[assembly:DependencyAttribute("Assembly1", LoadHint.Always)]
[assembly:DependencyAttribute("Assembly2", LoadHint.Sometimes)]
```

```cpp
using namespace System::Runtime::CompilerServices;
[assembly:DependencyAttribute("Assembly1", LoadHint.Always)];
[assembly:DependencyAttribute("Assembly2", LoadHint.Sometimes)];
```

<span data-ttu-id="52adc-309">Der Assemblyname enthält keine Dateinamenerweiterung.</span><span class="sxs-lookup"><span data-stu-id="52adc-309">The assembly name does not include the file name extension.</span></span> <span data-ttu-id="52adc-310">Anzeigenamen können verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-310">Display names can be used.</span></span>

<a name="AssemblyHint"></a>

### <a name="specifying-a-default-binding-hint-for-an-assembly"></a><span data-ttu-id="52adc-311">Angeben eines standardmäßigen Bindungshinweises für eine Assembly</span><span class="sxs-lookup"><span data-stu-id="52adc-311">Specifying a default binding hint for an assembly</span></span>

<span data-ttu-id="52adc-312">Standardmäßige Bindungshinweise werden nur für Assemblys benötigt, die direkt und häufig von einer Anwendung verwendet werden, die über eine Abhängigkeit zu diesen Assemblys verfügt.</span><span class="sxs-lookup"><span data-stu-id="52adc-312">Default binding hints are only needed for assemblies that will be used immediately and frequently by any application that has a dependency on them.</span></span> <span data-ttu-id="52adc-313">Wenden Sie <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> mit <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> auf diese Assemblys an, um anzugeben, dass die feste Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="52adc-313">Apply the <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> with <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> to such assemblies to specify that hard binding should be used.</span></span>

> [!NOTE]
> <span data-ttu-id="52adc-314">Es gibt keinen Grund, <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> auf DLL-Assemblys anzuwenden, die nicht in diese Kategorie fallen, da das Anwenden des Attributs mit einem anderen Wert als <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> ohne Auswirkung bleibt.</span><span class="sxs-lookup"><span data-stu-id="52adc-314">There is no reason to apply <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> to .dll assemblies that do not fall into this category, because applying the attribute with any value other than <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> has the same effect as not applying the attribute at all.</span></span>

<span data-ttu-id="52adc-315">Microsoft verwendet das <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute>, um die feste Bindung als Standard für eine verhältnismäßig kleine Anzahl von Assemblys in .NET Framework anzugeben, beispielsweise mscorlib.dll.</span><span class="sxs-lookup"><span data-stu-id="52adc-315">Microsoft uses the <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> to specify that hard binding is the default for a very small number of assemblies in the .NET Framework, such as mscorlib.dll.</span></span>

<a name="Deferred"></a>

## <a name="deferred-processing"></a><span data-ttu-id="52adc-316">Verzögertes Verarbeiten</span><span class="sxs-lookup"><span data-stu-id="52adc-316">Deferred processing</span></span>

<span data-ttu-id="52adc-317">Die Generierung von systemeigenen Images für eine sehr große Anwendung kann sehr viel Zeit beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="52adc-317">Generation of native images for a very large application can take considerable time.</span></span> <span data-ttu-id="52adc-318">Entsprechend können Änderungen an einer freigegebenen Komponente oder an den Computereinstellungen die Aktualisierung vieler systemeigener Images erfordern.</span><span class="sxs-lookup"><span data-stu-id="52adc-318">Similarly, changes to a shared component or changes to computer settings might require many native images to be updated.</span></span> <span data-ttu-id="52adc-319">Die Aktion `install` und die Aktion `update` verfügen über eine Option `/queue`, über die Sie den Vorgang zur verzögerten Ausführung in eine Warteschlange stellen und vom Dienst für systemeigene Images verarbeiten lassen können.</span><span class="sxs-lookup"><span data-stu-id="52adc-319">The `install` and `update` actions have a `/queue` option that queues the operation for deferred execution by the native image service.</span></span> <span data-ttu-id="52adc-320">Außerdem verfügt "Ngen.exe" über die Aktion `queue` und die Aktion `executeQueuedItems`, mit der der Dienst in gewissem Umfang gesteuert werden kann.</span><span class="sxs-lookup"><span data-stu-id="52adc-320">In addition, Ngen.exe has `queue` and `executeQueuedItems` actions that provide some control over the service.</span></span> <span data-ttu-id="52adc-321">Weitere Informationen finden Sie unter [Dienst für systemeigene Abbilder](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="52adc-321">For more information, see [Native Image Service](#native-image-service).</span></span>

<a name="JITCompilation"></a>

## <a name="native-images-and-jit-compilation"></a><span data-ttu-id="52adc-322">Native Images und JIT-Kompilierung</span><span class="sxs-lookup"><span data-stu-id="52adc-322">Native images and JIT compilation</span></span>

<span data-ttu-id="52adc-323">Wenn Ngen.exe auf Methoden in einer Assembly trifft, die von diesem Programm nicht generiert werden können, werden diese Methoden aus dem systemeigenen Image ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="52adc-323">If Ngen.exe encounters any methods in an assembly that it cannot generate, it excludes them from the native image.</span></span> <span data-ttu-id="52adc-324">Wenn die Laufzeit diese Assembly ausführt, werden die nicht im systemeigenen Image enthaltenen Methoden auf JIT-Kompilierung zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="52adc-324">When the runtime executes this assembly, it reverts to JIT compilation for the methods that were not included in the native image.</span></span>

<span data-ttu-id="52adc-325">Darüber hinaus werden systemeigene Images nicht verwendet, wenn die Assembly aktualisiert wurde bzw. das Image aus irgendeinem Grund ungültig geworden ist.</span><span class="sxs-lookup"><span data-stu-id="52adc-325">In addition, native images are not used if the assembly has been upgraded, or if the image has been invalidated for any reason.</span></span>

<a name="InvalidImages"></a>

### <a name="invalid-images"></a><span data-ttu-id="52adc-326">Ungültige Images</span><span class="sxs-lookup"><span data-stu-id="52adc-326">Invalid images</span></span>

<span data-ttu-id="52adc-327">Wenn Sie mit "Ngen.exe" ein systemeigenes Image einer Assembly erstellen, hängt die Ausgabe von den Optionen in der Befehlszeile und den Computereinstellungen ab.</span><span class="sxs-lookup"><span data-stu-id="52adc-327">When you use Ngen.exe to create a native image of an assembly, the output depends upon the command-line options that you specify and certain settings on your computer.</span></span> <span data-ttu-id="52adc-328">Dies betrifft folgende Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="52adc-328">These settings include the following:</span></span>

- <span data-ttu-id="52adc-329">Die Version von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="52adc-329">The version of the .NET Framework.</span></span>

- <span data-ttu-id="52adc-330">Die Version des Betriebssystems, wenn der Wechsel von der Windows 9x-Familie zur Windows NT-Familie durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="52adc-330">The version of the operating system, if the change is from the Windows 9x family to the Windows NT family.</span></span>

- <span data-ttu-id="52adc-331">Die genaue Identität der Assembly (durch Neukompilierung wird die Identität geändert).</span><span class="sxs-lookup"><span data-stu-id="52adc-331">The exact identity of the assembly (recompilation changes identity).</span></span>

- <span data-ttu-id="52adc-332">Die genaue Identität aller Assemblys, auf die die Assembly verweist (durch Neukompilierung wird die Identität geändert).</span><span class="sxs-lookup"><span data-stu-id="52adc-332">The exact identity of all assemblies that the assembly references (recompilation changes identity).</span></span>

- <span data-ttu-id="52adc-333">Sicherheitsfaktoren.</span><span class="sxs-lookup"><span data-stu-id="52adc-333">Security factors.</span></span>

<span data-ttu-id="52adc-334">Diese Daten werden beim Generieren eines systemeigenen Image von Ngen.exe aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="52adc-334">Ngen.exe records this information when it generates a native image.</span></span> <span data-ttu-id="52adc-335">Beim Ausführen einer Assembly sucht die Common Language Runtime nach dem systemeigenen Image, das mit den Optionen und Einstellungen in Übereinstimmung mit der aktuellen Computerumgebung generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="52adc-335">When you execute an assembly, the runtime looks for the native image generated with options and settings that match the computer's current environment.</span></span> <span data-ttu-id="52adc-336">Die Laufzeit wird auf die JIT-Kompilierung einer Assembly zurückgesetzt, falls kein geeignetes systemeigenes Image gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="52adc-336">The runtime reverts to JIT compilation of an assembly if it cannot find a matching native image.</span></span> <span data-ttu-id="52adc-337">Die folgenden Änderungen an den Einstellungen und der Umgebung eines Computers führen dazu, dass systemeigene Images ungültig werden:</span><span class="sxs-lookup"><span data-stu-id="52adc-337">The following changes to a computer's settings and environment cause native images to become invalid:</span></span>

- <span data-ttu-id="52adc-338">Die Version von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="52adc-338">The version of the .NET Framework.</span></span>

     <span data-ttu-id="52adc-339">Wenn Sie .NET Framework aktualisieren, werden alle von Ihnen mit Ngen.exe erstellten systemeigenen Images ungültig.</span><span class="sxs-lookup"><span data-stu-id="52adc-339">If you apply an update to the .NET Framework, all native images that you have created using Ngen.exe become invalid.</span></span> <span data-ttu-id="52adc-340">Aus diesem Grund wird bei allen Updates von .NET Framework der Befehl `Ngen Update` ausgeführt, um sicherzustellen, dass alle systemeigenen Images erneut generiert werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-340">For this reason, all updates of the .NET Framework execute the `Ngen Update` command, to ensure that all native images are regenerated.</span></span> <span data-ttu-id="52adc-341">.NET Framework erzeugt automatisch neue systemeigene Images für die .NET Framework-Bibliotheken, die installiert werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-341">The .NET Framework automatically creates new native images for the .NET Framework libraries that it installs.</span></span>

- <span data-ttu-id="52adc-342">Die Version des Betriebssystems, wenn der Wechsel von der Windows 9x-Familie zur Windows NT-Familie durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="52adc-342">The version of the operating system, if the change is from the Windows 9x family to the Windows NT family.</span></span>

     <span data-ttu-id="52adc-343">Wenn sich beispielsweise die Version des Betriebssystems eines Computers von Windows 98 in Windows XP ändert, werden alle nativen Images im Cache für native Images ungültig.</span><span class="sxs-lookup"><span data-stu-id="52adc-343">For example, if the version of the operating system running on a computer changes from Windows 98 to Windows XP, all native images stored in the native image cache become invalid.</span></span> <span data-ttu-id="52adc-344">Wenn sich das Betriebssystem jedoch von Windows 2000 in Windows XP ändert, werden die Images nicht ungültig.</span><span class="sxs-lookup"><span data-stu-id="52adc-344">However, if the operating system changes from Windows 2000 to Windows XP, the images are not invalidated.</span></span>

- <span data-ttu-id="52adc-345">Die genaue Identität der Assembly.</span><span class="sxs-lookup"><span data-stu-id="52adc-345">The exact identity of the assembly.</span></span>

     <span data-ttu-id="52adc-346">Nach dem Neukompilieren einer Assembly wird das systemeigene Image der Assembly ungültig.</span><span class="sxs-lookup"><span data-stu-id="52adc-346">If you recompile an assembly, the assembly's corresponding native image becomes invalid.</span></span>

- <span data-ttu-id="52adc-347">Die genaue Identität aller Assemblys, auf die die Assembly verweist.</span><span class="sxs-lookup"><span data-stu-id="52adc-347">The exact identity of any assemblies the assembly references.</span></span>

     <span data-ttu-id="52adc-348">Wenn Sie eine verwaltete Assembly aktualisieren, werden alle systemeigenen Images, die direkt oder indirekt von dieser Assembly abhängen, ungültig und müssen erneut generiert werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-348">If you update a managed assembly, all native images that directly or indirectly depend on that assembly become invalid and need to be regenerated.</span></span> <span data-ttu-id="52adc-349">Dies betrifft sowohl normale Verweise als auch fest gebundene Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="52adc-349">This includes both ordinary references and hard-bound dependencies.</span></span> <span data-ttu-id="52adc-350">Bei jedem Softwareupdate sollte das Installationsprogramm den Befehl `Ngen Update` ausführen, um sicherzustellen, dass alle abhängigen systemeigenen Images erneut generiert werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-350">Whenever a software update is applied, the installation program should execute an `Ngen Update` command to ensure that all dependent native images are regenerated.</span></span>

- <span data-ttu-id="52adc-351">Sicherheitsfaktoren.</span><span class="sxs-lookup"><span data-stu-id="52adc-351">Security factors.</span></span>

     <span data-ttu-id="52adc-352">Wenn die Sicherheitsrichtlinien eines Computers so geändert werden, dass Berechtigungen für eine Assembly widerrufen werden, können vorher kompilierte systemeigene Images für die entsprechende Assembly ungültig werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-352">Changing machine security policy to restrict permissions previously granted to an assembly can cause a previously compiled native image for that assembly to become invalid.</span></span>

     <span data-ttu-id="52adc-353">Ausführliche Informationen über die Verwaltung der Codezugriffssicherheit durch die Common Language Runtime und die Verwendung von Berechtigungen finden Sie unter [Codezugriffssicherheit](../misc/code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="52adc-353">For detailed information about how the common language runtime administers code access security and how to use permissions, see [Code Access Security](../misc/code-access-security.md).</span></span>

<a name="Troubleshooting"></a>

## <a name="troubleshooting"></a><span data-ttu-id="52adc-354">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="52adc-354">Troubleshooting</span></span>

<span data-ttu-id="52adc-355">In den folgenden Themen zur Problembehandlung wird erläutert, welche nativen Images verwendet werden und welche von der Anwendung nicht unterstützt werden. So können Sie feststellen, wann der JIT-Compiler beginnt, eine Methode zu kompilieren. Zudem wird gezeigt, wie Sie die Kompilierung nativer Images für bestimmte Methoden deaktivieren können.</span><span class="sxs-lookup"><span data-stu-id="52adc-355">The following troubleshooting topics allow you to see which native images are being used and which cannot be used by your application, to determine when the JIT compiler starts to compile a method, and shows how to opt out of native image compilation of specified methods.</span></span>

<a name="Fusion"></a>

### <a name="assembly-binding-log-viewer"></a><span data-ttu-id="52adc-356">Assembly Binding Log Viewer</span><span class="sxs-lookup"><span data-stu-id="52adc-356">Assembly Binding Log Viewer</span></span>

<span data-ttu-id="52adc-357">Um zu überprüfen, ob native Images von der Anwendung verwendet werden, können Sie den [Assembly Binding Log Viewer (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="52adc-357">To confirm that native images are being used by your application, you can use the [Fuslogvw.exe (Assembly Binding Log Viewer)](fuslogvw-exe-assembly-binding-log-viewer.md).</span></span> <span data-ttu-id="52adc-358">Wählen Sie im Fenster der Bindungsprotokollanzeige im Feld **Kategorien protokollieren** die Option **Native Images** aus.</span><span class="sxs-lookup"><span data-stu-id="52adc-358">Select **Native Images** in the **Log Categories** box on the binding log viewer window.</span></span> <span data-ttu-id="52adc-359">Fuslogvw.exe liefert Informationen über die Gründe, aus denen ein systemeigenes Image abgelehnt wurde.</span><span class="sxs-lookup"><span data-stu-id="52adc-359">Fuslogvw.exe provides information about why a native image was rejected.</span></span>

<a name="MDA"></a>

### <a name="the-jitcompilationstart-managed-debugging-assistant"></a><span data-ttu-id="52adc-360">Der Assistent für verwaltetes Debuggen (jitCompilationStart)</span><span class="sxs-lookup"><span data-stu-id="52adc-360">The JITCompilationStart managed debugging assistant</span></span>

<span data-ttu-id="52adc-361">Mit dem Assistenten für verwaltetes Debuggen, [jitCompilationStart](../debug-trace-profile/jitcompilationstart-mda.md), können Sie bestimmen, wann der JIT-Compiler mit der Kompilierung einer Funktion beginnt.</span><span class="sxs-lookup"><span data-stu-id="52adc-361">You can use the [jitCompilationStart](../debug-trace-profile/jitcompilationstart-mda.md) managed debugging assistant (MDA) to determine when the JIT compiler starts to compile a function.</span></span>

<a name="OptOut"></a>

### <a name="opting-out-of-native-image-generation"></a><span data-ttu-id="52adc-362">Deaktivieren der Generierung nativer Images</span><span class="sxs-lookup"><span data-stu-id="52adc-362">Opting out of native image generation</span></span>

<span data-ttu-id="52adc-363">In einigen Fällen hat NGen.exe möglicherweise Probleme beim Generieren eines nativen Images für eine bestimmte Methode, oder Sie bevorzugen, dass die Methode statt in ein natives Image JIT-kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="52adc-363">In some cases, NGen.exe may have difficulty generating a native image for a specific method, or you may prefer that the method be JIT compiled rather then compiled to a native image.</span></span> <span data-ttu-id="52adc-364">In diesem Fall können Sie mit dem Attribut `System.Runtime.BypassNGenAttribute` verhindern, dass NGen.exe ein natives Image für eine bestimmte Methode generiert.</span><span class="sxs-lookup"><span data-stu-id="52adc-364">In this case, you can use the `System.Runtime.BypassNGenAttribute` attribute to prevent NGen.exe from generating a native image for a particular method.</span></span> <span data-ttu-id="52adc-365">Das Attribut muss einzeln auf jede Methode angewendet werden, deren Code nicht in das native Image eingeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="52adc-365">The attribute must be applied individually to each method whose code you do not want to include in the native image.</span></span> <span data-ttu-id="52adc-366">NGen.exe erkennt das Attribut und generiert keinen Code im nativen Image für die entsprechende Methode.</span><span class="sxs-lookup"><span data-stu-id="52adc-366">NGen.exe recognizes the attribute and does not generate code in the native image for the corresponding method.</span></span>

<span data-ttu-id="52adc-367">Beachten Sie jedoch, dass `BypassNGenAttribute` in der .NET Framework-Klassenbibliothek nicht als Typ definiert ist.</span><span class="sxs-lookup"><span data-stu-id="52adc-367">Note, however, that `BypassNGenAttribute` is not defined as a type in the .NET Framework Class Library.</span></span> <span data-ttu-id="52adc-368">Um das Attribut im Code verwenden zu können, müssen Sie es zunächst wie folgt definieren:</span><span class="sxs-lookup"><span data-stu-id="52adc-368">In order to consume the attribute in your code, you must first define it as follows:</span></span>

[!code-csharp[System.Runtime.BypassNGenAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/cs/Optout1.cs#1)]
[!code-vb[System.Runtime.BypassNGenAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/vb/Optout1.vb#1)]

<span data-ttu-id="52adc-369">Anschließend können Sie das Attribut methodenweise anwenden.</span><span class="sxs-lookup"><span data-stu-id="52adc-369">You can then apply the attribute on a per-method basis.</span></span> <span data-ttu-id="52adc-370">Im folgende Beispiel wird Native Image Generator angewiesen, kein natives Image für die Methode `ExampleClass.ToJITCompile` zu generieren.</span><span class="sxs-lookup"><span data-stu-id="52adc-370">The following example instructs the Native Image Generator that it should not generate a native image for the `ExampleClass.ToJITCompile` method.</span></span>

[!code-csharp[System.Runtime.BypassNGenAttribute#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/cs/Optout1.cs#2)]
[!code-vb[System.Runtime.BypassNGenAttribute#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/vb/Optout1.vb#2)]

## <a name="examples"></a><span data-ttu-id="52adc-371">Beispiele</span><span class="sxs-lookup"><span data-stu-id="52adc-371">Examples</span></span>

<span data-ttu-id="52adc-372">Mit dem folgenden Befehl wird ein systemeigenes Image für `ClientApp.exe` generiert, im aktuellen Verzeichnis abgelegt und anschließend im Cache für systemeigene Images installiert.</span><span class="sxs-lookup"><span data-stu-id="52adc-372">The following command generates a native image for `ClientApp.exe`, located in the current directory, and installs the image in the native image cache.</span></span> <span data-ttu-id="52adc-373">Wenn eine Konfigurationsdatei für die Assembly vorhanden ist, wird sie von Ngen.exe verwendet.</span><span class="sxs-lookup"><span data-stu-id="52adc-373">If a configuration file exists for the assembly, Ngen.exe uses it.</span></span> <span data-ttu-id="52adc-374">Außerdem werden systemeigene Images für alle DLL-Dateien generiert, auf die `ClientApp.exe` verweist.</span><span class="sxs-lookup"><span data-stu-id="52adc-374">In addition, native images are generated for any .dll files that `ClientApp.exe` references.</span></span>

```console
ngen install ClientApp.exe
```

<span data-ttu-id="52adc-375">Ein mit Ngen.exe installiertes Image wird auch als Stammelement bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="52adc-375">An image installed with Ngen.exe is also called a root.</span></span> <span data-ttu-id="52adc-376">Ein Stammelement kann eine Anwendung oder eine freigegebene Komponente sein.</span><span class="sxs-lookup"><span data-stu-id="52adc-376">A root can be an application or a shared component.</span></span>

<span data-ttu-id="52adc-377">Durch den folgenden Befehl wird ein systemeigenes Image für `MyAssembly.exe` mit dem angegebenen Pfad generiert.</span><span class="sxs-lookup"><span data-stu-id="52adc-377">The following command generates a native image for `MyAssembly.exe` with the specified path.</span></span>

```console
ngen install c:\myfiles\MyAssembly.exe
```

<span data-ttu-id="52adc-378">Bei der Suche nach Assemblys und ihren Abhängigkeiten verwendet Ngen.exe dieselbe Überprüfungslogik wie die Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="52adc-378">When locating assemblies and their dependencies, Ngen.exe uses the same probing logic used by the common language runtime.</span></span> <span data-ttu-id="52adc-379">Das Verzeichnis, in dem `ClientApp.exe` enthalten ist, wird standardmäßig als Basisverzeichnis der Anwendung verwendet, und sämtliche Überprüfungen von Assemblys werden in diesem Verzeichnis gestartet.</span><span class="sxs-lookup"><span data-stu-id="52adc-379">By default, the directory that contains `ClientApp.exe` is used as the application base directory, and all assembly probing begins in this directory.</span></span> <span data-ttu-id="52adc-380">Sie können dieses Verhalten mit der Option `/AppBase` überschreiben.</span><span class="sxs-lookup"><span data-stu-id="52adc-380">You can override this behavior by using the `/AppBase` option.</span></span>

> [!NOTE]
> <span data-ttu-id="52adc-381">Dies ist eine Änderung im Verhalten von "Ngen.exe" gegenüber .NET Framework Version 1.0 und 1.1, bei denen die Anwendungsbasis auf das aktuelle Verzeichnis festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="52adc-381">This is a change from Ngen.exe behavior in the .NET Framework versions 1.0 and 1.1, where the application base is set to the current directory.</span></span>

<span data-ttu-id="52adc-382">Eine Assembly kann über eine Abhängigkeit ohne Verweis verfügen, wenn sie beispielsweise eine DLL-Datei mithilfe der <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Methode lädt.</span><span class="sxs-lookup"><span data-stu-id="52adc-382">An assembly can have a dependency without a reference, for example if it loads a .dll file by using the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="52adc-383">Sie können mit der Option `/ExeConfig` ein systemeigenes Image für eine solche DLL-Datei erstellen, indem Sie Konfigurationsinformationen für die Anwendungsassembly verwenden.</span><span class="sxs-lookup"><span data-stu-id="52adc-383">You can create a native image for such a .dll file by using configuration information for the application assembly, with the `/ExeConfig` option.</span></span> <span data-ttu-id="52adc-384">Der folgende Befehl generiert ein systemeigenes Image für `MyLib.dll,` mithilfe der Konfigurationsinformationen aus `MyApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="52adc-384">The following command generates a native image for `MyLib.dll,` using the configuration information from `MyApp.exe`.</span></span>

```console
ngen install c:\myfiles\MyLib.dll /ExeConfig:c:\myapps\MyApp.exe
```

<span data-ttu-id="52adc-385">Auf diese Weise installierte Assemblys werden nicht entfernt, wenn die Anwendung entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="52adc-385">Assemblies installed in this way are not removed when the application is removed.</span></span>

<span data-ttu-id="52adc-386">Verwenden Sie zum Deinstallieren einer Abhängigkeit dieselben Befehlszeilenoptionen wie beim Installieren.</span><span class="sxs-lookup"><span data-stu-id="52adc-386">To uninstall a dependency, use the same command-line options that were used to install it.</span></span> <span data-ttu-id="52adc-387">Durch den folgenden Befehl wird `MyLib.dll` aus dem vorherigen Beispiel deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="52adc-387">The following command uninstalls the `MyLib.dll` from the previous example.</span></span>

```console
ngen uninstall c:\myfiles\MyLib.dll /ExeConfig:c:\myapps\MyApp.exe
```

<span data-ttu-id="52adc-388">Verwendung Sie zum Erstellen eines systemeigenen Images für eine Assembly im globalen Assemblycache den Anzeigenamen der Assembly.</span><span class="sxs-lookup"><span data-stu-id="52adc-388">To create a native image for an assembly in the global assembly cache, use the display name of the assembly.</span></span> <span data-ttu-id="52adc-389">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="52adc-389">For example:</span></span>

```console
ngen install "ClientApp, Version=1.0.0.0, Culture=neutral,
  PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL"
```

<span data-ttu-id="52adc-390">Ngen.exe generiert einen separaten Satz von Images für jedes Szenario, das Sie installieren.</span><span class="sxs-lookup"><span data-stu-id="52adc-390">NGen.exe generates a separate set of images for each scenario you install.</span></span> <span data-ttu-id="52adc-391">Durch die folgenden Befehle wird beispielsweise ein vollständiger Satz von systemeigenen Images für den normalen Ablauf, ein anderer vollständiger Satz für das Debuggen und ein dritter Satz für die Profilerstellung erstellt:</span><span class="sxs-lookup"><span data-stu-id="52adc-391">For example, the following commands install a complete set of native images for normal operation, another complete set for debugging, and a third for profiling:</span></span>

```console
ngen install MyApp.exe
ngen install MyApp.exe /debug
ngen install MyApp.exe /profile
```

### <a name="displaying-the-native-image-cache"></a><span data-ttu-id="52adc-392">Anzeigen des Caches für systemeigene Images</span><span class="sxs-lookup"><span data-stu-id="52adc-392">Displaying the Native Image Cache</span></span>

<span data-ttu-id="52adc-393">Sobald systemeigene Images im Cache installiert wurden, können sie mit "Ngen.exe" angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-393">Once native images are installed in the cache, they can be displayed using Ngen.exe.</span></span> <span data-ttu-id="52adc-394">Der folgende Befehl dient zur Anzeige aller systemeigenen Images im Cache für systemeigene Images.</span><span class="sxs-lookup"><span data-stu-id="52adc-394">The following command displays all native images in the native image cache.</span></span>

```console
ngen display
```

<span data-ttu-id="52adc-395">Durch die Aktion `display` werden zuerst alle Stammassemblys und dann alle systemeigenen Images auf dem Computer aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="52adc-395">The `display` action lists all the root assemblies first, followed by a list of all the native images on the computer.</span></span>

<span data-ttu-id="52adc-396">Verwenden Sie den einfachen Namen einer Assembly, um nur Informationen für diese Assembly anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="52adc-396">Use the simple name of an assembly to display information only for that assembly.</span></span> <span data-ttu-id="52adc-397">Durch den folgenden Befehl werden alle systemeigenen Images aus dem Cache für systemeigene Images angezeigt, die den Teilnamen `MyAssembly` aufweisen, sowie ihre Abhängigkeiten und alle Stammassemblys, die über eine Abhängigkeit zu `MyAssembly` verfügen:</span><span class="sxs-lookup"><span data-stu-id="52adc-397">The following command displays all native images in the native image cache that match the partial name `MyAssembly`, their dependencies, and all roots that have a dependency on `MyAssembly`:</span></span>

```console
ngen display MyAssembly
```

<span data-ttu-id="52adc-398">Zum Beurteilen des Einflusses, den eine `update`-Aktion nach der Aktualisierung der freigegebenen Komponente hat, ist es hilfreich, die Stammassemblys zu kennen, die von der Assembly der freigegebenen Komponente abhängen.</span><span class="sxs-lookup"><span data-stu-id="52adc-398">Knowing what roots depend on a shared component assembly is useful in gauging the impact of an `update` action after the shared component is upgraded.</span></span>

<span data-ttu-id="52adc-399">Wenn Sie die Dateierweiterung einer Assembly angeben, müssen Sie entweder den Pfad angeben oder "Ngen.exe" von dem Verzeichnis aus ausführen, in dem die Assembly enthalten ist:</span><span class="sxs-lookup"><span data-stu-id="52adc-399">If you specify an assembly's file extension, you must either specify the path or execute Ngen.exe from the directory containing the assembly:</span></span>

```console
ngen display c:\myApps\MyAssembly.exe
```

<span data-ttu-id="52adc-400">Der folgende Befehl dient zur Anzeige aller nativen Images im Cache für native Images mit dem Namen `MyAssembly` und der Version 1.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="52adc-400">The following command displays all native images in the native image cache with the name `MyAssembly` and the version 1.0.0.0.</span></span>

```console
ngen display "myAssembly, version=1.0.0.0"
```

### <a name="updating-images"></a><span data-ttu-id="52adc-401">Aktualisieren von Images</span><span class="sxs-lookup"><span data-stu-id="52adc-401">Updating Images</span></span>

<span data-ttu-id="52adc-402">Images werden normalerweise aktualisiert, nachdem eine freigegebene Komponente aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="52adc-402">Images are typically updated after a shared component has been upgraded.</span></span> <span data-ttu-id="52adc-403">Verwenden Sie zum Aktualisieren aller systemeigenen Images, die bzw. deren Abhängigkeiten geändert wurden, die Aktion `update` ohne Argumente.</span><span class="sxs-lookup"><span data-stu-id="52adc-403">To update all native images that have changed, or whose dependencies have changed, use the `update` action with no arguments.</span></span>

```console
ngen update
```

<span data-ttu-id="52adc-404">Das Aktualisieren aller Images kann ein langwieriger Prozess sein.</span><span class="sxs-lookup"><span data-stu-id="52adc-404">Updating all images can be a lengthy process.</span></span> <span data-ttu-id="52adc-405">Sie können die Updates mit der Option `/queue` in eine Warteschlange stellen, um sie vom Dienst für systemeigene Images ausführen zu lassen.</span><span class="sxs-lookup"><span data-stu-id="52adc-405">You can queue the updates for execution by the native image service by using the `/queue` option.</span></span> <span data-ttu-id="52adc-406">Weitere Informationen zur Option `/queue` und den Prioritäten bei der Installation finden Sie unter [Dienst für systemeigene Abbilder](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="52adc-406">For more information on the `/queue` option and installation priorities, see [Native Image Service](#native-image-service).</span></span>

```console
ngen update /queue
```

### <a name="uninstalling-images"></a><span data-ttu-id="52adc-407">Deinstallieren von Images</span><span class="sxs-lookup"><span data-stu-id="52adc-407">Uninstalling Images</span></span>

<span data-ttu-id="52adc-408">"Ngen.exe" verwaltet eine Liste von Abhängigkeiten. Freigegebene Komponenten können demnach nur entfernt werden, nachdem alle Assemblys, die von diesen Komponenten abhängen, entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="52adc-408">Ngen.exe maintains a list of dependencies, so that shared components are removed only when all assemblies that depend on them have been removed.</span></span> <span data-ttu-id="52adc-409">Darüber hinaus wird eine freigegebene Komponente, die als Stammelement installiert wurde, nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="52adc-409">In addition, a shared component is not removed if it has been installed as a root.</span></span>

<span data-ttu-id="52adc-410">Mit dem folgenden Befehl werden alle Szenarien für den Stamm `ClientApp.exe` deinstalliert:</span><span class="sxs-lookup"><span data-stu-id="52adc-410">The following command uninstalls all scenarios for the root `ClientApp.exe`:</span></span>

```console
ngen uninstall ClientApp
```

<span data-ttu-id="52adc-411">Mit der Aktion `uninstall` können bestimmte Szenarien entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-411">The `uninstall` action can be used to remove specific scenarios.</span></span> <span data-ttu-id="52adc-412">Mit dem folgenden Befehl werden alle Debugszenarien für `ClientApp.exe` deinstalliert:</span><span class="sxs-lookup"><span data-stu-id="52adc-412">The following command uninstalls all debug scenarios for `ClientApp.exe`:</span></span>

```console
ngen uninstall ClientApp /debug
```

> [!NOTE]
> <span data-ttu-id="52adc-413">Beim Deinstallieren von `/debug`-Szenarien werden keine Szenarien deinstalliert, die sowohl `/profile` als auch `/debug.` enthalten.</span><span class="sxs-lookup"><span data-stu-id="52adc-413">Uninstalling `/debug` scenarios does not uninstall a scenario that includes both `/profile` and `/debug.`</span></span>

<span data-ttu-id="52adc-414">Mit dem folgenden Befehl werden alle Szenarien für eine bestimmte Version von `ClientApp.exe` deinstalliert:</span><span class="sxs-lookup"><span data-stu-id="52adc-414">The following command uninstalls all scenarios for a specific version of `ClientApp.exe`:</span></span>

```console
ngen uninstall "ClientApp, Version=1.0.0.0"
```

<span data-ttu-id="52adc-415">Mit den folgenden Befehlen werden alle Szenarien für `"ClientApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL",` oder nur das Debugszenario für diese Assembly deinstalliert:</span><span class="sxs-lookup"><span data-stu-id="52adc-415">The following commands uninstall all scenarios for `"ClientApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL",` or just the debug scenario for that assembly:</span></span>

```console
ngen uninstall "ClientApp, Version=1.0.0.0, Culture=neutral,
  PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL"
ngen uninstall "ClientApp, Version=1.0.0.0, Culture=neutral,
  PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL" /debug
```

<span data-ttu-id="52adc-416">Wie bei der Aktion `install` erfordert die Angabe einer Erweiterung entweder, dass "Ngen.exe" von dem Verzeichnis aus ausgeführt werden muss, in dem die Assembly enthalten ist, oder dass der vollständige Pfad angegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="52adc-416">As with the `install` action, supplying an extension requires either executing Ngen.exe from the directory containing the assembly or specifying a full path.</span></span>

<span data-ttu-id="52adc-417">Beispiele, die sich auf den Dienst für systemeigene Abbilder beziehen, finden Sie unter [Dienst für systemeigene Abbilder](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="52adc-417">For examples relating to the native image service, see [Native Image Service](#native-image-service).</span></span>

## <a name="native-image-task"></a><span data-ttu-id="52adc-418">Aufgabe zur Generierung nativer Images</span><span class="sxs-lookup"><span data-stu-id="52adc-418">Native Image Task</span></span>

<span data-ttu-id="52adc-419">Die Aufgabe zur Generierung systemeigener Images ist eine Windows-Aufgabe, die systemeigene Images generiert und verwaltet.</span><span class="sxs-lookup"><span data-stu-id="52adc-419">The native image task is a Windows task that generates and maintains native images.</span></span> <span data-ttu-id="52adc-420">Die Aufgabe zur Generierung nativer Images geht so vor, dass sie automatisch native Images für die unterstützten Szenarien generiert und freigibt.</span><span class="sxs-lookup"><span data-stu-id="52adc-420">The native image task generates and reclaims native images automatically for supported scenarios.</span></span> <span data-ttu-id="52adc-421">Sie ermöglichte es Installationsprogrammen außerdem, [Ngen.exe (Native Image Generator)](ngen-exe-native-image-generator.md) zu verwenden, um native Images nach einer Zeitverzögerung zu erstellen und zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="52adc-421">It also enables installers to use [Ngen.exe (Native Image Generator)](ngen-exe-native-image-generator.md) to create and update native images at a deferred time.</span></span>

<span data-ttu-id="52adc-422">Die Aufgabe zur Generierung nativer Images wird einmal für jede CPU-Architektur registriert, die auf einem Computer unterstützt wird. Dadurch ist es möglich, Anwendungen zu kompilieren, die genau für jede Architektur angepasst sind:</span><span class="sxs-lookup"><span data-stu-id="52adc-422">The native image task is registered once for each CPU architecture supported on a computer, to allow compilation for applications that target each architecture:</span></span>

|<span data-ttu-id="52adc-423">Aufgabenname</span><span class="sxs-lookup"><span data-stu-id="52adc-423">Task name</span></span>|<span data-ttu-id="52adc-424">32-Bit-Computer</span><span class="sxs-lookup"><span data-stu-id="52adc-424">32-bit computer</span></span>|<span data-ttu-id="52adc-425">64-Bit-Computer</span><span class="sxs-lookup"><span data-stu-id="52adc-425">64-bit computer</span></span>|
|---------------|----------------------|----------------------|
|<span data-ttu-id="52adc-426">NET Framework NGEN v4.0.30319</span><span class="sxs-lookup"><span data-stu-id="52adc-426">NET Framework NGEN v4.0.30319</span></span>|<span data-ttu-id="52adc-427">Ja</span><span class="sxs-lookup"><span data-stu-id="52adc-427">Yes</span></span>|<span data-ttu-id="52adc-428">Ja</span><span class="sxs-lookup"><span data-stu-id="52adc-428">Yes</span></span>|
|<span data-ttu-id="52adc-429">NET Framework NGEN v4.0.30319 64</span><span class="sxs-lookup"><span data-stu-id="52adc-429">NET Framework NGEN v4.0.30319 64</span></span>|<span data-ttu-id="52adc-430">Nein</span><span class="sxs-lookup"><span data-stu-id="52adc-430">No</span></span>|<span data-ttu-id="52adc-431">Ja</span><span class="sxs-lookup"><span data-stu-id="52adc-431">Yes</span></span>|

<span data-ttu-id="52adc-432">Die Aufgabe zur Generierung nativer Images ist in .NET Framework 4.5 und höher verfügbar, wenn sie unter Windows 8 oder höher ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="52adc-432">The native image task is available in the .NET Framework 4.5 and later versions, when running on Windows 8 or later.</span></span> <span data-ttu-id="52adc-433">In früheren Versionen von Windows verwendet .NET Framework den [Dienst für systemeigene Abbilder](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="52adc-433">On earlier versions of Windows, the .NET Framework uses the [Native Image Service](#native-image-service).</span></span>

### <a name="task-lifetime"></a><span data-ttu-id="52adc-434">Lebensdauer der Aufgabe</span><span class="sxs-lookup"><span data-stu-id="52adc-434">Task Lifetime</span></span>

<span data-ttu-id="52adc-435">Üblicherweise startet der Windows-Taskplaner die Aufgabe zur Generierung systemeigener Images jede Nacht, wenn sich der Computer im Leerlauf befindet.</span><span class="sxs-lookup"><span data-stu-id="52adc-435">In general, the Windows Task Scheduler starts the native image task every night when the computer is idle.</span></span> <span data-ttu-id="52adc-436">Die Aufgabe prüft auf zurückgestellte Arbeit, die von Anwendungsinstallationsprogrammen in die Warteschlange eingereiht wurde, auf zurückgestellte Aktualisierungsanforderungen für systemeigene Images sowie auf automatische Imageerstellung.</span><span class="sxs-lookup"><span data-stu-id="52adc-436">The task checks for any deferred work that is queued by application installers, any deferred native image update requests, and any automatic image creation.</span></span> <span data-ttu-id="52adc-437">Die Aufgabe schließt ausstehende Arbeitselemente ab und fährt dann herunter.</span><span class="sxs-lookup"><span data-stu-id="52adc-437">The task completes outstanding work items and then shuts down.</span></span> <span data-ttu-id="52adc-438">Wird für den Computer der Leerlaufzustand beendet, während die Aufgabe ausgeführt wird, wird die Aufgabe beendet.</span><span class="sxs-lookup"><span data-stu-id="52adc-438">If the computer stops being idle while the task is running, the task stops.</span></span>

<span data-ttu-id="52adc-439">Sie können die Aufgabe zur Generierung systemeigener Images auch manuell über die Taskplaner-Benutzeroberfläche oder durch manuelle Aufrufe von "NGen.exe" starten.</span><span class="sxs-lookup"><span data-stu-id="52adc-439">You can also start the native image task manually through the Task Scheduler UI or through manual calls to NGen.exe.</span></span> <span data-ttu-id="52adc-440">Wird die Aufgabe mit einer dieser Methoden gestartet, wird sie weiter ausgeführt, wenn der Computer nicht mehr im Leerlauf ist.</span><span class="sxs-lookup"><span data-stu-id="52adc-440">If the task is started through either of these methods, it will continue running when the computer is no longer idle.</span></span> <span data-ttu-id="52adc-441">Images, die manuell mit "NGen.exe" erstellt wurden, werden priorisiert, um vorhersagbares Verhalten für Installationsprogramme von Anwendungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="52adc-441">Images created manually by using NGen.exe are prioritized to enable predictable behavior for application installers.</span></span>

## <a name="native-image-service"></a><span data-ttu-id="52adc-442">Dienst für systemeigene Abbilder</span><span class="sxs-lookup"><span data-stu-id="52adc-442">Native Image Service</span></span>

<span data-ttu-id="52adc-443">Der Dienst für systemeigene Abbilder ist ein Windows-Dienst, der systemeigene Abbilder (Images) generiert und verwaltet.</span><span class="sxs-lookup"><span data-stu-id="52adc-443">The native image service is a Windows service that generates and maintains native images.</span></span> <span data-ttu-id="52adc-444">Der Dienst für systemeigene Abbilder ermöglicht es dem Entwickler, die Installation und Aktualisierung von systemeigenen Abbildern in Zeiträume zu verschieben, in denen sich der Computer im Leerlauf befindet.</span><span class="sxs-lookup"><span data-stu-id="52adc-444">The native image service allows the developer to defer the installation and update of native images to periods when the computer is idle.</span></span>

<span data-ttu-id="52adc-445">Normalerweise wird der Dienst für systemeigene Abbilder vom Installationsprogramm (Installer) für eine Anwendung oder ein Update gestartet.</span><span class="sxs-lookup"><span data-stu-id="52adc-445">Normally, the native image service is initiated by the installation program (installer) for an application or update.</span></span> <span data-ttu-id="52adc-446">Für Aktionen mit Priorität 3 wird der Dienst während Leerlaufzeiten des Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="52adc-446">For priority 3 actions, the service executes during idle time on the computer.</span></span> <span data-ttu-id="52adc-447">Der Dienst speichert seinen Zustand und kann, sofern erforderlich, selbst nach mehreren Neustarts fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-447">The service saves its state and is capable of continuing through multiple reboots if necessary.</span></span> <span data-ttu-id="52adc-448">Mehrere Imagekompilierungen können in die Warteschlange gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-448">Multiple image compilations can be queued.</span></span>

<span data-ttu-id="52adc-449">Der Dienst interagiert außerdem mit dem manuellen Befehl "Ngen.exe".</span><span class="sxs-lookup"><span data-stu-id="52adc-449">The service also interacts with the manual Ngen.exe command.</span></span> <span data-ttu-id="52adc-450">Manuelle Befehle haben Vorrang vor Hintergrundaktivitäten.</span><span class="sxs-lookup"><span data-stu-id="52adc-450">Manual commands take precedence over background activity.</span></span>

> [!NOTE]
> <span data-ttu-id="52adc-451">Unter Windows Vista ist der Anzeigenamen für den Dienst für systemeigene Abbilder "Microsoft.NET Framework NGEN 50727_X86" oder "Microsoft.NET Framework NGEN 50727_X64".</span><span class="sxs-lookup"><span data-stu-id="52adc-451">On Windows Vista, the name displayed for the native image service is "Microsoft.NET Framework NGEN v2.0.50727_X86" or "Microsoft.NET Framework NGEN v2.0.50727_X64".</span></span> <span data-ttu-id="52adc-452">Bei allen früheren Versionen von Microsoft Windows lautet der Name ".NET Runtime Optimization Service 50727_X86" oder ".NET Runtime Optimization Service 50727_X64".</span><span class="sxs-lookup"><span data-stu-id="52adc-452">On all earlier versions of Microsoft Windows, the name is ".NET Runtime Optimization Service v2.0.50727_X86" or ".NET Runtime Optimization Service v2.0.50727_X64".</span></span>

### <a name="launching-deferred-operations"></a><span data-ttu-id="52adc-453">Starten verzögerter Vorgänge</span><span class="sxs-lookup"><span data-stu-id="52adc-453">Launching Deferred Operations</span></span>

<span data-ttu-id="52adc-454">Es empfiehlt sich, vor dem Starten einer Installation oder Aktualisierung den Dienst zu beenden.</span><span class="sxs-lookup"><span data-stu-id="52adc-454">Before beginning an installation or upgrade, pausing the service is recommended.</span></span> <span data-ttu-id="52adc-455">Dadurch ist sichergestellt, dass der Dienst nicht ausgeführt wird, während das Installationsprogramm Dateien kopiert oder Assemblys im globalen Assemblycache ablegt.</span><span class="sxs-lookup"><span data-stu-id="52adc-455">This ensures that the service does not execute while the installer is copying files or putting assemblies in the global assembly cache.</span></span> <span data-ttu-id="52adc-456">Die folgende Befehlszeile von "Ngen.exe" beendet den Dienst:</span><span class="sxs-lookup"><span data-stu-id="52adc-456">The following Ngen.exe command line pauses the service:</span></span>

```console
ngen queue pause
```

<span data-ttu-id="52adc-457">Nachdem alle verzögerten Vorgänge in die Warteschlange gestellt wurden, kann der Dienst mit dem folgenden Befehl fortgesetzt werden:</span><span class="sxs-lookup"><span data-stu-id="52adc-457">When all deferred operations have been queued, the following command allows the service to resume:</span></span>

```console
ngen queue continue
```

<span data-ttu-id="52adc-458">Um die Generierung von systemeigenen Images zu verzögern, wenn eine neue Anwendung installiert oder eine freigegebene Komponente aktualisiert wird, verwenden Sie die `/queue`-Option mit der `install`- oder der `update`-Aktion.</span><span class="sxs-lookup"><span data-stu-id="52adc-458">To defer native image generation when installing a new application or when updating a shared component, use the `/queue` option with the `install` or `update` actions.</span></span> <span data-ttu-id="52adc-459">Mit den folgenden Befehlszeilen in "Ngen.exe" wird ein systemeigenes Image für eine freigegebene Komponente installiert und werden alle Stammelemente aktualisiert, die möglicherweise betroffen sind:</span><span class="sxs-lookup"><span data-stu-id="52adc-459">The following Ngen.exe command lines install a native image for a shared component and perform an update of all roots that may have been affected:</span></span>

```console
ngen install MyComponent /queue
ngen update /queue
```

<span data-ttu-id="52adc-460">Die `update`-Aktion bewirkt, dass alle systemeigenen Images neu generiert werden, die ungültig geworden sind, nicht nur diejenigen, für die `MyComponent` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="52adc-460">The `update` action regenerates all native images that have been invalidated, not just those that use `MyComponent`.</span></span>

<span data-ttu-id="52adc-461">Wenn die Anwendung aus vielen Stammelemente besteht, können Sie die Priorität der verzögerten Aktionen steuern.</span><span class="sxs-lookup"><span data-stu-id="52adc-461">If your application consists of many roots, you can control the priority of the deferred actions.</span></span> <span data-ttu-id="52adc-462">Die folgenden Befehle stellen die Installation der drei Stammelemente in die Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="52adc-462">The following commands queue the installation of three roots.</span></span> <span data-ttu-id="52adc-463">`Assembly1` wird zuerst installiert, ohne dass auf eine Leerlaufzeit gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="52adc-463">`Assembly1` is installed first, without waiting for idle time.</span></span> <span data-ttu-id="52adc-464">`Assembly2` wird ebenfalls ohne Warten auf eine Leerlaufzeit installiert, aber erst, nachdem alle Aktionen mit Priorität 1 abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="52adc-464">`Assembly2` is also installed without waiting for idle time, but after all priority 1 actions have completed.</span></span> <span data-ttu-id="52adc-465">`Assembly3` wird installiert, wenn der Dienst feststellt, dass sich der Computer im Leerlauf befindet.</span><span class="sxs-lookup"><span data-stu-id="52adc-465">`Assembly3` is installed when the service detects that the computer is idle.</span></span>

```console
ngen install Assembly1 /queue:1
ngen install Assembly2 /queue:2
ngen install Assembly3 /queue:3
```

<span data-ttu-id="52adc-466">Durch Verwenden der `executeQueuedItems`-Aktion können Sie erzwingen, dass in der Warteschlange befindliche Aktionen gleichzeitig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="52adc-466">You can force queued actions to occur synchronously by using the `executeQueuedItems` action.</span></span> <span data-ttu-id="52adc-467">Wenn Sie die optionale Priorität angeben, wirkt sich diese Aktion nur auf die Aktionen in der Warteschlange aus, die dieselbe oder eine niedrigere Priorität haben.</span><span class="sxs-lookup"><span data-stu-id="52adc-467">If you supply the optional priority, this action affects only the queued actions that have equal or lower priority.</span></span> <span data-ttu-id="52adc-468">Da die Standardpriorität gleich 3 ist, verarbeitet der folgende "Ngen.exe"-Befehl alle in der Warteschlange befindlichen Aktionen sofort, und er wird erst beendet, wenn die Aktionen abgeschlossen sind:</span><span class="sxs-lookup"><span data-stu-id="52adc-468">The default priority is 3, so the following Ngen.exe command processes all queued actions immediately, and does not return until they are finished:</span></span>

```console
ngen executeQueuedItems
```

<span data-ttu-id="52adc-469">Synchrone Befehle werden von "Ngen.exe" ausgeführt, und für sie wird nicht Dienst für systemeigene Abbilder verwendet.</span><span class="sxs-lookup"><span data-stu-id="52adc-469">Synchronous commands are executed by Ngen.exe and do not use the native image service.</span></span> <span data-ttu-id="52adc-470">Sie können Aktionen mit "Ngen.exe" ausführen, während der Dienst für systemeigene Abbilder ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="52adc-470">You can execute actions using Ngen.exe while the native image service is running.</span></span>

### <a name="service-shutdown"></a><span data-ttu-id="52adc-471">Beenden des Diensts</span><span class="sxs-lookup"><span data-stu-id="52adc-471">Service Shutdown</span></span>

<span data-ttu-id="52adc-472">Nachdem der Dienst durch Ausführen eines "Ngen.exe"-Befehls, der die `/queue`-Option enthält, gestartet wurde, wird er im Hintergrund ausgeführt, bis alle Aktionen abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="52adc-472">After being initiated by the execution of an Ngen.exe command that includes the `/queue` option, the service runs in the background until all actions have been completed.</span></span> <span data-ttu-id="52adc-473">Der Dienst speichert seinen Zustand, sodass er, sofern erforderlich, selbst nach mehreren Neustarts fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="52adc-473">The service saves its state so that it can continue through multiple reboots if necessary.</span></span> <span data-ttu-id="52adc-474">Wenn der Dienst feststellt, dass es keine weiteren Aktionen in der Warteschlange gibt, setzt er seinen Status zurück, sodass er beim nächsten Computerstart nicht neu gestartet wird, und dann beendet sich der Dienst selbst.</span><span class="sxs-lookup"><span data-stu-id="52adc-474">When the service detects that there are no more actions queued, it resets its status so that it will not restart the next time the computer is booted, and then it shuts itself down.</span></span>

### <a name="service-interaction-with-clients"></a><span data-ttu-id="52adc-475">Dienstinteraktion mit Clients</span><span class="sxs-lookup"><span data-stu-id="52adc-475">Service Interaction with Clients</span></span>

<span data-ttu-id="52adc-476">In .NET Framework 2.0 erfolgt die einzige Interaktion mit dem Dienst für systemeigene Abbilder über das Befehlszeilentool "Ngen.exe".</span><span class="sxs-lookup"><span data-stu-id="52adc-476">In the .NET Framework version 2.0, the only interaction with the native image service is through the command-line tool Ngen.exe.</span></span> <span data-ttu-id="52adc-477">Verwenden Sie das Befehlszeilentool in Installationsskripts, um Aktionen für den Dienst für systemeigene Abbilder in die Warteschlange zu stellen und mit dem Dienst zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="52adc-477">Use the command-line tool in installation scripts to queue actions for the native image service and to interact with the service.</span></span>

## <a name="see-also"></a><span data-ttu-id="52adc-478">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52adc-478">See also</span></span>

- [<span data-ttu-id="52adc-479">Extras</span><span class="sxs-lookup"><span data-stu-id="52adc-479">Tools</span></span>](index.md)
- [<span data-ttu-id="52adc-480">Der verwaltete Ausführungsprozess</span><span class="sxs-lookup"><span data-stu-id="52adc-480">Managed Execution Process</span></span>](../../standard/managed-execution-process.md)
- [<span data-ttu-id="52adc-481">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="52adc-481">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="52adc-482">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="52adc-482">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
