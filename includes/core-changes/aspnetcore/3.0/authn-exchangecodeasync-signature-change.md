---
ms.openlocfilehash: a4e20e0468d861138ad801c9dbfa15340b3f388c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032456"
---
### <a name="authentication-oauthhandler-exchangecodeasync-signature-changed"></a><span data-ttu-id="9b530-101">Authentifizierung: Signatur von OAuthHandler.ExchangeCodeAsync geändert</span><span class="sxs-lookup"><span data-stu-id="9b530-101">Authentication: OAuthHandler ExchangeCodeAsync signature changed</span></span>

<span data-ttu-id="9b530-102">In ASP.NET Core 3.0 wurde die Signatur von `OAuthHandler.ExchangeCodeAsync` geändert von:</span><span class="sxs-lookup"><span data-stu-id="9b530-102">In ASP.NET Core 3.0, the signature of `OAuthHandler.ExchangeCodeAsync` was changed from:</span></span>

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(string code, string redirectUri) { throw null; }
```

<span data-ttu-id="9b530-103">Nach:</span><span class="sxs-lookup"><span data-stu-id="9b530-103">To:</span></span>

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(Microsoft.AspNetCore.Authentication.OAuth.OAuthCodeExchangeContext context) { throw null; }
```

#### <a name="version-introduced"></a><span data-ttu-id="9b530-104">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9b530-104">Version introduced</span></span>

<span data-ttu-id="9b530-105">3.0</span><span class="sxs-lookup"><span data-stu-id="9b530-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="9b530-106">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="9b530-106">Old behavior</span></span>

<span data-ttu-id="9b530-107">Die Zeichenfolgen `code` und `redirectUri` wurden als separate Argumente übergeben.</span><span class="sxs-lookup"><span data-stu-id="9b530-107">The `code` and `redirectUri` strings were passed as separate arguments.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="9b530-108">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="9b530-108">New behavior</span></span>

<span data-ttu-id="9b530-109">`Code` und `RedirectUri` sind Eigenschaften von `OAuthCodeExchangeContext`, die über den `OAuthCodeExchangeContext`-Konstruktor festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="9b530-109">`Code` and `RedirectUri` are properties on `OAuthCodeExchangeContext` that can be set via the `OAuthCodeExchangeContext` constructor.</span></span> <span data-ttu-id="9b530-110">Der neue `OAuthCodeExchangeContext`-Typ ist das einzige Argument, das an `OAuthHandler.ExchangeCodeAsync` übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="9b530-110">The new `OAuthCodeExchangeContext` type is the only argument passed to `OAuthHandler.ExchangeCodeAsync`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="9b530-111">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="9b530-111">Reason for change</span></span>

<span data-ttu-id="9b530-112">Diese Änderung ermöglicht die Bereitstellung zusätzlicher Parameter, ohne dass es zu Breaking Changes kommt.</span><span class="sxs-lookup"><span data-stu-id="9b530-112">This change allows additional parameters to be provided in a non-breaking manner.</span></span> <span data-ttu-id="9b530-113">Es müssen keine neuen `ExchangeCodeAsync`-Überladungen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9b530-113">There's no need to create new `ExchangeCodeAsync` overloads.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9b530-114">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="9b530-114">Recommended action</span></span>

<span data-ttu-id="9b530-115">Erstellen Sie einen `OAuthCodeExchangeContext` mit geeigneten Werten für `code` und `redirectUri`.</span><span class="sxs-lookup"><span data-stu-id="9b530-115">Construct an `OAuthCodeExchangeContext` with the appropriate `code` and `redirectUri` values.</span></span> <span data-ttu-id="9b530-116">Es muss eine <xref:Microsoft.AspNetCore.Authentication.AuthenticationProperties>-Instanz bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9b530-116">An <xref:Microsoft.AspNetCore.Authentication.AuthenticationProperties> instance must be provided.</span></span> <span data-ttu-id="9b530-117">Diese einzelne `OAuthCodeExchangeContext`-Instanz kann anstelle mehrerer Argumente an `OAuthHandler.ExchangeCodeAsync` übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="9b530-117">This single `OAuthCodeExchangeContext` instance can be passed to `OAuthHandler.ExchangeCodeAsync` instead of multiple arguments.</span></span>

#### <a name="category"></a><span data-ttu-id="9b530-118">Kategorie</span><span class="sxs-lookup"><span data-stu-id="9b530-118">Category</span></span>

<span data-ttu-id="9b530-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9b530-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9b530-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="9b530-120">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler%601.ExchangeCodeAsync(System.String,System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler`1.ExchangeCodeAsync(System.String,System.String)`

-->
