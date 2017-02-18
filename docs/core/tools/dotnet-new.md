---
title: Befehl dotnet-new | Microsoft-Dokumentation
description: Der dotnet-new-Befehl erstellt neue .NET Core-Projekte im aktuellen Verzeichnis.
keywords: dotnet-new, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 10/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 263c3d05-3a47-46a6-8023-3ca16b488410
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: a49fe94ca8f678c614fb7f58767693c73e34c737

---

#<a name="dotnet-new"></a>dotnet-new

> [!WARNING]
> Dieses Thema gilt für .NET Core Preview 2-Tools. Informationen zur .NET Core Tools RC4-Version finden Sie im Thema [dotnet-new (.NET Core Tools RC4)](../preview3/tools/dotnet-new.md).

## <a name="name"></a>Name
`dotnet-new`: Erstellt neue .NET Core-Projekte im aktuellen Verzeichnis

## <a name="synopsis"></a>Übersicht
`dotnet new [--help] [--type] [--lang]`

## <a name="description"></a>Beschreibung
Der Befehl `dotnet new` bietet eine bequeme Möglichkeit, ein gültiges .NET Core-Projekt und Beispielquellcode zum Ausprobieren des Befehlszeilenschnittstellen-Toolsets (CLI) zu initialisieren. 

Dieser Befehl wird im Kontext eines Verzeichnisses aufgerufen. Wenn er aufgerufen wird, führt der Befehl dazu, dass zwei wichtige Elemente im aktuellen Verzeichnis abgelegt werden: 

1. Eine Datei `Program.cs` (oder `Program.fs`) mit einem „Hello World“-Beispielprogramm.
2. Eine gültige Datei `project.json`.

Danach kann das Projekt kompiliert und/oder weiter bearbeitet werden. 

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.  

`-l|--lang <C#|F#>`

Die Sprache des Projekts. Wird standardmäßig auf `C#` festgelegt. Weitere gültige Werte sind `csharp`, `fsharp`, `cs` und `fs`.

`-t|--type`

Der Typ des Projekts. Gültige Werte für C# sind `console`, `web`, `lib` und `xunittest`, und für F# nur `console`. 

## <a name="examples"></a>Beispiele

Erstellen Sie ein C#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:

`dotnet new` oder `dotnet new --lang c#` 
   
Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:

`dotnet new --lang f#`
  
Erstellen Sie ein neues ASP.NET Core C#-Anwendungsprojekt im aktuellen Verzeichnis:

`dotnet new -t web`


<!--HONumber=Feb17_HO2-->


