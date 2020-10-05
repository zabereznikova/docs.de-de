---
ms.openlocfilehash: a9545c66d3873b5114fe66e13c77ddc28e20020e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077604"
---
### <a name="blazor-protectedbrowserstorage-feature-moved-to-shared-framework"></a><span data-ttu-id="1d64f-101">Blazor: Das Feature ProtectedBrowserStorage wurde in das freigegebene Framework verschoben</span><span class="sxs-lookup"><span data-stu-id="1d64f-101">Blazor: ProtectedBrowserStorage feature moved to shared framework</span></span>

<span data-ttu-id="1d64f-102">Im Rahmen des Release von ASP.NET Core 5.0 RC2 wurde das Feature `ProtectedBrowserStorage` in das freigegebene Framework von ASP.NET Core verschoben.</span><span class="sxs-lookup"><span data-stu-id="1d64f-102">As part of the ASP.NET Core 5.0 RC2 release, the `ProtectedBrowserStorage` feature moved to the ASP.NET Core shared framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1d64f-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="1d64f-103">Version introduced</span></span>

<span data-ttu-id="1d64f-104">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="1d64f-104">5.0 RC2</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="1d64f-105">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="1d64f-105">Old behavior</span></span>

<span data-ttu-id="1d64f-106">In ASP.NET Core 5.0, Preview 8 ist das Feature als Teil des Pakets [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) verfügbar, kann aber nur in Blazor WebAssembly verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1d64f-106">In ASP.NET Core 5.0 Preview 8, the feature is available as a part of the [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) package but was only usable in Blazor WebAssembly.</span></span>

<span data-ttu-id="1d64f-107">In ASP.NET Core 5.0 RC1 ist das Feature als Teil des Pakets [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) verfügbar, das auf das gemeinsame Framework `Microsoft.AspNetCore.App` verweist.</span><span class="sxs-lookup"><span data-stu-id="1d64f-107">In ASP.NET Core 5.0 RC1, the feature is available as part of the [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) package, which references the `Microsoft.AspNetCore.App` shared framework.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="1d64f-108">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="1d64f-108">New behavior</span></span>

<span data-ttu-id="1d64f-109">In ASP.NET Core 5.0 RC2 wird kein Verweis auf ein NuGet-Paket mehr benötigt, um auf das Feature zu verweisen und dieses zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d64f-109">In ASP.NET Core 5.0 RC2, a NuGet package reference is no longer needed to reference and use the feature.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="1d64f-110">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="1d64f-110">Reason for change</span></span>

<span data-ttu-id="1d64f-111">Die Umstellung auf das freigegebene Framework sorgt für mehr Benutzerfreundlichkeit.</span><span class="sxs-lookup"><span data-stu-id="1d64f-111">The move to the shared framework is a better fit for the user experience customers expect.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1d64f-112">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="1d64f-112">Recommended action</span></span>

<span data-ttu-id="1d64f-113">Wenn Sie ein Upgrade von ASP.NET Core 5.0 RC1 ausführen, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="1d64f-113">If upgrading from ASP.NET Core 5.0 RC1, complete the following steps:</span></span>

1. <span data-ttu-id="1d64f-114">Entfernen Sie den Verweis auf das Paket `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` aus dem Projekt.</span><span class="sxs-lookup"><span data-stu-id="1d64f-114">Remove the `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` package reference from the project.</span></span>
1. <span data-ttu-id="1d64f-115">Ersetzen Sie `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` durch `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span><span class="sxs-lookup"><span data-stu-id="1d64f-115">Replace `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="1d64f-116">Entfernen Sie den Aufruf von `AddProtectedBrowserStorage` aus ihrer `Startup`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="1d64f-116">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

<span data-ttu-id="1d64f-117">Wenn Sie ein Upgrade von ASP.NET Core 5.0, Preview 8 ausführen, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="1d64f-117">If upgrading from ASP.NET Core 5.0 Preview 8, complete the following steps:</span></span>

1. <span data-ttu-id="1d64f-118">Entfernen Sie den Verweis auf das Paket `Microsoft.AspNetCore.Components.Web.Extensions` aus dem Projekt.</span><span class="sxs-lookup"><span data-stu-id="1d64f-118">Remove the `Microsoft.AspNetCore.Components.Web.Extensions` package reference from the project.</span></span>
1. <span data-ttu-id="1d64f-119">Ersetzen Sie `using Microsoft.AspNetCore.Components.Web.Extensions;` durch `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span><span class="sxs-lookup"><span data-stu-id="1d64f-119">Replace `using Microsoft.AspNetCore.Components.Web.Extensions;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="1d64f-120">Entfernen Sie den Aufruf von `AddProtectedBrowserStorage` aus ihrer `Startup`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="1d64f-120">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

#### <a name="category"></a><span data-ttu-id="1d64f-121">Kategorie</span><span class="sxs-lookup"><span data-stu-id="1d64f-121">Category</span></span>

<span data-ttu-id="1d64f-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1d64f-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1d64f-123">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="1d64f-123">Affected APIs</span></span>

<span data-ttu-id="1d64f-124">Keine</span><span class="sxs-lookup"><span data-stu-id="1d64f-124">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
