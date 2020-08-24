---
title: Verwaltung der C#-Sprachversion – Leitfaden für C#
description: Erfahren Sie mehr darüber, wie und aus welchen Gründen die C#-Sprachversion basierend auf Ihrem Projekt bestimmt wird. Erfahren Sie, wie Sie den Standardwert manuell überschreiben.
ms.custom: updateeachrelease
ms.date: 05/20/2020
ms.openlocfilehash: a27f3210f399f1bed190c18d778cf3824772d576
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656851"
---
# <a name="c-language-versioning"></a><span data-ttu-id="d13dd-104">Verwaltung der C#-Sprachversion</span><span class="sxs-lookup"><span data-stu-id="d13dd-104">C# language versioning</span></span>

<span data-ttu-id="d13dd-105">Der C#-Compiler bestimmt eine Standardsprachversion, die auf den Zielframeworks Ihres Projekts basiert.</span><span class="sxs-lookup"><span data-stu-id="d13dd-105">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="d13dd-106">In Visual Studio gibt es keine Benutzeroberfläche zum Ändern dieses Werts, aber Sie können ihn ändern, indem Sie die *CSPROJ*-Datei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="d13dd-106">Visual Studio doesn't provide a UI to change the value, but you can change it by editing the *csproj* file.</span></span> <span data-ttu-id="d13dd-107">Mit der Auswahl des Standardwerts wird sichergestellt, dass Sie die neueste Sprachversion nutzen, die mit Ihrem Zielframework kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="d13dd-107">The choice of default ensures that you use the latest language version compatible with your target framework.</span></span> <span data-ttu-id="d13dd-108">So profitieren Sie vom Zugriff auf die neuesten Sprachfeatures, die mit dem Zielframework Ihres Projekts kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="d13dd-108">You benefit from access to the latest language features compatible with your project's target.</span></span> <span data-ttu-id="d13dd-109">Mit dem Standardwert wird außerdem sichergestellt, dass Sie keine Sprache verwenden, die Typen oder Runtimeverhalten erfordert, die nicht im Zielframework verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d13dd-109">This default choice also ensures you don't use a language that requires types or runtime behavior not available in your target framework.</span></span> <span data-ttu-id="d13dd-110">Wenn Sie eine Sprachversion auswählen, die neuer als die Standardeinstellung ist, können Kompilierzeit- und Runtimefehler auftreten, die schwer zu diagnostizieren sind.</span><span class="sxs-lookup"><span data-stu-id="d13dd-110">Choosing a language version newer than the default can cause hard to diagnose compile-time and runtime errors.</span></span>

<span data-ttu-id="d13dd-111">Die in diesem Artikel aufgeführten Regeln gelten für den Compiler, der im Lieferumfang von Visual Studio 2019 oder dem .NET Core 3.0 SDK enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="d13dd-111">The rules in this article apply to the compiler delivered with Visual Studio 2019 or the .NET Core 3.0 SDK.</span></span> <span data-ttu-id="d13dd-112">Die C#-Compiler, die Teil der Visual Studio 2017-Installation oder von früheren .NET Core SDK-Versionen sind, sind standardmäßig auf C# 7.0 ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="d13dd-112">The C# compilers that are part of the Visual Studio 2017 installation or earlier .NET Core SDK versions target C# 7.0 by default.</span></span>

<span data-ttu-id="d13dd-113">C# 8.0 (und höher) wird nur in .NET Core 3.x und neueren Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d13dd-113">C# 8.0 (and higher) is supported only on .NET Core 3.x and newer versions.</span></span> <span data-ttu-id="d13dd-114">Viele der neuesten Features erfordern Bibliotheks- und Runtimefeatures, die mit .NET Core 3.x eingeführt wurden:</span><span class="sxs-lookup"><span data-stu-id="d13dd-114">Many of the newest features require library and runtime features introduced in .NET Core 3.x:</span></span>

- <span data-ttu-id="d13dd-115">[Die Implementierung von Standardschnittstellen](../whats-new/csharp-8.md#default-interface-methods) erfordert neue Features in der .NET Core 3.0-CLR.</span><span class="sxs-lookup"><span data-stu-id="d13dd-115">[Default interface implementation](../whats-new/csharp-8.md#default-interface-methods) requires new features in the .NET Core 3.0 CLR.</span></span>
- <span data-ttu-id="d13dd-116">Für [asynchrone Datenströme](../whats-new/csharp-8.md#asynchronous-streams) sind die neuen Typen <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType> und <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType> erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d13dd-116">[Async streams](../whats-new/csharp-8.md#asynchronous-streams) require the new types <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType>, and <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="d13dd-117">Für [Indizes und Bereiche](../whats-new/csharp-8.md#indices-and-ranges) sind die neuen Typen <xref:System.Index?displayProperty=nameWithType> und <xref:System.Range?displayProperty=nameWithType> erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d13dd-117">[Indices and ranges](../whats-new/csharp-8.md#indices-and-ranges) require the new types <xref:System.Index?displayProperty=nameWithType> and <xref:System.Range?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="d13dd-118">[Verweistypen, die NULL-Werte zulassen](../whats-new/csharp-8.md#nullable-reference-types), nutzen mehrere [Attribute](attributes/nullable-analysis.md), um bessere Warnungen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d13dd-118">[Nullable reference types](../whats-new/csharp-8.md#nullable-reference-types) make use of several [attributes](attributes/nullable-analysis.md) to provide better warnings.</span></span> <span data-ttu-id="d13dd-119">Diese Attribute wurden in .NET Core 3.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d13dd-119">Those attributes were added in .NET Core 3.0.</span></span> <span data-ttu-id="d13dd-120">Andere Zielframeworks wurden nicht mit diesen Attributen versehen.</span><span class="sxs-lookup"><span data-stu-id="d13dd-120">Other target frameworks haven't been annotated with any of these attributes.</span></span> <span data-ttu-id="d13dd-121">Das bedeutet, dass Warnungen, die NULL-Werte zulassen, mögliche Probleme nicht exakt widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="d13dd-121">That means nullable warnings may not accurately reflect potential issues.</span></span>

## <a name="defaults"></a><span data-ttu-id="d13dd-122">der Arbeitszeittabelle</span><span class="sxs-lookup"><span data-stu-id="d13dd-122">Defaults</span></span>

<span data-ttu-id="d13dd-123">Der Compiler bestimmt basierend auf den folgenden Regeln eine Standardversion:</span><span class="sxs-lookup"><span data-stu-id="d13dd-123">The compiler determines a default based on these rules:</span></span>

| <span data-ttu-id="d13dd-124">Zielframework</span><span class="sxs-lookup"><span data-stu-id="d13dd-124">Target framework</span></span> | <span data-ttu-id="d13dd-125">Version</span><span class="sxs-lookup"><span data-stu-id="d13dd-125">version</span></span> | <span data-ttu-id="d13dd-126">C#-Sprachversionsstandard</span><span class="sxs-lookup"><span data-stu-id="d13dd-126">C# language version default</span></span> |
|------------------|---------|-----------------------------|
| <span data-ttu-id="d13dd-127">.NET Core</span><span class="sxs-lookup"><span data-stu-id="d13dd-127">.NET Core</span></span>        | <span data-ttu-id="d13dd-128">3.x</span><span class="sxs-lookup"><span data-stu-id="d13dd-128">3.x</span></span>     | <span data-ttu-id="d13dd-129">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="d13dd-129">C# 8.0</span></span>                      |
| <span data-ttu-id="d13dd-130">.NET Core</span><span class="sxs-lookup"><span data-stu-id="d13dd-130">.NET Core</span></span>        | <span data-ttu-id="d13dd-131">2.x</span><span class="sxs-lookup"><span data-stu-id="d13dd-131">2.x</span></span>     | <span data-ttu-id="d13dd-132">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="d13dd-132">C# 7.3</span></span>                      |
| <span data-ttu-id="d13dd-133">.NET-Standard</span><span class="sxs-lookup"><span data-stu-id="d13dd-133">.NET Standard</span></span>    | <span data-ttu-id="d13dd-134">2.1</span><span class="sxs-lookup"><span data-stu-id="d13dd-134">2.1</span></span>     | <span data-ttu-id="d13dd-135">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="d13dd-135">C# 8.0</span></span>                      |
| <span data-ttu-id="d13dd-136">.NET-Standard</span><span class="sxs-lookup"><span data-stu-id="d13dd-136">.NET Standard</span></span>    | <span data-ttu-id="d13dd-137">2.0</span><span class="sxs-lookup"><span data-stu-id="d13dd-137">2.0</span></span>     | <span data-ttu-id="d13dd-138">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="d13dd-138">C# 7.3</span></span>                      |
| <span data-ttu-id="d13dd-139">.NET-Standard</span><span class="sxs-lookup"><span data-stu-id="d13dd-139">.NET Standard</span></span>    | <span data-ttu-id="d13dd-140">1.x</span><span class="sxs-lookup"><span data-stu-id="d13dd-140">1.x</span></span>     | <span data-ttu-id="d13dd-141">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="d13dd-141">C# 7.3</span></span>                      |
| <span data-ttu-id="d13dd-142">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="d13dd-142">.NET Framework</span></span>   | <span data-ttu-id="d13dd-143">alle</span><span class="sxs-lookup"><span data-stu-id="d13dd-143">all</span></span>     | <span data-ttu-id="d13dd-144">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="d13dd-144">C# 7.3</span></span>                      |

<span data-ttu-id="d13dd-145">Wenn Ihr Projekt auf eine Vorschauframework abzielt, das eine entsprechende Vorschausprachversion besitzt, wird die Vorschausprachversion als Sprachversion verwendet.</span><span class="sxs-lookup"><span data-stu-id="d13dd-145">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="d13dd-146">In dieser Vorschau können Sie die neuesten Features in beliebigen Umgebungen verwenden, ohne Auswirkungen auf Projekte für eine veröffentlichte .NET Core-Version zu haben.</span><span class="sxs-lookup"><span data-stu-id="d13dd-146">You use the latest features with that preview in any environment, without affecting projects that target a released .NET Core version.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="d13dd-147">Überschreiben eines Standardwerts</span><span class="sxs-lookup"><span data-stu-id="d13dd-147">Override a default</span></span>

<span data-ttu-id="d13dd-148">Wenn Sie Ihre C#-Version explizit angeben müssen, haben Sie verschiedene Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="d13dd-148">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="d13dd-149">Manuelles Bearbeiten der [Projektdatei](#edit-the-project-file)</span><span class="sxs-lookup"><span data-stu-id="d13dd-149">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="d13dd-150">Festlegen der Sprachversion [für mehrere Projekte in einem Unterverzeichnis](#configure-multiple-projects)</span><span class="sxs-lookup"><span data-stu-id="d13dd-150">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="d13dd-151">Konfigurieren der [Compileroption `-langversion`](compiler-options/langversion-compiler-option.md)</span><span class="sxs-lookup"><span data-stu-id="d13dd-151">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md).</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="d13dd-152">Bearbeiten der Projektdatei</span><span class="sxs-lookup"><span data-stu-id="d13dd-152">Edit the project file</span></span>

<span data-ttu-id="d13dd-153">Sie können die Sprachversion in der Projektdatei festlegen.</span><span class="sxs-lookup"><span data-stu-id="d13dd-153">You can set the language version in your project file.</span></span> <span data-ttu-id="d13dd-154">Wenn Sie beispielsweise expliziten Zugriff auf Previewfunktionen wünschen, fügen Sie ein Element wie folgt hinzu:</span><span class="sxs-lookup"><span data-stu-id="d13dd-154">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="d13dd-155">Der Wert `preview` verwendet die neueste verfügbare Vorschauversion der Sprache C#, die Ihr Compiler unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d13dd-155">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="d13dd-156">Konfigurieren mehrerer Projekte</span><span class="sxs-lookup"><span data-stu-id="d13dd-156">Configure multiple projects</span></span>

<span data-ttu-id="d13dd-157">Sie können eine **Directory.Build.props**-Datei erstellen, die das Element `<LangVersion>` enthält, um mehrere Projekte zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d13dd-157">To configure multiple projects, you can create a **Directory.Build.props** file that contains the `<LangVersion>` element.</span></span> <span data-ttu-id="d13dd-158">In der Regel führen Sie dies im Projektmappenverzeichnis durch.</span><span class="sxs-lookup"><span data-stu-id="d13dd-158">You typically do that in your solution directory.</span></span> <span data-ttu-id="d13dd-159">Fügen Sie Folgendes in eine **Directory.Build.props**-Datei in Ihrem Projektmappenverzeichnis ein:</span><span class="sxs-lookup"><span data-stu-id="d13dd-159">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="d13dd-160">Builds in allen Unterverzeichnissen des Verzeichnisses, das diese Datei enthält, verwenden die C#-Vorschauversion.</span><span class="sxs-lookup"><span data-stu-id="d13dd-160">Builds in all subdirectories of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="d13dd-161">Weitere Informationen finden Sie im Artikel zum [Anpassen Ihres Builds](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="d13dd-161">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="d13dd-162">Referenz zur C#-Sprachversion</span><span class="sxs-lookup"><span data-stu-id="d13dd-162">C# language version reference</span></span>

<span data-ttu-id="d13dd-163">In der folgenden Tabelle sind alle aktuellen C#-Sprachversionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d13dd-163">The following table shows all current C# language versions.</span></span> <span data-ttu-id="d13dd-164">Wenn Ihr Compiler älter ist, versteht er möglicherweise nicht alle Werte.</span><span class="sxs-lookup"><span data-stu-id="d13dd-164">Your compiler may not necessarily understand every value if it's older.</span></span> <span data-ttu-id="d13dd-165">Wenn Sie .NET Core 3.0 oder höher installieren, verfügen Sie über Zugriff auf alle aufgeführten Elemente.</span><span class="sxs-lookup"><span data-stu-id="d13dd-165">If you install .NET Core 3.0 or later, then you have access to everything listed.</span></span>

[!INCLUDE [langversion-table](includes/langversion-table.md)]

> [!TIP]
> <span data-ttu-id="d13dd-166">Öffnen Sie die [Developer-Eingabeaufforderung für Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), und führen Sie den folgenden Befehl aus, um die Liste der auf Ihrem Computer verfügbaren Sprachversionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d13dd-166">Open the [Developer Command Prompt for Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), and run the following command to see the listing of language versions available on your machine.</span></span>
>
> ```CMD
> csc -langversion:?
> ```
>
> <span data-ttu-id="d13dd-167">Wenn Sie die Kompilierungsoption [-langversion](compiler-options/langversion-compiler-option.md) wie folgt abfragen, wird etwa Folgendes ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="d13dd-167">Questioning the [-langversion](compiler-options/langversion-compiler-option.md) compile option like this, will print something similar to the following:</span></span>
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
> 8.0 (default)
> latestmajor
> preview
> latest
> ```
