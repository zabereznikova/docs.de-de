---
ms.openlocfilehash: f6fd75c5b49156f44d31c650ea452eb549f13b0e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901637"
---
### <a name="mvc-jsonresult-moved-to-microsoftaspnetcoremvccore"></a><span data-ttu-id="3eb24-101">MVC: JsonResult verschoben in Microsoft.AspNetCore.Mvc.Core</span><span class="sxs-lookup"><span data-stu-id="3eb24-101">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>

<span data-ttu-id="3eb24-102">`JsonResult` wurde in die `Microsoft.AspNetCore.Mvc.Core`-Assembly verschoben.</span><span class="sxs-lookup"><span data-stu-id="3eb24-102">`JsonResult` has moved to the `Microsoft.AspNetCore.Mvc.Core` assembly.</span></span> <span data-ttu-id="3eb24-103">Dieser Typ wurde bisher in [Microsoft.AspNetCore.Mvc.Formatters.Json](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json) definiert.</span><span class="sxs-lookup"><span data-stu-id="3eb24-103">This type used to be defined in [Microsoft.AspNetCore.Mvc.Formatters.Json](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json).</span></span> <span data-ttu-id="3eb24-104">Ein [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute)-Attribut auf Assemblyebene wurde `Microsoft.AspNetCore.Mvc.Formatters.Json` hinzugefügt, um dieses Problem für die Mehrheit der Benutzer zu beheben.</span><span class="sxs-lookup"><span data-stu-id="3eb24-104">An assembly-level [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) attribute was added to `Microsoft.AspNetCore.Mvc.Formatters.Json` to address this issue for the majority of users.</span></span> <span data-ttu-id="3eb24-105">Bei Apps, die Bibliotheken von Drittanbietern verwenden, treten möglicherweise Probleme auf.</span><span class="sxs-lookup"><span data-stu-id="3eb24-105">Apps that use third-party libraries may encounter issues.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3eb24-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="3eb24-106">Version introduced</span></span>

<span data-ttu-id="3eb24-107">3.0 Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="3eb24-107">3.0 Preview 6</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="3eb24-108">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="3eb24-108">Old behavior</span></span>

<span data-ttu-id="3eb24-109">Eine App, die eine auf Version 2.2 basierende Bibliothek verwendet, wird erfolgreich erstellt.</span><span class="sxs-lookup"><span data-stu-id="3eb24-109">An app using a 2.2-based library builds successfully.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="3eb24-110">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="3eb24-110">New behavior</span></span>

<span data-ttu-id="3eb24-111">Für eine App, die eine auf Version 2.2 basierende Bibliothek verwendet, schlägt die Kompilierung fehl.</span><span class="sxs-lookup"><span data-stu-id="3eb24-111">An app using a 2.2-based library fails compilation.</span></span> <span data-ttu-id="3eb24-112">Eine Fehlermeldung, die ähnlich wie der folgende Text lautet, wird bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="3eb24-112">An error containing a variation of the following text is provided:</span></span>

```
The type 'JsonResult' exists in both 'Microsoft.AspNetCore.Mvc.Core, Version=3.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60' and 'Microsoft.AspNetCore.Mvc.Formatters.Json, Version=2.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60'
```

<span data-ttu-id="3eb24-113">Ein Beispiel für ein solches Problem finden Sie unter [dotnet/aspnetcore#7220](https://github.com/dotnet/aspnetcore/issues/7220).</span><span class="sxs-lookup"><span data-stu-id="3eb24-113">For an example of such an issue, see [dotnet/aspnetcore#7220](https://github.com/dotnet/aspnetcore/issues/7220).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="3eb24-114">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="3eb24-114">Reason for change</span></span>

<span data-ttu-id="3eb24-115">Änderungen auf Plattformebene an der Zusammenstellung von ASP.NET Core wie unter [aspnet/Announcements#325](https://github.com/aspnet/Announcements/issues/325) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3eb24-115">Platform-level changes to the composition of ASP.NET Core as described at [aspnet/Announcements#325](https://github.com/aspnet/Announcements/issues/325).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3eb24-116">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="3eb24-116">Recommended action</span></span>

<span data-ttu-id="3eb24-117">Bibliotheken, die anhand von Version 2.2 von `Microsoft.AspNetCore.Mvc.Formatters.Json` kompiliert wurden, müssen möglicherweise erneut kompiliert werden, um das Problem für alle Benutzer zu beheben.</span><span class="sxs-lookup"><span data-stu-id="3eb24-117">Libraries compiled against the 2.2 version of `Microsoft.AspNetCore.Mvc.Formatters.Json` may need to recompile to address the problem for all consumers.</span></span> <span data-ttu-id="3eb24-118">Wenden Sie sich an den Autor der Bibliothek, wenn Sie davon betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="3eb24-118">If affected, contact the library author.</span></span> <span data-ttu-id="3eb24-119">Fordern Sie eine Neukompilierung der Bibliothek mit dem Ziel ASP.NET Core 3.0 an.</span><span class="sxs-lookup"><span data-stu-id="3eb24-119">Request recompilation of the library to target ASP.NET Core 3.0.</span></span>

#### <a name="category"></a><span data-ttu-id="3eb24-120">Kategorie</span><span class="sxs-lookup"><span data-stu-id="3eb24-120">Category</span></span>

<span data-ttu-id="3eb24-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3eb24-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3eb24-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="3eb24-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.JsonResult?displayProperty=nameWithType>

<!-- 

### Affected APIs

`T:Microsoft.AspNetCore.Mvc.JsonResult`

-->
