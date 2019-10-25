---
ms.openlocfilehash: 177617569a93e09f4c2a05acc21dce362edd58bc
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394311"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a><span data-ttu-id="ac685-101">HTTP: Erweiterbarkeit von DefaultHttpContext entfernt</span><span class="sxs-lookup"><span data-stu-id="ac685-101">HTTP: DefaultHttpContext extensibility removed</span></span>

<span data-ttu-id="ac685-102">Im Rahmen der Leistungsverbesserungen in ASP.NET Core 3.0 wurde die Erweiterbarkeit von `DefaultHttpContext` aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="ac685-102">As part of ASP.NET Core 3.0 performance improvements, the extensibility of `DefaultHttpContext` was removed.</span></span> <span data-ttu-id="ac685-103">Die Klasse ist jetzt `sealed`.</span><span class="sxs-lookup"><span data-stu-id="ac685-103">The class is now `sealed`.</span></span> <span data-ttu-id="ac685-104">Weitere Informationen finden Sie unter [aspnet/AspNetCore#6504](https://github.com/aspnet/AspNetCore/pull/6504).</span><span class="sxs-lookup"><span data-stu-id="ac685-104">For more information, see [aspnet/AspNetCore#6504](https://github.com/aspnet/AspNetCore/pull/6504).</span></span>

<span data-ttu-id="ac685-105">Wenn Sie für Komponententests `Mock<DefaultHttpContext>` verwenden, nutzen Sie stattdessen `Mock<HttpContext>`.</span><span class="sxs-lookup"><span data-stu-id="ac685-105">If your unit tests use `Mock<DefaultHttpContext>`, use `Mock<HttpContext>` instead.</span></span> 

<span data-ttu-id="ac685-106">Weitere Informationen finden Sie unter [aspnet/AspNetCore#6534](https://github.com/aspnet/AspNetCore/issues/6534).</span><span class="sxs-lookup"><span data-stu-id="ac685-106">For discussion, see [aspnet/AspNetCore#6534](https://github.com/aspnet/AspNetCore/issues/6534).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ac685-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="ac685-107">Version introduced</span></span>

<span data-ttu-id="ac685-108">3.0</span><span class="sxs-lookup"><span data-stu-id="ac685-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="ac685-109">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="ac685-109">Old behavior</span></span>

<span data-ttu-id="ac685-110">Klassen konnten von `DefaultHttpContext` abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ac685-110">Classes can derive from `DefaultHttpContext`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="ac685-111">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="ac685-111">New behavior</span></span>

<span data-ttu-id="ac685-112">Klassen können nicht mehr von `DefaultHttpContext` abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ac685-112">Classes can't derive from `DefaultHttpContext`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ac685-113">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="ac685-113">Reason for change</span></span>

<span data-ttu-id="ac685-114">Die Erweiterbarkeit wurde anfänglich bereitgestellt, um das Pooling des `HttpContext` zu ermöglichen, sie führt aber zu einer unnötigen Komplexität und hat andere Optimierungen behindert.</span><span class="sxs-lookup"><span data-stu-id="ac685-114">The extensibility was provided initially to allow pooling of the `HttpContext`, but it introduced unnecessary complexity and impeded other optimizations.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ac685-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="ac685-115">Recommended action</span></span>

<span data-ttu-id="ac685-116">Wenn Sie in Komponententests `Mock<DefaultHttpContext>` verwenden, nutzen Sie stattdessen `Mock<HttpContext>`.</span><span class="sxs-lookup"><span data-stu-id="ac685-116">If you're using `Mock<DefaultHttpContext>` in your unit tests, begin using `Mock<HttpContext>` instead.</span></span> 

#### <a name="category"></a><span data-ttu-id="ac685-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="ac685-117">Category</span></span>

<span data-ttu-id="ac685-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ac685-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ac685-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ac685-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Http.DefaultHttpContext?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Http.DefaultHttpContext`

-->
