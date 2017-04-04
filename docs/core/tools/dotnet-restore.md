---
title: "Befehl „dotnet-restore“ – .NET Core-CLI | Microsoft-Dokumentation"
description: "Erfahren Sie mehr über das Wiederherstellen von Abhängigkeiten und projektspezifischen Tools mit dem Befehl dotnet-restore."
keywords: dotnet-restore, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fd7a5769-afbe-4838-bbaf-3ae0cfcbb914
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: 92da0806eb6c365a4622668242edc28d9966ed26
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-restore"></a>dotnet-restore

## <a name="name"></a>Name

`dotnet-restore`: Stellt die Abhängigkeiten und Tools eines Projekts wieder her

## <a name="synopsis"></a>Übersicht

`dotnet restore [<ROOT>] [-s|--source] [-r|--runtime] [--packages] [--disable-parallel] [--configfile] [--no-cache] [--ignore-failed-sources] [--no-dependencies] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>Beschreibung

Der Befehl `dotnet restore` verwendet NuGet zum Wiederherstellen von Abhängigkeiten sowie projektspezifischen Tools, die in der Projektdatei angegeben sind. Standardmäßig wird die Wiederherstellung von Abhängigkeiten und Tools parallel ausgeführt.

Zum Wiederherstellen der Abhängigkeiten benötigt NuGet die Feeds, wo sich die Pakete befinden. Feeds werden in der Regel über die Konfigurationsdatei *NuGet.config* bereitgestellt. Eine standardmäßige Konfigurationsdatei wird bereitgestellt, wenn die CLI-Tools installiert sind. Sie geben zusätzliche Feeds an, indem Sie eine eigene *NuGet.config*-Datei im Projektverzeichnis erstellen. Sie können auch zusätzliche Feeds pro Aufruf an der Eingabeaufforderung angeben. 

Für Abhängigkeiten geben Sie mithilfe des Arguments `--packages` an, wo die wiederhergestellten Pakete während der Wiederherstellung platziert werden. Wenn nichts angegeben wurde, wird der Standardcache des NuGet-Pakets verwendet. Er befindet sich im Verzeichnis `.nuget/packages` im Basisverzeichnis des Benutzers auf allen Betriebssystemen (z.B. */home/user1* unter Linux oder *C:\Users\user1* unter Windows).

Für projektspezifische Tools stellt `dotnet restore` zunächst das Paket wieder her, in dem sich das Tool befindet, und danach die Abhängigkeiten des Tools gemäß seiner Projektdatei.

## <a name="arguments"></a>Argumente

`ROOT` 
    
Optionaler Pfad zur wiederherzustellenden Projektdatei.

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`-s|--source <SOURCE>`

Gibt eine NuGet-Paketquelle an, die während des Wiederherstellungsvorgangs zu verwenden ist. Dies überschreibt alle Quellen, die in der/den *NuGet.config*-Datei(en) angegeben sind. Es können mehrere Quellen bereitgestellt werden, indem diese Option mehrmals angegeben wird.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Gibt eine Laufzeit für die Wiederherstellung des Pakets an. Wird für das Wiederherstellen von Paketen für Laufzeiten verwendet, die nicht explizit im `<RuntimeIdentifiers>`-Tag in der *.csproj*-Datei aufgeführt sind. Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md). Es können mehrere RIDs bereitgestellt werden, indem diese Option mehrmals angegeben wird.

`--packages <PACKAGES_DIRECTORY]`

Gibt das Verzeichnis für wiederhergestellte Pakete an. 

`--disable-parallel`

Deaktiviert paralleles Erstellen von mehreren Projekten. 

`--configfile <FILE>`

Die NuGet-Konfigurationsdatei (*NuGet.config*) für den Wiederherstellungsvorgang.

`--no-cache`

Gibt an, dass Pakete und HTTP-Anfragen nicht zwischengespeichert werden.

`--ignore-failed-sources`

Bei fehlerhaften Quellen nur warnen, wenn Pakete die Versionsanforderung erfüllen.

`--no-dependencies`

Wenn Sie ein Projekt mit Projekt-zu-Projekt (P2P)-Verweisen wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.

`--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

## <a name="examples"></a>Beispiele

Wiederherstellen von Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis:

`dotnet restore` 

Wiederherstellen von Abhängigkeiten und Tools für das Projekt `app1` im vorgegebenen Pfad:

`dotnet restore ~/projects/app1/app1.csproj`
    
Wiederherstellen der Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis mit dem bereitgestellten Dateipfad als Quelle:

`dotnet restore -s c:\packages\mypackages` 

Wiederherstellen der Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis mit den beiden bereitgestellten Dateipfaden als Quellen:

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages` 

Wiederherstellen von Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis und nur Anzeige von Fehlern in der Ausgabe:

`dotnet restore --verbosity Error`

