---
title: "dotnet-build-Befehl – .NET Core-CLI"
description: "Der dotnet-build-Befehl erstellt ein Projekt und alle seine Abhängigkeiten."
keywords: dotnet-build, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 5e1a2bc4-a919-4a86-8f33-a9b218b1fcb3
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d2006b15978f384e53e43a0a2562e81d10582abd
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-build"></a><span data-ttu-id="c9ed0-104">dotnet-build</span><span class="sxs-lookup"><span data-stu-id="c9ed0-104">dotnet-build</span></span>

## <a name="name"></a><span data-ttu-id="c9ed0-105">Name</span><span class="sxs-lookup"><span data-stu-id="c9ed0-105">Name</span></span>

<span data-ttu-id="c9ed0-106">`dotnet-build`: Erstellt ein Projekt und alle seine Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="c9ed0-106">`dotnet-build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c9ed0-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c9ed0-107">Synopsis</span></span>

`dotnet build [<PROJECT>] [-o|--output] [-f|--framework] [-c|--configuration] [-r|--runtime] [--version-suffix] [--no-incremental] [--no-dependencies] [-v|--verbosity] [-h|--help]`

## <a name="description"></a><span data-ttu-id="c9ed0-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c9ed0-108">Description</span></span>

<span data-ttu-id="c9ed0-109">Der `dotnet build`-Befehl erstellt das Projekt und die zugehörigen Abhängigkeiten in einen Satz von Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-109">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="c9ed0-110">Die Binärdateien enthalten den Projektcode in Intermediate Language-Dateien (IL) mit einer *.dll*-Erweiterung und Symboldateien, die zum Debuggen mit einer *.pdb*-Erweiterung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-110">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension and symbol files used for debugging with a *.pdb* extension.</span></span> <span data-ttu-id="c9ed0-111">Eine JSON-Datei für Abhängigkeiten (*\*.deps.json*) wird erstellt, die Abhängigkeiten der Anwendung aufführt.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-111">A dependencies JSON file (*\*.deps.json*) is produced that lists the dependencies of the application.</span></span> <span data-ttu-id="c9ed0-112">Eine *\*.runtimeconfig.json*-Datei wird erstellt, die die gemeinsam genutzte Laufzeit und deren Version für die Anwendung anzeigt.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-112">A *\*.runtimeconfig.json* file is produced, which specifies the shared runtime and its version for the application.</span></span>

<span data-ttu-id="c9ed0-113">Verfügt das Projekt über Abhängigkeiten von Drittanbietern, z.B. Bibliotheken von NuGet, werden diese aus dem NuGet-Cache aufgelöst und sind nicht mit der Buildausgabe des Projekts verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-113">If the project has third-party dependencies, such as libraries from NuGet, they're resolved from the NuGet cache and aren't available with the project's built output.</span></span> <span data-ttu-id="c9ed0-114">Bedenken Sie, dass das Produkt von `dotnet build` nicht auf einen anderen Computer zur Ausführung übertragen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-114">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="c9ed0-115">Dies unterscheidet sich zum Verhalten des .NET Framework, bei dem die Erstellung eines ausführbaren Projekts (eine Anwendung) eine Ausgabe erzeugt, die auf jedem Computer ausgeführt werden kann, auf dem .NET Framework installiert ist.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-115">This is in contrast to the behavior of the .NET Framework in which building an executable project (an application) produces output that's runnable on any machine where the .NET Framework is installed.</span></span> <span data-ttu-id="c9ed0-116">Um ein ähnliches Verhalten mit .NET Core zu erhalten, verwenden Sie den Befehl [dotnet publish](dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="c9ed0-116">To have a similar experience with .NET Core, you use the [dotnet publish](dotnet-publish.md) command.</span></span> <span data-ttu-id="c9ed0-117">Weitere Informationen finden Sie unter [.NET Core Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="c9ed0-117">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> 

<span data-ttu-id="c9ed0-118">Das Erstellen erfordert die *project.assets.json*-Datei, die die Abhängigkeiten Ihrer Anwendung aufführt.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-118">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="c9ed0-119">Die Datei wird erstellt, wenn Sie [`dotnet restore`](dotnet-restore.md) vor dem Erstellen des Projekts ausführen.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-119">The file is created when you execute [`dotnet restore`](dotnet-restore.md) before building the project.</span></span> <span data-ttu-id="c9ed0-120">Ohne die vorhandenen Ressourcendateien kann das Tools die Verweisassemblys nicht auflösen, was zu Fehlern führt.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-120">Without the assets file in place, the tooling cannot resolve reference assemblies, which will result in errors.</span></span>

<span data-ttu-id="c9ed0-121">`dotnet build` verwendet MSBuild, um das Projekt zu erstellen und unterstützt daher parallele und inkrementelle Builds.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-121">`dotnet build` uses MSBuild to build the project; thus, it supports both parallel and incremental builds.</span></span> <span data-ttu-id="c9ed0-122">Weitere Informationen finden Sie unter [Inkrementelle Builds](/visualstudio/msbuild/incremental-builds).</span><span class="sxs-lookup"><span data-stu-id="c9ed0-122">Refer to [Incremental Builds](/visualstudio/msbuild/incremental-builds) for more information.</span></span> 

<span data-ttu-id="c9ed0-123">Zusätzlich zu diesen Optionen akzeptiert der `dotnet build`-Befehl MSBuild-Optionen, wie z.B. `/p` zum Festlegen von Eigenschaften oder `/l` zum Definieren eines Protokolls.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-123">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `/p` for setting properties or `/l` to define a logger.</span></span> <span data-ttu-id="c9ed0-124">Erfahren Sie mehr über diese Optionen in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="c9ed0-124">Learn more about these options in the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> 

<span data-ttu-id="c9ed0-125">Ob das Projekt ausführbar ist oder nicht, richtet sich nach der `<OutputType>`-Eigenschaft in der Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-125">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="c9ed0-126">Das folgende Beispiel zeigt ein Projekt, das ausführbaren Code erzeugt:</span><span class="sxs-lookup"><span data-stu-id="c9ed0-126">The following example shows a project that will produce executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="c9ed0-127">Lassen Sie die `<OutputType>`-Eigenschaft weg, um eine Bibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-127">In order to produce a library, omit the `<OutputType>` property.</span></span> <span data-ttu-id="c9ed0-128">Der Hauptunterschied in der Buildausgabe ist, dass die IL-DLL für eine Bibliothek keine Einstiegspunkte enthält und nicht ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-128">The main difference in built output is that the IL DLL for a library doesn't contain entry points and can't be executed.</span></span> 

## <a name="arguments"></a><span data-ttu-id="c9ed0-129">Argumente</span><span class="sxs-lookup"><span data-stu-id="c9ed0-129">Arguments</span></span>

`PROJECT`

<span data-ttu-id="c9ed0-130">Die zu erstellende Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-130">The project file to build.</span></span> <span data-ttu-id="c9ed0-131">Wenn Sie keine Projektdatei angeben, durchsucht MSBuild das aktuelle Arbeitsverzeichnis nach einer Dateierweiterung, die mit *proj* endet, und verwendet diese.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-131">If a project file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="c9ed0-132">Optionen</span><span class="sxs-lookup"><span data-stu-id="c9ed0-132">Options</span></span>

`-h|--help`

<span data-ttu-id="c9ed0-133">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-133">Prints out a short help for the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c9ed0-134">Verzeichnis, in dem die erstellten Binärdateien platziert werden.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-134">Directory in which to place the built binaries.</span></span> <span data-ttu-id="c9ed0-135">Sie müssen außerdem `--framework` definieren, wenn Sie diese Option angeben.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-135">You also need to define `--framework` when you specify this option.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="c9ed0-136">Kompiliert für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="c9ed0-136">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="c9ed0-137">Das Framework muss in der [Projektdatei](csproj.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-137">The framework must be defined in the [project file](csproj.md).</span></span>

`-c|--configuration <CONFIGURATION>`

<span data-ttu-id="c9ed0-138">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-138">Defines the build configuration.</span></span> <span data-ttu-id="c9ed0-139">Wenn nicht angegeben, wird standardmäßig die Buildkonfiguration auf `Debug` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-139">If omitted, the build configuration defaults to `Debug`.</span></span> <span data-ttu-id="c9ed0-140">Verwendet `Release`, um eine Releasekonfiguration zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-140">Use `Release` build a Release configuration.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="c9ed0-141">Legt die Ziellaufzeit fest.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-141">Specifies the target runtime.</span></span> <span data-ttu-id="c9ed0-142">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="c9ed0-142">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="c9ed0-143">Definiert das Versionssuffix für ein Sternchen (`*`) im Versionsfeld der Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-143">Defines the version suffix for an asterisk (`*`) in the version field of the project file.</span></span> <span data-ttu-id="c9ed0-144">Das Format entspricht den NuGet-Versionsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-144">The format follows NuGet's version guidelines.</span></span>

`--no-incremental`

<span data-ttu-id="c9ed0-145">Markiert den Build als unsicher für inkrementelle Builds.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-145">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="c9ed0-146">Deaktiviert die inkrementelle Kompilierung und erzwingt eine komplette Neuerstellung des Abhängigkeitsdiagramms des Projekts.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-146">This turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

`--no-dependencies`

<span data-ttu-id="c9ed0-147">Ignoriert Verweise zwischen Projekten (P2P) und erstellt nur das zum Erstellen angegebene Stammprojekt.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-147">Ignores project-to-project (P2P) references and only builds the root project specified to build.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="c9ed0-148">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-148">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c9ed0-149">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c9ed0-149">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="c9ed0-150">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c9ed0-150">Examples</span></span>

<span data-ttu-id="c9ed0-151">Erstellt ein Projekt und seine Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="c9ed0-151">Build a project and its dependencies:</span></span>

`dotnet build`

<span data-ttu-id="c9ed0-152">Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="c9ed0-152">Build a project and its dependencies using Release configuration:</span></span>

`dotnet build --configuration Release`

<span data-ttu-id="c9ed0-153">Erstellt ein Projekt und seine Abhängigkeiten für eine bestimmte Laufzeit (in diesem Beispiel Ubuntu 16.04):</span><span class="sxs-lookup"><span data-stu-id="c9ed0-153">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 16.04):</span></span>

`dotnet build --runtime ubuntu.16.04-x64`

