---
ms.openlocfilehash: 3b94c88809513e31a5f226bcfce39abbfa4de378
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70017371"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a>ASP.NET ValidationContext.MemberName ist bei Verwendung des benutzerdefinierten DataAnnotations.ValidationAttribute nicht NULL

|   |   |
|---|---|
|Details|Wenn in .NET Framework 4.7.2 und früheren Versionen ein benutzerdefiniertes <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> verwendet wurde, wurde von der <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType>-Eigenschaft <code>null</code> zurückgegeben.  In .NET Framework 4.8 wird der Membername zurückgegeben.|
|Vorschlag|Fügen Sie die folgende Einstellung zur Konfigurationsdatei Ihrer App hinzu, um das vorherige Verhalten wiederherzustellen:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Dieses Verhalten wird in einem zukünftigen Release geändert. Dann müssen Sie das neue Verhalten explizit aktivieren. Die Eigenschaft wird dann einen nicht-NULL-Wert für das benutzerdefinierte `ValidationAttribute`-Element zurückgeben, wenn die Option `aspnet:GetValidationMemberName` auf `true` festgelegt ist.|
|Bereich|Unbekannt|
|Version|4.8|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|
