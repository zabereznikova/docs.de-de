---
title: Befehl „dotnet sln“
description: Der Befehl dotnet-sln bietet eine praktische Option, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten.
ms.date: 02/14/2020
ms.openlocfilehash: b2455c04a46b2a10b8142d8ddc2d8129f2154b27
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77543481"
---
# <a name="dotnet-sln"></a><span data-ttu-id="dd6b4-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="dd6b4-103">dotnet sln</span></span>

<span data-ttu-id="dd6b4-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="dd6b4-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="dd6b4-105">Name</span><span class="sxs-lookup"><span data-stu-id="dd6b4-105">Name</span></span>

<span data-ttu-id="dd6b4-106">`dotnet sln`: Listet die Projekte in einer .NET Core-Projektmappendatei auf oder ändert sie.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-106">`dotnet sln` - Lists or modifies the projects in a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="dd6b4-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="dd6b4-107">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command] [-h|--help]
```

## <a name="description"></a><span data-ttu-id="dd6b4-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dd6b4-108">Description</span></span>

<span data-ttu-id="dd6b4-109">Der Befehl `dotnet sln` bietet eine komfortable Möglichkeit, Projekte in einer Projektmappendatei aufzulisten und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-109">The `dotnet sln` command provides a convenient way to list and modify projects in a solution file.</span></span>

<span data-ttu-id="dd6b4-110">Die Projektmappendatei muss immer vorhanden sein, um den Befehl `dotnet sln` verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-110">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="dd6b4-111">Wenn Sie eine Datei erstellen müssen, verwenden Sie den Befehl [dotnet new](dotnet-new.md) wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="dd6b4-111">If you need to create one, use the [dotnet new](dotnet-new.md) command, as in the following example:</span></span>

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a><span data-ttu-id="dd6b4-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="dd6b4-112">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="dd6b4-113">Dies ist die zu verwendende Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-113">The solution file to use.</span></span> <span data-ttu-id="dd6b4-114">Wenn dieses Argument weggelassen wird, durchsucht der Befehl das aktuelle Verzeichnis nach einem.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-114">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="dd6b4-115">Wenn keine oder mehrere Projektmappendateien gefunden werden, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-115">If it finds no solution file or multiple solution files, the command fails.</span></span>

## <a name="options"></a><span data-ttu-id="dd6b4-116">Optionen</span><span class="sxs-lookup"><span data-stu-id="dd6b4-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="dd6b4-117">Gibt eine Beschreibung zur Verwendung des Befehls aus.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-117">Prints out a description of how to use the command.</span></span>

## <a name="commands"></a><span data-ttu-id="dd6b4-118">Befehle</span><span class="sxs-lookup"><span data-stu-id="dd6b4-118">Commands</span></span>

### `list`

<span data-ttu-id="dd6b4-119">Listet alle Projekte auf, die in einer Projektmappendatei enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-119">Lists all projects in a solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="dd6b4-120">Übersicht</span><span class="sxs-lookup"><span data-stu-id="dd6b4-120">Synopsis</span></span>

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="dd6b4-121">Argumente</span><span class="sxs-lookup"><span data-stu-id="dd6b4-121">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="dd6b4-122">Dies ist die zu verwendende Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-122">The solution file to use.</span></span> <span data-ttu-id="dd6b4-123">Wenn dieses Argument weggelassen wird, durchsucht der Befehl das aktuelle Verzeichnis nach einem.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-123">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="dd6b4-124">Wenn keine oder mehrere Projektmappendateien gefunden werden, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-124">If it finds no solution file or multiple solution files, the command fails.</span></span>

#### <a name="options"></a><span data-ttu-id="dd6b4-125">Optionen</span><span class="sxs-lookup"><span data-stu-id="dd6b4-125">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="dd6b4-126">Gibt eine Beschreibung zur Verwendung des Befehls aus.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-126">Prints out a description of how to use the command.</span></span>
  
### `add`

<span data-ttu-id="dd6b4-127">Fügt der Projektmappendatei ein oder mehrere Projekte hinzu.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-127">Adds one or more projects to the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="dd6b4-128">Übersicht</span><span class="sxs-lookup"><span data-stu-id="dd6b4-128">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder] <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="dd6b4-129">Argumente</span><span class="sxs-lookup"><span data-stu-id="dd6b4-129">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="dd6b4-130">Dies ist die zu verwendende Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-130">The solution file to use.</span></span> <span data-ttu-id="dd6b4-131">Falls nicht angegeben, durchsucht der Befehl das aktuelle Verzeichnis nach einer und schlägt fehl, wenn es mehrere Projektmappendateien gibt.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-131">If it is unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="dd6b4-132">Dies ist der Pfad zum Projekt bzw. den Projekten, die zur Projektmappe hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-132">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="dd6b4-133">UNIX-/Linux-Shell-[Globmustererweiterungen](https://en.wikipedia.org/wiki/Glob_(programming)) werden ordnungsgemäß mit dem `dotnet sln`-Befehl verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-133">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="dd6b4-134">Optionen</span><span class="sxs-lookup"><span data-stu-id="dd6b4-134">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="dd6b4-135">Gibt eine Beschreibung zur Verwendung des Befehls aus.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-135">Prints out a description of how to use the command.</span></span>

- **`--in-root`**

  <span data-ttu-id="dd6b4-136">Hiermit werden die Projekte im Stamm der Projektmappe platziert anstatt einen Projektmappenordner zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-136">Places the projects in the root of the solution, rather than creating a solution folder.</span></span> <span data-ttu-id="dd6b4-137">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-137">Available since .NET Core 3.0 SDK.</span></span>

- **`-s|--solution-folder`**

  <span data-ttu-id="dd6b4-138">Dies ist der Zielpfad des Projektmappenordners, dem die Projekte hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-138">The destination solution folder path to add the projects to.</span></span> <span data-ttu-id="dd6b4-139">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-139">Available since .NET Core 3.0 SDK.</span></span>

### `remove`

<span data-ttu-id="dd6b4-140">Entfernt mindestens ein Projekt aus der Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-140">Removes a project or multiple projects from the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="dd6b4-141">Übersicht</span><span class="sxs-lookup"><span data-stu-id="dd6b4-141">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="dd6b4-142">Argumente</span><span class="sxs-lookup"><span data-stu-id="dd6b4-142">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="dd6b4-143">Dies ist die zu verwendende Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-143">The solution file to use.</span></span> <span data-ttu-id="dd6b4-144">Falls nicht angegeben, durchsucht der Befehl das aktuelle Verzeichnis nach einer und schlägt fehl, wenn es mehrere Projektmappendateien gibt.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-144">If is left unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="dd6b4-145">Dies ist der Pfad zum Projekt bzw. den Projekten, die zur Projektmappe hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-145">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="dd6b4-146">UNIX-/Linux-Shell-[Globmustererweiterungen](https://en.wikipedia.org/wiki/Glob_(programming)) werden ordnungsgemäß mit dem `dotnet sln`-Befehl verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-146">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="dd6b4-147">Optionen</span><span class="sxs-lookup"><span data-stu-id="dd6b4-147">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="dd6b4-148">Gibt eine Beschreibung zur Verwendung des Befehls aus.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-148">Prints out a description of how to use the command.</span></span>

## <a name="examples"></a><span data-ttu-id="dd6b4-149">Beispiele</span><span class="sxs-lookup"><span data-stu-id="dd6b4-149">Examples</span></span>

- <span data-ttu-id="dd6b4-150">Listen Sie alle Projekte in einer Projektmappe auf:</span><span class="sxs-lookup"><span data-stu-id="dd6b4-150">List the projects in a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln list
  ```

- <span data-ttu-id="dd6b4-151">Fügen Sie ein C#-Projekt zu einer Projektmappe hinzu:</span><span class="sxs-lookup"><span data-stu-id="dd6b4-151">Add a C# project to a solution:</span></span>

  ```dotnetcli
  dotnet sln add todo-app/todo-app.csproj
  ```

- <span data-ttu-id="dd6b4-152">Entfernen Sie ein C#-Projekt aus einer Projektmappe:</span><span class="sxs-lookup"><span data-stu-id="dd6b4-152">Remove a C# project from a solution:</span></span>

  ```dotnetcli
  dotnet sln remove todo-app/todo-app.csproj
  ```

- <span data-ttu-id="dd6b4-153">Fügen Sie mehrere C#-Projekte zum Stamm einer Projektmappe hinzu:</span><span class="sxs-lookup"><span data-stu-id="dd6b4-153">Add multiple C# projects to the root of a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj --in-root
  ```

- <span data-ttu-id="dd6b4-154">Fügen Sie mehrere C#-Projekte zu einer Projektmappe hinzu:</span><span class="sxs-lookup"><span data-stu-id="dd6b4-154">Add multiple C# projects to a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="dd6b4-155">Entfernen Sie mehrere C#-Projekte aus einer Projektmappe:</span><span class="sxs-lookup"><span data-stu-id="dd6b4-155">Remove multiple C# projects from a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="dd6b4-156">Fügen Sie mehrere C#-Projekte zu einer Projektmappe hinzu, indem Sie ein Globmuster (nur UNIX/Linux) verwenden:</span><span class="sxs-lookup"><span data-stu-id="dd6b4-156">Add multiple C# projects to a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- <span data-ttu-id="dd6b4-157">Entfernen Sie mehrere C#-Projekte aus einer Projektmappe, indem Sie ein Globmuster (nur UNIX/Linux) verwenden:</span><span class="sxs-lookup"><span data-stu-id="dd6b4-157">Remove multiple C# projects from a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```
