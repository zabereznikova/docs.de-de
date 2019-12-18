---
title: Debuggen und Profilerstellung von Konfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die das Debuggen und die Profilerstellung für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: c57cfa7233f48def890ded3c9d589b7f268147df
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998858"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a>Laufzeitkonfigurationsoptionen für das Debuggen und die Profilerstellung

## <a name="enable-diagnostics"></a>Aktivieren der Diagnosefunktion

- Konfiguriert, ob der Debugger, der Profiler und die EventPipe-Diagnose aktiviert oder deaktiviert sind
- Standard: Aktiviert (`1`)

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | Nicht zutreffend | Nicht zutreffend |
| **Umgebungsvariable** | `COMPlus_EnableDiagnostics` | `1` – aktiviert<br/>`0` – deaktiviert |

## <a name="enable-profiling"></a>Aktivieren der Profilerstellung

- Konfiguriert, ob die Profilerstellung für den aktuell laufenden Prozess aktiviert ist
- Standard: Deaktiviert (`0`)

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
- Standard: Deaktiviert (`0`)

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | Nicht zutreffend | Nicht zutreffend |
| **Umgebungsvariable** | `COMPlus_PerfMapEnabled` | `0` – deaktiviert<br/>`1` – aktiviert |

## <a name="perf-log-markers"></a>Leistungsprotokollmarker

- Aktiviert oder deaktiviert das angegebene Signal, um als Marker in den Leistungsprotokollen akzeptiert oder ignoriert zu werden, wenn `COMPlus_PerfMapEnabled` auf `1` festgelegt ist
- Standard: Deaktiviert (`0`)

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | Nicht zutreffend | Nicht zutreffend |
| **Umgebungsvariable** | `COMPlus_PerfMapIgnoreSignal` | `0` – deaktiviert<br/>`1` – aktiviert |
