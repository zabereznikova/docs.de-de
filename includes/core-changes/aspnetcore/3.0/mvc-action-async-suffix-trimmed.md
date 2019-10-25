---
ms.openlocfilehash: dc9f37ae0cd6eef2c67e62421571290bba1c2233
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393936"
---
### <a name="mvc-async-suffix-trimmed-from-controller-action-names"></a>MVC: Async-Suffix aus Controlleraktionsnamen entfernt

Im Zusammenhang mit [aspnet/AspNetCore#4849](https://github.com/aspnet/AspNetCore/issues/4849) entfernt ASP.NET Core MVC das Suffix `Async` standardmäßig aus Aktionsnamen. Ab ASP.NET Core 3.0 wirkt sich diese Änderung sowohl auf das Routing als auch auf die Linkgenerierung aus.

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

Die Aktion ist über `Product/ListAsync` routingfähig. Für die Linkgenerierung muss das Suffix `Async` angegeben werden. Beispiel:

```cshtml
<a asp-controller="Product" asp-action="ListAsync">List</a>
```

#### <a name="new-behavior"></a>Neues Verhalten

In ASP.NET Core 3.0 ist die Aktion über `Product/List` routingfähig. Der Code zur Linkgenerierung sollte das Suffix `Async` nicht verwenden. Beispiel:

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

#### <a name="recommended-action"></a>Empfohlene Maßnahme

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
