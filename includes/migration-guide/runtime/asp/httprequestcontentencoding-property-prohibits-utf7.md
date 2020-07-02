---
ms.openlocfilehash: 7d3568fef933758c40e47cefa86c24d31d4119fc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620130"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a>HttpRequest.ContentEncoding-Eigenschaft verhindert UTF7

#### <a name="details"></a>Details

Ab .NET Framework 4.5 ist die UTF-7-Codierung in <xref:System.Web.HttpRequest?displayProperty=fullName>-Texten nicht zulässig. Teilweise treten bei Daten für Anwendungen, die von eingehenden UTF-7-Daten abhängen, Decodierungsprobleme auf.

#### <a name="suggestion"></a>Vorschlag

Im Idealfall sollten Anwendungen aktualisiert verwenden, damit sie die UTF-7-Codierung in <xref:System.Web.HttpRequest?displayProperty=fullName> nicht verwenden. Alternativ kann das Legacyverhalten mithilfe des <code>aspnet:AllowUtf7RequestContentEncoding</code>-Attributs des [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md)-Elements wiederhergestellt werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
