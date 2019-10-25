---
ms.openlocfilehash: a16d443a37fb0bb5f6bdc4a39e7dcb4f91c54ead
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394243"
---
### <a name="authorization-iauthorizationpolicyprovider-implementations-require-new-method"></a><span data-ttu-id="5f1fa-101">Autorisierung: Implementierungen von IAuthorizationPolicyProvider erfordern eine neue Methode.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-101">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>

<span data-ttu-id="5f1fa-102">In ASP.NET Core 3.0 wurde `IAuthorizationPolicyProvider` eine neue `GetFallbackPolicyAsync`-Methode hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-102">In ASP.NET Core 3.0, a new `GetFallbackPolicyAsync` method was added to `IAuthorizationPolicyProvider`.</span></span> <span data-ttu-id="5f1fa-103">Diese Fallbackrichtlinie wird von der Autorisierungsmiddleware verwendet, wenn keine Richtlinie angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-103">This fallback policy is used by the authorization middleware when no policy is specified.</span></span>

<span data-ttu-id="5f1fa-104">Weitere Informationen finden Sie unter [aspnet/AspNetCore#9759](https://github.com/aspnet/AspNetCore/pull/9759).</span><span class="sxs-lookup"><span data-stu-id="5f1fa-104">For more information, see [aspnet/AspNetCore#9759](https://github.com/aspnet/AspNetCore/pull/9759).</span></span> 

#### <a name="version-introduced"></a><span data-ttu-id="5f1fa-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="5f1fa-105">Version introduced</span></span>

<span data-ttu-id="5f1fa-106">3.0</span><span class="sxs-lookup"><span data-stu-id="5f1fa-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="5f1fa-107">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="5f1fa-107">Old behavior</span></span>

<span data-ttu-id="5f1fa-108">Implementierungen von `IAuthorizationPolicyProvider` haben keine `GetFallbackPolicyAsync`-Methode erfordert.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-108">Implementations of `IAuthorizationPolicyProvider` didn't require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="5f1fa-109">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="5f1fa-109">New behavior</span></span>

<span data-ttu-id="5f1fa-110">Implementierungen von `IAuthorizationPolicyProvider` erfordern eine `GetFallbackPolicyAsync`-Methode.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-110">Implementations of `IAuthorizationPolicyProvider` require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="5f1fa-111">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="5f1fa-111">Reason for change</span></span>

<span data-ttu-id="5f1fa-112">Es war eine neue Methode erforderlich, damit die neue `AuthorizationMiddleware` verwendet wird, wenn keine Richtlinie angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-112">A new method was needed for the new `AuthorizationMiddleware` to use when no policy is specified.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5f1fa-113">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="5f1fa-113">Recommended action</span></span>

<span data-ttu-id="5f1fa-114">Fügen Sie Ihren Implementierungen von `IAuthorizationPolicyProvider` die `GetFallbackPolicyAsync`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-114">Add the `GetFallbackPolicyAsync` method to your implementations of `IAuthorizationPolicyProvider`.</span></span>

#### <a name="category"></a><span data-ttu-id="5f1fa-115">Kategorie</span><span class="sxs-lookup"><span data-stu-id="5f1fa-115">Category</span></span>

<span data-ttu-id="5f1fa-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5f1fa-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5f1fa-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="5f1fa-117">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider`

-->
