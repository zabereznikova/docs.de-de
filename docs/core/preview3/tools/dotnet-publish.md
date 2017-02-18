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
ms.assetid: f2ef275a-7c5e-430a-8c30-65f52af62771
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 0d222382640fc239760f8f51c69f1f306674d7ca

---

#<a name="dotnet-publish-net-core-tools-rc4"></a>dotnet-publish (.NET Core Tools RC4)

> [!WARNING]
> Dieses Thema gilt für .NET Core Tools RC4. Informationen zu .NET Core Preview 2-Tools finden Sie im Thema [dotnet-publish](../../tools/dotnet-publish.md).

## <a name="name"></a>Name

`dotnet-publish`: Packt die Anwendung und alle ihre Abhängigkeiten in einen Ordner, bereit für die Veröffentlichung

## <a name="synopsis"></a>Übersicht

`dotnet publish [project] 
    [--help] [--framework]  
    [--runtime] [--output]  
    [--version-suffix] [--configuration]`

## <a name="description"></a>Beschreibung

`dotnet publish` kompiliert die Anwendung, liest ihre Abhängigkeiten, die in der Projektdatei angegeben sind, und veröffentlicht die resultierenden Dateien in einem Verzeichnis. 

Je nach Art der portablen App wird das resultierende Verzeichnis Folgendes enthalten:

1. *Framework-abhängige Bereitstellung* – Anwendungscode in Zwischensprache (IL) und alle von der Anwendung verwalteten Abhängigkeiten.
2. *Eigenständige Bereitstellung* – wie oben, sowie die gesamte Runtime für die Zielplattform.

Weitere Informationen finden Sie unter [.NET Core Anwendungsbereitstellung](../deploying/index.md).

## <a name="options"></a>Optionen

`[project]` 

Das zu veröffentlichende Projekt – standardmäßig das aktuelle Verzeichnis, wenn `[project]` nicht angegeben ist. 

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.  

`-f|--framework <FRAMEWORK>`

Veröffentlicht die Anwendung für eine bestimmte Framework-ID (FID). 

`-r|--runtime <RUNTIME_IDENTIFIER>`

Veröffentlicht die Anwendung für eine bestimmte Laufzeit. Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../../rid-catalog.md).

`-o|--output <OUTPUT_PATH>`

Geben Sie den Pfad für das Verzeichnis an. Wenn nicht angegeben, wird standardmäßig *_./bin/[configuration]/[framework]/_* für portable Applikationen oder *_./bin/[configuration]/[framework]/[runtime]_* für eigenständige Bereitstellungen gewählt.

`--version-suffix [VERSION_SUFFIX]`

Definiert, durch was `*` im Versionsfeld der Projektdatei ersetzt werden soll.

`-c|--configuration [Debug|Release]`

Konfiguration bei der Veröffentlichung. Der Standardwert ist `Debug`.

## <a name="examples"></a>Beispiele

Veröffentlichen einer Anwendung:

`dotnet publish`

Veröffentlichen der Anwendung unter Verwendung der angegebenen Projektdatei:

`dotnet publish ~/projects/app1/app1.csproj`
    
Veröffentlichen der aktuellen Anwendung mithilfe des Frameworks `netcoreapp1.0`:

`dotnet publish --framework netcoreapp1.0`
    
Veröffentlichen der aktuellen Anwendung mithilfe des Frameworks `netcoreapp1.0` und der Runtime für `OS X 10.10` (die RID muss in der Projektdatei vorhanden sein):

`dotnet publish --framework netcoreapp1.0 --runtime osx.10.11-x64`

## <a name="see-also"></a>Siehe auch
* [Frameworks](../../../standard/frameworks.md)
* [Runtime-ID-Katalog (RID)](../../rid-catalog.md)



<!--HONumber=Feb17_HO2-->


