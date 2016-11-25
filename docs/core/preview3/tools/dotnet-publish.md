---
title: Dotnet-publish-Befehl | .NET Core-SDK
description: "Der dotnet-publish-Befehl veröffentlicht ein .NET Core-Projekt in ein Verzeichnis."
keywords: dotnet-publish, CLI, CLI-Befehl, .NET Core
author: mairaw
manager: wpickett
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 8a7e1c52-5c57-4bf5-abad-727450ebeefd
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: e480c32faa22859de74e06f3a199fba1c0720c46

---

#<a name="dotnet-publish"></a>dotnet-publish

## <a name="name"></a>Name

`dotnet-publish` – Packt die Anwendung und alle ihre Abhängigkeiten in einen Ordner, bereit für die Veröffentlichung

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



<!--HONumber=Nov16_HO3-->


