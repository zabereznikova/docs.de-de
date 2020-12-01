---
ms.openlocfilehash: b0e1d6d720a1c9b827fb4585606e64b545d395d7
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032593"
---
### <a name="kestrel-request-trailer-headers-moved-to-new-collection"></a>Kestrel: Anforderungstrailer-Header wurden in neue Sammlung verschoben.

In früheren Versionen fügte Kestrel aufgeteilte HTTP/1.1-Trailer-Header in die Sammlung der Anforderungsheader ein, wenn der Anforderungstext bis zum Ende gelesen wurde. Durch dieses Verhalten war keine eindeutige Trennung zwischen Headern und Trailern möglich. Es wurde entschieden, die Trailer in eine neue Sammlung zu verschieben.

HTTP/2-Anforderungstrailer waren in ASP.NET Core 2.2 nicht verfügbar. Sie sind jetzt aber in dieser neuen Sammlung in ASP.NET Core 3.0 enthalten.

Für den Zugriff auf diese Trailer wurden neue Anforderungserweiterungsmethoden hinzugefügt.

HTTP/1.1-Trailer sind verfügbar, sobald der gesamte Anforderungstext gelesen wurde.

HTTP/2-Trailer sind verfügbar, sobald sie vom Client empfangen wurden. Der Client sendet die Trailer erst, wenn der gesamte Anforderungstext mindestens vom Server gepuffert wurde. Sie müssen möglicherweise den Anforderungstext lesen, um Pufferspeicher freizugeben. Trailer sind immer verfügbar, wenn Sie den Anforderungstext bis zum Ende lesen. Die Trailer markieren das Ende des Texts.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Anforderungstrailer-Header wurden der Sammlung `HttpRequest.Headers` hinzugefügt.

#### <a name="new-behavior"></a>Neues Verhalten

Anforderungstrailer-Header sind **nicht** in der Sammlung `HttpRequest.Headers` enthalten. Verwenden Sie die folgenden Erweiterungsmethoden in `HttpRequest`, um darauf zuzugreifen:

- `GetDeclaredTrailers()` ruft den Anforderungsheader „Trailer“ ab, in dem aufgelistet wird, welche Trailer nach dem Text erwartet werden.
- `SupportsTrailers()` gibt an, ob die Anforderung das Empfangen von Trailer-Headern unterstützt.
- `CheckTrailersAvailable()` legt fest, ob die Anforderung Trailer unterstützt und ob diese zum Lesen verfügbar sind.
- `GetTrailer(string trailerName)` ruft den angeforderten Trailer-Header aus der Antwort ab.

#### <a name="reason-for-change"></a>Grund für die Änderung

Trailer stellen ein wichtiges Feature in Szenarien wie gRPC dar. Das Zusammenführen der Trailer mit den Anforderungsheadern war für Benutzer verwirrend.

#### <a name="recommended-action"></a>Empfohlene Aktion

Verwenden Sie die trailerbezogenen Erweiterungsmethoden in `HttpRequest`, um auf Trailer zuzugreifen.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.Http.HttpRequest.Headers?displayProperty=nameWithType>

<!--

#### Affected APIs

`P:Microsoft.AspNetCore.Http.HttpRequest.Headers`

-->
