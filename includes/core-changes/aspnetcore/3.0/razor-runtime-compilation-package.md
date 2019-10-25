---
ms.openlocfilehash: 8479168b64153d3c729f8814a2649df8d46f2135
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394429"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a><span data-ttu-id="54dff-101">Razor: Laufzeitkompilierung wurde in ein Paket verschoben.</span><span class="sxs-lookup"><span data-stu-id="54dff-101">Razor: Runtime compilation moved to a package</span></span>

<span data-ttu-id="54dff-102">Die Unterstützung für die Laufzeitkompilierung von Razor-Ansichten und Razor Pages wurde in ein separates Paket verschoben.</span><span class="sxs-lookup"><span data-stu-id="54dff-102">Support for runtime compilation of Razor views and Razor Pages has moved to a separate package.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="54dff-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="54dff-103">Version introduced</span></span>

<span data-ttu-id="54dff-104">3.0</span><span class="sxs-lookup"><span data-stu-id="54dff-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="54dff-105">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="54dff-105">Old behavior</span></span>

<span data-ttu-id="54dff-106">Die Laufzeitkompilierung ist ohne zusätzliche Pakete verfügbar.</span><span class="sxs-lookup"><span data-stu-id="54dff-106">Runtime compilation is available without needing additional packages.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="54dff-107">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="54dff-107">New behavior</span></span>

<span data-ttu-id="54dff-108">Die Funktionalität wurde in das Paket `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` verschoben.</span><span class="sxs-lookup"><span data-stu-id="54dff-108">The functionality has been moved to the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>

<span data-ttu-id="54dff-109">Die folgenden APIs waren bereits in `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` zur Unterstützung der Laufzeitkompilierung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="54dff-109">The following APIs were previously available in `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` to support runtime compilation.</span></span> <span data-ttu-id="54dff-110">Die APIs sind jetzt über `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions` verfügbar.</span><span class="sxs-lookup"><span data-stu-id="54dff-110">The APIs are now available via `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.</span></span>

- `RazorViewEngineOptions.FileProviders` -> `MvcRazorRuntimeCompilationOptions.FileProviders`
- `RazorViewEngineOptions.AdditionalCompilationReferences` -> `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`

<span data-ttu-id="54dff-111">Darüber hinaus wurde `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` entfernt.</span><span class="sxs-lookup"><span data-stu-id="54dff-111">In addition, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` has been removed.</span></span> <span data-ttu-id="54dff-112">Die erneute Kompilierung von Dateiänderungen wird durch einen Verweis auf das Paket `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="54dff-112">Recompilation on file changes is enabled by default by referencing the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="54dff-113">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="54dff-113">Reason for change</span></span>

<span data-ttu-id="54dff-114">Diese Änderung war erforderlich, um die Abhängigkeit des freigegebenen ASP.NET Core-Frameworks von Roslyn aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="54dff-114">This change was necessary to remove the ASP.NET Core shared framework dependency on Roslyn.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="54dff-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="54dff-115">Recommended action</span></span>

<span data-ttu-id="54dff-116">Für Apps, die eine Laufzeitkompilierung oder eine erneute Kompilierung von Razor-Dateien erfordern, sollten die folgenden Schritte ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="54dff-116">Apps that require runtime compilation or recompilation of Razor files should take the following steps:</span></span>

1. <span data-ttu-id="54dff-117">Fügen Sie einen Verweis auf das Paket `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` hinzu.</span><span class="sxs-lookup"><span data-stu-id="54dff-117">Add a reference to the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>
1. <span data-ttu-id="54dff-118">Aktualisieren Sie die `Startup.ConfigureServices`-Methode des Projekts so, dass diese einen Aufruf von `AddMvcRazorRuntimeCompilation` enthält.</span><span class="sxs-lookup"><span data-stu-id="54dff-118">Update the project's `Startup.ConfigureServices` method to include a call to `AddMvcRazorRuntimeCompilation`.</span></span> <span data-ttu-id="54dff-119">Gehen Sie beispielsweise in `Startup.ConfigureServices` folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="54dff-119">For example, in `Startup.ConfigureServices`:</span></span>

    ```csharp
    services.AddMvc()
        .AddMvcRazorRuntimeCompilation();
    ```

#### <a name="category"></a><span data-ttu-id="54dff-120">Kategorie</span><span class="sxs-lookup"><span data-stu-id="54dff-120">Category</span></span>

<span data-ttu-id="54dff-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="54dff-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="54dff-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="54dff-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
