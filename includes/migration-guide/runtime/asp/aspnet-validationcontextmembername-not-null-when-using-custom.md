---
ms.openlocfilehash: 7002c74594993ac6bf28643ef3271da356190c66
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621965"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a>ASP.NET ValidationContext.MemberName ist bei Verwendung des benutzerdefinierten DataAnnotations.ValidationAttribute nicht NULL

#### <a name="details"></a>Details

Wenn in .NET Framework 4.7.2 und früheren Versionen ein benutzerdefiniertes <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> verwendet wurde, wurde von der <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType>-Eigenschaft `null` zurückgegeben. In der .NET Framework 4.8-Version vor dem Update vom Oktober 2019 wird der Membername zurückgegeben. Ab der [Vorschauversion des Qualitätsrollups für .NET Framework vom Oktober 2019](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) für .NET Framework 4.8 wird standardmäßig `null` zurückgegeben, aber Sie können sich dafür entscheiden, stattdessen den Membernamen zurückzugeben.

#### <a name="suggestion"></a>Vorschlag

Fügen Sie die folgende Einstellung zu Ihrer Datei *web.config* hinzu, damit die Eigenschaft den Membernamen in der [Vorschauversion des Qualitätsrollups für .NET Framework vom Oktober 2019](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) für .NET Framework 4.8 und spätere Versionen zurückgibt:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>In der .NET Framework 4.8-Version vor dem Update vom Oktober 2019 stellt das Hinzufügen dieser Eigenschaft zu Ihrer Datei *web.config* das vorherige Verhalten wieder her, und die Eigenschaft gibt `null` zurück.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Unbekannt|
|Version|4.8|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|
