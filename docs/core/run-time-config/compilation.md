---
title: Kompilierungskonfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die die Funktionsweise des JIT-Compilers für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: adf1f01dba7387b89ee56784e33653d6a132c0e3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77092888"
---
# <a name="run-time-configuration-options-for-compilation"></a>Laufzeitkonfigurationsoptionen für die Kompilierung

## <a name="tiered-compilation"></a>Mehrstufig Kompilierung

- Hiermit wird konfiguriert, ob der Just-in-Time-Compiler (JIT) eine [mehrstufige Kompilierung](../whats-new/dotnet-core-3-0.md#tiered-compilation) verwendet. Die mehrstufige Kompilierung übergibt Methoden über zwei Ebenen:
  - Die erste Stufe erzeugt schneller Code ([Quick JIT](#quick-jit)) oder lädt vorkompilierten Code ([ReadyToRun](#readytorun)).
  - Die zweite Stufe erstellt optimierten Code im Hintergrund („Optimieren von JIT“).
- In .NET Core 3.0 und höher ist die mehrstufige Kompilierung standardmäßig aktiviert.
- In .NET Core 2.1 und 2.2 ist die mehrstufige Kompilierung standardmäßig deaktiviert.
- Weitere Informationen finden Sie im [Leitfaden zur mehrstufigen Kompilierung](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation-guide.md).

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `System.Runtime.TieredCompilation` | `true` – aktiviert<br/>`false` – deaktiviert |
| **MSBuild-Eigenschaft** | `TieredCompilation` | `true` – aktiviert<br/>`false` – deaktiviert |
| **Umgebungsvariable** | `COMPlus_TieredCompilation` | `1` – aktiviert<br/>`0` – deaktiviert |

### <a name="examples"></a>Beispiele

*runtimeconfig.json*-Datei:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation": false
      }
   }
}
```

Projektdatei:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilation>false</TieredCompilation>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit"></a>Quick JIT

- Hiermit wird konfiguriert, ob der JIT-Compiler *Quick JIT* verwendet. Bei Methoden, die keine Schleifen enthalten und für die kein vorkompilierter Code verfügbar ist, kompiliert Quick JIT diese schneller, aber ohne Optimierungen.
- Die Aktivierung von Quick JIT verringert die Startzeit, kann aber Code mit verminderten Leistungsmerkmalen erzeugen. Zum Beispiel verwendet der Code möglicherweise mehr Stapelspeicher, kann mehr Speicher belegen und langsamer ausgeführt werden.
- Wenn Quick JIT deaktiviert, aber die [mehrstufige Kompilierung](#tiered-compilation) aktiviert ist, wird nur vorkompilierter Code bei der mehrstufigen Kompilierung verwendet. Wenn eine Methode nicht mit [ReadyToRun](#readytorun) vorkompiliert ist, ist das JIT-Verhalten dasselbe, als wenn die [mehrstufige Kompilierung](#tiered-compilation) deaktiviert wäre.
- In .NET Core 3.0 und höher ist Quick JIT standardmäßig aktiviert.
- In .NET Core 2.1 und 2.2 ist Quick JIT standardmäßig deaktiviert.

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `System.Runtime.TieredCompilation.QuickJit` | `true` – aktiviert<br/>`false` – deaktiviert |
| **MSBuild-Eigenschaft** | `TieredCompilationQuickJit` | `true` – aktiviert<br/>`false` – deaktiviert |
| **Umgebungsvariable** | `COMPlus_TC_QuickJit` | `1` – aktiviert<br/>`0` – deaktiviert |

### <a name="examples"></a>Beispiele

*runtimeconfig.json*-Datei:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJit": false
      }
   }
}
```

Projektdatei:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit-for-loops"></a>Quick JIT für Schleifen

- Hiermit wird konfiguriert, ob der JIT-Compiler Quick JIT bei Methoden verwendet, die Schleifen enthalten.
- Die Aktivierung von Quick JIT für Schleifen kann die Startleistung verbessern. Lange Schleifen können jedoch für lange Zeiträume in weniger optimiertem Code hängen bleiben.
- Wenn [Quick JIT](#quick-jit) deaktiviert ist, hat diese Einstellung keine Auswirkung.
- Standard: Deaktiviert (`false`)

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `System.Runtime.TieredCompilation.QuickJitForLoops` | `false` – deaktiviert<br/>`true` – aktiviert |
| **MSBuild-Eigenschaft** | `TieredCompilationQuickJitForLoops` | `false` – deaktiviert<br/>`true` – aktiviert |
| **Umgebungsvariable** | `COMPlus_TC_QuickJitForLoops` | `0` – deaktiviert<br/>`1` – aktiviert |

### <a name="examples"></a>Beispiele

*runtimeconfig.json*-Datei:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJitForLoops": false
      }
   }
}
```

Projektdatei:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJitForLoops>false</TieredCompilationQuickJitForLoops>
  </PropertyGroup>

</Project>
```

## <a name="readytorun"></a>ReadyToRun

- Das ReadyToRun-Image konfiguriert, ob die .NET Core-Runtime vorkompilierten Code für Images mit verfügbaren ReadyToRun-Daten verwendet. Wenn Sie diese Option deaktivieren, erzwingt die Runtime eine JIT-Kompilierung für Frameworkcode.
- Weitere Informationen finden Sie unter [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).
- Standard: Aktiviert (`1`)

| | Einstellungsname | Werte |
| - | - | - |
| **Umgebungsvariable** | `COMPlus_ReadyToRun` | `1` – aktiviert<br/>`0` – deaktiviert |
