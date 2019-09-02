---
title: Befehl „dotnet sln“
description: Der Befehl dotnet-sln bietet eine praktische Option, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten.
ms.date: 06/13/2018
ms.openlocfilehash: 3f18d6a2851d955d07cecc0cbc4c161cf0ec3e08
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70202794"
---
# <a name="dotnet-sln"></a><span data-ttu-id="2d2e4-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="2d2e4-103">dotnet sln</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="2d2e4-104">name</span><span class="sxs-lookup"><span data-stu-id="2d2e4-104">Name</span></span>

<span data-ttu-id="2d2e4-105">`dotnet sln`: Ändert eine .NET Core-Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="2d2e4-105">`dotnet sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2d2e4-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="2d2e4-106">Synopsis</span></span>

```console
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a><span data-ttu-id="2d2e4-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2d2e4-107">Description</span></span>

<span data-ttu-id="2d2e4-108">Der Befehl `dotnet sln` bietet eine praktische Möglichkeit, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="2d2e4-108">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

<span data-ttu-id="2d2e4-109">Die Projektmappendatei muss immer vorhanden sein, um den Befehl `dotnet sln` verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="2d2e4-109">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="2d2e4-110">Wenn Sie eine Datei erstellen müssen, verwenden Sie den Befehl [dotnet new](dotnet-new.md) wie in folgendem Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2d2e4-110">If you need to create one, use the [dotnet new](dotnet-new.md) command, like in the following example:</span></span>

```console
dotnet new sln
```

## <a name="commands"></a><span data-ttu-id="2d2e4-111">Befehle</span><span class="sxs-lookup"><span data-stu-id="2d2e4-111">Commands</span></span>

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

<span data-ttu-id="2d2e4-112">Fügt mindestens ein Projekt zur Projektmappendatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="2d2e4-112">Adds a project or multiple projects to the solution file.</span></span> <span data-ttu-id="2d2e4-113">[Globbing patterns (Globmuster)](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Terminals unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2d2e4-113">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

<span data-ttu-id="2d2e4-114">Entfernt mindestens ein Projekt aus der Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="2d2e4-114">Removes a project or multiple projects from the solution file.</span></span> <span data-ttu-id="2d2e4-115">[Globbing patterns (Globmuster)](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Terminals unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2d2e4-115">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`list`

<span data-ttu-id="2d2e4-116">Listet alle Projekte auf, die in einer Projektmappendatei enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2d2e4-116">Lists all projects in a solution file.</span></span>

## <a name="arguments"></a><span data-ttu-id="2d2e4-117">Argumente</span><span class="sxs-lookup"><span data-stu-id="2d2e4-117">Arguments</span></span>

`SOLUTION_NAME`

<span data-ttu-id="2d2e4-118">Die zu verwendende Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="2d2e4-118">Solution file to use.</span></span> <span data-ttu-id="2d2e4-119">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="2d2e4-119">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="2d2e4-120">Gibt es mehrere Projektmappendateien in dem Verzeichnis, muss eine angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2d2e4-120">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="2d2e4-121">Optionen</span><span class="sxs-lookup"><span data-stu-id="2d2e4-121">Options</span></span>

`-h|--help`

<span data-ttu-id="2d2e4-122">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="2d2e4-122">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="2d2e4-123">Beispiele</span><span class="sxs-lookup"><span data-stu-id="2d2e4-123">Examples</span></span>

<span data-ttu-id="2d2e4-124">Fügen Sie ein C#-Projekt zu einer Projektmappe hinzu:</span><span class="sxs-lookup"><span data-stu-id="2d2e4-124">Add a C# project to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj`

<span data-ttu-id="2d2e4-125">Entfernen Sie ein C#-Projekt aus einer Projektmappe:</span><span class="sxs-lookup"><span data-stu-id="2d2e4-125">Remove a C# project from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

<span data-ttu-id="2d2e4-126">Fügen Sie mehrere C#-Projekte zu einer Projektmappe hinzu:</span><span class="sxs-lookup"><span data-stu-id="2d2e4-126">Add multiple C# projects to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="2d2e4-127">Entfernen Sie mehrere C#-Projekte aus einer Projektmappe:</span><span class="sxs-lookup"><span data-stu-id="2d2e4-127">Remove multiple C# projects from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="2d2e4-128">Fügen Sie mehrere C#-Projekte zu einer Projektmappe hinzu, indem Sie ein Globmuster verwenden:</span><span class="sxs-lookup"><span data-stu-id="2d2e4-128">Add multiple C# projects to a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln add **/*.csproj`

<span data-ttu-id="2d2e4-129">Entfernen Sie mehrere C#-Projekte aus einer Projektmappe, indem Sie ein Globmuster verwenden:</span><span class="sxs-lookup"><span data-stu-id="2d2e4-129">Remove multiple C# projects from a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln remove **/*.csproj`

> [!NOTE]
> <span data-ttu-id="2d2e4-130">Globbing ist kein Feature der CLI, sondern der Befehlsshell.</span><span class="sxs-lookup"><span data-stu-id="2d2e4-130">Globbing is not a CLI feature but rather a feature of the command shell.</span></span> <span data-ttu-id="2d2e4-131">Um die Dateien erfolgreich zu erweitern, müssen Sie eine Shell verwenden, die Globbing unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2d2e4-131">To successfully expand the files, you must use a shell that supports globbing.</span></span> <span data-ttu-id="2d2e4-132">Weitere Informationen zum Globbing finden Sie bei [Wikipedia](https://en.wikipedia.org/wiki/Glob_(programming)).</span><span class="sxs-lookup"><span data-stu-id="2d2e4-132">For more information about globbing, see [Wikipedia](https://en.wikipedia.org/wiki/Glob_(programming)).</span></span>
