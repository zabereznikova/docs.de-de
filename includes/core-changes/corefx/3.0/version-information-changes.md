---
ms.openlocfilehash: 2a751acc129ebd1c917b87f8083ffef72c7d8c17
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568176"
---
### <a name="apis-that-report-version-now-report-product-and-not-file-version"></a>APIs, die Versionsinformationen melden, melden nun die Produktversion und nicht die Dateiversion

Viele APIs, die in .NET Core Versionsinformationen zurückgeben, geben nun anstelle der Dateiversion die Produktversion zurück.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Core 2.2 und früheren Versionen, wird in Methoden wie <xref:System.Environment.Version?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> und im Dialogfeld mit den Dateieigenschaften für .NET Core-Assemblys die Dateiversion angegeben. Ab .NET Core 3.0 wird die Produktversion angegeben.

In der folgenden Abbildung sind die unterschiedlichen Versionsinformationen für die *System.Runtime.dll*-Assembly für .NET Core 2.2 (links) und .NET Core 3.0 (rechts) zu sehen, die im Dialogfeld mit Dateieigenschaften im **Windows-Explorer** angezeigt werden.

![Unterschiedliche Produktversionsinformationen](~/docs/images/core-changes/corefx/version-information-changes/file-details.png)

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Keine Durch diese Änderung soll die Version einfacher und intuitiver zu erkennen sein.

#### <a name="category"></a>Kategorie

CoreFx

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Environment.Version?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>

<!--

### Affected APIs

- `P:System.Environment.Version`
- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
