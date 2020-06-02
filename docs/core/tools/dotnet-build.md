---
title: Befehl „dotnet build“
description: Der dotnet build-Befehl erstellt ein Projekt und alle seine Abhängigkeiten.
ms.date: 02/14/2020
ms.openlocfilehash: 5375df61dbf8e9b4db8772b0e2767e9bca0bb254
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "83840909"
---
# <a name="dotnet-build"></a><span data-ttu-id="d2a58-103">dotnet build</span><span class="sxs-lookup"><span data-stu-id="d2a58-103">dotnet build</span></span>

<span data-ttu-id="d2a58-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="d2a58-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="d2a58-105">name</span><span class="sxs-lookup"><span data-stu-id="d2a58-105">Name</span></span>

<span data-ttu-id="d2a58-106">`dotnet build`: Erstellt ein Projekt und alle seine Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="d2a58-106">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d2a58-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d2a58-107">Synopsis</span></span>

```dotnetcli
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [-f|--framework <FRAMEWORK>] [--force] [--interactive] [--no-dependencies]
    [--no-incremental] [--no-restore] [--nologo] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--runtime <RUNTIME_IDENTIFIER>] [-s|--source <SOURCE>]
    [-v|--verbosity <LEVEL>] [--version-suffix <VERSION_SUFFIX>]

dotnet build -h|--help
```

## <a name="description"></a><span data-ttu-id="d2a58-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2a58-108">Description</span></span>

<span data-ttu-id="d2a58-109">Der `dotnet build`-Befehl erstellt das Projekt und die zugehörigen Abhängigkeiten in einen Satz von Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="d2a58-109">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="d2a58-110">Die Binärdateien enthalten den Projektcode in IL-Dateien (Intermediate Language) mit der Erweiterung *DLL*.</span><span class="sxs-lookup"><span data-stu-id="d2a58-110">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension.</span></span>  <span data-ttu-id="d2a58-111">Abhängig vom Projekttyp und den Einstellungen können auch andere Dateien enthalten sein, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="d2a58-111">Depending on the project type and settings, other files may be included, such as:</span></span>

- <span data-ttu-id="d2a58-112">Eine ausführbare Datei, die zum Ausführen der Anwendung verwendet werden kann, wenn der Projekttyp eine ausführbare Datei für .NET Core 3.0 oder höher ist.</span><span class="sxs-lookup"><span data-stu-id="d2a58-112">An executable that can be used to run the application, if the project type is an executable targeting .NET Core 3.0 or later.</span></span>
- <span data-ttu-id="d2a58-113">Symboldateien mit der Erweiterung *PDB*, die für das Debuggen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d2a58-113">Symbol files used for debugging with a *.pdb* extension.</span></span>
- <span data-ttu-id="d2a58-114">Eine Datei *.deps.json*, die die Abhängigkeiten der Anwendung oder Bibliothek auflistet.</span><span class="sxs-lookup"><span data-stu-id="d2a58-114">A *.deps.json* file, which lists the dependencies of the application or library.</span></span>
- <span data-ttu-id="d2a58-115">Eine Datei *.runtimeconfig.json*, die die freigegebene Laufzeit und deren Version für eine Anwendung angibt.</span><span class="sxs-lookup"><span data-stu-id="d2a58-115">A *.runtimeconfig.json* file, which specifies the shared runtime and its version for an application.</span></span>
- <span data-ttu-id="d2a58-116">Andere Bibliotheken, von denen das Projekt abhängig ist (über Projektverweise oder NuGet-Paketverweise).</span><span class="sxs-lookup"><span data-stu-id="d2a58-116">Other libraries that the project depends on (via project references or NuGet package references).</span></span>

<span data-ttu-id="d2a58-117">Bei ausführbaren Projekten für frühere Versionen als .NET Core 3.0 werden Bibliotheksabhängigkeiten von NuGet in der Regel NICHT in den Ausgabeordner kopiert.</span><span class="sxs-lookup"><span data-stu-id="d2a58-117">For executable projects targeting versions earlier than .NET Core 3.0, library dependencies from NuGet are typically NOT copied to the output folder.</span></span>  <span data-ttu-id="d2a58-118">Sie werden zur Laufzeit aus dem NuGet-Ordner für globale Pakete aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="d2a58-118">They're resolved from the NuGet global packages folder at run time.</span></span> <span data-ttu-id="d2a58-119">Bedenken Sie, dass das Produkt von `dotnet build` nicht auf einen anderen Computer zur Ausführung übertragen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d2a58-119">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="d2a58-120">Zum Erstellen einer Version der Anwendung, die bereitgestellt werden kann, müssen Sie sie veröffentlichen (z.B. mit dem Befehl [dotnet publish](dotnet-publish.md)).</span><span class="sxs-lookup"><span data-stu-id="d2a58-120">To create a version of the application that can be deployed, you need to publish it (for example, with the [dotnet publish](dotnet-publish.md) command).</span></span> <span data-ttu-id="d2a58-121">Weitere Informationen finden Sie unter [.NET Core Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="d2a58-121">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="d2a58-122">Bei ausführbaren Projekten für .NET Core 3.0 oder höher werden Bibliotheksabhängigkeiten in den Ausgabeordner kopiert.</span><span class="sxs-lookup"><span data-stu-id="d2a58-122">For executable projects targeting .NET Core 3.0 and later, library dependencies are copied to the output folder.</span></span> <span data-ttu-id="d2a58-123">Dies bedeutet, dass die Buildausgabe bereitstellbar sein sollte, wenn keine andere veröffentlichungsspezifische Logik (wie bei Webprojekten) vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d2a58-123">This means that if there isn't any other publish-specific logic (such as Web projects have), the build output should be deployable.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="d2a58-124">Implizite Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="d2a58-124">Implicit restore</span></span>

<span data-ttu-id="d2a58-125">Das Erstellen erfordert die *project.assets.json*-Datei, die die Abhängigkeiten Ihrer Anwendung aufführt.</span><span class="sxs-lookup"><span data-stu-id="d2a58-125">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="d2a58-126">Die Datei wird erstellt, wenn [`dotnet restore`](dotnet-restore.md) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d2a58-126">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="d2a58-127">Ohne die vorhandenen Ressourcendateien kann das Tool die Verweisassemblys nicht auflösen, was zu Fehlern führt.</span><span class="sxs-lookup"><span data-stu-id="d2a58-127">Without the assets file in place, the tooling can't resolve reference assemblies, which results in errors.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

### <a name="executable-or-library-output"></a><span data-ttu-id="d2a58-128">Ausgabe der ausführbaren Datei oder Bibliothek</span><span class="sxs-lookup"><span data-stu-id="d2a58-128">Executable or library output</span></span>

<span data-ttu-id="d2a58-129">Ob das Projekt ausführbar ist oder nicht, richtet sich nach der `<OutputType>`-Eigenschaft in der Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="d2a58-129">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="d2a58-130">Das folgende Beispiel zeigt ein Projekt, das ausführbaren Code erzeugt:</span><span class="sxs-lookup"><span data-stu-id="d2a58-130">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="d2a58-131">Um eine Bibliothek zu generieren, lassen Sie die Eigenschaft `<OutputType>` weg, oder ändern Sie ihren Wert in `Library`.</span><span class="sxs-lookup"><span data-stu-id="d2a58-131">To produce a library, omit the `<OutputType>` property or change its value to `Library`.</span></span> <span data-ttu-id="d2a58-132">Die IL-DLL für eine Bibliothek enthält keine Einstiegspunkte und kann nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d2a58-132">The IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

### <a name="msbuild"></a><span data-ttu-id="d2a58-133">MSBuild</span><span class="sxs-lookup"><span data-stu-id="d2a58-133">MSBuild</span></span>

<span data-ttu-id="d2a58-134">`dotnet build` verwendet MSBuild zum Erstellen des Projekts und unterstützt daher parallele und inkrementelle Builds.</span><span class="sxs-lookup"><span data-stu-id="d2a58-134">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="d2a58-135">Weitere Informationen finden Sie unter [Incremental Builds](/visualstudio/msbuild/incremental-builds) (Inkrementelle Builds).</span><span class="sxs-lookup"><span data-stu-id="d2a58-135">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="d2a58-136">Zusätzlich zu diesen Optionen akzeptiert der `dotnet build`-Befehl MSBuild-Optionen, wie z.B. `-p` zum Festlegen von Eigenschaften oder `-l` zum Definieren eines Protokolls.</span><span class="sxs-lookup"><span data-stu-id="d2a58-136">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `-p` for setting properties or `-l` to define a logger.</span></span> <span data-ttu-id="d2a58-137">Weitere Informationen zu diesen Optionen finden Sie in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="d2a58-137">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="d2a58-138">Sie können auch den Befehl [dotnet msbuild](dotnet-msbuild.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="d2a58-138">Or you can also use the [dotnet msbuild](dotnet-msbuild.md) command.</span></span>

<span data-ttu-id="d2a58-139">Das Ausführen von `dotnet build` entspricht der Ausführung von `dotnet msbuild -restore`. Die Standardausführlichkeit der Ausgabe unterscheidet sich jedoch.</span><span class="sxs-lookup"><span data-stu-id="d2a58-139">Running `dotnet build` is equivalent to running `dotnet msbuild -restore`; however, the default verbosity of the output is different.</span></span>

## <a name="arguments"></a><span data-ttu-id="d2a58-140">Argumente</span><span class="sxs-lookup"><span data-stu-id="d2a58-140">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="d2a58-141">Die zu erstellende Projekt- oder Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="d2a58-141">The project or solution file to build.</span></span> <span data-ttu-id="d2a58-142">Wenn Sie keine Projekt- oder Projektmappendatei angeben, durchsucht MSBuild das aktuelle Arbeitsverzeichnis nach einer Dateierweiterung, die mit *proj* oder *sln* endet, und verwendet diese.</span><span class="sxs-lookup"><span data-stu-id="d2a58-142">If a project or solution file isn't specified, MSBuild searches the current working directory for a file that has a file extension that ends in either *proj* or *sln* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="d2a58-143">Optionen</span><span class="sxs-lookup"><span data-stu-id="d2a58-143">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="d2a58-144">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="d2a58-144">Defines the build configuration.</span></span> <span data-ttu-id="d2a58-145">Der Standardwert für die meisten Projekte ist `Debug`, aber Sie können die Buildkonfigurationseinstellungen in Ihrem Projekt überschreiben.</span><span class="sxs-lookup"><span data-stu-id="d2a58-145">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d2a58-146">Kompiliert für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d2a58-146">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="d2a58-147">Das Framework muss in der [Projektdatei](csproj.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="d2a58-147">The framework must be defined in the [project file](csproj.md).</span></span>

- **`--force`**

  <span data-ttu-id="d2a58-148">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="d2a58-148">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="d2a58-149">Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="d2a58-149">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="d2a58-150">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="d2a58-150">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="d2a58-151">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten.</span><span class="sxs-lookup"><span data-stu-id="d2a58-151">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="d2a58-152">Beispielsweise, um die Authentifizierung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d2a58-152">For example, to complete authentication.</span></span> <span data-ttu-id="d2a58-153">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="d2a58-153">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="d2a58-154">Ignoriert Verweise zwischen Projekten (P2P) und erstellt nur das angegebene Stammprojekt.</span><span class="sxs-lookup"><span data-stu-id="d2a58-154">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

- **`--no-incremental`**

  <span data-ttu-id="d2a58-155">Markiert den Build als unsicher für inkrementelle Builds.</span><span class="sxs-lookup"><span data-stu-id="d2a58-155">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="d2a58-156">Das Flag deaktiviert die inkrementelle Kompilierung und erzwingt eine komplette Neuerstellung des Abhängigkeitsdiagramms des Projekts.</span><span class="sxs-lookup"><span data-stu-id="d2a58-156">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

- **`--no-restore`**

  <span data-ttu-id="d2a58-157">Führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="d2a58-157">Doesn't execute an implicit restore during build.</span></span>

- **`--nologo`**

  <span data-ttu-id="d2a58-158">Unterdrückt die Anzeige von Startbanner und Copyrightmeldung.</span><span class="sxs-lookup"><span data-stu-id="d2a58-158">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="d2a58-159">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="d2a58-159">Available since .NET Core 3.0 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="d2a58-160">Verzeichnis, in dem die erstellten Binärdateien platziert werden.</span><span class="sxs-lookup"><span data-stu-id="d2a58-160">Directory in which to place the built binaries.</span></span> <span data-ttu-id="d2a58-161">Wenn nicht angegeben, ist der Standardpfad `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="d2a58-161">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="d2a58-162">Bei Projekten mit mehreren Zielframeworks (über die `TargetFrameworks`-Eigenschaft) müssen Sie auch `--framework` definieren, wenn Sie diese Option angeben.</span><span class="sxs-lookup"><span data-stu-id="d2a58-162">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="d2a58-163">Legt die Ziellaufzeit fest.</span><span class="sxs-lookup"><span data-stu-id="d2a58-163">Specifies the target runtime.</span></span> <span data-ttu-id="d2a58-164">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="d2a58-164">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="d2a58-165">Der URI der NuGet-Paketquelle, die während des Wiederherstellungsvorgangs zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="d2a58-165">The URI of the NuGet package source to use during the restore operation.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="d2a58-166">Legt den MSBuild-Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="d2a58-166">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="d2a58-167">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d2a58-167">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="d2a58-168">Der Standardwert ist `minimal`.</span><span class="sxs-lookup"><span data-stu-id="d2a58-168">The default is `minimal`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="d2a58-169">Hiermit wird der Wert der `$(VersionSuffix)`-Eigenschaft festgelegt, die beim Erstellen des Projekts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d2a58-169">Sets the value of the `$(VersionSuffix)` property to use when building the project.</span></span> <span data-ttu-id="d2a58-170">Dies funktioniert nur, wenn die `$(Version)`-Eigenschaft nicht festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d2a58-170">This only works if the `$(Version)` property isn't set.</span></span> <span data-ttu-id="d2a58-171">Dann wird `$(Version)` auf `$(VersionPrefix)` festgelegt, kombiniert mit dem `$(VersionSuffix)`, getrennt durch einen Bindestrich.</span><span class="sxs-lookup"><span data-stu-id="d2a58-171">Then, `$(Version)` is set to the `$(VersionPrefix)` combined with the `$(VersionSuffix)`, separated by a dash.</span></span>

## <a name="examples"></a><span data-ttu-id="d2a58-172">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d2a58-172">Examples</span></span>

- <span data-ttu-id="d2a58-173">Erstellt ein Projekt und seine Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="d2a58-173">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet build
  ```

- <span data-ttu-id="d2a58-174">Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="d2a58-174">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet build --configuration Release
  ```

- <span data-ttu-id="d2a58-175">Erstellt ein Projekt und seine Abhängigkeiten für eine bestimmte Laufzeit (in diesem Beispiel Ubuntu 18.04):</span><span class="sxs-lookup"><span data-stu-id="d2a58-175">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 18.04):</span></span>

  ```dotnetcli
  dotnet build --runtime ubuntu.18.04-x64
  ```

- <span data-ttu-id="d2a58-176">Erstellt ein Projekt und verwendet die angegebene NuGet-Paketquelle während des Wiederherstellungsvorgangs (.NET Core 2.0 SDK und spätere Versionen):</span><span class="sxs-lookup"><span data-stu-id="d2a58-176">Build the project and use the specified NuGet package source during the restore operation (.NET Core 2.0 SDK and later versions):</span></span>

  ```dotnetcli
  dotnet build --source c:\packages\mypackages
  ```

- <span data-ttu-id="d2a58-177">Erstellen eines Projekts und festlegen der Version 1.2.3.4 als Buildparameter mithilfe der `-p`[MSBuild-Option](#msbuild):</span><span class="sxs-lookup"><span data-stu-id="d2a58-177">Build the project and set version 1.2.3.4 as a build parameter using the `-p` [MSBuild option](#msbuild):</span></span>

  ```dotnetcli
  dotnet build -p:Version=1.2.3.4
  ```
