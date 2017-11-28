---
title: "dotnet sln-Befehl – .NET Core-CLI"
description: "Der Befehl dotnet-sln bietet eine praktische Option, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 5071cb80be0fb14829a0fdffd0f5a2d2371b6ba8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-sln"></a>dotnet sln

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Name

`dotnet-sln`: Ändert eine .NET Core-Projektmappendatei.

## <a name="synopsis"></a>Übersicht

```
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet sln` bietet eine praktische Möglichkeit, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten.

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