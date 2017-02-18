---
title: Befehl dotnet-pack | Microsoft-Dokumentation
description: "Der dotnet-pack-Befehl erstellt NuGet-Pakete für ein .NET Core-Projekt."
keywords: dotnet-pack, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 10/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8dbbb3f7-b817-4161-a6c8-a3489d05e051
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 8e266f9b34923b0ab69140d78a20afeca00e0b7c

---

#<a name="dotnet-pack-net-core-tools-rc4"></a>dotnet-pack (.NET Core Tools RC4)

> [!WARNING]
> Dieses Thema gilt für .NET Core Tools RC4. Informationen zu .NET Core Preview 2-Tools finden Sie im Thema [dotnet-pack](../../tools/dotnet-pack.md).

## <a name="name"></a>Name

`dotnet-pack`: Packt den Code in ein NuGet-Paket

## <a name="synopsis"></a>Übersicht

`dotnet pack [--help] [--output]  
    [--no-build] [--include-symbols]
    [--include-source] [--servicable]
    [--configuration]  [--version-suffix]
    [project]`  

## <a name="description"></a>Beschreibung

Der Befehl `dotnet pack` erstellt das Projekt und NuGet-Pakete. Das Ergebnis dieses Befehls ist ein NuGet-Paket. Wenn die `--include-symbols`-Option vorhanden ist, wird ein anderes Paket mit den Debugsymbolen erstellt. 

NuGet-Abhängigkeiten des gepackten Projekts werden der Datei `nuspec` hinzugefügt. Sie werden aufgelöst, wenn das Paket installiert wird. Verweise zwischen Projekten werden innerhalb des Projekts nicht gepackt. Derzeit benötigen Sie ein Paket pro Projekt, wenn Sie Abhängigkeiten zwischen Projekten haben.

`dotnet pack` erstellt standardmäßig zuerst das Projekt. Wenn Sie dies vermeiden möchten, übergeben Sie die Option `--no-build`. Dies kann bei fortlaufenden Integrations-Buildszenarios (CI) hilfreich sein, indem Sie beispielsweise wissen, dass der Code erst kürzlich erstellt wurde. 

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.  

`[project]` 
    
Das zu packende Projekt. Es kann entweder ein Pfad zu einer [CSPROJ-Datei](csproj.md) oder zu einem Verzeichnis sein. Wenn nichts angegeben ist, wird standardmäßig das aktuelle Verzeichnis verwendet. 

`-o|--output <OUTPUT_DIRECTORY>`

Platziert die erstellten Pakete in das angegebene Verzeichnis. 

`--no-build`

Das Projekt wird vor dem Packen nicht erstellt. 

`--include-source`

Nimmt die Quelldateien in das NuGet-Paket auf. Die Quelldateien befinden sich im Ordner `src` im `nupkg`. 

`--include-symbols`

Generiert das NuGet-Paket mit Symbolen. 

`-c|--configuration <Debug|Release>`

Konfiguration, die beim Erstellen des Projekts verwendet wird. Wird dies nicht angegeben, wird standardmäßig `Debug` festgelegt.

`--version-suffix`

Aktualisiert das Sternchen im `-*`-Paket-Versionssuffix mit einer angegebenen Zeichenfolge.

## <a name="examples"></a>Beispiele

Packt das Projekt im aktuellen Verzeichnis:

`dotnet pack`

Packt das Projekt app1:

`dotnet pack ~/projects/app1/project.csproj`
    
Packt das Projekt im aktuellen Verzeichnis, und platziert die erstellten Pakete in den angegebenen Ordner:

`dotnet pack --output nupkgs`

Packt das Projekt im aktuellen Verzeichnis in den angegebenen Ordner und überspringt den Buildschritt:

`dotnet pack --no-build --output nupkgs`

Packt das aktuelle Projekt und aktualisiert die resultierende Paketversion mit dem angegebenen Suffix. Zum Beispiel wird Version `1.0.0-*` aktualisiert zu `1.0.0-ci-1234`.

`dotnet pack --version-suffix "ci-1234"`


<!--HONumber=Feb17_HO2-->


