---
title: Befehl dotnet-publish | Microsoft-Dokumentation
description: "Der dotnet-publish-Befehl veröffentlicht ein .NET Core-Projekt in ein Verzeichnis."
keywords: dotnet-publish, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8a7e1c52-5c57-4bf5-abad-727450ebeefd
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 1cf1611ab83874ad44855521d21040d102206338

---

#<a name="dotnet-publish"></a>dotnet-publish

> [!WARNING]
> Dieses Thema gilt für .NET Core Preview 2-Tools. Informationen zur .NET Core Tools RC4-Version finden Sie im Thema [dotnet-publish (.NET Core Tools RC4)](../preview3/tools/dotnet-publish.md).

## <a name="name"></a>Name

`dotnet-publish`: Packt die Anwendung und alle ihre Abhängigkeiten in einen Ordner, bereit für die Veröffentlichung

## <a name="synopsis"></a>Übersicht

`dotnet publish [project] 
    [--help] [--framework]  
    [--runtime] [--build-base-path] [--output]  
    [--version-suffix] [--configuration] [--native-subdirectory] [--no-build]`

## <a name="description"></a>Beschreibung

`dotnet publish` kompiliert die Anwendung, liest ihre Abhängigkeiten, die in der Datei [project.json](project-json.md) angegeben sind, und veröffentlicht die resultierenden Dateien in einem Verzeichnis. 

Je nach Art der portablen App wird das resultierende Verzeichnis Folgendes enthalten:

1. *Portable Anwendung* – Anwendungscode in Zwischensprache (IL) und alle von der Anwendung verwalteten Abhängigkeiten.
    * *Portable Anwendung mit nativen Abhängigkeiten* – wie oben mit einem Unterverzeichnis für die unterstützte Plattform jeder nativen Abhängigkeit. 
2. *Eigenständige Anwendung* – wie oben, sowie die gesamte Laufzeit für die Zielplattform.

Weitere Informationen finden Sie unter [.NET Core Anwendungsbereitstellung](../deploying/index.md).

## <a name="options"></a>Optionen

`[project]` 

Das zu veröffentlichende Projekt – standardmäßig das aktuelle Verzeichnis, wenn `[project]` nicht angegeben ist. Dieser Wert kann ein Pfad zu der Datei [project.json](project-json.md) oder in das Projektverzeichnis sein, das die Datei [project.json](project-json.md) enthält. Wenn keine Datei [project.json](project-json.md) gefunden werden kann, löst `dotnet publish` einen Fehler aus. 

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.  

`-f|--framework <FRAMEWORK>`

Veröffentlicht die Anwendung für eine bestimmte Framework-ID (FID). Wenn nicht angegeben, wird die FID aus [project.json](project-json.md#frameworks) ausgelesen. Wenn keine gültige Framework-ID gefunden wird, löst der Befehl einen Fehler aus. Wenn mehrere gültige Frameworks gefunden werden, veröffentlicht der Befehl für alle gültigen Frameworks. 

`-r|--runtime <RUNTIME_IDENTIFIER>`

Veröffentlicht die Anwendung für eine bestimmte Laufzeit. Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).

`-b|--build-base-path <OUTPUT_DIRECTORY>`

Verzeichnis, in dem temporäre Ausgaben platziert werden.

`-o|--output <OUTPUT_PATH>`

Geben Sie den Pfad für das Verzeichnis an. Wenn nicht angegeben, wird standardmäßig *_./bin/[configuration]/[framework]/_* für portable Applikationen oder *_./bin/[configuration]/[framework]/[runtime]_* für eigenständige Bereitstellungen gewählt.

`--version-suffix [VERSION_SUFFIX]`

Definiert, durch was `*` im Versionsfeld der Datei „project.json“ ersetzt werden soll.

`-c|--configuration [Debug|Release]`

Konfiguration bei der Veröffentlichung. Der Standardwert ist `Debug`.

`[--native-subdirectory]` Temporärer Mechanismus zum Einschließen der Unterverzeichnisse nativer Elemente der Abhängigkeitspakete in der Ausgabe. 

`[--no-build]` Erstellt keine Projekte vor der Veröffentlichung.

## <a name="examples"></a>Beispiele

Veröffentlichen einer Anwendung mithilfe des Frameworks in `project.json`. Wenn `project.json` [Laufzeiten](project-json.md#runtimes)-Knoten enthält, wird für die RID der aktuellen Plattform veröffentlicht.

`dotnet publish`

Veröffentlichen der Anwendung unter Verwendung der angegebenen Datei [project.json](project-json.md):

`dotnet publish ~/projects/app1/project.json`
    
Veröffentlichen der aktuellen Anwendung mithilfe des Frameworks `netcoreapp1.0`:

`dotnet publish --framework netcoreapp1.0`
    
Veröffentlichen der aktuellen Anwendung mithilfe des Frameworks `netcoreapp1.0` und Runtime für `OS X 10.10` (die RID muss in dem `project.json` [Laufzeiten](project-json.md#runtimes)-Knoten vorhanden sein):

`dotnet publish --framework netcoreapp1.0 --runtime osx.10.11-x64`

## <a name="see-also"></a>Siehe auch
* [Frameworks](../../standard/frameworks.md)
* [Runtime-ID-Katalog (RID)](../rid-catalog.md)


<!--HONumber=Feb17_HO2-->


