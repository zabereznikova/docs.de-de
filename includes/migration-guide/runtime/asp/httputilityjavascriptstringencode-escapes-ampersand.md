---
ms.openlocfilehash: b648aee35ff44730f545f0fa06f4e0a86615dece
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606686"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a>HttpUtility.JavaScriptStringEncode versieht kaufmännisches Und-Zeichen mit Escapezeichen

#### <a name="details"></a>Details

Ab .NET Framework 4.5 wird das kaufmännische Und-Zeichen (&) von <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> mit einem Escapezeichen (&amp;) versehen.

#### <a name="suggestion"></a>Vorschlag

Wenn Ihre App vom vorherigen Verhalten dieser Methode abhängig ist, können Sie dem [appSettings-Element von ASP.NET](/previous-versions/aspnet/hh975440(v=vs.120)) eine „aspnet:JavaScriptDoNotEncodeAmpersand“-Einstellung in der Konfigurationsdatei hinzufügen.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String)`
- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)`

-->
