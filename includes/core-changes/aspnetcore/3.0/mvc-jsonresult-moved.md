---
ms.openlocfilehash: 96c2a32dd7cca91e965601d715bbd4625bba439a
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032623"
---
### <a name="mvc-jsonresult-moved-to-microsoftaspnetcoremvccore"></a><span data-ttu-id="edd42-101">MVC: JsonResult verschoben in Microsoft.AspNetCore.Mvc.Core</span><span class="sxs-lookup"><span data-stu-id="edd42-101">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>

<span data-ttu-id="edd42-102">`JsonResult` wurde in die `Microsoft.AspNetCore.Mvc.Core`-Assembly verschoben.</span><span class="sxs-lookup"><span data-stu-id="edd42-102">`JsonResult` has moved to the `Microsoft.AspNetCore.Mvc.Core` assembly.</span></span> <span data-ttu-id="edd42-103">Dieser Typ wurde bisher in [Microsoft.AspNetCore.Mvc.Formatters.Json](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json) definiert.</span><span class="sxs-lookup"><span data-stu-id="edd42-103">This type used to be defined in [Microsoft.AspNetCore.Mvc.Formatters.Json](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json).</span></span> <span data-ttu-id="edd42-104">Ein [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute)-Attribut auf Assemblyebene wurde `Microsoft.AspNetCore.Mvc.Formatters.Json` hinzugefügt, um dieses Problem für die Mehrheit der Benutzer zu beheben.</span><span class="sxs-lookup"><span data-stu-id="edd42-104">An assembly-level [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) attribute was added to `Microsoft.AspNetCore.Mvc.Formatters.Json` to address this issue for the majority of users.</span></span> <span data-ttu-id="edd42-105">Bei Apps, die Bibliotheken von Drittanbietern verwenden, treten möglicherweise Probleme auf.</span><span class="sxs-lookup"><span data-stu-id="edd42-105">Apps that use third-party libraries may encounter issues.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="edd42-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="edd42-106">Version introduced</span></span>

<span data-ttu-id="edd42-107">3.0 Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="edd42-107">3.0 Preview 6</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="edd42-108">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="edd42-108">Old behavior</span></span>

<span data-ttu-id="edd42-109">Eine App, die eine auf Version 2.2 basierende Bibliothek verwendet, wird erfolgreich erstellt.</span><span class="sxs-lookup"><span data-stu-id="edd42-109">An app using a 2.2-based library builds successfully.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="edd42-110">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="edd42-110">New behavior</span></span>

<span data-ttu-id="edd42-111">Für eine App, die eine auf Version 2.2 basierende Bibliothek verwendet, schlägt die Kompilierung fehl.</span><span class="sxs-lookup"><span data-stu-id="edd42-111">An app using a 2.2-based library fails compilation.</span></span> <span data-ttu-id="edd42-112">Eine Fehlermeldung, die ähnlich wie der folgende Text lautet, wird bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="edd42-112">An error containing a variation of the following text is provided:</span></span>

```output
The type 'JsonResult' exists in both 'Microsoft.AspNetCore.Mvc.Core, Version=3.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60' and 'Microsoft.AspNetCore.Mvc.Formatters.Json, Version=2.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60'
```

<span data-ttu-id="edd42-113">Ein Beispiel für ein solches Problem finden Sie unter [dotnet/aspnetcore#7220](https://github.com/dotnet/aspnetcore/issues/7220).</span><span class="sxs-lookup"><span data-stu-id="edd42-113">For an example of such an issue, see [dotnet/aspnetcore#7220](https://github.com/dotnet/aspnetcore/issues/7220).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="edd42-114">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="edd42-114">Reason for change</span></span>

<span data-ttu-id="edd42-115">Änderungen auf Plattformebene an der Zusammenstellung von ASP.NET Core wie unter [aspnet/Announcements#325](https://github.com/aspnet/Announcements/issues/325) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="edd42-115">Platform-level changes to the composition of ASP.NET Core as described at [aspnet/Announcements#325](https://github.com/aspnet/Announcements/issues/325).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="edd42-116">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="edd42-116">Recommended action</span></span>

<span data-ttu-id="edd42-117">Bibliotheken, die anhand von Version 2.2 von `Microsoft.AspNetCore.Mvc.Formatters.Json` kompiliert wurden, müssen möglicherweise erneut kompiliert werden, um das Problem für alle Benutzer zu beheben.</span><span class="sxs-lookup"><span data-stu-id="edd42-117">Libraries compiled against the 2.2 version of `Microsoft.AspNetCore.Mvc.Formatters.Json` may need to recompile to address the problem for all consumers.</span></span> <span data-ttu-id="edd42-118">Wenden Sie sich an den Autor der Bibliothek, wenn Sie davon betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="edd42-118">If affected, contact the library author.</span></span> <span data-ttu-id="edd42-119">Fordern Sie eine Neukompilierung der Bibliothek mit dem Ziel ASP.NET Core 3.0 an.</span><span class="sxs-lookup"><span data-stu-id="edd42-119">Request recompilation of the library to target ASP.NET Core 3.0.</span></span>

#### <a name="category"></a><span data-ttu-id="edd42-120">Kategorie</span><span class="sxs-lookup"><span data-stu-id="edd42-120">Category</span></span>

<span data-ttu-id="edd42-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="edd42-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="edd42-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="edd42-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.JsonResult?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.JsonResult`

-->
