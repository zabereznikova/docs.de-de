---
title: dotnet store-befehl
description: Der „dotnet store“-Befehl speichert die angegebenen Assemblys im Laufzeitpaketspeicher.
author: bleroy
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: a12738d0cc8edcbb65d5b6fab6e7c8b209b0f4b5
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48029894"
---
# <a name="dotnet-store"></a>dotnet store

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a>name

`dotnet store`: speichert die angegebenen Assemblys im [Laufzeitpaketspeicher](../deploying/runtime-store.md).

## <a name="synopsis"></a>Übersicht

`dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]`

## <a name="description"></a>Beschreibung 

`dotnet store`: speichert die angegebenen Assemblys im [Laufzeitpaketspeicher](../deploying/runtime-store.md). Assemblys werden standardmäßig für die Ziellaufzeit und das Zielframework optimiert. Weitere Informationen finden Sie unter [Laufzeitpaketspeicher](../deploying/runtime-store.md).

## <a name="required-options"></a>Erforderliche Optionen

`-f|--framework <FRAMEWORK>`

Gibt das [Zielframework](../../standard/frameworks.md) an.

`-m|--manifest <PATH_TO_MANIFEST_FILE>`

Die *Manifestdatei des Paketspeichers* ist eine XML-Datei, die die Liste der zu speichernden Pakete enthält. Das Format der Manifestdatei ist mit dem SDK-Projektformat kompatibel. Also kann eine Projektdatei, die auf das gewünschte Paket verweist, mit der Option `-m|--manifest` verwendet werden, um Assemblys im Laufzeitpaketspeicher zu speichern. Wiederholen Sie die Option und den Pfad für jede Datei, um mehrere Manifestdateien anzugeben. Beispiel: `--manifest packages1.csproj --manifest packages2.csproj`.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Der als Ziel zu verwendende [Laufzeitbezeichner](../rid-catalog.md).

## <a name="optional-options"></a>Optionale Optionen

`--framework-version <FRAMEWORK_VERSION>`

Gibt die Version des .NET Core SDK an. Mit dieser Option können Sie eine bestimmte Frameworkversion auswählen, die nicht das von der `-f|--framework`-Option angegebene Framework ist.

`-h|--help`

Zeigt Hilfeinformationen

`-o|--output <OUTPUT_DIRECTORY>`

Gibt den Pfad zum Laufzeitpaketspeicher an. Wenn nicht angegeben, wird das Unterverzeichnis *store* des .NET Core-Installationsverzeichnisses des Benutzerprofils als Standardeinstellung verwendet.

`--skip-optimization`

Überspringt die Optimierungsphase

`--skip-symbols`

Überspringt die Symbolgenerierung. Sie können aktuell nur unter Windows und Linux Symbole generieren.

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

`-w|--working-dir <INTERMEDIATE_WORKING_DIRECTORY>`

Das Arbeitsverzeichnis, das vom Befehl verwendet wird. Wenn nicht angegeben, wird das Unterverzeichnis *obj* des aktuellen Verzeichnisses verwendet.

## <a name="examples"></a>Beispiele

Speichern Sie die in der Projektdatei *packages.csproj* für .NET Core 2.0.0 angegebenen Pakete:

`dotnet store --manifest packages.csproj --framework-version 2.0.0`

Speichern Sie die in der Datei *packages.csproj* angegebenen Pakete ohne Optimierung:

`dotnet store --manifest packages.csproj --skip-optimization`

## <a name="see-also"></a>Siehe auch

* [Laufzeitpaketspeicher](../deploying/runtime-store.md)