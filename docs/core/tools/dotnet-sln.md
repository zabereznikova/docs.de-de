---
title: dotnet sln-Befehl – .NET Core-CLI
description: Der Befehl dotnet-sln bietet eine praktische Option, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 845e666b9d8a8b206c7e1978a7dde9f33ffb8a32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-sln"></a><span data-ttu-id="ccb14-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="ccb14-103">dotnet sln</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="ccb14-104">name</span><span class="sxs-lookup"><span data-stu-id="ccb14-104">Name</span></span>

<span data-ttu-id="ccb14-105">`dotnet sln`: Ändert eine .NET Core-Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="ccb14-105">`dotnet sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ccb14-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ccb14-106">Synopsis</span></span>

```
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a><span data-ttu-id="ccb14-107">description</span><span class="sxs-lookup"><span data-stu-id="ccb14-107">Description</span></span>

<span data-ttu-id="ccb14-108">Der Befehl `dotnet sln` bietet eine praktische Möglichkeit, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="ccb14-108">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

## <a name="commands"></a><span data-ttu-id="ccb14-109">Befehle</span><span class="sxs-lookup"><span data-stu-id="ccb14-109">Commands</span></span>

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

<span data-ttu-id="ccb14-110">Fügt mindestens ein Projekt zur Projektmappendatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="ccb14-110">Adds a project or multiple projects to the solution file.</span></span> <span data-ttu-id="ccb14-111">[Globbing patterns (Globmuster)](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Terminals unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ccb14-111">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

<span data-ttu-id="ccb14-112">Entfernt mindestens ein Projekt aus der Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="ccb14-112">Removes a project or multiple projects from the solution file.</span></span> <span data-ttu-id="ccb14-113">[Globbing patterns (Globmuster)](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Terminals unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ccb14-113">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`list`

<span data-ttu-id="ccb14-114">Listet alle Projekte auf, die in einer Projektmappendatei enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="ccb14-114">Lists all projects in a solution file.</span></span>

## <a name="arguments"></a><span data-ttu-id="ccb14-115">Argumente</span><span class="sxs-lookup"><span data-stu-id="ccb14-115">Arguments</span></span>

`SOLUTION_NAME`

<span data-ttu-id="ccb14-116">Die zu verwendende Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="ccb14-116">Solution file to use.</span></span> <span data-ttu-id="ccb14-117">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="ccb14-117">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="ccb14-118">Gibt es mehrere Projektmappendateien in dem Verzeichnis, muss eine angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ccb14-118">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="ccb14-119">Optionen</span><span class="sxs-lookup"><span data-stu-id="ccb14-119">Options</span></span>

`-h|--help`

<span data-ttu-id="ccb14-120">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="ccb14-120">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="ccb14-121">Beispiele</span><span class="sxs-lookup"><span data-stu-id="ccb14-121">Examples</span></span>

<span data-ttu-id="ccb14-122">Fügen Sie ein C#-Projekt zu einer Projektmappe hinzu:</span><span class="sxs-lookup"><span data-stu-id="ccb14-122">Add a C# project to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj`

<span data-ttu-id="ccb14-123">Entfernen Sie ein C#-Projekt aus einer Projektmappe:</span><span class="sxs-lookup"><span data-stu-id="ccb14-123">Remove a C# project from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

<span data-ttu-id="ccb14-124">Fügen Sie mehrere C#-Projekte zu einer Projektmappe hinzu:</span><span class="sxs-lookup"><span data-stu-id="ccb14-124">Add multiple C# projects to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="ccb14-125">Entfernen Sie mehrere C#-Projekte aus einer Projektmappe:</span><span class="sxs-lookup"><span data-stu-id="ccb14-125">Remove multiple C# projects from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="ccb14-126">Fügen Sie mehrere C#-Projekte zu einer Projektmappe hinzu, indem Sie ein Globmuster verwenden:</span><span class="sxs-lookup"><span data-stu-id="ccb14-126">Add multiple C# projects to a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln add **/*.csproj`

<span data-ttu-id="ccb14-127">Entfernen Sie mehrere C#-Projekte aus einer Projektmappe, indem Sie ein Globmuster verwenden:</span><span class="sxs-lookup"><span data-stu-id="ccb14-127">Remove multiple C# projects from a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln remove **/*.csproj`
