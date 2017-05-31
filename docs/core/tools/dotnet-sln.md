---
title: "Befehl dotnet-sln – .NET Core CLI | Microsoft-Dokumentation"
description: "Der Befehl dotnet-sln bietet eine praktische Option, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten."
keywords: dotnet-sln, CLI, CLI-Befehl, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 04/11/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: e5a72d3e-c14b-4b0a-a978-c5e54a0988c6
ms.translationtype: Human Translation
ms.sourcegitcommit: 7d7f0864ee1641627c4a55192d81ed76f2f44450
ms.openlocfilehash: 0a832765d01609aebd10b13387a4317a6a246c30
ms.contentlocale: de-de
ms.lasthandoff: 04/11/2017

---

# <a name="dotnet-sln"></a>dotnet-sln

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

