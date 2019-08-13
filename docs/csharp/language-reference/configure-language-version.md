---
title: Verwaltung der C#-Sprachversion – Leitfaden für C#
description: Hier erfahren Sie, wie die C#-Sprachversion basierend auf Ihrem Projekt bestimmt wird, und Sie lernen die verschiedenen Werte kennen, die Sie manuell an die Sprachversion anpassen können.
ms.date: 07/10/2019
ms.openlocfilehash: 744cec0aac21f743648cccbdc93cf2977c32d644
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796534"
---
# <a name="c-language-versioning"></a><span data-ttu-id="469ae-103">Verwaltung der C#-Sprachversion</span><span class="sxs-lookup"><span data-stu-id="469ae-103">C# language versioning</span></span>

<span data-ttu-id="469ae-104">Der C#-Compiler bestimmt eine Standardsprachversion, basierend auf dem oder den Zielframeworks Ihres Projekts.</span><span class="sxs-lookup"><span data-stu-id="469ae-104">The C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="469ae-105">Der Grund dafür ist, dass die Sprache C# Features enthalten kann, die von Typen oder Laufzeitkomponenten abhängig sind, die nicht in allen .NET-Implementierungen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="469ae-105">This is because the C# language may have features that rely on types or runtime components that are not available in every .NET implementation.</span></span> <span data-ttu-id="469ae-106">Damit wird sichergestellt, dass Sie die Sprachversion mit der höchsten Kompatibilität erhalten, ganz gleich, für welches Ziel Sie Ihr Projekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="469ae-106">This also ensures that for whatever target your project is built against, you get the highest compatible language version by default.</span></span>

## <a name="defaults"></a><span data-ttu-id="469ae-107">der Arbeitszeittabelle</span><span class="sxs-lookup"><span data-stu-id="469ae-107">Defaults</span></span>

<span data-ttu-id="469ae-108">Der Compiler bestimmt basierend auf den folgenden Regeln eine Standardversion:</span><span class="sxs-lookup"><span data-stu-id="469ae-108">The compiler determines a default based on these rules:</span></span>

|<span data-ttu-id="469ae-109">Zielframework</span><span class="sxs-lookup"><span data-stu-id="469ae-109">Target framework</span></span>|<span data-ttu-id="469ae-110">Version</span><span class="sxs-lookup"><span data-stu-id="469ae-110">version</span></span>|<span data-ttu-id="469ae-111">C#-Sprachversionsstandard</span><span class="sxs-lookup"><span data-stu-id="469ae-111">C# language version default</span></span>|
|----------------|-------|---------------------------|
|<span data-ttu-id="469ae-112">.NET Core</span><span class="sxs-lookup"><span data-stu-id="469ae-112">.NET Core</span></span>|<span data-ttu-id="469ae-113">3.x</span><span class="sxs-lookup"><span data-stu-id="469ae-113">3.x</span></span>|<span data-ttu-id="469ae-114">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="469ae-114">C# 8.0</span></span>|
|<span data-ttu-id="469ae-115">.NET Core</span><span class="sxs-lookup"><span data-stu-id="469ae-115">.NET Core</span></span>|<span data-ttu-id="469ae-116">2.x</span><span class="sxs-lookup"><span data-stu-id="469ae-116">2.x</span></span>|<span data-ttu-id="469ae-117">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="469ae-117">C# 7.3</span></span>|
|<span data-ttu-id="469ae-118">.NET-Standard</span><span class="sxs-lookup"><span data-stu-id="469ae-118">.NET Standard</span></span>|<span data-ttu-id="469ae-119">alle</span><span class="sxs-lookup"><span data-stu-id="469ae-119">all</span></span>|<span data-ttu-id="469ae-120">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="469ae-120">C# 7.3</span></span>|
|<span data-ttu-id="469ae-121">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="469ae-121">.NET Framework</span></span>|<span data-ttu-id="469ae-122">alle</span><span class="sxs-lookup"><span data-stu-id="469ae-122">all</span></span>|<span data-ttu-id="469ae-123">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="469ae-123">C# 7.3</span></span>|

## <a name="default-for-previews"></a><span data-ttu-id="469ae-124">Standard für Vorschauversionen</span><span class="sxs-lookup"><span data-stu-id="469ae-124">Default for previews</span></span>

<span data-ttu-id="469ae-125">Wenn Ihr Projekt auf eine Vorschauframework abzielt, das eine entsprechende Vorschausprachversion besitzt, wird die Vorschausprachversion als Sprachversion verwendet.</span><span class="sxs-lookup"><span data-stu-id="469ae-125">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="469ae-126">Damit wird sichergestellt, dass Sie die neuesten Features verwenden können, die garantiert mit dieser Vorschauversion in jeder Umgebung funktionieren ohne Auswirkungen auf Ihre Projekte, die auf eine freigegebene .NET Core-Version abzielen.</span><span class="sxs-lookup"><span data-stu-id="469ae-126">This ensures that you can use the latest features that are guaranteed to work with that preview in any environment without affecting your projects that target a released .NET Core version.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="469ae-127">Überschreiben eines Standardwerts</span><span class="sxs-lookup"><span data-stu-id="469ae-127">Override a default</span></span>

<span data-ttu-id="469ae-128">Wenn Sie Ihre C#-Version explizit angeben müssen, haben Sie verschiedene Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="469ae-128">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="469ae-129">Manuelles Bearbeiten der [Projektdatei](#edit-the-project-file)</span><span class="sxs-lookup"><span data-stu-id="469ae-129">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="469ae-130">Festlegen der Sprachversion [für mehrere Projekte in einem Unterverzeichnis](#configure-multiple-projects)</span><span class="sxs-lookup"><span data-stu-id="469ae-130">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="469ae-131">Konfigurieren der [Compileroption `-langversion`](compiler-options/langversion-compiler-option.md)</span><span class="sxs-lookup"><span data-stu-id="469ae-131">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md)</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="469ae-132">Bearbeiten der Projektdatei</span><span class="sxs-lookup"><span data-stu-id="469ae-132">Edit the project file</span></span>

<span data-ttu-id="469ae-133">Sie können die Sprachversion in der Projektdatei festlegen.</span><span class="sxs-lookup"><span data-stu-id="469ae-133">You can set the language version in your project file.</span></span> <span data-ttu-id="469ae-134">Wenn Sie beispielsweise expliziten Zugriff auf Previewfunktionen wünschen, fügen Sie ein Element wie folgt hinzu:</span><span class="sxs-lookup"><span data-stu-id="469ae-134">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="469ae-135">Der Wert `preview` verwendet die neueste verfügbare Vorschauversion der Sprache C#, die Ihr Compiler unterstützt.</span><span class="sxs-lookup"><span data-stu-id="469ae-135">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="469ae-136">Konfigurieren mehrerer Projekte</span><span class="sxs-lookup"><span data-stu-id="469ae-136">Configure multiple projects</span></span>

<span data-ttu-id="469ae-137">Sie können eine **Directory.Build.props**-Datei erstellen, die das Element `<LangVersion>` enthält, um mehrere Verzeichnisse zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="469ae-137">You can create a **Directory.Build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="469ae-138">In der Regel führen Sie dies im Projektmappenverzeichnis durch.</span><span class="sxs-lookup"><span data-stu-id="469ae-138">You typically do that in your solution directory.</span></span> <span data-ttu-id="469ae-139">Fügen Sie Folgendes in eine **Directory.Build.props**-Datei in Ihrem Projektmappenverzeichnis ein:</span><span class="sxs-lookup"><span data-stu-id="469ae-139">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="469ae-140">Nun verwenden alle Unterverzeichnisse des Verzeichnisses, das diese Datei enthält, die C#-Vorschauversion.</span><span class="sxs-lookup"><span data-stu-id="469ae-140">Now, builds in every subdirectory of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="469ae-141">Weitere Informationen finden Sie im Artikel zum [Anpassen Ihres Builds](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="469ae-141">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="469ae-142">Referenz zur C#-Sprachversion</span><span class="sxs-lookup"><span data-stu-id="469ae-142">C# language version reference</span></span>

<span data-ttu-id="469ae-143">In der folgenden Tabelle sind alle aktuellen C#-Sprachversionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="469ae-143">The following table shows all current C# language versions.</span></span> <span data-ttu-id="469ae-144">Wenn Ihr Compiler älter ist, versteht er möglicherweise nicht alle Werte.</span><span class="sxs-lookup"><span data-stu-id="469ae-144">Your compiler may not necessarily understand every value if it is older.</span></span> <span data-ttu-id="469ae-145">Sie haben Zugriff auf alle aufgeführten Elemente, wenn Sie .NET Core 3.0 installieren.</span><span class="sxs-lookup"><span data-stu-id="469ae-145">If you install .NET Core 3.0, then you will have access to everything listed.</span></span>

|<span data-ttu-id="469ae-146">Wert</span><span class="sxs-lookup"><span data-stu-id="469ae-146">Value</span></span>|<span data-ttu-id="469ae-147">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="469ae-147">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="469ae-148">preview</span><span class="sxs-lookup"><span data-stu-id="469ae-148">preview</span></span>|<span data-ttu-id="469ae-149">Der Compiler akzeptiert jede gültige Sprachsyntax der letzten Vorschauversion.</span><span class="sxs-lookup"><span data-stu-id="469ae-149">The compiler accepts all valid language syntax from the latest preview version.</span></span>|
|<span data-ttu-id="469ae-150">latest</span><span class="sxs-lookup"><span data-stu-id="469ae-150">latest</span></span>|<span data-ttu-id="469ae-151">Der Compiler akzeptiert die Syntax der neuesten veröffentlichte Version des Compilers (einschließlich Nebenversionen).</span><span class="sxs-lookup"><span data-stu-id="469ae-151">The compiler accepts syntax from the latest released version of the compiler (including minor version).</span></span>|
|<span data-ttu-id="469ae-152">latestMajor</span><span class="sxs-lookup"><span data-stu-id="469ae-152">latestMajor</span></span>|<span data-ttu-id="469ae-153">Der Compiler akzeptiert die Syntax der neuesten veröffentlichte Hauptversion des Compilers.</span><span class="sxs-lookup"><span data-stu-id="469ae-153">The compiler accepts syntax from the latest released major version of the compiler.</span></span>|
|<span data-ttu-id="469ae-154">8.0</span><span class="sxs-lookup"><span data-stu-id="469ae-154">8.0</span></span>|<span data-ttu-id="469ae-155">Der Compiler akzeptiert nur Syntax, die in C# 8.0 oder niedriger enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="469ae-155">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="469ae-156">7.3</span><span class="sxs-lookup"><span data-stu-id="469ae-156">7.3</span></span>|<span data-ttu-id="469ae-157">Der Compiler akzeptiert nur Syntax, die in C# 7.3 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="469ae-157">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="469ae-158">7.2</span><span class="sxs-lookup"><span data-stu-id="469ae-158">7.2</span></span>|<span data-ttu-id="469ae-159">Der Compiler akzeptiert nur Syntax, die in C# 7.2 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="469ae-159">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="469ae-160">7.1</span><span class="sxs-lookup"><span data-stu-id="469ae-160">7.1</span></span>|<span data-ttu-id="469ae-161">Der Compiler akzeptiert nur Syntax, die in C# 7.1 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="469ae-161">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="469ae-162">7</span><span class="sxs-lookup"><span data-stu-id="469ae-162">7</span></span>|<span data-ttu-id="469ae-163">Der Compiler akzeptiert nur Syntax, die in C# 7.0 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="469ae-163">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="469ae-164">6</span><span class="sxs-lookup"><span data-stu-id="469ae-164">6</span></span>|<span data-ttu-id="469ae-165">Der Compiler akzeptiert nur Syntax, die in C# 6.0 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="469ae-165">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="469ae-166">5</span><span class="sxs-lookup"><span data-stu-id="469ae-166">5</span></span>|<span data-ttu-id="469ae-167">Der Compiler akzeptiert nur Syntax, die in C# 5.0 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="469ae-167">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="469ae-168">4</span><span class="sxs-lookup"><span data-stu-id="469ae-168">4</span></span>|<span data-ttu-id="469ae-169">Der Compiler akzeptiert nur Syntax, die in C# 4.0 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="469ae-169">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="469ae-170">3</span><span class="sxs-lookup"><span data-stu-id="469ae-170">3</span></span>|<span data-ttu-id="469ae-171">Der Compiler akzeptiert nur Syntax, die in C# 3.0 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="469ae-171">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="469ae-172">ISO-2</span><span class="sxs-lookup"><span data-stu-id="469ae-172">ISO-2</span></span>|<span data-ttu-id="469ae-173">Der Compiler akzeptiert nur Syntax, die in ISO/IEC 23270:2006 C# (2.0) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="469ae-173">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0)</span></span> |
|<span data-ttu-id="469ae-174">ISO-1</span><span class="sxs-lookup"><span data-stu-id="469ae-174">ISO-1</span></span>|<span data-ttu-id="469ae-175">Der Compiler akzeptiert nur Syntax, die in ISO/IEC 23270:2003 C# (1.0/1.2) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="469ae-175">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2)</span></span> |
