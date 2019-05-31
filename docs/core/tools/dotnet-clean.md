---
title: Befehl „dotnet clean“
description: Mit dem Befehl „dotnet clean“ wird das aktuelle Verzeichnis bereinigt.
ms.date: 04/14/2019
ms.openlocfilehash: fa19f1b041e4031082f928135395a5f06ce702e9
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631823"
---
# <a name="dotnet-clean"></a>dotnet clean

**Dieses Thema gilt für: ✓**.NET Core 1.x SDK und spätere Versionen

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>name

`dotnet clean`: Löscht die Ausgabe eines Projekts.

## <a name="synopsis"></a>Übersicht

```
dotnet clean [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--interactive] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet clean` löscht die Ausgabe des vorherigen Builds. Er ist als [MSBuild-Ziel](/visualstudio/msbuild/msbuild-targets) implementiert, sodass das Projekt ausgewertet wird, wenn der Befehl ausgeführt wird. Es werden nur die Ausgaben gelöscht, die während des Builds erstellt wurden. Sowohl der Ordner für Zwischenausgabe (*obj*) als auch der Ordner für die endgültige Ausgabe (*bin*) werden bereinigt.

## <a name="arguments"></a>Argumente

`PROJECT | SOLUTION`

MSBuild-Projekt oder Projektmappe, das/die bereinigt werden soll. Wenn Sie keine Projekt- oder Projektmappendatei angeben, durchsucht MSBuild das aktuelle Arbeitsverzeichnis nach einer Dateierweiterung, die mit *proj* oder *sln* endet, und verwendet diese.

## <a name="options"></a>Optionen

* **`-c|--configuration {Debug|Release}`**

  Legt die Buildkonfiguration fest. Der Standardwert ist `Debug`sein. Diese Option ist bei der Bereinigung nur erforderlich, wenn Sie sie bei der Erstellung angegeben haben.

* **`-f|--framework <FRAMEWORK>`**

  Das [Framework](../../standard/frameworks.md), das bei der Erstellung angegeben wurde. Das Framework muss in der [Projektdatei](csproj.md) definiert werden. Wenn Sie das Framework bei der Erstellung angegeben haben, müssen Sie das Framework bei der Bereinigung angeben.

* **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

* **`--interactive`**

  Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten. Beispielsweise, um die Authentifizierung abzuschließen. Verfügbar seit .NET Core 3.0 SDK.

* **`-o|--output <OUTPUT_DIRECTORY>`**

  Das Verzeichnis mit den zu bereinigenden Buildartefakten. Geben Sie den `-f|--framework <FRAMEWORK>`-Schalter mit dem Schalter des Ausgabeverzeichnisses an, wenn Sie das Framework bei der Erstellung des Projekts angegeben haben.

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Bereinigt den Ausgabeordner der angegebenen Runtime Wird bei der Erstellung einer [eigenständigen Bereitstellung](../deploying/index.md#self-contained-deployments-scd) verwendet. Die Option ist seit dem .NET Core 2.0 SDK verfügbar.

* **`-v|--verbosity <LEVEL>`**

  Legt den MSBuild-Ausführlichkeitsgrad fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`. Die Standardeinstellung ist `normal`.

## <a name="examples"></a>Beispiele

* Bereinigen Sie einen Standardbuild des Projekts:

  ```console
  dotnet clean
  ```

* Bereinigen Sie ein Projektbuild mit der Konfiguration „Release“:

  ```console
  dotnet clean --configuration Release
  ```
