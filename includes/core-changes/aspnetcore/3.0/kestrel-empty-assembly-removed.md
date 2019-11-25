---
ms.openlocfilehash: 1c9c899d77dd69e185281d98bfec18ce73d80815
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394221"
---
### <a name="kestrel-empty-https-assembly-removed"></a>Kestrel: Leere HTTPS-Assembly wurde entfernt.

Die Assembly <xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName> wurde entfernt.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="reason-for-change"></a>Grund für die Änderung

In ASP.NET Core 2.1 wurde der Inhalt von `Microsoft.AspNetCore.Server.Kestrel.Https` nach <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName> verschoben. Diese Änderung wurde ohne Breaking Change mithilfe von `[TypeForwardedTo]`-Attributen durchgeführt.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

- In Bibliotheken, die auf `Microsoft.AspNetCore.Server.Kestrel.Https` 2.0 verweisen, sollten alle ASP.NET Core-Abhängigkeiten auf 2.1 oder höher aktualisiert werden. Andernfalls können sie beim Laden in eine ASP.NET Core 3.0-App unterbrochen werden.
- In Apps und Bibliotheken, die auf ASP.NET Core 2.1 und höher abzielen, sollten alle direkten Verweise auf das NuGet-Paket `Microsoft.AspNetCore.Server.Kestrel.Https` entfernt werden.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
