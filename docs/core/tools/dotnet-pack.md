---
title: Befehl dotnet-pack | Microsoft-Dokumentation
description: "Der dotnet-pack-Befehl erstellt NuGet-Pakete für ein .NET Core-Projekt."
keywords: dotnet-pack, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8dbbb3f7-b817-4161-a6c8-a3489d05e051
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 88289a09a22bf20ec9089ec6a74269cd682a305b
ms.lasthandoff: 03/07/2017

---

#<a name="dotnet-pack"></a>dotnet-pack

## <a name="name"></a>Name

`dotnet-pack`: Packt den Code in ein NuGet-Paket

## <a name="synopsis"></a>Übersicht

```
dotnet pack [project] [-o|--output] [--no-build] [--include-symbols] [--include-source] [-c|--configuration] [--version-suffix] [-s|--serviceable] [-v|--verbosity]
dotnet pack [-h|--help]
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet pack` erstellt das Projekt und NuGet-Pakete. Das Ergebnis dieses Befehls ist ein NuGet-Paket. Wenn die `--include-symbols`-Option vorhanden ist, wird ein anderes Paket mit den Debugsymbolen erstellt. 

NuGet-Abhängigkeiten des gepackten Projekts werden der Datei `nuspec` hinzugefügt. Sie werden aufgelöst, wenn das Paket installiert wird. Verweise zwischen Projekten werden innerhalb des Projekts nicht gepackt. Derzeit benötigen Sie ein Paket pro Projekt, wenn Sie Abhängigkeiten zwischen Projekten haben.

`dotnet pack` erstellt standardmäßig zuerst das Projekt. Wenn Sie dies vermeiden möchten, übergeben Sie die Option `--no-build`. Dies kann bei fortlaufenden Integrations-Buildszenarios (CI) hilfreich sein, indem Sie beispielsweise wissen, dass der Code erst kürzlich erstellt wurde. 

## <a name="arguments"></a>Argumente

`project` 
    
Das zu packende Projekt. Es kann entweder ein Pfad zu einer [CSPROJ-Datei](csproj.md) oder zu einem Verzeichnis sein. Wenn nichts angegeben ist, wird standardmäßig das aktuelle Verzeichnis verwendet. 

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.  

`-o|--output <OUTPUT_DIRECTORY>`

Platziert die erstellten Pakete in das angegebene Verzeichnis. 

`--no-build`

Das Projekt wird vor dem Packen nicht erstellt. 

`--include-symbols`

Generiert die nupkg-Symbole. 

`--include-source`

Nimmt die Quelldateien in das NuGet-Paket auf. Die Quelldateien befinden sich im Ordner `src` im `nupkg`. 

`-c|--configuration <Debug|Release>`

Konfiguration, die beim Erstellen des Projekts verwendet wird. Wird dies nicht angegeben, wird standardmäßig `Debug` festgelegt.

`--version-suffix <VERSION_SUFFIX>`

Definiert den Wert für die $(VersionSuffix) MSBuild-Eigenschaft im Projekt.

`-s|--serviceable`

Legt das zu verarbeitende Flag im Paket fest. Weitere Informationen finden Sie unter https://aka.ms/nupkgservicing.

`--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

## <a name="examples"></a>Beispiele

Packt das Projekt im aktuellen Verzeichnis:

`dotnet pack`

Packt das Projekt app1:

`dotnet pack ~/projects/app1/project.csproj`
    
Packt das Projekt im aktuellen Verzeichnis, und platziert die erstellten Pakete in den angegebenen Ordner:

`dotnet pack --output nupkgs`

Packt das Projekt im aktuellen Verzeichnis in den angegebenen Ordner und überspringt den Buildschritt:

`dotnet pack --no-build --output nupkgs`

Packt das aktuelle Projekt und aktualisiert die resultierende Paketversion mit dem angegebenen Suffix. Das Suffix der Projektversion wird in der *.csproj*-Datei als `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` konfiguriert.

`dotnet pack --version-suffix "ci-1234"`
