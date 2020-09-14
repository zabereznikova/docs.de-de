---
ms.openlocfilehash: 7140f6d4cac063088b3663ab98d292104218b542
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465511"
---
### <a name="cookie-path-handling-now-conforms-to-rfc-6265"></a>Verarbeitung von Cookiepfaden jetzt mit RFC 6265 konform

In [RFC 6265](https://tools.ietf.org/html/rfc6265) definierte Pfadverarbeitungsalgorithmen wurden für die Klassen <xref:System.Net.Cookie> und <xref:System.Net.CookieContainer> implementiert.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0

#### <a name="change-description"></a>Änderungsbeschreibung

- Die Eigenschaft <xref:System.Net.Cookie.Path> ist kein erforderliches Präfix für den Anforderungspfad mehr.
- Die Berechnung des Standardwerts von <xref:System.Net.Cookie.Path> und der Pfadabgleichalgorithmus wurden wie gemäß [Abschnitt 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) des RFC 6265 implementiert.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

In denen meisten Fällen müssen Sie keine Maßnahmen ergreifen. Wenn Ihr Code jedoch von der <xref:System.Net.Cookie.Path>-Validierung abhängig wäre, müssten Sie die erforderliche Validierung in Ihren Code implementieren. Wenn Ihr Code von der Standardwertberechnung für <xref:System.Net.Cookie.Path> abhängig wäre, sollten Sie den Wert <xref:System.Net.Cookie.Path> manuell eingeben, anstatt den Standardwert zu verwenden.

#### <a name="category"></a>Kategorie

Netzwerk

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Net.Cookie?displayProperty=fullName>
- <xref:System.Net.CookieContainer?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Cookie`
- `T:System.Net.CookieContainer`

-->
