---
title: Befehl dotnet-run | Microsoft-Dokumentation
description: "Der dotnet-run-Befehl bietet eine praktische Option zum Ausführen der Anwendung aus dem Quellcode."
keywords: dotnet-run, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 40d4e60f-9900-4a48-b03c-0bae06792d91
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 60bb9160e43788539b0dc6bcf1372bb925e9ba22
ms.lasthandoff: 03/07/2017

---

#<a name="dotnet-run"></a>dotnet-run

## <a name="name"></a>Name 

`dotnet-run`: Führt Quellcode „in-place“ (direkt) ohne explizite Kompilierungs- oder Startbefehle aus

## <a name="synopsis"></a>Übersicht

```
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

## <a name="description"></a>Beschreibung

Der `dotnet run`-Befehl bietet eine praktische Option zum Ausführen der Anwendung aus dem Quellcode mit einem Befehl. Es empfiehlt sich für eine schnelle iterative Entwicklung in der Befehlszeile. Der Befehl hängt vom [`dotnet build`](dotnet-build.md)-Befehl ab, um den Code zu erstellen, sodass Anforderungen für das Build und dieses Projekt zuerst erstellt werden müssen. Wenden Sie dies auch auf `dotnet run` an. 

Ausgabedateien werden im Standardspeicherort `bin/<configuration>/<target>` geschrieben. Angenommen, Sie haben eine `netcoreapp1.0`-Anwendung und Sie führen `dotnet run` aus, dann wird die Ausgabe in `bin/Debug/netcoreapp1.0` platziert. Dateien werden bei Bedarf überschrieben. Temporäre Dateien befinden sich im `obj`-Verzeichnis. 

Im Falle eines Projekts mit mehreren angegebenen Frameworks zeigt `dotnet run` einen Fehler an, es sei denn, die `--framework`-Option wird verwendet, um anzugeben, für welches Framework die Anwendung ausgeführt wird.

Der Befehl `dotnet run` muss im Kontext von Projekten, nicht erstellter Assemblys verwendet werden. Wenn Sie stattdessen eine portable Anwendungs-DLL ausführen möchten, verwenden Sie [dotnet](dotnet.md) ohne jeden Befehl wie im folgenden Beispiel:
 
`dotnet myapp.dll`

Weitere Informationen zu den `dotnet`-Treibern finden Sie unter dem Thema [.NET Core-Befehlszeilentools (CLI)](index.md).

Um die Anwendung auszuführen, löst der `dotnet run`-Befehl die Abhängigkeiten der Anwendung außerhalb der freigegebenen Laufzeit aus dem NuGet-Cache. Deshalb wird davon abgeraten, diesen Befehl zur Ausführung der Anwendung in der Produktion zu verwenden. Stattdessen sollten Sie eine [Bereitstellung erstellen](../deploying/index.md) und zwar mithilfe des [`dotnet publish`](dotnet-publish.md)-Befehls und sie in der Produktion verwenden. 

## <a name="options"></a>Optionen

`--`

Grenzt Argumente für `dotnet run` von Argumenten für die ausgeführte Anwendung ab. Alle nachfolgenden Argumente werden der ausgeführten Anwendung übergeben. 

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`-c|--configuration {Debug|Release}`

Konfiguration, die beim Erstellen des Projekts verwendet wird. Der Standardwert ist `Debug`.

`-f|--framework <FRAMEWORK_IDENTIFIER>`

Erstellt und führt die Anwendung mithilfe des angegebenen Frameworks aus. Das Framework muss in der Projektdatei angegeben werden.

`-p|--project <PATH>`

Gibt den Pfad zur ausführenden Projektdatei an. Es kann entweder ein Pfad zu einer [CSPROJ](csproj.md)-Datei oder zu einem Verzeichnis mit einer [CSPROJ](csproj.md)-Datei sein. Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt. 

## <a name="examples"></a>Beispiele

Führt das Projekt im aktuellen Verzeichnis aus:

`dotnet run` 

Führt das angegebene Projekt aus:

`dotnet run --project /projects/proj1/proj1.csproj`

Führt das Projekt im aktuellen Verzeichnis aus (das Argument `--help` in diesem Beispiel wird der ausgeführten Anwendung übergeben, da das Argument `--` verwendet wurde):

`dotnet run --configuration Release -- --help`
