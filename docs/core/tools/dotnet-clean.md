---
title: Befehl „dotnet clean“
description: Mit dem Befehl „dotnet clean“ wird das aktuelle Verzeichnis bereinigt.
ms.date: 06/26/2019
ms.openlocfilehash: 736c0bba5d156e919534f1ad811641e815b3ffac
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734252"
---
# <a name="dotnet-clean"></a><span data-ttu-id="e2e81-103">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="e2e81-103">dotnet clean</span></span>

<span data-ttu-id="e2e81-104">**Dieser Artikel gilt für:** ✔️ .NET Core 1.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="e2e81-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="e2e81-105">name</span><span class="sxs-lookup"><span data-stu-id="e2e81-105">Name</span></span>

<span data-ttu-id="e2e81-106">`dotnet clean`: Löscht die Ausgabe eines Projekts.</span><span class="sxs-lookup"><span data-stu-id="e2e81-106">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e2e81-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="e2e81-107">Synopsis</span></span>

```dotnetcli
dotnet clean [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--interactive]
    [--nologo] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a><span data-ttu-id="e2e81-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2e81-108">Description</span></span>

<span data-ttu-id="e2e81-109">Der Befehl `dotnet clean` löscht die Ausgabe des vorherigen Builds.</span><span class="sxs-lookup"><span data-stu-id="e2e81-109">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="e2e81-110">Er ist als [MSBuild-Ziel](/visualstudio/msbuild/msbuild-targets) implementiert, sodass das Projekt ausgewertet wird, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e2e81-110">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="e2e81-111">Es werden nur die Ausgaben gelöscht, die während des Builds erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="e2e81-111">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="e2e81-112">Sowohl der Ordner für Zwischenausgabe (*obj*) als auch der Ordner für die endgültige Ausgabe (*bin*) werden bereinigt.</span><span class="sxs-lookup"><span data-stu-id="e2e81-112">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="e2e81-113">Argumente</span><span class="sxs-lookup"><span data-stu-id="e2e81-113">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="e2e81-114">MSBuild-Projekt oder Projektmappe, das/die bereinigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e2e81-114">The MSBuild project or solution to clean.</span></span> <span data-ttu-id="e2e81-115">Wenn Sie keine Projekt- oder Projektmappendatei angeben, durchsucht MSBuild das aktuelle Arbeitsverzeichnis nach einer Dateierweiterung, die mit *proj* oder *sln* endet, und verwendet diese.</span><span class="sxs-lookup"><span data-stu-id="e2e81-115">If a project or solution file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* or *sln*, and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="e2e81-116">Optionen</span><span class="sxs-lookup"><span data-stu-id="e2e81-116">Options</span></span>

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="e2e81-117">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="e2e81-117">Defines the build configuration.</span></span> <span data-ttu-id="e2e81-118">Der Standardwert ist `Debug`.</span><span class="sxs-lookup"><span data-stu-id="e2e81-118">The default value is `Debug`.</span></span> <span data-ttu-id="e2e81-119">Diese Option ist bei der Bereinigung nur erforderlich, wenn Sie sie bei der Erstellung angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="e2e81-119">This option is only required when cleaning if you specified it during build time.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e2e81-120">Das [Framework](../../standard/frameworks.md), das bei der Erstellung angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="e2e81-120">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="e2e81-121">Das Framework muss in der [Projektdatei](csproj.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="e2e81-121">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="e2e81-122">Wenn Sie das Framework bei der Erstellung angegeben haben, müssen Sie das Framework bei der Bereinigung angeben.</span><span class="sxs-lookup"><span data-stu-id="e2e81-122">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

* **`-h|--help`**

  <span data-ttu-id="e2e81-123">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="e2e81-123">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="e2e81-124">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten.</span><span class="sxs-lookup"><span data-stu-id="e2e81-124">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="e2e81-125">Beispielsweise, um die Authentifizierung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e2e81-125">For example, to complete authentication.</span></span> <span data-ttu-id="e2e81-126">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="e2e81-126">Available since .NET Core 3.0 SDK.</span></span>

* **`--nologo`**

  <span data-ttu-id="e2e81-127">Unterdrückt die Anzeige von Startbanner und Copyrightmeldung.</span><span class="sxs-lookup"><span data-stu-id="e2e81-127">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="e2e81-128">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="e2e81-128">Available since .NET Core 3.0 SDK.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="e2e81-129">Das Verzeichnis mit den zu bereinigenden Buildartefakten.</span><span class="sxs-lookup"><span data-stu-id="e2e81-129">The directory that contains the build artifacts to clean.</span></span> <span data-ttu-id="e2e81-130">Geben Sie den `-f|--framework <FRAMEWORK>`-Schalter mit dem Schalter des Ausgabeverzeichnisses an, wenn Sie das Framework bei der Erstellung des Projekts angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="e2e81-130">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="e2e81-131">Bereinigt den Ausgabeordner der angegebenen Runtime</span><span class="sxs-lookup"><span data-stu-id="e2e81-131">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="e2e81-132">Wird bei der Erstellung einer [eigenständigen Bereitstellung](../deploying/index.md#self-contained-deployments-scd) verwendet.</span><span class="sxs-lookup"><span data-stu-id="e2e81-132">This is used when a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd) was created.</span></span> <span data-ttu-id="e2e81-133">Die Option ist seit dem .NET Core 2.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e2e81-133">Option available since .NET Core 2.0 SDK.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="e2e81-134">Legt den MSBuild-Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="e2e81-134">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="e2e81-135">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="e2e81-135">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="e2e81-136">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="e2e81-136">The default is `normal`.</span></span>

## <a name="examples"></a><span data-ttu-id="e2e81-137">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e2e81-137">Examples</span></span>

* <span data-ttu-id="e2e81-138">Bereinigen Sie einen Standardbuild des Projekts:</span><span class="sxs-lookup"><span data-stu-id="e2e81-138">Clean a default build of the project:</span></span>

  ```dotnetcli
  dotnet clean
  ```

* <span data-ttu-id="e2e81-139">Bereinigen Sie ein Projektbuild mit der Konfiguration „Release“:</span><span class="sxs-lookup"><span data-stu-id="e2e81-139">Clean a project built using the Release configuration:</span></span>

  ```dotnetcli
  dotnet clean --configuration Release
  ```
