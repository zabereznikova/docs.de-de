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
ms.openlocfilehash: 7cb84c2dc7fc4d16b00bd6459132390ab80131f3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="c1e16-104">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="c1e16-104">dotnet remove reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c1e16-105">Name</span><span class="sxs-lookup"><span data-stu-id="c1e16-105">Name</span></span>

<span data-ttu-id="c1e16-106">`dotnet remove reference`: Entfernt Projekt-zu-Projekt-Verweise.</span><span class="sxs-lookup"><span data-stu-id="c1e16-106">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c1e16-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c1e16-107">Synopsis</span></span>

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="c1e16-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1e16-108">Description</span></span>

<span data-ttu-id="c1e16-109">Der `dotnet remove reference`-Befehl bietet eine praktische Option zum Entfernen von Projektverweisen von einem Projekt.</span><span class="sxs-lookup"><span data-stu-id="c1e16-109">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="c1e16-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="c1e16-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="c1e16-111">Zielprojektdatei.</span><span class="sxs-lookup"><span data-stu-id="c1e16-111">Target project file.</span></span> <span data-ttu-id="c1e16-112">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="c1e16-112">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="c1e16-113">Zu entfernende Projekt-zu-Projekt (P2P)-Verweise.</span><span class="sxs-lookup"><span data-stu-id="c1e16-113">Project to project (P2P references to remove.</span></span> <span data-ttu-id="c1e16-114">Sie können ein oder mehrere Projekte angeben.</span><span class="sxs-lookup"><span data-stu-id="c1e16-114">You can specify one or multiple projects.</span></span> <span data-ttu-id="c1e16-115">[Globmuster](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Terminals unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c1e16-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="c1e16-116">Optionen</span><span class="sxs-lookup"><span data-stu-id="c1e16-116">Options</span></span>

`-h|--help`

<span data-ttu-id="c1e16-117">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="c1e16-117">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="c1e16-118">Entfernt den Verweis nur, wenn auf ein bestimmtes [Framework](../../standard/frameworks.md) abgezielt wird.</span><span class="sxs-lookup"><span data-stu-id="c1e16-118">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="c1e16-119">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c1e16-119">Examples</span></span>

<span data-ttu-id="c1e16-120">Entfernen Sie einen Projektverweis aus dem angegebenen Projekt:</span><span class="sxs-lookup"><span data-stu-id="c1e16-120">Remove a project reference from the specified project:</span></span>

`dotnet remove app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="c1e16-121">Entfernen Sie mehrere Projektverweise aus dem Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="c1e16-121">Remove multiple project references from the project in the current directory:</span></span>

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="c1e16-122">Entfernen Sie mehrere Projektverweise mithilfe eines Globmusters auf Unix/Linux:</span><span class="sxs-lookup"><span data-stu-id="c1e16-122">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

`dotnet remove app/app.csproj reference **/*.csproj`
