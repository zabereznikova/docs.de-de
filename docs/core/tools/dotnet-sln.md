---
title: Befehl „dotnet sln“
description: Der Befehl dotnet-sln bietet eine praktische Option, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten.
ms.date: 12/07/2020
ms.openlocfilehash: 480634550f6fa1983bb46f51b439dc8a686ead3c
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851696"
---
# <a name="dotnet-sln"></a><span data-ttu-id="99fe5-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="99fe5-103">dotnet sln</span></span>

<span data-ttu-id="99fe5-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="99fe5-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="99fe5-105">name</span><span class="sxs-lookup"><span data-stu-id="99fe5-105">Name</span></span>

<span data-ttu-id="99fe5-106">`dotnet sln`: Der Befehl listet die Projekte in einer .NET-Projektmappendatei auf oder ändert sie.</span><span class="sxs-lookup"><span data-stu-id="99fe5-106">`dotnet sln` - Lists or modifies the projects in a .NET solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="99fe5-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="99fe5-107">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command]

dotnet sln [command] -h|--help
```

## <a name="description"></a><span data-ttu-id="99fe5-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99fe5-108">Description</span></span>

<span data-ttu-id="99fe5-109">Der Befehl `dotnet sln` bietet eine komfortable Möglichkeit, Projekte in einer Projektmappendatei aufzulisten und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="99fe5-109">The `dotnet sln` command provides a convenient way to list and modify projects in a solution file.</span></span>

<span data-ttu-id="99fe5-110">Die Projektmappendatei muss immer vorhanden sein, um den Befehl `dotnet sln` verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="99fe5-110">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="99fe5-111">Wenn Sie eine Datei erstellen müssen, verwenden Sie den Befehl [dotnet new](dotnet-new.md) wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="99fe5-111">If you need to create one, use the [dotnet new](dotnet-new.md) command, as in the following example:</span></span>

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a><span data-ttu-id="99fe5-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="99fe5-112">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="99fe5-113">Dies ist die zu verwendende Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="99fe5-113">The solution file to use.</span></span> <span data-ttu-id="99fe5-114">Wenn dieses Argument weggelassen wird, durchsucht der Befehl das aktuelle Verzeichnis nach einem.</span><span class="sxs-lookup"><span data-stu-id="99fe5-114">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="99fe5-115">Wenn keine oder mehrere Projektmappendateien gefunden werden, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="99fe5-115">If it finds no solution file or multiple solution files, the command fails.</span></span>

## <a name="options"></a><span data-ttu-id="99fe5-116">Optionen</span><span class="sxs-lookup"><span data-stu-id="99fe5-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="99fe5-117">Gibt eine Beschreibung zur Verwendung des Befehls aus.</span><span class="sxs-lookup"><span data-stu-id="99fe5-117">Prints out a description of how to use the command.</span></span>

## <a name="commands"></a><span data-ttu-id="99fe5-118">Befehle</span><span class="sxs-lookup"><span data-stu-id="99fe5-118">Commands</span></span>

### `list`

<span data-ttu-id="99fe5-119">Listet alle Projekte auf, die in einer Projektmappendatei enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="99fe5-119">Lists all projects in a solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="99fe5-120">Übersicht</span><span class="sxs-lookup"><span data-stu-id="99fe5-120">Synopsis</span></span>

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="99fe5-121">Argumente</span><span class="sxs-lookup"><span data-stu-id="99fe5-121">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="99fe5-122">Dies ist die zu verwendende Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="99fe5-122">The solution file to use.</span></span> <span data-ttu-id="99fe5-123">Wenn dieses Argument weggelassen wird, durchsucht der Befehl das aktuelle Verzeichnis nach einem.</span><span class="sxs-lookup"><span data-stu-id="99fe5-123">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="99fe5-124">Wenn keine oder mehrere Projektmappendateien gefunden werden, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="99fe5-124">If it finds no solution file or multiple solution files, the command fails.</span></span>

#### <a name="options"></a><span data-ttu-id="99fe5-125">Optionen</span><span class="sxs-lookup"><span data-stu-id="99fe5-125">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="99fe5-126">Gibt eine Beschreibung zur Verwendung des Befehls aus.</span><span class="sxs-lookup"><span data-stu-id="99fe5-126">Prints out a description of how to use the command.</span></span>
  
### `add`

<span data-ttu-id="99fe5-127">Fügt der Projektmappendatei ein oder mehrere Projekte hinzu.</span><span class="sxs-lookup"><span data-stu-id="99fe5-127">Adds one or more projects to the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="99fe5-128">Übersicht</span><span class="sxs-lookup"><span data-stu-id="99fe5-128">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder <PATH>] <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="99fe5-129">Argumente</span><span class="sxs-lookup"><span data-stu-id="99fe5-129">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="99fe5-130">Dies ist die zu verwendende Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="99fe5-130">The solution file to use.</span></span> <span data-ttu-id="99fe5-131">Falls nicht angegeben, durchsucht der Befehl das aktuelle Verzeichnis nach einer und schlägt fehl, wenn es mehrere Projektmappendateien gibt.</span><span class="sxs-lookup"><span data-stu-id="99fe5-131">If it is unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="99fe5-132">Dies ist der Pfad zum Projekt bzw. den Projekten, die zur Projektmappe hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="99fe5-132">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="99fe5-133">UNIX-/Linux-Shell-[Globmustererweiterungen](https://en.wikipedia.org/wiki/Glob_(programming)) werden ordnungsgemäß mit dem `dotnet sln`-Befehl verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="99fe5-133">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="99fe5-134">Optionen</span><span class="sxs-lookup"><span data-stu-id="99fe5-134">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="99fe5-135">Gibt eine Beschreibung zur Verwendung des Befehls aus.</span><span class="sxs-lookup"><span data-stu-id="99fe5-135">Prints out a description of how to use the command.</span></span>

- **`--in-root`**

  <span data-ttu-id="99fe5-136">Hiermit werden die Projekte im Stamm der Projektmappe platziert anstatt einen Projektmappenordner zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="99fe5-136">Places the projects in the root of the solution, rather than creating a solution folder.</span></span> <span data-ttu-id="99fe5-137">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="99fe5-137">Available since .NET Core 3.0 SDK.</span></span>

- **`-s|--solution-folder <PATH>`**

  <span data-ttu-id="99fe5-138">Dies ist der Zielpfad des Projektmappenordners, dem die Projekte hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="99fe5-138">The destination solution folder path to add the projects to.</span></span> <span data-ttu-id="99fe5-139">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="99fe5-139">Available since .NET Core 3.0 SDK.</span></span>

### `remove`

<span data-ttu-id="99fe5-140">Entfernt mindestens ein Projekt aus der Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="99fe5-140">Removes a project or multiple projects from the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="99fe5-141">Übersicht</span><span class="sxs-lookup"><span data-stu-id="99fe5-141">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="99fe5-142">Argumente</span><span class="sxs-lookup"><span data-stu-id="99fe5-142">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="99fe5-143">Dies ist die zu verwendende Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="99fe5-143">The solution file to use.</span></span> <span data-ttu-id="99fe5-144">Falls nicht angegeben, durchsucht der Befehl das aktuelle Verzeichnis nach einer und schlägt fehl, wenn es mehrere Projektmappendateien gibt.</span><span class="sxs-lookup"><span data-stu-id="99fe5-144">If is left unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="99fe5-145">Dies ist der Pfad zum Projekt bzw. den Projekten, die zur Projektmappe hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="99fe5-145">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="99fe5-146">UNIX-/Linux-Shell-[Globmustererweiterungen](https://en.wikipedia.org/wiki/Glob_(programming)) werden ordnungsgemäß mit dem `dotnet sln`-Befehl verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="99fe5-146">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="99fe5-147">Optionen</span><span class="sxs-lookup"><span data-stu-id="99fe5-147">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="99fe5-148">Gibt eine Beschreibung zur Verwendung des Befehls aus.</span><span class="sxs-lookup"><span data-stu-id="99fe5-148">Prints out a description of how to use the command.</span></span>

## <a name="examples"></a><span data-ttu-id="99fe5-149">Beispiele</span><span class="sxs-lookup"><span data-stu-id="99fe5-149">Examples</span></span>

- <span data-ttu-id="99fe5-150">Listen Sie alle Projekte in einer Projektmappe auf:</span><span class="sxs-lookup"><span data-stu-id="99fe5-150">List the projects in a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln list
  ```

- <span data-ttu-id="99fe5-151">Fügen Sie ein C#-Projekt zu einer Projektmappe hinzu:</span><span class="sxs-lookup"><span data-stu-id="99fe5-151">Add a C# project to a solution:</span></span>

  ```dotnetcli
  dotnet sln add todo-app/todo-app.csproj
  ```

- <span data-ttu-id="99fe5-152">Entfernen Sie ein C#-Projekt aus einer Projektmappe:</span><span class="sxs-lookup"><span data-stu-id="99fe5-152">Remove a C# project from a solution:</span></span>

  ```dotnetcli
  dotnet sln remove todo-app/todo-app.csproj
  ```

- <span data-ttu-id="99fe5-153">Fügen Sie mehrere C#-Projekte zum Stamm einer Projektmappe hinzu:</span><span class="sxs-lookup"><span data-stu-id="99fe5-153">Add multiple C# projects to the root of a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj --in-root
  ```

- <span data-ttu-id="99fe5-154">Fügen Sie mehrere C#-Projekte zu einer Projektmappe hinzu:</span><span class="sxs-lookup"><span data-stu-id="99fe5-154">Add multiple C# projects to a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="99fe5-155">Entfernen Sie mehrere C#-Projekte aus einer Projektmappe:</span><span class="sxs-lookup"><span data-stu-id="99fe5-155">Remove multiple C# projects from a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="99fe5-156">Fügen Sie mehrere C#-Projekte zu einer Projektmappe hinzu, indem Sie ein Globmuster (nur UNIX/Linux) verwenden:</span><span class="sxs-lookup"><span data-stu-id="99fe5-156">Add multiple C# projects to a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- <span data-ttu-id="99fe5-157">Fügen Sie mehrere C#-Projekte zu einer Projektmappe hinzu, indem Sie ein Globmuster (nur Windows PowerShell) verwenden:</span><span class="sxs-lookup"><span data-stu-id="99fe5-157">Add multiple C# projects to a solution using a globbing pattern (Windows PowerShell only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add (ls -r **/*.csproj)
  ```

- <span data-ttu-id="99fe5-158">Entfernen Sie mehrere C#-Projekte aus einer Projektmappe, indem Sie ein Globmuster (nur UNIX/Linux) verwenden:</span><span class="sxs-lookup"><span data-stu-id="99fe5-158">Remove multiple C# projects from a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```

- <span data-ttu-id="99fe5-159">Entfernen Sie mehrere C#-Projekte aus einer Projektmappe, indem Sie ein Globmuster (nur Windows PowerShell) verwenden:</span><span class="sxs-lookup"><span data-stu-id="99fe5-159">Remove multiple C# projects from a solution using a globbing pattern (Windows PowerShell only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove (ls -r **/*.csproj)
  ```

- <span data-ttu-id="99fe5-160">Erstellen Sie eine Projektmappe, eine Konsolen-App und zwei Klassenbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="99fe5-160">Create a solution, a console app, and two class libraries.</span></span> <span data-ttu-id="99fe5-161">Fügen Sie die Projekte zur Projektmappe hinzu, und verwenden Sie die Option `--solution-folder` von `dotnet sln`, um die Klassenbibliotheken in einem Projektmappenordner zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="99fe5-161">Add the projects to the solution, and use the `--solution-folder` option of `dotnet sln` to organize the class libraries into a solution folder.</span></span>

  ```dotnetcli
  dotnet new sln -n mysolution
  dotnet new console -o myapp
  dotnet new classlib -o mylib1
  dotnet new classlib -o mylib2
  dotnet sln mysolution.sln add myapp\myapp.csproj
  dotnet sln mysolution.sln add mylib1\mylib1.csproj --solution-folder mylibs
  dotnet sln mysolution.sln add mylib2\mylib2.csproj --solution-folder mylibs
  ```

  <span data-ttu-id="99fe5-162">Der folgende Screenshot zeigt das Ergebnis im **Projektmappen-Explorer** von Visual Studio 2019:</span><span class="sxs-lookup"><span data-stu-id="99fe5-162">The following screenshot shows the result in Visual Studio 2019 **Solution Explorer**:</span></span>

  :::image type="content" source="media/dotnet-sln/dotnet-sln-solution-folder.png" alt-text="Projektmappen-Explorer mit Klassenbibliotheksprojekten gruppiert in einem Projektmappenordner":::
