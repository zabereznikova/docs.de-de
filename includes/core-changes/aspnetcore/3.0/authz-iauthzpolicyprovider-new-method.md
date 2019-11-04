---
ms.openlocfilehash: 74b989a2413d2192f7cf5208e400eaed879ea096
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198440"
---
### <a name="authorization-iauthorizationpolicyprovider-implementations-require-new-method"></a>Autorisierung: Implementierungen von IAuthorizationPolicyProvider erfordern eine neue Methode.

In ASP.NET Core 3.0 wurde `IAuthorizationPolicyProvider` eine neue `GetFallbackPolicyAsync`-Methode hinzugefügt. Diese Fallbackrichtlinie wird von der Autorisierungsmiddleware verwendet, wenn keine Richtlinie angegeben wird.

Weitere Informationen finden Sie unter [aspnet/AspNetCore#9759](https://github.com/aspnet/AspNetCore/pull/9759).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Implementierungen von `IAuthorizationPolicyProvider` haben keine `GetFallbackPolicyAsync`-Methode erfordert.

#### <a name="new-behavior"></a>Neues Verhalten

Implementierungen von `IAuthorizationPolicyProvider` erfordern eine `GetFallbackPolicyAsync`-Methode.

#### <a name="reason-for-change"></a>Grund für die Änderung

Es war eine neue Methode erforderlich, damit die neue `AuthorizationMiddleware` verwendet wird, wenn keine Richtlinie angegeben wird.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Fügen Sie Ihren Implementierungen von `IAuthorizationPolicyProvider` die `GetFallbackPolicyAsync`-Methode hinzu.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider`

-->
