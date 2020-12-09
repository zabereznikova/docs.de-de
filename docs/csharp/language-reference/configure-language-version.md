---
title: Verwaltung der C#-Sprachversion – Leitfaden für C#
description: Erfahren Sie mehr darüber, wie und aus welchen Gründen die C#-Sprachversion basierend auf Ihrem Projekt bestimmt wird. Erfahren Sie, wie Sie den Standardwert manuell überschreiben.
ms.custom: updateeachrelease
ms.date: 08/11/2020
ms.openlocfilehash: b022b726861bd6ea45b188df44549dc279d34a74
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "96598917"
---
# <a name="c-language-versioning"></a><span data-ttu-id="217f6-104">Verwaltung der C#-Sprachversion</span><span class="sxs-lookup"><span data-stu-id="217f6-104">C# language versioning</span></span>

<span data-ttu-id="217f6-105">Der C#-Compiler bestimmt eine Standardsprachversion, die auf den Zielframeworks Ihres Projekts basiert.</span><span class="sxs-lookup"><span data-stu-id="217f6-105">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="217f6-106">In Visual Studio gibt es keine Benutzeroberfläche zum Ändern dieses Werts, aber Sie können ihn ändern, indem Sie die *CSPROJ*-Datei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="217f6-106">Visual Studio doesn't provide a UI to change the value, but you can change it by editing the *csproj* file.</span></span> <span data-ttu-id="217f6-107">Mit der Auswahl des Standardwerts wird sichergestellt, dass Sie die neueste Sprachversion nutzen, die mit Ihrem Zielframework kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="217f6-107">The choice of default ensures that you use the latest language version compatible with your target framework.</span></span> <span data-ttu-id="217f6-108">So profitieren Sie vom Zugriff auf die neuesten Sprachfeatures, die mit dem Zielframework Ihres Projekts kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="217f6-108">You benefit from access to the latest language features compatible with your project's target.</span></span> <span data-ttu-id="217f6-109">Mit dem Standardwert wird außerdem sichergestellt, dass Sie keine Sprache verwenden, die Typen oder Runtimeverhalten erfordert, die nicht im Zielframework verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="217f6-109">This default choice also ensures you don't use a language that requires types or runtime behavior not available in your target framework.</span></span> <span data-ttu-id="217f6-110">Wenn Sie eine Sprachversion auswählen, die neuer als die Standardeinstellung ist, können Kompilierzeit- und Runtimefehler auftreten, die schwer zu diagnostizieren sind.</span><span class="sxs-lookup"><span data-stu-id="217f6-110">Choosing a language version newer than the default can cause hard to diagnose compile-time and runtime errors.</span></span>

<span data-ttu-id="217f6-111">Die in diesem Artikel aufgeführten Regeln gelten für den Compiler, der in Visual Studio 2019 oder dem .NET SDK enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="217f6-111">The rules in this article apply to the compiler delivered with Visual Studio 2019 or the .NET SDK.</span></span> <span data-ttu-id="217f6-112">Die C#-Compiler, die Teil der Visual Studio 2017-Installation oder von früheren .NET Core SDK-Versionen sind, sind standardmäßig auf C# 7.0 ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="217f6-112">The C# compilers that are part of the Visual Studio 2017 installation or earlier .NET Core SDK versions target C# 7.0 by default.</span></span>

<span data-ttu-id="217f6-113">C# 8.0 wird nur in .NET Core 3.x und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="217f6-113">C# 8.0 is supported only on .NET Core 3.x and newer versions.</span></span> <span data-ttu-id="217f6-114">Viele der neuesten Features erfordern Bibliotheks- und Runtimefeatures, die mit .NET Core 3.x eingeführt wurden:</span><span class="sxs-lookup"><span data-stu-id="217f6-114">Many of the newest features require library and runtime features introduced in .NET Core 3.x:</span></span>

- <span data-ttu-id="217f6-115">[Die Implementierung von Standardschnittstellen](../whats-new/csharp-8.md#default-interface-methods) erfordert neue Features in der .NET Core 3.0-CLR.</span><span class="sxs-lookup"><span data-stu-id="217f6-115">[Default interface implementation](../whats-new/csharp-8.md#default-interface-methods) requires new features in the .NET Core 3.0 CLR.</span></span>
- <span data-ttu-id="217f6-116">Für [asynchrone Datenströme](../whats-new/csharp-8.md#asynchronous-streams) sind die neuen Typen <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType> und <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType> erforderlich.</span><span class="sxs-lookup"><span data-stu-id="217f6-116">[Async streams](../whats-new/csharp-8.md#asynchronous-streams) require the new types <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType>, and <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="217f6-117">Für [Indizes und Bereiche](../whats-new/csharp-8.md#indices-and-ranges) sind die neuen Typen <xref:System.Index?displayProperty=nameWithType> und <xref:System.Range?displayProperty=nameWithType> erforderlich.</span><span class="sxs-lookup"><span data-stu-id="217f6-117">[Indices and ranges](../whats-new/csharp-8.md#indices-and-ranges) require the new types <xref:System.Index?displayProperty=nameWithType> and <xref:System.Range?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="217f6-118">[Verweistypen, die NULL-Werte zulassen](../whats-new/csharp-8.md#nullable-reference-types), nutzen mehrere [Attribute](attributes/nullable-analysis.md), um bessere Warnungen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="217f6-118">[Nullable reference types](../whats-new/csharp-8.md#nullable-reference-types) make use of several [attributes](attributes/nullable-analysis.md) to provide better warnings.</span></span> <span data-ttu-id="217f6-119">Diese Attribute wurden in .NET Core 3.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="217f6-119">Those attributes were added in .NET Core 3.0.</span></span> <span data-ttu-id="217f6-120">Andere Zielframeworks wurden nicht mit diesen Attributen versehen.</span><span class="sxs-lookup"><span data-stu-id="217f6-120">Other target frameworks haven't been annotated with any of these attributes.</span></span> <span data-ttu-id="217f6-121">Das bedeutet, dass Warnungen, die NULL-Werte zulassen, mögliche Probleme nicht exakt widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="217f6-121">That means nullable warnings may not accurately reflect potential issues.</span></span>

<span data-ttu-id="217f6-122">C# 9.0 wird nur in .NET 5 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="217f6-122">C# 9.0 is supported only on .NET 5 and newer versions.</span></span>

## <a name="defaults"></a><span data-ttu-id="217f6-123">der Arbeitszeittabelle</span><span class="sxs-lookup"><span data-stu-id="217f6-123">Defaults</span></span>

<span data-ttu-id="217f6-124">Der Compiler bestimmt basierend auf den folgenden Regeln eine Standardversion:</span><span class="sxs-lookup"><span data-stu-id="217f6-124">The compiler determines a default based on these rules:</span></span>

| <span data-ttu-id="217f6-125">Zielframework</span><span class="sxs-lookup"><span data-stu-id="217f6-125">Target framework</span></span> | <span data-ttu-id="217f6-126">Version</span><span class="sxs-lookup"><span data-stu-id="217f6-126">version</span></span> | <span data-ttu-id="217f6-127">C#-Sprachversionsstandard</span><span class="sxs-lookup"><span data-stu-id="217f6-127">C# language version default</span></span> |
|------------------|---------|-----------------------------|
| <span data-ttu-id="217f6-128">.NET</span><span class="sxs-lookup"><span data-stu-id="217f6-128">.NET</span></span>             | <span data-ttu-id="217f6-129">5.x</span><span class="sxs-lookup"><span data-stu-id="217f6-129">5.x</span></span>     | <span data-ttu-id="217f6-130">C# 9.0</span><span class="sxs-lookup"><span data-stu-id="217f6-130">C# 9.0</span></span>                      |
| <span data-ttu-id="217f6-131">.NET Core</span><span class="sxs-lookup"><span data-stu-id="217f6-131">.NET Core</span></span>        | <span data-ttu-id="217f6-132">3.x</span><span class="sxs-lookup"><span data-stu-id="217f6-132">3.x</span></span>     | <span data-ttu-id="217f6-133">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="217f6-133">C# 8.0</span></span>                      |
| <span data-ttu-id="217f6-134">.NET Core</span><span class="sxs-lookup"><span data-stu-id="217f6-134">.NET Core</span></span>        | <span data-ttu-id="217f6-135">2.x</span><span class="sxs-lookup"><span data-stu-id="217f6-135">2.x</span></span>     | <span data-ttu-id="217f6-136">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="217f6-136">C# 7.3</span></span>                      |
| <span data-ttu-id="217f6-137">.NET-Standard</span><span class="sxs-lookup"><span data-stu-id="217f6-137">.NET Standard</span></span>    | <span data-ttu-id="217f6-138">2.1</span><span class="sxs-lookup"><span data-stu-id="217f6-138">2.1</span></span>     | <span data-ttu-id="217f6-139">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="217f6-139">C# 8.0</span></span>                      |
| <span data-ttu-id="217f6-140">.NET-Standard</span><span class="sxs-lookup"><span data-stu-id="217f6-140">.NET Standard</span></span>    | <span data-ttu-id="217f6-141">2.0</span><span class="sxs-lookup"><span data-stu-id="217f6-141">2.0</span></span>     | <span data-ttu-id="217f6-142">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="217f6-142">C# 7.3</span></span>                      |
| <span data-ttu-id="217f6-143">.NET-Standard</span><span class="sxs-lookup"><span data-stu-id="217f6-143">.NET Standard</span></span>    | <span data-ttu-id="217f6-144">1.x</span><span class="sxs-lookup"><span data-stu-id="217f6-144">1.x</span></span>     | <span data-ttu-id="217f6-145">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="217f6-145">C# 7.3</span></span>                      |
| <span data-ttu-id="217f6-146">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="217f6-146">.NET Framework</span></span>   | <span data-ttu-id="217f6-147">alle</span><span class="sxs-lookup"><span data-stu-id="217f6-147">all</span></span>     | <span data-ttu-id="217f6-148">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="217f6-148">C# 7.3</span></span>                      |

<span data-ttu-id="217f6-149">Wenn Ihr Projekt auf eine Vorschauframework abzielt, das eine entsprechende Vorschausprachversion besitzt, wird die Vorschausprachversion als Sprachversion verwendet.</span><span class="sxs-lookup"><span data-stu-id="217f6-149">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="217f6-150">In dieser Vorschau können Sie die neuesten Features in beliebigen Umgebungen verwenden, ohne Auswirkungen auf Projekte für eine veröffentlichte .NET Core-Version zu haben.</span><span class="sxs-lookup"><span data-stu-id="217f6-150">You use the latest features with that preview in any environment, without affecting projects that target a released .NET Core version.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="217f6-151">Visual Studio 2017 hat allen erstellten Projektdateien einen `<LangVersion>latest</LangVersion>`-Eintrag hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="217f6-151">Visual Studio 2017 added a `<LangVersion>latest</LangVersion>` entry to any project files it created.</span></span> <span data-ttu-id="217f6-152">Dieser lautete *C# 7.0*, als er hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="217f6-152">That meant *C# 7.0* when it was added.</span></span> <span data-ttu-id="217f6-153">Wenn Sie jedoch ein Upgrade auf Visual Studio 2019 durchführen, ist dies unabhängig vom Zielframework die neueste veröffentlichte Version.</span><span class="sxs-lookup"><span data-stu-id="217f6-153">However, once you upgrade to Visual Studio 2019, that means the latest released version, regardless of the target framework.</span></span> <span data-ttu-id="217f6-154">Diese Projekte setzen jetzt [das Standardverhalten außer Kraft](#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="217f6-154">These projects now [override the default behavior](#override-a-default).</span></span> <span data-ttu-id="217f6-155">Bearbeiten Sie die Projektdatei, und entfernen Sie den Knoten.</span><span class="sxs-lookup"><span data-stu-id="217f6-155">You should edit the project file and remove that node.</span></span> <span data-ttu-id="217f6-156">Anschließend verwendet das Projekt die für das Zielframework empfohlene Compilerversion.</span><span class="sxs-lookup"><span data-stu-id="217f6-156">Then, your project will use the compiler version recommended for your target framework.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="217f6-157">Überschreiben eines Standardwerts</span><span class="sxs-lookup"><span data-stu-id="217f6-157">Override a default</span></span>

<span data-ttu-id="217f6-158">Wenn Sie Ihre C#-Version explizit angeben müssen, haben Sie verschiedene Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="217f6-158">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="217f6-159">Manuelles Bearbeiten der [Projektdatei](#edit-the-project-file)</span><span class="sxs-lookup"><span data-stu-id="217f6-159">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="217f6-160">Festlegen der Sprachversion [für mehrere Projekte in einem Unterverzeichnis](#configure-multiple-projects)</span><span class="sxs-lookup"><span data-stu-id="217f6-160">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="217f6-161">Konfigurieren der [Compileroption `-langversion`](compiler-options/langversion-compiler-option.md)</span><span class="sxs-lookup"><span data-stu-id="217f6-161">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md).</span></span>

> [!TIP]
> <span data-ttu-id="217f6-162">Wenn Sie wissen möchten, welche Sprachversion Sie derzeit verwenden, fügen Sie `#error version` (Groß-/Kleinschreibung beachten) in Ihren Code ein.</span><span class="sxs-lookup"><span data-stu-id="217f6-162">To know what language version you're currently using, put `#error version` (case sensitive) in your code.</span></span> <span data-ttu-id="217f6-163">Dadurch erzeugt der Compiler eine Diagnose (CS8304) mit einer Nachricht, die die verwendete Compilerversion und die aktuelle ausgewählte Sprachversion enthält.</span><span class="sxs-lookup"><span data-stu-id="217f6-163">This makes the compiler produce a diagnostic, CS8304, with a message containing the compiler version being used and the current selected language version.</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="217f6-164">Bearbeiten der Projektdatei</span><span class="sxs-lookup"><span data-stu-id="217f6-164">Edit the project file</span></span>

<span data-ttu-id="217f6-165">Sie können die Sprachversion in der Projektdatei festlegen.</span><span class="sxs-lookup"><span data-stu-id="217f6-165">You can set the language version in your project file.</span></span> <span data-ttu-id="217f6-166">Wenn Sie beispielsweise expliziten Zugriff auf Previewfunktionen wünschen, fügen Sie ein Element wie folgt hinzu:</span><span class="sxs-lookup"><span data-stu-id="217f6-166">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="217f6-167">Der Wert `preview` verwendet die neueste verfügbare Vorschauversion der Sprache C#, die Ihr Compiler unterstützt.</span><span class="sxs-lookup"><span data-stu-id="217f6-167">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="217f6-168">Konfigurieren mehrerer Projekte</span><span class="sxs-lookup"><span data-stu-id="217f6-168">Configure multiple projects</span></span>

<span data-ttu-id="217f6-169">Sie können eine **Directory.Build.props**-Datei erstellen, die das Element `<LangVersion>` enthält, um mehrere Projekte zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="217f6-169">To configure multiple projects, you can create a **Directory.Build.props** file that contains the `<LangVersion>` element.</span></span> <span data-ttu-id="217f6-170">In der Regel führen Sie dies im Projektmappenverzeichnis durch.</span><span class="sxs-lookup"><span data-stu-id="217f6-170">You typically do that in your solution directory.</span></span> <span data-ttu-id="217f6-171">Fügen Sie Folgendes in eine **Directory.Build.props**-Datei in Ihrem Projektmappenverzeichnis ein:</span><span class="sxs-lookup"><span data-stu-id="217f6-171">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="217f6-172">Builds in allen Unterverzeichnissen des Verzeichnisses, das diese Datei enthält, verwenden die C#-Vorschauversion.</span><span class="sxs-lookup"><span data-stu-id="217f6-172">Builds in all subdirectories of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="217f6-173">Weitere Informationen finden Sie im Artikel zum [Anpassen Ihres Builds](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="217f6-173">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="217f6-174">Referenz zur C#-Sprachversion</span><span class="sxs-lookup"><span data-stu-id="217f6-174">C# language version reference</span></span>

<span data-ttu-id="217f6-175">In der folgenden Tabelle sind alle aktuellen C#-Sprachversionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="217f6-175">The following table shows all current C# language versions.</span></span> <span data-ttu-id="217f6-176">Wenn Ihr Compiler älter ist, versteht er möglicherweise nicht alle Werte.</span><span class="sxs-lookup"><span data-stu-id="217f6-176">Your compiler may not necessarily understand every value if it's older.</span></span> <span data-ttu-id="217f6-177">Wenn Sie das neueste .NET SDK installieren, erhalten Sie Zugriff auf alle aufgelisteten Syntaxversionen.</span><span class="sxs-lookup"><span data-stu-id="217f6-177">If you install the latest .NET SDK, then you have access to everything listed.</span></span>

[!INCLUDE [langversion-table](includes/langversion-table.md)]

> [!TIP]
> <span data-ttu-id="217f6-178">Öffnen Sie die [Developer-Eingabeaufforderung für Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), und führen Sie den folgenden Befehl aus, um die Liste der auf Ihrem Computer verfügbaren Sprachversionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="217f6-178">Open the [Developer Command Prompt for Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), and run the following command to see the listing of language versions available on your machine.</span></span>
>
> ```CMD
> csc -langversion:?
> ```
>
> <span data-ttu-id="217f6-179">Wenn Sie die Kompilierungsoption [-langversion](compiler-options/langversion-compiler-option.md) wie folgt abfragen, wird etwa Folgendes ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="217f6-179">Questioning the [-langversion](compiler-options/langversion-compiler-option.md) compile option like this, will print something similar to the following:</span></span>
>
> ```CMD
> Supported language versions:
> default
> 1
> 2
> 3
> 4
> 5
> 6
> 7.0
> 7.1
> 7.2
> 7.3
> 8.0
> 9.0 (default)
> latestmajor
> preview
> latest
> ```
