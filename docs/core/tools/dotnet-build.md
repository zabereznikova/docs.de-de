---
title: Befehl „dotnet build“
description: Der dotnet build-Befehl erstellt ein Projekt und alle seine Abhängigkeiten.
ms.date: 04/24/2019
ms.openlocfilehash: df264fe830259832e5c75db9fd71230ba70a9f18
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2019
ms.locfileid: "65959194"
---
# <a name="dotnet-build"></a><span data-ttu-id="b9638-103">dotnet build</span><span class="sxs-lookup"><span data-stu-id="b9638-103">dotnet build</span></span>

<span data-ttu-id="b9638-104">**Dieser Artikel gilt für: ✓**.NET Core 1.x SDK und spätere Versionen</span><span class="sxs-lookup"><span data-stu-id="b9638-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="b9638-105">name</span><span class="sxs-lookup"><span data-stu-id="b9638-105">Name</span></span>

<span data-ttu-id="b9638-106">`dotnet build`: Erstellt ein Projekt und alle seine Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="b9638-106">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b9638-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="b9638-107">Synopsis</span></span>

```
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--force] [--interactive] [--no-dependencies]
    [--no-incremental] [--nologo] [--no-restore] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```

## <a name="description"></a><span data-ttu-id="b9638-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9638-108">Description</span></span>

<span data-ttu-id="b9638-109">Der `dotnet build`-Befehl erstellt das Projekt und die zugehörigen Abhängigkeiten in einen Satz von Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="b9638-109">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="b9638-110">Die Binärdateien enthalten den Projektcode in Intermediate Language-Dateien (IL) mit einer *.dll*-Erweiterung und Symboldateien, die zum Debuggen mit einer *.pdb*-Erweiterung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b9638-110">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension and symbol files used for debugging with a *.pdb* extension.</span></span> <span data-ttu-id="b9638-111">Eine JSON-Datei für Abhängigkeiten ( *\*.deps.json*) wird erstellt, die Abhängigkeiten der Anwendung aufführt.</span><span class="sxs-lookup"><span data-stu-id="b9638-111">A dependencies JSON file (*\*.deps.json*) is produced that lists the dependencies of the application.</span></span> <span data-ttu-id="b9638-112">Eine *\*.runtimeconfig.json*-Datei wird erstellt, die die gemeinsam genutzte Laufzeit und deren Version für die Anwendung anzeigt.</span><span class="sxs-lookup"><span data-stu-id="b9638-112">A *\*.runtimeconfig.json* file is produced, which specifies the shared runtime and its version for the application.</span></span>

<span data-ttu-id="b9638-113">Verfügt das Projekt über Abhängigkeiten von Drittanbietern, z.B. Bibliotheken von NuGet, werden diese aus dem NuGet-Cache aufgelöst und sind nicht mit der Buildausgabe des Projekts verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b9638-113">If the project has third-party dependencies, such as libraries from NuGet, they're resolved from the NuGet cache and aren't available with the project's built output.</span></span> <span data-ttu-id="b9638-114">Bedenken Sie, dass das Produkt von `dotnet build` nicht auf einen anderen Computer zur Ausführung übertragen werden kann.</span><span class="sxs-lookup"><span data-stu-id="b9638-114">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="b9638-115">Dies unterscheidet sich zum Verhalten des .NET Framework, bei dem die Erstellung eines ausführbaren Projekts (eine Anwendung) eine Ausgabe erzeugt, die auf jedem Computer ausgeführt werden kann, auf dem .NET Framework installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b9638-115">This is in contrast to the behavior of the .NET Framework in which building an executable project (an application) produces output that's runnable on any machine where the .NET Framework is installed.</span></span> <span data-ttu-id="b9638-116">Um ein ähnliches Verhalten mit .NET Core zu erhalten, müssen Sie den Befehl [dotnet publish](dotnet-publish.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9638-116">To have a similar experience with .NET Core, you need to use the [dotnet publish](dotnet-publish.md) command.</span></span> <span data-ttu-id="b9638-117">Weitere Informationen finden Sie unter [.NET Core Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="b9638-117">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="b9638-118">Das Erstellen erfordert die *project.assets.json*-Datei, die die Abhängigkeiten Ihrer Anwendung aufführt.</span><span class="sxs-lookup"><span data-stu-id="b9638-118">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="b9638-119">Die Datei wird erstellt, wenn [`dotnet restore`](dotnet-restore.md) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b9638-119">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="b9638-120">Ohne die vorhandenen Ressourcendateien kann das Tool die Verweisassemblys nicht auflösen, was zu Fehlern führt.</span><span class="sxs-lookup"><span data-stu-id="b9638-120">Without the assets file in place, the tooling can't resolve reference assemblies, which results in errors.</span></span> <span data-ttu-id="b9638-121">Mit dem .NET Core 1.x SDK müssen Sie `dotnet restore` explizit ausführen, bevor Sie `dotnet build` ausführen.</span><span class="sxs-lookup"><span data-stu-id="b9638-121">With .NET Core 1.x SDK, you needed to explicitly run the `dotnet restore` before running `dotnet build`.</span></span> <span data-ttu-id="b9638-122">Ab dem .NET Core 2.0 SDK wird `dotnet restore` implizit ausgeführt, wenn Sie `dotnet build` ausführen.</span><span class="sxs-lookup"><span data-stu-id="b9638-122">Starting with .NET Core 2.0 SDK, `dotnet restore` runs implicitly when you run `dotnet build`.</span></span> <span data-ttu-id="b9638-123">Wenn Sie das implizite Wiederherstellen deaktivieren möchten, wenn Sie den Buildbefehl ausführen, können Sie die `--no-restore`-Option übergeben.</span><span class="sxs-lookup"><span data-stu-id="b9638-123">If you want to disable implicit restore when running the build command, you can pass the `--no-restore` option.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

<span data-ttu-id="b9638-124">Ob das Projekt ausführbar ist oder nicht, richtet sich nach der `<OutputType>`-Eigenschaft in der Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="b9638-124">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="b9638-125">Das folgende Beispiel zeigt ein Projekt, das ausführbaren Code erzeugt:</span><span class="sxs-lookup"><span data-stu-id="b9638-125">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="b9638-126">Lassen Sie die `<OutputType>`-Eigenschaft weg, um eine Bibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b9638-126">To produce a library, omit the `<OutputType>` property.</span></span> <span data-ttu-id="b9638-127">Der Hauptunterschied in der Buildausgabe ist, dass die IL-DLL für eine Bibliothek keine Einstiegspunkte enthält und nicht ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b9638-127">The main difference in built output is that the IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

### <a name="msbuild"></a><span data-ttu-id="b9638-128">MSBuild</span><span class="sxs-lookup"><span data-stu-id="b9638-128">MSBuild</span></span>

<span data-ttu-id="b9638-129">`dotnet build` verwendet MSBuild zum Erstellen des Projekts und unterstützt daher parallele und inkrementelle Builds.</span><span class="sxs-lookup"><span data-stu-id="b9638-129">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="b9638-130">Weitere Informationen finden Sie unter [Incremental Builds](/visualstudio/msbuild/incremental-builds) (Inkrementelle Builds).</span><span class="sxs-lookup"><span data-stu-id="b9638-130">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="b9638-131">Zusätzlich zu diesen Optionen akzeptiert der `dotnet build`-Befehl MSBuild-Optionen, wie z.B. `-p` zum Festlegen von Eigenschaften oder `-l` zum Definieren eines Protokolls.</span><span class="sxs-lookup"><span data-stu-id="b9638-131">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `-p` for setting properties or `-l` to define a logger.</span></span> <span data-ttu-id="b9638-132">Weitere Informationen zu diesen Optionen finden Sie in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="b9638-132">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="b9638-133">Sie können auch den Befehl [dotnet msbuild](dotnet-msbuild.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9638-133">Or you can also use the [dotnet msbuild](dotnet-msbuild.md) command.</span></span>

<span data-ttu-id="b9638-134">Die Ausführung von `dotnet build` entspricht `dotnet msbuild -restore -target:Build`.</span><span class="sxs-lookup"><span data-stu-id="b9638-134">Running `dotnet build` is equivalent to `dotnet msbuild -restore -target:Build`.</span></span>

## <a name="arguments"></a><span data-ttu-id="b9638-135">Argumente</span><span class="sxs-lookup"><span data-stu-id="b9638-135">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="b9638-136">Die zu erstellende Projekt- oder Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="b9638-136">The project or solution file to build.</span></span> <span data-ttu-id="b9638-137">Wenn Sie keine Projekt- oder Projektmappendatei angeben, durchsucht MSBuild das aktuelle Arbeitsverzeichnis nach einer Dateierweiterung, die mit *proj* oder *sln* endet, und verwendet diese.</span><span class="sxs-lookup"><span data-stu-id="b9638-137">If a project or solution file isn't specified, MSBuild searches the current working directory for a file that has a file extension that ends in either *proj* or *sln* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="b9638-138">Optionen</span><span class="sxs-lookup"><span data-stu-id="b9638-138">Options</span></span>

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="b9638-139">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="b9638-139">Defines the build configuration.</span></span> <span data-ttu-id="b9638-140">Der Standardwert ist `Debug`sein.</span><span class="sxs-lookup"><span data-stu-id="b9638-140">The default value is `Debug`.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b9638-141">Kompiliert für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="b9638-141">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="b9638-142">Das Framework muss in der [Projektdatei](csproj.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="b9638-142">The framework must be defined in the [project file](csproj.md).</span></span>

* **`--force`**

  <span data-ttu-id="b9638-143">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="b9638-143">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="b9638-144">Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="b9638-144">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span> <span data-ttu-id="b9638-145">Verfügbar seit .NET Core 2.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="b9638-145">Available since .NET Core 2.0 SDK.</span></span>

* **`-h|--help`**

  <span data-ttu-id="b9638-146">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="b9638-146">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="b9638-147">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten.</span><span class="sxs-lookup"><span data-stu-id="b9638-147">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="b9638-148">Beispielsweise, um die Authentifizierung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b9638-148">For example, to complete authentication.</span></span> <span data-ttu-id="b9638-149">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="b9638-149">Available since .NET Core 3.0 SDK.</span></span>

* **`--no-dependencies`**

  <span data-ttu-id="b9638-150">Ignoriert Verweise zwischen Projekten (P2P) und erstellt nur das angegebene Stammprojekt.</span><span class="sxs-lookup"><span data-stu-id="b9638-150">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

* **`--no-incremental`**

  <span data-ttu-id="b9638-151">Markiert den Build als unsicher für inkrementelle Builds.</span><span class="sxs-lookup"><span data-stu-id="b9638-151">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="b9638-152">Das Flag deaktiviert die inkrementelle Kompilierung und erzwingt eine komplette Neuerstellung des Abhängigkeitsdiagramms des Projekts.</span><span class="sxs-lookup"><span data-stu-id="b9638-152">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

* **`--no-logo`**

  <span data-ttu-id="b9638-153">Unterdrückt die Anzeige von Startbanner und Copyrightmeldung.</span><span class="sxs-lookup"><span data-stu-id="b9638-153">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="b9638-154">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="b9638-154">Available since .NET Core 3.0 SDK.</span></span>

* **`--no-restore`**

  <span data-ttu-id="b9638-155">Führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="b9638-155">Doesn't execute an implicit restore during build.</span></span> <span data-ttu-id="b9638-156">Verfügbar seit .NET Core 2.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="b9638-156">Available since .NET Core 2.0 SDK.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="b9638-157">Verzeichnis, in dem die erstellten Binärdateien platziert werden.</span><span class="sxs-lookup"><span data-stu-id="b9638-157">Directory in which to place the built binaries.</span></span> <span data-ttu-id="b9638-158">Sie müssen außerdem `--framework` definieren, wenn Sie diese Option angeben.</span><span class="sxs-lookup"><span data-stu-id="b9638-158">You also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="b9638-159">Wenn nicht angegeben, ist der Standardpfad `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="b9638-159">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="b9638-160">Legt die Ziellaufzeit fest.</span><span class="sxs-lookup"><span data-stu-id="b9638-160">Specifies the target runtime.</span></span> <span data-ttu-id="b9638-161">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="b9638-161">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="b9638-162">Legt den MSBuild-Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="b9638-162">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="b9638-163">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="b9638-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="b9638-164">Die Standardeinstellung ist `minimal`.</span><span class="sxs-lookup"><span data-stu-id="b9638-164">The default is `minimal`.</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="b9638-165">Hiermit wird der Wert der `$(VersionSuffix)`-Eigenschaft festgelegt, die beim Erstellen des Projekts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b9638-165">Sets the value of the `$(VersionSuffix)` property to use when building the project.</span></span> <span data-ttu-id="b9638-166">Dies funktioniert nur, wenn die `$(Version)`-Eigenschaft nicht festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b9638-166">This only works if the `$(Version)` property isn't set.</span></span> <span data-ttu-id="b9638-167">Dann wird `$(Version)` auf `$(VersionPrefix)` festgelegt, kombiniert mit dem `$(VersionSuffix)`, getrennt durch einen Bindestrich.</span><span class="sxs-lookup"><span data-stu-id="b9638-167">Then, `$(Version)` is set to the `$(VersionPrefix)` combined with the `$(VersionSuffix)`, separated by a dash.</span></span>

## <a name="examples"></a><span data-ttu-id="b9638-168">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b9638-168">Examples</span></span>

* <span data-ttu-id="b9638-169">Erstellt ein Projekt und seine Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="b9638-169">Build a project and its dependencies:</span></span>

  ```console
  dotnet build
  ```

* <span data-ttu-id="b9638-170">Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="b9638-170">Build a project and its dependencies using Release configuration:</span></span>

  ```console
  dotnet build --configuration Release
  ```

* <span data-ttu-id="b9638-171">Erstellt ein Projekt und seine Abhängigkeiten für eine bestimmte Laufzeit (in diesem Beispiel Ubuntu 18.04):</span><span class="sxs-lookup"><span data-stu-id="b9638-171">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 18.04):</span></span>

  ```console
  dotnet build --runtime ubuntu.18.04-x64
  ```

* <span data-ttu-id="b9638-172">Erstellt ein Projekt und verwendet die angegebene NuGet-Paketquelle während des Wiederherstellungsvorgangs (.NET Core 2.0 SDK und spätere Versionen):</span><span class="sxs-lookup"><span data-stu-id="b9638-172">Build the project and use the specified NuGet package source during the restore operation (.NET Core 2.0 SDK and later versions):</span></span>

  ```console
  dotnet build --source c:\packages\mypackages
  ```

* <span data-ttu-id="b9638-173">Erstellen Sie das Projekt, und legen Sie Version 1.2.3.4 als Buildparameter mithilfe der `-p` [MSBuild-Option](#msbuild) fest:</span><span class="sxs-lookup"><span data-stu-id="b9638-173">Build the project and set version 1.2.3.4 as a build parameter using the `-p` [MSBuild option](#msbuild):</span></span>

  ```console
  dotnet build -p:Version=1.2.3.4
  ```
