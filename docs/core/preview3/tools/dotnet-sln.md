---
title: Befehl dotnet-sln | Microsoft-Dokumentation
description: "Der Befehl dotnet-sln bietet eine praktische Option, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten."
keywords: dotnet-run, CLI, CLI-Befehl, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 02/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: e5a72d3e-c14b-4b0a-a978-c5e54a0988c6
translationtype: Human Translation
ms.sourcegitcommit: 6c0474e2964043b6c090ecb4e68b46ff42ca670c
ms.openlocfilehash: c5ed2482222b02b8b50599b48a28afa5922e0135

---
# <a name="dotnet-sln"></a>dotnet-sln

[!INCLUDE[preview-warning](../../../includes/warning.md)]

## <a name="name"></a>Name

`dotnet-sln`: Ändert eine .NET Core-Projektmappendatei.

## <a name="synopsis"></a>Übersicht

```
dotnet sln [<SLN_NAME>] add <project> <project>
dotnet sln [<SLN_NAME>] add **/**
dotnet sln [<SLN_NAME>] remove <project> <project>
dotnet sln [<SLN_NAME>] remove **/**
dotnet sln [<SLN_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet sln` bietet eine praktische Möglichkeit, Projekte zu einer Projektmappendatei hinzuzufügen, Projekte aus einer Projektmappendatei zu entfernen oder die in einer Projektmappendatei enthaltenen Projekte aufzulisten.

## <a name="commands"></a>Befehle

`add <project>`

`add **/*`

Fügt mindestens ein Projekt zur Projektmappendatei hinzu. Globmuster wird auf Unix/Linux-basierten Terminals unterstützt.

`remove <project>`

`remove **/*`

Entfernt mindestens ein Projekt aus der Projektmappendatei. Globmuster wird auf Unix/Linux-basierten Terminals unterstützt.

`list`

Listet alle Projekte auf, die in einer Projektmappendatei enthalten sind.

## <a name="arguments"></a>Argumente

`SLN_NAME`

Die zu verwendende Projektmappendatei. Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektmappendatei. Gibt es mehrere Projektmappendateien in dem Verzeichnis, muss eine angegeben werden.

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

## <a name="examples"></a>Beispiele

Fügen Sie ein Projekt zu einer Projektmappe hinzu:

`dotnet sln todo.sln add todo-app/todo-app.csproj`

Fügen Sie ein Projekt zur Projektmappe im aktuellen Verzeichnis hinzu:

`dotnet sln add todo-app.csproj`

Entfernen Sie ein Projekt aus einer Projektmappe:

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

Fügen Sie mehrere Projekte zu einer Projektmappe hinzu, indem Sie ein Muster zur Verwendung von Platzhaltern verwenden:

`dotnet sln add **/**/*.fsproj`



<!--HONumber=Feb17_HO2-->


