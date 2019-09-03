---
title: Verwaltung der C#-Sprachversion – Leitfaden für C#
description: Hier erfahren Sie, wie die C#-Sprachversion basierend auf Ihrem Projekt bestimmt wird, und Sie lernen die verschiedenen Werte kennen, die Sie manuell an die Sprachversion anpassen können.
ms.date: 07/10/2019
ms.openlocfilehash: fae36f5305e23fbfa1c55c5881e37391670f93ab
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040351"
---
# <a name="c-language-versioning"></a><span data-ttu-id="20a97-103">Verwaltung der C#-Sprachversion</span><span class="sxs-lookup"><span data-stu-id="20a97-103">C# language versioning</span></span>

<span data-ttu-id="20a97-104">Der C#-Compiler bestimmt eine Standardsprachversion, die auf den Zielframeworks Ihres Projekts basiert.</span><span class="sxs-lookup"><span data-stu-id="20a97-104">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="20a97-105">Der Grund dafür ist, dass die Sprache C# Features enthalten kann, die von Typen oder Laufzeitkomponenten abhängig sind, die nicht in allen .NET-Implementierungen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="20a97-105">This is because the C# language may have features that rely on types or runtime components that are not available in every .NET implementation.</span></span> <span data-ttu-id="20a97-106">Damit wird sichergestellt, dass Sie die Sprachversion mit der höchsten Kompatibilität erhalten, ganz gleich, für welches Ziel Sie Ihr Projekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="20a97-106">This also ensures that for whatever target your project is built against, you get the highest compatible language version by default.</span></span>

<span data-ttu-id="20a97-107">Die in diesem Artikel aufgeführten Regeln gelten für den Compiler, der im Lieferumfang von Visual Studio 2019 oder dem .NET Core 3.0 SDK enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="20a97-107">The rules in this article apply to the compiler delivered with Visual Studio 2019, or the .NET Core 3.0 SDK.</span></span> <span data-ttu-id="20a97-108">Die C#-Compiler, die Teil der Visual Studio 2017-Installation oder von früheren .NET Core SDK-Versionen sind, sind standardmäßig auf C# 7.0 ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="20a97-108">The C# compilers that are part of the Visual Studio 2017 installation or earlier .NET Core SDK versions target C# 7.0 by default.</span></span> 

## <a name="defaults"></a><span data-ttu-id="20a97-109">der Arbeitszeittabelle</span><span class="sxs-lookup"><span data-stu-id="20a97-109">Defaults</span></span>

<span data-ttu-id="20a97-110">Der Compiler bestimmt basierend auf den folgenden Regeln eine Standardversion:</span><span class="sxs-lookup"><span data-stu-id="20a97-110">The compiler determines a default based on these rules:</span></span>

|<span data-ttu-id="20a97-111">Zielframework</span><span class="sxs-lookup"><span data-stu-id="20a97-111">Target framework</span></span>|<span data-ttu-id="20a97-112">Version</span><span class="sxs-lookup"><span data-stu-id="20a97-112">version</span></span>|<span data-ttu-id="20a97-113">C#-Sprachversionsstandard</span><span class="sxs-lookup"><span data-stu-id="20a97-113">C# language version default</span></span>|
|----------------|-------|---------------------------|
|<span data-ttu-id="20a97-114">.NET Core</span><span class="sxs-lookup"><span data-stu-id="20a97-114">.NET Core</span></span>|<span data-ttu-id="20a97-115">3.x</span><span class="sxs-lookup"><span data-stu-id="20a97-115">3.x</span></span>|<span data-ttu-id="20a97-116">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="20a97-116">C# 8.0</span></span>|
|<span data-ttu-id="20a97-117">.NET Core</span><span class="sxs-lookup"><span data-stu-id="20a97-117">.NET Core</span></span>|<span data-ttu-id="20a97-118">2.x</span><span class="sxs-lookup"><span data-stu-id="20a97-118">2.x</span></span>|<span data-ttu-id="20a97-119">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="20a97-119">C# 7.3</span></span>|
|<span data-ttu-id="20a97-120">.NET-Standard</span><span class="sxs-lookup"><span data-stu-id="20a97-120">.NET Standard</span></span>|<span data-ttu-id="20a97-121">alle</span><span class="sxs-lookup"><span data-stu-id="20a97-121">all</span></span>|<span data-ttu-id="20a97-122">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="20a97-122">C# 7.3</span></span>|
|<span data-ttu-id="20a97-123">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="20a97-123">.NET Framework</span></span>|<span data-ttu-id="20a97-124">alle</span><span class="sxs-lookup"><span data-stu-id="20a97-124">all</span></span>|<span data-ttu-id="20a97-125">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="20a97-125">C# 7.3</span></span>|

## <a name="default-for-previews"></a><span data-ttu-id="20a97-126">Standard für Vorschauversionen</span><span class="sxs-lookup"><span data-stu-id="20a97-126">Default for previews</span></span>

<span data-ttu-id="20a97-127">Wenn Ihr Projekt auf eine Vorschauframework abzielt, das eine entsprechende Vorschausprachversion besitzt, wird die Vorschausprachversion als Sprachversion verwendet.</span><span class="sxs-lookup"><span data-stu-id="20a97-127">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="20a97-128">Damit wird sichergestellt, dass Sie die neuesten Features verwenden können, die garantiert mit dieser Vorschauversion in jeder Umgebung funktionieren ohne Auswirkungen auf Ihre Projekte, die auf eine freigegebene .NET Core-Version abzielen.</span><span class="sxs-lookup"><span data-stu-id="20a97-128">This ensures that you can use the latest features that are guaranteed to work with that preview in any environment without affecting your projects that target a released .NET Core version.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="20a97-129">Überschreiben eines Standardwerts</span><span class="sxs-lookup"><span data-stu-id="20a97-129">Override a default</span></span>

<span data-ttu-id="20a97-130">Wenn Sie Ihre C#-Version explizit angeben müssen, haben Sie verschiedene Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="20a97-130">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="20a97-131">Manuelles Bearbeiten der [Projektdatei](#edit-the-project-file)</span><span class="sxs-lookup"><span data-stu-id="20a97-131">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="20a97-132">Festlegen der Sprachversion [für mehrere Projekte in einem Unterverzeichnis](#configure-multiple-projects)</span><span class="sxs-lookup"><span data-stu-id="20a97-132">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="20a97-133">Konfigurieren der [Compileroption `-langversion`](compiler-options/langversion-compiler-option.md)</span><span class="sxs-lookup"><span data-stu-id="20a97-133">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md)</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="20a97-134">Bearbeiten der Projektdatei</span><span class="sxs-lookup"><span data-stu-id="20a97-134">Edit the project file</span></span>

<span data-ttu-id="20a97-135">Sie können die Sprachversion in der Projektdatei festlegen.</span><span class="sxs-lookup"><span data-stu-id="20a97-135">You can set the language version in your project file.</span></span> <span data-ttu-id="20a97-136">Wenn Sie beispielsweise expliziten Zugriff auf Previewfunktionen wünschen, fügen Sie ein Element wie folgt hinzu:</span><span class="sxs-lookup"><span data-stu-id="20a97-136">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="20a97-137">Der Wert `preview` verwendet die neueste verfügbare Vorschauversion der Sprache C#, die Ihr Compiler unterstützt.</span><span class="sxs-lookup"><span data-stu-id="20a97-137">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="20a97-138">Konfigurieren mehrerer Projekte</span><span class="sxs-lookup"><span data-stu-id="20a97-138">Configure multiple projects</span></span>

<span data-ttu-id="20a97-139">Sie können eine **Directory.Build.props**-Datei erstellen, die das Element `<LangVersion>` enthält, um mehrere Verzeichnisse zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="20a97-139">You can create a **Directory.Build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="20a97-140">In der Regel führen Sie dies im Projektmappenverzeichnis durch.</span><span class="sxs-lookup"><span data-stu-id="20a97-140">You typically do that in your solution directory.</span></span> <span data-ttu-id="20a97-141">Fügen Sie Folgendes in eine **Directory.Build.props**-Datei in Ihrem Projektmappenverzeichnis ein:</span><span class="sxs-lookup"><span data-stu-id="20a97-141">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="20a97-142">Nun verwenden alle Unterverzeichnisse des Verzeichnisses, das diese Datei enthält, die C#-Vorschauversion.</span><span class="sxs-lookup"><span data-stu-id="20a97-142">Now, builds in every subdirectory of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="20a97-143">Weitere Informationen finden Sie im Artikel zum [Anpassen Ihres Builds](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="20a97-143">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="20a97-144">Referenz zur C#-Sprachversion</span><span class="sxs-lookup"><span data-stu-id="20a97-144">C# language version reference</span></span>

<span data-ttu-id="20a97-145">In der folgenden Tabelle sind alle aktuellen C#-Sprachversionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="20a97-145">The following table shows all current C# language versions.</span></span> <span data-ttu-id="20a97-146">Wenn Ihr Compiler älter ist, versteht er möglicherweise nicht alle Werte.</span><span class="sxs-lookup"><span data-stu-id="20a97-146">Your compiler may not necessarily understand every value if it is older.</span></span> <span data-ttu-id="20a97-147">Sie haben Zugriff auf alle aufgeführten Elemente, wenn Sie .NET Core 3.0 installieren.</span><span class="sxs-lookup"><span data-stu-id="20a97-147">If you install .NET Core 3.0, then you will have access to everything listed.</span></span>

|<span data-ttu-id="20a97-148">Wert</span><span class="sxs-lookup"><span data-stu-id="20a97-148">Value</span></span>|<span data-ttu-id="20a97-149">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="20a97-149">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="20a97-150">preview</span><span class="sxs-lookup"><span data-stu-id="20a97-150">preview</span></span>|<span data-ttu-id="20a97-151">Der Compiler akzeptiert jede gültige Sprachsyntax der letzten Vorschauversion.</span><span class="sxs-lookup"><span data-stu-id="20a97-151">The compiler accepts all valid language syntax from the latest preview version.</span></span>|
|<span data-ttu-id="20a97-152">latest</span><span class="sxs-lookup"><span data-stu-id="20a97-152">latest</span></span>|<span data-ttu-id="20a97-153">Der Compiler akzeptiert die Syntax der neuesten veröffentlichte Version des Compilers (einschließlich Nebenversionen).</span><span class="sxs-lookup"><span data-stu-id="20a97-153">The compiler accepts syntax from the latest released version of the compiler (including minor version).</span></span>|
|<span data-ttu-id="20a97-154">latestMajor</span><span class="sxs-lookup"><span data-stu-id="20a97-154">latestMajor</span></span>|<span data-ttu-id="20a97-155">Der Compiler akzeptiert die Syntax der neuesten veröffentlichte Hauptversion des Compilers.</span><span class="sxs-lookup"><span data-stu-id="20a97-155">The compiler accepts syntax from the latest released major version of the compiler.</span></span>|
|<span data-ttu-id="20a97-156">8.0</span><span class="sxs-lookup"><span data-stu-id="20a97-156">8.0</span></span>|<span data-ttu-id="20a97-157">Der Compiler akzeptiert nur Syntax, die in C# 8.0 oder niedriger enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="20a97-157">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="20a97-158">7.3</span><span class="sxs-lookup"><span data-stu-id="20a97-158">7.3</span></span>|<span data-ttu-id="20a97-159">Der Compiler akzeptiert nur Syntax, die in C# 7.3 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="20a97-159">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="20a97-160">7.2</span><span class="sxs-lookup"><span data-stu-id="20a97-160">7.2</span></span>|<span data-ttu-id="20a97-161">Der Compiler akzeptiert nur Syntax, die in C# 7.2 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="20a97-161">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="20a97-162">7.1</span><span class="sxs-lookup"><span data-stu-id="20a97-162">7.1</span></span>|<span data-ttu-id="20a97-163">Der Compiler akzeptiert nur Syntax, die in C# 7.1 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="20a97-163">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="20a97-164">7</span><span class="sxs-lookup"><span data-stu-id="20a97-164">7</span></span>|<span data-ttu-id="20a97-165">Der Compiler akzeptiert nur Syntax, die in C# 7.0 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="20a97-165">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="20a97-166">6</span><span class="sxs-lookup"><span data-stu-id="20a97-166">6</span></span>|<span data-ttu-id="20a97-167">Der Compiler akzeptiert nur Syntax, die in C# 6.0 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="20a97-167">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="20a97-168">5</span><span class="sxs-lookup"><span data-stu-id="20a97-168">5</span></span>|<span data-ttu-id="20a97-169">Der Compiler akzeptiert nur Syntax, die in C# 5.0 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="20a97-169">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="20a97-170">4</span><span class="sxs-lookup"><span data-stu-id="20a97-170">4</span></span>|<span data-ttu-id="20a97-171">Der Compiler akzeptiert nur Syntax, die in C# 4.0 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="20a97-171">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="20a97-172">3</span><span class="sxs-lookup"><span data-stu-id="20a97-172">3</span></span>|<span data-ttu-id="20a97-173">Der Compiler akzeptiert nur Syntax, die in C# 3.0 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="20a97-173">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="20a97-174">ISO-2</span><span class="sxs-lookup"><span data-stu-id="20a97-174">ISO-2</span></span>|<span data-ttu-id="20a97-175">Der Compiler akzeptiert nur Syntax, die in ISO/IEC 23270:2006 C# (2.0) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="20a97-175">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0)</span></span> |
|<span data-ttu-id="20a97-176">ISO-1</span><span class="sxs-lookup"><span data-stu-id="20a97-176">ISO-1</span></span>|<span data-ttu-id="20a97-177">Der Compiler akzeptiert nur Syntax, die in ISO/IEC 23270:2003 C# (1.0/1.2) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="20a97-177">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2)</span></span> |
