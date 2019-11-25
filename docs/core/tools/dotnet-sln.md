---
title: Befehl „dotnet sln“
description: Der Befehl dotnet-sln bietet eine praktische Option, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten.
ms.date: 10/29/2019
ms.openlocfilehash: 18702c7638798117bd04d5c6a829d64cc6bf18a8
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2019
ms.locfileid: "73191818"
---
# <a name="dotnet-sln"></a><span data-ttu-id="d53e0-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="d53e0-103">dotnet sln</span></span>

<span data-ttu-id="d53e0-104">**Dieser Artikel gilt für: ✓**.NET Core 1.x SDK und spätere Versionen</span><span class="sxs-lookup"><span data-stu-id="d53e0-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="d53e0-105">name</span><span class="sxs-lookup"><span data-stu-id="d53e0-105">Name</span></span>

<span data-ttu-id="d53e0-106">`dotnet sln`: Ändert eine .NET Core-Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="d53e0-106">`dotnet sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d53e0-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d53e0-107">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command] [-h|--help]
```

## <a name="description"></a><span data-ttu-id="d53e0-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d53e0-108">Description</span></span>

<span data-ttu-id="d53e0-109">Der Befehl `dotnet sln` bietet eine praktische Möglichkeit, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="d53e0-109">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

<span data-ttu-id="d53e0-110">Die Projektmappendatei muss immer vorhanden sein, um den Befehl `dotnet sln` verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="d53e0-110">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="d53e0-111">Wenn Sie eine Datei erstellen müssen, verwenden Sie den Befehl [dotnet new](dotnet-new.md) wie in folgendem Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d53e0-111">If you need to create one, use the [dotnet new](dotnet-new.md) command, like in the following example:</span></span>

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a><span data-ttu-id="d53e0-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="d53e0-112">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="d53e0-113">Dies ist die zu verwendende Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="d53e0-113">The solution file to use.</span></span> <span data-ttu-id="d53e0-114">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="d53e0-114">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="d53e0-115">Gibt es mehrere Projektmappendateien in dem Verzeichnis, muss eine angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d53e0-115">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="d53e0-116">Optionen</span><span class="sxs-lookup"><span data-stu-id="d53e0-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="d53e0-117">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="d53e0-117">Prints out a short help for the command.</span></span>

## <a name="commands"></a><span data-ttu-id="d53e0-118">Befehle</span><span class="sxs-lookup"><span data-stu-id="d53e0-118">Commands</span></span>

### `add`

<span data-ttu-id="d53e0-119">Fügt mindestens ein Projekt zur Projektmappendatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="d53e0-119">Adds a project or multiple projects to the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="d53e0-120">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d53e0-120">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder] <PROJECT_PATH>
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="d53e0-121">Argumente</span><span class="sxs-lookup"><span data-stu-id="d53e0-121">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="d53e0-122">Dies ist die zu verwendende Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="d53e0-122">The solution file to use.</span></span> <span data-ttu-id="d53e0-123">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="d53e0-123">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="d53e0-124">Gibt es mehrere Projektmappendateien in dem Verzeichnis, muss eine angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d53e0-124">If there are multiple solution files in the directory, one must be specified.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="d53e0-125">Dies ist der Pfad zum Projekt, das zur Projektmappe hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d53e0-125">The path to the project to add to the solution.</span></span> <span data-ttu-id="d53e0-126">Fügen Sie mehrere Projekte hinzu, indem Sie diese durch Leerzeichen getrennt nacheinander hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d53e0-126">Add multiple projects by adding one after the other separated by spaces.</span></span> <span data-ttu-id="d53e0-127">UNIX-/Linux-Shell-[Globmustererweiterungen](https://en.wikipedia.org/wiki/Glob_(programming)) werden ordnungsgemäß mit dem `dotnet sln`-Befehl verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d53e0-127">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="d53e0-128">Optionen</span><span class="sxs-lookup"><span data-stu-id="d53e0-128">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="d53e0-129">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="d53e0-129">Prints out a short help for the command.</span></span>

- **`--in-root`**

  <span data-ttu-id="d53e0-130">Hiermit werden die Projekte im Stamm der Projektmappe platziert anstatt einen Projektmappenordner zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d53e0-130">Places the projects in the root of the solution, rather than creating a solution folder.</span></span> <span data-ttu-id="d53e0-131">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="d53e0-131">Available since .NET Core 3.0 SDK.</span></span>

- **`-s|--solution-folder`**

  <span data-ttu-id="d53e0-132">Dies ist der Zielpfad des Projektmappenordners, dem die Projekte hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d53e0-132">The destination solution folder path to add the projects to.</span></span> <span data-ttu-id="d53e0-133">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="d53e0-133">Available since .NET Core 3.0 SDK.</span></span>

### `remove`

<span data-ttu-id="d53e0-134">Entfernt mindestens ein Projekt aus der Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="d53e0-134">Removes a project or multiple projects from the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="d53e0-135">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d53e0-135">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH>
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="d53e0-136">Argumente</span><span class="sxs-lookup"><span data-stu-id="d53e0-136">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="d53e0-137">Dies ist die zu verwendende Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="d53e0-137">The solution file to use.</span></span> <span data-ttu-id="d53e0-138">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="d53e0-138">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="d53e0-139">Gibt es mehrere Projektmappendateien in dem Verzeichnis, muss eine angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d53e0-139">If there are multiple solution files in the directory, one must be specified.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="d53e0-140">Dies ist der Pfad zum Projekt, das aus der Projektmappe entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d53e0-140">The path to the project to remove from the solution.</span></span> <span data-ttu-id="d53e0-141">Sie können mehrere Projekte entfernen, indem Sie diese durch Leerzeichen getrennt nacheinander hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d53e0-141">Remove multiple projects by adding one after the other separated by spaces.</span></span> <span data-ttu-id="d53e0-142">UNIX-/Linux-Shell-[Globmustererweiterungen](https://en.wikipedia.org/wiki/Glob_(programming)) werden ordnungsgemäß mit dem `dotnet sln`-Befehl verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d53e0-142">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="d53e0-143">Optionen</span><span class="sxs-lookup"><span data-stu-id="d53e0-143">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="d53e0-144">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="d53e0-144">Prints out a short help for the command.</span></span>

### `list`

<span data-ttu-id="d53e0-145">Listet alle Projekte auf, die in einer Projektmappendatei enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d53e0-145">Lists all projects in a solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="d53e0-146">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d53e0-146">Synopsis</span></span>

```dotnetcli
dotnet sln list [-h|--help]
```
  
#### <a name="arguments"></a><span data-ttu-id="d53e0-147">Argumente</span><span class="sxs-lookup"><span data-stu-id="d53e0-147">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="d53e0-148">Dies ist die zu verwendende Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="d53e0-148">The solution file to use.</span></span> <span data-ttu-id="d53e0-149">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="d53e0-149">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="d53e0-150">Gibt es mehrere Projektmappendateien in dem Verzeichnis, muss eine angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d53e0-150">If there are multiple solution files in the directory, one must be specified.</span></span>

#### <a name="options"></a><span data-ttu-id="d53e0-151">Optionen</span><span class="sxs-lookup"><span data-stu-id="d53e0-151">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="d53e0-152">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="d53e0-152">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="d53e0-153">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d53e0-153">Examples</span></span>

<span data-ttu-id="d53e0-154">Fügen Sie ein C#-Projekt zu einer Projektmappe hinzu:</span><span class="sxs-lookup"><span data-stu-id="d53e0-154">Add a C# project to a solution:</span></span>

```dotnetcli
dotnet sln todo.sln add todo-app/todo-app.csproj
```

<span data-ttu-id="d53e0-155">Entfernen Sie ein C#-Projekt aus einer Projektmappe:</span><span class="sxs-lookup"><span data-stu-id="d53e0-155">Remove a C# project from a solution:</span></span>

```dotnetcli
dotnet sln todo.sln remove todo-app/todo-app.csproj
```

<span data-ttu-id="d53e0-156">Fügen Sie mehrere C#-Projekte zu einer Projektmappe hinzu:</span><span class="sxs-lookup"><span data-stu-id="d53e0-156">Add multiple C# projects to a solution:</span></span>

```dotnetcli
dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
```

<span data-ttu-id="d53e0-157">Entfernen Sie mehrere C#-Projekte aus einer Projektmappe:</span><span class="sxs-lookup"><span data-stu-id="d53e0-157">Remove multiple C# projects from a solution:</span></span>

```dotnetcli
dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
```

<span data-ttu-id="d53e0-158">Fügen Sie mehrere C#-Projekte zu einer Projektmappe hinzu, indem Sie ein Globmuster (nur UNIX/Linux) verwenden:</span><span class="sxs-lookup"><span data-stu-id="d53e0-158">Add multiple C# projects to a solution using a globbing pattern (Unix/Linux only):</span></span>

```dotnetcli
dotnet sln todo.sln add **/*.csproj
```

<span data-ttu-id="d53e0-159">Entfernen Sie mehrere C#-Projekte aus einer Projektmappe, indem Sie ein Globmuster (nur UNIX/Linux) verwenden:</span><span class="sxs-lookup"><span data-stu-id="d53e0-159">Remove multiple C# projects from a solution using a globbing pattern (Unix/Linux only):</span></span>

```dotnetcli
dotnet sln todo.sln remove **/*.csproj
```
