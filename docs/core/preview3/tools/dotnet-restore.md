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
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: 6fb08a8765ad720b51e796aa0991087413d02e44

---

#<a name="dotnet-restore"></a>dotnet-restore

## <a name="name"></a>Name

`dotnet-restore` – Stellt die Abhängigkeiten und Tools eines Projekts wieder her

## <a name="synopsis"></a>Übersicht

`dotnet restore [root] [--help] [--source]  
    [--packages] [--disable-parallel] [--configfile] 
    [--no-cache] [--ignore-failed-sources] [--no-dependencies]`

## <a name="description"></a>Beschreibung

Der Befehl `dotnet restore` verwendet NuGet zum Wiederherstellen von Abhängigkeiten sowie projektspezifischen Tools, die in der Projektdatei angegeben sind. Standardmäßig wird die Wiederherstellung von Abhängigkeiten und Tools parallel ausgeführt.

Zum Wiederherstellen der Abhängigkeiten benötigt NuGet die Feeds, wo sich die Pakete befinden. Feeds werden in der Regel über die Konfigurationsdatei „NuGet.config“ bereitgestellt. Eine Standarddatei ist vorhanden, wenn die CLI-Tools installiert sind. Sie können mehrere Feeds angeben, indem Sie eine eigene Datei „NuGet.config“ im Projektverzeichnis erstellen. Feeds können auch per Aufruf in der Befehlszeile angegeben werden. 

Für Abhängigkeiten können Sie mithilfe des Arguments `--packages` angeben, wo die wiederhergestellten Pakete während der Wiederherstellung platziert werden. Wenn nichts angegeben ist, wird der Standardcache des NuGet-Pakets verwendet. Er befindet sich im Verzeichnis `.nuget/packages` im Basisverzeichnis des Benutzers auf allen Betriebssystemen (z.B. */home/user1* unter Linux oder *C:\Users\user1* unter Windows).

Für projektspezifische Tools stellt `dotnet restore` zunächst das Paket wieder her, in dem sich das Tool befindet, und danach die Abhängigkeiten des Tools gemäß seiner Projektdatei.

## <a name="options"></a>Optionen

`[root]` 
    
Optionaler Pfad zur wiederherzustellenden Projektdatei. 

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`-s|--source <SOURCE>`

Gibt eine NuGet-Paketquelle an, die während des Wiederherstellungsvorgangs zu verwenden ist. Dies überschreibt alle Quellen, die in den Dateien „NuGet.config“ angegeben sind. Es können mehrere Quellen bereitgestellt werden, indem diese Option mehrmals angegeben wird.

`--packages <PACKAGES_DIRECTORY]`

Gibt das Verzeichnis an, in dem die wiederhergestellten Pakete zu platzieren sind. 

`--disable-parallel`

Deaktiviert paralleles Erstellen von mehreren Projekten. 

`--configfile <FILE>`

Die NuGet-Konfigurationsdatei („NuGet.config“) für den Wiederherstellungsvorgang.

`--no-cache`

Gibt an, dass Pakete und HTTP-Anfragen nicht zwischengespeichert werden.

` --ignore-failed-sources`

Zu fehlerhaften Quellen nur warnen, wenn Pakete die Versionsanforderung erfüllen.

`--no-dependencies`

Wenn Sie ein Projekt mit P2P-Verweisen wiederherstellen, stellen Sie nicht die Verweise wieder her, sondern nur das Stammprojekt. 

## <a name="examples"></a>Beispiele

Wiederherstellen von Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis:

`dotnet restore` 

Wiederherstellen von Abhängigkeiten und Tools für das Projekt `app1` im vorgegebenen Pfad:

`dotnet restore ~/projects/app1/app1.csproj``
    
Wiederherstellen der Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis, mit dem bereitgestellten Dateipfad als Fallbackquelle:

`dotnet restore -f c:\packages\mypackages` 

Wiederherstellen der Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis, mit den beiden bereitgestellten Dateipfaden als Fallbackquellen:

`dotnet restore -f c:\packages\mypackages -f c:\packages\myotherpackages` 

Wiederherstellen von Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis und nur Anzeige von Fehlern in der Ausgabe:

`dotnet restore --verbosity Error`



<!--HONumber=Nov16_HO3-->


