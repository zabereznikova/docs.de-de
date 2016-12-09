---
title: Dotnet-run-Befehl | .NET Core-SDK
description: "Der dotnet-run-Befehl bietet eine praktische Option zum Ausführen der Anwendung aus dem Quellcode."
keywords: dotnet-run, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 495ff50b-cb30-4d30-8f20-beb3d5e7c31f
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: 6f95125640e7341426c3a019771a6b8595d10e73

---

#<a name="dotnet-run"></a>dotnet-run

## <a name="name"></a>Name 

dotnet-run – Führt Quellcode "in-Place" ohne explizite Kompilierung oder Startbefehle aus

## <a name="synopsis"></a>Übersicht

`dotnet run [--help] [--framework] [--configuration]
    [--project] [[--] [application arguments]]`

## <a name="description"></a>Beschreibung
Der `dotnet run`-Befehl bietet eine praktische Option zum Ausführen der Anwendung aus dem Quellcode mit einem Befehl. Kompiliert Quellcode, erzeugt ein Ausgabeprogramm und führt dieses Programm aus. Dieser Befehl eignet sich für eine schnelle iterative Entwicklung und kann auch zum Ausführen eines quellenverteilten Programms (z.B. einer Website) verwendet werden.

Dieser Befehl basiert auf [Dotnet Build](dotnet-build.md) zum Erstellen von Quelleingaben für eine .NET-Assembly, bevor das Programm gestartet wird. Die Anforderungen für diesen Befehl und die Verarbeitung von Quelleingaben werden vom Buildbefehl geerbt. Die Dokumentation für den Buildbefehl enthält weitere Informationen zu diesen Anforderungen.

Ausgabedateien werden in den untergeordneten *Bin*-Ordner geschrieben, der erstellt wird, wenn er nicht vorhanden ist. Dateien werden bei Bedarf überschrieben. Temporäre Dateien werden in den untergeordneten *Obj*-Ordner geschrieben.  

Im Falle eines Projekts mit mehreren angegebenen Frameworks wählt `dotnet run` zuerst die .NET Core-Frameworks aus. Wenn diese nicht vorhanden sind, tritt ein Fehler auf. Verwenden Sie zum Angeben anderer Frameworks das Argument `--framework`.

Der Befehl `dotnet run` muss im Kontext von Projekten, nicht erstellter Assemblys verwendet werden. Wenn Sie stattdessen eine portable Anwendungs-DLL ausführen möchten, verwenden Sie [dotnet](dotnet.md) ohne jeden Befehl wie im folgenden Beispiel:
 
`dotnet myapp.dll`

Weitere Informationen zu den `dotnet`-Treibern finden Sie unter dem Thema [.NET Core-Befehlszeilentools (CLI)](index.md).

## <a name="options"></a>Optionen

`--`

Grenzt Argumente für `dotnet run` von Argumenten für die ausgeführte Anwendung ab. Alle nachfolgenden Argumente werden der ausgeführten Anwendung übergeben. 

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`-f`, `--framework <FRAMEWORK_IDENTIFIER>`

Führt die Anwendung für eine bestimmte Framework-ID (FID) aus. 

`-c`, `--configuration <Debug|Release>`

Konfiguration bei der Veröffentlichung. Der Standardwert ist `Debug`.

`-p`, `--project [PATH]`

Gibt an, welches Projekt auszuführen ist. Es kann entweder ein Pfad zu einer [CSPROJ](csproj.md)-Datei oder zu einem Verzeichnis mit einer [CSPROJ](csproj.md)-Datei sein. Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt. 

## <a name="examples"></a>Beispiele

Führt das Projekt im aktuellen Verzeichnis aus: `dotnet run` 

Führt das angegebene Projekt aus:

`dotnet run --project /projects/proj1/proj1.csproj`

Führt das Projekt im aktuellen Verzeichnis aus (das Argument `--help` in diesem Beispiel wird der ausgeführten Anwendung übergeben, da das Argument `--` verwendet wurde):

`dotnet run --configuration Release -- --help`


<!--HONumber=Nov16_HO3-->


