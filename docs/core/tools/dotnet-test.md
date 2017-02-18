---
title: Befehl dotnet-test | Microsoft-Dokumentation
description: "Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet."
keywords: Dotnet-Test, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 3a0fa917-eb0a-4d7e-9217-d06e65455675
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 871a6f736272309f6fae74b06f437c7271df2321

---

#<a name="dotnet-test"></a>Dotnet-Test

> [!WARNING]
> Dieses Thema gilt für .NET Core Preview 2-Tools. Informationen zur .NET Core Tools RC4-Version finden Sie im Thema [dotnet-test (.NET Core Tools RC4)](../preview3/tools/dotnet-test.md).

## <a name="name"></a>Name

`dotnet-test`: Führt Komponententests mit konfiguriertem Test Runner durch

## <a name="synopsis"></a>Übersicht

`dotnet test [project] [--help] 
    [--parentProcessId] [--port] [--configuration]   
    [--output] [--build-base-path] [--framework] [--runtime]
    [--no-build]`  

## <a name="description"></a>Beschreibung

Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet. Komponententests sind Klassenbibliotheksprojekte, die Abhängigkeiten vom Komponententest-Framework (z.B. NUnit oder xUnit) und dotnet-Test-Runner für dieses Komponententestframework aufweisen. Sie werden als NuGet-Pakete verpackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.

Testprojekte müssen auch mithilfe des Knotens „testRunner“ einen Test Runner-Eigenschaft in project.json angeben. Dieser Wert sollte den Namen des Komponententestframeworks enthalten.

Das folgende Beispiel project.json zeigt die erforderlichen Eigenschaften:

```json
{
  "version": "1.0.0-*",
  "buildOptions": {
    "debugType": "portable"
  },
  "dependencies": {
    "System.Runtime.Serialization.Primitives": "4.1.1",
    "xunit": "2.1.0",
    "dotnet-test-xunit": "1.0.0-rc2-192208-24"
  },
  "testRunner": "xunit",
  "frameworks": {
    "netcoreapp1.0": {
      "dependencies": {
        "Microsoft.NETCore.App": {
          "type": "platform",
          "version": "1.0.0"
        }
      },
      "imports": [
        "dotnet5.4",
        "portable-net451+win8"
      ]
    }
  }
}
```

`dotnet test` unterstützt zwei ausführende Modi:

1. Konsole: Im Konsolenmodus führt `dotnet test` einfach alle an ihn übergebenen Befehle vollständig aus und gibt die Ergebnisse aus. Jedes Mal, wenn Sie `dotnet test` aufrufen, ohne den Port aufzurufen, wird es im Konsolenmodus ausgeführt, wodurch wiederum der Runner im Konsolenmodus ausgeführt wird.
2. Entwurfszeit: im Kontext anderer Tools, wie Editoren oder Integrierter Entwicklungsumgebungen (IDEs) verwendet. Sie finden weitere Informationen zu diesem Modus in der Datei [Dotnet-Testprotokoll](test-protocol.md). 

## <a name="options"></a>Optionen

`[project]`
    
Gibt den Pfad des Testprojekts an. Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis angegeben.

`-?|-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`--parentProcessId`

Wird von IDEs verwendet, um ihre Prozess-ID anzugeben. Test wird beendet, wenn der übergeordnete Prozess beendet wird.

`--port`

Wird von IDEs verwendet, um eine Portnummer für die Überwachung einer Verbindung anzugeben.

`-c|--configuration <Debug|Release>`

Konfiguration für die Erstellung. Der Standardwert ist `Release`. 

`-o|--output [OUTPUT_DIRECTORY]`

Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.

`-b|--build-base-path <OUTPUT_DIRECTORY>`

Verzeichnis, in dem temporäre Ausgaben platziert werden.

`-f|--framework [FRAMEWORK]`

Sucht nach Testbinärdateien für ein bestimmtes Framework.

`-r|--runtime [RUNTIME_IDENTIFIER]`

Suchen Sie nach den Testbinärdateien für die angegebene Laufzeit.

`--no-build` 

Erstellt das Testprojekt nicht vor der Ausführung. 

## <a name="examples"></a>Beispiele

Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:

`dotnet test` 

Führen Sie die Tests im Projekt test1 durch:

`dotnet test /projects/test1/project.json` 

## <a name="see-also"></a>Siehe auch

[Kommunikationsprotokoll dotnet-Test](test-protocol.md)

[Frameworks](../../standard/frameworks.md)

[Runtime-ID-Katalog (RID)](../rid-catalog.md)


<!--HONumber=Feb17_HO2-->


