---
ms.openlocfilehash: 135d59de135c8416d384b221379f912c8a9172ad
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621970"
---
### <a name="aspnet-incorrect-multipart-handling-may-result-in-lost-form-data"></a>Falsche Behandlung von mehrteiligen Elementen in ASP.NET kann zu Datenverlusten bei Formularen führen.

#### <a name="details"></a>Details

In Anwendungen, die .NET Framework 4.7.2 und frühere Versionen gezielt nutzen, werden mehrteilige Grenzwerte von ASP.Net möglicherweise falsch analysiert, was dazu führt, dass Formulardaten bei der Ausführung einer Anforderung nicht verfügbar sind. Anwendungen, die .NET Framework 4.8 oder höhere Versionen gezielt nutzen, analysieren mehrteilige Daten ordnungsgemäß, sodass Formularwerte bei der Ausführung von Anforderungen verfügbar sind.

#### <a name="suggestion"></a>Vorschlag

Ab Anwendungen, die unter .NET Framework 4.8 ausgeführt werden, ändert sich das Standardverhalten bei gezielter Nutzung von .NET Framework 4.8 oder höher durch Verwenden des <code>targetFrameworkVersion</code>-Elements, und Trennzeichen werden entfernt. Wenn frühere Framework-Versionen gezielt genutzt oder <code>targetFrameworkVersion</code> nicht verwendet wird, werden weiterhin für einige Werte nachstehende Trennzeichen zurückgegeben. Dieses Verhalten kann mit einer <code>appSetting</code> ebenfalls explizit festgelegt werden:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:UseLegacyMultiValueHeaderHandling&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   |Unbekannt|
|Version|4.8|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Web.HttpRequest.Form?displayProperty=nameWithType></li><li><xref:System.Web.HttpRequest.Files?displayProperty=nameWithType></li><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
