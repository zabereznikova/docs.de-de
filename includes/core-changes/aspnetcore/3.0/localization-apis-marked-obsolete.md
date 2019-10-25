---
ms.openlocfilehash: da1ec7908b3082fc61313cb805773aa600bc1b5d
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394416"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete"></a><span data-ttu-id="d9914-101">Lokalisierung: ResourceManagerWithCultureStringLocalizer und WithCulture wurden als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="d9914-101">Localization: ResourceManagerWithCultureStringLocalizer and WithCulture marked obsolete</span></span>

<span data-ttu-id="d9914-102">Die [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18)-Klasse und der Schnittstellenmember [WithCulture](https://github.com/aspnet/Localization/blob/master/src/Microsoft.Extensions.Localization/ResourceManagerStringLocalizer.cs#L154-L170) führten häufig zu Verwirrung bei Benutzern der Lokalisierung, insbesondere bei der Erstellung einer eigenen Implementierung von `IStringLocalizer`.</span><span class="sxs-lookup"><span data-stu-id="d9914-102">The [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18) class and [WithCulture](https://github.com/aspnet/Localization/blob/master/src/Microsoft.Extensions.Localization/ResourceManagerStringLocalizer.cs#L154-L170) interface member are often sources of confusion for users of localization, especially when creating their own `IStringLocalizer` implementation.</span></span> <span data-ttu-id="d9914-103">Diese Elemente vermittelten dem Benutzer den Eindruck, dass eine `IStringLocalizer`-Instanz lediglich „pro Sprache, pro Ressource“ gilt.</span><span class="sxs-lookup"><span data-stu-id="d9914-103">These items give the user the impression that an `IStringLocalizer` instance is "per-language, per-resource".</span></span> <span data-ttu-id="d9914-104">Tatsächlich sollten die Instanzen nur „pro Ressource“ gelten.</span><span class="sxs-lookup"><span data-stu-id="d9914-104">In reality, the instances should only be "per-resource".</span></span> <span data-ttu-id="d9914-105">Die gesuchte Sprache wird zur Ausführungszeit von der `CultureInfo.CurrentUICulture` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d9914-105">The language searched for is determined by the `CultureInfo.CurrentUICulture` at execution time.</span></span> <span data-ttu-id="d9914-106">Um dieses Problem zu beheben, wurden die APIs in ASP.NET Core 3.0 Preview 3 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="d9914-106">To eliminate the source of confusion, the APIs were marked as obsolete in ASP.NET Core 3.0 Preview 3.</span></span> <span data-ttu-id="d9914-107">Die APIs werden in einem der nächsten Releases entfernt.</span><span class="sxs-lookup"><span data-stu-id="d9914-107">The APIs will be removed in a future release.</span></span>

<span data-ttu-id="d9914-108">Weitere Kontextinformationen finden Sie unter [aspnet/AspNetCore#3324](https://github.com/aspnet/AspNetCore/issues/3324).</span><span class="sxs-lookup"><span data-stu-id="d9914-108">For context, see [aspnet/AspNetCore#3324](https://github.com/aspnet/AspNetCore/issues/3324).</span></span> <span data-ttu-id="d9914-109">Weitere Informationen finden Sie unter [aspnet/AspNetCore#7756](https://github.com/aspnet/AspNetCore/issues/7756).</span><span class="sxs-lookup"><span data-stu-id="d9914-109">For discussion, see [aspnet/AspNetCore#7756](https://github.com/aspnet/AspNetCore/issues/7756).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d9914-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d9914-110">Version introduced</span></span>

<span data-ttu-id="d9914-111">3.0</span><span class="sxs-lookup"><span data-stu-id="d9914-111">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="d9914-112">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="d9914-112">Old behavior</span></span>

<span data-ttu-id="d9914-113">Methoden wurden nicht als `Obsolete` gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="d9914-113">Methods weren't marked as `Obsolete`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="d9914-114">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="d9914-114">New behavior</span></span>

<span data-ttu-id="d9914-115">Methoden werden als `Obsolete` gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="d9914-115">Methods are marked `Obsolete`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d9914-116">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="d9914-116">Reason for change</span></span>

<span data-ttu-id="d9914-117">Die APIs stellten einen Anwendungsfall dar, der nicht empfohlen wird.</span><span class="sxs-lookup"><span data-stu-id="d9914-117">The APIs represented a use case that isn't recommended.</span></span> <span data-ttu-id="d9914-118">Der Entwurf der Lokalisierung war unklar.</span><span class="sxs-lookup"><span data-stu-id="d9914-118">There was confusion about the design of localization.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d9914-119">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="d9914-119">Recommended action</span></span>

<span data-ttu-id="d9914-120">Es wird empfohlen, stattdessen `ResourceManagerStringLocalizer` zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d9914-120">The recommendation is to use `ResourceManagerStringLocalizer` instead.</span></span> <span data-ttu-id="d9914-121">Lassen Sie die Kultur durch `CurrentCulture` festlegen.</span><span class="sxs-lookup"><span data-stu-id="d9914-121">Let the culture be set by the `CurrentCulture`.</span></span> <span data-ttu-id="d9914-122">Falls dies nicht möglich ist, erstellen Sie eine Kopie von [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18), und verwenden Sie diese.</span><span class="sxs-lookup"><span data-stu-id="d9914-122">If that isn't an option, create and use a copy of [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18).</span></span>

#### <a name="category"></a><span data-ttu-id="d9914-123">Kategorie</span><span class="sxs-lookup"><span data-stu-id="d9914-123">Category</span></span>

<span data-ttu-id="d9914-124">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d9914-124">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d9914-125">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="d9914-125">Affected APIs</span></span>

- <xref:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer>
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
