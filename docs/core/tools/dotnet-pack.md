---
title: "dotnet-pack-Befehl – .NET Core-CLI"
description: "Der dotnet-pack-Befehl erstellt NuGet-Pakete für ein .NET Core-Projekt."
keywords: dotnet-pack, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8dbbb3f7-b817-4161-a6c8-a3489d05e051
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 04b967fdf6578098caae8c21604c5d6160eb6775
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-pack"></a><span data-ttu-id="14d78-104">dotnet-pack</span><span class="sxs-lookup"><span data-stu-id="14d78-104">dotnet-pack</span></span>

## <a name="name"></a><span data-ttu-id="14d78-105">Name</span><span class="sxs-lookup"><span data-stu-id="14d78-105">Name</span></span>

<span data-ttu-id="14d78-106">`dotnet-pack`: Packt den Code in ein NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="14d78-106">`dotnet-pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="14d78-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="14d78-107">Synopsis</span></span>

`dotnet pack [<PROJECT>] [-o|--output] [--no-build] [--include-symbols] [--include-source] [-c|--configuration] [--version-suffix <VERSION_SUFFIX>] [-s|--serviceable] [-v|--verbosity] [-h|--help]`

## <a name="description"></a><span data-ttu-id="14d78-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14d78-108">Description</span></span>

<span data-ttu-id="14d78-109">Der Befehl `dotnet pack` erstellt das Projekt und NuGet-Pakete.</span><span class="sxs-lookup"><span data-stu-id="14d78-109">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="14d78-110">Das Ergebnis dieses Befehls ist ein NuGet-Paket.</span><span class="sxs-lookup"><span data-stu-id="14d78-110">The result of this command is a NuGet package.</span></span> <span data-ttu-id="14d78-111">Wenn die `--include-symbols`-Option vorhanden ist, wird ein anderes Paket mit den Debugsymbolen erstellt.</span><span class="sxs-lookup"><span data-stu-id="14d78-111">If the `--include-symbols` option is present, another package containing the debug symbols is created.</span></span> 

<span data-ttu-id="14d78-112">NuGet-Abhängigkeiten des gepackten Projekts werden der Datei *nuspec* hinzugefügt. Sie werden ordnungsgemäß aufgelöst, wenn das Paket installiert wird.</span><span class="sxs-lookup"><span data-stu-id="14d78-112">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="14d78-113">Verweise zwischen Projekten werden innerhalb des Projekts nicht gepackt.</span><span class="sxs-lookup"><span data-stu-id="14d78-113">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="14d78-114">Derzeit benötigen Sie ein Paket pro Projekt, wenn Sie Abhängigkeiten zwischen Projekten haben.</span><span class="sxs-lookup"><span data-stu-id="14d78-114">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="14d78-115">`dotnet pack` erstellt standardmäßig zuerst das Projekt.</span><span class="sxs-lookup"><span data-stu-id="14d78-115">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="14d78-116">Wenn Sie dieses Verhalten vermeiden möchten, übergeben Sie die Option `--no-build`.</span><span class="sxs-lookup"><span data-stu-id="14d78-116">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="14d78-117">Dies ist bei Buildszenarios der Continuous Integration (CI) oft hilfreich, bei denen Sie wissen, dass der Code kürzlich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="14d78-117">This is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="14d78-118">Sie können dem `dotnet pack`-Befehl MSBuild-Eigenschaften für den Packvorgang bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="14d78-118">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="14d78-119">Weitere Informationen finden Sie in den [NuGet-Metadateneigenschaften](csproj.md#nuget-metadata-properties) und in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="14d78-119">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

## <a name="arguments"></a><span data-ttu-id="14d78-120">Argumente</span><span class="sxs-lookup"><span data-stu-id="14d78-120">Arguments</span></span>

`PROJECT` 
    
<span data-ttu-id="14d78-121">Das zu packende Projekt.</span><span class="sxs-lookup"><span data-stu-id="14d78-121">The project to pack.</span></span> <span data-ttu-id="14d78-122">Es ist entweder ein Pfad zu einer [csproj-Datei](csproj.md) oder zu einem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="14d78-122">It's either a path to a [csproj file](csproj.md) or to a directory.</span></span> <span data-ttu-id="14d78-123">Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis angegeben.</span><span class="sxs-lookup"><span data-stu-id="14d78-123">If omitted, it defaults to the current directory.</span></span> 

## <a name="options"></a><span data-ttu-id="14d78-124">Optionen</span><span class="sxs-lookup"><span data-stu-id="14d78-124">Options</span></span>

`-h|--help`

<span data-ttu-id="14d78-125">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="14d78-125">Prints out a short help for the command.</span></span>  

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="14d78-126">Platziert die erstellten Pakete in das angegebene Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="14d78-126">Places the built packages in the directory specified.</span></span> 

`--no-build`

<span data-ttu-id="14d78-127">Erstellt das Projekt nicht vor dem Packen.</span><span class="sxs-lookup"><span data-stu-id="14d78-127">Don't build the project before packing.</span></span> 

`--include-symbols`

<span data-ttu-id="14d78-128">Generiert die Symbole `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="14d78-128">Generates the symbols `nupkg`.</span></span> 

`--include-source`

<span data-ttu-id="14d78-129">Nimmt die Quelldateien in das NuGet-Paket auf.</span><span class="sxs-lookup"><span data-stu-id="14d78-129">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="14d78-130">Die Quelldateien befinden sich im Ordner `src` im `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="14d78-130">The sources files are included in the `src` folder within the `nupkg`.</span></span> 

`-c|--configuration <CONFIGURATION>`

<span data-ttu-id="14d78-131">Konfiguration, die beim Erstellen des Projekts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="14d78-131">Configuration to use when building the project.</span></span> <span data-ttu-id="14d78-132">Wenn nicht angegeben, wird die Konfiguration standardmäßig auf `Debug` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="14d78-132">If not specified, configuration defaults to `Debug`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="14d78-133">Definiert den Wert für die `$(VersionSuffix)`-MSBuild-Eigenschaft im Projekt.</span><span class="sxs-lookup"><span data-stu-id="14d78-133">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-s|--serviceable`

<span data-ttu-id="14d78-134">Legt das zu verarbeitende Flag im Paket fest.</span><span class="sxs-lookup"><span data-stu-id="14d78-134">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="14d78-135">Weitere Informationen finden Sie unter [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries (.NET Blog: .NET 4.5.1 unterstützt Microsoft Sicherheitsupdates für .NET NuGet-Bibliotheken)](https://aka.ms/nupkgservicing).</span><span class="sxs-lookup"><span data-stu-id="14d78-135">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="14d78-136">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="14d78-136">Sets the verbosity level of the command.</span></span> <span data-ttu-id="14d78-137">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="14d78-137">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="14d78-138">Beispiele</span><span class="sxs-lookup"><span data-stu-id="14d78-138">Examples</span></span>

<span data-ttu-id="14d78-139">Packt das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="14d78-139">Pack the project in the current directory:</span></span>

`dotnet pack`

<span data-ttu-id="14d78-140">Packt das `app1`-Projekt:</span><span class="sxs-lookup"><span data-stu-id="14d78-140">Pack the `app1` project:</span></span>

`dotnet pack ~/projects/app1/project.csproj`
    
<span data-ttu-id="14d78-141">Packt das Projekt im aktuellen Verzeichnis, und platziert die erstellten Pakete in den `nupkgs`-Ordner:</span><span class="sxs-lookup"><span data-stu-id="14d78-141">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

`dotnet pack --output nupkgs`

<span data-ttu-id="14d78-142">Packt das Projekt im aktuellen Verzeichnis in den `nupkgs`-Ordner und überspringt den Buildschritt:</span><span class="sxs-lookup"><span data-stu-id="14d78-142">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

`dotnet pack --no-build --output nupkgs`

<span data-ttu-id="14d78-143">Mit dem Versionssuffix des Projekts, das als `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in der *.csproj*-Datei konfiguriert ist, packen Sie das aktuelle Projekt, und aktualisieren Sie die resultierende Paketversion mit dem angegebenen Suffix:</span><span class="sxs-lookup"><span data-stu-id="14d78-143">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

`dotnet pack --version-suffix "ci-1234"`

<span data-ttu-id="14d78-144">Legen Sie die Paketversion auf `2.1.0` mithilfe der MSBuild-Eigenschaft `PackageVersion` fest.</span><span class="sxs-lookup"><span data-stu-id="14d78-144">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

`dotnet pack /p:PackageVersion=2.1.0`

