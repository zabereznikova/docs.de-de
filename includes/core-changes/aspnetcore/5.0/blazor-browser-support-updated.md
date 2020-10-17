---
ms.openlocfilehash: 584014572ab799e1e3ab2f02c9fbf4fe6b0c17e7
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "91804924"
---
### <a name="blazor-updated-browser-support"></a><span data-ttu-id="ed606-101">Blazor: Aktualisierte Browserunterstützung</span><span class="sxs-lookup"><span data-stu-id="ed606-101">Blazor: Updated browser support</span></span>

<span data-ttu-id="ed606-102">Mit ASP.NET Core 5.0 werden [neue Blazor-Features](https://github.com/dotnet/aspnetcore/issues/21514) eingeführt. Einige davon sind mit älteren Browsern nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="ed606-102">ASP.NET Core 5.0 introduces [new Blazor features](https://github.com/dotnet/aspnetcore/issues/21514), some of which are incompatible with older browsers.</span></span> <span data-ttu-id="ed606-103">Die Liste der von Blazor in ASP.NET Core 5.0 unterstützten Browser wurde entsprechend aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="ed606-103">The list of browsers supported by Blazor in ASP.NET Core 5.0 has been updated accordingly.</span></span>

<span data-ttu-id="ed606-104">Weitere Informationen finden Sie im GitHub-Issue [dotnet/aspnetcore#26475](https://github.com/dotnet/aspnetcore/issues/26475).</span><span class="sxs-lookup"><span data-stu-id="ed606-104">For discussion, see GitHub issue [dotnet/aspnetcore#26475](https://github.com/dotnet/aspnetcore/issues/26475).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ed606-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="ed606-105">Version introduced</span></span>

<span data-ttu-id="ed606-106">5.0</span><span class="sxs-lookup"><span data-stu-id="ed606-106">5.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="ed606-107">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="ed606-107">Old behavior</span></span>

<span data-ttu-id="ed606-108">Blazor Server unterstützt Microsoft Internet Explorer 11 mit erforderlichen Polyfills.</span><span class="sxs-lookup"><span data-stu-id="ed606-108">Blazor Server supports Microsoft Internet Explorer 11 with sufficient polyfills.</span></span> <span data-ttu-id="ed606-109">Blazor Server und Blazor WebAssembly können auch mit der [Vorgängerversion von Microsoft Edge](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ed606-109">Blazor Server and Blazor WebAssembly are also functional in [Microsoft Edge Legacy](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy).</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="ed606-110">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="ed606-110">New behavior</span></span>

<span data-ttu-id="ed606-111">Blazor Server in ASP.NET Core 5.0 wird mit Microsoft Internet Explorer 11 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ed606-111">Blazor Server in ASP.NET Core 5.0 isn't supported with Microsoft Internet Explorer 11.</span></span> <span data-ttu-id="ed606-112">Blazor Server und Blazor WebAssembly sind in der Vorgängerversion von Microsoft Edge nicht voll funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="ed606-112">Blazor Server and Blazor WebAssembly aren't fully functional in Microsoft Edge Legacy.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ed606-113">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="ed606-113">Reason for change</span></span>

<span data-ttu-id="ed606-114">Neue Blazor-Features in ASP.NET Core 5.0 sind mit diesen älteren Browsern nicht kompatibel. Außerdem nimmt die Verwendung dieser älteren Browser immer mehr ab.</span><span class="sxs-lookup"><span data-stu-id="ed606-114">New Blazor features in ASP.NET Core 5.0 are incompatible with these older browsers, and use of these older browsers is diminishing.</span></span> <span data-ttu-id="ed606-115">Weitere Informationen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="ed606-115">For more information, see the following resources:</span></span>

* [<span data-ttu-id="ed606-116">Was ist die Vorgängerversion von Microsoft Edge?</span><span class="sxs-lookup"><span data-stu-id="ed606-116">Windows support for Microsoft Edge Legacy is also ending on March 9, 2021</span></span>](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy)
* [<span data-ttu-id="ed606-117">Microsoft 365-Apps und -Dienste beenden die Unterstützung für IE 11; Ende der Unterstützung für die Legacyversion von Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ed606-117">Microsoft 365 apps and services will end support for Microsoft Internet Explorer 11 by August 17, 2021</span></span>](/lifecycle/announcements/m365-ie11-microsoft-edge-legacy)

#### <a name="recommended-action"></a><span data-ttu-id="ed606-118">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="ed606-118">Recommended action</span></span>

<span data-ttu-id="ed606-119">Führen Sie ein Upgrade dieser älteren Browser auf den [neuen, Chromium-basierten Microsoft Edge-Browser](https://www.microsoft.com/edge) durch.</span><span class="sxs-lookup"><span data-stu-id="ed606-119">Upgrade from these older browsers to the [new, Chromium-based Microsoft Edge](https://www.microsoft.com/edge).</span></span> <span data-ttu-id="ed606-120">Für Blazor-Apps, die auf die Unterstützung dieser alten Browser angewiesen sind, können Sie ASP.NET Core 3.1 verwenden.</span><span class="sxs-lookup"><span data-stu-id="ed606-120">For Blazor apps that need to support these older browsers, use ASP.NET Core 3.1.</span></span> <span data-ttu-id="ed606-121">Die Liste unterstützter Browser für Blazor in ASP.NET Core 3.1 wurde nicht geändert und ist unter [Unterstützte Plattformen für ASP.NET Core Blazor](/aspnet/core/blazor/supported-platforms?view=aspnetcore-3.1) dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="ed606-121">The supported browsers list for Blazor in ASP.NET Core 3.1 hasn't changed and is documented at [Supported platforms](/aspnet/core/blazor/supported-platforms?view=aspnetcore-3.1).</span></span>

#### <a name="category"></a><span data-ttu-id="ed606-122">Kategorie</span><span class="sxs-lookup"><span data-stu-id="ed606-122">Category</span></span>

<span data-ttu-id="ed606-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ed606-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ed606-124">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ed606-124">Affected APIs</span></span>

<span data-ttu-id="ed606-125">Keine</span><span class="sxs-lookup"><span data-stu-id="ed606-125">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
