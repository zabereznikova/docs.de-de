---
title: Befehl „dotnet pack“
description: Der dotnet pack-Befehl erstellt NuGet-Pakete für ein .NET Core-Projekt.
ms.date: 08/08/2019
ms.openlocfilehash: ba5a438d58963222c3fa55d2c585ef503dcd49db
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70990411"
---
# <a name="dotnet-pack"></a>dotnet pack

**Dieses Thema gilt für: ✓**.NET Core 1.x SDK und spätere Versionen

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>name

`dotnet pack`: Packt den Code in ein NuGet-Paket

## <a name="synopsis"></a>Übersicht

```console
dotnet pack [<PROJECT>|<SOLUTION>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--interactive] 
    [--no-build] [--no-dependencies] [--no-restore] [--nologo] [-o|--output] [--runtime] [-s|--serviceable] 
    [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```

## <a name="description"></a>BESCHREIBUNG

Der Befehl `dotnet pack` erstellt das Projekt und NuGet-Pakete. Das Ergebnis dieses Befehls ist ein NuGet-Paket (d. h., eine *NUPKG*-Datei). 

Wenn Sie ein Paket generieren möchten, das die Debugsymbole enthält, stehen Ihnen zwei Optionen zur Verfügung:

- `--include-symbols`: Es erstellt das Symbolpaket.
- `--include-source`: Es erstellt das Symbolpaket mit einem `src`-Ordner, der die Quelldateien enthält.

NuGet-Abhängigkeiten des gepackten Projekts werden der Datei *nuspec* hinzugefügt. Sie werden ordnungsgemäß aufgelöst, wenn das Paket installiert wird. Verweise zwischen Projekten werden innerhalb des Projekts nicht gepackt. Derzeit benötigen Sie ein Paket pro Projekt, wenn Sie Abhängigkeiten zwischen Projekten haben.

`dotnet pack` erstellt standardmäßig zuerst das Projekt. Wenn Sie dieses Verhalten vermeiden möchten, übergeben Sie die Option `--no-build`. Diese Option ist bei Buildszenarios der Continuous Integration (CI) oft hilfreich, bei denen Sie wissen, dass der Code kürzlich erstellt wurde.

Sie können dem `dotnet pack`-Befehl MSBuild-Eigenschaften für den Packvorgang bereitstellen. Weitere Informationen finden Sie in den [NuGet-Metadateneigenschaften](csproj.md#nuget-metadata-properties) und in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference). Der Abschnitt [Beispiele](#examples) enthält Informationen darüber, wie der MSBuild-Schalter „-p“ für verschiedene Szenarien verwendet wird.

Webprojekte können standardmäßig nicht verpackt werden. Um das Standardverhalten zu überschreiben, fügen Sie Ihrer *.csproj*-Datei die folgende Eigenschaft hinzu:

```xml
<PropertyGroup>
   <IsPackable>true</IsPackable>
</PropertyGroup>
```

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a>Argumente

`PROJECT | SOLUTION`

  Das Projekt oder die Projektmappe, die gepackt werden soll. Es ist entweder ein Pfad zu einer [CSPROJ-Datei](csproj.md), einer Projektmappendatei oder zu einem Verzeichnis. Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einem Projekt oder einer Projektmappendatei.

## <a name="options"></a>Optionen

* **`-c|--configuration {Debug|Release}`**

  Legt die Buildkonfiguration fest. Der Standardwert ist `Debug`sein.

* **`--force`**

  Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war. Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*. Die Option ist seit dem .NET Core 2.0 SDK verfügbar.

* **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

* **`--include-source`**

  Schließt neben den regulären NuGet-Paketen im Ausgabeverzeichnis auch die NuGet-Pakete der Debugsymbole ein. Die Quelldateien befinden sich im `src`-Ordner im Symbolpaket.

* **`--include-symbols`**

  Schließt neben den regulären NuGet-Paketen im Ausgabeverzeichnis auch die NuGet-Pakete der Debugsymbole ein.

* **`--interactive`**

  Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen). Verfügbar seit .NET Core 3.0 SDK.

* **`--no-build`**

  Erstellt das Projekt nicht vor dem Packen. Zudem wird das Flag `--no-restore` implizit festgelegt.

* **`--no-dependencies`**

  Ignoriert Verweise zwischen Projekten und stellt nur das zum Erstellen angegebene Stammprojekt wieder her. Die Option ist seit dem .NET Core 2.0 SDK verfügbar.

* **`--no-restore`**

  Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird. Die Option ist seit dem .NET Core 2.0 SDK verfügbar.

* **`--nologo`**

  Unterdrückt die Anzeige von Startbanner und Copyrightmeldung. Verfügbar seit .NET Core 3.0 SDK.

* **`-o|--output <OUTPUT_DIRECTORY>`**

  Platziert die erstellten Pakete in das angegebene Verzeichnis.

* **`--runtime <RUNTIME_IDENTIFIER>`**

  Gibt die Ziellaufzeit an, für die Pakete wiederhergestellt werden sollen Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md). Die Option ist seit dem .NET Core 2.0 SDK verfügbar.

* **`-s|--serviceable`**

  Legt das zu verarbeitende Flag im Paket fest. Weitere Informationen finden Sie unter [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries (.NET Blog: .NET 4.5.1 unterstützt Microsoft Sicherheitsupdates für .NET NuGet-Bibliotheken)](https://aka.ms/nupkgservicing).

* **`--version-suffix <VERSION_SUFFIX>`**

  Definiert den Wert für die `$(VersionSuffix)`-MSBuild-Eigenschaft im Projekt.

* **`-v|--verbosity <LEVEL>`**

  Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

## <a name="examples"></a>Beispiele

* Packt das Projekt im aktuellen Verzeichnis:

  ```console
  dotnet pack
  ```

* Packt das `app1`-Projekt:

  ```console
  dotnet pack ~/projects/app1/project.csproj
  ```

* Packt das Projekt im aktuellen Verzeichnis, und platziert die erstellten Pakete in den `nupkgs`-Ordner:

  ```console
  dotnet pack --output nupkgs
  ```

* Packt das Projekt im aktuellen Verzeichnis in den `nupkgs`-Ordner und überspringt den Buildschritt:

  ```console
  dotnet pack --no-build --output nupkgs
  ```

* Mit dem Versionssuffix des Projekts, das als `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in der *.csproj*-Datei konfiguriert ist, packen Sie das aktuelle Projekt, und aktualisieren Sie die resultierende Paketversion mit dem angegebenen Suffix:

  ```console
  dotnet pack --version-suffix "ci-1234"
  ```

* Legen Sie die Paketversion auf `2.1.0` mithilfe der MSBuild-Eigenschaft `PackageVersion` fest.

  ```console
  dotnet pack -p:PackageVersion=2.1.0
  ```

* Packen Sie das Projekt für ein bestimmtes [Zielframework](../../standard/frameworks.md):

  ```console
  dotnet pack -p:TargetFrameworks=net45
  ```

* Packen Sie das Projekt, und verwenden Sie eine bestimmte Runtime (Windows 10) für den Wiederherstellungsvorgang (.NET Core SDK 2.0 und spätere Versionen):

  ```console
  dotnet pack --runtime win10-x64
  ```

* Packen Sie das Projekt mithilfe einer [NUSPEC-Datei](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec):

  ```console
  dotnet pack ~/projects/app1/project.csproj -p:NuspecFile=~/projects/app1/project.nuspec -p:NuspecBasePath=~/projects/app1/nuget
  ```
