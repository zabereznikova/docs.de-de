---
ms.openlocfilehash: 494e792d63a611cdaedf3e40aa607cfbb0420ae4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901857"
---
### <a name="authentication-newtonsoftjson-types-replaced"></a><span data-ttu-id="9c07a-101">Authentifizierung: Newtonsoft.Json-Typen wurden ersetzt.</span><span class="sxs-lookup"><span data-stu-id="9c07a-101">Authentication: Newtonsoft.Json types replaced</span></span>

<span data-ttu-id="9c07a-102">In ASP.NET Core 3.0 wurden die in Authentifizierungs-APIs verwendeten `Newtonsoft.Json`-Typen durch `System.Text.Json`-Typen ersetzt.</span><span class="sxs-lookup"><span data-stu-id="9c07a-102">In ASP.NET Core 3.0, `Newtonsoft.Json` types used in Authentication APIs have been replaced with `System.Text.Json` types.</span></span> <span data-ttu-id="9c07a-103">Mit Ausnahme der folgenden Fälle ist die grundlegende Verwendung der Authentifizierungspakete nicht betroffen:</span><span class="sxs-lookup"><span data-stu-id="9c07a-103">Except for the following cases, basic usage of the Authentication packages remains unaffected:</span></span>

* <span data-ttu-id="9c07a-104">Von den OAuth-Anbietern abgeleitete Klassen (z. B. von [aspnet-contrib ](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers))</span><span class="sxs-lookup"><span data-stu-id="9c07a-104">Classes derived from the OAuth providers, such as those from [aspnet-contrib](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers).</span></span>
* <span data-ttu-id="9c07a-105">Erweiterte Implementierungen von Anspruchsbearbeitungen</span><span class="sxs-lookup"><span data-stu-id="9c07a-105">Advanced claim manipulation implementations.</span></span>

<span data-ttu-id="9c07a-106">Weitere Informationen finden Sie unter [dotnet/aspnetcore#7105](https://github.com/dotnet/aspnetcore/pull/7105).</span><span class="sxs-lookup"><span data-stu-id="9c07a-106">For more information, see [dotnet/aspnetcore#7105](https://github.com/dotnet/aspnetcore/pull/7105).</span></span> <span data-ttu-id="9c07a-107">Weitere Informationen finden Sie unter [dotnet/aspnetcore#7289](https://github.com/dotnet/aspnetcore/issues/7289).</span><span class="sxs-lookup"><span data-stu-id="9c07a-107">For discussion, see [dotnet/aspnetcore#7289](https://github.com/dotnet/aspnetcore/issues/7289).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9c07a-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9c07a-108">Version introduced</span></span>

<span data-ttu-id="9c07a-109">3.0</span><span class="sxs-lookup"><span data-stu-id="9c07a-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9c07a-110">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="9c07a-110">Recommended action</span></span>

<span data-ttu-id="9c07a-111">Bei abgeleiteten OAuth-Implementierungen besteht die häufigste Änderung darin, dass `JObject.Parse` in der `CreateTicketAsync`-Überschreibung durch `JsonDocument.Parse` ersetzt wird, wie [hier](https://github.com/dotnet/aspnetcore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40) gezeigt.</span><span class="sxs-lookup"><span data-stu-id="9c07a-111">For derived OAuth implementations, the most common change is to replace `JObject.Parse` with `JsonDocument.Parse` in the `CreateTicketAsync` override as shown [here](https://github.com/dotnet/aspnetcore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40).</span></span> <span data-ttu-id="9c07a-112">`JsonDocument` implementiert `IDisposable`.</span><span class="sxs-lookup"><span data-stu-id="9c07a-112">`JsonDocument` implements `IDisposable`.</span></span>

<span data-ttu-id="9c07a-113">In der folgenden Liste werden bekannte Änderungen erläutert:</span><span class="sxs-lookup"><span data-stu-id="9c07a-113">The following list outlines known changes:</span></span>

- <span data-ttu-id="9c07a-114"><xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType> wird `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`.</span><span class="sxs-lookup"><span data-stu-id="9c07a-114"><xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType> becomes `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`.</span></span> <span data-ttu-id="9c07a-115">Alle abgeleiteten Implementierungen von `ClaimAction` sind gleichermaßen betroffen.</span><span class="sxs-lookup"><span data-stu-id="9c07a-115">All derived implementations of `ClaimAction` are similarly affected.</span></span>
- <span data-ttu-id="9c07a-116"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> wird zu `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`</span><span class="sxs-lookup"><span data-stu-id="9c07a-116"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> becomes `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`</span></span>
- <span data-ttu-id="9c07a-117"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> wird zu `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`</span><span class="sxs-lookup"><span data-stu-id="9c07a-117"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> becomes `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`</span></span>
- <span data-ttu-id="9c07a-118">Aus <xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext> wurde ein alter Konstruktor entfernt und im anderen `JObject` durch `JsonElement` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="9c07a-118"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext> has had one old constructor removed and the other replaced `JObject` with `JsonElement`.</span></span> <span data-ttu-id="9c07a-119">Die `User`-Eigenschaft und die `RunClaimActions`-Methode wurden entsprechend angepasst.</span><span class="sxs-lookup"><span data-stu-id="9c07a-119">The `User` property and `RunClaimActions` method have been updated to match.</span></span>
- <span data-ttu-id="9c07a-120"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)> akzeptiert jetzt einen Parameter vom Typ `JsonDocument` anstelle von `JObject`.</span><span class="sxs-lookup"><span data-stu-id="9c07a-120"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)> now accepts a parameter of type `JsonDocument` instead of `JObject`.</span></span> <span data-ttu-id="9c07a-121">Die `Response`-Eigenschaft wurde entsprechend angepasst.</span><span class="sxs-lookup"><span data-stu-id="9c07a-121">The `Response` property has been updated to match.</span></span> <span data-ttu-id="9c07a-122">`OAuthTokenResponse` kann nun verworfen und durch `OAuthHandler` ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="9c07a-122">`OAuthTokenResponse` is now disposable and will be disposed by `OAuthHandler`.</span></span> <span data-ttu-id="9c07a-123">Abgeleitete OAuth-Implementierungen, die `ExchangeCodeAsync` überschreiben, müssen das `JsonDocument` oder die `OAuthTokenResponse` nicht verwerfen.</span><span class="sxs-lookup"><span data-stu-id="9c07a-123">Derived OAuth implementations overriding `ExchangeCodeAsync` don't need to dispose the `JsonDocument` or `OAuthTokenResponse`.</span></span>
- <span data-ttu-id="9c07a-124"><xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType> wurde von `JObject` in `JsonDocument` geändert.</span><span class="sxs-lookup"><span data-stu-id="9c07a-124"><xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType> changed from `JObject` to `JsonDocument`.</span></span>
- <span data-ttu-id="9c07a-125"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType> wurde von `JObject` in `JsonElement` geändert.</span><span class="sxs-lookup"><span data-stu-id="9c07a-125"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType> changed from `JObject` to `JsonElement`.</span></span>
- <span data-ttu-id="9c07a-126"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,Newtonsoft.Json.Linq.JObject)?displayProperty=nameWithType> akzeptiert nun `JsonElement` anstelle von `JObject`.</span><span class="sxs-lookup"><span data-stu-id="9c07a-126"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,Newtonsoft.Json.Linq.JObject)?displayProperty=nameWithType> changed from accepting `JObject` to `JsonElement`.</span></span>

#### <a name="category"></a><span data-ttu-id="9c07a-127">Kategorie</span><span class="sxs-lookup"><span data-stu-id="9c07a-127">Category</span></span>

<span data-ttu-id="9c07a-128">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9c07a-128">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9c07a-129">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="9c07a-129">Affected APIs</span></span>

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
