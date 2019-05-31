---
title: Befehl „dotnet clean“
description: Mit dem Befehl „dotnet clean“ wird das aktuelle Verzeichnis bereinigt.
ms.date: 04/14/2019
ms.openlocfilehash: fa19f1b041e4031082f928135395a5f06ce702e9
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631823"
---
# <a name="dotnet-clean"></a><span data-ttu-id="f37ee-103">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="f37ee-103">dotnet clean</span></span>

<span data-ttu-id="f37ee-104">**Dieses Thema gilt für: ✓**.NET Core 1.x SDK und spätere Versionen</span><span class="sxs-lookup"><span data-stu-id="f37ee-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="f37ee-105">name</span><span class="sxs-lookup"><span data-stu-id="f37ee-105">Name</span></span>

<span data-ttu-id="f37ee-106">`dotnet clean`: Löscht die Ausgabe eines Projekts.</span><span class="sxs-lookup"><span data-stu-id="f37ee-106">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f37ee-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f37ee-107">Synopsis</span></span>

```
dotnet clean [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--interactive] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a><span data-ttu-id="f37ee-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f37ee-108">Description</span></span>

<span data-ttu-id="f37ee-109">Der Befehl `dotnet clean` löscht die Ausgabe des vorherigen Builds.</span><span class="sxs-lookup"><span data-stu-id="f37ee-109">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="f37ee-110">Er ist als [MSBuild-Ziel](/visualstudio/msbuild/msbuild-targets) implementiert, sodass das Projekt ausgewertet wird, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f37ee-110">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="f37ee-111">Es werden nur die Ausgaben gelöscht, die während des Builds erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f37ee-111">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="f37ee-112">Sowohl der Ordner für Zwischenausgabe (*obj*) als auch der Ordner für die endgültige Ausgabe (*bin*) werden bereinigt.</span><span class="sxs-lookup"><span data-stu-id="f37ee-112">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="f37ee-113">Argumente</span><span class="sxs-lookup"><span data-stu-id="f37ee-113">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="f37ee-114">MSBuild-Projekt oder Projektmappe, das/die bereinigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f37ee-114">The MSBuild project or solution to clean.</span></span> <span data-ttu-id="f37ee-115">Wenn Sie keine Projekt- oder Projektmappendatei angeben, durchsucht MSBuild das aktuelle Arbeitsverzeichnis nach einer Dateierweiterung, die mit *proj* oder *sln* endet, und verwendet diese.</span><span class="sxs-lookup"><span data-stu-id="f37ee-115">If a project or solution file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* or *sln*, and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="f37ee-116">Optionen</span><span class="sxs-lookup"><span data-stu-id="f37ee-116">Options</span></span>

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="f37ee-117">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="f37ee-117">Defines the build configuration.</span></span> <span data-ttu-id="f37ee-118">Der Standardwert ist `Debug`sein.</span><span class="sxs-lookup"><span data-stu-id="f37ee-118">The default value is `Debug`.</span></span> <span data-ttu-id="f37ee-119">Diese Option ist bei der Bereinigung nur erforderlich, wenn Sie sie bei der Erstellung angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="f37ee-119">This option is only required when cleaning if you specified it during build time.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="f37ee-120">Das [Framework](../../standard/frameworks.md), das bei der Erstellung angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="f37ee-120">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="f37ee-121">Das Framework muss in der [Projektdatei](csproj.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="f37ee-121">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="f37ee-122">Wenn Sie das Framework bei der Erstellung angegeben haben, müssen Sie das Framework bei der Bereinigung angeben.</span><span class="sxs-lookup"><span data-stu-id="f37ee-122">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

* **`-h|--help`**

  <span data-ttu-id="f37ee-123">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="f37ee-123">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="f37ee-124">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten.</span><span class="sxs-lookup"><span data-stu-id="f37ee-124">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="f37ee-125">Beispielsweise, um die Authentifizierung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="f37ee-125">For example, to complete authentication.</span></span> <span data-ttu-id="f37ee-126">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="f37ee-126">Available since .NET Core 3.0 SDK.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="f37ee-127">Das Verzeichnis mit den zu bereinigenden Buildartefakten.</span><span class="sxs-lookup"><span data-stu-id="f37ee-127">The directory that contains the build artifacts to clean.</span></span> <span data-ttu-id="f37ee-128">Geben Sie den `-f|--framework <FRAMEWORK>`-Schalter mit dem Schalter des Ausgabeverzeichnisses an, wenn Sie das Framework bei der Erstellung des Projekts angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="f37ee-128">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="f37ee-129">Bereinigt den Ausgabeordner der angegebenen Runtime</span><span class="sxs-lookup"><span data-stu-id="f37ee-129">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="f37ee-130">Wird bei der Erstellung einer [eigenständigen Bereitstellung](../deploying/index.md#self-contained-deployments-scd) verwendet.</span><span class="sxs-lookup"><span data-stu-id="f37ee-130">This is used when a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd) was created.</span></span> <span data-ttu-id="f37ee-131">Die Option ist seit dem .NET Core 2.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f37ee-131">Option available since .NET Core 2.0 SDK.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="f37ee-132">Legt den MSBuild-Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="f37ee-132">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="f37ee-133">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f37ee-133">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f37ee-134">Die Standardeinstellung ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="f37ee-134">The default is `normal`.</span></span>

## <a name="examples"></a><span data-ttu-id="f37ee-135">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f37ee-135">Examples</span></span>

* <span data-ttu-id="f37ee-136">Bereinigen Sie einen Standardbuild des Projekts:</span><span class="sxs-lookup"><span data-stu-id="f37ee-136">Clean a default build of the project:</span></span>

  ```console
  dotnet clean
  ```

* <span data-ttu-id="f37ee-137">Bereinigen Sie ein Projektbuild mit der Konfiguration „Release“:</span><span class="sxs-lookup"><span data-stu-id="f37ee-137">Clean a project built using the Release configuration:</span></span>

  ```console
  dotnet clean --configuration Release
  ```
