---
ms.openlocfilehash: 9d138f79fcede4acac837f8d7793aa343ced737c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032536"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a><span data-ttu-id="d6ca3-101">HTTP: Erweiterbarkeit von DefaultHttpContext entfernt</span><span class="sxs-lookup"><span data-stu-id="d6ca3-101">HTTP: DefaultHttpContext extensibility removed</span></span>

<span data-ttu-id="d6ca3-102">Im Rahmen der Leistungsverbesserungen in ASP.NET Core 3.0 wurde die Erweiterbarkeit von `DefaultHttpContext` aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d6ca3-102">As part of ASP.NET Core 3.0 performance improvements, the extensibility of `DefaultHttpContext` was removed.</span></span> <span data-ttu-id="d6ca3-103">Die Klasse ist jetzt `sealed`.</span><span class="sxs-lookup"><span data-stu-id="d6ca3-103">The class is now `sealed`.</span></span> <span data-ttu-id="d6ca3-104">Weitere Informationen finden Sie unter [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504).</span><span class="sxs-lookup"><span data-stu-id="d6ca3-104">For more information, see [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504).</span></span>

<span data-ttu-id="d6ca3-105">Wenn Sie für Komponententests `Mock<DefaultHttpContext>` verwenden, nutzen Sie stattdessen `Mock<HttpContext>` oder `new DefaultHttpContext()`.</span><span class="sxs-lookup"><span data-stu-id="d6ca3-105">If your unit tests use `Mock<DefaultHttpContext>`, use `Mock<HttpContext>` or `new DefaultHttpContext()` instead.</span></span>

<span data-ttu-id="d6ca3-106">Weitere Informationen finden Sie unter [dotnet/aspnetcore#6534](https://github.com/dotnet/aspnetcore/issues/6534).</span><span class="sxs-lookup"><span data-stu-id="d6ca3-106">For discussion, see [dotnet/aspnetcore#6534](https://github.com/dotnet/aspnetcore/issues/6534).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d6ca3-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d6ca3-107">Version introduced</span></span>

<span data-ttu-id="d6ca3-108">3.0</span><span class="sxs-lookup"><span data-stu-id="d6ca3-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="d6ca3-109">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="d6ca3-109">Old behavior</span></span>

<span data-ttu-id="d6ca3-110">Klassen konnten von `DefaultHttpContext` abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="d6ca3-110">Classes can derive from `DefaultHttpContext`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="d6ca3-111">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="d6ca3-111">New behavior</span></span>

<span data-ttu-id="d6ca3-112">Klassen können nicht mehr von `DefaultHttpContext` abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="d6ca3-112">Classes can't derive from `DefaultHttpContext`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d6ca3-113">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="d6ca3-113">Reason for change</span></span>

<span data-ttu-id="d6ca3-114">Die Erweiterbarkeit wurde anfänglich bereitgestellt, um das Pooling des `HttpContext` zu ermöglichen, sie führt aber zu einer unnötigen Komplexität und hat andere Optimierungen behindert.</span><span class="sxs-lookup"><span data-stu-id="d6ca3-114">The extensibility was provided initially to allow pooling of the `HttpContext`, but it introduced unnecessary complexity and impeded other optimizations.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d6ca3-115">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="d6ca3-115">Recommended action</span></span>

<span data-ttu-id="d6ca3-116">Wenn Sie in Komponententests `Mock<DefaultHttpContext>` verwenden, nutzen Sie stattdessen `Mock<HttpContext>`.</span><span class="sxs-lookup"><span data-stu-id="d6ca3-116">If you're using `Mock<DefaultHttpContext>` in your unit tests, begin using `Mock<HttpContext>` instead.</span></span>

#### <a name="category"></a><span data-ttu-id="d6ca3-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="d6ca3-117">Category</span></span>

<span data-ttu-id="d6ca3-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d6ca3-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d6ca3-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="d6ca3-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Http.DefaultHttpContext?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Http.DefaultHttpContext`

-->
