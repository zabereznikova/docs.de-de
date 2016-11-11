---
title: Dotnet-restore-Befehl | .NET Core-SDK
description: "Informationen zum Wiederherstellen von Abhängigkeiten und projektspezifische Tools zum dotnet-restore-Befehl"
keywords: dotnet-restore, CLI, CLI-Befehl, .NET Core
author: mairaw
manager: wpickett
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 60489b25-38de-47e6-bed1-59d9f42e2d46
translationtype: Human Translation
ms.sourcegitcommit: c6ee3f5663d0a3f62914e8de474cca4d15340c9d
ms.openlocfilehash: 3c6c651aebfac0c27f340021d7779d37aa8bfe38

---

#<a name="dotnetrestore"></a>dotnet-restore

## <a name="name"></a>Name

`dotnet-restore` – Stellt die Abhängigkeiten und Tools eines Projekts wieder her

## <a name="synopsis"></a>Übersicht

`dotnet restore [root] [--help] [--force-english-output] [--source]  
    [--packages] [--disable-parallel] [--fallbacksource] [--configfile] 
    [--no-cache] [--infer-runtimes] [--verbosity] [--ignore-failed-sources]`

## <a name="description"></a>Beschreibung

Der Befehl `dotnet restore` verwendet NuGet zum Wiederherstellen von Abhängigkeiten sowie projektspezifische Tools, die in der Datei [project.json](project-json.md) angegeben sind. Standardmäßig wird die Wiederherstellung von Abhängigkeiten und Tools parallel ausgeführt.

Zum Wiederherstellen der Abhängigkeiten benötigt NuGet die Feeds, wo sich die Pakete befinden. Feeds werden in der Regel über die Konfigurationsdatei „NuGet.config“ bereitgestellt. Eine Standarddatei ist vorhanden, wenn die CLI-Tools installiert sind. Sie können mehrere Feeds angeben, indem Sie eine eigene Datei „NuGet.config“ im Projektverzeichnis erstellen. Feeds können auch per Aufruf in der Befehlszeile angegeben werden. 

Für Abhängigkeiten können Sie mithilfe des Arguments `--packages` angeben, wo die wiederhergestellten Pakete während der Wiederherstellung platziert werden. Wenn nichts angegeben ist, wird der Standardcache des NuGet-Pakets verwendet. Er befindet sich im Verzeichnis `.nuget/packages` im Basisverzeichnis des Benutzers auf allen Betriebssystemen (z.B. */home/user1* unter Linux oder *C:\Users\user1* unter Windows).

Für projektspezifische Tools stellt `dotnet restore` zunächst das Paket wieder her, in dem sich das Tool befindet, und danach die Abhängigkeiten des Tools gemäß seiner Datei [project.json](project-json.md). 

## <a name="options"></a>Optionen

`[root]` 
    
 Eine Liste der wiederherzustellenden Projekte oder Projektordner. Jeder Wert kann ein Pfad zu einer Datei [project.json](project-json.md) oder [global.json](global-json.md) oder zu einem Ordner sein. Wenn ein Ordner angegeben wird, wird der Wiederherstellungsvorgang nach einer Datei [project.json](project-json.md) in allen Unterverzeichnissen rekursiv suchen und die Wiederherstellung für jede gefundene Datei [project.json](project-json.md) ausführen.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

 `--force-english-output`

Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.

`-s|--source <SOURCE>`

Gibt eine NuGet-Paketquelle an, die während des Wiederherstellungsvorgangs zu verwenden ist. Dies überschreibt alle Quellen, die in den Dateien „NuGet.config“ angegeben sind. Es können mehrere Quellen bereitgestellt werden, indem diese Option mehrmals angegeben wird.

`--packages <PACKAGES_DIRECTORY]`

Gibt das Verzeichnis an, in dem die wiederhergestellten Pakete zu platzieren sind. 

`--disable-parallel`

Deaktiviert paralleles Erstellen von mehreren Projekten. 

`-f|--fallbacksource <FEED>`

Gibt eine Liste von Paketquellen als Fallback für den Wiederherstellungsvorgang an, wenn alle anderen Quellen nicht verfügbar sind. Alle gültigen Feed-Formate sind zulässig. Es können mehrere Fallbackquellen bereitgestellt werden, indem diese Option mehrmals angegeben wird.

`--configfile <FILE>`

Die NuGet-Konfigurationsdatei („NuGet.config“) für den Wiederherstellungsvorgang.

`--no-cache`

Gibt an, dass Pakete und HTTP-Anfragen nicht zwischengespeichert werden.

`--infer-runtimes`

Temporäre Option, damit NuGet Runtime-IDs (RIDs) aus älteren Repositorys ableiten kann.

`--verbosity [LEVEL]`

Die Ausführlichkeit der verwendeten Protokollierung. Zulässige Werte: `Debug`, `Verbose`, `Information`, `Minimal`, `Warning` oder `Error`.

` --ignore-failed-sources`

Zu fehlerhaften Quellen nur warnen, wenn Pakete die Versionsanforderung erfüllen.

## <a name="examples"></a>Beispiele

Wiederherstellen von Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis:

`dotnet restore` 

Wiederherstellen von Abhängigkeiten und Tools für das Projekt `app1` im vorgegebenen Pfad:

`dotnet restore ~/projects/app1/project.json`
    
Wiederherstellen der Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis, mit dem bereitgestellten Dateipfad als Fallbackquelle:

`dotnet restore -f c:\packages\mypackages` 

Wiederherstellen der Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis, mit den beiden bereitgestellten Dateipfaden als Fallbackquellen:

`dotnet restore -f c:\packages\mypackages -f c:\packages\myotherpackages` 

Wiederherstellen von Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis und nur Anzeige von Fehlern in der Ausgabe:

`dotnet restore --verbosity Error`


<!--HONumber=Nov16_HO1-->


