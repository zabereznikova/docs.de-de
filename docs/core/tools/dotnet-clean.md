---
title: "Befehl „dotnet-clean“ – .NET Core-CLI"
description: "Mit dem Befehl „dotnet-clean“ wird das aktuelle Verzeichnis bereinigt."
keywords: dotnet-clean, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: eff65fa1-bab4-4421-8260-d0a284b690b2
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 10222781d5bff596d1b7883bc73097758e878235
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-clean"></a><span data-ttu-id="9a363-104">dotnet-clean</span><span class="sxs-lookup"><span data-stu-id="9a363-104">dotnet-clean</span></span>

## <a name="name"></a><span data-ttu-id="9a363-105">Name</span><span class="sxs-lookup"><span data-stu-id="9a363-105">Name</span></span>

<span data-ttu-id="9a363-106">`dotnet-clean`: Löscht die Ausgabe eines Projekts.</span><span class="sxs-lookup"><span data-stu-id="9a363-106">`dotnet-clean` - Cleans the output of a project.</span></span> 

## <a name="synopsis"></a><span data-ttu-id="9a363-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="9a363-107">Synopsis</span></span>

`dotnet clean [<PROJECT>] [-o|--output] [-f|--framework] [-c|--configuration] [-v|--verbosity] [-h|--help]`

## <a name="description"></a><span data-ttu-id="9a363-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a363-108">Description</span></span>

<span data-ttu-id="9a363-109">Der Befehl `dotnet clean` löscht die Ausgabe des vorherigen Builds.</span><span class="sxs-lookup"><span data-stu-id="9a363-109">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="9a363-110">Er ist als [MSBuild-Ziel](/visualstudio/msbuild/msbuild-targets) implementiert, sodass das Projekt ausgewertet wird, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9a363-110">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="9a363-111">Es werden nur die Ausgaben gelöscht, die während des Builds erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="9a363-111">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="9a363-112">Sowohl der Ordner für Zwischenausgabe (*obj*) als auch der Ordner für die endgültige Ausgabe (*bin*) werden bereinigt.</span><span class="sxs-lookup"><span data-stu-id="9a363-112">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="9a363-113">Argumente</span><span class="sxs-lookup"><span data-stu-id="9a363-113">Arguments</span></span>

`PROJECT`

<span data-ttu-id="9a363-114">Das zu bereinigende MSBuild-Projekt.</span><span class="sxs-lookup"><span data-stu-id="9a363-114">The MSBuild project to clean.</span></span> <span data-ttu-id="9a363-115">Wenn Sie keine Projektdatei angeben, durchsucht MSBuild das aktuelle Arbeitsverzeichnis nach einer Dateierweiterung, die mit *proj* endet, und verwendet diese.</span><span class="sxs-lookup"><span data-stu-id="9a363-115">If a project file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="9a363-116">Optionen</span><span class="sxs-lookup"><span data-stu-id="9a363-116">Options</span></span>

`-h|--help`

<span data-ttu-id="9a363-117">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="9a363-117">Prints out a short help for the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="9a363-118">Verzeichnis, in dem die Buildausgaben abgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="9a363-118">Directory in which the build outputs are placed.</span></span> <span data-ttu-id="9a363-119">Geben Sie den `-f|--framework <FRAMEWORK>`-Schalter mit dem Schalter des Ausgabeverzeichnisses an, wenn Sie das Framework bei der Erstellung des Projekts angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="9a363-119">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="9a363-120">Das [Framework](../../standard/frameworks.md), das bei der Erstellung angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="9a363-120">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="9a363-121">Das Framework muss in der [Projektdatei](csproj.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="9a363-121">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="9a363-122">Wenn Sie das Framework bei der Erstellung angegeben haben, müssen Sie das Framework bei der Bereinigung angeben.</span><span class="sxs-lookup"><span data-stu-id="9a363-122">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

`-c|--configuration <CONFIGURATION>`

<span data-ttu-id="9a363-123">Legt die Konfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="9a363-123">Defines the configuration.</span></span> <span data-ttu-id="9a363-124">Wenn kein Wert angegeben ist, wird als Standardwert `Debug` verwendet.</span><span class="sxs-lookup"><span data-stu-id="9a363-124">If omitted, it defaults to `Debug`.</span></span> <span data-ttu-id="9a363-125">Diese Eigenschaft ist bei der Bereinigung nur erforderlich, wenn Sie sie bei der Erstellung angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="9a363-125">This property is only required when cleaning if you specified it during build time.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="9a363-126">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="9a363-126">Sets the verbosity level of the command.</span></span> <span data-ttu-id="9a363-127">Zulässige Grade sind q[uiet], m[inimal], n[ormal], d[etailed] und diag[nostic].</span><span class="sxs-lookup"><span data-stu-id="9a363-127">Allowed levels are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic].</span></span>

## <a name="examples"></a><span data-ttu-id="9a363-128">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9a363-128">Examples</span></span>

<span data-ttu-id="9a363-129">Bereinigen Sie einen Standardbuild des Projekts:</span><span class="sxs-lookup"><span data-stu-id="9a363-129">Clean a default build of the project:</span></span>

`dotnet clean`

<span data-ttu-id="9a363-130">Bereinigen Sie ein Projektbuild mit der Konfiguration „Release“:</span><span class="sxs-lookup"><span data-stu-id="9a363-130">Clean a project built using the Release configuration:</span></span>

`dotnet clean --configuration Release`

