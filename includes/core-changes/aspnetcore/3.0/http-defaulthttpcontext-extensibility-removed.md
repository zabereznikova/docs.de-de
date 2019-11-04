---
ms.openlocfilehash: 7b5ae84d02b83a10a4b9e002fc2ed4ee0833b84c
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198449"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a><span data-ttu-id="3d089-101">HTTP: Erweiterbarkeit von DefaultHttpContext entfernt</span><span class="sxs-lookup"><span data-stu-id="3d089-101">HTTP: DefaultHttpContext extensibility removed</span></span>

<span data-ttu-id="3d089-102">Im Rahmen der Leistungsverbesserungen in ASP.NET Core 3.0 wurde die Erweiterbarkeit von `DefaultHttpContext` aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="3d089-102">As part of ASP.NET Core 3.0 performance improvements, the extensibility of `DefaultHttpContext` was removed.</span></span> <span data-ttu-id="3d089-103">Die Klasse ist jetzt `sealed`.</span><span class="sxs-lookup"><span data-stu-id="3d089-103">The class is now `sealed`.</span></span> <span data-ttu-id="3d089-104">Weitere Informationen finden Sie unter [aspnet/AspNetCore#6504](https://github.com/aspnet/AspNetCore/pull/6504).</span><span class="sxs-lookup"><span data-stu-id="3d089-104">For more information, see [aspnet/AspNetCore#6504](https://github.com/aspnet/AspNetCore/pull/6504).</span></span>

<span data-ttu-id="3d089-105">Wenn Sie für Komponententests `Mock<DefaultHttpContext>` verwenden, nutzen Sie stattdessen `Mock<HttpContext>`.</span><span class="sxs-lookup"><span data-stu-id="3d089-105">If your unit tests use `Mock<DefaultHttpContext>`, use `Mock<HttpContext>` instead.</span></span>

<span data-ttu-id="3d089-106">Weitere Informationen finden Sie unter [aspnet/AspNetCore#6534](https://github.com/aspnet/AspNetCore/issues/6534).</span><span class="sxs-lookup"><span data-stu-id="3d089-106">For discussion, see [aspnet/AspNetCore#6534](https://github.com/aspnet/AspNetCore/issues/6534).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3d089-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="3d089-107">Version introduced</span></span>

<span data-ttu-id="3d089-108">3.0</span><span class="sxs-lookup"><span data-stu-id="3d089-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="3d089-109">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="3d089-109">Old behavior</span></span>

<span data-ttu-id="3d089-110">Klassen konnten von `DefaultHttpContext` abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="3d089-110">Classes can derive from `DefaultHttpContext`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="3d089-111">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="3d089-111">New behavior</span></span>

<span data-ttu-id="3d089-112">Klassen können nicht mehr von `DefaultHttpContext` abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="3d089-112">Classes can't derive from `DefaultHttpContext`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="3d089-113">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="3d089-113">Reason for change</span></span>

<span data-ttu-id="3d089-114">Die Erweiterbarkeit wurde anfänglich bereitgestellt, um das Pooling des `HttpContext` zu ermöglichen, sie führt aber zu einer unnötigen Komplexität und hat andere Optimierungen behindert.</span><span class="sxs-lookup"><span data-stu-id="3d089-114">The extensibility was provided initially to allow pooling of the `HttpContext`, but it introduced unnecessary complexity and impeded other optimizations.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3d089-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="3d089-115">Recommended action</span></span>

<span data-ttu-id="3d089-116">Wenn Sie in Komponententests `Mock<DefaultHttpContext>` verwenden, nutzen Sie stattdessen `Mock<HttpContext>`.</span><span class="sxs-lookup"><span data-stu-id="3d089-116">If you're using `Mock<DefaultHttpContext>` in your unit tests, begin using `Mock<HttpContext>` instead.</span></span>

#### <a name="category"></a><span data-ttu-id="3d089-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="3d089-117">Category</span></span>

<span data-ttu-id="3d089-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3d089-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3d089-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="3d089-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Http.DefaultHttpContext?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Http.DefaultHttpContext`

-->
