---
title: Befehl „dotnet clean“
description: Mit dem Befehl „dotnet clean“ wird das aktuelle Verzeichnis bereinigt.
ms.date: 06/26/2019
ms.openlocfilehash: 982232833b460b4ea4181acebee74dcef54d3131
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117743"
---
# <a name="dotnet-clean"></a>dotnet clean

**Dieses Thema gilt für: ✓**.NET Core 1.x SDK und spätere Versionen

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>NAME

`dotnet clean`: Löscht die Ausgabe eines Projekts.

## <a name="synopsis"></a>Zusammenfassung

```dotnetcli
dotnet clean [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--interactive] 
    [--nologo] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a>BESCHREIBUNG

Der Befehl `dotnet clean` löscht die Ausgabe des vorherigen Builds. Er ist als [MSBuild-Ziel](/visualstudio/msbuild/msbuild-targets) implementiert, sodass das Projekt ausgewertet wird, wenn der Befehl ausgeführt wird. Es werden nur die Ausgaben gelöscht, die während des Builds erstellt wurden. Sowohl der Ordner für Zwischenausgabe (*obj*) als auch der Ordner für die endgültige Ausgabe (*bin*) werden bereinigt.

## <a name="arguments"></a>Argumente

`PROJECT | SOLUTION`

MSBuild-Projekt oder Projektmappe, das/die bereinigt werden soll. Wenn Sie keine Projekt- oder Projektmappendatei angeben, durchsucht MSBuild das aktuelle Arbeitsverzeichnis nach einer Dateierweiterung, die mit *proj* oder *sln* endet, und verwendet diese.

## <a name="options"></a>Optionen

* **`-c|--configuration {Debug|Release}`**

  Legt die Buildkonfiguration fest. Standardwert: `Debug`. Diese Option ist bei der Bereinigung nur erforderlich, wenn Sie sie bei der Erstellung angegeben haben.

* **`-f|--framework <FRAMEWORK>`**

  Das [Framework](../../standard/frameworks.md), das bei der Erstellung angegeben wurde. Das Framework muss in der [Projektdatei](csproj.md) definiert werden. Wenn Sie das Framework bei der Erstellung angegeben haben, müssen Sie das Framework bei der Bereinigung angeben.

* **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

* **`--interactive`**

  Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten. Beispielsweise, um die Authentifizierung abzuschließen. Verfügbar seit .NET Core 3.0 SDK.

* **`--nologo`**

  Unterdrückt die Anzeige von Startbanner und Copyrightmeldung. Verfügbar seit .NET Core 3.0 SDK.

* **`-o|--output <OUTPUT_DIRECTORY>`**

  Das Verzeichnis mit den zu bereinigenden Buildartefakten. Geben Sie den `-f|--framework <FRAMEWORK>`-Schalter mit dem Schalter des Ausgabeverzeichnisses an, wenn Sie das Framework bei der Erstellung des Projekts angegeben haben.

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Bereinigt den Ausgabeordner der angegebenen Runtime Wird bei der Erstellung einer [eigenständigen Bereitstellung](../deploying/index.md#self-contained-deployments-scd) verwendet. Die Option ist seit dem .NET Core 2.0 SDK verfügbar.

* **`-v|--verbosity <LEVEL>`**

  Legt den MSBuild-Ausführlichkeitsgrad fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`. Der Standardwert lautet `normal`.

## <a name="examples"></a>Beispiele

* Bereinigen Sie einen Standardbuild des Projekts:

  ```dotnetcli
  dotnet clean
  ```

* Bereinigen Sie ein Projektbuild mit der Konfiguration „Release“:

  ```dotnetcli
  dotnet clean --configuration Release
  ```
