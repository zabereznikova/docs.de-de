---
ms.openlocfilehash: b88f7d4a17f885b687d99ab9410a56039e176080
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614431"
---
### <a name="calls-to-claimsidentity-constructors"></a>Aufrufe von ClaimsIdentity-Konstruktoren

#### <a name="details"></a>Details

Ab .NET Framework 4.6.2 legen <xref:System.Security.Claims.ClaimsIdentity>-Konstruktoren mit einem <xref:System.Security.Principal.IIdentity?displayProperty=fullName>-Parameter die Eigenschaft <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> anders fest. Wenn es sich bei dem <xref:System.Security.Principal.IIdentity?displayProperty=fullName>-Argument um ein <xref:System.Security.Claims.ClaimsIdentity>-Objekt handelt und die <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName>-Eigenschaft des <xref:System.Security.Claims.ClaimsIdentity>-Objekts nicht `null` ist, wird die <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName>-Eigenschaft mithilfe der <xref:System.Security.Claims.ClaimsIdentity.Clone>-Methode angefügt. In .NET Framework 4.6.1 und früheren Versionen wurde die <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName>-Eigenschaft als vorhandener Verweis angefügt. Aufgrund der Änderung ab .NET Framework 4.6.2 entspricht die <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName>-Eigenschaft des neuen <xref:System.Security.Claims.ClaimsIdentity>-Objekts nicht der <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName>-Eigenschaft des Konstruktorarguments <xref:System.Security.Principal.IIdentity?displayProperty=fullName>. In .NET Framework 4.6.1 und früheren Versionen sind die Eigenschaften gleich.

#### <a name="suggestion"></a>Vorschlag

Wenn dieses Verhalten nicht erwünscht ist, können Sie das vorherige Verhalten wiederherstellen, indem Sie den `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity`-Schalter in Ihrer Anwendungskonfigurationsdatei auf `true` festlegen. Dazu müssen Sie dem Abschnitt `<runtime>` Ihrer web.config-Datei Folgendes hinzufügen:

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true" />
  </runtime>
</configuration>
```

| Name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.6.2       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity)>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim})>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim},System.String,System.String,System.String)>
