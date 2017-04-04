---
title: "Befehl „dotnet-clean“ – .NET Core-CLI | Microsoft-Dokumentation"
description: "Mit dem Befehl „dotnet-clean“ wird das aktuelle Verzeichnis bereinigt."
keywords: dotnet-clean, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: eff65fa1-bab4-4421-8260-d0a284b690b2
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: 0bdd8b9ab133ca92e414618412d95d8136d6234a
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-clean"></a>dotnet-clean

## <a name="name"></a>Name

`dotnet-clean`: Löscht die Ausgabe eines Projekts. 

## <a name="synopsis"></a>Übersicht

`dotnet clean [<PROJECT>] [-o|--output] [-f|--framework] [-c|--configuration] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>Beschreibung

Der Befehl `dotnet clean` löscht die Ausgabe des vorherigen Builds. Er ist als [MSBuild-Ziel](https://docs.microsoft.com/visualstudio/msbuild/msbuild-targets) implementiert, sodass das Projekt ausgewertet wird, wenn der Befehl ausgeführt wird. Es werden nur die Ausgaben gelöscht, die während des Builds erstellt wurden. Sowohl der Ordner für Zwischenausgabe (*obj*) als auch der Ordner für die endgültige Ausgabe (*bin*) werden bereinigt.

## <a name="arguments"></a>Argumente

`PROJECT`

Das zu bereinigende MSBuild-Projekt. Wenn Sie keine Projektdatei angeben, durchsucht MSBuild das aktuelle Arbeitsverzeichnis nach einer Dateierweiterung, die mit *proj* endet, und verwendet diese.

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`-o|--output <OUTPUT_DIRECTORY>`

Verzeichnis, in dem die Buildausgaben abgelegt wurden. Geben Sie den `-f|--framework <FRAMEWORK>`-Schalter mit dem Schalter des Ausgabeverzeichnisses an, wenn Sie das Framework bei der Erstellung des Projekts angegeben haben.

`-f|--framework <FRAMEWORK>`

Das [Framework](../../standard/frameworks.md), das bei der Erstellung angegeben wurde. Das Framework muss in der [Projektdatei](csproj.md) definiert werden. Wenn Sie das Framework bei der Erstellung angegeben haben, müssen Sie das Framework bei der Bereinigung angeben.

`-c|--configuration <CONFIGURATION>`

Legt die Konfiguration fest. Wenn kein Wert angegeben ist, wird als Standardwert `Debug` verwendet. Diese Eigenschaft ist bei der Bereinigung nur erforderlich, wenn Sie sie bei der Erstellung angegeben haben.

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Grade sind q[uiet], m[inimal], n[ormal], d[etailed] und diag[nostic].

## <a name="examples"></a>Beispiele

Bereinigen Sie einen Standardbuild des Projekts:

`dotnet clean`

Bereinigen Sie ein Projektbuild mit der Konfiguration „Release“:

`dotnet clean --configuration Release`

