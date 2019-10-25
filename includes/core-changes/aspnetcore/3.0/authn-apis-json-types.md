---
ms.openlocfilehash: ad451329d7b9ec15bc8b3c49159346d79944d692
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393973"
---
### <a name="authentication-newtonsoftjson-types-replaced"></a>Authentifizierung: Newtonsoft.Json-Typen wurden ersetzt.

In ASP.NET Core 3.0 wurden die in Authentifizierungs-APIs verwendeten `Newtonsoft.Json`-Typen durch `System.Text.Json`-Typen ersetzt. Mit Ausnahme der folgenden Fälle ist die grundlegende Verwendung der Authentifizierungspakete nicht betroffen:

* Von den OAuth-Anbietern abgeleitete Klassen (z. B. von [aspnet-contrib ](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers))
* Erweiterte Implementierungen von Anspruchsbearbeitungen

Weitere Informationen finden Sie unter [aspnet/AspNetCore#7105](https://github.com/aspnet/AspNetCore/pull/7105). Weitere Informationen finden Sie unter [aspnet/AspNetCore#7289](https://github.com/aspnet/AspNetCore/issues/7289).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Bei abgeleiteten OAuth-Implementierungen besteht die häufigste Änderung darin, dass `JObject.Parse` in der `CreateTicketAsync`-Überschreibung durch `JsonDocument.Parse` ersetzt wird, wie [hier](https://github.com/aspnet/AspNetCore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40) gezeigt. `JsonDocument` implementiert `IDisposable`.

In der folgenden Liste werden bekannte Änderungen erläutert:

- <xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType> wird `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`. Alle abgeleiteten Implementierungen von `ClaimAction` sind gleichermaßen betroffen.
- <xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> wird zu `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`
- <xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> wird zu `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`
- Aus <xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext> wurde ein alter Konstruktor entfernt und im anderen `JObject` durch `JsonElement` ersetzt. Die `User`-Eigenschaft und die `RunClaimActions`-Methode wurden entsprechend angepasst.
- <xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)> akzeptiert jetzt einen Parameter vom Typ `JsonDocument` anstelle von `JObject`. Die `Response`-Eigenschaft wurde entsprechend angepasst. `OAuthTokenResponse` kann nun verworfen und durch `OAuthHandler` ersetzt werden. Abgeleitete OAuth-Implementierungen, die `ExchangeCodeAsync` überschreiben, müssen das `JsonDocument` oder die `OAuthTokenResponse` nicht verwerfen.
- <xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType> wurde von `JObject` in `JsonDocument` geändert.
- <xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType> wurde von `JObject` in `JsonElement` geändert.
- <xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,Newtonsoft.Json.Linq.JObject)?displayProperty=nameWithType> akzeptiert nun `JsonElement` anstelle von `JObject`.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:Microsoft.AspNetCore.Authentication.Facebook?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.Google?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.MicrosoftAccount?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.OAuth?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.OpenIdConnect?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.Twitter?displayProperty=nameWithType>

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Authentication.Facebook`
- `N:Microsoft.AspNetCore.Authentication.Google`
- `N:Microsoft.AspNetCore.Authentication.MicrosoftAccount`
- `N:Microsoft.AspNetCore.Authentication.OAuth`
- `N:Microsoft.AspNetCore.Authentication.OpenIdConnect`
- `N:Microsoft.AspNetCore.Authentication.Twitter`

-->
