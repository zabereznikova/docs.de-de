---
title: Befehl „dotnet build“
description: Der dotnet build-Befehl erstellt ein Projekt und alle seine Abhängigkeiten.
ms.date: 10/14/2019
ms.openlocfilehash: b85ef06aa445e4708487deed9ec6bfeffeab3657
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454215"
---
# <a name="dotnet-build"></a><span data-ttu-id="bd5a9-103">dotnet build</span><span class="sxs-lookup"><span data-stu-id="bd5a9-103">dotnet build</span></span>

<span data-ttu-id="bd5a9-104">**Dieser Artikel gilt für: ✓**.NET Core 1.x SDK und spätere Versionen</span><span class="sxs-lookup"><span data-stu-id="bd5a9-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="bd5a9-105">name</span><span class="sxs-lookup"><span data-stu-id="bd5a9-105">Name</span></span>

<span data-ttu-id="bd5a9-106">`dotnet build`: Erstellt ein Projekt und alle seine Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="bd5a9-106">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="bd5a9-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="bd5a9-107">Synopsis</span></span>

```dotnetcli
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--force]
    [--interactive] [--no-dependencies] [--no-incremental] [--no-restore] [--nologo] 
    [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```

## <a name="description"></a><span data-ttu-id="bd5a9-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bd5a9-108">Description</span></span>

<span data-ttu-id="bd5a9-109">Der `dotnet build`-Befehl erstellt das Projekt und die zugehörigen Abhängigkeiten in einen Satz von Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-109">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="bd5a9-110">Die Binärdateien enthalten den Projektcode in IL-Dateien (Intermediate Language) mit der Erweiterung *DLL*.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-110">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension.</span></span>  <span data-ttu-id="bd5a9-111">Abhängig vom Projekttyp und den Einstellungen können auch andere Dateien enthalten sein, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="bd5a9-111">Depending on the project type and settings, other files may be included, such as:</span></span>

- <span data-ttu-id="bd5a9-112">Eine ausführbare Datei, die zum Ausführen der Anwendung verwendet werden kann, wenn der Projekttyp eine ausführbare Datei für .NET Core 3.0 oder höher ist.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-112">An executable that can be used to run the application, if the project type is an executable targeting .NET Core 3.0 or later.</span></span>
- <span data-ttu-id="bd5a9-113">Symboldateien mit der Erweiterung *PDB*, die für das Debuggen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-113">Symbol files used for debugging with a *.pdb* extension.</span></span>
- <span data-ttu-id="bd5a9-114">Eine Datei *.deps.json*, die die Abhängigkeiten der Anwendung oder Bibliothek auflistet.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-114">A *.deps.json* file, which lists the dependencies of the application or library.</span></span>
- <span data-ttu-id="bd5a9-115">Eine Datei *.runtimeconfig.json*, die die freigegebene Laufzeit und deren Version für eine Anwendung angibt.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-115">A *.runtimeconfig.json* file, which specifies the shared runtime and its version for an application.</span></span>
- <span data-ttu-id="bd5a9-116">Andere Bibliotheken, von denen das Projekt abhängig ist (über Projektverweise oder NuGet-Paketverweise).</span><span class="sxs-lookup"><span data-stu-id="bd5a9-116">Other libraries that the project depends on (via project references or NuGet package references).</span></span>

<span data-ttu-id="bd5a9-117">Bei ausführbaren Projekten für frühere Versionen als .NET Core 3.0 werden Bibliotheksabhängigkeiten von NuGet in der Regel NICHT in den Ausgabeordner kopiert.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-117">For executable projects targeting versions earlier than .NET Core 3.0, library dependencies from NuGet are typically NOT copied to the output folder.</span></span>  <span data-ttu-id="bd5a9-118">Sie werden zur Laufzeit aus dem NuGet-Ordner für globale Pakete aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-118">They're resolved from the NuGet global packages folder at run time.</span></span> <span data-ttu-id="bd5a9-119">Bedenken Sie, dass das Produkt von `dotnet build` nicht auf einen anderen Computer zur Ausführung übertragen werden kann.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-119">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="bd5a9-120">Zum Erstellen einer Version der Anwendung, die bereitgestellt werden kann, müssen Sie sie veröffentlichen (z.B. mit dem Befehl [dotnet publish](dotnet-publish.md)).</span><span class="sxs-lookup"><span data-stu-id="bd5a9-120">To create a version of the application that can be deployed, you need to publish it (for example, with the [dotnet publish](dotnet-publish.md) command).</span></span> <span data-ttu-id="bd5a9-121">Weitere Informationen finden Sie unter [.NET Core Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="bd5a9-121">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="bd5a9-122">Bei ausführbaren Projekten für .NET Core 3.0 oder höher werden Bibliotheksabhängigkeiten in den Ausgabeordner kopiert.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-122">For executable projects targeting .NET Core 3.0 and later, library dependencies are copied to the output folder.</span></span> <span data-ttu-id="bd5a9-123">Dies bedeutet, dass die Buildausgabe bereitstellbar sein sollte, wenn keine andere veröffentlichungsspezifische Logik (wie bei Webprojekten) vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-123">This means that if there isn't any other publish-specific logic (such as Web projects have), the build output should be deployable.</span></span>

<span data-ttu-id="bd5a9-124">Das Erstellen erfordert die *project.assets.json*-Datei, die die Abhängigkeiten Ihrer Anwendung aufführt.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-124">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="bd5a9-125">Die Datei wird erstellt, wenn [`dotnet restore`](dotnet-restore.md) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-125">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="bd5a9-126">Ohne die vorhandenen Ressourcendateien kann das Tool die Verweisassemblys nicht auflösen, was zu Fehlern führt.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-126">Without the assets file in place, the tooling can't resolve reference assemblies, which results in errors.</span></span> <span data-ttu-id="bd5a9-127">Mit dem .NET Core 1.x SDK müssen Sie `dotnet restore` explizit ausführen, bevor Sie `dotnet build` ausführen.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-127">With .NET Core 1.x SDK, you needed to explicitly run `dotnet restore` before running `dotnet build`.</span></span> <span data-ttu-id="bd5a9-128">Ab dem .NET Core 2.0 SDK wird `dotnet restore` implizit ausgeführt, wenn Sie `dotnet build` ausführen.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-128">Starting with .NET Core 2.0 SDK, `dotnet restore` runs implicitly when you run `dotnet build`.</span></span> <span data-ttu-id="bd5a9-129">Wenn Sie das implizite Wiederherstellen deaktivieren möchten, wenn Sie den Buildbefehl ausführen, können Sie die `--no-restore`-Option übergeben.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-129">If you want to disable implicit restore when running the build command, you can pass the `--no-restore` option.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

<span data-ttu-id="bd5a9-130">Ob das Projekt ausführbar ist oder nicht, richtet sich nach der `<OutputType>`-Eigenschaft in der Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-130">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="bd5a9-131">Das folgende Beispiel zeigt ein Projekt, das ausführbaren Code erzeugt:</span><span class="sxs-lookup"><span data-stu-id="bd5a9-131">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="bd5a9-132">Um eine Bibliothek zu generieren, lassen Sie die Eigenschaft `<OutputType>` weg, oder ändern Sie ihren Wert in `Library`.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-132">To produce a library, omit the `<OutputType>` property or change its value to `Library`.</span></span> <span data-ttu-id="bd5a9-133">Die IL-DLL für eine Bibliothek enthält keine Einstiegspunkte und kann nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-133">The IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

### <a name="msbuild"></a><span data-ttu-id="bd5a9-134">MSBuild</span><span class="sxs-lookup"><span data-stu-id="bd5a9-134">MSBuild</span></span>

<span data-ttu-id="bd5a9-135">`dotnet build` verwendet MSBuild zum Erstellen des Projekts und unterstützt daher parallele und inkrementelle Builds.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-135">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="bd5a9-136">Weitere Informationen finden Sie unter [Incremental Builds](/visualstudio/msbuild/incremental-builds) (Inkrementelle Builds).</span><span class="sxs-lookup"><span data-stu-id="bd5a9-136">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="bd5a9-137">Zusätzlich zu diesen Optionen akzeptiert der `dotnet build`-Befehl MSBuild-Optionen, wie z.B. `-p` zum Festlegen von Eigenschaften oder `-l` zum Definieren eines Protokolls.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-137">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `-p` for setting properties or `-l` to define a logger.</span></span> <span data-ttu-id="bd5a9-138">Weitere Informationen zu diesen Optionen finden Sie in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="bd5a9-138">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="bd5a9-139">Sie können auch den Befehl [dotnet msbuild](dotnet-msbuild.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-139">Or you can also use the [dotnet msbuild](dotnet-msbuild.md) command.</span></span>

<span data-ttu-id="bd5a9-140">Das Ausführen von `dotnet build` entspricht der Ausführung von `dotnet msbuild -restore`. Die Standardausführlichkeit der Ausgabe unterscheidet sich jedoch.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-140">Running `dotnet build` is equivalent to running `dotnet msbuild -restore`; however, the default verbosity of the output is different.</span></span>

## <a name="arguments"></a><span data-ttu-id="bd5a9-141">Argumente</span><span class="sxs-lookup"><span data-stu-id="bd5a9-141">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="bd5a9-142">Die zu erstellende Projekt- oder Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-142">The project or solution file to build.</span></span> <span data-ttu-id="bd5a9-143">Wenn Sie keine Projekt- oder Projektmappendatei angeben, durchsucht MSBuild das aktuelle Arbeitsverzeichnis nach einer Dateierweiterung, die mit *proj* oder *sln* endet, und verwendet diese.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-143">If a project or solution file isn't specified, MSBuild searches the current working directory for a file that has a file extension that ends in either *proj* or *sln* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="bd5a9-144">Optionen</span><span class="sxs-lookup"><span data-stu-id="bd5a9-144">Options</span></span>

- **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="bd5a9-145">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-145">Defines the build configuration.</span></span> <span data-ttu-id="bd5a9-146">Der Standardwert für die meisten Projekte ist `Debug`, aber Sie können die Buildkonfigurationseinstellungen in Ihrem Projekt überschreiben.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-146">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="bd5a9-147">Kompiliert für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="bd5a9-147">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="bd5a9-148">Das Framework muss in der [Projektdatei](csproj.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-148">The framework must be defined in the [project file](csproj.md).</span></span>

- **`--force`**

  <span data-ttu-id="bd5a9-149">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-149">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="bd5a9-150">Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-150">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span> <span data-ttu-id="bd5a9-151">Verfügbar seit .NET Core 2.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-151">Available since .NET Core 2.0 SDK.</span></span>

- **`-h|--help`**

  <span data-ttu-id="bd5a9-152">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-152">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="bd5a9-153">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-153">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="bd5a9-154">Beispielsweise, um die Authentifizierung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-154">For example, to complete authentication.</span></span> <span data-ttu-id="bd5a9-155">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-155">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="bd5a9-156">Ignoriert Verweise zwischen Projekten (P2P) und erstellt nur das angegebene Stammprojekt.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-156">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

- **`--no-incremental`**

  <span data-ttu-id="bd5a9-157">Markiert den Build als unsicher für inkrementelle Builds.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-157">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="bd5a9-158">Das Flag deaktiviert die inkrementelle Kompilierung und erzwingt eine komplette Neuerstellung des Abhängigkeitsdiagramms des Projekts.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-158">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

- **`--no-restore`**

  <span data-ttu-id="bd5a9-159">Führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-159">Doesn't execute an implicit restore during build.</span></span> <span data-ttu-id="bd5a9-160">Verfügbar seit .NET Core 2.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-160">Available since .NET Core 2.0 SDK.</span></span>

- **`--nologo`**

  <span data-ttu-id="bd5a9-161">Unterdrückt die Anzeige von Startbanner und Copyrightmeldung.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-161">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="bd5a9-162">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-162">Available since .NET Core 3.0 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="bd5a9-163">Verzeichnis, in dem die erstellten Binärdateien platziert werden.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-163">Directory in which to place the built binaries.</span></span> <span data-ttu-id="bd5a9-164">Wenn nicht angegeben, ist der Standardpfad `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-164">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="bd5a9-165">Bei Projekten mit mehreren Zielframeworks (über die `TargetFrameworks`-Eigenschaft) müssen Sie auch `--framework` definieren, wenn Sie diese Option angeben.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-165">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="bd5a9-166">Legt die Ziellaufzeit fest.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-166">Specifies the target runtime.</span></span> <span data-ttu-id="bd5a9-167">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="bd5a9-167">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="bd5a9-168">Legt den MSBuild-Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-168">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="bd5a9-169">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-169">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="bd5a9-170">Die Standardeinstellung ist `minimal`.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-170">The default is `minimal`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="bd5a9-171">Hiermit wird der Wert der `$(VersionSuffix)`-Eigenschaft festgelegt, die beim Erstellen des Projekts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-171">Sets the value of the `$(VersionSuffix)` property to use when building the project.</span></span> <span data-ttu-id="bd5a9-172">Dies funktioniert nur, wenn die `$(Version)`-Eigenschaft nicht festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-172">This only works if the `$(Version)` property isn't set.</span></span> <span data-ttu-id="bd5a9-173">Dann wird `$(Version)` auf `$(VersionPrefix)` festgelegt, kombiniert mit dem `$(VersionSuffix)`, getrennt durch einen Bindestrich.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-173">Then, `$(Version)` is set to the `$(VersionPrefix)` combined with the `$(VersionSuffix)`, separated by a dash.</span></span>

## <a name="examples"></a><span data-ttu-id="bd5a9-174">Beispiele</span><span class="sxs-lookup"><span data-stu-id="bd5a9-174">Examples</span></span>

- <span data-ttu-id="bd5a9-175">Erstellt ein Projekt und seine Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="bd5a9-175">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet build
  ```

- <span data-ttu-id="bd5a9-176">Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="bd5a9-176">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet build --configuration Release
  ```

- <span data-ttu-id="bd5a9-177">Erstellt ein Projekt und seine Abhängigkeiten für eine bestimmte Laufzeit (in diesem Beispiel Ubuntu 18.04):</span><span class="sxs-lookup"><span data-stu-id="bd5a9-177">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 18.04):</span></span>

  ```dotnetcli
  dotnet build --runtime ubuntu.18.04-x64
  ```

- <span data-ttu-id="bd5a9-178">Erstellt ein Projekt und verwendet die angegebene NuGet-Paketquelle während des Wiederherstellungsvorgangs (.NET Core 2.0 SDK und spätere Versionen):</span><span class="sxs-lookup"><span data-stu-id="bd5a9-178">Build the project and use the specified NuGet package source during the restore operation (.NET Core 2.0 SDK and later versions):</span></span>

  ```dotnetcli
  dotnet build --source c:\packages\mypackages
  ```

- <span data-ttu-id="bd5a9-179">Erstellen Sie das Projekt, und legen Sie Version 1.2.3.4 als Buildparameter mithilfe der `-p` [MSBuild-Option](#msbuild) fest:</span><span class="sxs-lookup"><span data-stu-id="bd5a9-179">Build the project and set version 1.2.3.4 as a build parameter using the `-p` [MSBuild option](#msbuild):</span></span>

  ```dotnetcli
  dotnet build -p:Version=1.2.3.4
  ```
