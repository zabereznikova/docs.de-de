---
title: Konfigurationseinstellungen für das Threading
description: Erfahren Sie mehr über Laufzeiteinstellungen, die das Threading für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 1c7c16993a07ef95223481791153b75ab2f61533
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761927"
---
# <a name="run-time-configuration-options-for-threading"></a>Laufzeitkonfigurationsoptionen für das Threading

## <a name="cpu-groups"></a>CPU-Gruppen

- Hiermit wird konfiguriert, ob Threads automatisch über CPU-Gruppen verteilt werden.
- Wenn Sie diese Einstellung weglassen, werden Threads nicht über CPU-Gruppen verteilt. Dies entspricht der Einstellung des Werts auf `0`.

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | Nicht zutreffend | Nicht zutreffend |
| **Umgebungsvariable** | `COMPlus_Thread_UseAllCpuGroups` | `0` – deaktiviert<br/>`1` – aktiviert |

## <a name="minimum-threads"></a>Mindestanzahl an Threads

- Gibt die Mindestanzahl an Threads für den Arbeitsthreadpool an.
- Entspricht der <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>-Methode

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `System.Threading.ThreadPool.MinThreads` | Eine ganze Zahl, die die Mindestanzahl an Threads angibt |
| **MSBuild-Eigenschaft** | `ThreadPoolMinThreads` | Eine ganze Zahl, die die Mindestanzahl an Threads angibt |
| **Umgebungsvariable** | Nicht zutreffend | Nicht zutreffend |

### <a name="examples"></a>Beispiele

*runtimeconfig.json*-Datei:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

Projektdatei:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a>Maximale Anzahl an Threads

- Gibt die maximale Anzahl an Threads für den Arbeitsthreadpool an.
- Entspricht der <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>-Methode

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `System.Threading.ThreadPool.MaxThreads` | Eine ganze Zahl, die die maximale Anzahl der Threads darstellt |
| **MSBuild-Eigenschaft** | `ThreadPoolMaxThreads` | Eine ganze Zahl, die die maximale Anzahl der Threads darstellt |
| **Umgebungsvariable** | Nicht zutreffend | Nicht zutreffend |

### <a name="examples"></a>Beispiele

*runtimeconfig.json*-Datei:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

Projektdatei:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
