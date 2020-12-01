---
ms.openlocfilehash: ed5a90063b8963d79f412ec1c5c0b9030f980f83
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032563"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a><span data-ttu-id="93934-101">Identität: SignInManager-Konstruktor akzeptiert neuen Parameter.</span><span class="sxs-lookup"><span data-stu-id="93934-101">Identity: SignInManager constructor accepts new parameter</span></span>

<span data-ttu-id="93934-102">Ab ASP.NET Core 3.0 wurde dem `SignInManager`-Konstruktor ein neuer `IUserConfirmation<TUser>`-Parameter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="93934-102">Starting with ASP.NET Core 3.0, a new `IUserConfirmation<TUser>` parameter was added to the `SignInManager` constructor.</span></span> <span data-ttu-id="93934-103">Weitere Informationen finden Sie unter [dotnet/aspnetcore#8356](https://github.com/dotnet/aspnetcore/issues/8356).</span><span class="sxs-lookup"><span data-stu-id="93934-103">For more information, see [dotnet/aspnetcore#8356](https://github.com/dotnet/aspnetcore/issues/8356).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="93934-104">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="93934-104">Version introduced</span></span>

<span data-ttu-id="93934-105">3.0</span><span class="sxs-lookup"><span data-stu-id="93934-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="93934-106">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="93934-106">Reason for change</span></span>

<span data-ttu-id="93934-107">Diese Änderung war erforderlich, um Unterstützung für neue E-Mail-/Bestätigungsflows für Identitäten zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="93934-107">The motivation for the change was to add support for new email / confirmation flows in Identity.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="93934-108">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="93934-108">Recommended action</span></span>

<span data-ttu-id="93934-109">Wenn Sie manuell einen `SignInManager` erstellen, stellen Sie eine Implementierung von `IUserConfirmation` bereit, oder nutzen Sie dafür eine der Abhängigkeitsinjektion.</span><span class="sxs-lookup"><span data-stu-id="93934-109">If manually constructing a `SignInManager`, provide an implementation of `IUserConfirmation` or grab one from dependency injection to provide.</span></span>

#### <a name="category"></a><span data-ttu-id="93934-110">Kategorie</span><span class="sxs-lookup"><span data-stu-id="93934-110">Category</span></span>

<span data-ttu-id="93934-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="93934-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="93934-112">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="93934-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
