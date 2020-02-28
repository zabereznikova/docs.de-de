---
title: Befehl „dotnet clean“
description: Mit dem Befehl „dotnet clean“ wird das aktuelle Verzeichnis bereinigt.
ms.date: 02/14/2020
ms.openlocfilehash: 186f1ea07718a8e178f88c3d079cf6e2f1f8660b
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503753"
---
# <a name="dotnet-clean"></a><span data-ttu-id="82c66-103">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="82c66-103">dotnet clean</span></span>

<span data-ttu-id="82c66-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="82c66-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="82c66-105">name</span><span class="sxs-lookup"><span data-stu-id="82c66-105">Name</span></span>

<span data-ttu-id="82c66-106">`dotnet clean`: Löscht die Ausgabe eines Projekts.</span><span class="sxs-lookup"><span data-stu-id="82c66-106">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="82c66-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="82c66-107">Synopsis</span></span>

```dotnetcli
dotnet clean [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--interactive]
    [--nologo] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a><span data-ttu-id="82c66-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82c66-108">Description</span></span>

<span data-ttu-id="82c66-109">Der Befehl `dotnet clean` löscht die Ausgabe des vorherigen Builds.</span><span class="sxs-lookup"><span data-stu-id="82c66-109">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="82c66-110">Er ist als [MSBuild-Ziel](/visualstudio/msbuild/msbuild-targets) implementiert, sodass das Projekt ausgewertet wird, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="82c66-110">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="82c66-111">Es werden nur die Ausgaben gelöscht, die während des Builds erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="82c66-111">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="82c66-112">Sowohl der Ordner für Zwischenausgabe (*obj*) als auch der Ordner für die endgültige Ausgabe (*bin*) werden bereinigt.</span><span class="sxs-lookup"><span data-stu-id="82c66-112">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="82c66-113">Argumente</span><span class="sxs-lookup"><span data-stu-id="82c66-113">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="82c66-114">MSBuild-Projekt oder Projektmappe, das/die bereinigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="82c66-114">The MSBuild project or solution to clean.</span></span> <span data-ttu-id="82c66-115">Wenn Sie keine Projekt- oder Projektmappendatei angeben, durchsucht MSBuild das aktuelle Arbeitsverzeichnis nach einer Dateierweiterung, die mit *proj* oder *sln* endet, und verwendet diese.</span><span class="sxs-lookup"><span data-stu-id="82c66-115">If a project or solution file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* or *sln*, and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="82c66-116">Optionen</span><span class="sxs-lookup"><span data-stu-id="82c66-116">Options</span></span>

* **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="82c66-117">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="82c66-117">Defines the build configuration.</span></span> <span data-ttu-id="82c66-118">Der Standardwert für die meisten Projekte ist `Debug`, aber Sie können die Buildkonfigurationseinstellungen in Ihrem Projekt überschreiben.</span><span class="sxs-lookup"><span data-stu-id="82c66-118">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span> <span data-ttu-id="82c66-119">Diese Option ist bei der Bereinigung nur erforderlich, wenn Sie sie bei der Erstellung angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="82c66-119">This option is only required when cleaning if you specified it during build time.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="82c66-120">Das [Framework](../../standard/frameworks.md), das bei der Erstellung angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="82c66-120">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="82c66-121">Das Framework muss in der [Projektdatei](csproj.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="82c66-121">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="82c66-122">Wenn Sie das Framework bei der Erstellung angegeben haben, müssen Sie das Framework bei der Bereinigung angeben.</span><span class="sxs-lookup"><span data-stu-id="82c66-122">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

* **`-h|--help`**

  <span data-ttu-id="82c66-123">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="82c66-123">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="82c66-124">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten.</span><span class="sxs-lookup"><span data-stu-id="82c66-124">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="82c66-125">Beispielsweise, um die Authentifizierung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="82c66-125">For example, to complete authentication.</span></span> <span data-ttu-id="82c66-126">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="82c66-126">Available since .NET Core 3.0 SDK.</span></span>

* **`--nologo`**

  <span data-ttu-id="82c66-127">Unterdrückt die Anzeige von Startbanner und Copyrightmeldung.</span><span class="sxs-lookup"><span data-stu-id="82c66-127">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="82c66-128">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="82c66-128">Available since .NET Core 3.0 SDK.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="82c66-129">Das Verzeichnis mit den zu bereinigenden Buildartefakten.</span><span class="sxs-lookup"><span data-stu-id="82c66-129">The directory that contains the build artifacts to clean.</span></span> <span data-ttu-id="82c66-130">Geben Sie den `-f|--framework <FRAMEWORK>`-Schalter mit dem Schalter des Ausgabeverzeichnisses an, wenn Sie das Framework bei der Erstellung des Projekts angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="82c66-130">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="82c66-131">Bereinigt den Ausgabeordner der angegebenen Runtime</span><span class="sxs-lookup"><span data-stu-id="82c66-131">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="82c66-132">Wird bei der Erstellung einer [eigenständigen Bereitstellung](../deploying/index.md#publish-self-contained) verwendet.</span><span class="sxs-lookup"><span data-stu-id="82c66-132">This is used when a [self-contained deployment](../deploying/index.md#publish-self-contained) was created.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="82c66-133">Legt den MSBuild-Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="82c66-133">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="82c66-134">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="82c66-134">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="82c66-135">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="82c66-135">The default is `normal`.</span></span>

## <a name="examples"></a><span data-ttu-id="82c66-136">Beispiele</span><span class="sxs-lookup"><span data-stu-id="82c66-136">Examples</span></span>

* <span data-ttu-id="82c66-137">Bereinigen Sie einen Standardbuild des Projekts:</span><span class="sxs-lookup"><span data-stu-id="82c66-137">Clean a default build of the project:</span></span>

  ```dotnetcli
  dotnet clean
  ```

* <span data-ttu-id="82c66-138">Bereinigen Sie ein Projektbuild mit der Konfiguration „Release“:</span><span class="sxs-lookup"><span data-stu-id="82c66-138">Clean a project built using the Release configuration:</span></span>

  ```dotnetcli
  dotnet clean --configuration Release
  ```
