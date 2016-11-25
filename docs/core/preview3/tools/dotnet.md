---
title: Dotnet-Befehl | .NET Core-SDK
description: "Informationen zum dotnet-Befehl (generischer Treiber für die .NET Core CLI-Tools) und dessen Verwendung."
keywords: dotnet, CLI, CLI-Befehle, .NET Core
author: mairaw
manager: wpickett
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 93015521-2127-4fe9-8fce-ca79bcc4ff49
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: bbc13c8cca82e660f0f8ccf7d88c0340d9c06e68

---

#<a name="dotnet-command"></a>dotnet-Befehl

## <a name="name"></a>Name

dotnet – allgemeiner Treiber für das Ausführen von Befehlszeilenbefehlen

## <a name="synopsis"></a>Übersicht

`dotnet [--version] [--verbose] [--info] [command] [arguments] [--help]`

## <a name="description"></a>Beschreibung
`dotnet` ist ein generischer Treiber für die Befehlszeilenschnittstellen-Toolkette (CLI). Allein aufgerufen gibt er kurze Anweisungen. 

Jede bestimmte Funktion ist als Befehl implementiert. Um die Funktion zu verwenden, wird der Befehl nach `dotnet` angegeben, wie z.B. [`dotnet build`](dotnet-build.md). Alle Argumente nach dem Befehl sind die eigenen Argumente. 

Nur bei portablen Apps wird `dotnet` als ein eigenständiger Befehl verwendet. Geben Sie einfach eine portable Anwendungs-DLL nach dem Verb `dotnet` an, um die Anwendung auszuführen.    

## <a name="options"></a>Optionen

`-v|--verbose`

Aktiviert die ausführliche Ausgabe.

`--version`

Druckt die Version der CLI-Tools.

`--info`

Druckt weitere Informationen zu den CLI-Tools, z.B. das aktuelle Betriebssystem, SHA für die Version committen, usw. 

`-h|--help`

Druckt eine kurze Hilfe für den Befehl. Bei Verwendung nur mit `dotnet`, wird auch eine Liste der verfügbaren Befehle gedruckt.  

## <a name="dotnet-commands"></a>dotnet-Befehle

Die folgenden Befehle sind für dotnet vorhanden:

* [dotnet-new](dotnet-new.md)
   * Initialisiert ein neues F#-Konsolenanwendungsprojekt.
* [dotnet-restore](dotnet-restore.md)
  * Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her. 
* [dotnet-build](dotnet-build.md)
  * Erstellt eine .NET Core-Anwendung.
* [dotnet-publish](dotnet-publish.md)
   * Veröffentlicht eine portable oder eigenständige .NET-Anwendung.
* [dotnet-run](dotnet-run.md)
   * Führt die Anwendung aus der Quelle aus.
* [dotnet-test](dotnet-test.md)
   * Führt Tests mit einem Testprogramm durch, das in der Datei „project.json“ angegeben ist.
* [dotnet-pack](dotnet-pack.md)
   * Erstellt ein NuGet-Paket aus Ihrem Code.
* [dotnet-migrate](dotnet-migrate.md)
   * Migriert ein gültiges Preview 2-Projekt in ein Preview 3-Projekt
* [dotnet-msbuild](dotnet-msbuild.md)
   * Ermöglicht den Zugriff auf die MSBuild-Befehlszeile

## <a name="examples"></a>Beispiele

Initialisieren einer .NET Core-Konsolenanwendung, die kompiliert und ausgeführt werden kann:

`dotnet new`

Wiederherstellen von Abhängigkeiten für eine bestimmte Anwendung:

`dotnet restore`

Erstellen eines Projekts und seiner Abhängigkeiten in einem vorgegebenen Verzeichnis: 

`dotnet build`

Ausführen einer portablen App namens `myapp.dll`: `dotnet myapp.dll`

## <a name="environment"></a>Umgebung 

`DOTNET_PACKAGES`

Der Cache des primären Pakets. Wenn nichts festgelegt ist, wird standardmäßig „$HOME/.nuget/packages unter Unix oder %HOME%\NuGet\Packages“ unter Windows ausgewählt.

`DOTNET_SERVICING`

Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden. `true`zum Deaktivieren der Telemetriefunktion (Werte „true“, „1“ oder „yes“ akzeptiert); andernfalls `false` (Werte „false“, „0“ oder „no“ akzeptiert). Wenn nicht festgelegt, gilt standardmäßig `false`, d.h. die Telemetriefunktion ist aktiviert.




<!--HONumber=Nov16_HO3-->


