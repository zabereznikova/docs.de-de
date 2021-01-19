---
title: Befehl „dotnet build“
description: Der dotnet build-Befehl erstellt ein Projekt und alle seine Abhängigkeiten.
ms.date: 02/14/2020
ms.openlocfilehash: cc8c6ed30dbf8ff0602fb19e5001f618a8380f16
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189954"
---
# <a name="dotnet-build"></a>dotnet build

**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen

## <a name="name"></a>name

`dotnet build`: Erstellt ein Projekt und alle seine Abhängigkeiten

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [-f|--framework <FRAMEWORK>] [--force] [--interactive] [--no-dependencies]
    [--no-incremental] [--no-restore] [--nologo] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--runtime <RUNTIME_IDENTIFIER>] [--source <SOURCE>]
    [-v|--verbosity <LEVEL>] [--version-suffix <VERSION_SUFFIX>]

dotnet build -h|--help
```

## <a name="description"></a>Beschreibung

Der `dotnet build`-Befehl erstellt das Projekt und die zugehörigen Abhängigkeiten in einen Satz von Binärdateien. Die Binärdateien enthalten den Projektcode in IL-Dateien (Intermediate Language) mit der Erweiterung *DLL*.  Abhängig vom Projekttyp und den Einstellungen können auch andere Dateien enthalten sein, beispielsweise:

- Eine ausführbare Datei, die zum Ausführen der Anwendung verwendet werden kann, wenn der Projekttyp eine ausführbare Datei für .NET Core 3.0 oder höher ist.
- Symboldateien mit der Erweiterung *PDB*, die für das Debuggen verwendet werden.
- Eine Datei *.deps.json*, die die Abhängigkeiten der Anwendung oder Bibliothek auflistet.
- Eine Datei *.runtimeconfig.json*, die die freigegebene Laufzeit und deren Version für eine Anwendung angibt.
- Andere Bibliotheken, von denen das Projekt abhängig ist (über Projektverweise oder NuGet-Paketverweise).

Bei ausführbaren Projekten für frühere Versionen als .NET Core 3.0 werden Bibliotheksabhängigkeiten von NuGet in der Regel NICHT in den Ausgabeordner kopiert.  Sie werden zur Laufzeit aus dem NuGet-Ordner für globale Pakete aufgelöst. Bedenken Sie, dass das Produkt von `dotnet build` nicht auf einen anderen Computer zur Ausführung übertragen werden kann. Zum Erstellen einer Version der Anwendung, die bereitgestellt werden kann, müssen Sie sie veröffentlichen (z.B. mit dem Befehl [dotnet publish](dotnet-publish.md)). Weitere Informationen finden Sie unter [.NET-Anwendungsbereitstellung](../deploying/index.md).

Bei ausführbaren Projekten für .NET Core 3.0 oder höher werden Bibliotheksabhängigkeiten in den Ausgabeordner kopiert. Dies bedeutet, dass die Buildausgabe bereitstellbar sein sollte, wenn keine andere veröffentlichungsspezifische Logik (wie bei Webprojekten) vorhanden ist.

### <a name="implicit-restore"></a>Implizite Wiederherstellung

Das Erstellen erfordert die *project.assets.json*-Datei, die die Abhängigkeiten Ihrer Anwendung aufführt. Die Datei wird erstellt, wenn [`dotnet restore`](dotnet-restore.md) ausgeführt wird. Ohne die vorhandenen Ressourcendateien kann das Tool die Verweisassemblys nicht auflösen, was zu Fehlern führt.

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

### <a name="executable-or-library-output"></a>Ausgabe der ausführbaren Datei oder Bibliothek

Ob das Projekt ausführbar ist oder nicht, richtet sich nach der `<OutputType>`-Eigenschaft in der Projektdatei. Das folgende Beispiel zeigt ein Projekt, das ausführbaren Code erzeugt:

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

Um eine Bibliothek zu generieren, lassen Sie die Eigenschaft `<OutputType>` weg, oder ändern Sie ihren Wert in `Library`. Die IL-DLL für eine Bibliothek enthält keine Einstiegspunkte und kann nicht ausgeführt werden.

### <a name="msbuild"></a>MSBuild

`dotnet build` verwendet MSBuild zum Erstellen des Projekts und unterstützt daher parallele und inkrementelle Builds. Weitere Informationen finden Sie unter [Incremental Builds](/visualstudio/msbuild/incremental-builds) (Inkrementelle Builds).

Zusätzlich zu diesen Optionen akzeptiert der `dotnet build`-Befehl MSBuild-Optionen, wie z.B. `-p` zum Festlegen von Eigenschaften oder `-l` zum Definieren eines Protokolls. Weitere Informationen zu diesen Optionen finden Sie in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference). Sie können auch den Befehl [dotnet msbuild](dotnet-msbuild.md) verwenden.

Das Ausführen von `dotnet build` entspricht der Ausführung von `dotnet msbuild -restore`. Die Standardausführlichkeit der Ausgabe unterscheidet sich jedoch.

## <a name="arguments"></a>Argumente

`PROJECT | SOLUTION`

Die zu erstellende Projekt- oder Projektmappendatei. Wenn Sie keine Projekt- oder Projektmappendatei angeben, durchsucht MSBuild das aktuelle Arbeitsverzeichnis nach einer Dateierweiterung, die mit *proj* oder *sln* endet, und verwendet diese.

## <a name="options"></a>Optionen

- **`-c|--configuration <CONFIGURATION>`**

  Legt die Buildkonfiguration fest. Der Standardwert für die meisten Projekte ist `Debug`, aber Sie können die Buildkonfigurationseinstellungen in Ihrem Projekt überschreiben.

- **`-f|--framework <FRAMEWORK>`**

  Kompiliert für ein bestimmtes [Framework](../../standard/frameworks.md). Das Framework muss in der [Projektdatei](../project-sdk/overview.md) definiert werden.

- **`--force`**

  Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war. Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

- **`--interactive`**

  Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten. Beispielsweise, um die Authentifizierung abzuschließen. Verfügbar seit .NET Core 3.0 SDK.

- **`--no-dependencies`**

  Ignoriert Verweise zwischen Projekten (P2P) und erstellt nur das angegebene Stammprojekt.

- **`--no-incremental`**

  Markiert den Build als unsicher für inkrementelle Builds. Das Flag deaktiviert die inkrementelle Kompilierung und erzwingt eine komplette Neuerstellung des Abhängigkeitsdiagramms des Projekts.

- **`--no-restore`**

  Führt keine implizite Wiederherstellung während der Projekterstellung durch.

- **`--nologo`**

  Unterdrückt die Anzeige von Startbanner und Copyrightmeldung. Verfügbar seit .NET Core 3.0 SDK.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Verzeichnis, in dem die erstellten Binärdateien platziert werden. Wenn nicht angegeben, ist der Standardpfad `./bin/<configuration>/<framework>/`.  Bei Projekten mit mehreren Zielframeworks (über die `TargetFrameworks`-Eigenschaft) müssen Sie auch `--framework` definieren, wenn Sie diese Option angeben.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Legt die Ziellaufzeit fest. Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).

- **`--source <SOURCE>`**

  Der URI der NuGet-Paketquelle, die während des Wiederherstellungsvorgangs zu verwenden ist.

- **`-v|--verbosity <LEVEL>`**

  Legt den MSBuild-Ausführlichkeitsgrad fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`. Der Standardwert ist `minimal`.

- **`--version-suffix <VERSION_SUFFIX>`**

  Hiermit wird der Wert der `$(VersionSuffix)`-Eigenschaft festgelegt, die beim Erstellen des Projekts verwendet werden soll. Dies funktioniert nur, wenn die `$(Version)`-Eigenschaft nicht festgelegt ist. Dann wird `$(Version)` auf `$(VersionPrefix)` festgelegt, kombiniert mit dem `$(VersionSuffix)`, getrennt durch einen Bindestrich.

## <a name="examples"></a>Beispiele

- Erstellt ein Projekt und seine Abhängigkeiten:

  ```dotnetcli
  dotnet build
  ```

- Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:

  ```dotnetcli
  dotnet build --configuration Release
  ```

- Erstellt ein Projekt und seine Abhängigkeiten für eine bestimmte Laufzeit (in diesem Beispiel Ubuntu 18.04):

  ```dotnetcli
  dotnet build --runtime ubuntu.18.04-x64
  ```

- Erstellen eines Projekts und Verwenden der angegebenen NuGet-Paketquelle während des Wiederherstellungsvorgangs:

  ```dotnetcli
  dotnet build --source c:\packages\mypackages
  ```

- Erstellen eines Projekts und festlegen der Version 1.2.3.4 als Buildparameter mithilfe der `-p`[MSBuild-Option](#msbuild):

  ```dotnetcli
  dotnet build -p:Version=1.2.3.4
  ```
