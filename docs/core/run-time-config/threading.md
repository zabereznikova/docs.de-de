---
title: Konfigurationseinstellungen für das Threading
description: Erfahren Sie mehr über Laufzeiteinstellungen, die das Threading für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 6a920dbc301830e3f4c95bf637ff3de6d4f464ff
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998828"
---
# <a name="run-time-configuration-options-for-threading"></a>Laufzeitkonfigurationsoptionen für das Threading

## <a name="cpu-groups"></a>CPU-Gruppen

- Hiermit wird konfiguriert, ob Threads automatisch über CPU-Gruppen verteilt werden.
- Standard: Deaktiviert (`0`)

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | Nicht zutreffend | Nicht zutreffend |
| **Umgebungsvariable** | `COMPlus_Thread_UseAllCpuGroups` | `0` – deaktiviert<br/>`1` – aktiviert |

## <a name="minimum-threads"></a>Mindestanzahl an Threads

- Gibt die Mindestanzahl an Threads für den Arbeitsthreadpool an
- Entspricht der <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>-Methode

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `System.Threading.ThreadPool.MinThreads` | Eine ganze Zahl, die die Mindestanzahl an Threads angibt |
| **Umgebungsvariable** | Nicht zutreffend | Nicht zutreffend |

## <a name="maximum-threads"></a>Maximale Anzahl an Threads

- Gibt die maximale Anzahl an Threads für den Arbeitsthreadpool an
- Entspricht der <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>-Methode

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `System.Threading.ThreadPool.MaxThreads` | Eine ganze Zahl, die die maximale Anzahl der Threads darstellt |
| **Umgebungsvariable** | Nicht zutreffend | Nicht zutreffend |
