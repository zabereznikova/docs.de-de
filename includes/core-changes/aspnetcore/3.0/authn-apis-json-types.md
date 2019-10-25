---
ms.openlocfilehash: ad451329d7b9ec15bc8b3c49159346d79944d692
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393973"
---
### <a name="authentication-newtonsoftjson-types-replaced"></a><span data-ttu-id="fd68d-101">Authentifizierung: Newtonsoft.Json-Typen wurden ersetzt.</span><span class="sxs-lookup"><span data-stu-id="fd68d-101">Authentication: Newtonsoft.Json types replaced</span></span>

<span data-ttu-id="fd68d-102">In ASP.NET Core 3.0 wurden die in Authentifizierungs-APIs verwendeten `Newtonsoft.Json`-Typen durch `System.Text.Json`-Typen ersetzt.</span><span class="sxs-lookup"><span data-stu-id="fd68d-102">In ASP.NET Core 3.0, `Newtonsoft.Json` types used in Authentication APIs have been replaced with `System.Text.Json` types.</span></span> <span data-ttu-id="fd68d-103">Mit Ausnahme der folgenden Fälle ist die grundlegende Verwendung der Authentifizierungspakete nicht betroffen:</span><span class="sxs-lookup"><span data-stu-id="fd68d-103">Except for the following cases, basic usage of the Authentication packages remains unaffected:</span></span>

* <span data-ttu-id="fd68d-104">Von den OAuth-Anbietern abgeleitete Klassen (z. B. von [aspnet-contrib ](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers))</span><span class="sxs-lookup"><span data-stu-id="fd68d-104">Classes derived from the OAuth providers, such as those from [aspnet-contrib](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers).</span></span>
* <span data-ttu-id="fd68d-105">Erweiterte Implementierungen von Anspruchsbearbeitungen</span><span class="sxs-lookup"><span data-stu-id="fd68d-105">Advanced claim manipulation implementations.</span></span>

<span data-ttu-id="fd68d-106">Weitere Informationen finden Sie unter [aspnet/AspNetCore#7105](https://github.com/aspnet/AspNetCore/pull/7105).</span><span class="sxs-lookup"><span data-stu-id="fd68d-106">For more information, see [aspnet/AspNetCore#7105](https://github.com/aspnet/AspNetCore/pull/7105).</span></span> <span data-ttu-id="fd68d-107">Weitere Informationen finden Sie unter [aspnet/AspNetCore#7289](https://github.com/aspnet/AspNetCore/issues/7289).</span><span class="sxs-lookup"><span data-stu-id="fd68d-107">For discussion, see [aspnet/AspNetCore#7289](https://github.com/aspnet/AspNetCore/issues/7289).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="fd68d-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="fd68d-108">Version introduced</span></span>

<span data-ttu-id="fd68d-109">3.0</span><span class="sxs-lookup"><span data-stu-id="fd68d-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="fd68d-110">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="fd68d-110">Recommended action</span></span>

<span data-ttu-id="fd68d-111">Bei abgeleiteten OAuth-Implementierungen besteht die häufigste Änderung darin, dass `JObject.Parse` in der `CreateTicketAsync`-Überschreibung durch `JsonDocument.Parse` ersetzt wird, wie [hier](https://github.com/aspnet/AspNetCore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40) gezeigt.</span><span class="sxs-lookup"><span data-stu-id="fd68d-111">For derived OAuth implementations, the most common change is to replace `JObject.Parse` with `JsonDocument.Parse` in the `CreateTicketAsync` override as shown [here](https://github.com/aspnet/AspNetCore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40).</span></span> <span data-ttu-id="fd68d-112">`JsonDocument` implementiert `IDisposable`.</span><span class="sxs-lookup"><span data-stu-id="fd68d-112">`JsonDocument` implements `IDisposable`.</span></span>

<span data-ttu-id="fd68d-113">In der folgenden Liste werden bekannte Änderungen erläutert:</span><span class="sxs-lookup"><span data-stu-id="fd68d-113">The following list outlines known changes:</span></span>

- <span data-ttu-id="fd68d-114"><xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType> wird `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`.</span><span class="sxs-lookup"><span data-stu-id="fd68d-114"><xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType> becomes `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`.</span></span> <span data-ttu-id="fd68d-115">Alle abgeleiteten Implementierungen von `ClaimAction` sind gleichermaßen betroffen.</span><span class="sxs-lookup"><span data-stu-id="fd68d-115">All derived implementations of `ClaimAction` are similarly affected.</span></span>
- <span data-ttu-id="fd68d-116"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> wird zu `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`</span><span class="sxs-lookup"><span data-stu-id="fd68d-116"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> becomes `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`</span></span>
- <span data-ttu-id="fd68d-117"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> wird zu `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`</span><span class="sxs-lookup"><span data-stu-id="fd68d-117"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> becomes `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`</span></span>
- <span data-ttu-id="fd68d-118">Aus <xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext> wurde ein alter Konstruktor entfernt und im anderen `JObject` durch `JsonElement` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="fd68d-118"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext> has had one old constructor removed and the other replaced `JObject` with `JsonElement`.</span></span> <span data-ttu-id="fd68d-119">Die `User`-Eigenschaft und die `RunClaimActions`-Methode wurden entsprechend angepasst.</span><span class="sxs-lookup"><span data-stu-id="fd68d-119">The `User` property and `RunClaimActions` method have been updated to match.</span></span>
- <span data-ttu-id="fd68d-120"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)> akzeptiert jetzt einen Parameter vom Typ `JsonDocument` anstelle von `JObject`.</span><span class="sxs-lookup"><span data-stu-id="fd68d-120"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)> now accepts a parameter of type `JsonDocument` instead of `JObject`.</span></span> <span data-ttu-id="fd68d-121">Die `Response`-Eigenschaft wurde entsprechend angepasst.</span><span class="sxs-lookup"><span data-stu-id="fd68d-121">The `Response` property has been updated to match.</span></span> <span data-ttu-id="fd68d-122">`OAuthTokenResponse` kann nun verworfen und durch `OAuthHandler` ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="fd68d-122">`OAuthTokenResponse` is now disposable and will be disposed by `OAuthHandler`.</span></span> <span data-ttu-id="fd68d-123">Abgeleitete OAuth-Implementierungen, die `ExchangeCodeAsync` überschreiben, müssen das `JsonDocument` oder die `OAuthTokenResponse` nicht verwerfen.</span><span class="sxs-lookup"><span data-stu-id="fd68d-123">Derived OAuth implementations overriding `ExchangeCodeAsync` don't need to dispose the `JsonDocument` or `OAuthTokenResponse`.</span></span>
- <span data-ttu-id="fd68d-124"><xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType> wurde von `JObject` in `JsonDocument` geändert.</span><span class="sxs-lookup"><span data-stu-id="fd68d-124"><xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType> changed from `JObject` to `JsonDocument`.</span></span>
- <span data-ttu-id="fd68d-125"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType> wurde von `JObject` in `JsonElement` geändert.</span><span class="sxs-lookup"><span data-stu-id="fd68d-125"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType> changed from `JObject` to `JsonElement`.</span></span>
- <span data-ttu-id="fd68d-126"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,Newtonsoft.Json.Linq.JObject)?displayProperty=nameWithType> akzeptiert nun `JsonElement` anstelle von `JObject`.</span><span class="sxs-lookup"><span data-stu-id="fd68d-126"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,Newtonsoft.Json.Linq.JObject)?displayProperty=nameWithType> changed from accepting `JObject` to `JsonElement`.</span></span>

#### <a name="category"></a><span data-ttu-id="fd68d-127">Kategorie</span><span class="sxs-lookup"><span data-stu-id="fd68d-127">Category</span></span>

<span data-ttu-id="fd68d-128">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="fd68d-128">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fd68d-129">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="fd68d-129">Affected APIs</span></span>

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
