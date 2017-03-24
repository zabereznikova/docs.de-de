---
title: Befehl dotnet-test | Microsoft-Dokumentation
description: "Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet."
keywords: Dotnet-Test, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 4bf0aef4-148a-41c6-bb95-0a9e1af8762e
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 21f3850520b922f16c77f831a045ec58bdf1b5c1
ms.lasthandoff: 03/07/2017

---

#<a name="dotnet-test"></a>Dotnet-Test

## <a name="name"></a>Name

`dotnet-test` – .NET-Testtreiber

## <a name="synopsis"></a>Übersicht

```
dotnet test [project] [-s|--settings] [-t|--list-tests] [--filter] [-a|--test-adapter-path] [-l|--logger] [-c|--configuration] [-f|--framework] [-o|--output] [-d|--diag] [--no-build] [-v|--verbosity]
dotnet test [-h|--help]
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet. Komponententests sind Klassenbibliotheksprojekte, die Abhängigkeiten vom Komponententest-Framework (z.B. NUnit oder xUnit) und dotnet-Test-Runner für dieses Komponententestframework aufweisen. Sie werden als NuGet-Pakete verpackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.

Testprojekte müssen auch den Test Runner angeben. Dieser wird mit einem normalen `<PackageReference>`-Element angegeben, wie in der folgenden Beispielprojektdatei gezeigt:

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="options"></a>Optionen

`project`
    
Gibt den Pfad des Testprojekts an. Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis angegeben.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`-s|--settings <SETTINGS_FILE>`

Einstellungen, die beim Ausführen von Tests verwendet werden. 

`-t|--list-tests`

Listen Sie alle ermittelten Tests im aktuellen Projekt auf. 

`--filter <EXPRESSION>`

Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus. Weitere Informationen zur Filterungsunterstützung finden Sie unter [Running selective unit tests in Visual Studio using TestCaseFilter](https://aka.ms/vstest-filtering).

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf. 

`-l|--logger <LoggerUri/FriendlyName>`

Gibt eine Protokollierung für die Testergebnisse an. 

`-c|--configuration <Debug|Release>`

Konfiguration für die Erstellung. Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.

`-f|--framework <FRAMEWORK>`

Sucht nach Testbinärdateien für ein bestimmtes Framework.

`-o|--output <OUTPUT_DIRECTORY>`

Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei. 

`--no-build` 

Erstellt das Testprojekt nicht vor der Ausführung.

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

## <a name="examples"></a>Beispiele

Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:

`dotnet test` 

Führen Sie die Tests im Projekt test1 durch:

`dotnet test ~/projects/test1/test1.csproj` 

## <a name="see-also"></a>Siehe auch

[Frameworks](../../standard/frameworks.md)

[Runtime-ID-Katalog (RID)](../rid-catalog.md)
