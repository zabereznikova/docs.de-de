---
title: Debuggen und Profilerstellung von Konfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die das Debuggen und die Profilerstellung für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 5efd0f776da4b7ce6ff7f3bdfda24feec6e00f79
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761992"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a>Laufzeitkonfigurationsoptionen für das Debuggen und die Profilerstellung

## <a name="enable-diagnostics"></a>Aktivieren der Diagnosefunktion

- Konfiguriert, ob der Debugger, der Profiler und die EventPipe-Diagnose aktiviert oder deaktiviert sind
- Wenn Sie diese Einstellung weglassen, wird die Diagnose aktiviert. Dies entspricht der Einstellung des Werts auf `1`.

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | Nicht zutreffend | Nicht zutreffend |
| **Umgebungsvariable** | `COMPlus_EnableDiagnostics` | `1` – aktiviert<br/>`0` – deaktiviert |

## <a name="enable-profiling"></a>Aktivieren der Profilerstellung

- Konfiguriert, ob die Profilerstellung für den aktuell laufenden Prozess aktiviert ist
- Wenn Sie diese Einstellung weglassen, ist die Profilerstellung deaktiviert. Dies entspricht der Einstellung des Werts auf `0`.

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | Nicht zutreffend | Nicht zutreffend |
| **Umgebungsvariable** | `CORECLR_ENABLE_PROFILING` | `0` – deaktiviert<br/>`1` – aktiviert |

## <a name="profiler-guid"></a>GUID des Profilers

- Gibt die GUID des Profilers an, der in den aktuell laufenden Prozess geladen werden soll

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | Nicht zutreffend | Nicht zutreffend |
| **Umgebungsvariable** | `CORECLR_PROFILER` | *string-guid* |

## <a name="profiler-location"></a>Speicherort des Profilers

- Gibt den Pfad zur Profiler-DLL an, die in den aktuell laufenden Prozess geladen werden soll (32-Bit- oder 64-Bit-Paket)
- Wenn mehr als eine Variable festgelegt ist, haben die für die Bitanzahl spezifischen Variablen Vorrang. Diese geben an, welche Bitanzahl von Profiler geladen werden soll.
- Weitere Informationen finden Sie unter [Suchen der Profilerbibliothek](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).

| | Einstellungsname | Werte |
| - | - | - |
| **Umgebungsvariable** | `CORECLR_PROFILER_PATH` | *string-path* |
| **Umgebungsvariable** | `CORECLR_PROFILER_PATH_32` | *string-path* |
| **Umgebungsvariable** | `CORECLR_PROFILER_PATH_64` | *string-path* |

## <a name="write-perf-map"></a>Schreiben von Leistungszuordnungen

- Aktiviert oder deaktiviert das Schreiben von */tmp/perf-$pid.map* auf Linux-Systemen.
- Wenn Sie diese Einstellung weglassen, ist das Schreiben von Leistungszuordnungen deaktiviert. Dies entspricht der Einstellung des Werts auf `0`.

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | Nicht zutreffend | Nicht zutreffend |
| **Umgebungsvariable** | `COMPlus_PerfMapEnabled` | `0` – deaktiviert<br/>`1` – aktiviert |

## <a name="perf-log-markers"></a>Leistungsprotokollmarker

- Aktiviert oder deaktiviert das angegebene Signal, um als Marker in den Leistungsprotokollen akzeptiert oder ignoriert zu werden.
- Wenn Sie diese Einstellung weglassen, wird das angegebene Signal nicht ignoriert. Dies entspricht der Einstellung des Werts auf `0`.

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | Nicht zutreffend | Nicht zutreffend |
| **Umgebungsvariable** | `COMPlus_PerfMapIgnoreSignal` | `0` – deaktiviert<br/>`1` – aktiviert |

> [!NOTE]
> Diese Einstellung wird ignoriert, wenn [COMPlus_PerfMapEnabled](#write-perf-map) ausgelassen oder auf `0` festgelegt wird (d. h. deaktiviert).
