---
title: dotnet clean-Befehl – .NET Core-CLI
description: Mit dem Befehl „dotnet clean“ wird das aktuelle Verzeichnis bereinigt.
ms.date: 12/04/2018
ms.openlocfilehash: 9930d2905f234e7125f27367cda36aa85ae23b87
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144454"
---
# <a name="dotnet-clean"></a><span data-ttu-id="3af10-103">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="3af10-103">dotnet clean</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="3af10-104">name</span><span class="sxs-lookup"><span data-stu-id="3af10-104">Name</span></span>

<span data-ttu-id="3af10-105">`dotnet clean`: Löscht die Ausgabe eines Projekts.</span><span class="sxs-lookup"><span data-stu-id="3af10-105">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3af10-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="3af10-106">Synopsis</span></span>

```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a><span data-ttu-id="3af10-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3af10-107">Description</span></span>

<span data-ttu-id="3af10-108">Der Befehl `dotnet clean` löscht die Ausgabe des vorherigen Builds.</span><span class="sxs-lookup"><span data-stu-id="3af10-108">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="3af10-109">Er ist als [MSBuild-Ziel](/visualstudio/msbuild/msbuild-targets) implementiert, sodass das Projekt ausgewertet wird, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3af10-109">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="3af10-110">Es werden nur die Ausgaben gelöscht, die während des Builds erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="3af10-110">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="3af10-111">Sowohl der Ordner für Zwischenausgabe (*obj*) als auch der Ordner für die endgültige Ausgabe (*bin*) werden bereinigt.</span><span class="sxs-lookup"><span data-stu-id="3af10-111">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="3af10-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="3af10-112">Arguments</span></span>

`PROJECT`

<span data-ttu-id="3af10-113">Das zu bereinigende MSBuild-Projekt.</span><span class="sxs-lookup"><span data-stu-id="3af10-113">The MSBuild project to clean.</span></span> <span data-ttu-id="3af10-114">Wenn Sie keine Projektdatei angeben, durchsucht MSBuild das aktuelle Arbeitsverzeichnis nach einer Dateierweiterung, die mit *proj* endet, und verwendet diese.</span><span class="sxs-lookup"><span data-stu-id="3af10-114">If a project file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="3af10-115">Optionen</span><span class="sxs-lookup"><span data-stu-id="3af10-115">Options</span></span>

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="3af10-116">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="3af10-116">Defines the build configuration.</span></span> <span data-ttu-id="3af10-117">Der Standardwert ist `Debug`sein.</span><span class="sxs-lookup"><span data-stu-id="3af10-117">The default value is `Debug`.</span></span> <span data-ttu-id="3af10-118">Diese Option ist bei der Bereinigung nur erforderlich, wenn Sie sie bei der Erstellung angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="3af10-118">This option is only required when cleaning if you specified it during build time.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3af10-119">Das [Framework](../../standard/frameworks.md), das bei der Erstellung angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="3af10-119">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="3af10-120">Das Framework muss in der [Projektdatei](csproj.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="3af10-120">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="3af10-121">Wenn Sie das Framework bei der Erstellung angegeben haben, müssen Sie das Framework bei der Bereinigung angeben.</span><span class="sxs-lookup"><span data-stu-id="3af10-121">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

* **`-h|--help`**

  <span data-ttu-id="3af10-122">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="3af10-122">Prints out a short help for the command.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="3af10-123">Verzeichnis, in dem die Buildausgaben abgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="3af10-123">Directory in which the build outputs are placed.</span></span> <span data-ttu-id="3af10-124">Geben Sie den `-f|--framework <FRAMEWORK>`-Schalter mit dem Schalter des Ausgabeverzeichnisses an, wenn Sie das Framework bei der Erstellung des Projekts angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="3af10-124">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="3af10-125">Bereinigt den Ausgabeordner der angegebenen Runtime</span><span class="sxs-lookup"><span data-stu-id="3af10-125">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="3af10-126">Wird bei der Erstellung einer [eigenständigen Bereitstellung](../deploying/index.md#self-contained-deployments-scd) verwendet.</span><span class="sxs-lookup"><span data-stu-id="3af10-126">This is used when a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd) was created.</span></span> <span data-ttu-id="3af10-127">Die Option ist seit dem .NET Core 2.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3af10-127">Option available since .NET Core 2.0 SDK.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="3af10-128">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="3af10-128">Sets the verbosity level of the command.</span></span> <span data-ttu-id="3af10-129">Zulässige Grade sind q[uiet], m[inimal], n[ormal], d[etailed] und diag[nostic].</span><span class="sxs-lookup"><span data-stu-id="3af10-129">Allowed levels are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic].</span></span>

## <a name="examples"></a><span data-ttu-id="3af10-130">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3af10-130">Examples</span></span>

* <span data-ttu-id="3af10-131">Bereinigen Sie einen Standardbuild des Projekts:</span><span class="sxs-lookup"><span data-stu-id="3af10-131">Clean a default build of the project:</span></span>

  ```console
  dotnet clean
  ```

* <span data-ttu-id="3af10-132">Bereinigen Sie ein Projektbuild mit der Konfiguration „Release“:</span><span class="sxs-lookup"><span data-stu-id="3af10-132">Clean a project built using the Release configuration:</span></span>

  ```console
  dotnet clean --configuration Release
  ```