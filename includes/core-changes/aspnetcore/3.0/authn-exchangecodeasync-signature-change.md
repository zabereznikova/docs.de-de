---
ms.openlocfilehash: a4e20e0468d861138ad801c9dbfa15340b3f388c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032456"
---
### <a name="authentication-oauthhandler-exchangecodeasync-signature-changed"></a>Authentifizierung: Signatur von OAuthHandler.ExchangeCodeAsync geändert

In ASP.NET Core 3.0 wurde die Signatur von `OAuthHandler.ExchangeCodeAsync` geändert von:

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(string code, string redirectUri) { throw null; }
```

Nach:

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(Microsoft.AspNetCore.Authentication.OAuth.OAuthCodeExchangeContext context) { throw null; }
```

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Die Zeichenfolgen `code` und `redirectUri` wurden als separate Argumente übergeben.

#### <a name="new-behavior"></a>Neues Verhalten

`Code` und `RedirectUri` sind Eigenschaften von `OAuthCodeExchangeContext`, die über den `OAuthCodeExchangeContext`-Konstruktor festgelegt werden können. Der neue `OAuthCodeExchangeContext`-Typ ist das einzige Argument, das an `OAuthHandler.ExchangeCodeAsync` übergeben wird.

#### <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung ermöglicht die Bereitstellung zusätzlicher Parameter, ohne dass es zu Breaking Changes kommt. Es müssen keine neuen `ExchangeCodeAsync`-Überladungen erstellt werden.

#### <a name="recommended-action"></a>Empfohlene Aktion

Erstellen Sie einen `OAuthCodeExchangeContext` mit geeigneten Werten für `code` und `redirectUri`. Es muss eine <xref:Microsoft.AspNetCore.Authentication.AuthenticationProperties>-Instanz bereitgestellt werden. Diese einzelne `OAuthCodeExchangeContext`-Instanz kann anstelle mehrerer Argumente an `OAuthHandler.ExchangeCodeAsync` übergeben werden.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler%601.ExchangeCodeAsync(System.String,System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler`1.ExchangeCodeAsync(System.String,System.String)`

-->
