---
title: Befehl „dotnet build“
description: Der dotnet build-Befehl erstellt ein Projekt und alle seine Abhängigkeiten.
ms.date: 10/07/2019
ms.openlocfilehash: db353feebab920dc8f63b9854d14f050adeb0b79
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250189"
---
# <a name="dotnet-build"></a>dotnet build

**Dieser Artikel gilt für: ✓**.NET Core 1.x SDK und spätere Versionen

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>name

`dotnet build`: Erstellt ein Projekt und alle seine Abhängigkeiten

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--force] [--interactive] [--no-dependencies]
    [--no-incremental] [--no-restore] [--nologo] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```

## <a name="description"></a>BESCHREIBUNG

Der `dotnet build`-Befehl erstellt das Projekt und die zugehörigen Abhängigkeiten in einen Satz von Binärdateien. Die Binärdateien enthalten den Projektcode in Intermediate Language-Dateien (IL) mit einer *.dll*-Erweiterung und Symboldateien, die zum Debuggen mit einer *.pdb*-Erweiterung verwendet werden. Eine JSON-Datei für Abhängigkeiten ( *.deps.json*) wird erstellt, die die Abhängigkeiten der Anwendung aufführt. Eine Datei vom Typ *.runtimeconfig.json* wird erstellt, die die freigegebene Laufzeit und deren Version für die Anwendung angibt.

Verfügt das Projekt über Abhängigkeiten von Drittanbietern, z.B. Bibliotheken von NuGet, werden diese aus dem NuGet-Cache aufgelöst und sind nicht mit der Buildausgabe des Projekts verfügbar. Bedenken Sie, dass das Produkt von `dotnet build` nicht auf einen anderen Computer zur Ausführung übertragen werden kann. Dies unterscheidet sich zum Verhalten des .NET Framework, bei dem die Erstellung eines ausführbaren Projekts (eine Anwendung) eine Ausgabe erzeugt, die auf jedem Computer ausgeführt werden kann, auf dem .NET Framework installiert ist. Um ein ähnliches Verhalten mit .NET Core zu erhalten, müssen Sie den Befehl [dotnet publish](dotnet-publish.md) verwenden. Weitere Informationen finden Sie unter [.NET Core Anwendungsbereitstellung](../deploying/index.md).

Das Erstellen erfordert die *project.assets.json*-Datei, die die Abhängigkeiten Ihrer Anwendung aufführt. Die Datei wird erstellt, wenn [`dotnet restore`](dotnet-restore.md) ausgeführt wird. Ohne die vorhandenen Ressourcendateien kann das Tool die Verweisassemblys nicht auflösen, was zu Fehlern führt. Mit dem .NET Core 1.x SDK müssen Sie `dotnet restore` explizit ausführen, bevor Sie `dotnet build` ausführen. Ab dem .NET Core 2.0 SDK wird `dotnet restore` implizit ausgeführt, wenn Sie `dotnet build` ausführen. Wenn Sie das implizite Wiederherstellen deaktivieren möchten, wenn Sie den Buildbefehl ausführen, können Sie die `--no-restore`-Option übergeben.

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

Ob das Projekt ausführbar ist oder nicht, richtet sich nach der `<OutputType>`-Eigenschaft in der Projektdatei. Das folgende Beispiel zeigt ein Projekt, das ausführbaren Code erzeugt:

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

Lassen Sie die `<OutputType>`-Eigenschaft weg, um eine Bibliothek zu erstellen. Der Hauptunterschied in der Buildausgabe ist, dass die IL-DLL für eine Bibliothek keine Einstiegspunkte enthält und nicht ausgeführt werden kann.

### <a name="msbuild"></a>MSBuild

`dotnet build` verwendet MSBuild zum Erstellen des Projekts und unterstützt daher parallele und inkrementelle Builds. Weitere Informationen finden Sie unter [Incremental Builds](/visualstudio/msbuild/incremental-builds) (Inkrementelle Builds).

Zusätzlich zu diesen Optionen akzeptiert der `dotnet build`-Befehl MSBuild-Optionen, wie z.B. `-p` zum Festlegen von Eigenschaften oder `-l` zum Definieren eines Protokolls. Weitere Informationen zu diesen Optionen finden Sie in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference). Sie können auch den Befehl [dotnet msbuild](dotnet-msbuild.md) verwenden.

Die Ausführung von `dotnet build` entspricht `dotnet msbuild -restore -target:Build`.

## <a name="arguments"></a>Argumente

`PROJECT | SOLUTION`

Die zu erstellende Projekt- oder Projektmappendatei. Wenn Sie keine Projekt- oder Projektmappendatei angeben, durchsucht MSBuild das aktuelle Arbeitsverzeichnis nach einer Dateierweiterung, die mit *proj* oder *sln* endet, und verwendet diese.

## <a name="options"></a>Optionen

* **`-c|--configuration {CONFIGURATION}`**

  Legt die Buildkonfiguration fest. Der Standardwert für die meisten Projekte ist `Debug`, aber Sie können die Buildkonfigurationseinstellungen in Ihrem Projekt überschreiben.

* **`-f|--framework <FRAMEWORK>`**

  Kompiliert für ein bestimmtes [Framework](../../standard/frameworks.md). Das Framework muss in der [Projektdatei](csproj.md) definiert werden.

* **`--force`**

  Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war. Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*. Verfügbar seit .NET Core 2.0 SDK.

* **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

* **`--interactive`**

  Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten. Beispielsweise, um die Authentifizierung abzuschließen. Verfügbar seit .NET Core 3.0 SDK.

* **`--no-dependencies`**

  Ignoriert Verweise zwischen Projekten (P2P) und erstellt nur das angegebene Stammprojekt.

* **`--no-incremental`**

  Markiert den Build als unsicher für inkrementelle Builds. Das Flag deaktiviert die inkrementelle Kompilierung und erzwingt eine komplette Neuerstellung des Abhängigkeitsdiagramms des Projekts.

* **`--no-restore`**

  Führt keine implizite Wiederherstellung während der Projekterstellung durch. Verfügbar seit .NET Core 2.0 SDK.

* **`--nologo`**

  Unterdrückt die Anzeige von Startbanner und Copyrightmeldung. Verfügbar seit .NET Core 3.0 SDK.

* **`-o|--output <OUTPUT_DIRECTORY>`**

  Verzeichnis, in dem die erstellten Binärdateien platziert werden. Sie müssen außerdem `--framework` definieren, wenn Sie diese Option angeben. Wenn nicht angegeben, ist der Standardpfad `./bin/<configuration>/<framework>/`.

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Legt die Ziellaufzeit fest. Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).

* **`-v|--verbosity <LEVEL>`**

  Legt den MSBuild-Ausführlichkeitsgrad fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`. Die Standardeinstellung ist `minimal`.

* **`--version-suffix <VERSION_SUFFIX>`**

  Hiermit wird der Wert der `$(VersionSuffix)`-Eigenschaft festgelegt, die beim Erstellen des Projekts verwendet werden soll. Dies funktioniert nur, wenn die `$(Version)`-Eigenschaft nicht festgelegt ist. Dann wird `$(Version)` auf `$(VersionPrefix)` festgelegt, kombiniert mit dem `$(VersionSuffix)`, getrennt durch einen Bindestrich.

## <a name="examples"></a>Beispiele

* Erstellt ein Projekt und seine Abhängigkeiten:

  ```dotnetcli
  dotnet build
  ```

* Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:

  ```dotnetcli
  dotnet build --configuration Release
  ```

* Erstellt ein Projekt und seine Abhängigkeiten für eine bestimmte Laufzeit (in diesem Beispiel Ubuntu 18.04):

  ```dotnetcli
  dotnet build --runtime ubuntu.18.04-x64
  ```

* Erstellt ein Projekt und verwendet die angegebene NuGet-Paketquelle während des Wiederherstellungsvorgangs (.NET Core 2.0 SDK und spätere Versionen):

  ```dotnetcli
  dotnet build --source c:\packages\mypackages
  ```

* Erstellen Sie das Projekt, und legen Sie Version 1.2.3.4 als Buildparameter mithilfe der `-p` [MSBuild-Option](#msbuild) fest:

  ```dotnetcli
  dotnet build -p:Version=1.2.3.4
  ```
