---
title: dotnet clean-Befehl – .NET Core-CLI
description: Mit dem Befehl „dotnet clean“ wird das aktuelle Verzeichnis bereinigt.
ms.date: 12/04/2018
ms.openlocfilehash: 9930d2905f234e7125f27367cda36aa85ae23b87
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144454"
---
# <a name="dotnet-clean"></a>dotnet clean

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet clean`: Löscht die Ausgabe eines Projekts.

## <a name="synopsis"></a>Übersicht

```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet clean` löscht die Ausgabe des vorherigen Builds. Er ist als [MSBuild-Ziel](/visualstudio/msbuild/msbuild-targets) implementiert, sodass das Projekt ausgewertet wird, wenn der Befehl ausgeführt wird. Es werden nur die Ausgaben gelöscht, die während des Builds erstellt wurden. Sowohl der Ordner für Zwischenausgabe (*obj*) als auch der Ordner für die endgültige Ausgabe (*bin*) werden bereinigt.

## <a name="arguments"></a>Argumente

`PROJECT`

Das zu bereinigende MSBuild-Projekt. Wenn Sie keine Projektdatei angeben, durchsucht MSBuild das aktuelle Arbeitsverzeichnis nach einer Dateierweiterung, die mit *proj* endet, und verwendet diese.

## <a name="options"></a>Optionen

* **`-c|--configuration {Debug|Release}`**

  Legt die Buildkonfiguration fest. Der Standardwert ist `Debug`sein. Diese Option ist bei der Bereinigung nur erforderlich, wenn Sie sie bei der Erstellung angegeben haben.

* **`-f|--framework <FRAMEWORK>`**

  Das [Framework](../../standard/frameworks.md), das bei der Erstellung angegeben wurde. Das Framework muss in der [Projektdatei](csproj.md) definiert werden. Wenn Sie das Framework bei der Erstellung angegeben haben, müssen Sie das Framework bei der Bereinigung angeben.

* **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

* **`-o|--output <OUTPUT_DIRECTORY>`**

  Verzeichnis, in dem die Buildausgaben abgelegt wurden. Geben Sie den `-f|--framework <FRAMEWORK>`-Schalter mit dem Schalter des Ausgabeverzeichnisses an, wenn Sie das Framework bei der Erstellung des Projekts angegeben haben.

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Bereinigt den Ausgabeordner der angegebenen Runtime Wird bei der Erstellung einer [eigenständigen Bereitstellung](../deploying/index.md#self-contained-deployments-scd) verwendet. Die Option ist seit dem .NET Core 2.0 SDK verfügbar.

* **`-v|--verbosity <LEVEL>`**

  Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Grade sind q[uiet], m[inimal], n[ormal], d[etailed] und diag[nostic].

## <a name="examples"></a>Beispiele

* Bereinigen Sie einen Standardbuild des Projekts:

  ```console
  dotnet clean
  ```

* Bereinigen Sie ein Projektbuild mit der Konfiguration „Release“:

  ```console
  dotnet clean --configuration Release
  ```