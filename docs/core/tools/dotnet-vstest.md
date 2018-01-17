---
title: "dotnet vstest-Befehl – .NET Core-CLI"
description: "Der dotnet vstest-Befehl erstellt ein Projekt und alle seine Abhängigkeiten."
author: guardrex
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: f2ad875430b2dc7f0ffbadfb9a39dd83854557cb
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2018
---
# <a name="dotnet-vstest"></a>dotnet vstest

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet-vstest`: Führt Tests auf Grundlage der angegebenen Dateien aus.

## <a name="synopsis"></a>Übersicht

`dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath] [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger] [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]`

## <a name="description"></a>description

Der `dotnet-vstest`-Befehl führt die `VSTest.Console`-Befehlszeilenanwendung aus, um automatisierte Komponententests und Tests der codierten UI-Anwendung auszuführen.

## <a name="arguments"></a>Argumente

`TEST_FILE_NAMES`

Führt Tests auf Grundlage der angegebenen Assemblys aus. Trennt mehrere Test-Assemblynamen durch Leerzeichen.

## <a name="options"></a>Optionen

`--Settings|/Settings:<Settings File>`

Einstellungen, die beim Ausführen von Tests verwendet werden.

`--Tests|/Tests:<Test Names>`

Führt Tests aus, die mit den eingegebenen Werten übereinstimmen. Trennt mehrere Werte per Komma voneinander ab.

`--TestAdapterPath|/TestAdapterPath`

Verwendet benutzerdefinierte Testadapter aus einem angegebenen Pfad (falls vorhanden) im Testlauf.

`--Platform|/Platform:<Platform type>`

Verwendete Zielplattformarchitektur für die Testausführung. Gültige Werte sind `x86`, `x64` und `ARM`.

`--Framework|/Framework:<Framework Version>`

.NET Framework-Zielversion, in der der Test ausgeführt wird. Beispiele für gültige Werte sind `.NETFramework,Version=v4.6`, `.NETCoreApp,Version=v1.0` usw. Andere unterstützte Werte sind `Framework35`, `Framework40`, `Framework45` und `FrameworkCore10`.

`--Parallel|/Parallel`

Führt Tests parallel aus. Standardmäßig stehen alle verfügbaren Kerne auf dem Computer zur Nutzung zur Verfügung. Legt eine explizite Zahl an Kernen mit einer Einstellungsdatei fest.

`--TestCaseFilter|/TestCaseFilter:<Expression>`

Führt Tests aus, die mit dem angegebenen Ausdruck übereinstimmen. `<Expression>` hat das Format `<property>Operator<value>[|&<Expression>]`, wobei der Operator `=`, `!=`, oder `~` ist.  Operator `~` verfügt über „contains“-Semantik und gilt für Zeichenfolgeneigenschaften wie `DisplayName`. Klammern `()` werden verwendet, um untergeordnete Ausdrücke zu gruppieren.

`-?|--Help|/?|/Help`

Druckt eine kurze Hilfe für den Befehl.

`--logger|/logger:<Logger Uri/FriendlyName>`

Geben Sie eine Protokollierung für die Testergebnisse an.  

* Verwenden Sie den `TfsPublisher`-Protokollierungsanbieter zum Veröffentlichen von Testergebnissen in Team Foundation Server:

  ```
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* Verwenden Sie zum Protokollieren von Ergebnissen in einer Visual Studio-Testergebnisdatei (TRX) den `trx`-Protokollierungsanbieter. Dieser Schalter erstellt eine Datei im Verzeichnis mit den Testergebnissen mit dem angegebenen Protokolldateinamen. Wenn `LogFileName` nicht angegeben wird, wird ein eindeutiger Dateiname erstellt, um die Testergebnisse aufzunehmen.

  ```
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

Listet gefundene Tests aus dem angegebenen Testcontainer auf.

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

Prozess-ID des übergeordneten Prozesses, der für den Start des aktuellen Prozesses verantwortlich ist.

`--Port|/Port:<Port>`

Gibt den Port für die Socketverbindung an und empfängt die Ereignismeldungen.

`--Diag|/Diag:<Path to log file>`

Aktiviert die ausführlichen Protokolle für die Testplattform. Protokolle werden in die angegebene Datei geschrieben.

`args`

Gibt zusätzliche Argumente an, die an den Adapter übergeben werden sollen. Argumente werden als Name-Wert-Paare des Formulars `<n>=<v>` angegeben, wobei `<n>` der Argumentname und `<v>` der Argumentwert ist. Trennt mehrere Argumente durch Leerzeichen.

## <a name="examples"></a>Beispiele

Führt Tests in `mytestproject.dll` aus:

`dotnet vstest mytestproject.dll`

Führen Sie Tests in `mytestproject.dll` aus, und exportieren Sie sie in den benutzerdefinierten Ordner mit benutzerdefiniertem Namen:

`dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path`

Führt Tests in `mytestproject.dll` und `myothertestproject.exe` aus:

`dotnet vstest mytestproject.dll myothertestproject.exe`

Führt `TestMethod1`-Tests aus:

`dotnet vstest /Tests:TestMethod1`

Führt `TestMethod1`- und `TestMethod2`-Tests aus:

`dotnet vstest /Tests:TestMethod1,TestMethod2`

