---
ms.openlocfilehash: c10d617e07ca2fa0239298d449d93cf833b83fce
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81275204"
---
### <a name="calls-to-claimsidentity-constructors"></a>Aufrufe von ClaimsIdentity-Konstruktoren

|   |   |
|---|---|
|Details|Ab .NET Framework 4.6.2 legen <xref:System.Security.Claims.ClaimsIdentity>-Konstruktoren mit einem <xref:System.Security.Principal.IIdentity?displayProperty=name>-Parameter die Eigenschaft <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name> anders fest. Wenn es sich bei dem <xref:System.Security.Principal.IIdentity?displayProperty=name>-Argument um ein <xref:System.Security.Claims.ClaimsIdentity>-Objekt handelt und die <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name>-Eigenschaft des <xref:System.Security.Claims.ClaimsIdentity>-Objekts nicht <code>null</code> ist, wird die <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name>-Eigenschaft mithilfe der <xref:System.Security.Claims.ClaimsIdentity.Clone>-Methode angefügt. In .NET Framework 4.6.1 und früheren Versionen wurde die <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name>-Eigenschaft als vorhandener Verweis angefügt. Aufgrund der Änderung ab .NET Framework 4.6.2 entspricht die <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name>-Eigenschaft des neuen <xref:System.Security.Claims.ClaimsIdentity>-Objekts nicht der <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name>-Eigenschaft des Konstruktorarguments <xref:System.Security.Principal.IIdentity?displayProperty=name>. In .NET Framework 4.6.1 und früheren Versionen sind die Eigenschaften gleich.|
|Vorschlag|Wenn dieses Verhalten nicht erwünscht ist, können Sie das vorherige Verhalten wiederherstellen, indem Sie den <code>Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity</code>-Schalter in Ihrer Anwendungskonfigurationsdatei auf <code>true</code> festlegen. Dazu müssen Sie dem Abschnitt <code>&lt;runtime&gt;</code> Ihrer web.config-Datei Folgendes hinzufügen:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|`Scope`|Edge|
|Version|4.6.2|
|Geben Sie Folgendes ein:|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity)></li><li><xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim})></li><li><xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim},System.String,System.String,System.String)></li></ul>|
