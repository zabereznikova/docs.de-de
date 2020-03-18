---
ms.openlocfilehash: 58b1190e3e6a3168d35700eed655f6756e076a29
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901639"
---
### <a name="mvc-async-suffix-trimmed-from-controller-action-names"></a>MVC: Async-Suffix aus Controlleraktionsnamen entfernt

Im Zusammenhang mit [dotnet/aspnetcore#4849](https://github.com/dotnet/aspnetcore/issues/4849) entfernt ASP.NET Core MVC das Suffix `Async` standardmäßig aus Aktionsnamen. Ab ASP.NET Core 3.0 wirkt sich diese Änderung sowohl auf das Routing als auch auf die Linkgenerierung aus.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Nehmen Sie den folgenden ASP.NET Core MVC-Controller an:

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

Die Aktion ist über `Product/ListAsync` routingfähig. Für die Linkgenerierung muss das Suffix `Async` angegeben werden. Zum Beispiel:

```cshtml
<a asp-controller="Product" asp-action="ListAsync">List</a>
```

#### <a name="new-behavior"></a>Neues Verhalten

In ASP.NET Core 3.0 ist die Aktion über `Product/List` routingfähig. Der Code zur Linkgenerierung sollte das Suffix `Async` nicht verwenden. Zum Beispiel:

```cshtml
<a asp-controller="Product" asp-action="List">List</a>
```

Diese Änderung hat keine Auswirkungen auf Namen, die mit dem `[ActionName]`-Attribut angegeben werden. Sie können neue Verhalten deaktivieren, indem Sie `MvcOptions.SuppressAsyncSuffixInActionNames` in `Startup.ConfigureServices` auf `false` festlegen:

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="reason-for-change"></a>Grund für die Änderung

Es gibt die Konvention, asynchrone .NET-Methoden durch das Suffix `Async` zu kennzeichnen. Wenn eine Methode jedoch eine MVC-Aktion definiert, ist das Suffix `Async` nicht wünschenswert.

#### <a name="recommended-action"></a>Empfohlene Aktion

Wenn Ihre App von MVC-Aktionen abhängig ist, die das Suffix `Async` im Namen beibehalten, führen Sie eine der folgenden Maßnahmen aus:

- Verwenden Sie das `[ActionName]`-Attribut, um den ursprünglichen Namen beizubehalten.
- Deaktivieren Sie das Umbenennen vollständig, indem Sie `MvcOptions.SuppressAsyncSuffixInActionNames` in `Startup.ConfigureServices` auf `false` festlegen:

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
