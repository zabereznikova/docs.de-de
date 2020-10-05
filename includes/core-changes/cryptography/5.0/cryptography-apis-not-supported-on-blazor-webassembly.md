---
ms.openlocfilehash: 6c2aff4abf558307d599ff7533c82286e037bc71
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406146"
---
### <a name="systemsecuritycryptography-apis-not-supported-on-blazor-webassembly"></a>System.Security.Cryptography-APIs werden in Blazor WebAssembly nicht unterstützt

<xref:System.Security.Cryptography>-APIs lösen zur Laufzeit eine <xref:System.PlatformNotSupportedException> aus, wenn sie in einem Browser ausgeführt werden.

#### <a name="change-description"></a>Änderungsbeschreibung

In früheren Versionen von .NET waren die meisten <xref:System.Security.Cryptography>-APIs für Blazor WebAssembly-Apps nicht verfügbar. Ab .NET 5.0 sind Blazor WebAssembly-Apps zwar auf die gesamte API-Oberfläche für .NET 5 ausgerichtet, aber aufgrund von Browsereinschränkungen der Sandbox werden nicht alle .NET 5-APIs unterstützt. In .NET 5.0 und höheren Versionen lösen die nicht unterstützten <xref:System.Security.Cryptography>-APIs eine <xref:System.PlatformNotSupportedException> aus, wenn sie in WebAssembly ausgeführt werden.

> [!TIP]
> Wenn Sie ein Projekt erstellen, das die Browserplattform unterstützt, kennzeichnet das [Analysetool für die Plattformkompatibilität](../../../../docs/core/compatibility/code-analysis.md#ca1416-platform-compatibility) sämtliche Aufrufe der betroffenen APIs. Dieses Analysetool wird standardmäßig in Apps für .NET 5.0 und höher ausgeführt.

#### <a name="reason-for-change"></a>Grund für die Änderung

Microsoft kann OpenSSL nicht als Abhängigkeit mit der Blazor WebAssembly-Konfiguration integrieren. Wir haben versucht, dieses Problem zu umgehen, indem wir eine Integration in die API `SubtleCrypto` des Browsers vorgenommen haben. Leider waren dafür aber einschlägige API-Änderungen erforderlich, die die Integration zu kompliziert machten.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 RC1

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Zurzeit gibt es keine gute Möglichkeit, dieses Problem zu umgehen.

#### <a name="category"></a>Kategorie

- ASP.NET Core
- Kryptografie

#### <a name="affected-apis"></a>Betroffene APIs

Alle <xref:System.Security.Cryptography?displayProperty=fullName>-APIs außer:

- `System.Security.Cryptography.RandomNumberGenerator`
- `System.Security.Cryptography.IncrementalHash`
- `System.Security.Cryptography.SHA1`
- `System.Security.Cryptography.SHA256`
- `System.Security.Cryptography.SHA384`
- `System.Security.Cryptography.SHA512`
- `System.Security.Cryptography.SHA1Managed`
- `System.Security.Cryptography.SHA256Managed`
- `System.Security.Cryptography.SHA384Managed`
- `System.Security.Cryptography.SHA512Managed`

<!--

#### Affected APIs

- `T:System.Security.Cryptography`

-->
