---
title: "dotnet-sln-Befehl – .NET Core-CLI"
description: "Der Befehl dotnet-sln bietet eine praktische Option, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten."
keywords: dotnet-sln, CLI, CLI-Befehl, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 04/11/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: e5a72d3e-c14b-4b0a-a978-c5e54a0988c6
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 606929fbcafddf47abf5da6d3c8ce97d5af06909
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-sln"></a><span data-ttu-id="d4335-104">dotnet-sln</span><span class="sxs-lookup"><span data-stu-id="d4335-104">dotnet-sln</span></span>

## <a name="name"></a><span data-ttu-id="d4335-105">Name</span><span class="sxs-lookup"><span data-stu-id="d4335-105">Name</span></span>

<span data-ttu-id="d4335-106">`dotnet-sln`: Ändert eine .NET Core-Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="d4335-106">`dotnet-sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d4335-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d4335-107">Synopsis</span></span>

```
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a><span data-ttu-id="d4335-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4335-108">Description</span></span>

<span data-ttu-id="d4335-109">Der Befehl `dotnet sln` bietet eine praktische Möglichkeit, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="d4335-109">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

## <a name="commands"></a><span data-ttu-id="d4335-110">Befehle</span><span class="sxs-lookup"><span data-stu-id="d4335-110">Commands</span></span>

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

<span data-ttu-id="d4335-111">Fügt mindestens ein Projekt zur Projektmappendatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="d4335-111">Adds a project or multiple projects to the solution file.</span></span> <span data-ttu-id="d4335-112">[Globbing patterns (Globmuster)](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Terminals unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d4335-112">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

<span data-ttu-id="d4335-113">Entfernt mindestens ein Projekt aus der Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="d4335-113">Removes a project or multiple projects from the solution file.</span></span> <span data-ttu-id="d4335-114">[Globbing patterns (Globmuster)](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Terminals unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d4335-114">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`list`

<span data-ttu-id="d4335-115">Listet alle Projekte auf, die in einer Projektmappendatei enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d4335-115">List all projects in a solution file.</span></span>

## <a name="arguments"></a><span data-ttu-id="d4335-116">Argumente</span><span class="sxs-lookup"><span data-stu-id="d4335-116">Arguments</span></span>

`SOLUTION_NAME`

<span data-ttu-id="d4335-117">Die zu verwendende Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="d4335-117">Solution file to use.</span></span> <span data-ttu-id="d4335-118">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="d4335-118">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="d4335-119">Gibt es mehrere Projektmappendateien in dem Verzeichnis, muss eine angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d4335-119">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="d4335-120">Optionen</span><span class="sxs-lookup"><span data-stu-id="d4335-120">Options</span></span>

`-h|--help`

<span data-ttu-id="d4335-121">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="d4335-121">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="d4335-122">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d4335-122">Examples</span></span>

<span data-ttu-id="d4335-123">Fügen Sie ein C#-Projekt zu einer Projektmappe hinzu:</span><span class="sxs-lookup"><span data-stu-id="d4335-123">Add a C# project to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj`

<span data-ttu-id="d4335-124">Entfernen Sie ein C#-Projekt aus einer Projektmappe:</span><span class="sxs-lookup"><span data-stu-id="d4335-124">Remove a C# project from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

<span data-ttu-id="d4335-125">Fügen Sie mehrere C#-Projekte zu einer Projektmappe hinzu:</span><span class="sxs-lookup"><span data-stu-id="d4335-125">Add multiple C# projects to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="d4335-126">Entfernen Sie mehrere C#-Projekte aus einer Projektmappe:</span><span class="sxs-lookup"><span data-stu-id="d4335-126">Remove multiple C# projects from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="d4335-127">Fügen Sie mehrere C#-Projekte zu einer Projektmappe hinzu, indem Sie ein Globmuster verwenden:</span><span class="sxs-lookup"><span data-stu-id="d4335-127">Add multiple C# projects to a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln add **/*.csproj`

<span data-ttu-id="d4335-128">Entfernen Sie mehrere C#-Projekte aus einer Projektmappe, indem Sie ein Globmuster verwenden:</span><span class="sxs-lookup"><span data-stu-id="d4335-128">Remove multiple C# projects from a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln remove **/*.csproj`

