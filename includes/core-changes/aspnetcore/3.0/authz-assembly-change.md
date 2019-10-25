---
ms.openlocfilehash: 65bac44c84589fb55d2b04c39088c2825c451a6b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394059"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a><span data-ttu-id="173d9-101">Autorisierung: AddAuthorization-Überladung in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="173d9-101">Authorization: AddAuthorization overload moved to different assembly</span></span>

<span data-ttu-id="173d9-102">Die wichtigsten `AddAuthorization`-Methoden, die bisher in `Microsoft.AspNetCore.Authorization` enthalten waren, wurden in `AddAuthorizationCore` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="173d9-102">The core `AddAuthorization` methods that used to reside in `Microsoft.AspNetCore.Authorization` were renamed to `AddAuthorizationCore`.</span></span> <span data-ttu-id="173d9-103">Die alten `AddAuthorization`-Methoden sind immer noch vorhanden, befinden sich jedoch stattdessen im Paket `Microsoft.AspNetCore.Authorization.Policy`.</span><span class="sxs-lookup"><span data-stu-id="173d9-103">The old `AddAuthorization` methods still exist, but are in the `Microsoft.AspNetCore.Authorization.Policy` package instead.</span></span> <span data-ttu-id="173d9-104">Dies sollte auf Apps, die beide Methoden verwenden, keine Auswirkung haben.</span><span class="sxs-lookup"><span data-stu-id="173d9-104">Apps using both methods should see no impact.</span></span> <span data-ttu-id="173d9-105">Apps, die das Richtlinienpaket nicht verwendet haben, müssen auf die Verwendung von `AddAuthorizationCore` umgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="173d9-105">Apps that weren't using the policy package must switch to using `AddAuthorizationCore`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="173d9-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="173d9-106">Version introduced</span></span>

<span data-ttu-id="173d9-107">3.0</span><span class="sxs-lookup"><span data-stu-id="173d9-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="173d9-108">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="173d9-108">Old behavior</span></span>

<span data-ttu-id="173d9-109">Die `AddAuthorization`-Methoden waren in `Microsoft.AspNetCore.Authorization` enthalten.</span><span class="sxs-lookup"><span data-stu-id="173d9-109">`AddAuthorization` methods existed in `Microsoft.AspNetCore.Authorization`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="173d9-110">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="173d9-110">New behavior</span></span>

<span data-ttu-id="173d9-111">Die `AddAuthorization`-Methoden sind jetzt in `Microsoft.AspNetCore.Authorization.Policy` enthalten.</span><span class="sxs-lookup"><span data-stu-id="173d9-111">`AddAuthorization` methods exist in `Microsoft.AspNetCore.Authorization.Policy`.</span></span> <span data-ttu-id="173d9-112">`AddAuthorizationCore` ist der neue Name für die alten Methoden.</span><span class="sxs-lookup"><span data-stu-id="173d9-112">`AddAuthorizationCore` is the new name for the old methods.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="173d9-113">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="173d9-113">Reason for change</span></span>

<span data-ttu-id="173d9-114">`AddAuthorization` ist ein besserer Methodenname für das Hinzufügen aller allgemeinen Dienste, die für die Autorisierung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="173d9-114">`AddAuthorization` is a better method name for adding all common services needed for authorization.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="173d9-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="173d9-115">Recommended action</span></span>

<span data-ttu-id="173d9-116">Fügen Sie entweder einen Verweis auf `Microsoft.AspNetCore.Authorization.Policy` hinzu, oder verwenden Sie stattdessen `AddAuthorizationCore`.</span><span class="sxs-lookup"><span data-stu-id="173d9-116">Either add a reference to `Microsoft.AspNetCore.Authorization.Policy` or use `AddAuthorizationCore` instead.</span></span>

#### <a name="category"></a><span data-ttu-id="173d9-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="173d9-117">Category</span></span>

<span data-ttu-id="173d9-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="173d9-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="173d9-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="173d9-119">Affected APIs</span></span>

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
