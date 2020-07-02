---
ms.openlocfilehash: c5a061dffa1deb66e1769d6ec70dfa2155ac6a31
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615707"
---
### <a name="calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a>Das Aufrufen von CreateDefaultAuthorizationContext mit einem NULL-Argument wurde geändert

#### <a name="details"></a>Details

Die Implementierung des <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=fullName>-Elements, das von einem Aufruf von <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=fullName> mit dem NULL-Wert als Argument „authorizationPolicies“ zurückgegeben wurde, hat seine Implementierung in .NET Framework 4.6 geändert.

#### <a name="suggestion"></a>Vorschlag

In seltenen Fällen liegen bei WCF-Apps, die die benutzerdefinierte Authentifizierung verwenden, möglicherweise Verhaltensunterschiede vor. In derartigen Fällen gibt es zwei Möglichkeiten, um das vorherige Verhalten wiederherzustellen:

- Kompilieren Sie Ihre App erneut, damit sie auf eine frühere Version als .NET Framework 4.6 abzielt. Verwenden Sie für mithilfe von IIS gehosteten Diensten das `<httpRuntime targetFramework="x.x">`-Element, um auf eine frühere Version von .NET Framework abzuzielen.
- Fügen Sie dem Abschnitt `<appSettings>` Ihrer Datei „app.config“ die folgende Zeile hinzu:

    ```xml
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />
    ```

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.6         |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=nameWithType>
