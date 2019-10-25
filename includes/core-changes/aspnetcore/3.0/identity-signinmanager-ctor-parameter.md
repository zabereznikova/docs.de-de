---
ms.openlocfilehash: 56b394c4698f60baeb70d3c17d1abee5d867deb7
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394159"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a><span data-ttu-id="ebfc1-101">Identität: SignInManager-Konstruktor akzeptiert neuen Parameter.</span><span class="sxs-lookup"><span data-stu-id="ebfc1-101">Identity: SignInManager constructor accepts new parameter</span></span>

<span data-ttu-id="ebfc1-102">Ab ASP.NET Core 3.0 wurde dem `SignInManager`-Konstruktor ein neuer `IUserConfirmation<TUser>`-Parameter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ebfc1-102">Starting with ASP.NET Core 3.0, a new `IUserConfirmation<TUser>` parameter was added to the `SignInManager` constructor.</span></span> <span data-ttu-id="ebfc1-103">Weitere Informationen finden Sie unter [aspnet/AspNetCore#8356](https://github.com/aspnet/AspNetCore/issues/8356).</span><span class="sxs-lookup"><span data-stu-id="ebfc1-103">For more information, see [aspnet/AspNetCore#8356](https://github.com/aspnet/AspNetCore/issues/8356).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ebfc1-104">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="ebfc1-104">Version introduced</span></span>

<span data-ttu-id="ebfc1-105">3.0</span><span class="sxs-lookup"><span data-stu-id="ebfc1-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ebfc1-106">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="ebfc1-106">Reason for change</span></span>

<span data-ttu-id="ebfc1-107">Diese Änderung war erforderlich, um Unterstützung für neue E-Mail-/Bestätigungsflows für Identitäten zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="ebfc1-107">The motivation for the change was to add support for new email / confirmation flows in Identity.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ebfc1-108">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="ebfc1-108">Recommended action</span></span>

<span data-ttu-id="ebfc1-109">Wenn Sie manuell einen `SignInManager` erstellen, stellen Sie eine Implementierung von `IUserConfirmation` bereit, oder nutzen Sie dafür eine der Abhängigkeitsinjektion.</span><span class="sxs-lookup"><span data-stu-id="ebfc1-109">If manually constructing a `SignInManager`, provide an implementation of `IUserConfirmation` or grab one from dependency injection to provide.</span></span>

#### <a name="category"></a><span data-ttu-id="ebfc1-110">Kategorie</span><span class="sxs-lookup"><span data-stu-id="ebfc1-110">Category</span></span>

<span data-ttu-id="ebfc1-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ebfc1-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ebfc1-112">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ebfc1-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
