---
title: "Verweisbefehl „dotnet-remove“ – .NET Core-CLI"
description: "Der Verweisbefehl „dotnet-remove“ bietet eine praktische Option zum Entfernen von Projekt-zu-Projekt-Verweisen."
keywords: dotnet-remove, CLI, CLI-Befehl, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 889c6b7e-a313-40b1-9fd3-6a6f4c52f1d0
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e22f64370be4b56597a303d79d3aabe1ff22a78a
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-remove-reference"></a><span data-ttu-id="0e5d3-104">Verweis „dotnet-remove“</span><span class="sxs-lookup"><span data-stu-id="0e5d3-104">dotnet-remove reference</span></span>

## <a name="name"></a><span data-ttu-id="0e5d3-105">Name</span><span class="sxs-lookup"><span data-stu-id="0e5d3-105">Name</span></span>

<span data-ttu-id="0e5d3-106">`dotnet-remove reference`: Entfernt Projekt-zu-Projekt-Verweise.</span><span class="sxs-lookup"><span data-stu-id="0e5d3-106">`dotnet-remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0e5d3-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="0e5d3-107">Synopsis</span></span>

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="0e5d3-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e5d3-108">Description</span></span>

<span data-ttu-id="0e5d3-109">Der `dotnet remove reference`-Befehl bietet eine praktische Option zum Entfernen von Projektverweisen von einem Projekt.</span><span class="sxs-lookup"><span data-stu-id="0e5d3-109">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="0e5d3-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="0e5d3-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="0e5d3-111">Zielprojektdatei.</span><span class="sxs-lookup"><span data-stu-id="0e5d3-111">Target project file.</span></span> <span data-ttu-id="0e5d3-112">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="0e5d3-112">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="0e5d3-113">Zu entfernende Projekt-zu-Projekt (P2P)-Verweise.</span><span class="sxs-lookup"><span data-stu-id="0e5d3-113">Project to project (P2P references to remove.</span></span> <span data-ttu-id="0e5d3-114">Sie können ein oder mehrere Projekte angeben.</span><span class="sxs-lookup"><span data-stu-id="0e5d3-114">You can specify one or multiple projects.</span></span> <span data-ttu-id="0e5d3-115">[Globmuster](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Terminals unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0e5d3-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="0e5d3-116">Optionen</span><span class="sxs-lookup"><span data-stu-id="0e5d3-116">Options</span></span>

`-h|--help`

<span data-ttu-id="0e5d3-117">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="0e5d3-117">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="0e5d3-118">Entfernt den Verweis nur, wenn auf ein bestimmtes [Framework](../../standard/frameworks.md) abgezielt wird.</span><span class="sxs-lookup"><span data-stu-id="0e5d3-118">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="0e5d3-119">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0e5d3-119">Examples</span></span>

<span data-ttu-id="0e5d3-120">Entfernen Sie einen Projektverweis aus dem angegebenen Projekt:</span><span class="sxs-lookup"><span data-stu-id="0e5d3-120">Remove a project reference from the specified project:</span></span>

`dotnet remove app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="0e5d3-121">Entfernen Sie mehrere Projektverweise aus dem Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="0e5d3-121">Remove multiple project references from the project in the current directory:</span></span>

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="0e5d3-122">Entfernen Sie mehrere Projektverweise mithilfe eines Globmusters auf Unix/Linux:</span><span class="sxs-lookup"><span data-stu-id="0e5d3-122">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

`dotnet remove app/app.csproj reference **/*.csproj`

