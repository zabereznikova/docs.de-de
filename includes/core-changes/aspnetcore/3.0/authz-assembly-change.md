---
ms.openlocfilehash: b91cdc7a0d2e4258662155a840500ce21ab35760
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74100997"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a><span data-ttu-id="7c768-101">Autorisierung: AddAuthorization-Überladung in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="7c768-101">Authorization: AddAuthorization overload moved to different assembly</span></span>

<span data-ttu-id="7c768-102">Die wichtigsten `AddAuthorization`-Methoden, die bisher in `Microsoft.AspNetCore.Authorization` enthalten waren, wurden in `AddAuthorizationCore` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="7c768-102">The core `AddAuthorization` methods that used to reside in `Microsoft.AspNetCore.Authorization` were renamed to `AddAuthorizationCore`.</span></span> <span data-ttu-id="7c768-103">Die alten `AddAuthorization`-Methoden sind immer noch vorhanden, befinden sich jedoch stattdessen in der Assembly `Microsoft.AspNetCore.Authorization.Policy`.</span><span class="sxs-lookup"><span data-stu-id="7c768-103">The old `AddAuthorization` methods still exist, but are in the `Microsoft.AspNetCore.Authorization.Policy` assembly instead.</span></span> <span data-ttu-id="7c768-104">Dies sollte auf Apps, die beide Methoden verwenden, keine Auswirkung haben.</span><span class="sxs-lookup"><span data-stu-id="7c768-104">Apps using both methods should see no impact.</span></span> <span data-ttu-id="7c768-105">Beachten Sie, dass `Microsoft.AspNetCore.Authorization.Policy` nun im freigegebenen Framework und nicht mehr in einem eigenständigen Paket enthalten ist, wie unter [Freigegebenes Framework: Assemblys aus Microsoft.AspNetCore.App entfernt](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp) dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7c768-105">Note that `Microsoft.AspNetCore.Authorization.Policy` now ships in the shared framework rather than a standalone package as discussed in [Shared framework: Assemblies removed from Microsoft.AspNetCore.App](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7c768-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="7c768-106">Version introduced</span></span>

<span data-ttu-id="7c768-107">3.0</span><span class="sxs-lookup"><span data-stu-id="7c768-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="7c768-108">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="7c768-108">Old behavior</span></span>
<span data-ttu-id="7c768-109">Die `AddAuthorization`-Methoden waren in `Microsoft.AspNetCore.Authorization` enthalten.</span><span class="sxs-lookup"><span data-stu-id="7c768-109">`AddAuthorization` methods existed in `Microsoft.AspNetCore.Authorization`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="7c768-110">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="7c768-110">New behavior</span></span>

<span data-ttu-id="7c768-111">Die `AddAuthorization`-Methoden sind jetzt in `Microsoft.AspNetCore.Authorization.Policy` enthalten.</span><span class="sxs-lookup"><span data-stu-id="7c768-111">`AddAuthorization` methods exist in `Microsoft.AspNetCore.Authorization.Policy`.</span></span> <span data-ttu-id="7c768-112">`AddAuthorizationCore` ist der neue Name für die alten Methoden.</span><span class="sxs-lookup"><span data-stu-id="7c768-112">`AddAuthorizationCore` is the new name for the old methods.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="7c768-113">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="7c768-113">Reason for change</span></span>

<span data-ttu-id="7c768-114">`AddAuthorization` ist ein besserer Methodenname für das Hinzufügen aller allgemeinen Dienste, die für die Autorisierung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="7c768-114">`AddAuthorization` is a better method name for adding all common services needed for authorization.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7c768-115">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="7c768-115">Recommended action</span></span>

<span data-ttu-id="7c768-116">Fügen Sie entweder einen Verweis auf `Microsoft.AspNetCore.Authorization.Policy` hinzu, oder verwenden Sie stattdessen `AddAuthorizationCore`.</span><span class="sxs-lookup"><span data-stu-id="7c768-116">Either add a reference to `Microsoft.AspNetCore.Authorization.Policy` or use `AddAuthorizationCore` instead.</span></span>

#### <a name="category"></a><span data-ttu-id="7c768-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="7c768-117">Category</span></span>

<span data-ttu-id="7c768-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7c768-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7c768-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="7c768-119">Affected APIs</span></span>

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
