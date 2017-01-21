---
title: Dotnet-new-Befehl | .NET Core
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
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 7483dc92bec60f3ce97242dceb26abec829fdca1

---

#<a name="dotnet-new"></a>dotnet-new

## <a name="name"></a>Name
dotnet-new – Erstellt neue .NET Core-Projekte im aktuellen Verzeichnis

## <a name="synopsis"></a>Übersicht
`dotnet new [--help] [--type] [--lang]`

## <a name="description"></a>Beschreibung
Der Befehl `dotnet new` bietet eine bequeme Möglichkeit, ein gültiges .NET Core-Projekt und Beispielquellcode zum Ausprobieren des Befehlszeilenschnittstellen-Toolsets (CLI) zu initialisieren. 

Dieser Befehl wird im Kontext eines Verzeichnisses aufgerufen. Wenn er aufgerufen wird, führt der Befehl dazu, dass zwei wichtige Elemente im aktuellen Verzeichnis abgelegt werden: 

1. Eine Datei `Program.cs` (oder `Program.fs`) mit einem „Hello World“-Beispielprogramm.
2. Eine gültige CSPROJ-Projektdatei.

Danach kann das Projekt kompiliert und/oder weiter bearbeitet werden. 

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.  

`-l|--lang C#`

Die Sprache des Projekts. Wird standardmäßig auf `C#` festgelegt. Weitere gültige Werte sind `csharp` und `cs`.

`-t|--type`

Der Typ des Projekts. Gültige Werte für C# sind `console`, `web`, `lib` und `xunittest`, und für F# nur `console`. 

## <a name="examples"></a>Beispiele

Erstellen Sie ein C#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:

`dotnet new` oder `dotnet new --lang c#` 
   
Erstellen Sie ein neues ASP.NET Core C#-Anwendungsprojekt im aktuellen Verzeichnis:

`dotnet new -t web`



<!--HONumber=Jan17_HO3-->


