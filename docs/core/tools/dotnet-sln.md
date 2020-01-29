---
title: Befehl „dotnet sln“
description: Der Befehl dotnet-sln bietet eine praktische Option, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten.
ms.date: 10/29/2019
ms.openlocfilehash: e344deaae0867202a79a3c38df48a2be8d4d7d13
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733082"
---
# <a name="dotnet-sln"></a>dotnet sln

**Dieser Artikel gilt für:** ✔️ .NET Core 1.x SDK und neuere Versionen

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>name

`dotnet sln`: Ändert eine .NET Core-Projektmappendatei.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command] [-h|--help]
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet sln` bietet eine praktische Möglichkeit, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten.

Die Projektmappendatei muss immer vorhanden sein, um den Befehl `dotnet sln` verwenden zu können. Wenn Sie eine Datei erstellen müssen, verwenden Sie den Befehl [dotnet new](dotnet-new.md) wie in folgendem Beispiel:

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a>Argumente

- **`SOLUTION_FILE`**

  Dies ist die zu verwendende Projektmappendatei. Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei. Gibt es mehrere Projektmappendateien in dem Verzeichnis, muss eine angegeben werden.

## <a name="options"></a>Optionen

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

## <a name="commands"></a>Befehle

### `add`

Fügt mindestens ein Projekt zur Projektmappendatei hinzu.

#### <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder] <PROJECT_PATH>
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a>Argumente

- **`SOLUTION_FILE`**

  Dies ist die zu verwendende Projektmappendatei. Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei. Gibt es mehrere Projektmappendateien in dem Verzeichnis, muss eine angegeben werden.

- **`PROJECT_PATH`**

  Dies ist der Pfad zum Projekt, das zur Projektmappe hinzugefügt werden soll. Fügen Sie mehrere Projekte hinzu, indem Sie diese durch Leerzeichen getrennt nacheinander hinzufügen. UNIX-/Linux-Shell-[Globmustererweiterungen](https://en.wikipedia.org/wiki/Glob_(programming)) werden ordnungsgemäß mit dem `dotnet sln`-Befehl verarbeitet.

#### <a name="options"></a>Optionen

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

- **`--in-root`**

  Hiermit werden die Projekte im Stamm der Projektmappe platziert anstatt einen Projektmappenordner zu erstellen. Verfügbar seit .NET Core 3.0 SDK.

- **`-s|--solution-folder`**

  Dies ist der Zielpfad des Projektmappenordners, dem die Projekte hinzugefügt werden sollen. Verfügbar seit .NET Core 3.0 SDK.

### `remove`

Entfernt mindestens ein Projekt aus der Projektmappendatei.

#### <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH>
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a>Argumente

- **`SOLUTION_FILE`**

  Dies ist die zu verwendende Projektmappendatei. Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei. Gibt es mehrere Projektmappendateien in dem Verzeichnis, muss eine angegeben werden.

- **`PROJECT_PATH`**

  Dies ist der Pfad zum Projekt, das aus der Projektmappe entfernt werden soll. Sie können mehrere Projekte entfernen, indem Sie diese durch Leerzeichen getrennt nacheinander hinzufügen. UNIX-/Linux-Shell-[Globmustererweiterungen](https://en.wikipedia.org/wiki/Glob_(programming)) werden ordnungsgemäß mit dem `dotnet sln`-Befehl verarbeitet.

#### <a name="options"></a>Optionen

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

### `list`

Listet alle Projekte auf, die in einer Projektmappendatei enthalten sind.

#### <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a>Argumente

- **`SOLUTION_FILE`**

  Dies ist die zu verwendende Projektmappendatei. Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei. Gibt es mehrere Projektmappendateien in dem Verzeichnis, muss eine angegeben werden.

#### <a name="options"></a>Optionen

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

## <a name="examples"></a>Beispiele

- Fügen Sie ein C#-Projekt zu einer Projektmappe hinzu:

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj
  ```

- Entfernen Sie ein C#-Projekt aus einer Projektmappe:

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj
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

- Entfernen Sie mehrere C#-Projekte aus einer Projektmappe, indem Sie ein Globmuster (nur UNIX/Linux) verwenden:

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```
