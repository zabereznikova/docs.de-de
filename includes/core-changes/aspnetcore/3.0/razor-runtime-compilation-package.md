---
ms.openlocfilehash: cd13e7560ee98e0c862c5e2293521c6aaa273455
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344307"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a><span data-ttu-id="ab8c4-101">Razor: Laufzeitkompilierung wurde in ein Paket verschoben.</span><span class="sxs-lookup"><span data-stu-id="ab8c4-101">Razor: Runtime compilation moved to a package</span></span>

<span data-ttu-id="ab8c4-102">Die Unterstützung für die Laufzeitkompilierung von Razor-Ansichten und Razor Pages wurde in ein separates Paket verschoben.</span><span class="sxs-lookup"><span data-stu-id="ab8c4-102">Support for runtime compilation of Razor views and Razor Pages has moved to a separate package.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ab8c4-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="ab8c4-103">Version introduced</span></span>

<span data-ttu-id="ab8c4-104">3.0</span><span class="sxs-lookup"><span data-stu-id="ab8c4-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="ab8c4-105">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="ab8c4-105">Old behavior</span></span>

<span data-ttu-id="ab8c4-106">Die Laufzeitkompilierung ist ohne zusätzliche Pakete verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ab8c4-106">Runtime compilation is available without needing additional packages.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="ab8c4-107">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="ab8c4-107">New behavior</span></span>

<span data-ttu-id="ab8c4-108">Die Funktionalität wurde in das Paket [Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation/) verschoben.</span><span class="sxs-lookup"><span data-stu-id="ab8c4-108">The functionality has been moved to the [Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation/) package.</span></span>

<span data-ttu-id="ab8c4-109">Die folgenden APIs waren bereits in `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` zur Unterstützung der Laufzeitkompilierung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ab8c4-109">The following APIs were previously available in `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` to support runtime compilation.</span></span> <span data-ttu-id="ab8c4-110">Die APIs sind jetzt über `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions` verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ab8c4-110">The APIs are now available via `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.</span></span>

- <span data-ttu-id="ab8c4-111">`RazorViewEngineOptions.FileProviders` ist jetzt `MvcRazorRuntimeCompilationOptions.FileProviders`.</span><span class="sxs-lookup"><span data-stu-id="ab8c4-111">`RazorViewEngineOptions.FileProviders` is now `MvcRazorRuntimeCompilationOptions.FileProviders`</span></span>
- <span data-ttu-id="ab8c4-112">`RazorViewEngineOptions.AdditionalCompilationReferences` ist jetzt `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`.</span><span class="sxs-lookup"><span data-stu-id="ab8c4-112">`RazorViewEngineOptions.AdditionalCompilationReferences` is now `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`</span></span>

<span data-ttu-id="ab8c4-113">Darüber hinaus wurde `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` entfernt.</span><span class="sxs-lookup"><span data-stu-id="ab8c4-113">In addition, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` has been removed.</span></span> <span data-ttu-id="ab8c4-114">Die erneute Kompilierung von Dateiänderungen wird durch einen Verweis auf das Paket `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ab8c4-114">Recompilation on file changes is enabled by default by referencing the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ab8c4-115">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="ab8c4-115">Reason for change</span></span>

<span data-ttu-id="ab8c4-116">Diese Änderung war erforderlich, um die Abhängigkeit des freigegebenen ASP.NET Core-Frameworks von Roslyn aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="ab8c4-116">This change was necessary to remove the ASP.NET Core shared framework dependency on Roslyn.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ab8c4-117">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="ab8c4-117">Recommended action</span></span>

<span data-ttu-id="ab8c4-118">Für Apps, die eine Laufzeitkompilierung oder eine erneute Kompilierung von Razor-Dateien erfordern, sollten die folgenden Schritte ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="ab8c4-118">Apps that require runtime compilation or recompilation of Razor files should take the following steps:</span></span>

1. <span data-ttu-id="ab8c4-119">Fügen Sie einen Verweis auf das Paket `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` hinzu.</span><span class="sxs-lookup"><span data-stu-id="ab8c4-119">Add a reference to the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>
1. <span data-ttu-id="ab8c4-120">Aktualisieren Sie die `Startup.ConfigureServices`-Methode des Projekts so, dass diese einen Aufruf von `AddRazorRuntimeCompilation` enthält.</span><span class="sxs-lookup"><span data-stu-id="ab8c4-120">Update the project's `Startup.ConfigureServices` method to include a call to `AddRazorRuntimeCompilation`.</span></span> <span data-ttu-id="ab8c4-121">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ab8c4-121">For example:</span></span>

    ```csharp
    services.AddMvc()
        .AddRazorRuntimeCompilation();
    ```

#### <a name="category"></a><span data-ttu-id="ab8c4-122">Kategorie</span><span class="sxs-lookup"><span data-stu-id="ab8c4-122">Category</span></span>

<span data-ttu-id="ab8c4-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ab8c4-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ab8c4-124">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ab8c4-124">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
