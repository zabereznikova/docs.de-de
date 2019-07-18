---
ms.openlocfilehash: 0056baa1e5f0cdc5bfcf8b0e83c9490ec5722926
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235709"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a>HttpUtility.JavaScriptStringEncode versieht kaufmännisches Und-Zeichen mit Escapezeichen

|   |   |
|---|---|
|Details|Ab .NET Framework 4.5 wird das kaufmännische Und-Zeichen (&) von <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=name> mit einem Escapezeichen (&amp;) versehen.|
|Vorschlag|Wenn Ihre App vom vorherigen Verhalten dieser Methode abhängig ist, können Sie dem [appSettings-Element von ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) eine „aspnet:JavaScriptDoNotEncodeAmpersand“-Einstellung in der Konfigurationsdatei hinzufügen.|
|Bereich|Gering|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
