---
ms.openlocfilehash: 3f702febc78488b9413ec9303ded211493650f02
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198448"
---
### <a name="mvc-precompilation-tool-deprecated"></a><span data-ttu-id="b7c4d-101">MVC: Vorkompilierungstool wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="b7c4d-101">MVC: Precompilation tool deprecated</span></span>

<span data-ttu-id="b7c4d-102">In ASP.NET Core 1.1 wurde das Paket `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` (MVC-Vorkompilierungstool) eingeführt, um die Kompilierung von Razor-Dateien (*CSHTML*-Dateien) bei der Veröffentlichung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b7c4d-102">In ASP.NET Core 1.1, the `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` (MVC precompilation tool) package was introduced to add support for publish-time compilation of Razor files (*.cshtml* files).</span></span> <span data-ttu-id="b7c4d-103">In ASP.NET Core 2.1 wurde das [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-2.1) eingeführt, um die Funktionen des Vorkompilierungstools zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="b7c4d-103">In ASP.NET Core 2.1, the [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-2.1) was introduced to expand upon features of the precompilation tool.</span></span> <span data-ttu-id="b7c4d-104">Mit dem Razor SDK wurde auch die Möglichkeit geschaffen, Razor-Dateien bei der Erstellung und Veröffentlichung zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="b7c4d-104">The Razor SDK added support for build- and publish-time compilation of Razor files.</span></span> <span data-ttu-id="b7c4d-105">Das SDK überprüft die Richtigkeit der *CSHTML*-Dateien zur Erstellungszeit und verbessert gleichzeitig die Startzeit der App.</span><span class="sxs-lookup"><span data-stu-id="b7c4d-105">The SDK verifies the correctness of *.cshtml* files at build time while improving on app startup time.</span></span> <span data-ttu-id="b7c4d-106">Das Razor SDK ist standardmäßig aktiviert und kann ohne weitere Aktion verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b7c4d-106">The Razor SDK is on by default, and no gesture is required to start using it.</span></span>

<span data-ttu-id="b7c4d-107">In ASP.NET Core 3.0 wurde das MVC-Vorkompilierungstool aus der Zeit von ASP.NET Core 1.1 entfernt.</span><span class="sxs-lookup"><span data-stu-id="b7c4d-107">In ASP.NET Core 3.0, the ASP.NET Core 1.1-era MVC precompilation tool was removed.</span></span> <span data-ttu-id="b7c4d-108">Frühere Paketversionen erhalten weiterhin wichtige Fehler- und Sicherheitskorrekturen, wenn Patches veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="b7c4d-108">Earlier package versions will continue receiving important bug and security fixes in the patch release.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b7c4d-109">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="b7c4d-109">Version introduced</span></span>

<span data-ttu-id="b7c4d-110">3.0</span><span class="sxs-lookup"><span data-stu-id="b7c4d-110">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b7c4d-111">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="b7c4d-111">Old behavior</span></span>

<span data-ttu-id="b7c4d-112">Das Paket `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` wurde zum Vorkompilieren von MVC-Razor-Ansichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="b7c4d-112">The `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` package was used to pre-compile MVC Razor views.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="b7c4d-113">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="b7c4d-113">New behavior</span></span>

<span data-ttu-id="b7c4d-114">Das Razor SDK unterstützt diese Funktion nun nativ.</span><span class="sxs-lookup"><span data-stu-id="b7c4d-114">The Razor SDK natively supports this functionality.</span></span> <span data-ttu-id="b7c4d-115">Das Paket `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` wird nicht mehr aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="b7c4d-115">The `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` package is no longer updated.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b7c4d-116">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="b7c4d-116">Reason for change</span></span>

<span data-ttu-id="b7c4d-117">Das Razor SDK bietet mehr Funktionen und überprüft die Richtigkeit der *CSHTML*-Dateien zur Erstellungszeit.</span><span class="sxs-lookup"><span data-stu-id="b7c4d-117">The Razor SDK provides more functionality and verifies the correctness of *.cshtml* files at build time.</span></span> <span data-ttu-id="b7c4d-118">Das SDK verbessert auch die Startzeit von Apps.</span><span class="sxs-lookup"><span data-stu-id="b7c4d-118">The SDK also improves app startup time.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b7c4d-119">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="b7c4d-119">Recommended action</span></span>

<span data-ttu-id="b7c4d-120">Benutzer von ASP.NET Core 2.1 oder höher sollten auf die native Unterstützung für die Vorkompilierung im [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-3.0) wechseln.</span><span class="sxs-lookup"><span data-stu-id="b7c4d-120">For users of ASP.NET Core 2.1 or later, update to use the native support for precompilation in the [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-3.0).</span></span> <span data-ttu-id="b7c4d-121">Wenn Fehler oder fehlende Features die Migration zum Razor SDK verhindern, melden Sie auf [aspnet/AspNetCore](https://github.com/aspnet/AspNetCore/issues) ein Problem.</span><span class="sxs-lookup"><span data-stu-id="b7c4d-121">If bugs or missing features prevent migration to the Razor SDK, open an issue at [aspnet/AspNetCore](https://github.com/aspnet/AspNetCore/issues).</span></span>

#### <a name="category"></a><span data-ttu-id="b7c4d-122">Kategorie</span><span class="sxs-lookup"><span data-stu-id="b7c4d-122">Category</span></span>

<span data-ttu-id="b7c4d-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7c4d-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b7c4d-124">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="b7c4d-124">Affected APIs</span></span>

<span data-ttu-id="b7c4d-125">Keine</span><span class="sxs-lookup"><span data-stu-id="b7c4d-125">None</span></span>

<!-- 

### Affected APIs

Not detectable via API analysis

-->
