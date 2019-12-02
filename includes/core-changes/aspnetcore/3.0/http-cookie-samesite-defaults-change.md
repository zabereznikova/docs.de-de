---
ms.openlocfilehash: 15ba678431b97e7c961c119d83546569bdf9bad2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74282522"
---
### <a name="http-some-cookie-samesite-defaults-changed-to-none"></a>HTTP: Einige Standardeinstellungen für Cookie-SameSite wurden in None geändert.

Bei `SameSite` handelt es sich um eine Option für Cookies, mit der einige CSRF-Angriffe (Cross-Site Request Forgery, websiteübergreifende Anforderungsfälschung) entschärft werden können. Als diese Option erstmals eingeführt wurde, wurden inkonsistente Standardwerte für verschiedene ASP.NET Core-APIs verwendet. Diese Inkonsistenz führte zu verwirrenden Ergebnissen. Ab ASP.NET Core 3.0 sind diese Standardeinstellungen besser abgestimmt. Sie müssen dieses Feature auf Komponentenbasis aktivieren.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Ähnliche ASP.NET Core-APIs verwendeten unterschiedliche <xref:Microsoft.AspNetCore.Http.SameSiteMode>-Standardwerte. Ein Beispiel für die Inkonsistenz sind `HttpResponse.Cookies.Append(String, String)` und `HttpResponse.Cookies.Append(String, String, CookieOptions)`, wofür die Standardwerte `SameSiteMode.None` bzw. `SameSiteMode.Lax` verwendet wurden.

#### <a name="new-behavior"></a>Neues Verhalten

Alle betroffenen APIs verwenden standardmäßig `SameSiteMode.None`.

#### <a name="reason-for-change"></a>Grund für die Änderung

Der Standardwert wurde geändert, um `SameSite` zu einem Feature zu machen, das aktiviert werden muss.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Für jede Komponente, die Cookies ausgibt, muss entschieden werden, ob `SameSite` für die zugehörigen Szenarios geeignet ist. Überprüfen Sie die Nutzung der betroffenen APIs, und konfigurieren Sie `SameSite` nach Bedarf neu.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)`
- `Overload:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy`

-->
