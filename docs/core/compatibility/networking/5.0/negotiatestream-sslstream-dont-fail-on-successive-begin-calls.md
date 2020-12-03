---
title: 'Breaking Change: NegotiateStream und SslStream lassen aufeinanderfolgende Begin-Vorgänge zu'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den Fehler auf Sicherheitsstreams anders gehandhabt werden und aufeinander folgende Aufrufe von BeginAuthenticateAsServer oder BeginAuthenticateAsClient nicht mehr fehlschlagen.
ms.date: 10/18/2020
ms.openlocfilehash: e0226d0f5586efca050ca3497ca1490fa21fd943
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759385"
---
# <a name="negotiatestream-and-sslstream-allow-successive-begin-operations"></a>NegotiateStream und SslStream lassen aufeinanderfolgende Begin-Vorgänge zu

Fehler in Sicherheitsstreams werden anders gehandhabt, und aufeinanderfolgende Aufrufe von `BeginAuthenticateAsServer` oder `BeginAuthenticateAsClient` sollten nicht mehr fehlschlagen.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="change-description"></a>Änderungsbeschreibung

In früheren .NET-Versionen führten aufeinanderfolgende Aufrufe von `BeginAuthenticateAsServer` oder `BeginAuthenticateAsClient` ohne vorheriges Aufrufen von `EndAuthenticateAsServer` oder `EndAuthenticateAsClient` zu einer <xref:System.NotSupportedException>. Ab .NET 5.0 führen aufeinanderfolgende Aufrufe von `BeginAuthenticateAsServer` oder `BeginAuthenticateAsClient` nicht mehr zu einer <xref:System.NotSupportedException>, da diese APIs von einer <xref:System.Threading.Tasks.Task>-basierten Implementierung unterstützt werden.

## <a name="reason-for-change"></a>Grund für die Änderung

Wenn Sie bei der internen Implementierung vom asynchronen Programmiermodell zur <xref:System.Threading.Tasks.Task>-basierten Implementierung wechseln, wird die Leistung verbessert, und der Code ist weniger komplex.

## <a name="recommended-action"></a>Empfohlene Maßnahme

Auf der Seite des Entwicklers ist keine Aktion erforderlich.

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Net.Security.SslStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.SslStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsClient`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient`

### Category

Networking

-->
