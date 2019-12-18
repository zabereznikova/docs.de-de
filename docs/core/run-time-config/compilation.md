---
title: Kompilierungskonfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die die Funktionsweise des JIT-Compilers für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: bcc445b6edc48d9432ee614b0b19c9c25621f4a0
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998876"
---
# <a name="run-time-configuration-options-for-compilation"></a>Laufzeitkonfigurationsoptionen für die Kompilierung

## <a name="tiered-compilation"></a>Mehrstufig Kompilierung

- Konfiguriert, ob der JIT-Compiler [mehrstufige Kompilierung](../whats-new/dotnet-core-3-0.md#tiered-compilation) verwendet.
- In .NET Core 3.0 und höher ist die mehrstufige Kompilierung standardmäßig aktiviert.
- In .NET Core 2.1 und 2.2 ist die mehrstufige Kompilierung standardmäßig deaktiviert.

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `System.Runtime.TieredCompilation` | `true` – aktiviert<br/>`false` – deaktiviert |
| **Umgebungsvariable** | `COMPlus_TieredCompilation` | `1` – aktiviert<br/>`0` – deaktiviert |
