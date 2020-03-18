---
ms.openlocfilehash: 58dbb73902c0226fa81acf1a70de2160f406f6c6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901935"
---
### <a name="authorization-iauthorizationpolicyprovider-implementations-require-new-method"></a><span data-ttu-id="35c0d-101">Autorisierung: Implementierungen von IAuthorizationPolicyProvider erfordern eine neue Methode.</span><span class="sxs-lookup"><span data-stu-id="35c0d-101">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>

<span data-ttu-id="35c0d-102">In ASP.NET Core 3.0 wurde `IAuthorizationPolicyProvider` eine neue `GetFallbackPolicyAsync`-Methode hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="35c0d-102">In ASP.NET Core 3.0, a new `GetFallbackPolicyAsync` method was added to `IAuthorizationPolicyProvider`.</span></span> <span data-ttu-id="35c0d-103">Diese Fallbackrichtlinie wird von der Autorisierungsmiddleware verwendet, wenn keine Richtlinie angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="35c0d-103">This fallback policy is used by the authorization middleware when no policy is specified.</span></span>

<span data-ttu-id="35c0d-104">Weitere Informationen finden Sie unter [dotnet/aspnetcore#9759](https://github.com/dotnet/aspnetcore/pull/9759).</span><span class="sxs-lookup"><span data-stu-id="35c0d-104">For more information, see [dotnet/aspnetcore#9759](https://github.com/dotnet/aspnetcore/pull/9759).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="35c0d-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="35c0d-105">Version introduced</span></span>

<span data-ttu-id="35c0d-106">3.0</span><span class="sxs-lookup"><span data-stu-id="35c0d-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="35c0d-107">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="35c0d-107">Old behavior</span></span>

<span data-ttu-id="35c0d-108">Implementierungen von `IAuthorizationPolicyProvider` haben keine `GetFallbackPolicyAsync`-Methode erfordert.</span><span class="sxs-lookup"><span data-stu-id="35c0d-108">Implementations of `IAuthorizationPolicyProvider` didn't require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="35c0d-109">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="35c0d-109">New behavior</span></span>

<span data-ttu-id="35c0d-110">Implementierungen von `IAuthorizationPolicyProvider` erfordern eine `GetFallbackPolicyAsync`-Methode.</span><span class="sxs-lookup"><span data-stu-id="35c0d-110">Implementations of `IAuthorizationPolicyProvider` require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="35c0d-111">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="35c0d-111">Reason for change</span></span>

<span data-ttu-id="35c0d-112">Es war eine neue Methode erforderlich, damit die neue `AuthorizationMiddleware` verwendet wird, wenn keine Richtlinie angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="35c0d-112">A new method was needed for the new `AuthorizationMiddleware` to use when no policy is specified.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="35c0d-113">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="35c0d-113">Recommended action</span></span>

<span data-ttu-id="35c0d-114">Fügen Sie Ihren Implementierungen von `IAuthorizationPolicyProvider` die `GetFallbackPolicyAsync`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="35c0d-114">Add the `GetFallbackPolicyAsync` method to your implementations of `IAuthorizationPolicyProvider`.</span></span>

#### <a name="category"></a><span data-ttu-id="35c0d-115">Kategorie</span><span class="sxs-lookup"><span data-stu-id="35c0d-115">Category</span></span>

<span data-ttu-id="35c0d-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="35c0d-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="35c0d-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="35c0d-117">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider`

-->
