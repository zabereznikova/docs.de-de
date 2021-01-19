---
title: Befehl „dotnet clean“
description: Mit dem Befehl „dotnet clean“ wird das aktuelle Verzeichnis bereinigt.
ms.date: 02/14/2020
ms.openlocfilehash: 1023f13c7662abb7dad613128631c7644ca15bb9
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189602"
---
# <a name="dotnet-clean"></a>dotnet clean

**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen

## <a name="name"></a>Name

`dotnet clean`: Löscht die Ausgabe eines Projekts.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet clean [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [-f|--framework <FRAMEWORK>] [--interactive]
    [--nologo] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--runtime <RUNTIME_IDENTIFIER>] [-v|--verbosity <LEVEL>]

dotnet clean -h|--help
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet clean` löscht die Ausgabe des vorherigen Builds. Er ist als [MSBuild-Ziel](/visualstudio/msbuild/msbuild-targets) implementiert, sodass das Projekt ausgewertet wird, wenn der Befehl ausgeführt wird. Es werden nur die Ausgaben gelöscht, die während des Builds erstellt wurden. Sowohl der Ordner für Zwischenausgabe (*obj*) als auch der Ordner für die endgültige Ausgabe (*bin*) werden bereinigt.

## <a name="arguments"></a>Argumente

`PROJECT | SOLUTION`

MSBuild-Projekt oder Projektmappe, das/die bereinigt werden soll. Wenn Sie keine Projekt- oder Projektmappendatei angeben, durchsucht MSBuild das aktuelle Arbeitsverzeichnis nach einer Dateierweiterung, die mit *proj* oder *sln* endet, und verwendet diese.

## <a name="options"></a>Optionen

* **`-c|--configuration <CONFIGURATION>`**

  Legt die Buildkonfiguration fest. Der Standardwert für die meisten Projekte ist `Debug`, aber Sie können die Buildkonfigurationseinstellungen in Ihrem Projekt überschreiben. Diese Option ist bei der Bereinigung nur erforderlich, wenn Sie sie bei der Erstellung angegeben haben.

* **`-f|--framework <FRAMEWORK>`**

  Das [Framework](../../standard/frameworks.md), das bei der Erstellung angegeben wurde. Das Framework muss in der [Projektdatei](../project-sdk/overview.md) definiert werden. Wenn Sie das Framework bei der Erstellung angegeben haben, müssen Sie das Framework bei der Bereinigung angeben.

* **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

* **`--interactive`**

  Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten. Beispielsweise, um die Authentifizierung abzuschließen. Verfügbar seit .NET Core 3.0 SDK.

* **`--nologo`**

  Unterdrückt die Anzeige von Startbanner und Copyrightmeldung. Verfügbar seit .NET Core 3.0 SDK.

* **`-o|--output <OUTPUT_DIRECTORY>`**

  Das Verzeichnis mit den zu bereinigenden Buildartefakten. Geben Sie den `-f|--framework <FRAMEWORK>`-Schalter mit dem Schalter des Ausgabeverzeichnisses an, wenn Sie das Framework bei der Erstellung des Projekts angegeben haben.

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Bereinigt den Ausgabeordner der angegebenen Runtime Wird bei der Erstellung einer [eigenständigen Bereitstellung](../deploying/index.md#publish-self-contained) verwendet.

* **`-v|--verbosity <LEVEL>`**

  Legt den MSBuild-Ausführlichkeitsgrad fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`. Der Standardwert ist `normal`.

## <a name="examples"></a>Beispiele

* Bereinigen Sie einen Standardbuild des Projekts:

  ```dotnetcli
  dotnet clean
  ```

* Bereinigen Sie ein Projektbuild mit der Konfiguration „Release“:

  ```dotnetcli
  dotnet clean --configuration Release
  ```
