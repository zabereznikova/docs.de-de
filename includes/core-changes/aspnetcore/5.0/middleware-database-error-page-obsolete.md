---
ms.openlocfilehash: f1129500c9b779256b2650fe6fa855152cb3ae80
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811265"
---
### <a name="middleware-database-error-page-marked-as-obsolete"></a><span data-ttu-id="f3e47-101">Middleware: Datenbankfehlerseite als veraltet markiert</span><span class="sxs-lookup"><span data-stu-id="f3e47-101">Middleware: Database error page marked as obsolete</span></span>

<span data-ttu-id="f3e47-102">Die [DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0) und die zugehörigen Erweiterungsmethoden wurden in ASP.NET Core 5.0 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="f3e47-102">The [DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0) and its associated extension methods were marked as obsolete in ASP.NET Core 5.0.</span></span> <span data-ttu-id="f3e47-103">Die Middleware und Erweiterungsmethoden werden in ASP.NET Core 6.0 entfernt.</span><span class="sxs-lookup"><span data-stu-id="f3e47-103">The middleware and extension methods will be removed in ASP.NET Core 6.0.</span></span> <span data-ttu-id="f3e47-104">Die Funktionalität wird stattdessen von `DatabaseDeveloperPageExceptionFilter` und den zugehörigen Erweiterungsmethoden bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f3e47-104">The functionality will instead be provided by `DatabaseDeveloperPageExceptionFilter` and its extension methods.</span></span>

<span data-ttu-id="f3e47-105">Weitere Informationen finden Sie unter dem GitHub-Issue [dotnet/aspnetcore#24987](https://github.com/dotnet/aspnetcore/issues/24987).</span><span class="sxs-lookup"><span data-stu-id="f3e47-105">For discussion, see the GitHub issue at [dotnet/aspnetcore#24987](https://github.com/dotnet/aspnetcore/issues/24987).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f3e47-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="f3e47-106">Version introduced</span></span>

<span data-ttu-id="f3e47-107">5.0 RC 1</span><span class="sxs-lookup"><span data-stu-id="f3e47-107">5.0 RC 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="f3e47-108">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="f3e47-108">Old behavior</span></span>

<span data-ttu-id="f3e47-109">`DatabaseErrorPageMiddleware` und die zugehörigen Erweiterungsmethoden waren nicht veraltet.</span><span class="sxs-lookup"><span data-stu-id="f3e47-109">`DatabaseErrorPageMiddleware` and its associated extension methods weren't obsolete.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="f3e47-110">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="f3e47-110">New behavior</span></span>

<span data-ttu-id="f3e47-111">`DatabaseErrorPageMiddleware` und die zugehörigen Erweiterungsmethoden sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="f3e47-111">`DatabaseErrorPageMiddleware` and its associated extension methods are obsolete.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f3e47-112">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="f3e47-112">Reason for change</span></span>

<span data-ttu-id="f3e47-113">`DatabaseErrorPageMiddleware` wurde in eine erweiterbare API für die [Seite mit Ausnahmen für Entwickler](/aspnet/core/fundamentals/error-handling#developer-exception-page) migriert.</span><span class="sxs-lookup"><span data-stu-id="f3e47-113">`DatabaseErrorPageMiddleware` was migrated to an extensible API for the [developer exception page](/aspnet/core/fundamentals/error-handling#developer-exception-page).</span></span> <span data-ttu-id="f3e47-114">Weitere Informationen zur erweiterbaren API finden Sie im GitHub-Issue [dotnet/aspnetcore#8536](https://github.com/dotnet/aspnetcore/issues/8536).</span><span class="sxs-lookup"><span data-stu-id="f3e47-114">For more information on the extensible API, see GitHub issue [dotnet/aspnetcore#8536](https://github.com/dotnet/aspnetcore/issues/8536).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f3e47-115">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="f3e47-115">Recommended action</span></span>

<span data-ttu-id="f3e47-116">Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f3e47-116">Complete the following steps:</span></span>

1. <span data-ttu-id="f3e47-117">Verwenden Sie `DatabaseErrorPageMiddleware` nicht mehr in Ihrem Projekt.</span><span class="sxs-lookup"><span data-stu-id="f3e47-117">Stop using `DatabaseErrorPageMiddleware` in your project.</span></span> <span data-ttu-id="f3e47-118">Entfernen Sie beispielsweise den Methodenaufruf `UseDatabaseErrorPage` aus `Startup.Configure`:</span><span class="sxs-lookup"><span data-stu-id="f3e47-118">For example, remove the `UseDatabaseErrorPage` method call from `Startup.Configure`:</span></span>

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDatabaseErrorPage();
        }
    }
    ```

1. <span data-ttu-id="f3e47-119">Fügen Sie die Seite mit Ausnahmen für Entwickler zu Ihrem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="f3e47-119">Add the developer exception page to your project.</span></span> <span data-ttu-id="f3e47-120">Rufen Sie beispielsweise die Methode <xref:Microsoft.AspNetCore.Builder.DeveloperExceptionPageExtensions.UseDeveloperExceptionPage%2A> in `Startup.Configure` auf:</span><span class="sxs-lookup"><span data-stu-id="f3e47-120">For example, call the <xref:Microsoft.AspNetCore.Builder.DeveloperExceptionPageExtensions.UseDeveloperExceptionPage%2A> method in `Startup.Configure`:</span></span>

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }
    }
    ```

1. <span data-ttu-id="f3e47-121">Fügen Sie den Datenbankfilter für die Seite mit Ausnahmen für Entwickler zu der Dienstsammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="f3e47-121">Add the database developer page exception filter to the services collection.</span></span> <span data-ttu-id="f3e47-122">Rufen Sie beispielsweise die Methode `AddDatabaseDeveloperPageExceptionFilter` in `Startup.ConfigureServices` auf:</span><span class="sxs-lookup"><span data-stu-id="f3e47-122">For example, call the `AddDatabaseDeveloperPageExceptionFilter` method in `Startup.ConfigureServices`:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddDatabaseDeveloperPageExceptionFilter();
    }
    ```

#### <a name="category"></a><span data-ttu-id="f3e47-123">Kategorie</span><span class="sxs-lookup"><span data-stu-id="f3e47-123">Category</span></span>

<span data-ttu-id="f3e47-124">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f3e47-124">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f3e47-125">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="f3e47-125">Affected APIs</span></span>

- [<span data-ttu-id="f3e47-126">Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage</span><span class="sxs-lookup"><span data-stu-id="f3e47-126">Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage</span></span>](/dotnet/api/microsoft.aspnetcore.builder.databaseerrorpageextensions.usedatabaseerrorpage?view=aspnetcore-3.0)
- [<span data-ttu-id="f3e47-127">Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware</span><span class="sxs-lookup"><span data-stu-id="f3e47-127">Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware</span></span>](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0)

<!-- 

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage`
- `T:Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware`

-->
