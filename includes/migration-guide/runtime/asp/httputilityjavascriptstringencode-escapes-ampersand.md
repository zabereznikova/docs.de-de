---
ms.openlocfilehash: d587e542a72d584502ac3ac892619cc38b88ef77
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620142"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a>HttpUtility.JavaScriptStringEncode versieht kaufmännisches Und-Zeichen mit Escapezeichen

#### <a name="details"></a>Details

Ab .NET Framework 4.5 wird das kaufmännische Und-Zeichen (&) von <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> mit einem Escapezeichen (&amp;) versehen.

#### <a name="suggestion"></a>Vorschlag

Wenn Ihre App vom vorherigen Verhalten dieser Methode abhängig ist, können Sie dem [appSettings-Element von ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) eine „aspnet:JavaScriptDoNotEncodeAmpersand“-Einstellung in der Konfigurationsdatei hinzufügen.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
