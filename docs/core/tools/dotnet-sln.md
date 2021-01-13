---
title: Befehl „dotnet sln“
description: Der Befehl dotnet-sln bietet eine praktische Option, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten.
ms.date: 12/07/2020
ms.openlocfilehash: af502efe842e9c9610137738d86c05e00a3b37df
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633649"
---
# <a name="dotnet-sln"></a>dotnet sln

**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen

## <a name="name"></a>name

`dotnet sln`: Der Befehl listet die Projekte in einer .NET-Projektmappendatei auf oder ändert sie.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command]

dotnet sln [command] -h|--help
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet sln` bietet eine komfortable Möglichkeit, Projekte in einer Projektmappendatei aufzulisten und zu ändern.

Die Projektmappendatei muss immer vorhanden sein, um den Befehl `dotnet sln` verwenden zu können. Wenn Sie eine Datei erstellen müssen, verwenden Sie den Befehl [dotnet new](dotnet-new.md) wie im folgenden Beispiel:

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a>Argumente

- **`SOLUTION_FILE`**

  Dies ist die zu verwendende Projektmappendatei. Wenn dieses Argument weggelassen wird, durchsucht der Befehl das aktuelle Verzeichnis nach einem. Wenn keine oder mehrere Projektmappendateien gefunden werden, schlägt der Befehl fehl.

## <a name="options"></a>Optionen

- **`-h|--help`**

  Gibt eine Beschreibung zur Verwendung des Befehls aus.

## <a name="commands"></a>Befehle

### `list`

Listet alle Projekte auf, die in einer Projektmappendatei enthalten sind.

#### <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a>Argumente

- **`SOLUTION_FILE`**

  Dies ist die zu verwendende Projektmappendatei. Wenn dieses Argument weggelassen wird, durchsucht der Befehl das aktuelle Verzeichnis nach einem. Wenn keine oder mehrere Projektmappendateien gefunden werden, schlägt der Befehl fehl.

#### <a name="options"></a>Optionen

- **`-h|--help`**

  Gibt eine Beschreibung zur Verwendung des Befehls aus.
  
### `add`

Fügt der Projektmappendatei ein oder mehrere Projekte hinzu.

#### <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder <PATH>] <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a>Argumente

- **`SOLUTION_FILE`**

  Dies ist die zu verwendende Projektmappendatei. Falls nicht angegeben, durchsucht der Befehl das aktuelle Verzeichnis nach einer und schlägt fehl, wenn es mehrere Projektmappendateien gibt.

- **`PROJECT_PATH`**

  Dies ist der Pfad zum Projekt bzw. den Projekten, die zur Projektmappe hinzugefügt werden sollen. UNIX-/Linux-Shell-[Globmustererweiterungen](https://en.wikipedia.org/wiki/Glob_(programming)) werden ordnungsgemäß mit dem `dotnet sln`-Befehl verarbeitet.

#### <a name="options"></a>Optionen

- **`-h|--help`**

  Gibt eine Beschreibung zur Verwendung des Befehls aus.

- **`--in-root`**

  Hiermit werden die Projekte im Stamm der Projektmappe platziert anstatt einen Projektmappenordner zu erstellen. Verfügbar seit .NET Core 3.0 SDK.

- **`-s|--solution-folder <PATH>`**

  Dies ist der Zielpfad des [Projektmappenordners](/visualstudio/ide/solutions-and-projects-in-visual-studio#solution-folder), dem die Projekte hinzugefügt werden sollen. Verfügbar seit .NET Core 3.0 SDK.

### `remove`

Entfernt mindestens ein Projekt aus der Projektmappendatei.

#### <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a>Argumente

- **`SOLUTION_FILE`**

  Dies ist die zu verwendende Projektmappendatei. Falls nicht angegeben, durchsucht der Befehl das aktuelle Verzeichnis nach einer und schlägt fehl, wenn es mehrere Projektmappendateien gibt.

- **`PROJECT_PATH`**

  Dies ist der Pfad zum Projekt bzw. den Projekten, die zur Projektmappe hinzugefügt werden sollen. UNIX-/Linux-Shell-[Globmustererweiterungen](https://en.wikipedia.org/wiki/Glob_(programming)) werden ordnungsgemäß mit dem `dotnet sln`-Befehl verarbeitet.

#### <a name="options"></a>Optionen

- **`-h|--help`**

  Gibt eine Beschreibung zur Verwendung des Befehls aus.

## <a name="examples"></a>Beispiele

- Listen Sie alle Projekte in einer Projektmappe auf:

  ```dotnetcli
  dotnet sln todo.sln list
  ```

- Fügen Sie ein C#-Projekt zu einer Projektmappe hinzu:

  ```dotnetcli
  dotnet sln add todo-app/todo-app.csproj
  ```

- Entfernen Sie ein C#-Projekt aus einer Projektmappe:

  ```dotnetcli
  dotnet sln remove todo-app/todo-app.csproj
  ```

- Fügen Sie mehrere C#-Projekte zum Stamm einer Projektmappe hinzu:

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj --in-root
  ```

- Fügen Sie mehrere C#-Projekte zu einer Projektmappe hinzu:

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- Entfernen Sie mehrere C#-Projekte aus einer Projektmappe:

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- Fügen Sie mehrere C#-Projekte zu einer Projektmappe hinzu, indem Sie ein Globmuster (nur UNIX/Linux) verwenden:

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- Fügen Sie mehrere C#-Projekte zu einer Projektmappe hinzu, indem Sie ein Globmuster (nur Windows PowerShell) verwenden:

  ```dotnetcli
  dotnet sln todo.sln add (ls -r **/*.csproj)
  ```

- Entfernen Sie mehrere C#-Projekte aus einer Projektmappe, indem Sie ein Globmuster (nur UNIX/Linux) verwenden:

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```

- Entfernen Sie mehrere C#-Projekte aus einer Projektmappe, indem Sie ein Globmuster (nur Windows PowerShell) verwenden:

  ```dotnetcli
  dotnet sln todo.sln remove (ls -r **/*.csproj)
  ```

- Erstellen Sie eine Projektmappe, eine Konsolen-App und zwei Klassenbibliotheken. Fügen Sie die Projekte zur Projektmappe hinzu, und verwenden Sie die Option `--solution-folder` von `dotnet sln`, um die Klassenbibliotheken in einem Projektmappenordner zu organisieren.

  ```dotnetcli
  dotnet new sln -n mysolution
  dotnet new console -o myapp
  dotnet new classlib -o mylib1
  dotnet new classlib -o mylib2
  dotnet sln mysolution.sln add myapp\myapp.csproj
  dotnet sln mysolution.sln add mylib1\mylib1.csproj --solution-folder mylibs
  dotnet sln mysolution.sln add mylib2\mylib2.csproj --solution-folder mylibs
  ```

  Der folgende Screenshot zeigt das Ergebnis im **Projektmappen-Explorer** von Visual Studio 2019:

  :::image type="content" source="media/dotnet-sln/dotnet-sln-solution-folder.png" alt-text="Projektmappen-Explorer mit Klassenbibliotheksprojekten gruppiert in einem Projektmappenordner":::
