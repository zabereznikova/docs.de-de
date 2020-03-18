---
ms.openlocfilehash: 5612ebce67946e22aaeeba861115ce4f8967e1f5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75344453"
---
### <a name="apis-that-report-version-now-report-product-and-not-file-version"></a>APIs, die Versionsinformationen melden, melden nun die Produktversion und nicht die Dateiversion

Viele APIs, die in .NET Core Versionsinformationen zurückgeben, geben nun anstelle der Dateiversion die Produktversion zurück.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Core 2.2 und früheren Versionen, wird in Methoden wie <xref:System.Environment.Version?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> und im Dialogfeld mit den Dateieigenschaften für .NET Core-Assemblys die Dateiversion angegeben. Ab .NET Core 3.0 wird die Produktversion angegeben.

In der folgenden Abbildung sind die unterschiedlichen Versionsinformationen für die *System.Runtime.dll*-Assembly für .NET Core 2.2 (links) und .NET Core 3.0 (rechts) zu sehen, die im Dialogfeld mit Dateieigenschaften im **Windows-Explorer** angezeigt werden.

![Unterschiedliche Produktversionsinformationen](~/docs/images/core-changes/corefx/version-information-changes/file-details.png)

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Aktion

Keine. Durch diese Änderung soll die Version einfacher und intuitiver zu erkennen sein.

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
