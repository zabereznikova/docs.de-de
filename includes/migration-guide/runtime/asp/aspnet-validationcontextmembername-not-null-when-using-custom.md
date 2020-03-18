---
ms.openlocfilehash: c0be08023f80bf0f96cc08f34b9ea8c5a73839e3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "77466026"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a>ASP.NET ValidationContext.MemberName ist bei Verwendung des benutzerdefinierten DataAnnotations.ValidationAttribute nicht NULL

|   |   |
|---|---|
|Details|Wenn in .NET Framework 4.7.2 und früheren Versionen ein benutzerdefiniertes <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> verwendet wurde, wurde von der <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType>-Eigenschaft `null` zurückgegeben. In der .NET Framework 4.8-Version vor dem Update vom Oktober 2019 wird der Membername zurückgegeben. Ab der [Vorschauversion des Qualitätsrollups für .NET Framework vom Oktober 2019](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) für .NET Framework 4.8 wird standardmäßig `null` zurückgegeben, aber Sie können sich dafür entscheiden, stattdessen den Membernamen zurückzugeben. |
|Vorschlag|Fügen Sie die folgende Einstellung zu Ihrer Datei *web.config* hinzu, damit die Eigenschaft den Membernamen in der [Vorschauversion des Qualitätsrollups für .NET Framework vom Oktober 2019](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) für .NET Framework 4.8 und spätere Versionen zurückgibt:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>In der .NET Framework 4.8-Version vor dem Update vom Oktober 2019 stellt das Hinzufügen dieser Eigenschaft zu Ihrer Datei *web.config* das vorherige Verhalten wieder her, und die Eigenschaft gibt `null` zurück.|
|`Scope`|Unbekannt|
|Version|4.8|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|
