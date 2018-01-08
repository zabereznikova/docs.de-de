---
title: "Verweisbefehl „dotnet remove“ – .NET Core-CLI"
description: "Der Verweisbefehl „dotnet remove“ bietet eine praktische Option zum Entfernen von Projekt-zu-Projekt-Verweisen."
keywords: dotnet-remove, CLI, CLI-Befehl, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 691fd77c7605b6476adc764f20e59b51abd7d914
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="559b1-104">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="559b1-104">dotnet remove reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="559b1-105">name</span><span class="sxs-lookup"><span data-stu-id="559b1-105">Name</span></span>

<span data-ttu-id="559b1-106">`dotnet remove reference`: Entfernt Projekt-zu-Projekt-Verweise.</span><span class="sxs-lookup"><span data-stu-id="559b1-106">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="559b1-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="559b1-107">Synopsis</span></span>

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="559b1-108">description</span><span class="sxs-lookup"><span data-stu-id="559b1-108">Description</span></span>

<span data-ttu-id="559b1-109">Der `dotnet remove reference`-Befehl bietet eine praktische Option zum Entfernen von Projektverweisen von einem Projekt.</span><span class="sxs-lookup"><span data-stu-id="559b1-109">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="559b1-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="559b1-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="559b1-111">Zielprojektdatei.</span><span class="sxs-lookup"><span data-stu-id="559b1-111">Target project file.</span></span> <span data-ttu-id="559b1-112">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="559b1-112">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="559b1-113">Zu entfernende Projekt-zu-Projekt (P2P)-Verweise.</span><span class="sxs-lookup"><span data-stu-id="559b1-113">Project to project (P2P references to remove.</span></span> <span data-ttu-id="559b1-114">Sie können ein oder mehrere Projekte angeben.</span><span class="sxs-lookup"><span data-stu-id="559b1-114">You can specify one or multiple projects.</span></span> <span data-ttu-id="559b1-115">[Globmuster](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Terminals unterstützt.</span><span class="sxs-lookup"><span data-stu-id="559b1-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="559b1-116">Optionen</span><span class="sxs-lookup"><span data-stu-id="559b1-116">Options</span></span>

`-h|--help`

<span data-ttu-id="559b1-117">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="559b1-117">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="559b1-118">Entfernt den Verweis nur, wenn auf ein bestimmtes [Framework](../../standard/frameworks.md) abgezielt wird.</span><span class="sxs-lookup"><span data-stu-id="559b1-118">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="559b1-119">Beispiele</span><span class="sxs-lookup"><span data-stu-id="559b1-119">Examples</span></span>

<span data-ttu-id="559b1-120">Entfernen Sie einen Projektverweis aus dem angegebenen Projekt:</span><span class="sxs-lookup"><span data-stu-id="559b1-120">Remove a project reference from the specified project:</span></span>

`dotnet remove app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="559b1-121">Entfernen Sie mehrere Projektverweise aus dem Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="559b1-121">Remove multiple project references from the project in the current directory:</span></span>

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="559b1-122">Entfernen Sie mehrere Projektverweise mithilfe eines Globmusters auf Unix/Linux:</span><span class="sxs-lookup"><span data-stu-id="559b1-122">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

`dotnet remove app/app.csproj reference **/*.csproj`
