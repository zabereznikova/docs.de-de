---
title: Konfigurationsdateien für Code Analyse Regeln
description: Erfahren Sie mehr über die verschiedenen Konfigurationsdateien zum Konfigurieren von Code Analyse Regeln.
ms.date: 09/24/2020
ms.topic: conceptual
no-loc:
- EditorConfig
ms.openlocfilehash: cf9b8f4033e6774684b2b7e3b788ef3c157d95df
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96592105"
---
# <a name="configuration-files-for-code-analysis-rules"></a><span data-ttu-id="4a0cb-103">Konfigurationsdateien für Code Analyse Regeln</span><span class="sxs-lookup"><span data-stu-id="4a0cb-103">Configuration files for code analysis rules</span></span>

<span data-ttu-id="4a0cb-104">Code Analyse Regeln verfügen über verschiedene [Konfigurationsoptionen](configuration-options.md).</span><span class="sxs-lookup"><span data-stu-id="4a0cb-104">Code analysis rules have various [configuration options](configuration-options.md).</span></span> <span data-ttu-id="4a0cb-105">Diese Optionen werden als Schlüssel-Wert-Paare in einer der folgenden Analyse Konfigurationsdateien angegeben:</span><span class="sxs-lookup"><span data-stu-id="4a0cb-105">You specify these options as key-value pairs in one of the following analyzer configuration files:</span></span>

- <span data-ttu-id="4a0cb-106">[EditorConfig](#editorconfig) file: dateibasierte oder Ordner basierte Konfigurationsoptionen.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-106">[EditorConfig](#editorconfig) file: File-based or folder-based configuration options.</span></span>
- <span data-ttu-id="4a0cb-107">[Globale analyzerconfig](#global-analyzerconfig) -Datei: Konfigurationsoptionen auf Projektebene.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-107">[Global AnalyzerConfig](#global-analyzerconfig) file: Project-level configuration options.</span></span>

## EditorConfig

<span data-ttu-id="4a0cb-108">[EditorConfig](/visualstudio/ide/create-portable-custom-editor-options) Dateien werden verwendet, um **Optionen bereitzustellen, die auf bestimmte Quelldateien oder Ordner angewendet** werden.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-108">[EditorConfig](/visualstudio/ide/create-portable-custom-editor-options) files are used to provide **options that apply to specific source files or folders**.</span></span> <span data-ttu-id="4a0cb-109">Optionen werden Unterabschnitts Kopfzeilen abgelegt, um die entsprechenden Dateien und Ordner zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-109">Options are placed under section headers to identify the applicable files and folders.</span></span> <span data-ttu-id="4a0cb-110">Fügen Sie einen Eintrag für jede Regel hinzu, die Sie konfigurieren möchten, und platzieren Sie ihn unter dem entsprechenden Datei Erweiterungs Abschnitt, z `[*.cs]` . b..</span><span class="sxs-lookup"><span data-stu-id="4a0cb-110">Add an entry for each rule you want to configure, and place it under the corresponding file extension section, for example, `[*.cs]`.</span></span>

```ini
[*.cs]
<option_name> = <option_value>
```

<span data-ttu-id="4a0cb-111">Im obigen Beispiel `[*.cs]` ist ein editorconfig-Abschnitts Header, mit dem alle c#-Dateien mit `.cs` der Dateierweiterung innerhalb des aktuellen Ordners ausgewählt werden, einschließlich der Unterordner.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-111">In the above example, `[*.cs]` is an editorconfig section header to select all C# files with `.cs` file extension within the current folder, including subfolders.</span></span> <span data-ttu-id="4a0cb-112">Der nachfolgende Eintrag `<option_name> = <option_value>` ist eine Analyzer-Option, die auf alle c#-Dateien angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-112">The subsequent entry, `<option_name> = <option_value>`, is an analyzer option that will be applied to all the C# files.</span></span>

<span data-ttu-id="4a0cb-113">Sie können EditorConfig Datei Konventionen auf einen Ordner, ein Projekt oder ein gesamtes Repository anwenden, indem Sie die Datei im entsprechenden Verzeichnis platzieren.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-113">You can apply EditorConfig file conventions to a folder, a project, or an entire repo by placing the file in the corresponding directory.</span></span> <span data-ttu-id="4a0cb-114">Diese Optionen werden bei der Ausführung der Analyse während der Buildzeit und beim Bearbeiten von Code in Visual Studio angewendet.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-114">These options are applied when executing the analysis at build time and while you edit code in Visual Studio.</span></span>

<span data-ttu-id="4a0cb-115">Wenn Sie über eine vorhandene *editorconfig* -Datei für Editor-Einstellungen verfügen, z. b. eine Einzugs Größe, oder wenn Sie nachfolgende Leerzeichen kürzen möchten, können Sie die Konfigurationsoptionen für die Code Analyse in derselben Datei platzieren.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-115">If you have an existing *.editorconfig* file for editor settings such as indent size or whether to trim trailing whitespace, you can place your code analysis configuration options in the same file.</span></span>

> [!TIP]
> <span data-ttu-id="4a0cb-116">Visual Studio stellt eine *Editor config* -Element Vorlage bereit, die es einfach macht, eine dieser Dateien zu Ihrem Projekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-116">Visual Studio provides an *.editorconfig* item template that makes is easy to add one of these files to your project.</span></span> <span data-ttu-id="4a0cb-117">Weitere Informationen finden Sie unter [Hinzufügen einer EditorConfig Datei zu einem Projekt](/visualstudio/ide/create-portable-custom-editor-options#add-an-editorconfig-file-to-a-project).</span><span class="sxs-lookup"><span data-stu-id="4a0cb-117">For more information, see [Add an EditorConfig file to a project](/visualstudio/ide/create-portable-custom-editor-options#add-an-editorconfig-file-to-a-project).</span></span>

### <a name="example"></a><span data-ttu-id="4a0cb-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4a0cb-118">Example</span></span>

<span data-ttu-id="4a0cb-119">Im folgenden finden Sie eine Beispiel EditorConfig Datei zum Konfigurieren von Optionen und des Regel schwere Grads:</span><span class="sxs-lookup"><span data-stu-id="4a0cb-119">Following is an example EditorConfig file to configure options and rule severity:</span></span>

```ini
# Remove the line below if you want to inherit .editorconfig settings from higher directories
root = true

# C# files
[*.cs]

#### Core EditorConfig Options ####

# Indentation and spacing
indent_size = 4
indent_style = space
tab_width = 4

#### .NET Coding Conventions ####

# this. and Me. preferences
dotnet_style_qualification_for_method = true:warning

#### Diagnostic configuration ####

# CA1000: Do not declare static members on generic types
dotnet_diagnostic.CA1000.severity = warning
```

## <a name="global-analyzerconfig"></a><span data-ttu-id="4a0cb-120">Globale analyzerconfig</span><span class="sxs-lookup"><span data-stu-id="4a0cb-120">Global AnalyzerConfig</span></span>

<span data-ttu-id="4a0cb-121">Beginnend mit dem .net 5,0 SDK (das in Visual Studio 2019, Version 16,8 und höheren Versionen unterstützt wird), können Sie auch Analyzer-Optionen mit globalen _analyzerconfig_ -Dateien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-121">Starting with the .NET 5.0 SDK (which is supported in Visual Studio 2019 version 16.8 and later versions), you can also configure analyzer options with global _AnalyzerConfig_ files.</span></span> <span data-ttu-id="4a0cb-122">Diese Dateien werden verwendet, um Optionen bereitzustellen, **die für alle Quelldateien in einem Projekt gelten**, unabhängig von deren Dateinamen oder Dateipfaden.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-122">These files are used to provide **options that apply to all the source files in a project**, regardless of their file names or file paths.</span></span>

<span data-ttu-id="4a0cb-123">Im Unterschied zu [EditorConfig](#editorconfig) Dateien können globale Konfigurationsdateien nicht verwendet werden, um Editor-Stileinstellungen für IDES zu konfigurieren, wie z. b. die Einzugs Größe oder das Kürzen von nachfolgenden Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-123">Unlike [EditorConfig](#editorconfig) files, global config files can't be used to configure editor style settings for IDEs, such as indent size or whether to trim trailing whitespace.</span></span> <span data-ttu-id="4a0cb-124">Stattdessen sind Sie ausschließlich für die Angabe von Analyzer-Konfigurationsoptionen auf Projektebene vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-124">Instead, they are designed purely for specifying project-level analyzer configuration options.</span></span>

### <a name="format"></a><span data-ttu-id="4a0cb-125">Format</span><span class="sxs-lookup"><span data-stu-id="4a0cb-125">Format</span></span>

<span data-ttu-id="4a0cb-126">Im Unterschied EditorConfig zu Dateien, die über Abschnitts Header verfügen müssen, z `[*.cs]` . b., um die entsprechenden Dateien und Ordner zu identifizieren, haben globale analyzerconfig-Dateien keine Abschnitts Header.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-126">Unlike EditorConfig files, which must have section headers, such as `[*.cs]`, to identify the applicable files and folders, global AnalyzerConfig files don't have section headers.</span></span> <span data-ttu-id="4a0cb-127">Stattdessen benötigen Sie einen Eintrag der obersten Ebene des Formulars `is_global = true` , um Sie von regulären Dateien zu unterscheiden EditorConfig .</span><span class="sxs-lookup"><span data-stu-id="4a0cb-127">Instead, they require a top level entry of the form `is_global = true` to differentiate them from regular EditorConfig files.</span></span> <span data-ttu-id="4a0cb-128">Dies gibt an, dass alle Optionen in der Datei auf das gesamte Projekt angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-128">This indicates that all the options in the file apply to the entire project.</span></span> <span data-ttu-id="4a0cb-129">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4a0cb-129">For example:</span></span>

```ini
is_global = true
<option_name> = <option_value>
```

### <a name="naming"></a><span data-ttu-id="4a0cb-130">Benennung</span><span class="sxs-lookup"><span data-stu-id="4a0cb-130">Naming</span></span>

<span data-ttu-id="4a0cb-131">Im Unterschied EditorConfig zu Dateien, die benannt werden müssen `.editorconfig` , benötigen globale Konfigurationsdateien keinen bestimmten Namen oder keine Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-131">Unlike EditorConfig files, which must be named `.editorconfig`, global config files do not need to have a specific name or extension.</span></span> <span data-ttu-id="4a0cb-132">Wenn Sie diese Dateien jedoch als benennen, `.globalconfig` werden Sie implizit auf alle c#-und Visual Basic Projekte innerhalb des aktuellen Ordners angewendet, einschließlich der Unterordner.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-132">However, if you name these files as `.globalconfig` then they will be implicitly applied to all the C# and Visual Basic projects within the current folder, including subfolders.</span></span> <span data-ttu-id="4a0cb-133">Andernfalls müssen Sie das Element explizit der `GlobalAnalyzerConfigFiles` MSBuild-Projektdatei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="4a0cb-133">Otherwise, you must explicitly add the `GlobalAnalyzerConfigFiles` item to your MSBuild project file:</span></span>

```xml
<ItemGroup>
  <GlobalAnalyzerConfigFiles Include="<path_to_global_analyzer_config>" />
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="4a0cb-134">Der Eintrag der obersten Ebene `is_global = true` ist auch dann erforderlich, wenn die Datei den Namen hat `.globalconfig` .</span><span class="sxs-lookup"><span data-stu-id="4a0cb-134">The top-level entry `is_global = true` is required even when the file is named `.globalconfig`.</span></span>

### <a name="example"></a><span data-ttu-id="4a0cb-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4a0cb-135">Example</span></span>

<span data-ttu-id="4a0cb-136">Im folgenden finden Sie ein Beispiel für eine globale analyzerconfig-Datei zum Konfigurieren von Optionen und des Regel schwere Grads auf Projektebene:</span><span class="sxs-lookup"><span data-stu-id="4a0cb-136">Following is an example global AnalyzerConfig file to configure options and rule severity at the project level:</span></span>

```ini
# Top level entry required to mark this as a global AnalyzerConfig file
is_global = true

# NOTE: No section headers for configuration entries

#### .NET Coding Conventions ####

# this. and Me. preferences
dotnet_style_qualification_for_method = true:warning

#### Diagnostic configuration ####

# CA1000: Do not declare static members on generic types
dotnet_diagnostic.CA1000.severity = warning
```

## <a name="precedence"></a><span data-ttu-id="4a0cb-137">Rangfolge</span><span class="sxs-lookup"><span data-stu-id="4a0cb-137">Precedence</span></span>

<span data-ttu-id="4a0cb-138">Sowohl EditorConfig Dateien als auch globale analyzerconfig-Dateien geben ein Schlüssel-Wert-Paar für jede Option an.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-138">Both EditorConfig files and global AnalyzerConfig files specify a key-value pair for each option.</span></span> <span data-ttu-id="4a0cb-139">Konflikte treten auf, wenn mehrere Einträge mit demselben Schlüssel, aber unterschiedlichen Werten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-139">Conflicts arise when there are multiple entries with the same key but different values.</span></span>

### <a name="general-options"></a><span data-ttu-id="4a0cb-140">Allgemeine Optionen</span><span class="sxs-lookup"><span data-stu-id="4a0cb-140">General options</span></span>

<span data-ttu-id="4a0cb-141">Wenn Konflikte zwischen Optionen auftreten, werden die folgenden Rang Folge Regeln verwendet, um die Konflikte aufzulösen:</span><span class="sxs-lookup"><span data-stu-id="4a0cb-141">When conflicts arise between options, the following precedence rules are used to resolve the conflicts:</span></span>

- <span data-ttu-id="4a0cb-142">In Konflikt stehende Einträge in derselben Konfigurationsdatei: der Eintrag, der später in der Datei angezeigt wird, gewinnt.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-142">Conflicting entries in the same configuration file: The entry that appears later in the file wins.</span></span> <span data-ttu-id="4a0cb-143">Dies gilt für widersprüchliche Einträge in einer einzelnen EditorConfig Datei und auch innerhalb einer einzelnen globalen analyzerconfig-Datei.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-143">This is true for conflicting entries within a single EditorConfig file and also within a single global AnalyzerConfig file.</span></span>

- <span data-ttu-id="4a0cb-144">In Konflikt stehende Einträge in zwei EditorConfig Dateien: der Eintrag in der Datei, der EditorConfig tiefer im Dateisystem ist und daher über einen längeren Dateipfad verfügt, gewinnt.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-144">Conflicting entries in two EditorConfig files: The entry in the EditorConfig file that's deeper in the file system, and hence has a longer file path, wins.</span></span>

- <span data-ttu-id="4a0cb-145">In Konflikt stehende Einträge in zwei globalen analyzerconfig-Dateien: eine Compilerwarnung wird gemeldet, und beide Einträge werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-145">Conflicting entries in two global AnalyzerConfig files: A compiler warning is reported and both entries are ignored.</span></span>

- <span data-ttu-id="4a0cb-146">In Konflikt stehende Einträge in einer EditorConfig Datei und eine globale analyzerconfig-Datei: der Eintrag in der EditorConfig Datei gewinnt.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-146">Conflicting entries in an EditorConfig file and a Global AnalyzerConfig file: The entry in the EditorConfig file wins.</span></span>

### <a name="severity-options"></a><span data-ttu-id="4a0cb-147">Optionen für Schweregrad</span><span class="sxs-lookup"><span data-stu-id="4a0cb-147">Severity options</span></span>

<span data-ttu-id="4a0cb-148">Die vorherigen [allgemeinen Rang Folge Regeln](#general-options) gelten für alle Optionen, die in den Konfigurationsdateien angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-148">The previous [general precedence rules](#general-options) apply for all options specified in configuration files.</span></span> <span data-ttu-id="4a0cb-149">Für Optionen zum [Konfigurieren des schwere](configuration-options.md#severity-level) Grads gelten die folgenden zusätzlichen Rang Folge Regeln:</span><span class="sxs-lookup"><span data-stu-id="4a0cb-149">For [severity configuration](configuration-options.md#severity-level) options, the following additional precedence rules apply:</span></span>

- <span data-ttu-id="4a0cb-150">Die in der Befehlszeile als Compileroptionen (oder) angegebenen Schweregrad Optionen über `/nowarn` `/warnaserror` schreiben immer die in und globalen analyzerconfig-Dateien angegebenen Optionen für den [Schweregrad](configuration-options.md#severity-level) EditorConfig .</span><span class="sxs-lookup"><span data-stu-id="4a0cb-150">Severity options specified at the command line as compiler options (`/nowarn` or `/warnaserror`) always override [severity configuration](configuration-options.md#severity-level) options specified in EditorConfig and global AnalyzerConfig files.</span></span>

- <span data-ttu-id="4a0cb-151">Schweregrad Optionen können auch mit einer [RuleSet](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) -Datei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-151">Severity options can also be specified with a [Ruleset](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) file.</span></span> <span data-ttu-id="4a0cb-152">RuleSets-Dateien sind jedoch veraltet und werden von EditorConfig und globalen analyzerconfig-Dateien entfernt.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-152">However, rulesets files are deprecated in favor of EditorConfig and global AnalyzerConfig files.</span></span> <span data-ttu-id="4a0cb-153">Es wird empfohlen, [RuleSet-Dateien in eine entsprechende EditorConfig Datei zu konvertieren](/visualstudio/code-quality/use-roslyn-analyzers#convert-an-existing-ruleset-file-to-editorconfig-file).</span><span class="sxs-lookup"><span data-stu-id="4a0cb-153">It's recommended that you [convert ruleset files to an equivalent EditorConfig file](/visualstudio/code-quality/use-roslyn-analyzers#convert-an-existing-ruleset-file-to-editorconfig-file).</span></span> <span data-ttu-id="4a0cb-154">Die Rangfolge für in Konflikt stehende Schweregrade von einer RuleSet-Datei und EditorConfig oder von globalen analyzerconfig-Dateien ist nicht _definiert_.</span><span class="sxs-lookup"><span data-stu-id="4a0cb-154">Precedence for conflicting severity entries from a ruleset file and EditorConfig or global AnalyzerConfig files is _undefined_.</span></span>

- <span data-ttu-id="4a0cb-155">Informationen zu Rang folgen Regeln für Verwandte Schweregrad Optionen mit unterschiedlichen Schlüsseln, z. b. wenn verschiedene Schweregrade für eine einzelne Regel angegeben werden, und für die Kategorie, zu der die Regel fällt, finden Sie unter [Konfigurationsoptionen für die Code Analyse](configuration-options.md#precedence).</span><span class="sxs-lookup"><span data-stu-id="4a0cb-155">For information about precedence rules for related severity options with different keys, for example, when different severities are specified for a single rule and for the category that rule falls under, see [Configuration options for code analysis](configuration-options.md#precedence).</span></span>

## <a name="see-also"></a><span data-ttu-id="4a0cb-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a0cb-156">See also</span></span>

- [<span data-ttu-id="4a0cb-157">EditorConfig vs Global analyzerconfig-Entwurfsproblem</span><span class="sxs-lookup"><span data-stu-id="4a0cb-157">EditorConfig vs global AnalyzerConfig design issue</span></span>](https://github.com/dotnet/roslyn/issues/47707)
