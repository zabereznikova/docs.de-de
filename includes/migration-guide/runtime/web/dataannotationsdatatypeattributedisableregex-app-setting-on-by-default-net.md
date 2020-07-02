---
ms.openlocfilehash: f17efc89b738a9fd20cc687de1dae01a44664271
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621234"
---
### <a name="dataannotationsdatatypeattributedisableregex-app-setting-is-on-by-default-in-net-framework-472"></a>Die App-Einstellung „dataAnnotations:dataTypeAttribute:disableRegEx“ ist in .NET Framework 4.7.2 standardmäßig aktiviert.

#### <a name="details"></a>Details

In .NET Framework 4.6.1 wurde die App-Einstellung <code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code> eingeführt, mir der Benutzer die Verwendung regulärer Ausdrücke in Datentypattributen (z.B. <xref:System.ComponentModel.DataAnnotations.EmailAddressAttribute?displayProperty=nameWithType>, <xref:System.ComponentModel.DataAnnotations.UrlAttribute?displayProperty=nameWithType> und <xref:System.ComponentModel.DataAnnotations.PhoneAttribute?displayProperty=nameWithType>) deaktivieren können. So können Sicherheitsrisiken wie mögliche Denial-of-Service-Angriffe mit bestimmten regulären Ausdrücken gesenkt werden.<br/>In .NET Framework 4.6.1 war diese App-Einstellung zur Verwendung von regulären Ausdrücken standardmäßig auf <code>false</code> festgelegt. Ab .NET Framework 4.7.2 ist dieser Konfigurationsparameter standardmäßig auf <code>true</code> festgelegt, um Sicherheitsrisiken für Webanwendungen für .NET Framework 4.7.2 und höher weiter zu senken.

#### <a name="suggestion"></a>Vorschlag

Wenn regulärer Ausdrücke in Ihrer Webanwendung nach dem Upgrade auf .NET Framework 4.7.2 nicht mehr funktionieren, können Sie den Wert der Einstellung <code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code> in <code>false</code> ändern, um wieder das alte Verhalten zu verwenden.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot; value=&quot;false&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.7.2|
|Typ|Laufzeit|
