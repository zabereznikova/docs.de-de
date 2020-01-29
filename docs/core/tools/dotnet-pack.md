---
title: Befehl „dotnet pack“
description: Der dotnet pack-Befehl erstellt NuGet-Pakete für ein .NET Core-Projekt.
ms.date: 08/08/2019
ms.openlocfilehash: 057d1029e5c933912c43c178b6db8a8498f2ed57
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734118"
---
# <a name="dotnet-pack"></a><span data-ttu-id="a4237-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="a4237-103">dotnet pack</span></span>

<span data-ttu-id="a4237-104">**Dieser Artikel gilt für:** ✔️ .NET Core 1.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="a4237-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="a4237-105">name</span><span class="sxs-lookup"><span data-stu-id="a4237-105">Name</span></span>

<span data-ttu-id="a4237-106">`dotnet pack`: Packt den Code in ein NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="a4237-106">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a4237-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="a4237-107">Synopsis</span></span>

```dotnetcli
dotnet pack [<PROJECT>|<SOLUTION>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--interactive]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo] [-o|--output] [--runtime] [-s|--serviceable]
    [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```

## <a name="description"></a><span data-ttu-id="a4237-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4237-108">Description</span></span>

<span data-ttu-id="a4237-109">Der Befehl `dotnet pack` erstellt das Projekt und NuGet-Pakete.</span><span class="sxs-lookup"><span data-stu-id="a4237-109">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="a4237-110">Das Ergebnis dieses Befehls ist ein NuGet-Paket (d. h., eine *NUPKG*-Datei).</span><span class="sxs-lookup"><span data-stu-id="a4237-110">The result of this command is a NuGet package (that is, a *.nupkg* file).</span></span>

<span data-ttu-id="a4237-111">Wenn Sie ein Paket generieren möchten, das die Debugsymbole enthält, stehen Ihnen zwei Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="a4237-111">If you want to generate a package that contains the debug symbols, you have two options available:</span></span>

- <span data-ttu-id="a4237-112">`--include-symbols`: Es erstellt das Symbolpaket.</span><span class="sxs-lookup"><span data-stu-id="a4237-112">`--include-symbols` - it creates the symbols package.</span></span>
- <span data-ttu-id="a4237-113">`--include-source`: Es erstellt das Symbolpaket mit einem `src`-Ordner, der die Quelldateien enthält.</span><span class="sxs-lookup"><span data-stu-id="a4237-113">`--include-source` - it creates the symbols package with a `src` folder inside containing the source files.</span></span>

<span data-ttu-id="a4237-114">NuGet-Abhängigkeiten des gepackten Projekts werden der Datei *nuspec* hinzugefügt. Sie werden ordnungsgemäß aufgelöst, wenn das Paket installiert wird.</span><span class="sxs-lookup"><span data-stu-id="a4237-114">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="a4237-115">Verweise zwischen Projekten werden innerhalb des Projekts nicht gepackt.</span><span class="sxs-lookup"><span data-stu-id="a4237-115">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="a4237-116">Derzeit benötigen Sie ein Paket pro Projekt, wenn Sie Abhängigkeiten zwischen Projekten haben.</span><span class="sxs-lookup"><span data-stu-id="a4237-116">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="a4237-117">`dotnet pack` erstellt standardmäßig zuerst das Projekt.</span><span class="sxs-lookup"><span data-stu-id="a4237-117">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="a4237-118">Wenn Sie dieses Verhalten vermeiden möchten, übergeben Sie die Option `--no-build`.</span><span class="sxs-lookup"><span data-stu-id="a4237-118">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="a4237-119">Diese Option ist bei Buildszenarios der Continuous Integration (CI) oft hilfreich, bei denen Sie wissen, dass der Code kürzlich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a4237-119">This option is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="a4237-120">Sie können dem `dotnet pack`-Befehl MSBuild-Eigenschaften für den Packvorgang bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a4237-120">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="a4237-121">Weitere Informationen finden Sie in den [NuGet-Metadateneigenschaften](csproj.md#nuget-metadata-properties) und in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="a4237-121">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="a4237-122">Der Abschnitt [Beispiele](#examples) enthält Informationen darüber, wie der MSBuild-Schalter „-p“ für verschiedene Szenarien verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a4237-122">The [Examples](#examples) section shows how to use the MSBuild -p switch for a couple of different scenarios.</span></span>

<span data-ttu-id="a4237-123">Webprojekte können standardmäßig nicht verpackt werden.</span><span class="sxs-lookup"><span data-stu-id="a4237-123">Web projects aren't packable by default.</span></span> <span data-ttu-id="a4237-124">Um das Standardverhalten zu überschreiben, fügen Sie Ihrer *.csproj*-Datei die folgende Eigenschaft hinzu:</span><span class="sxs-lookup"><span data-stu-id="a4237-124">To override the default behavior, add the following property to your *.csproj* file:</span></span>

```xml
<PropertyGroup>
   <IsPackable>true</IsPackable>
</PropertyGroup>
```

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="a4237-125">Argumente</span><span class="sxs-lookup"><span data-stu-id="a4237-125">Arguments</span></span>

`PROJECT | SOLUTION`

  <span data-ttu-id="a4237-126">Das Projekt oder die Projektmappe, die gepackt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a4237-126">The project or solution to pack.</span></span> <span data-ttu-id="a4237-127">Es ist entweder ein Pfad zu einer [CSPROJ-Datei](csproj.md), einer Projektmappendatei oder zu einem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a4237-127">It's either a path to a [csproj file](csproj.md), a solution file, or to a directory.</span></span> <span data-ttu-id="a4237-128">Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einem Projekt oder einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="a4237-128">If not specified, the command searches the current directory for a project or solution file.</span></span>

## <a name="options"></a><span data-ttu-id="a4237-129">Optionen</span><span class="sxs-lookup"><span data-stu-id="a4237-129">Options</span></span>

- **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="a4237-130">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="a4237-130">Defines the build configuration.</span></span> <span data-ttu-id="a4237-131">Der Standardwert ist `Debug`.</span><span class="sxs-lookup"><span data-stu-id="a4237-131">The default value is `Debug`.</span></span>

- **`--force`**

  <span data-ttu-id="a4237-132">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="a4237-132">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="a4237-133">Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="a4237-133">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span> <span data-ttu-id="a4237-134">Die Option ist seit dem .NET Core 2.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a4237-134">Option available since .NET Core 2.0 SDK.</span></span>

- **`-h|--help`**

  <span data-ttu-id="a4237-135">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="a4237-135">Prints out a short help for the command.</span></span>

- **`--include-source`**

  <span data-ttu-id="a4237-136">Schließt neben den regulären NuGet-Paketen im Ausgabeverzeichnis auch die NuGet-Pakete der Debugsymbole ein.</span><span class="sxs-lookup"><span data-stu-id="a4237-136">Includes the debug symbols NuGet packages in addition to the regular NuGet packages in the output directory.</span></span> <span data-ttu-id="a4237-137">Die Quelldateien befinden sich im `src`-Ordner im Symbolpaket.</span><span class="sxs-lookup"><span data-stu-id="a4237-137">The sources files are included in the `src` folder within the symbols package.</span></span>

- **`--include-symbols`**

  <span data-ttu-id="a4237-138">Schließt neben den regulären NuGet-Paketen im Ausgabeverzeichnis auch die NuGet-Pakete der Debugsymbole ein.</span><span class="sxs-lookup"><span data-stu-id="a4237-138">Includes the debug symbols NuGet packages in addition to the regular NuGet packages in the output directory.</span></span>

- **`--interactive`**

  <span data-ttu-id="a4237-139">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen).</span><span class="sxs-lookup"><span data-stu-id="a4237-139">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="a4237-140">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="a4237-140">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-build`**

  <span data-ttu-id="a4237-141">Erstellt das Projekt nicht vor dem Packen.</span><span class="sxs-lookup"><span data-stu-id="a4237-141">Doesn't build the project before packing.</span></span> <span data-ttu-id="a4237-142">Zudem wird das Flag `--no-restore` implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a4237-142">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="a4237-143">Ignoriert Verweise zwischen Projekten und stellt nur das zum Erstellen angegebene Stammprojekt wieder her.</span><span class="sxs-lookup"><span data-stu-id="a4237-143">Ignores project-to-project references and only restores the root project.</span></span> <span data-ttu-id="a4237-144">Die Option ist seit dem .NET Core 2.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a4237-144">Option available since .NET Core 2.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="a4237-145">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a4237-145">Doesn't execute an implicit restore when running the command.</span></span> <span data-ttu-id="a4237-146">Die Option ist seit dem .NET Core 2.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a4237-146">Option available since .NET Core 2.0 SDK.</span></span>

- **`--nologo`**

  <span data-ttu-id="a4237-147">Unterdrückt die Anzeige von Startbanner und Copyrightmeldung.</span><span class="sxs-lookup"><span data-stu-id="a4237-147">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="a4237-148">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="a4237-148">Available since .NET Core 3.0 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="a4237-149">Platziert die erstellten Pakete in das angegebene Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a4237-149">Places the built packages in the directory specified.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="a4237-150">Gibt die Ziellaufzeit an, für die Pakete wiederhergestellt werden sollen</span><span class="sxs-lookup"><span data-stu-id="a4237-150">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="a4237-151">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="a4237-151">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="a4237-152">Die Option ist seit dem .NET Core 2.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a4237-152">Option available since .NET Core 2.0 SDK.</span></span>

- **`-s|--serviceable`**

  <span data-ttu-id="a4237-153">Legt das zu verarbeitende Flag im Paket fest.</span><span class="sxs-lookup"><span data-stu-id="a4237-153">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="a4237-154">Weitere Informationen finden Sie unter [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries (.NET Blog: .NET 4.5.1 unterstützt Microsoft Sicherheitsupdates für .NET NuGet-Bibliotheken)](https://aka.ms/nupkgservicing).</span><span class="sxs-lookup"><span data-stu-id="a4237-154">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="a4237-155">Definiert den Wert für die `$(VersionSuffix)`-MSBuild-Eigenschaft im Projekt.</span><span class="sxs-lookup"><span data-stu-id="a4237-155">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="a4237-156">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="a4237-156">Sets the verbosity level of the command.</span></span> <span data-ttu-id="a4237-157">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="a4237-157">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="a4237-158">Beispiele</span><span class="sxs-lookup"><span data-stu-id="a4237-158">Examples</span></span>

- <span data-ttu-id="a4237-159">Packt das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="a4237-159">Pack the project in the current directory:</span></span>

  ```dotnetcli
  dotnet pack
  ```

- <span data-ttu-id="a4237-160">Packt das `app1`-Projekt:</span><span class="sxs-lookup"><span data-stu-id="a4237-160">Pack the `app1` project:</span></span>

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj
  ```

- <span data-ttu-id="a4237-161">Packt das Projekt im aktuellen Verzeichnis, und platziert die erstellten Pakete in den `nupkgs`-Ordner:</span><span class="sxs-lookup"><span data-stu-id="a4237-161">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

  ```dotnetcli
  dotnet pack --output nupkgs
  ```

- <span data-ttu-id="a4237-162">Packt das Projekt im aktuellen Verzeichnis in den `nupkgs`-Ordner und überspringt den Buildschritt:</span><span class="sxs-lookup"><span data-stu-id="a4237-162">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

  ```dotnetcli
  dotnet pack --no-build --output nupkgs
  ```

- <span data-ttu-id="a4237-163">Mit dem Versionssuffix des Projekts, das als `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in der *.csproj*-Datei konfiguriert ist, packen Sie das aktuelle Projekt, und aktualisieren Sie die resultierende Paketversion mit dem angegebenen Suffix:</span><span class="sxs-lookup"><span data-stu-id="a4237-163">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

  ```dotnetcli
  dotnet pack --version-suffix "ci-1234"
  ```

- <span data-ttu-id="a4237-164">Legen Sie die Paketversion auf `2.1.0` mithilfe der MSBuild-Eigenschaft `PackageVersion` fest.</span><span class="sxs-lookup"><span data-stu-id="a4237-164">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

  ```dotnetcli
  dotnet pack -p:PackageVersion=2.1.0
  ```

- <span data-ttu-id="a4237-165">Packen Sie das Projekt für ein bestimmtes [Zielframework](../../standard/frameworks.md):</span><span class="sxs-lookup"><span data-stu-id="a4237-165">Pack the project for a specific [target framework](../../standard/frameworks.md):</span></span>

  ```dotnetcli
  dotnet pack -p:TargetFrameworks=net45
  ```

- <span data-ttu-id="a4237-166">Packen Sie das Projekt, und verwenden Sie eine bestimmte Runtime (Windows 10) für den Wiederherstellungsvorgang (.NET Core SDK 2.0 und spätere Versionen):</span><span class="sxs-lookup"><span data-stu-id="a4237-166">Pack the project and use a specific runtime (Windows 10) for the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

  ```dotnetcli
  dotnet pack --runtime win10-x64
  ```

- <span data-ttu-id="a4237-167">Packen Sie das Projekt mithilfe einer [NUSPEC-Datei](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec):</span><span class="sxs-lookup"><span data-stu-id="a4237-167">Pack the project using a [.nuspec file](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec):</span></span>

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj -p:NuspecFile=~/projects/app1/project.nuspec -p:NuspecBasePath=~/projects/app1/nuget
  ```
