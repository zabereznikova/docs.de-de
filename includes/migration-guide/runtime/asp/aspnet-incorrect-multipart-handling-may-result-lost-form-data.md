---
ms.openlocfilehash: d61a3b3dd855d783d7bff7cb74e5b84969e60860
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608046"
---
### <a name="aspnet-incorrect-multipart-handling-may-result-in-lost-form-data"></a>Falsche Behandlung von mehrteiligen Elementen in ASP.NET kann zu Datenverlusten bei Formularen führen.

#### <a name="details"></a>Details

In Anwendungen für .NET Framework 4.7.2 und früher werden mehrteilige Grenzwerte von ASP.NET möglicherweise falsch analysiert, was dazu führt, dass Formulardaten bei der Ausführung einer Anforderung nicht verfügbar sind. Anwendungen, die .NET Framework 4.8 oder höhere Versionen gezielt nutzen, analysieren mehrteilige Daten ordnungsgemäß, sodass Formularwerte bei der Ausführung von Anforderungen verfügbar sind.

#### <a name="suggestion"></a>Vorschlag

Ab Anwendungen, die unter .NET Framework 4.8 ausgeführt werden, ändert sich das Standardverhalten bei gezielter Nutzung von .NET Framework 4.8 oder höher durch Verwenden des <code>targetFrameworkVersion</code>-Elements, und Trennzeichen werden entfernt. Wenn frühere Framework-Versionen gezielt genutzt oder <code>targetFrameworkVersion</code> nicht verwendet wird, werden weiterhin für einige Werte nachstehende Trennzeichen zurückgegeben. Dieses Verhalten kann mit einer <code>appSetting</code> ebenfalls explizit festgelegt werden:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:UseLegacyMultiValueHeaderHandling&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   |Unbekannt|
|Version|4.8|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Web.HttpRequest.Form?displayProperty=nameWithType>
- <xref:System.Web.HttpRequest.Files?displayProperty=nameWithType>
- <xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.HttpRequest.Form`
- `P:System.Web.HttpRequest.Files`
- `P:System.Web.HttpRequest.ContentEncoding`

-->
