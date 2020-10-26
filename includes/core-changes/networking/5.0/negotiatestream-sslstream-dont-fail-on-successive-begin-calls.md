---
ms.openlocfilehash: 16994e9cd97b31a30c8c5ce49d2042ff79b3f60b
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050517"
---
### <a name="negotiatestream-and-sslstream-allow-successive-begin-operations"></a>NegotiateStream und SslStream lassen aufeinanderfolgende Begin-Vorgänge zu

Fehler in Sicherheitsstreams werden anders gehandhabt, und aufeinanderfolgende Aufrufe von `BeginAuthenticateAsServer` oder `BeginAuthenticateAsClient` sollten nicht mehr fehlschlagen.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 RC1

#### <a name="change-description"></a>Änderungsbeschreibung

In früheren .NET-Versionen führten aufeinanderfolgende Aufrufe von `BeginAuthenticateAsServer` oder `BeginAuthenticateAsClient` ohne vorheriges Aufrufen von `EndAuthenticateAsServer` oder `EndAuthenticateAsClient` zu einer <xref:System.NotSupportedException>. Ab .NET 5.0 führen aufeinanderfolgende Aufrufe von `BeginAuthenticateAsServer` oder `BeginAuthenticateAsClient` nicht mehr zu einer <xref:System.NotSupportedException>, da diese APIs von einer <xref:System.Threading.Tasks.Task>-basierten Implementierung unterstützt werden.

#### <a name="reason-for-change"></a>Grund für die Änderung

Wenn Sie bei der internen Implementierung vom asynchronen Programmiermodell zur <xref:System.Threading.Tasks.Task>-basierten Implementierung wechseln, wird die Leistung verbessert, und der Code ist weniger komplex.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Auf der Seite des Entwicklers ist keine Aktion erforderlich.

#### <a name="category"></a>Kategorie

Netzwerk

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Net.Security.SslStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.SslStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsClient`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient`

-->
