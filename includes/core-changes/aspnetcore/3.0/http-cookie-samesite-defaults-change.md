---
ms.openlocfilehash: 15ba678431b97e7c961c119d83546569bdf9bad2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74282522"
---
### <a name="http-some-cookie-samesite-defaults-changed-to-none"></a><span data-ttu-id="10627-101">HTTP: Einige Standardeinstellungen für Cookie-SameSite wurden in None geändert.</span><span class="sxs-lookup"><span data-stu-id="10627-101">HTTP: Some cookie SameSite defaults changed to None</span></span>

<span data-ttu-id="10627-102">Bei `SameSite` handelt es sich um eine Option für Cookies, mit der einige CSRF-Angriffe (Cross-Site Request Forgery, websiteübergreifende Anforderungsfälschung) entschärft werden können.</span><span class="sxs-lookup"><span data-stu-id="10627-102">`SameSite` is an option for cookies that can help mitigate some Cross-Site Request Forgery (CSRF) attacks.</span></span> <span data-ttu-id="10627-103">Als diese Option erstmals eingeführt wurde, wurden inkonsistente Standardwerte für verschiedene ASP.NET Core-APIs verwendet.</span><span class="sxs-lookup"><span data-stu-id="10627-103">When this option was initially introduced, inconsistent defaults were used across various ASP.NET Core APIs.</span></span> <span data-ttu-id="10627-104">Diese Inkonsistenz führte zu verwirrenden Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="10627-104">The inconsistency has led to confusing results.</span></span> <span data-ttu-id="10627-105">Ab ASP.NET Core 3.0 sind diese Standardeinstellungen besser abgestimmt.</span><span class="sxs-lookup"><span data-stu-id="10627-105">As of ASP.NET Core 3.0, these defaults are better aligned.</span></span> <span data-ttu-id="10627-106">Sie müssen dieses Feature auf Komponentenbasis aktivieren.</span><span class="sxs-lookup"><span data-stu-id="10627-106">You must opt in to this feature on a per-component basis.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="10627-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="10627-107">Version introduced</span></span>

<span data-ttu-id="10627-108">3.0</span><span class="sxs-lookup"><span data-stu-id="10627-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="10627-109">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="10627-109">Old behavior</span></span>

<span data-ttu-id="10627-110">Ähnliche ASP.NET Core-APIs verwendeten unterschiedliche <xref:Microsoft.AspNetCore.Http.SameSiteMode>-Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="10627-110">Similar ASP.NET Core APIs used different default <xref:Microsoft.AspNetCore.Http.SameSiteMode> values.</span></span> <span data-ttu-id="10627-111">Ein Beispiel für die Inkonsistenz sind `HttpResponse.Cookies.Append(String, String)` und `HttpResponse.Cookies.Append(String, String, CookieOptions)`, wofür die Standardwerte `SameSiteMode.None` bzw. `SameSiteMode.Lax` verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="10627-111">An example of the inconsistency is seen in `HttpResponse.Cookies.Append(String, String)` and `HttpResponse.Cookies.Append(String, String, CookieOptions)`, which defaulted to `SameSiteMode.None` and `SameSiteMode.Lax`, respectively.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="10627-112">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="10627-112">New behavior</span></span>

<span data-ttu-id="10627-113">Alle betroffenen APIs verwenden standardmäßig `SameSiteMode.None`.</span><span class="sxs-lookup"><span data-stu-id="10627-113">All the affected APIs default to `SameSiteMode.None`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="10627-114">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="10627-114">Reason for change</span></span>

<span data-ttu-id="10627-115">Der Standardwert wurde geändert, um `SameSite` zu einem Feature zu machen, das aktiviert werden muss.</span><span class="sxs-lookup"><span data-stu-id="10627-115">The default value was changed to make `SameSite` an opt-in feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="10627-116">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="10627-116">Recommended action</span></span>

<span data-ttu-id="10627-117">Für jede Komponente, die Cookies ausgibt, muss entschieden werden, ob `SameSite` für die zugehörigen Szenarios geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="10627-117">Each component that emits cookies needs to decide if `SameSite` is appropriate for its scenarios.</span></span> <span data-ttu-id="10627-118">Überprüfen Sie die Nutzung der betroffenen APIs, und konfigurieren Sie `SameSite` nach Bedarf neu.</span><span class="sxs-lookup"><span data-stu-id="10627-118">Review your usage of the affected APIs and reconfigure `SameSite` as needed.</span></span>

#### <a name="category"></a><span data-ttu-id="10627-119">Kategorie</span><span class="sxs-lookup"><span data-stu-id="10627-119">Category</span></span>

<span data-ttu-id="10627-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="10627-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="10627-121">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="10627-121">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)`
- `Overload:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy`

-->
