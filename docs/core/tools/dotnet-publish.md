---
title: Befehl dotnet-publish | Microsoft-Dokumentation
description: "Der dotnet-publish-Befehl veröffentlicht ein .NET Core-Projekt in ein Verzeichnis."
keywords: dotnet-publish, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f2ef275a-7c5e-430a-8c30-65f52af62771
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 78487673d8fa07286605fb806f30083747b17386
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-publish"></a>dotnet-publish

## <a name="name"></a>Name

`dotnet-publish`: Packt die Anwendung und alle ihre Abhängigkeiten in einen Ordner, bereit für die Veröffentlichung

## <a name="synopsis"></a>Übersicht

```
dotnet publish [project] [-f|--framework] [-r|--runtime] [-o|--output] [-c|--configuration] [--version-suffix] [-v|--verbosity]
dotnet publish [-h|--help]
```

## <a name="description"></a>Beschreibung

`dotnet publish` kompiliert die Anwendung, liest ihre Abhängigkeiten, die in der Projektdatei angegeben sind, und veröffentlicht die resultierenden Dateien in einem Verzeichnis. Die Ausgabe wird Folgendes enthalten:

1. Intermediate Language-Code (IL) in einer Assembly mit einer `*.dll`-Erweiterung.
2. *deps.json*-Datei, die alle Abhängigkeiten des Projekts enthält. 
3. *Runtime.config.json*-Datei, die gemeinsam genutzte Laufzeit angibt, die die Anwendung erwartet, sowie andere Konfigurationsoptionen für die Laufzeit (z.B. Garbage Collection-Typ).
4. Alle Abhängigkeiten der Anwendung. Diese werden aus dem NuGet-Cache und in den Ausgabeordner kopiert. 

Die Ausgabe des `dotnet publish`-Befehls wird auf einem Remotecomputer für die Ausführung bereitgestellt werden und ist die einzige offiziell unterstützte Art zum Vorbereiten der Anwendung für die Bereitstellung auf einem anderen Computer (z.B. ein Server) für die Ausführung. Je nach Art der Bereitstellung, die im Projekt angegeben ist, muss auf den Remotecomputern die freigegebene .NET Core-Laufzeit installiert sein. Weitere Informationen finden Sie unter [.NET Core Anwendungsbereitstellung](../deploying/index.md).

## <a name="arguments"></a>Argumente

`project` 

Das zu veröffentlichende Projekt – standardmäßig das aktuelle Verzeichnis, wenn `project` nicht angegeben ist. 

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.  

`-f|--framework <FRAMEWORK>`

Veröffentlicht die Anwendung für das angegebene Zielframework. Das Zielframework muss in der Projektdatei angegeben werden.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Veröffentlicht die Anwendung für eine bestimmte Laufzeit. Wird bei der Erstellung einer [unabhängige Bereitstellung](../deploying/index.md#self-contained-deployments-scd) verwendet. Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md). Standardmäßig wird eine [Framework-abhängige Anwendung](../deploying/index.md#framework-dependent-deployments-fdd) veröffentlicht.

`-o|--output <OUTPUT_PATH>`

Geben Sie den Pfad für das Verzeichnis an. Wenn nicht angegeben, wird standardmäßig *_./bin/[configuration]/[framework]/_* für portable Applikationen oder *_./bin/[configuration]/[framework]/[runtime]_* für eigenständige Bereitstellungen gewählt.

`-c|--configuration {Debug|Release}`

Konfiguration, die beim Erstellen des Projekts verwendet wird. Der Standardwert ist `Debug`.

`--version-suffix <VERSION_SUFFIX>`

Definiert, durch was `*` im Versionsfeld der Projektdatei ersetzt werden soll.

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

## <a name="examples"></a>Beispiele

Veröffentlichen Sie das Projekt aus dem aktuellen Verzeichnis:

`dotnet publish`

Veröffentlichen Sie die Anwendung unter Verwendung der angegebenen Projektdatei:

`dotnet publish ~/projects/app1/app1.csproj`
    
Veröffentlichen Sie das Projekt aus dem aktuellen Verzeichnis unter Verwendung des `netcoreapp1.1`-Framework:

`dotnet publish --framework netcoreapp1.1`
    
Veröffentlichen der aktuellen Anwendung mithilfe des Frameworks `netcoreapp1.1` und der Runtime für `OS X 10.10` (die RID muss in der Projektdatei vorhanden sein):

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

## <a name="see-also"></a>Siehe auch
* [Frameworks](../../standard/frameworks.md)
* [Runtime-ID-Katalog (RID)](../rid-catalog.md)
