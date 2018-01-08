---
title: "dotnet pack-Befehl – .NET Core-CLI"
description: "Der dotnet pack-Befehl erstellt NuGet-Pakete für ein .NET Core-Projekt."
author: mairaw
ms.author: mairaw
ms.date: 12/13/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 28cd05db0643097a7271fd0488354846598ba493
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-pack"></a><span data-ttu-id="b380b-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="b380b-103">dotnet pack</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="b380b-104">name</span><span class="sxs-lookup"><span data-stu-id="b380b-104">Name</span></span>

<span data-ttu-id="b380b-105">`dotnet pack`: Packt den Code in ein NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="b380b-105">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b380b-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="b380b-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b380b-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b380b-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet pack [<PROJECT>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--no-build] [--no-dependencies] [--no-restore] [-o|--output] [--runtime] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b380b-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b380b-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet pack [<PROJECT>] [-c|--configuration] [--include-source] [--include-symbols] [--no-build] [-o|--output] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="b380b-109">description</span><span class="sxs-lookup"><span data-stu-id="b380b-109">Description</span></span>

<span data-ttu-id="b380b-110">Der Befehl `dotnet pack` erstellt das Projekt und NuGet-Pakete.</span><span class="sxs-lookup"><span data-stu-id="b380b-110">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="b380b-111">Das Ergebnis dieses Befehls ist ein NuGet-Paket.</span><span class="sxs-lookup"><span data-stu-id="b380b-111">The result of this command is a NuGet package.</span></span> <span data-ttu-id="b380b-112">Wenn die `--include-symbols`-Option vorhanden ist, wird ein anderes Paket mit den Debugsymbolen erstellt.</span><span class="sxs-lookup"><span data-stu-id="b380b-112">If the `--include-symbols` option is present, another package containing the debug symbols is created.</span></span>

<span data-ttu-id="b380b-113">NuGet-Abhängigkeiten des gepackten Projekts werden der Datei *nuspec* hinzugefügt. Sie werden ordnungsgemäß aufgelöst, wenn das Paket installiert wird.</span><span class="sxs-lookup"><span data-stu-id="b380b-113">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="b380b-114">Verweise zwischen Projekten werden innerhalb des Projekts nicht gepackt.</span><span class="sxs-lookup"><span data-stu-id="b380b-114">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="b380b-115">Derzeit benötigen Sie ein Paket pro Projekt, wenn Sie Abhängigkeiten zwischen Projekten haben.</span><span class="sxs-lookup"><span data-stu-id="b380b-115">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="b380b-116">`dotnet pack` erstellt standardmäßig zuerst das Projekt.</span><span class="sxs-lookup"><span data-stu-id="b380b-116">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="b380b-117">Wenn Sie dieses Verhalten vermeiden möchten, übergeben Sie die Option `--no-build`.</span><span class="sxs-lookup"><span data-stu-id="b380b-117">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="b380b-118">Dies ist bei Buildszenarios der Continuous Integration (CI) oft hilfreich, bei denen Sie wissen, dass der Code kürzlich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b380b-118">This is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="b380b-119">Sie können dem `dotnet pack`-Befehl MSBuild-Eigenschaften für den Packvorgang bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b380b-119">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="b380b-120">Weitere Informationen finden Sie in den [NuGet-Metadateneigenschaften](csproj.md#nuget-metadata-properties) und in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="b380b-120">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="b380b-121">Der Abschnitt [Beispiele](#examples) enthält Informationen darüber, wie die MSBuild-Eigenschaft „/p“ für verschiedene Szenarien verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b380b-121">The [Examples](#examples) section shows how to use the MSBuild /p switch for a couple of different scenarios.</span></span>

## <a name="arguments"></a><span data-ttu-id="b380b-122">Argumente</span><span class="sxs-lookup"><span data-stu-id="b380b-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="b380b-123">Das zu packende Projekt.</span><span class="sxs-lookup"><span data-stu-id="b380b-123">The project to pack.</span></span> <span data-ttu-id="b380b-124">Es ist entweder ein Pfad zu einer [csproj-Datei](csproj.md) oder zu einem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b380b-124">It's either a path to a [csproj file](csproj.md) or to a directory.</span></span> <span data-ttu-id="b380b-125">Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis angegeben.</span><span class="sxs-lookup"><span data-stu-id="b380b-125">If omitted, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="b380b-126">Optionen</span><span class="sxs-lookup"><span data-stu-id="b380b-126">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b380b-127">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b380b-127">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="b380b-128">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="b380b-128">Defines the build configuration.</span></span> <span data-ttu-id="b380b-129">Der Standardwert ist `Debug`.</span><span class="sxs-lookup"><span data-stu-id="b380b-129">The default value is `Debug`.</span></span>

<span data-ttu-id="b380b-130">`--force` erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="b380b-130">`--force` Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="b380b-131">Dies entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="b380b-131">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="b380b-132">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="b380b-132">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="b380b-133">Nimmt die Quelldateien in das NuGet-Paket auf.</span><span class="sxs-lookup"><span data-stu-id="b380b-133">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="b380b-134">Die Quelldateien befinden sich im Ordner `src` im `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="b380b-134">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="b380b-135">Generiert die Symbole `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="b380b-135">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="b380b-136">Erstellt das Projekt nicht vor dem Packen.</span><span class="sxs-lookup"><span data-stu-id="b380b-136">Doesn't build the project before packing.</span></span>

`--no-dependencies`

<span data-ttu-id="b380b-137">Ignoriert Verweise zwischen Projekten und stellt nur das zum Erstellen angegebene Stammprojekt wieder her.</span><span class="sxs-lookup"><span data-stu-id="b380b-137">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="b380b-138">Führt kein implizites Wiederherstellen durch, wenn der Befehl ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="b380b-138">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b380b-139">Platziert die erstellten Pakete in das angegebene Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b380b-139">Places the built packages in the directory specified.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="b380b-140">Gibt die Ziellaufzeit an, für die Pakete wiederhergestellt werden sollen</span><span class="sxs-lookup"><span data-stu-id="b380b-140">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="b380b-141">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="b380b-141">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-s|--serviceable`

<span data-ttu-id="b380b-142">Legt das zu verarbeitende Flag im Paket fest.</span><span class="sxs-lookup"><span data-stu-id="b380b-142">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="b380b-143">Weitere Informationen finden Sie unter [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries (.NET Blog: .NET 4.5.1 unterstützt Microsoft Sicherheitsupdates für .NET NuGet-Bibliotheken)](https://aka.ms/nupkgservicing).</span><span class="sxs-lookup"><span data-stu-id="b380b-143">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="b380b-144">Definiert den Wert für die `$(VersionSuffix)`-MSBuild-Eigenschaft im Projekt.</span><span class="sxs-lookup"><span data-stu-id="b380b-144">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="b380b-145">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="b380b-145">Sets the verbosity level of the command.</span></span> <span data-ttu-id="b380b-146">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="b380b-146">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b380b-147">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b380b-147">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="b380b-148">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="b380b-148">Defines the build configuration.</span></span> <span data-ttu-id="b380b-149">Der Standardwert ist `Debug`.</span><span class="sxs-lookup"><span data-stu-id="b380b-149">The default value is `Debug`.</span></span>

`-h|--help`

<span data-ttu-id="b380b-150">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="b380b-150">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="b380b-151">Nimmt die Quelldateien in das NuGet-Paket auf.</span><span class="sxs-lookup"><span data-stu-id="b380b-151">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="b380b-152">Die Quelldateien befinden sich im Ordner `src` im `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="b380b-152">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="b380b-153">Generiert die Symbole `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="b380b-153">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="b380b-154">Erstellt das Projekt nicht vor dem Packen.</span><span class="sxs-lookup"><span data-stu-id="b380b-154">Doesn't build the project before packing.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b380b-155">Platziert die erstellten Pakete in das angegebene Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b380b-155">Places the built packages in the directory specified.</span></span>

`-s|--serviceable`

<span data-ttu-id="b380b-156">Legt das zu verarbeitende Flag im Paket fest.</span><span class="sxs-lookup"><span data-stu-id="b380b-156">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="b380b-157">Weitere Informationen finden Sie unter [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries (.NET Blog: .NET 4.5.1 unterstützt Microsoft Sicherheitsupdates für .NET NuGet-Bibliotheken)](https://aka.ms/nupkgservicing).</span><span class="sxs-lookup"><span data-stu-id="b380b-157">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="b380b-158">Definiert den Wert für die `$(VersionSuffix)`-MSBuild-Eigenschaft im Projekt.</span><span class="sxs-lookup"><span data-stu-id="b380b-158">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="b380b-159">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="b380b-159">Sets the verbosity level of the command.</span></span> <span data-ttu-id="b380b-160">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="b380b-160">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="b380b-161">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b380b-161">Examples</span></span>

<span data-ttu-id="b380b-162">Packt das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="b380b-162">Pack the project in the current directory:</span></span>

`dotnet pack`

<span data-ttu-id="b380b-163">Packt das `app1`-Projekt:</span><span class="sxs-lookup"><span data-stu-id="b380b-163">Pack the `app1` project:</span></span>

`dotnet pack ~/projects/app1/project.csproj`
    
<span data-ttu-id="b380b-164">Packt das Projekt im aktuellen Verzeichnis, und platziert die erstellten Pakete in den `nupkgs`-Ordner:</span><span class="sxs-lookup"><span data-stu-id="b380b-164">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

`dotnet pack --output nupkgs`

<span data-ttu-id="b380b-165">Packt das Projekt im aktuellen Verzeichnis in den `nupkgs`-Ordner und überspringt den Buildschritt:</span><span class="sxs-lookup"><span data-stu-id="b380b-165">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

`dotnet pack --no-build --output nupkgs`

<span data-ttu-id="b380b-166">Mit dem Versionssuffix des Projekts, das als `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in der *.csproj*-Datei konfiguriert ist, packen Sie das aktuelle Projekt, und aktualisieren Sie die resultierende Paketversion mit dem angegebenen Suffix:</span><span class="sxs-lookup"><span data-stu-id="b380b-166">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

`dotnet pack --version-suffix "ci-1234"`

<span data-ttu-id="b380b-167">Legen Sie die Paketversion auf `2.1.0` mithilfe der MSBuild-Eigenschaft `PackageVersion` fest.</span><span class="sxs-lookup"><span data-stu-id="b380b-167">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

`dotnet pack /p:PackageVersion=2.1.0`

<span data-ttu-id="b380b-168">Packen Sie das Projekt für ein bestimmtes [Zielframework](../../standard/frameworks.md):</span><span class="sxs-lookup"><span data-stu-id="b380b-168">Pack the project for a specific [target framework](../../standard/frameworks.md):</span></span>

`dotnet pack /p:TargetFrameworks=net45`
