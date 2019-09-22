---
title: Befehl „dotnet sln“
description: Der Befehl dotnet-sln bietet eine praktische Option, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten.
ms.date: 06/13/2018
ms.openlocfilehash: 84508aaefff61b31e2965576ebc2daaae7331951
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117589"
---
# <a name="dotnet-sln"></a>dotnet sln

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>NAME

`dotnet sln`: Ändert eine .NET Core-Projektmappendatei.

## <a name="synopsis"></a>Zusammenfassung

```dotnetcli
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a>BESCHREIBUNG

Der Befehl `dotnet sln` bietet eine praktische Möglichkeit, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten.

Die Projektmappendatei muss immer vorhanden sein, um den Befehl `dotnet sln` verwenden zu können. Wenn Sie eine Datei erstellen müssen, verwenden Sie den Befehl [dotnet new](dotnet-new.md) wie in folgendem Beispiel:

```dotnetcli
dotnet new sln
```

## <a name="commands"></a>Befehle

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

Fügt mindestens ein Projekt zur Projektmappendatei hinzu. [Globbing patterns (Globmuster)](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Terminals unterstützt.

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

Entfernt mindestens ein Projekt aus der Projektmappendatei. [Globbing patterns (Globmuster)](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Terminals unterstützt.

`list`

Listet alle Projekte auf, die in einer Projektmappendatei enthalten sind.

## <a name="arguments"></a>Argumente

`SOLUTION_NAME`

Die zu verwendende Projektmappendatei. Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei. Gibt es mehrere Projektmappendateien in dem Verzeichnis, muss eine angegeben werden.

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

## <a name="examples"></a>Beispiele

Fügen Sie ein C#-Projekt zu einer Projektmappe hinzu:

`dotnet sln todo.sln add todo-app/todo-app.csproj`

Entfernen Sie ein C#-Projekt aus einer Projektmappe:

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

Fügen Sie mehrere C#-Projekte zu einer Projektmappe hinzu:

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

Entfernen Sie mehrere C#-Projekte aus einer Projektmappe:

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

Fügen Sie mehrere C#-Projekte zu einer Projektmappe hinzu, indem Sie ein Globmuster verwenden:

`dotnet sln todo.sln add **/*.csproj`

Entfernen Sie mehrere C#-Projekte aus einer Projektmappe, indem Sie ein Globmuster verwenden:

`dotnet sln todo.sln remove **/*.csproj`

> [!NOTE]
> Globbing ist kein Feature der CLI, sondern der Befehlsshell. Um die Dateien erfolgreich zu erweitern, müssen Sie eine Shell verwenden, die Globbing unterstützt. Weitere Informationen zum Globbing finden Sie bei [Wikipedia](https://en.wikipedia.org/wiki/Glob_(programming)).
