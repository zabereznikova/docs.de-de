---
ms.openlocfilehash: 26facb645de175d7ef0432394fc2b84f59e8437d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497243"
---
### <a name="error-codes-for-maxrequestlength-or-maxreceivedmessagesize-are-different"></a>Die Fehlercodes für maxRequestLength oder maxReceivedMessageSize sind unterschiedlich

#### <a name="details"></a>Details

Meldung in WCF-Webdiensten, die in Internetinformationsdiensten (Internet Information Services, IIS) oder in ASP.NET Development Server gehostet werden und maxRequestLength (in ASP.NET) oder maxReceivedMessageSize (in WCF) überschreiten, haben verschiedene Fehlercodes. Der HTTP-Statuscode hat sich von 400 (Ungültige Anforderung) in 413 (Anforderungseinheit zu groß) geändert, und entweder die maxRequestLength- oder die maxReceivedMessageSize-Einstellung löst eine <xref:System.ServiceModel.ProtocolException?displayProperty=fullName>-Ausnahme aus. Dies gilt auch für Fälle, in denen der Übergangsmodus „Streamed“ ist.

#### <a name="suggestion"></a>Vorschlag

Diese Änderung erleichtert das Debuggen in Fällen, in denen die Länge der Meldung die von ASP.NET oder WCF zulässigen Limits überschreiten. Sie müssen sämtlichen Code ändern, der Verarbeitungen auf Grundlage des HTTP-Statuscodes „400“ durchführt.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
