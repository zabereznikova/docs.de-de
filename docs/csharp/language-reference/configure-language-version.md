---
title: 'Leitfaden für C#: Auswählen der C#-Sprachversion'
description: Konfigurieren des Compilers zum Ausführen der Syntaxüberprüfung mithilfe einer spezifischen Compilerversion
ms.date: 05/24/2018
ms.openlocfilehash: 9b91e62168ced0f373e1a55def8b279dc64833d8
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207982"
---
# <a name="select-the-c-language-version"></a><span data-ttu-id="54034-103">Auswählen der C#-Sprachversion</span><span class="sxs-lookup"><span data-stu-id="54034-103">Select the C# language version</span></span>

<span data-ttu-id="54034-104">Der C#-Compiler legt standardmäßig die aktuellste freigegebene Hauptversion der Sprache fest.</span><span class="sxs-lookup"><span data-stu-id="54034-104">The C# compiler defaults to the latest major version of the language that has been released.</span></span> <span data-ttu-id="54034-105">Sie können jedes Projekt mit einem neuen Punktrelease der Sprache kompilieren.</span><span class="sxs-lookup"><span data-stu-id="54034-105">You may choose to compile any project using a new point release of the language.</span></span> <span data-ttu-id="54034-106">Mit einer neueren Version der Sprache können Sie die neuesten Sprachfeatures in Ihrem Projekt verwenden.</span><span class="sxs-lookup"><span data-stu-id="54034-106">Choosing a newer version of the language enables your project to make use of the latest language features.</span></span> <span data-ttu-id="54034-107">In anderen Szenarios müssen Sie möglicherweise überprüfen, dass ein Projekt ordnungsgemäß kompiliert wird, wenn Sie eine ältere Version der Sprache verwenden.</span><span class="sxs-lookup"><span data-stu-id="54034-107">In other scenarios, you may need to validate that a project compiles cleanly when using an older version of the language.</span></span>

<span data-ttu-id="54034-108">Diese Funktion entkoppelt das Installieren neuer Versionen vom SDK und den Tools in Ihrer Entwicklungsumgebung von der Entscheidung, neue Sprachfeatures in einem Projekt zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="54034-108">This capability decouples the decision to install new versions of the SDK and tools in your development environment from the decision to incorporate new language features in a project.</span></span> <span data-ttu-id="54034-109">Sie können das neueste SDK und die neuesten Tools auf Ihrem Buildcomputer installieren.</span><span class="sxs-lookup"><span data-stu-id="54034-109">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="54034-110">Jedes Projekt kann dazu konfiguriert werden, eine spezifische Version der Sprache für das Build zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="54034-110">Each project can be configured to use a specific version of the language for its build.</span></span>

<span data-ttu-id="54034-111">Es gibt verschiedene Möglichkeiten, die Sprachversion einzurichten:</span><span class="sxs-lookup"><span data-stu-id="54034-111">There are several ways to set the language version:</span></span>

- <span data-ttu-id="54034-112">Verwenden einer [Visual Studio-Schnellaktion](#visual-studio-quick-action)</span><span class="sxs-lookup"><span data-stu-id="54034-112">Rely on a [Visual Studio quick action](#visual-studio-quick-action).</span></span>
- <span data-ttu-id="54034-113">Festlegen der Sprachversion in der [Visual Studio-Benutzeroberfläche](#set-the-language-version-in-visual-studio)</span><span class="sxs-lookup"><span data-stu-id="54034-113">Set the language version in the [Visual Studio UI](#set-the-language-version-in-visual-studio).</span></span>
- <span data-ttu-id="54034-114">Manuelles Bearbeiten der [**CSPROJ**-Datei](#edit-the-csproj-file)</span><span class="sxs-lookup"><span data-stu-id="54034-114">Manually edit your [**.csproj** file](#edit-the-csproj-file).</span></span>
- <span data-ttu-id="54034-115">Festlegen der Sprachversion [für mehrere Projekte in einem Unterverzeichnis](#configure-multiple-projects)</span><span class="sxs-lookup"><span data-stu-id="54034-115">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="54034-116">Konfigurieren der [Compileroption `-langversion`](#set-the-langversion-compiler-option)</span><span class="sxs-lookup"><span data-stu-id="54034-116">Configure the [`-langversion` compiler option](#set-the-langversion-compiler-option).</span></span>

## <a name="visual-studio-quick-action"></a><span data-ttu-id="54034-117">Visual Studio-Schnellaktion</span><span class="sxs-lookup"><span data-stu-id="54034-117">Visual Studio quick action</span></span>

<span data-ttu-id="54034-118">Visual Studio unterstützt Sie beim Auswählen der erforderlichen Sprachversion.</span><span class="sxs-lookup"><span data-stu-id="54034-118">Visual Studio helps you determine the language version you need.</span></span> <span data-ttu-id="54034-119">Wenn Sie ein Sprachfeature verwenden, das in der derzeit konfigurierten Version nicht verfügbar ist, zeigt Visual Studio eine mögliche Lösung zum Aktualisieren der Sprachversion für das Projekt an.</span><span class="sxs-lookup"><span data-stu-id="54034-119">If you use a language feature that is not available for the currently configured version, Visual Studio shows a potential fix to update the language version for the project.</span></span>

## <a name="set-the-language-version-in-visual-studio"></a><span data-ttu-id="54034-120">Festlegen der Sprachversion in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="54034-120">Set the language version in Visual Studio</span></span>

<span data-ttu-id="54034-121">Sie können die Version in Visual Studio festlegen.</span><span class="sxs-lookup"><span data-stu-id="54034-121">You can set the version in Visual Studio.</span></span> <span data-ttu-id="54034-122">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="54034-122">Right-click on the project node in Solution Explorer and select **Properties**.</span></span> <span data-ttu-id="54034-123">Wählen Sie die Registerkarte **Build** aus, und klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="54034-123">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="54034-124">Wählen Sie in der Dropdownliste die Version aus.</span><span class="sxs-lookup"><span data-stu-id="54034-124">In the dropdown, select the version.</span></span> <span data-ttu-id="54034-125">Die folgende Abbildung zeigt die „aktuellste“ Einstellung:</span><span class="sxs-lookup"><span data-stu-id="54034-125">The following image shows the "latest" setting:</span></span>

![Screenshot der erweiterten Buildeinstellungen, in denen Sie die Sprachversion festlegen können](./media/configure-language-version/advanced-build-settings.png)

> [!NOTE]
> <span data-ttu-id="54034-127">Wenn Sie die Visual Studio-IDE verwenden, um Ihre CSPROJ-Dateien zu aktualisieren, werden separate Knoten für jede Buildkonfiguration von der IDE erstellt.</span><span class="sxs-lookup"><span data-stu-id="54034-127">If you use the Visual Studio IDE to update your csproj files, the IDE creates separate nodes for each build configuration.</span></span> <span data-ttu-id="54034-128">In der Regel legen Sie den gleichen Wert in allen Buildkonfigurationen fest, dennoch müssen Sie ihn für jede Buildkonfiguration explizit festlegen oder beim Ändern dieser Einstellung „Alle Konfigurationen“ auswählen.</span><span class="sxs-lookup"><span data-stu-id="54034-128">You'll typically set the value the same in all build configurations, but you need to set it explicitly for each build configuration, or select "All Configurations" when you modify this setting.</span></span> <span data-ttu-id="54034-129">Folgendes wird dann in Ihrer CSPROJ-Datei angezeigt:</span><span class="sxs-lookup"><span data-stu-id="54034-129">You'll see the following in your csproj file:</span></span>
>
>```xml
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
>  <LangVersion>latest</LangVersion>
></PropertyGroup>
>
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
>  <LangVersion>latest</LangVersion>
> </PropertyGroup>
> ```
>

## <a name="edit-the-csproj-file"></a><span data-ttu-id="54034-130">Bearbeiten der CSPROJ-Datei</span><span class="sxs-lookup"><span data-stu-id="54034-130">Edit the csproj file</span></span>

<span data-ttu-id="54034-131">Sie können die Sprachversion in der **CSPROJ**-Datei festlegen.</span><span class="sxs-lookup"><span data-stu-id="54034-131">You can set the language version in your **.csproj** file.</span></span> <span data-ttu-id="54034-132">Fügen Sie ein Element wie das Folgende ein:</span><span class="sxs-lookup"><span data-stu-id="54034-132">Add an element like the following:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="54034-133">Der Wert `latest` verwendet die neueste Nebenversion der C#-Sprache.</span><span class="sxs-lookup"><span data-stu-id="54034-133">The value `latest` uses the latest minor version of the C# language.</span></span> <span data-ttu-id="54034-134">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="54034-134">Valid values are:</span></span>

|<span data-ttu-id="54034-135">Wert</span><span class="sxs-lookup"><span data-stu-id="54034-135">Value</span></span>|<span data-ttu-id="54034-136">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="54034-136">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="54034-137">default</span><span class="sxs-lookup"><span data-stu-id="54034-137">default</span></span>|<span data-ttu-id="54034-138">Der Compiler akzeptiert jede gültige Sprachsyntax der letzten Hauptversion, die unterstützen werden kann.</span><span class="sxs-lookup"><span data-stu-id="54034-138">The compiler accepts all valid language syntax from the latest major version that it can support.</span></span>|
|<span data-ttu-id="54034-139">ISO-1</span><span class="sxs-lookup"><span data-stu-id="54034-139">ISO-1</span></span>|<span data-ttu-id="54034-140">Der Compiler akzeptiert nur Syntax, die in ISO/IEC 23270:2003 C# (1.0/1.2) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="54034-140">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2)</span></span> |
|<span data-ttu-id="54034-141">ISO-2</span><span class="sxs-lookup"><span data-stu-id="54034-141">ISO-2</span></span>|<span data-ttu-id="54034-142">Der Compiler akzeptiert nur Syntax, die in ISO/IEC 23270:2006 C# (2.0) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="54034-142">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0)</span></span> |
|<span data-ttu-id="54034-143">3</span><span class="sxs-lookup"><span data-stu-id="54034-143">3</span></span>|<span data-ttu-id="54034-144">Der Compiler akzeptiert nur Syntax, die in C# 3.0 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="54034-144">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="54034-145">4</span><span class="sxs-lookup"><span data-stu-id="54034-145">4</span></span>|<span data-ttu-id="54034-146">Der Compiler akzeptiert nur Syntax, die in C# 4.0 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="54034-146">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="54034-147">5</span><span class="sxs-lookup"><span data-stu-id="54034-147">5</span></span>|<span data-ttu-id="54034-148">Der Compiler akzeptiert nur Syntax, die in C# 5.0 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="54034-148">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="54034-149">6</span><span class="sxs-lookup"><span data-stu-id="54034-149">6</span></span>|<span data-ttu-id="54034-150">Der Compiler akzeptiert nur Syntax, die in C# 6.0 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="54034-150">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="54034-151">7</span><span class="sxs-lookup"><span data-stu-id="54034-151">7</span></span>|<span data-ttu-id="54034-152">Der Compiler akzeptiert nur Syntax, die in C# 7.0 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="54034-152">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="54034-153">7.1</span><span class="sxs-lookup"><span data-stu-id="54034-153">7.1</span></span>|<span data-ttu-id="54034-154">Der Compiler akzeptiert nur Syntax, die in C# 7.1 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="54034-154">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="54034-155">7.2</span><span class="sxs-lookup"><span data-stu-id="54034-155">7.2</span></span>|<span data-ttu-id="54034-156">Der Compiler akzeptiert nur Syntax, die in C# 7.2 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="54034-156">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="54034-157">7.3</span><span class="sxs-lookup"><span data-stu-id="54034-157">7.3</span></span>|<span data-ttu-id="54034-158">Der Compiler akzeptiert nur Syntax, die in C# 7.3 oder früher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="54034-158">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="54034-159">latest</span><span class="sxs-lookup"><span data-stu-id="54034-159">latest</span></span>|<span data-ttu-id="54034-160">Der Compiler akzeptiert alle gültige Sprachsyntax, die es unterstützen kann.</span><span class="sxs-lookup"><span data-stu-id="54034-160">The compiler accepts all valid language syntax that it can support.</span></span>|

<span data-ttu-id="54034-161">Die Auflösung der speziellen Zeichenfolgen `default` und `latest` sind die Haupt- (C# 7.0) und Nebensprachversionen (C# 7.3), die jeweils auf dem Buildcomputer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="54034-161">The special strings `default` and `latest` resolve to the latest major (C# 7.0) and minor (C# 7.3) language versions installed on the build machine, respectively.</span></span>

## <a name="configure-multiple-projects"></a><span data-ttu-id="54034-162">Konfigurieren mehrerer Projekte</span><span class="sxs-lookup"><span data-stu-id="54034-162">Configure multiple projects</span></span>

<span data-ttu-id="54034-163">Sie können eine **Directory.build.props**-Datei erstellen, die das Element `<LangVersion>` enthält, um mehrere Verzeichnisse zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="54034-163">You can create a **Directory.build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="54034-164">In der Regel führen Sie dies im Projektmappenverzeichnis durch.</span><span class="sxs-lookup"><span data-stu-id="54034-164">You typically do that in your solution directory.</span></span> <span data-ttu-id="54034-165">Fügen Sie Folgendes in eine **Directory.build.props**-Datei in Ihrem Projektmappenverzeichnis ein:</span><span class="sxs-lookup"><span data-stu-id="54034-165">Add the following to a **Directory.build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>7.3</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="54034-166">Nun verwenden alle Unterverzeichnisse des Verzeichnisses, das diese Datei enthält, die Syntax der Version 7.3 von C#.</span><span class="sxs-lookup"><span data-stu-id="54034-166">Now, builds in every subdirectory of the directory containing that file will use C# version 7.3 syntax.</span></span> <span data-ttu-id="54034-167">Weitere Informationen finden Sie im Artikel zum [Anpassen Ihres Builds](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="54034-167">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="set-the-langversion-compiler-option"></a><span data-ttu-id="54034-168">Festlegen der Compileroption „langversion“</span><span class="sxs-lookup"><span data-stu-id="54034-168">Set the langversion compiler option</span></span>

<span data-ttu-id="54034-169">Sie können die Befehlszeilenoption `-langversion` verwenden.</span><span class="sxs-lookup"><span data-stu-id="54034-169">You can use the `-langversion` command-line option.</span></span> <span data-ttu-id="54034-170">Weitere Informationen finden Sie im Artikel zur Compileroption [-langversion](../language-reference/compiler-options/langversion-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="54034-170">For more information, see the article on the [-langversion](../language-reference/compiler-options/langversion-compiler-option.md) compiler option.</span></span> <span data-ttu-id="54034-171">Sie können eine Liste der gültigen Werte anzeigen, indem Sie `csc -langversion:?` eingeben.</span><span class="sxs-lookup"><span data-stu-id="54034-171">You can see a list of the valid values by typing  `csc -langversion:?`.</span></span>
