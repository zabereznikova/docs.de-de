---
title: "Befehl dotnet-publish – .NET Core CLI | Microsoft-Dokumentation"
description: "Der dotnet-publish-Befehl veröffentlicht ein .NET Core-Projekt in ein Verzeichnis."
keywords: dotnet-publish, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f2ef275a-7c5e-430a-8c30-65f52af62771
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: 48bfe6c77ee6c5d905069f47da5512ac63a24b2a
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-publish"></a>dotnet-publish

## <a name="name"></a>Name

`dotnet-publish`: Packt die Anwendung und ihre Abhängigkeiten in einen Ordner für die Bereitstellung auf einem Hostsystem.

## <a name="synopsis"></a>Übersicht

`dotnet publish [<PROJECT>] [-f|--framework] [-r|--runtime] [-o|--output] [-c|--configuration] [--version-suffix] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>Beschreibung

`dotnet publish` kompiliert die Anwendung, liest ihre Abhängigkeiten, die in der Projektdatei angegeben sind, und veröffentlicht die resultierenden Dateien in einem Verzeichnis. Die Ausgabe wird Folgendes enthalten:

* Intermediate Language-Code (IL) in einer Assembly mit einer `*.dll`-Erweiterung.
* *\*deps.json*-Datei, die alle Abhängigkeiten des Projekts enthält.
* *\*.runtime.config.json*-Datei, die gemeinsam genutzte Laufzeit angibt, die die Anwendung erwartet, sowie andere Konfigurationsoptionen für die Laufzeit (z.B. Garbage Collection-Typ).
* Die Abhängigkeiten der Anwendung. Diese werden aus dem NuGet-Cache in den Ausgabeordner kopiert.

Die `dotnet publish`-Ausgabe des Befehls ist bereit für die Bereitstellung auf einem Hostsystem (z.B. ein Server, PC, Mac, Laptops) für die Ausführung und ist der einzige offiziell unterstützte Weg, um die Anwendung für die Bereitstellung vorzubereiten. Je nach Art der Bereitstellung, die im Projekt angegeben ist, hat das Hostsystem die freigegebene .NET Core-Laufzeit installiert oder nicht. Weitere Informationen finden Sie unter [.NET Core Anwendungsbereitstellung](../deploying/index.md). Die Verzeichnisstruktur der veröffentlichten Anwendung finden Sie unter [Directory structure (Verzeichnisstruktur)](https://docs.microsoft.com/en-us/aspnet/core/hosting/directory-structure).

## <a name="arguments"></a>Argumente

`PROJECT` 

Das zu veröffentlichende Projekt – standardmäßig das aktuelle Verzeichnis, wenn nicht angegeben. 

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.  

`-f|--framework <FRAMEWORK>`

Veröffentlicht die Anwendung für das angegebene [Zielframework](../../standard/frameworks.md). Sie müssen das Zielframework in der Projektdatei angeben.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Veröffentlicht die Anwendung für eine bestimmte Laufzeit. Wird bei der Erstellung einer [eigenständigen Bereitstellung (Self-contained deployments, SCD)](../deploying/index.md#self-contained-deployments-scd) verwendet. Eine Liste der Runtime-IDs (RIDs) finden Sie im [RID-Katalog](../rid-catalog.md). Standardmäßig wird eine [Framework-abhängige Bereitstellung (FDD)](../deploying/index.md#framework-dependent-deployments-fdd) veröffentlicht.

`-o|--output <OUTPUT_DIRECTORY>`

Gibt den Pfad für das Ausgabeverzeichnis an. Wenn nicht angegeben, wird standardmäßig *./bin/[configuration]/[framework]/* für eine Framework-abhängige Bereitstellung oder *./bin/[configuration]/[framework]/[runtime]* für eine eigenständige Bereitstellung gewählt.

`-c|--configuration <CONFIGURATION>`

Konfiguration, die beim Erstellen des Projekts verwendet wird. Der Standardwert ist `Debug`.

`--version-suffix <VERSION_SUFFIX>`

Definiert das Versionssuffix zum Ersetzen des Sternchens (`*`) im Versionsfeld der Projektdatei.

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

## <a name="examples"></a>Beispiele

Veröffentlicht das Projekt im aktuellen Verzeichnis:

`dotnet publish`

Veröffentlichen Sie die Anwendung unter Verwendung der angegebenen Projektdatei:

`dotnet publish ~/projects/app1/app1.csproj`
    
Veröffentlichen Sie das Projekt aus dem aktuellen Verzeichnis unter Verwendung des `netcoreapp1.1`-Frameworks:

`dotnet publish --framework netcoreapp1.1`
    
Veröffentlichen der aktuellen Anwendung mithilfe des `netcoreapp1.1`-Frameworks und der Laufzeit für `OS X 10.10` (Sie müssen diese RID in der Projektdatei auflisten).

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

## <a name="see-also"></a>Siehe auch

* [Zielframeworks](../../standard/frameworks.md)
* [Runtime-ID-Katalog (RID)](../rid-catalog.md)
