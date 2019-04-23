---
title: Befehl „dotnet build“
description: Der dotnet build-Befehl erstellt ein Projekt und alle seine Abhängigkeiten.
ms.date: 12/04/2018
ms.openlocfilehash: 6a701ee371221c780a878e64b996df95f709371f
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612692"
---
# <a name="dotnet-build"></a><span data-ttu-id="246df-103">dotnet build</span><span class="sxs-lookup"><span data-stu-id="246df-103">dotnet build</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="246df-104">name</span><span class="sxs-lookup"><span data-stu-id="246df-104">Name</span></span>

<span data-ttu-id="246df-105">`dotnet build`: Erstellt ein Projekt und alle seine Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="246df-105">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="246df-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="246df-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="246df-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="246df-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--force] [--no-dependencies] [--no-incremental]
    [--no-restore] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="246df-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="246df-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--no-dependencies] [--no-incremental] [-o|--output]
    [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="246df-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="246df-109">Description</span></span>

<span data-ttu-id="246df-110">Der `dotnet build`-Befehl erstellt das Projekt und die zugehörigen Abhängigkeiten in einen Satz von Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="246df-110">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="246df-111">Die Binärdateien enthalten den Projektcode in Intermediate Language-Dateien (IL) mit einer *.dll*-Erweiterung und Symboldateien, die zum Debuggen mit einer *.pdb*-Erweiterung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="246df-111">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension and symbol files used for debugging with a *.pdb* extension.</span></span> <span data-ttu-id="246df-112">Eine JSON-Datei für Abhängigkeiten (*\*.deps.json*) wird erstellt, die Abhängigkeiten der Anwendung aufführt.</span><span class="sxs-lookup"><span data-stu-id="246df-112">A dependencies JSON file (*\*.deps.json*) is produced that lists the dependencies of the application.</span></span> <span data-ttu-id="246df-113">Eine *\*.runtimeconfig.json*-Datei wird erstellt, die die gemeinsam genutzte Laufzeit und deren Version für die Anwendung anzeigt.</span><span class="sxs-lookup"><span data-stu-id="246df-113">A *\*.runtimeconfig.json* file is produced, which specifies the shared runtime and its version for the application.</span></span>

<span data-ttu-id="246df-114">Verfügt das Projekt über Abhängigkeiten von Drittanbietern, z.B. Bibliotheken von NuGet, werden diese aus dem NuGet-Cache aufgelöst und sind nicht mit der Buildausgabe des Projekts verfügbar.</span><span class="sxs-lookup"><span data-stu-id="246df-114">If the project has third-party dependencies, such as libraries from NuGet, they're resolved from the NuGet cache and aren't available with the project's built output.</span></span> <span data-ttu-id="246df-115">Bedenken Sie, dass das Produkt von `dotnet build` nicht auf einen anderen Computer zur Ausführung übertragen werden kann.</span><span class="sxs-lookup"><span data-stu-id="246df-115">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="246df-116">Dies unterscheidet sich zum Verhalten des .NET Framework, bei dem die Erstellung eines ausführbaren Projekts (eine Anwendung) eine Ausgabe erzeugt, die auf jedem Computer ausgeführt werden kann, auf dem .NET Framework installiert ist.</span><span class="sxs-lookup"><span data-stu-id="246df-116">This is in contrast to the behavior of the .NET Framework in which building an executable project (an application) produces output that's runnable on any machine where the .NET Framework is installed.</span></span> <span data-ttu-id="246df-117">Um ein ähnliches Verhalten mit .NET Core zu erhalten, müssen Sie den Befehl [dotnet publish](dotnet-publish.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="246df-117">To have a similar experience with .NET Core, you need to use the [dotnet publish](dotnet-publish.md) command.</span></span> <span data-ttu-id="246df-118">Weitere Informationen finden Sie unter [.NET Core Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="246df-118">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="246df-119">Das Erstellen erfordert die *project.assets.json*-Datei, die die Abhängigkeiten Ihrer Anwendung aufführt.</span><span class="sxs-lookup"><span data-stu-id="246df-119">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="246df-120">Die Datei wird erstellt, wenn [`dotnet restore`](dotnet-restore.md) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="246df-120">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="246df-121">Ohne die vorhandenen Ressourcendateien kann das Tool die Verweisassemblys nicht auflösen, was zu Fehlern führt.</span><span class="sxs-lookup"><span data-stu-id="246df-121">Without the assets file in place, the tooling cannot resolve reference assemblies, which results in errors.</span></span> <span data-ttu-id="246df-122">Mit dem .NET Core 1.x SDK müssen Sie `dotnet restore` explizit ausführen, bevor Sie `dotnet build` ausführen.</span><span class="sxs-lookup"><span data-stu-id="246df-122">With .NET Core 1.x SDK, you needed to explicitly run the `dotnet restore` before running `dotnet build`.</span></span> <span data-ttu-id="246df-123">Ab dem .NET Core 2.0 SDK wird `dotnet restore` implizit ausgeführt, wenn Sie `dotnet build` ausführen.</span><span class="sxs-lookup"><span data-stu-id="246df-123">Starting with .NET Core 2.0 SDK, `dotnet restore` runs implicitly when you run `dotnet build`.</span></span> <span data-ttu-id="246df-124">Wenn Sie das implizite Wiederherstellen deaktivieren möchten, wenn Sie den Buildbefehl ausführen, können Sie die `--no-restore`-Option übergeben.</span><span class="sxs-lookup"><span data-stu-id="246df-124">If you want to disable implicit restore when running the build command, you can pass the `--no-restore` option.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

<span data-ttu-id="246df-125">Ob das Projekt ausführbar ist oder nicht, richtet sich nach der `<OutputType>`-Eigenschaft in der Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="246df-125">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="246df-126">Das folgende Beispiel zeigt ein Projekt, das ausführbaren Code erzeugt:</span><span class="sxs-lookup"><span data-stu-id="246df-126">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="246df-127">Lassen Sie die `<OutputType>`-Eigenschaft weg, um eine Bibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="246df-127">In order to produce a library, omit the `<OutputType>` property.</span></span> <span data-ttu-id="246df-128">Der Hauptunterschied in der Buildausgabe ist, dass die IL-DLL für eine Bibliothek keine Einstiegspunkte enthält und nicht ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="246df-128">The main difference in built output is that the IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

### <a name="msbuild"></a><span data-ttu-id="246df-129">MSBuild</span><span class="sxs-lookup"><span data-stu-id="246df-129">MSBuild</span></span>

<span data-ttu-id="246df-130">`dotnet build` verwendet MSBuild zum Erstellen des Projekts und unterstützt daher parallele und inkrementelle Builds.</span><span class="sxs-lookup"><span data-stu-id="246df-130">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="246df-131">Weitere Informationen finden Sie unter [Incremental Builds](/visualstudio/msbuild/incremental-builds) (Inkrementelle Builds).</span><span class="sxs-lookup"><span data-stu-id="246df-131">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="246df-132">Zusätzlich zu diesen Optionen akzeptiert der `dotnet build`-Befehl MSBuild-Optionen, wie z.B. `-p` zum Festlegen von Eigenschaften oder `-l` zum Definieren eines Protokolls.</span><span class="sxs-lookup"><span data-stu-id="246df-132">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `-p` for setting properties or `-l` to define a logger.</span></span> <span data-ttu-id="246df-133">Weitere Informationen zu diesen Optionen finden Sie in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="246df-133">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="246df-134">Sie können auch den Befehl [dotnet msbuild](dotnet-msbuild.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="246df-134">Or you can also use the [dotnet msbuild](dotnet-msbuild.md) command.</span></span>

<span data-ttu-id="246df-135">Die Ausführung von `dotnet build` entspricht `dotnet msbuild -restore -target:Build`.</span><span class="sxs-lookup"><span data-stu-id="246df-135">Running `dotnet build` is equivalent to `dotnet msbuild -restore -target:Build`.</span></span>

## <a name="arguments"></a><span data-ttu-id="246df-136">Argumente</span><span class="sxs-lookup"><span data-stu-id="246df-136">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="246df-137">Die zu erstellende Projekt- oder Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="246df-137">The project or solution file to build.</span></span> <span data-ttu-id="246df-138">Wenn Sie kein Projekt- oder Projektmappendatei angeben, durchsucht MSBuild das aktuelle Arbeitsverzeichnis nach einer Dateierweiterung, die mit *proj* oder *sln* endet, und verwendet diese.</span><span class="sxs-lookup"><span data-stu-id="246df-138">If a project or solution file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in either *proj* or *sln* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="246df-139">Optionen</span><span class="sxs-lookup"><span data-stu-id="246df-139">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="246df-140">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="246df-140">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="246df-141">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="246df-141">Defines the build configuration.</span></span> <span data-ttu-id="246df-142">Der Standardwert ist `Debug`sein.</span><span class="sxs-lookup"><span data-stu-id="246df-142">The default value is `Debug`.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="246df-143">Kompiliert für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="246df-143">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="246df-144">Das Framework muss in der [Projektdatei](csproj.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="246df-144">The framework must be defined in the [project file](csproj.md).</span></span>

* **`--force`**

  <span data-ttu-id="246df-145">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="246df-145">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="246df-146">Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="246df-146">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

* **`-h|--help`**

  <span data-ttu-id="246df-147">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="246df-147">Prints out a short help for the command.</span></span>

* **`--no-dependencies`**

  <span data-ttu-id="246df-148">Ignoriert Verweise zwischen Projekten (P2P) und erstellt nur das angegebene Stammprojekt.</span><span class="sxs-lookup"><span data-stu-id="246df-148">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

* **`--no-incremental`**

  <span data-ttu-id="246df-149">Markiert den Build als unsicher für inkrementelle Builds.</span><span class="sxs-lookup"><span data-stu-id="246df-149">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="246df-150">Das Flag deaktiviert die inkrementelle Kompilierung und erzwingt eine komplette Neuerstellung des Abhängigkeitsdiagramms des Projekts.</span><span class="sxs-lookup"><span data-stu-id="246df-150">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

* **`--no-restore`**

  <span data-ttu-id="246df-151">Führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="246df-151">Doesn't execute an implicit restore during build.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="246df-152">Verzeichnis, in dem die erstellten Binärdateien platziert werden.</span><span class="sxs-lookup"><span data-stu-id="246df-152">Directory in which to place the built binaries.</span></span> <span data-ttu-id="246df-153">Sie müssen außerdem `--framework` definieren, wenn Sie diese Option angeben.</span><span class="sxs-lookup"><span data-stu-id="246df-153">You also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="246df-154">Wenn nicht angegeben, ist der Standardpfad `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="246df-154">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="246df-155">Legt die Ziellaufzeit fest.</span><span class="sxs-lookup"><span data-stu-id="246df-155">Specifies the target runtime.</span></span> <span data-ttu-id="246df-156">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="246df-156">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="246df-157">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="246df-157">Sets the verbosity level of the command.</span></span> <span data-ttu-id="246df-158">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="246df-158">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="246df-159">Definiert das Versionssuffix für ein Sternchen (`*`) im Versionsfeld der Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="246df-159">Defines the version suffix for an asterisk (`*`) in the version field of the project file.</span></span> <span data-ttu-id="246df-160">Das Format entspricht den NuGet-Versionsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="246df-160">The format follows NuGet's version guidelines.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="246df-161">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="246df-161">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="246df-162">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="246df-162">Defines the build configuration.</span></span> <span data-ttu-id="246df-163">Der Standardwert ist `Debug`sein.</span><span class="sxs-lookup"><span data-stu-id="246df-163">The default value is `Debug`.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="246df-164">Kompiliert für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="246df-164">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="246df-165">Das Framework muss in der [Projektdatei](csproj.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="246df-165">The framework must be defined in the [project file](csproj.md).</span></span>

* **`-h|--help`**

  <span data-ttu-id="246df-166">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="246df-166">Prints out a short help for the command.</span></span>

* **`--no-dependencies`**

  <span data-ttu-id="246df-167">Ignoriert Verweise zwischen Projekten (P2P) und erstellt nur das angegebene Stammprojekt.</span><span class="sxs-lookup"><span data-stu-id="246df-167">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

* **`--no-incremental`**

  <span data-ttu-id="246df-168">Markiert den Build als unsicher für inkrementelle Builds.</span><span class="sxs-lookup"><span data-stu-id="246df-168">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="246df-169">Das Flag deaktiviert die inkrementelle Kompilierung und erzwingt eine komplette Neuerstellung des Abhängigkeitsdiagramms des Projekts.</span><span class="sxs-lookup"><span data-stu-id="246df-169">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="246df-170">Verzeichnis, in dem die erstellten Binärdateien platziert werden.</span><span class="sxs-lookup"><span data-stu-id="246df-170">Directory in which to place the built binaries.</span></span> <span data-ttu-id="246df-171">Sie müssen außerdem `--framework` definieren, wenn Sie diese Option angeben.</span><span class="sxs-lookup"><span data-stu-id="246df-171">You also need to define `--framework` when you specify this option.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="246df-172">Legt die Ziellaufzeit fest.</span><span class="sxs-lookup"><span data-stu-id="246df-172">Specifies the target runtime.</span></span> <span data-ttu-id="246df-173">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="246df-173">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="246df-174">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="246df-174">Sets the verbosity level of the command.</span></span> <span data-ttu-id="246df-175">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="246df-175">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="246df-176">Definiert das Versionssuffix für ein Sternchen (`*`) im Versionsfeld der Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="246df-176">Defines the version suffix for an asterisk (`*`) in the version field of the project file.</span></span> <span data-ttu-id="246df-177">Das Format entspricht den NuGet-Versionsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="246df-177">The format follows NuGet's version guidelines.</span></span>

---

## <a name="examples"></a><span data-ttu-id="246df-178">Beispiele</span><span class="sxs-lookup"><span data-stu-id="246df-178">Examples</span></span>

* <span data-ttu-id="246df-179">Erstellt ein Projekt und seine Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="246df-179">Build a project and its dependencies:</span></span>

  ```console
  dotnet build
  ```

* <span data-ttu-id="246df-180">Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="246df-180">Build a project and its dependencies using Release configuration:</span></span>

  ```console
  dotnet build --configuration Release
  ```

* <span data-ttu-id="246df-181">Erstellt ein Projekt und seine Abhängigkeiten für eine bestimmte Laufzeit (in diesem Beispiel Ubuntu 16.04):</span><span class="sxs-lookup"><span data-stu-id="246df-181">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 16.04):</span></span>

  ```console
  dotnet build --runtime ubuntu.16.04-x64
  ```

* <span data-ttu-id="246df-182">Erstellt ein Projekt und verwendet die angegebene NuGet-Paketquelle während des Wiederherstellungsvorgangs (.NET Core 2.0 SDK und spätere Versionen):</span><span class="sxs-lookup"><span data-stu-id="246df-182">Build the project and use the specified NuGet package source during the restore operation (.NET Core 2.0 SDK and later versions):</span></span>

  ```console
  dotnet build --source c:\packages\mypackages
  ```

* <span data-ttu-id="246df-183">Erstellen Sie das Projekt, und legen Sie die 1.2.3.4-Version als Buildparameter fest:</span><span class="sxs-lookup"><span data-stu-id="246df-183">Build the project and set 1.2.3.4 version as a build parameter:</span></span>

  ```console
  dotnet build -p:Version=1.2.3.4
  ```