---
title: Befehl „dotnet pack“
description: Der Befehl „dotnet pack“ erstellt NuGet-Pakete für ein .NET-Projekt.
ms.date: 04/28/2020
ms.openlocfilehash: 3ca7947b4ed9902b163f09a7b57696f304610cce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674800"
---
# <a name="dotnet-pack"></a>dotnet pack

**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen

## <a name="name"></a>name

`dotnet pack`: Packt den Code in ein NuGet-Paket

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet pack [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [--force] [--include-source] [--include-symbols] [--interactive]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output <OUTPUT_DIRECTORY>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--serviceable] [-v|--verbosity <LEVEL>]
    [--version-suffix <VERSION_SUFFIX>]

dotnet pack -h|--help
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet pack` erstellt das Projekt und NuGet-Pakete. Das Ergebnis dieses Befehls ist ein NuGet-Paket (d. h., eine *NUPKG*-Datei).

Wenn Sie ein Paket generieren möchten, das die Debugsymbole enthält, stehen Ihnen zwei Optionen zur Verfügung:

- `--include-symbols`: Es erstellt das Symbolpaket.
- `--include-source`: Es erstellt das Symbolpaket mit einem `src`-Ordner, der die Quelldateien enthält.

NuGet-Abhängigkeiten des gepackten Projekts werden der Datei *nuspec* hinzugefügt. Sie werden ordnungsgemäß aufgelöst, wenn das Paket installiert wird. Verweise zwischen Projekten werden innerhalb des Projekts nicht gepackt. Derzeit benötigen Sie ein Paket pro Projekt, wenn Sie Abhängigkeiten zwischen Projekten haben.

`dotnet pack` erstellt standardmäßig zuerst das Projekt. Wenn Sie dieses Verhalten vermeiden möchten, übergeben Sie die Option `--no-build`. Diese Option ist bei Buildszenarios der Continuous Integration (CI) oft hilfreich, bei denen Sie wissen, dass der Code kürzlich erstellt wurde.

> [!NOTE]
> In einigen Fällen kann die implizierte Kompilierung nicht ausgeführt werden. Dies kann passieren, wenn `GeneratePackageOnBuild` festgelegt ist, um eine zyklische Abhängigkeit zwischen Build und Paketzielen zu vermeiden. Die Kompilierung kann auch fehlschlagen, wenn eine gesperrte Datei oder ein anderes Problem vorliegt.

Sie können dem `dotnet pack`-Befehl MSBuild-Eigenschaften für den Packvorgang bereitstellen. Weitere Informationen finden Sie in den [NuGet-Metadateneigenschaften](csproj.md#nuget-metadata-properties) und in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference). Der Abschnitt [Beispiele](#examples) enthält Informationen darüber, wie der MSBuild-Schalter „-p“ für verschiedene Szenarien verwendet wird.

Webprojekte können standardmäßig nicht verpackt werden. Um das Standardverhalten zu überschreiben, fügen Sie Ihrer *.csproj*-Datei die folgende Eigenschaft hinzu:

```xml
<PropertyGroup>
   <IsPackable>true</IsPackable>
</PropertyGroup>
```

### <a name="implicit-restore"></a>Implizite Wiederherstellung

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a>Argumente

`PROJECT | SOLUTION`

  Das Projekt oder die Projektmappe, die gepackt werden soll. Es ist entweder ein Pfad zu einer [CSPROJ-Datei](csproj.md), VBPROJ-Datei, FSPROJ-Datei, Projektmappendatei oder einem Verzeichnis. Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einem Projekt oder einer Projektmappendatei.

## <a name="options"></a>Optionen

- **`-c|--configuration <CONFIGURATION>`**

  Legt die Buildkonfiguration fest. Der Standardwert für die meisten Projekte ist `Debug`, aber Sie können die Buildkonfigurationseinstellungen in Ihrem Projekt überschreiben.

- **`--force`**

  Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war. Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

- **`--include-source`**

  Schließt neben den regulären NuGet-Paketen im Ausgabeverzeichnis auch die NuGet-Pakete der Debugsymbole ein. Die Quelldateien befinden sich im `src`-Ordner im Symbolpaket.

- **`--include-symbols`**

  Schließt neben den regulären NuGet-Paketen im Ausgabeverzeichnis auch die NuGet-Pakete der Debugsymbole ein.

- **`--interactive`**

  Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen). Verfügbar seit .NET Core 3.0 SDK.

- **`--no-build`**

  Erstellt das Projekt nicht vor dem Packen. Zudem wird das Flag `--no-restore` implizit festgelegt.

- **`--no-dependencies`**

  Ignoriert Verweise zwischen Projekten und stellt nur das zum Erstellen angegebene Stammprojekt wieder her.

- **`--no-restore`**

  Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.

- **`--nologo`**

  Unterdrückt die Anzeige von Startbanner und Copyrightmeldung. Verfügbar seit .NET Core 3.0 SDK.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Platziert die erstellten Pakete in das angegebene Verzeichnis.

- **`--runtime <RUNTIME_IDENTIFIER>`**

  Gibt die Ziellaufzeit an, für die Pakete wiederhergestellt werden sollen Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).

- **`-s|--serviceable`**

  Legt das zu verarbeitende Flag im Paket fest. Weitere Informationen finden Sie unter [.NET Blog: .NET Framework 4.5.1 unterstützt Microsoft-Sicherheitsupdates für .NET-NuGet-Bibliotheken](https://aka.ms/nupkgservicing).

- **`--version-suffix <VERSION_SUFFIX>`**

  Definiert den Wert für die `$(VersionSuffix)`-MSBuild-Eigenschaft im Projekt.

- **`-v|--verbosity <LEVEL>`**

  Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

## <a name="examples"></a>Beispiele

- Packt das Projekt im aktuellen Verzeichnis:

  ```dotnetcli
  dotnet pack
  ```

- Packt das `app1`-Projekt:

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj
  ```

- Packt das Projekt im aktuellen Verzeichnis, und platziert die erstellten Pakete in den `nupkgs`-Ordner:

  ```dotnetcli
  dotnet pack --output nupkgs
  ```

- Packt das Projekt im aktuellen Verzeichnis in den `nupkgs`-Ordner und überspringt den Buildschritt:

  ```dotnetcli
  dotnet pack --no-build --output nupkgs
  ```

- Mit dem Versionssuffix des Projekts, das als `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in der *.csproj*-Datei konfiguriert ist, packen Sie das aktuelle Projekt, und aktualisieren Sie die resultierende Paketversion mit dem angegebenen Suffix:

  ```dotnetcli
  dotnet pack --version-suffix "ci-1234"
  ```

- Legen Sie die Paketversion auf `2.1.0` mithilfe der MSBuild-Eigenschaft `PackageVersion` fest.

  ```dotnetcli
  dotnet pack -p:PackageVersion=2.1.0
  ```

- Packen Sie das Projekt für ein bestimmtes [Zielframework](../../standard/frameworks.md):

  ```dotnetcli
  dotnet pack -p:TargetFrameworks=net45
  ```

- Packen Sie das Projekt, und verwenden Sie eine bestimmte Runtime (Windows 10) für den Wiederherstellungsvorgang:

  ```dotnetcli
  dotnet pack --runtime win10-x64
  ```

- Packen Sie das Projekt mithilfe einer *NUSPEC-Datei*:

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj -p:NuspecFile=~/projects/app1/project.nuspec -p:NuspecBasePath=~/projects/app1/nuget
  ```

  Informationen zur Verwendung von `NuspecFile`, `NuspecBasePath` und `NuspecProperties` finden Sie in den folgenden Ressourcen:

  - [Packen mithilfe einer NUSPEC-Datei](/nuget/reference/msbuild-targets#packing-using-a-nuspec)
  - [Verbesserte Erweiterungspunkte zum Erstellen benutzerdefinierter Pakete](/nuget/reference/msbuild-targets#advanced-extension-points-to-create-customized-package)
  - [Globale Eigenschaften](/visualstudio/msbuild/msbuild-properties#global-properties)
