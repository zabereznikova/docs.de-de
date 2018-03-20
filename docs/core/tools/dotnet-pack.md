---
title: "dotnet pack-Befehl – .NET Core-CLI"
description: "Der dotnet pack-Befehl erstellt NuGet-Pakete für ein .NET Core-Projekt."
author: mairaw
ms.author: mairaw
ms.date: 03/10/2018
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 401a4491c27ea10d0fdf1877417f1e2d5da6839f
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
# <a name="dotnet-pack"></a>dotnet pack

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet pack`: Packt den Code in ein NuGet-Paket

## <a name="synopsis"></a>Übersicht

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

```
dotnet pack [<PROJECT>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [--runtime] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)
```
dotnet pack [<PROJECT>] [-c|--configuration] [--include-source] [--include-symbols] [--no-build] [-o|--output] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```
---

## <a name="description"></a>description

Der Befehl `dotnet pack` erstellt das Projekt und NuGet-Pakete. Das Ergebnis dieses Befehls ist ein NuGet-Paket. Wenn die `--include-symbols`-Option vorhanden ist, wird ein anderes Paket mit den Debugsymbolen erstellt.

NuGet-Abhängigkeiten des gepackten Projekts werden der Datei *nuspec* hinzugefügt. Sie werden ordnungsgemäß aufgelöst, wenn das Paket installiert wird. Verweise zwischen Projekten werden innerhalb des Projekts nicht gepackt. Derzeit benötigen Sie ein Paket pro Projekt, wenn Sie Abhängigkeiten zwischen Projekten haben.

`dotnet pack` erstellt standardmäßig zuerst das Projekt. Wenn Sie dieses Verhalten vermeiden möchten, übergeben Sie die Option `--no-build`. Dies ist bei Buildszenarios der Continuous Integration (CI) oft hilfreich, bei denen Sie wissen, dass der Code kürzlich erstellt wurde.

Sie können dem `dotnet pack`-Befehl MSBuild-Eigenschaften für den Packvorgang bereitstellen. Weitere Informationen finden Sie in den [NuGet-Metadateneigenschaften](csproj.md#nuget-metadata-properties) und in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference). Der Abschnitt [Beispiele](#examples) enthält Informationen darüber, wie die MSBuild-Eigenschaft „/p“ für verschiedene Szenarien verwendet wird.

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a>Argumente

`PROJECT`

Das zu packende Projekt. Es ist entweder ein Pfad zu einer [csproj-Datei](csproj.md) oder zu einem Verzeichnis. Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis angegeben.

## <a name="options"></a>Optionen

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

Legt die Buildkonfiguration fest. Der Standardwert ist `Debug`.

`--force` erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war. Dies entspricht dem Löschen der Datei *project.assets.json*.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`--include-source`

Nimmt die Quelldateien in das NuGet-Paket auf. Die Quelldateien befinden sich im Ordner `src` im `nupkg`.

`--include-symbols`

Generiert die Symbole `nupkg`.

`--no-build`

Erstellt das Projekt nicht vor dem Packen.

`--no-dependencies`

Ignoriert Verweise zwischen Projekten und stellt nur das zum Erstellen angegebene Stammprojekt wieder her.

`--no-restore`

Führt kein implizites Wiederherstellen durch, wenn der Befehl ausgeführt wird

`-o|--output <OUTPUT_DIRECTORY>`

Platziert die erstellten Pakete in das angegebene Verzeichnis.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Gibt die Ziellaufzeit an, für die Pakete wiederhergestellt werden sollen Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).

`-s|--serviceable`

Legt das zu verarbeitende Flag im Paket fest. Weitere Informationen finden Sie unter [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries (.NET Blog: .NET 4.5.1 unterstützt Microsoft Sicherheitsupdates für .NET NuGet-Bibliotheken)](https://aka.ms/nupkgservicing).

`--version-suffix <VERSION_SUFFIX>`

Definiert den Wert für die `$(VersionSuffix)`-MSBuild-Eigenschaft im Projekt.

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

Legt die Buildkonfiguration fest. Der Standardwert ist `Debug`.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`--include-source`

Nimmt die Quelldateien in das NuGet-Paket auf. Die Quelldateien befinden sich im Ordner `src` im `nupkg`.

`--include-symbols`

Generiert die Symbole `nupkg`.

`--no-build`

Erstellt das Projekt nicht vor dem Packen.

`-o|--output <OUTPUT_DIRECTORY>`

Platziert die erstellten Pakete in das angegebene Verzeichnis.

`-s|--serviceable`

Legt das zu verarbeitende Flag im Paket fest. Weitere Informationen finden Sie unter [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries (.NET Blog: .NET 4.5.1 unterstützt Microsoft Sicherheitsupdates für .NET NuGet-Bibliotheken)](https://aka.ms/nupkgservicing).

`--version-suffix <VERSION_SUFFIX>`

Definiert den Wert für die `$(VersionSuffix)`-MSBuild-Eigenschaft im Projekt.

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

---

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

Packen Sie das Projekt für ein bestimmtes [Zielframework](../../standard/frameworks.md):

`dotnet pack /p:TargetFrameworks=net45`

Packen Sie das Projekt, und verwenden Sie eine bestimmte Runtime (Windows 10) für den Wiederherstellungsvorgang (.NET Core SDK 2.0 und spätere Versionen):

`dotnet pack --runtime win10-x64`