---
title: dotnet store-befehl
description: Der „dotnet store“-Befehl speichert die angegebenen Assemblys im Laufzeitpaketspeicher.
ms.date: 02/14/2020
ms.openlocfilehash: da1d132b2b873ff55ec104b5bb092d0194889bdc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503578"
---
# <a name="dotnet-store"></a>dotnet store

**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen

## <a name="name"></a>Name

`dotnet store`: speichert die angegebenen Assemblys im [Laufzeitpaketspeicher](../deploying/runtime-store.md).

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]
```

## <a name="description"></a>Beschreibung

`dotnet store`: speichert die angegebenen Assemblys im [Laufzeitpaketspeicher](../deploying/runtime-store.md). Assemblys werden standardmäßig für die Ziellaufzeit und das Zielframework optimiert. Weitere Informationen finden Sie unter [Laufzeitpaketspeicher](../deploying/runtime-store.md).

## <a name="required-options"></a>Erforderliche Optionen

- **`-f|--framework <FRAMEWORK>`**

  Gibt das [Zielframework](../../standard/frameworks.md) an. Das Zielframework muss in der Projektdatei angegeben werden.

- **`-m|--manifest <PATH_TO_MANIFEST_FILE>`**

  Die *Manifestdatei des Paketspeichers* ist eine XML-Datei, die die Liste der zu speichernden Pakete enthält. Das Format der Manifestdatei ist mit dem SDK-Projektformat kompatibel. Also kann eine Projektdatei, die auf das gewünschte Paket verweist, mit der Option `-m|--manifest` verwendet werden, um Assemblys im Laufzeitpaketspeicher zu speichern. Wiederholen Sie die Option und den Pfad für jede Datei, um mehrere Manifestdateien anzugeben. Beispiel: `--manifest packages1.csproj --manifest packages2.csproj`.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Der als Ziel zu verwendende [Laufzeitbezeichner](../rid-catalog.md).

## <a name="optional-options"></a>Optionale Optionen

- **`--framework-version <FRAMEWORK_VERSION>`**

  Gibt die Version des .NET Core SDK an. Mit dieser Option können Sie eine bestimmte Frameworkversion auswählen, die nicht das von der `-f|--framework`-Option angegebene Framework ist.

- **`-h|--help`**

  Zeigt Hilfeinformationen

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Gibt den Pfad zum Laufzeitpaketspeicher an. Wenn nicht angegeben, wird das Unterverzeichnis *store* des .NET Core-Installationsverzeichnisses des Benutzerprofils als Standardeinstellung verwendet.

- **`--skip-optimization`**

  Überspringt die Optimierungsphase

- **`--skip-symbols`**

  Überspringt die Symbolgenerierung. Sie können aktuell nur unter Windows und Linux Symbole generieren.

- **`-v|--verbosity <LEVEL>`**

  Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

- **`-w|--working-dir <WORKING_DIRECTORY>`**

  Das Arbeitsverzeichnis, das vom Befehl verwendet wird. Wenn nicht angegeben, wird das Unterverzeichnis *obj* des aktuellen Verzeichnisses verwendet.

## <a name="examples"></a>Beispiele

- Speichern Sie die in der Projektdatei *packages.csproj* für .NET Core 2.0.0 angegebenen Pakete:

  ```dotnetcli
  dotnet store --manifest packages.csproj --framework-version 2.0.0
  ```

- Speichern Sie die in der Datei *packages.csproj* angegebenen Pakete ohne Optimierung:

  ```dotnetcli
  dotnet store --manifest packages.csproj --skip-optimization
  ```

## <a name="see-also"></a>Weitere Informationen

- [Laufzeitpaketspeicher](../deploying/runtime-store.md)
