---
ms.openlocfilehash: 6679e38aefa7d61ce430dc5375ff3b35c641ea27
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394353"
---
### <a name="identity-signinasync-throws-exception-for-unauthenticated-identity"></a><span data-ttu-id="75c62-101">Identität: SignInAsync löst eine Ausnahme für eine nicht authentifizierte Identität aus</span><span class="sxs-lookup"><span data-stu-id="75c62-101">Identity: SignInAsync throws exception for unauthenticated identity</span></span>

<span data-ttu-id="75c62-102">Standardmäßig löst `SignInAsync` eine Ausnahme für Prinzipale/Identitäten aus, bei denen `IsAuthenticated``false` ist.</span><span class="sxs-lookup"><span data-stu-id="75c62-102">By default, `SignInAsync` throws an exception for principals / identities in which `IsAuthenticated` is `false`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="75c62-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="75c62-103">Version introduced</span></span>

<span data-ttu-id="75c62-104">3.0</span><span class="sxs-lookup"><span data-stu-id="75c62-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="75c62-105">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="75c62-105">Old behavior</span></span>

<span data-ttu-id="75c62-106">`SignInAsync` akzeptiert alle Prinzipale/Identitäten, einschließlich Identitäten, bei denen `IsAuthenticated``false` ist.</span><span class="sxs-lookup"><span data-stu-id="75c62-106">`SignInAsync` accepts any principals / identities, including identities in which `IsAuthenticated` is `false`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="75c62-107">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="75c62-107">New behavior</span></span>

<span data-ttu-id="75c62-108">Standardmäßig löst `SignInAsync` eine Ausnahme für Prinzipale/Identitäten aus, bei denen `IsAuthenticated``false` ist.</span><span class="sxs-lookup"><span data-stu-id="75c62-108">By default, `SignInAsync` throws an exception for principals / identities in which `IsAuthenticated` is `false`.</span></span> <span data-ttu-id="75c62-109">Es gibt ein neues Flag, mit dem dieses Verhalten unterdrückt werden kann, aber das Standardverhalten wurde geändert.</span><span class="sxs-lookup"><span data-stu-id="75c62-109">There's a new flag to suppress this behavior, but the default behavior has changed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="75c62-110">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="75c62-110">Reason for change</span></span>

<span data-ttu-id="75c62-111">Das alte Verhalten war problematisch, da diese Prinzipale standardmäßig von `[Authorize]` / `RequireAuthenticatedUser()` abgelehnt wurden.</span><span class="sxs-lookup"><span data-stu-id="75c62-111">The old behavior was problematic because, by default, these principals were rejected by `[Authorize]` / `RequireAuthenticatedUser()`.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="75c62-112">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="75c62-112">Recommended action</span></span>

<span data-ttu-id="75c62-113">In ASP.NET Core 3.0 Preview 6 gibt es das Flag `RequireAuthenticatedSignIn` in `AuthenticationOptions`, das standardmäßig `true` ist.</span><span class="sxs-lookup"><span data-stu-id="75c62-113">In ASP.NET Core 3.0 Preview 6, there's a `RequireAuthenticatedSignIn` flag on `AuthenticationOptions` that is `true` by default.</span></span> <span data-ttu-id="75c62-114">Legen Sie dieses Flag auf `false` fest, um das alte Verhalten wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="75c62-114">Set this flag to `false` to restore the old behavior.</span></span>

#### <a name="category"></a><span data-ttu-id="75c62-115">Kategorie</span><span class="sxs-lookup"><span data-stu-id="75c62-115">Category</span></span>

<span data-ttu-id="75c62-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="75c62-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="75c62-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="75c62-117">Affected APIs</span></span>

<span data-ttu-id="75c62-118">Keine</span><span class="sxs-lookup"><span data-stu-id="75c62-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
