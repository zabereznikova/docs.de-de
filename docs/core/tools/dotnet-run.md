---
title: "Befehl dotnet-run – .NET Core CLI | Microsoft-Dokumentation"
description: "Der dotnet-run-Befehl bietet eine praktische Option zum Ausführen der Anwendung aus dem Quellcode."
keywords: dotnet-run, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/22/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 40d4e60f-9900-4a48-b03c-0bae06792d91
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: 49e6738a90663645f761bb7748a723624ad8fdc6
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-run"></a>dotnet-run

## <a name="name"></a>Name 

`dotnet-run`: Führt Quellcode ohne explizite Kompilierungs- oder Startbefehle aus.

## <a name="synopsis"></a>Übersicht

`dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]] [-h|--help]`

## <a name="description"></a>Beschreibung

Der `dotnet run`-Befehl bietet eine praktische Option zum Ausführen der Anwendung aus dem Quellcode mit einem Befehl. Es empfiehlt sich für eine schnelle iterative Entwicklung aus der Befehlszeile. Der Befehl hängt vom [`dotnet build`](dotnet-build.md)-Befehl ab, um den Code zu erstellen. Alle Anforderungen für den Build, z.B. dass das Projekt zuerst wiederhergestellt werden muss, werden auch auf `dotnet run` angewendet. 

Ausgabedateien werden im Standardspeicherort `bin/<configuration>/<target>` geschrieben. Angenommen, Sie haben eine `netcoreapp1.0`-Anwendung und Sie führen `dotnet run` aus, dann wird die Ausgabe in `bin/Debug/netcoreapp1.0` platziert. Dateien werden bei Bedarf überschrieben. Temporäre Dateien befinden sich im `obj`-Verzeichnis. 

Wenn das Projekt mehrere Frameworks angibt, führt das Ausführen von `dotnet run` zu einem Fehler, wenn nicht die `-f|--framework <FRAMEWORK>`-Option verwendet wird, um das Framework anzugeben.

Der Befehl `dotnet run` wird im Kontext von Projekten verwendet, nicht von erstellten Assemblys. Wenn Sie stattdessen eine Framework-abhängige DLL-Anwendung ausführen möchten, müssen Sie [dotnet](dotnet.md) ohne einen Befehl verwenden. Zum Ausführen von `myapp.dll` verwenden Sie z.B.:
 
```
dotnet myapp.dll
```

Weitere Informationen zum `dotnet`-Treiber finden Sie unter dem Thema [.NET Core-Befehlszeilentools (CLI)](index.md).

Um die Anwendung auszuführen, löst der `dotnet run`-Befehl die Abhängigkeiten der Anwendung außerhalb der freigegebenen Laufzeit aus dem NuGet-Cache. Da sie zwischengespeicherte Abhängigkeiten verwendet, wird nicht empfohlen, `dotnet run` zur Ausführung der Anwendungen in der Produktion zu verwenden. Stattdessen [erstellen Sie eine Bereitstellung](../deploying/index.md) mithilfe des [`dotnet publish`](dotnet-publish.md)-Befehls und stellen die veröffentlichte Ausgabe bereit. 

## <a name="options"></a>Optionen

`--`

Grenzt Argumente für `dotnet run` von Argumenten für die ausgeführte Anwendung ab. Alle nachfolgenden Argumente werden der Anwendungsausführung übergeben. 

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`-c|--configuration <CONFIGURATION>`

Konfiguration, die beim Erstellen des Projekts verwendet wird. Der Standardwert ist `Debug`.

`-f|--framework <FRAMEWORK>`

Erstellt und führt die Anwendung mithilfe des angegebenen [Frameworks](../../standard/frameworks.md) aus. Das Framework muss in der Projektdatei angegeben werden.

`-p|--project <PATH/PROJECT.csproj>`

Gibt den Pfad und Namen der Projektdatei an. (Siehe HINWEIS.) Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt.

> [!NOTE]
> Verwenden Sie den Pfad und Namen der Projektdatei mit der `-p|--project`-Option. Eine Regression in der CLI verhindert, dass zu diesem Zeitpunkt ein Pfad bereitgestellt wird. Weitere Informationen und eine Überwachung dieses Problems finden Sie unter [dotnet run -p, can not start a project (dotnet/cli #5992) (dotnet run -p, ein Projekt kann nicht gestartet werden (dotnet/cli #5992))](https://github.com/dotnet/cli/issues/5992).

## <a name="examples"></a>Beispiele

Führt das Projekt im aktuellen Verzeichnis aus:

`dotnet run` 

Führt das angegebene Projekt aus:

`dotnet run --project /projects/proj1/proj1.csproj`

Führt das Projekt im aktuellen Verzeichnis aus (das Argument `--help` in diesem Beispiel wird der Anwendung übergeben, da das Argument `--` verwendet wird):

`dotnet run --configuration Release -- --help`

