---
ms.openlocfilehash: 1b4b0aba3ea24682ae972bf283ac387692c83781
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75902010"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a><span data-ttu-id="64936-101">HTTP: Erweiterbarkeit von DefaultHttpContext entfernt</span><span class="sxs-lookup"><span data-stu-id="64936-101">HTTP: DefaultHttpContext extensibility removed</span></span>

<span data-ttu-id="64936-102">Im Rahmen der Leistungsverbesserungen in ASP.NET Core 3.0 wurde die Erweiterbarkeit von `DefaultHttpContext` aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="64936-102">As part of ASP.NET Core 3.0 performance improvements, the extensibility of `DefaultHttpContext` was removed.</span></span> <span data-ttu-id="64936-103">Die Klasse ist jetzt `sealed`.</span><span class="sxs-lookup"><span data-stu-id="64936-103">The class is now `sealed`.</span></span> <span data-ttu-id="64936-104">Weitere Informationen finden Sie unter [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504).</span><span class="sxs-lookup"><span data-stu-id="64936-104">For more information, see [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504).</span></span>

<span data-ttu-id="64936-105">Wenn Sie für Komponententests `Mock<DefaultHttpContext>` verwenden, nutzen Sie stattdessen `Mock<HttpContext>`.</span><span class="sxs-lookup"><span data-stu-id="64936-105">If your unit tests use `Mock<DefaultHttpContext>`, use `Mock<HttpContext>` instead.</span></span>

<span data-ttu-id="64936-106">Weitere Informationen finden Sie unter [dotnet/aspnetcore#6534](https://github.com/dotnet/aspnetcore/issues/6534).</span><span class="sxs-lookup"><span data-stu-id="64936-106">For discussion, see [dotnet/aspnetcore#6534](https://github.com/dotnet/aspnetcore/issues/6534).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="64936-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="64936-107">Version introduced</span></span>

<span data-ttu-id="64936-108">3.0</span><span class="sxs-lookup"><span data-stu-id="64936-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="64936-109">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="64936-109">Old behavior</span></span>

<span data-ttu-id="64936-110">Klassen konnten von `DefaultHttpContext` abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="64936-110">Classes can derive from `DefaultHttpContext`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="64936-111">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="64936-111">New behavior</span></span>

<span data-ttu-id="64936-112">Klassen können nicht mehr von `DefaultHttpContext` abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="64936-112">Classes can't derive from `DefaultHttpContext`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="64936-113">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="64936-113">Reason for change</span></span>

<span data-ttu-id="64936-114">Die Erweiterbarkeit wurde anfänglich bereitgestellt, um das Pooling des `HttpContext` zu ermöglichen, sie führt aber zu einer unnötigen Komplexität und hat andere Optimierungen behindert.</span><span class="sxs-lookup"><span data-stu-id="64936-114">The extensibility was provided initially to allow pooling of the `HttpContext`, but it introduced unnecessary complexity and impeded other optimizations.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="64936-115">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="64936-115">Recommended action</span></span>

<span data-ttu-id="64936-116">Wenn Sie in Komponententests `Mock<DefaultHttpContext>` verwenden, nutzen Sie stattdessen `Mock<HttpContext>`.</span><span class="sxs-lookup"><span data-stu-id="64936-116">If you're using `Mock<DefaultHttpContext>` in your unit tests, begin using `Mock<HttpContext>` instead.</span></span>

#### <a name="category"></a><span data-ttu-id="64936-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="64936-117">Category</span></span>

<span data-ttu-id="64936-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="64936-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="64936-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="64936-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Http.DefaultHttpContext?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Http.DefaultHttpContext`

-->
