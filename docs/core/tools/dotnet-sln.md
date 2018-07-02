---
title: dotnet sln-Befehl – .NET Core-CLI
description: Der Befehl dotnet-sln bietet eine praktische Option, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten.
author: mairaw
ms.author: mairaw
ms.date: 06/13/2018
ms.openlocfilehash: 65ae402ef5519863886c8cf833598f5314b4bdad
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207796"
---
# <a name="dotnet-sln"></a>dotnet sln

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet sln`: Ändert eine .NET Core-Projektmappendatei.

## <a name="synopsis"></a>Übersicht

```
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a>description

Der Befehl `dotnet sln` bietet eine praktische Möglichkeit, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten.

Die Projektmappendatei muss immer vorhanden sein, um den Befehl `dotnet sln` verwenden zu können. Wenn Sie eine Datei erstellen müssen, verwenden Sie den Befehl [dotnet new](dotnet-new.md) wie in folgendem Beispiel:

```
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
