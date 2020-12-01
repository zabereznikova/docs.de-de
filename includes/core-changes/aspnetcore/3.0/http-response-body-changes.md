---
ms.openlocfilehash: cd66317bc93343e03a73dec74dff534776ca42e4
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032543"
---
### <a name="http-response-body-infrastructure-changes"></a>HTTP: Änderungen an der Infrastruktur von Antworttexten

Die Infrastruktur für HTTP-Antworttexte wurde geändert. Wenn Sie `HttpResponse` direkt verwenden, sollten keine Änderungen am Code erforderlich sein. Wenn Sie `HttpResponse.Body` umschließen oder auf `HttpContext.Features` zugreifen, lesen Sie weiter.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Dem HTTP-Antworttext waren drei APIs zugeordnet:

- `IHttpResponseFeature.Body`
- `IHttpSendFileFeature.SendFileAsync`
- `IHttpBufferingFeature.DisableResponseBuffering`

#### <a name="new-behavior"></a>Neues Verhalten

Wenn Sie `HttpResponse.Body` ersetzen, wird das gesamte `IHttpResponseBodyFeature` durch einen Wrapper um den angegebenen Stream ersetzt, indem `StreamResponseBodyFeature` verwendet wird, um Standardimplementierungen für alle erwarteten APIs bereitzustellen. Durch das Zurücksetzen des ursprünglichen Streams wird diese Änderung zurückgesetzt.

#### <a name="reason-for-change"></a>Grund für die Änderung

Die Antworttext-APIs sollen in einer einzigen neuen Funktionsschnittstelle zusammengefasst werden.

#### <a name="recommended-action"></a>Empfohlene Aktion

Verwenden Sie `IHttpResponseBodyFeature` an den Stellen, an denen Sie zuvor `IHttpResponseFeature.Body`, `IHttpSendFileFeature` oder `IHttpBufferingFeature` verwendet haben.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature`
- `P:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body`
- `T:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature`

-->
