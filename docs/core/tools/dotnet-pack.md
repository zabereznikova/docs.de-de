---
title: "dotnet-pack-Befehl – .NET Core-CLI"
description: "Der dotnet-pack-Befehl erstellt NuGet-Pakete für ein .NET Core-Projekt."
keywords: dotnet-pack, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8dbbb3f7-b817-4161-a6c8-a3489d05e051
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 04b967fdf6578098caae8c21604c5d6160eb6775
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-pack"></a>dotnet-pack

## <a name="name"></a>Name

`dotnet-pack`: Packt den Code in ein NuGet-Paket

## <a name="synopsis"></a>Übersicht

`dotnet pack [<PROJECT>] [-o|--output] [--no-build] [--include-symbols] [--include-source] [-c|--configuration] [--version-suffix <VERSION_SUFFIX>] [-s|--serviceable] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>Beschreibung

Der Befehl `dotnet pack` erstellt das Projekt und NuGet-Pakete. Das Ergebnis dieses Befehls ist ein NuGet-Paket. Wenn die `--include-symbols`-Option vorhanden ist, wird ein anderes Paket mit den Debugsymbolen erstellt. 

NuGet-Abhängigkeiten des gepackten Projekts werden der Datei *nuspec* hinzugefügt. Sie werden ordnungsgemäß aufgelöst, wenn das Paket installiert wird. Verweise zwischen Projekten werden innerhalb des Projekts nicht gepackt. Derzeit benötigen Sie ein Paket pro Projekt, wenn Sie Abhängigkeiten zwischen Projekten haben.

`dotnet pack` erstellt standardmäßig zuerst das Projekt. Wenn Sie dieses Verhalten vermeiden möchten, übergeben Sie die Option `--no-build`. Dies ist bei Buildszenarios der Continuous Integration (CI) oft hilfreich, bei denen Sie wissen, dass der Code kürzlich erstellt wurde.

Sie können dem `dotnet pack`-Befehl MSBuild-Eigenschaften für den Packvorgang bereitstellen. Weitere Informationen finden Sie in den [NuGet-Metadateneigenschaften](csproj.md#nuget-metadata-properties) und in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).

## <a name="arguments"></a>Argumente

`PROJECT` 
    
Das zu packende Projekt. Es ist entweder ein Pfad zu einer [csproj-Datei](csproj.md) oder zu einem Verzeichnis. Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis angegeben. 

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.  

`-o|--output <OUTPUT_DIRECTORY>`

Platziert die erstellten Pakete in das angegebene Verzeichnis. 

`--no-build`

Erstellt das Projekt nicht vor dem Packen. 

`--include-symbols`

Generiert die Symbole `nupkg`. 

`--include-source`

Nimmt die Quelldateien in das NuGet-Paket auf. Die Quelldateien befinden sich im Ordner `src` im `nupkg`. 

`-c|--configuration <CONFIGURATION>`

Konfiguration, die beim Erstellen des Projekts verwendet wird. Wenn nicht angegeben, wird die Konfiguration standardmäßig auf `Debug` festgelegt.

`--version-suffix <VERSION_SUFFIX>`

Definiert den Wert für die `$(VersionSuffix)`-MSBuild-Eigenschaft im Projekt.

`-s|--serviceable`

Legt das zu verarbeitende Flag im Paket fest. Weitere Informationen finden Sie unter [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries (.NET Blog: .NET 4.5.1 unterstützt Microsoft Sicherheitsupdates für .NET NuGet-Bibliotheken)](https://aka.ms/nupkgservicing).

`--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

## <a name="examples"></a>Beispiele

Packt das Projekt im aktuellen Verzeichnis:

`dotnet pack`

Packt das `app1`-Projekt:

`dotnet pack ~/projects/app1/project.csproj`
    
Packt das Projekt im aktuellen Verzeichnis, und platziert die erstellten Pakete in den `nupkgs`-Ordner:

`dotnet pack --output nupkgs`

Packt das Projekt im aktuellen Verzeichnis in den `nupkgs`-Ordner und überspringt den Buildschritt:

`dotnet pack --no-build --output nupkgs`

Mit dem Versionssuffix des Projekts, das als `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in der *.csproj*-Datei konfiguriert ist, packen Sie das aktuelle Projekt, und aktualisieren Sie die resultierende Paketversion mit dem angegebenen Suffix:

`dotnet pack --version-suffix "ci-1234"`

Legen Sie die Paketversion auf `2.1.0` mithilfe der MSBuild-Eigenschaft `PackageVersion` fest.

`dotnet pack /p:PackageVersion=2.1.0`

