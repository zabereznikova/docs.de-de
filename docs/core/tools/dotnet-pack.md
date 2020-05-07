---
title: Befehl „dotnet pack“
description: Der dotnet pack-Befehl erstellt NuGet-Pakete für ein .NET Core-Projekt.
ms.date: 04/28/2020
ms.openlocfilehash: 26a8581f55a8dc9e61aa52e62ed94c73eefd3e03
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595753"
---
# <a name="dotnet-pack"></a><span data-ttu-id="b0fd4-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="b0fd4-103">dotnet pack</span></span>

<span data-ttu-id="b0fd4-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="b0fd4-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="b0fd4-105">name</span><span class="sxs-lookup"><span data-stu-id="b0fd4-105">Name</span></span>

<span data-ttu-id="b0fd4-106">`dotnet pack`: Packt den Code in ein NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="b0fd4-106">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b0fd4-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="b0fd4-107">Synopsis</span></span>

```dotnetcli
dotnet pack [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [--force] [--include-source] [--include-symbols] [--interactive]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output <OUTPUT_DIRECTORY>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--serviceable] [-v|--verbosity <LEVEL>]
    [--version-suffix <VERSION_SUFFIX>]

dotnet pack -h|--help
```

## <a name="description"></a><span data-ttu-id="b0fd4-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0fd4-108">Description</span></span>

<span data-ttu-id="b0fd4-109">Der Befehl `dotnet pack` erstellt das Projekt und NuGet-Pakete.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-109">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="b0fd4-110">Das Ergebnis dieses Befehls ist ein NuGet-Paket (d. h., eine *NUPKG*-Datei).</span><span class="sxs-lookup"><span data-stu-id="b0fd4-110">The result of this command is a NuGet package (that is, a *.nupkg* file).</span></span>

<span data-ttu-id="b0fd4-111">Wenn Sie ein Paket generieren möchten, das die Debugsymbole enthält, stehen Ihnen zwei Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="b0fd4-111">If you want to generate a package that contains the debug symbols, you have two options available:</span></span>

- <span data-ttu-id="b0fd4-112">`--include-symbols`: Es erstellt das Symbolpaket.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-112">`--include-symbols` - it creates the symbols package.</span></span>
- <span data-ttu-id="b0fd4-113">`--include-source`: Es erstellt das Symbolpaket mit einem `src`-Ordner, der die Quelldateien enthält.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-113">`--include-source` - it creates the symbols package with a `src` folder inside containing the source files.</span></span>

<span data-ttu-id="b0fd4-114">NuGet-Abhängigkeiten des gepackten Projekts werden der Datei *nuspec* hinzugefügt. Sie werden ordnungsgemäß aufgelöst, wenn das Paket installiert wird.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-114">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="b0fd4-115">Verweise zwischen Projekten werden innerhalb des Projekts nicht gepackt.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-115">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="b0fd4-116">Derzeit benötigen Sie ein Paket pro Projekt, wenn Sie Abhängigkeiten zwischen Projekten haben.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-116">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="b0fd4-117">`dotnet pack` erstellt standardmäßig zuerst das Projekt.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-117">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="b0fd4-118">Wenn Sie dieses Verhalten vermeiden möchten, übergeben Sie die Option `--no-build`.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-118">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="b0fd4-119">Diese Option ist bei Buildszenarios der Continuous Integration (CI) oft hilfreich, bei denen Sie wissen, dass der Code kürzlich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-119">This option is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

> [!NOTE]
> <span data-ttu-id="b0fd4-120">In einigen Fällen kann die implizierte Kompilierung nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-120">In some cases, the implicit build cannot be performed.</span></span> <span data-ttu-id="b0fd4-121">Dies kann passieren, wenn `GeneratePackageOnBuild` festgelegt ist, um eine zyklische Abhängigkeit zwischen Build und Paketzielen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-121">This can occur when `GeneratePackageOnBuild` is set, to avoid a cyclic dependency between build and pack targets.</span></span> <span data-ttu-id="b0fd4-122">Die Kompilierung kann auch fehlschlagen, wenn eine gesperrte Datei oder ein anderes Problem vorliegt.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-122">The build can also fail if there is a locked file or other issue.</span></span>

<span data-ttu-id="b0fd4-123">Sie können dem `dotnet pack`-Befehl MSBuild-Eigenschaften für den Packvorgang bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-123">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="b0fd4-124">Weitere Informationen finden Sie in den [NuGet-Metadateneigenschaften](csproj.md#nuget-metadata-properties) und in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="b0fd4-124">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="b0fd4-125">Der Abschnitt [Beispiele](#examples) enthält Informationen darüber, wie der MSBuild-Schalter „-p“ für verschiedene Szenarien verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-125">The [Examples](#examples) section shows how to use the MSBuild -p switch for a couple of different scenarios.</span></span>

<span data-ttu-id="b0fd4-126">Webprojekte können standardmäßig nicht verpackt werden.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-126">Web projects aren't packable by default.</span></span> <span data-ttu-id="b0fd4-127">Um das Standardverhalten zu überschreiben, fügen Sie Ihrer *.csproj*-Datei die folgende Eigenschaft hinzu:</span><span class="sxs-lookup"><span data-stu-id="b0fd4-127">To override the default behavior, add the following property to your *.csproj* file:</span></span>

```xml
<PropertyGroup>
   <IsPackable>true</IsPackable>
</PropertyGroup>
```

### <a name="implicit-restore"></a><span data-ttu-id="b0fd4-128">Implizite Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="b0fd4-128">Implicit restore</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="b0fd4-129">Argumente</span><span class="sxs-lookup"><span data-stu-id="b0fd4-129">Arguments</span></span>

`PROJECT | SOLUTION`

  <span data-ttu-id="b0fd4-130">Das Projekt oder die Projektmappe, die gepackt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-130">The project or solution to pack.</span></span> <span data-ttu-id="b0fd4-131">Es ist entweder ein Pfad zu einer [CSPROJ-Datei](csproj.md), einer Projektmappendatei oder zu einem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-131">It's either a path to a [csproj file](csproj.md), a solution file, or to a directory.</span></span> <span data-ttu-id="b0fd4-132">Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einem Projekt oder einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-132">If not specified, the command searches the current directory for a project or solution file.</span></span>

## <a name="options"></a><span data-ttu-id="b0fd4-133">Optionen</span><span class="sxs-lookup"><span data-stu-id="b0fd4-133">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="b0fd4-134">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-134">Defines the build configuration.</span></span> <span data-ttu-id="b0fd4-135">Der Standardwert für die meisten Projekte ist `Debug`, aber Sie können die Buildkonfigurationseinstellungen in Ihrem Projekt überschreiben.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-135">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`--force`**

  <span data-ttu-id="b0fd4-136">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-136">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="b0fd4-137">Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-137">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="b0fd4-138">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-138">Prints out a short help for the command.</span></span>

- **`--include-source`**

  <span data-ttu-id="b0fd4-139">Schließt neben den regulären NuGet-Paketen im Ausgabeverzeichnis auch die NuGet-Pakete der Debugsymbole ein.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-139">Includes the debug symbols NuGet packages in addition to the regular NuGet packages in the output directory.</span></span> <span data-ttu-id="b0fd4-140">Die Quelldateien befinden sich im `src`-Ordner im Symbolpaket.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-140">The sources files are included in the `src` folder within the symbols package.</span></span>

- **`--include-symbols`**

  <span data-ttu-id="b0fd4-141">Schließt neben den regulären NuGet-Paketen im Ausgabeverzeichnis auch die NuGet-Pakete der Debugsymbole ein.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-141">Includes the debug symbols NuGet packages in addition to the regular NuGet packages in the output directory.</span></span>

- **`--interactive`**

  <span data-ttu-id="b0fd4-142">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen).</span><span class="sxs-lookup"><span data-stu-id="b0fd4-142">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="b0fd4-143">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-143">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-build`**

  <span data-ttu-id="b0fd4-144">Erstellt das Projekt nicht vor dem Packen.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-144">Doesn't build the project before packing.</span></span> <span data-ttu-id="b0fd4-145">Zudem wird das Flag `--no-restore` implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-145">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="b0fd4-146">Ignoriert Verweise zwischen Projekten und stellt nur das zum Erstellen angegebene Stammprojekt wieder her.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-146">Ignores project-to-project references and only restores the root project.</span></span>

- **`--no-restore`**

  <span data-ttu-id="b0fd4-147">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-147">Doesn't execute an implicit restore when running the command.</span></span>

- **`--nologo`**

  <span data-ttu-id="b0fd4-148">Unterdrückt die Anzeige von Startbanner und Copyrightmeldung.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-148">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="b0fd4-149">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-149">Available since .NET Core 3.0 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="b0fd4-150">Platziert die erstellten Pakete in das angegebene Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-150">Places the built packages in the directory specified.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="b0fd4-151">Gibt die Ziellaufzeit an, für die Pakete wiederhergestellt werden sollen</span><span class="sxs-lookup"><span data-stu-id="b0fd4-151">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="b0fd4-152">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="b0fd4-152">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

- **`-s|--serviceable`**

  <span data-ttu-id="b0fd4-153">Legt das zu verarbeitende Flag im Paket fest.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-153">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="b0fd4-154">Weitere Informationen finden Sie unter [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries (.NET Blog: .NET 4.5.1 unterstützt Microsoft Sicherheitsupdates für .NET NuGet-Bibliotheken)](https://aka.ms/nupkgservicing).</span><span class="sxs-lookup"><span data-stu-id="b0fd4-154">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="b0fd4-155">Definiert den Wert für die `$(VersionSuffix)`-MSBuild-Eigenschaft im Projekt.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-155">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="b0fd4-156">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-156">Sets the verbosity level of the command.</span></span> <span data-ttu-id="b0fd4-157">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-157">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="b0fd4-158">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b0fd4-158">Examples</span></span>

- <span data-ttu-id="b0fd4-159">Packt das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="b0fd4-159">Pack the project in the current directory:</span></span>

  ```dotnetcli
  dotnet pack
  ```

- <span data-ttu-id="b0fd4-160">Packt das `app1`-Projekt:</span><span class="sxs-lookup"><span data-stu-id="b0fd4-160">Pack the `app1` project:</span></span>

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj
  ```

- <span data-ttu-id="b0fd4-161">Packt das Projekt im aktuellen Verzeichnis, und platziert die erstellten Pakete in den `nupkgs`-Ordner:</span><span class="sxs-lookup"><span data-stu-id="b0fd4-161">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

  ```dotnetcli
  dotnet pack --output nupkgs
  ```

- <span data-ttu-id="b0fd4-162">Packt das Projekt im aktuellen Verzeichnis in den `nupkgs`-Ordner und überspringt den Buildschritt:</span><span class="sxs-lookup"><span data-stu-id="b0fd4-162">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

  ```dotnetcli
  dotnet pack --no-build --output nupkgs
  ```

- <span data-ttu-id="b0fd4-163">Mit dem Versionssuffix des Projekts, das als `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in der *.csproj*-Datei konfiguriert ist, packen Sie das aktuelle Projekt, und aktualisieren Sie die resultierende Paketversion mit dem angegebenen Suffix:</span><span class="sxs-lookup"><span data-stu-id="b0fd4-163">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

  ```dotnetcli
  dotnet pack --version-suffix "ci-1234"
  ```

- <span data-ttu-id="b0fd4-164">Legen Sie die Paketversion auf `2.1.0` mithilfe der MSBuild-Eigenschaft `PackageVersion` fest.</span><span class="sxs-lookup"><span data-stu-id="b0fd4-164">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

  ```dotnetcli
  dotnet pack -p:PackageVersion=2.1.0
  ```

- <span data-ttu-id="b0fd4-165">Packen Sie das Projekt für ein bestimmtes [Zielframework](../../standard/frameworks.md):</span><span class="sxs-lookup"><span data-stu-id="b0fd4-165">Pack the project for a specific [target framework](../../standard/frameworks.md):</span></span>

  ```dotnetcli
  dotnet pack -p:TargetFrameworks=net45
  ```

- <span data-ttu-id="b0fd4-166">Packen Sie das Projekt, und verwenden Sie eine bestimmte Runtime (Windows 10) für den Wiederherstellungsvorgang:</span><span class="sxs-lookup"><span data-stu-id="b0fd4-166">Pack the project and use a specific runtime (Windows 10) for the restore operation:</span></span>

  ```dotnetcli
  dotnet pack --runtime win10-x64
  ```

- <span data-ttu-id="b0fd4-167">Packen Sie das Projekt mithilfe einer *NUSPEC-Datei*:</span><span class="sxs-lookup"><span data-stu-id="b0fd4-167">Pack the project using a *.nuspec* file:</span></span>

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj -p:NuspecFile=~/projects/app1/project.nuspec -p:NuspecBasePath=~/projects/app1/nuget
  ```

  <span data-ttu-id="b0fd4-168">Informationen zur Verwendung von `NuspecFile`, `NuspecBasePath` und `NuspecProperties` finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="b0fd4-168">For information about how to use `NuspecFile`, `NuspecBasePath`, and `NuspecProperties`, see the following resources:</span></span>
  
  - [<span data-ttu-id="b0fd4-169">Packen mithilfe einer NUSPEC-Datei</span><span class="sxs-lookup"><span data-stu-id="b0fd4-169">Packing using a .nuspec</span></span>](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec)
  - [<span data-ttu-id="b0fd4-170">Verbesserte Erweiterungspunkte zum Erstellen benutzerdefinierter Pakete</span><span class="sxs-lookup"><span data-stu-id="b0fd4-170">Advanced extension points to create customized package</span></span>](https://docs.microsoft.com/nuget/reference/msbuild-targets#advanced-extension-points-to-create-customized-package)
  - [<span data-ttu-id="b0fd4-171">Globale Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b0fd4-171">Global properties</span></span>](https://docs.microsoft.com/visualstudio/msbuild/msbuild-properties?view=vs-2019#global-properties)
