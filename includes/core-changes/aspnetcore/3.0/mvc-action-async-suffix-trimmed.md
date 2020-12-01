---
ms.openlocfilehash: 58b1190e3e6a3168d35700eed655f6756e076a29
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032606"
---
### <a name="mvc-async-suffix-trimmed-from-controller-action-names"></a><span data-ttu-id="3139a-101">MVC: Async-Suffix aus Controlleraktionsnamen entfernt</span><span class="sxs-lookup"><span data-stu-id="3139a-101">MVC: Async suffix trimmed from controller action names</span></span>

<span data-ttu-id="3139a-102">Im Zusammenhang mit [dotnet/aspnetcore#4849](https://github.com/dotnet/aspnetcore/issues/4849) entfernt ASP.NET Core MVC das Suffix `Async` standardmäßig aus Aktionsnamen.</span><span class="sxs-lookup"><span data-stu-id="3139a-102">As part of addressing [dotnet/aspnetcore#4849](https://github.com/dotnet/aspnetcore/issues/4849), ASP.NET Core MVC trims the suffix `Async` from action names by default.</span></span> <span data-ttu-id="3139a-103">Ab ASP.NET Core 3.0 wirkt sich diese Änderung sowohl auf das Routing als auch auf die Linkgenerierung aus.</span><span class="sxs-lookup"><span data-stu-id="3139a-103">Starting with ASP.NET Core 3.0, this change affects both routing and link generation.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3139a-104">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="3139a-104">Version introduced</span></span>

<span data-ttu-id="3139a-105">3.0</span><span class="sxs-lookup"><span data-stu-id="3139a-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="3139a-106">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="3139a-106">Old behavior</span></span>

<span data-ttu-id="3139a-107">Nehmen Sie den folgenden ASP.NET Core MVC-Controller an:</span><span class="sxs-lookup"><span data-stu-id="3139a-107">Consider the following ASP.NET Core MVC controller:</span></span>

```csharp
public class ProductController : Controller
{
    public async IActionResult ListAsync()
    {
        var model = await DbContext.Products.ToListAsync();
        return View(model);
    }
}
```

<span data-ttu-id="3139a-108">Die Aktion ist über `Product/ListAsync` routingfähig.</span><span class="sxs-lookup"><span data-stu-id="3139a-108">The action is routable via `Product/ListAsync`.</span></span> <span data-ttu-id="3139a-109">Für die Linkgenerierung muss das Suffix `Async` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3139a-109">Link generation requires specifying the `Async` suffix.</span></span> <span data-ttu-id="3139a-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3139a-110">For example:</span></span>

```cshtml
<a asp-controller="Product" asp-action="ListAsync">List</a>
```

#### <a name="new-behavior"></a><span data-ttu-id="3139a-111">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="3139a-111">New behavior</span></span>

<span data-ttu-id="3139a-112">In ASP.NET Core 3.0 ist die Aktion über `Product/List` routingfähig.</span><span class="sxs-lookup"><span data-stu-id="3139a-112">In ASP.NET Core 3.0, the action is routable via `Product/List`.</span></span> <span data-ttu-id="3139a-113">Der Code zur Linkgenerierung sollte das Suffix `Async` nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="3139a-113">Link generation code should omit the `Async` suffix.</span></span> <span data-ttu-id="3139a-114">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3139a-114">For example:</span></span>

```cshtml
<a asp-controller="Product" asp-action="List">List</a>
```

<span data-ttu-id="3139a-115">Diese Änderung hat keine Auswirkungen auf Namen, die mit dem `[ActionName]`-Attribut angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3139a-115">This change doesn't affect names specified using the `[ActionName]` attribute.</span></span> <span data-ttu-id="3139a-116">Sie können neue Verhalten deaktivieren, indem Sie `MvcOptions.SuppressAsyncSuffixInActionNames` in `Startup.ConfigureServices` auf `false` festlegen:</span><span class="sxs-lookup"><span data-stu-id="3139a-116">The new behavior can be disabled by setting `MvcOptions.SuppressAsyncSuffixInActionNames` to `false` in `Startup.ConfigureServices`:</span></span>

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="reason-for-change"></a><span data-ttu-id="3139a-117">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="3139a-117">Reason for change</span></span>

<span data-ttu-id="3139a-118">Es gibt die Konvention, asynchrone .NET-Methoden durch das Suffix `Async` zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="3139a-118">By convention, asynchronous .NET methods are suffixed with `Async`.</span></span> <span data-ttu-id="3139a-119">Wenn eine Methode jedoch eine MVC-Aktion definiert, ist das Suffix `Async` nicht wünschenswert.</span><span class="sxs-lookup"><span data-stu-id="3139a-119">However, when a method defines an MVC action, it's undesirable to use the `Async` suffix.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3139a-120">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="3139a-120">Recommended action</span></span>

<span data-ttu-id="3139a-121">Wenn Ihre App von MVC-Aktionen abhängig ist, die das Suffix `Async` im Namen beibehalten, führen Sie eine der folgenden Maßnahmen aus:</span><span class="sxs-lookup"><span data-stu-id="3139a-121">If your app depends on MVC actions preserving the name's `Async` suffix, choose one of the following mitigations:</span></span>

- <span data-ttu-id="3139a-122">Verwenden Sie das `[ActionName]`-Attribut, um den ursprünglichen Namen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="3139a-122">Use the `[ActionName]` attribute to preserve the original name.</span></span>
- <span data-ttu-id="3139a-123">Deaktivieren Sie das Umbenennen vollständig, indem Sie `MvcOptions.SuppressAsyncSuffixInActionNames` in `Startup.ConfigureServices` auf `false` festlegen:</span><span class="sxs-lookup"><span data-stu-id="3139a-123">Disable the renaming entirely by setting `MvcOptions.SuppressAsyncSuffixInActionNames` to `false` in `Startup.ConfigureServices`:</span></span>

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="category"></a><span data-ttu-id="3139a-124">Kategorie</span><span class="sxs-lookup"><span data-stu-id="3139a-124">Category</span></span>

<span data-ttu-id="3139a-125">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3139a-125">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3139a-126">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="3139a-126">Affected APIs</span></span>

<span data-ttu-id="3139a-127">Keine</span><span class="sxs-lookup"><span data-stu-id="3139a-127">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
