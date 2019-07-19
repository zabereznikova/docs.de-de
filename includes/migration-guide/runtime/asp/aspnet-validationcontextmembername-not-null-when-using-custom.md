---
ms.openlocfilehash: df13f6938ebaf8e96bb2825c1495044621f1c31b
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802611"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a>ASP.NET ValidationContext.MemberName ist bei Verwendung des benutzerdefinierten DataAnnotations.ValidationAttribute nicht NULL

|   |   |
|---|---|
|Details|Wenn in .NET Framework 4.7.2 und früheren Versionen ein benutzerdefiniertes <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> verwendet wurde, wurde von der <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType>-Eigenschaft <code>null</code> zurückgegeben.  In .NET Framework 4.8 wird der Membername zurückgegeben.|
|Vorschlag|Das Standardverhalten der <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType>-Eigenschaft bleibt unverändert.  Fügen Sie der Konfigurationsdatei Ihrer Anwendung die folgende Einstellung hinzu, um von der <code>ValidationContext.MemberName</code>-Eigenschaft einen gültigen Wert abzurufen:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Bereich|Unbekannt|
|Version|4.8|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|

